## 环境依赖
> * Python环境： Django1.8以上+Beatuifulsoup4(4.5.1)+Celery(3.1.25)+Django-celery(3.1.17)+lxml+MysqlDB+redis(2.10.5)+Scrapy(1.2.0)+scrapy-redis(0.6.3)+Unipath(1.1)+Twisted(16.6.0)
> * 数据库环境：MySQL5以上、Redis 3以上
> * 操作系统： Windows XP以上

## 数据来源
> * [百才招聘网](http://wuhan.baicai.com/)
> * [中华英才网](http://www.chinahr.com/wuhan/)
> * [前程无忧](http://www.51job.com/)
> * [智联招聘](https://www.zhaopin.com/)

## 信息格式

**网址**、**工作**、**工作类别**、**平均月薪**、**公司名称**、**工作地点**、**工作经验**、**学历**、**学位**、**职业描述**

## 部署方式
### 1. 安装所需要的库
+ bs4
+ scrapy
+ redis
+ scrapy-redis
+ pywin32
+ jieba
+ MySQLdb
+ django
+ celery（3.1.25）[ **windows不支持4**]
+ unipath
+ django-celery

## 2. 启动相关服务
> **Redis服务**
> **MySQL服务**

### 3. 启动程序
+ 启动定时任务
  + **celery -A JobEvaluating worker --loglevel=INFO**
  + **celery -A JobEvaluating beat -s celerybeat-schedule**
+ 同步数据库
  + **python manage.py makemigrations**
  + **python manage.py migrate**
+ 启动Django(python manage.py runserver)
