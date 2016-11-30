---
title: Chrome插件开发 - Hello world
date: 2016-11-30 12:01:24
categories: programming
tags: [web, chrome]
---

在学校选的projet是关于chrome插件开发的，这里记录一下。

# Hello world!

凡事先从hello world开始。

1. 阅读chrome的开发手册，新建一个项目文件夹

2. 我们需要manifest.json文件，告诉chrome我们的配置，去哪里找我们文件。

   下面的写的是我们目前的设置，只写hello world的话只需要配置基本的设置以及default_popup。

   ```json
   {
     "manifest_version": 2,
     "name": "TrelloGement",
     "description": "Organiser ses recherches d'appartement sur Paris grâce à Trello!",
     "version": "0.2.1",
     "browser_action": {
       "default_icon": "icon.png",
       "default_popup": "popup.html"
     },
     "background": {
       "scripts": ["background.js", "jquery-3.1.1.min.js", "client.js"]
     },
     "permissions": ["activeTab", "storage", "tabs", "https://api.trello.com/*", "https://trello.com/*"]
   }
   ```

3. 新建popup.html

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
   	<meta charset="UTF-8">
   	<title>Trellogement</title>
   </head>
   <body>
     <h1> Hello, world! </h1>
   </body>
   </html>
   ```

4. 一个简单的Hello world就实现了，在chrome加载这个文件夹作为未打包的插件，在popup的位置点击可以看到“Hello, world!”

