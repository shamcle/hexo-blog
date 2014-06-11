title: Python 定时器解决方案 
date: 2014-06-12 00:52:52
tags: python
---

[APScheduler](https://pypi.python.org/pypi/APScheduler)

## 安装

    easy_install apscheduler

### 包含

    from apscheduler.scheduler import Scheduler
    schedudler = Scheduler(daemonic = False)

daemonic属性是用来设置是否以后台线程的方式运行，默认值为true就是他会随主程序的结束一起结束，若设成false则只能手动结束（实质是调用python内部类threading中的setDaemon方法）。APScheduler是以线程池的多线程的方式并发执行任务的，线程数字可自定义

<!-- more -->

### 模式一：指定时间执行

    scheduler.add_date_job(job_function, datetime.now() + timedelta(seconds=15), name='job1', args=[datetime.now()])

15秒钟后执行一次

### 模式二：间隔执行

    scheduler.add_interval_job(job_function, hours=2, start_date='2014-06-12 09:51:59') 

从2014-06-12 09:51:59开始每2个小时执行一次

**装饰器模式**

    @interval_schedule(job_function, hours=2, start_date='2014-06-12 09:51:59') 

### 模式三：crontab

    scheduler.add_cron_job(job_function, month='6-8,11-12', day='12', hour='0-3')

6月到8月，11月到12月的12号的0点到3点执行

**装饰器模式**

    @cron_schedule(job_function, month='6-8,11-12', day='12', hour='0-3')

### 启动

    scheduler.start()

更多方法请参考：scheduler.py

还有对定时任务的一些操作和数据持久化，可以参考源码。






