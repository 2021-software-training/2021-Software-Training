# 今日任务(7.9)

## 1. 概述

由于随着页面基本上都写了挺多了，后端大家对RESTful形式的前后端分离也有了初步的了解，我们可以开始试着写一些后端接口。

今日主要任务包括：

1. 通过IDE来对Git的基本使用

2. 模型新增(如文章和评论，需要细致讨论一下)

3. 写接口

4. 前端完善界面

## 2. 前端需要做的

### 2.1 界面修改

1. 注册界面修改，需要加入邮箱的输入；

2. 注册和登陆界面需要加上背景

### 2.2 界面新增

5个界面(主页、所有文章、我的、设置、用户管理)各自单独的界面显示

---

## 3. 后端需要写的接口API(之后再补充)

|接口名|接口作用|接口参数|返回值|POST/GET|是否完成|备注|
|:--:|:-----:|:--:|:--:|:--:|:--:|:--:|
|login|登陆|username, password|judge, token|GET|是|无|
|register|注册|username, password, age, sex, CAPTCHA|judge|GET|否|无|
|check_email|邮箱验证|email|无|POST|否|[Django文档:发送邮件](https://docs.djangoproject.com/zh-hans/3.2/topics/email/)|
|check_phone_num|手机号验证|phone|无|POST|否|可以考虑去掉这个，因为发短信的接口一般是要钱的|
|get_passage_list|获得所有文章的文章列表|page_num|views, comments, title|GET|否|无|
|add_passage|发布新文章|passage的各个属性|无|GET|否|还需要讨论具体属性有啥|
|get_one_passage|获得一个文章的详细数据(如评论)|文章id|-|GET|否|还需讨论具体属性有啥|
|add_comment|新增评论|comment的属性|-|POST|否|还需要讨论具体有啥|
<!-- ||||||
||||||
||||||
||||||
||||||
||||||
||||||
||||||
||||||
||||||
||||||
|||||| -->

## 4. 其他已知问题

POST在带有参数的时候，Django无法接收，目前还没有解决，所以暂时一切POST请求都改写为GET