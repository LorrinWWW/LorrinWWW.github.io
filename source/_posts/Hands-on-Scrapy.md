---
title: Hands on Scrapy
date: 2017-06-21 20:00:27
categories: [programming]
tags: [scrapy, python, spider, crawl]
hidden: true
---

# 各个结构

## 新建项目

```bash
scrapy startproject <project_name> [project_dir]
```

文件结构：

```
├── author.json
├── runSpider.py
├── scrapy.cfg
└── projectname
    ├── __init__.py
    ├── items.py
    ├── middlewares.py
    ├── pipelines.py
    ├── settings.py      // 设置
    └── spiders          // 具体的爬虫
        ├── __init__.py
        ├── spider0.py
        └── spider1.py
```

## 爬虫主体

示例如下，一个带登录的爬虫。

```python
from scrapy.spiders import CrawlSpider
from scrapy.selector import Selector
from scrapy.http import Request, FormRequest

from tutorial.settings import *

class SampleSpider(CrawlSpider):
    name = 'sampleSpider'
    allowed_domains = ['sample.com']
    start_url = 'https://sample.xxx.xx.x.x.x.xxx'

    def __init__(self):
        self.headers = HEADER
    
    def start_requests(self):
        return [Request(
            "https://sample.com/signin",
            meta = {'cookiejar' : 1},
            callback = self.post_login
        )]

    def post_login(self, response):
        return [FormRequest(
            'https://www.sample.com/login/',
            method='POST',
            meta={'cookiejar': response.meta['cookiejar']},
            formdata = {
                'email':'xxxx',
                'password':'yyyy',
            },
            callback = self.after_login
        )]

    def after_login(self, response):
        return [Request(
            self.start_url,
            meta={'cookiejar': response.meta['cookiejar']},
            callback=self.parse,
            errback=self.parse_err,
        )]
    
    def parse(self, response):
        # do something
        pass

    def parse_err(self, response):
        print('eeeerrrrrrooooooorrrrrr!!!!!!')

```

## 选择器

#### 自带选择器：

- CSS Selector
- XPath

一般情况下CSS选择期即可满足要求，语法忘了google即可。

```python
query = 'h1.title::text'
response.css(query).extract()[0]
response.css(query).extract_first()
# response.css(query).extract_first().strip() # 一般用strip清理多余的空格等
```

#### BeautifulSoup

方便，但是慢。不能解析js。

#### lxml

用于解析XML，当然也可用于HTML。

## Item

内建的一种抽象数据结构类，自行定义所需要的。

使用时可以研究下ItemLoader。

#### Item Pipeline

Item被返回是被送往Item Pipeline进行进一步处理，即每次return Item等操作时，都会调用pipeline中的相应函数。一般有以下用途：

- 验证Item

  ```python
  from scrapy.exceptions import DropItem

  class PricePipeline(object):

      vat_factor = 1.15

      def process_item(self, item, spider):
          if item['price']:
              if item['price_excludes_vat']:
                  item['price'] = item['price'] * self.vat_factor
              return item
          else:
              raise DropItem("Missing price in %s" % item)
  ```

- 写到JSON文件

  ```python
  import json

  class JsonWriterPipeline(object):

      def open_spider(self, spider):
          self.file = open('items.jl', 'w')

      def close_spider(self, spider):
          self.file.close()

      def process_item(self, item, spider):
          line = json.dumps(dict(item)) + "\n"
          self.file.write(line)
          return item
  ```

- 写到MongoDB

  ```python
  import pymongo

  class MongoPipeline(object):

      collection_name = 'scrapy_items'

      def __init__(self, mongo_uri, mongo_db):
          self.mongo_uri = mongo_uri
          self.mongo_db = mongo_db

      @classmethod
      def from_crawler(cls, crawler):
          return cls(
              mongo_uri=crawler.settings.get('MONGO_URI'),
              mongo_db=crawler.settings.get('MONGO_DATABASE', 'items')
          )

      def open_spider(self, spider):
          self.client = pymongo.MongoClient(self.mongo_uri)
          self.db = self.client[self.mongo_db]

      def close_spider(self, spider):
          self.client.close()

      def process_item(self, item, spider):
          self.db[self.collection_name].insert_one(dict(item))
          return item
  ```

等。

# 例子

## 登陆

- POST表单模拟登录

  1. 首先要找到表单，在打开chrome的控制台，切换到"network"。
  2. 手动登录，并停止network录制(不然可能随着页面的跳转，记录都被刷掉了)。
  3. 依次查找，主要看headers中的form data，是否有和登录相关的信息
  4. 模拟发送该表单(注意Request url)

  具体写法见上面爬虫的例子

  如果有验证码的情况，简单的可以用pil，复杂的可能就比较困难了，可以考虑使用cookie模拟登录。

- 利用Cookie模拟登录

  1. 同样思路，打开network，并手动登录
  2. 在headers中找cookies
  3. 将cookies整理成字典形式，作为Request的参数即可


## CrawlSpider

区别于普通的Spider，CrawSpider更适合于用于爬全网，注意不能覆盖parse函数。

CrawlSpider通过Rule来限定搜索区域，parse会根据follow、callback的情况作出不同反应。

如果需要登录，则使用表单登录后，注意最后一次callback需设置为parse，否则程序将会停止，CrawlSpider失效。