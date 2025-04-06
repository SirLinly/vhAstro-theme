---
title: ${pageContext.request.contextPath}获取绝对路径乱码问题，导致jsp页面获取不到静态资源
date: 2022-03-24 00:05:00
updated: 2022-03-25 12:06:55
categories: 经验教程
tags:
- IntelliJ IDEA
- jsp
id: 7436
cover: 
---
## ${pageContext.request.contextPath}获取绝对路径乱码问题
### 问题
　　 **Maven搭建的SSM项目，jsp页面用${pageContext.request.contextPath}获取绝对路径，运行后页面获取不到静态资源。** 
#### 截图
![QQ截图20220324134751.png](https://img.bltang.cc/img/2022/03/1473072443.png)

### 解决方法
IDEA创建项目时web.xml中的头文件默认版本是2.3，需要改成3.0，如下所示。
![QQ截图20220325120357.png](https://img.bltang.cc/img/2022/03/1300116343.png)

```haml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xmlns="http://java.sun.com/xml/ns/javaee"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_3_0.xsd"
         id="WebApp_ID" version="3.0">
</web-app>
```
### 效果
重新发布项目 可见。
