# CSI语音技术需求总结

## 1. 基本需求概括

本贴吧包括**实用语音合成**功能，录涵盖社会、地区、生活、教育、娱乐明星、游戏、体育、企业等方方面面的**文章以及评论**

---

## 2. 业务功能图

![alt](https://github.com/2021-software-training/2021-Software-Training/blob/main/img/pic1.png)

<!-- ### 2.1 用户分类及其需求

1. 普通用户

2. 管理用户 -->

---

## 3. 对象的定义

### 3.1 用户类 User

#### 3.1.1 属性

|序号|   变量名  | 类型|含义|
|:--:|:---------:|:--:|:--:|
| 1  | name      | models.CharField     |　用户姓名　|
| 2  | password  | models.CharField     |　用户密码　|
| 3  | age       | models.IntegerField  |　用户年龄　|
| 4  | sex       | models.BooleanField  |　用户性别　|
| 5  | email     | models.EmailField    |　用户邮箱　|
| 6  | photo_url | models.ImageField    |　用户头像地址|
| 7  | admin     | models.BooleanField  |　是否为管理员|
| 8  | reg_time  | models.DateTimeField |　注册时间　|
| 9  | login_time| models.DateTimeField |　登陆时间　|
| 10 | user_id   | -------------------  |　用户ID　|

#### 3.1.2 方法

......

### 3.2 管理员类（继承于用户类）AdminUser

#### 3.2.1 属性

|序号|   变量名  | 类型|含义|
|:--:|:---------:|:--:|:--:|
| 1  | name      | models.CharField     |　用户姓名　|
| 2  | password  | models.CharField     |　用户密码　|
| 3  | age       | models.IntegerField  |　用户年龄　|
| 4  | sex       | models.BooleanField  |　用户性别　|
| 5  | email     | models.EmailField    |　用户邮箱　|
| 6  | photo_url | models.ImageField    |　用户头像地址|
| 7  | admin     | models.BooleanField  |　是否为管理员|
| 8  | reg_time  | models.DateTimeField |　注册时间　|
| 9  | login_time| models.DateTimeField |　登陆时间　|
| 10 | user_id   | -------------------  |　用户ID　|
|-|-|-|-|
| 10 | 
<!-- |10||||
|11||||
|12||||
|13||||
|14||||
|15||||
|16|||| -->

#### 3.2.2 方法

.......

### 3.3 文章类

#### 3.3.1 属性

|序号|   变量名  | 类型|含义|
|:--:|:---------:|:--:|:--:|
|1| passage_text | models.TextField      | 文章文本内容  |
|2| page_views   | models.IntegerField   | 文章浏览次数  |
|3| passage_time | models.DateTimeField  | 文章发布时间  |
|4| 评论         | 外键ForeignKey         | 文章下的评论  |
|5| passage_audio| models.FileField      | 语音的URL地址 |    
|6| title        | models.CharField      | 文章的标题    |
|7| passage_id   | ----------------------|　文章id       |
|8| author_id    | models.IntegerField   | 发布者的id|
<!-- |9||||
|10||||
|11||||
|12||||
|13||||
|||||
|||||

|||||
||||| -->
#### 3.3.2 方法

........

### 3.4 评论类 Comment

#### 3.4.1 属性

|序号|   变量名  | 类型|含义|
|:--:|:---------:|:--:|:--:|
|1| comment_text | models.TextField | 评论文本内容      |
|2| comment_audio| models.FileField | 语音的URL地址     |
|3| comment_time | models.DateTimeField | 评论的时间    |
|4| comment_id   | ---------------------| 评论的id      |
|5| passage_id   | models.IntegerField  |　文章id       |
|6| author_id    | models.IntegerField  | 发布者的id    |
<!-- |7| |||
|8| |||
|||||
|||||
|||||
||||| -->

#### 3.4.2 方法

..........

### 3.5 语音类 Audio

#### 3.5.1 属性

|序号|   变量名  | 类型|含义|
|:--:|:---------:|:--:|:--:|
|1| app_id      | models.FileField | 百度语音合成所需要的appID |
|2| api_key     | models.FileField | 百度语音合成所需要的apiKey|
|3| secret_key  | models.FileField | 语音合成所需要的secretKey|
|4| volume      | models.IntegerField | 百度语音合成的音量|
|5| vol_person  | models.IntegerField | 百度语音合成的发声人|
|6| vol_speed   | models.IntegerField | 百度语音合成的语速|
|7| vol_pitch   | models.IntegerField | 百度语音合成的音调|

#### 3.5.2 方法

....

---

## 4. 具体开发流程

### 4.1 基本知识的学习


#### 4.1.1 前端部分

前端主要包括以下内容

* [HTML+CSS入门](https://chinese.freecodecamp.org/learn/responsive-web-design/basic-html-and-html5/say-hello-to-html-elements)

* [JavaScript入门](https://wangdoc.com/javascript/index.html)

* [VUE框架官方文档](https://v3.cn.vuejs.org/guide/introduction.html)

* [网站快速成型工具（基于VUE3.0）](https://element-plus.gitee.io/#/zh-CN)

**学习目标：**
1. 掌握基本的html、css、JavaScript的语法并编写简单的界面

2. 能够看懂简单的VUE的框架并用WebStorm使用基础部分

3. 能够根据用户操作向后端发送请求

4. 能够使用IDE(WebStorm)进行基本的Git操作（这个我会教）

5. coding符合规范的命名规则和写法

6. 其他.....（想到了再补充）

#### 4.1.2 后端部分

* [HTML入门](https://chinese.freecodecamp.org/learn/responsive-web-design/basic-html-and-html5/say-hello-to-html-elements)

* [MySql数据库语法/教程](https://www.runoob.com/mysql/mysql-tutorial.html)

* [Django官方文档快速入门](https://docs.djangoproject.com/zh-hans/3.2/intro/tutorial01/)

* [Django-RESTful](https://zhuanlan.zhihu.com/p/32126430)

**学习目标：**

1. 掌握基本的html语法，能够看懂基本的html语法即可

2. 能够使用PyCharm创建Django框架进行基本的操作

3. 能够以RESTful方式与前台进行交互

4. 能够使用IDE(PyCharm)进行基本的Git操作（这个我会教）

5. coding符合规范的命名规则和写法

6. 对MySql数据库操作的基本语法熟悉

7. 其他.....（想到了再补充）

**建议时间：`1~2天完成`**

### 4.2 用户的注册和登陆

#### 4.2.1 原型图

如图所示：

![alt](https://github.com/2021-software-training/2021-Software-Training/blob/main/img/pic2.png)

![alt](https://github.com/2021-software-training/2021-Software-Training/blob/main/img/pic3.png)

#### 4.2.2 输入

1. 登陆

* 用户名
* 密码
* 记住密码（可选）

2. 注册

* 用户名
* 密码
* 确认密码
* 性别
* 年龄
* 邮箱

备注：我有登陆界面的模板

#### 4.2.3 输出及操作

> 点击登陆后：

*	如果用户名或密码 **为空** 的话，输出“用户名不能为空”或“密码不能为空”提示；
*	如果用户名密码 **输入错误** ，输出“用户名或密码错误”提示；
*	如果选中 **记住密码** 的话，下次登录密码自动输入；
*	如果 **填写正确** ，进入“我的文章模块”；
*   点击 **注册** 后，进入“注册”界面。

> 点击注册后：

*	如果用户名或密码或确认密码或邮箱为空的话，输出“用户名不能为空”或“密码不能为空”或“确认密码不能为空”或邮箱地址不能为空提示；
*	如果用户名已存在的话，输出“用户名已存在提示”；
*	如果密码与确认密码不一致，输出“密码与确认密码不一致”提示；
*	如果密码不是6个字节，输出“密码为6位提示”；
*	如果邮箱地址格式不对，输出“邮箱地址格式错误”提示；
*	如果填写正确，返回用户登录模块。

> 点击返回：

* 返回登录界面。

#### 4.2.4 开发要点
<!-- 
<p style="color: red;">此时我们只需要实现最基本的登陆功能，无须实现登陆后显示的主界面</p> -->

1. 此时我们只需要实现最基本的登陆功能，无须实现登陆后显示的主界面

2. 前端判断是否输入符合格式（也可以由后端来判断是否符合格式，到时候看情况）如果符合格式则向后端发送请求，后端操控数据库添加用户

**建议时间：`不多于1天完成`**

### 4.3 实现登陆后的菜单框架

#### 4.3.1 原型图

如图所示

![alt](https://github.com/2021-software-training/2021-Software-Training/blob/main/img/pic4.png)

#### 4.3.2 输入

**无**

#### 4.3.3 输出及操作

*	点击左边菜单选项：进入不同模块
*	点击修改密码：进入修改密码模块
*	点击退出登录：退出登录，进入登录模块

#### 4.3.4 开发要点

1. 只需要实现界面转换，不需要显示具体的界面中详细内容。

2. 在点击左边的菜单栏后，前端向后端发送界面改变的请求，~~后端接收到消息之后向前端发送Json数据~~（此部分先不需要发送具体的消息，因为我们现在只需要界面转换即可）

**建议时间：`一天完成`**

### 4.4
