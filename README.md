## Django搭建博客
![py27](https://camo.githubusercontent.com/392a32588691a8418368a51ff33a12d41f11f0a9/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f707974686f6e2d322e372d6666363962342e737667)
  [![](https://img.shields.io/badge/Django-1.10-green.svg)](http://www.spiderpy.cn/blog/)
[![](https://img.shields.io/badge/Powered%20by-@j_hao104-blue.svg)](http://www.spiderpy.cn/blog/)

使用Django快速搭建博客
### 要求
* Python: 2.X
* Django: 1.10.x
* Mysql

### 示例博客：<http://www.spiderpy.cn/blog>

### 特点

* 博客文章 markdown 渲染，代码高亮
* 三方社会化评论系统支持(畅言)
* 三种皮肤自由切换
* 阅读排行榜/最新评论
* 多目标源博文分享
* 博文归档
* 友情链接

### 下载
```
wget https://github.com/jhao104/django-blog/archive/master.zip
or
git clone git@github.com:jhao104/django-blog.git
```

### 安装
```
pip install -r requirements.txt  #安装所有依赖
setting.py配置自己的数据库
配置畅言：到http://changyan.kuaizhan.com/注册站点,将templates/message.html中js部分换成你在畅言中生成的js。
python manage.py makemigrations blog
python manage.py migrate
python manage.py runserver
```

### 使用

```python
# 初始化用户名密码
python manage.py createsuperuser
# 按照提示输入用户名、邮箱、密码即可
# 登录后台 编辑类型、标签、发布文章等
http://ip:port/admin

```

浏览器中打开<http://127.0.0.1:8000/>即可访问

## Screen Shots

* 首页
![首页](./doc/image/image1.png)

* 文章列表
![文章列表](./doc/image/image2.png)

* 文章内容
![文章内容](./doc/image/image3.png)

## 历史版本

* [黑白简约版](https://github.com/jhao104/django-blog/tree/v1.0)

## Trouble shooting

1. `django.core.exceptions.ImproperlyConfigured`
```
django.core.exceptions.ImproperlyConfigured: Specifying a namespace in include() without providing an app_name is not supported. Set the app_name attribute in the included module, or pass a 2-tuple containing the list of patterns and app_name instead.
```
[solution](https://stackoverflow.com/questions/48608894/specifying-a-namespace-in-include-without-providing-an-app-name)

2. `AttributeError: module 'blog.views' has no attribute 'GetComment'`
```
File "/Users/kylewong/Playground/Django/django-blog/blog/urls.py", line 25, in <module>
  url(r'^getComment/$', views.GetComment, name='get_comment'),
AttributeError: module 'blog.views' has no attribute 'GetComment'
```
Solution: Comment `url(r'^getComment/$', views.GetComment, name='get_comment'),`

3. Django admin login

  请输入一个正确的 用户名 和密码. 注意他们都是区分大小写的. [solution](https://stackoverflow.com/questions/26205423/django-admin-login)
