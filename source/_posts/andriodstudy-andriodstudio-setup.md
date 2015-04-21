title: "Mac上的Android Studio安装"
date: 2015-04-21 21:14:54
tags: android
---

参考：http://stormzhang.com/devtools/2014/11/25/android-studio-tutorial1/

## 下载安装

- 在[Andriod Developer官网](http://developer.android.com/sdk/index.html)下载安装；

- 由于需要翻墙，但是我用的是chrome插件翻墙，安装过程中缺少部分工具；

- 安装完毕之后，在[Android Dev Tools](http://www.androiddevtools.cn/)找了如下镜像站；


    中国科学院开源协会镜像站地址:
    IPV4/IPV6: http://mirrors.opencas.cn 端口：80
    IPV4/IPV6: http://mirrors.opencas.org 端口：80
    IPV4/IPV6: http://mirrors.opencas.ac.cn 端口：80

- 打开已经装好的Andriod Studio不完全体，一直找不到哪里设置代理，后来终于找到，Mac上是没有直接的入口进入设置，需要按快捷键```command+,```，在设置里找到Http Proxy，然后填上镜像网址和端口，注意是填http://后面的，例如：mirrors.opencas.ac.cn

- Andrio Studio还会要求下载最新的Java 1.7，本身会在报错提供链接，点进去下载完就是了，还需要在配置里吧链接改成这个安装版本

- 最坑的一部，在建模拟器，因为之前未翻墙的缘故，没有安装完全在启动项目的时候会出现```CPU acceleration status: HAX is not installed on this machine (/dev/HAX is missing).```这样的报错，查了相关资料发现需要在Android SDK Manage的Extras下载安装HAXM Installer，光在Sdk下载了还不行，还要去到安装目录手动安装，网上的解释是SDK Manage只是把安装包下载了，但是安装还是要自己去安装

完成以上步骤，终于终于准备工作做完，可以开始玩Android了。

