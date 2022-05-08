---
title: 'MongoDB, Docker and Python'
date: 2017-06-22 14:53:44
categories: [programming]
tags: [mongo, mongodb, docker, python]
hidden: true
---

## 安装

需要预先安装

- Docker
- Python
  - pymongo

## Docker

创建容器。若只使用一次，可以加上--rm；若要后台运行，加上-d

27017是mongodb的默认端口

```Bash
docker run --name my-mongo -it -p 27017:27017 mongo
```

创建完成后需要使用时：

```Shell
docker start my-mongo
```

## Python

```python
from pymongo import MongoClient

# connection
client = MongoClient()
client.server_info()
db = client.test

# loop cursor
cursor = db.cars.find()
for doc in cursor:
    print(doc)

# or just find one
db.cars.find_one()
```