---
title: dubbo-admin修改分组
tags:
  - dubbo
categories: 
  - 组件配置
date: 2018-05-17 10:18:05
---

## Dubbo-admin配置分组信息


### 前言
>日常我们使用dubbo-admin作为控制器管理应用和服务，同时可以配置路由，管理查询服务是否正常上线。搭建的过程中我们也会去配置比较多的东西，关于搭建的教程大家可以移步：[CSDN:dubbo-admin管理平台搭建](https://blog.csdn.net/u013142781/article/details/50396621)，这里主要给大家介绍关于分组的配置   

<!--more-->  
### 1.常用的修改
```
webapp/WEB-INF/dubbo.properties
```
通常我们会比较习惯在这里面修改zk的地址和对应的账号密码  
  
### 2.分组的修改
然而我们可能会在注册ZK的时候增加分组的概念来增加ZK的公用性。因此在搭建dubb-admin的时候需要修改对应的分组。对应的配置文件在
```
/META-INF/spring/dubbo-admin.xml
```
从这个配置文件我们可以看出来，实际上这个文件就是dubb-admin的dubbo配置文件，这里面找到
```
<dubbo:registry address="${dubbo.registry.address}" check="false" file="false" />
```
在这里按照正常dubbo分组配置方法增加group配置即可，然后重启dubbo-admin就可以正常看到相应的分组注册上线   
   
><font color = red>**当然这里也需要注意的一个dubbo-admin正常也只注册一个分组比较容易清晰的管理一个组下的所有服务**</font>