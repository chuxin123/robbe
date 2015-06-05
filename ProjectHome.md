## [最新动态: robbe-1.6.0发布了](http://www.oschina.net/news/47385/robbe-1-6-0) ##
## [robbe开源中国git托管](http://git.oschina.net/lionsoul/robbe) ##


## 一。robbe php开源高性能中文分词扩展 ##

robbe是建立在friso中文分词上的一个高性能php中文分词扩展。[了解friso](http://code.google.com/p/friso/)

1.目前最高版本：friso 1.6.0。

2.mmseg四种过滤算法，分词准确率达到了98.41%。

3.详细功能，请访问friso官方首页：[friso](http://code.google.com/p/friso/)。


## 二。分词速度 ##

测试环境：2.8GHZ/2G/Ubuntu

简单模式：3.1M/秒

复杂模式：1.4M/秒

（因为php中的大量字符串的复制，性能比friso有点下降）。


## 三。使用方法 ##

[Linux如何自主编译安装robbe？](http://www.oschina.net/question/853816_119031)

[Win下如何自己编译安装robbe?](http://www.oschina.net/question/853816_135216)

[robbe安装ueaner博客](http://blog.aboutc.net/php/59/php-installation-robbe-chinese-word-extension)

1。下载：

(1).在[friso下载](http://code.google.com/p/friso/downloads/list)下载最新的friso附件。

(2).在[robbe下载](http://code.google.com/p/robbe/downloads/list)下载最新的robbe附件。

2.安装：

(1). winNT系统：
复制friso-{version}/lib/win32/下的friso.dll和robbe-{version}/lib/win32/下的php\_robbe.dll到php的ext扩展目录下。

(2). linux系统：
同上（或者自己make去安装，先安装friso，在安装robbe）。

(3). php.ini配置：

```
//1.加入扩展：

extension=php_robbe.dll   //win
extension=php_robbe.so    //linux

//2.加入robbe php配置：

[robbe]
;configuration file for robbe.
robbe.ini_file = friso.ini文件的绝对地址。

```

3。php测试：

(1).运行phpinfo.php

看到：如下的配置信息表示配置成功了：

```
             robbe

Robbe Support	enabled
Version	        1.1
Bug Report	chenxin619315@gmail.com
Learn More	http://code.google.com/p/robbe
C Edition	http://code.google.com/p/friso
Java Edition	http://code.google.com/p/jcseg

Directive	Local Value	Master Value
robbe.ini_file	friso.ini地址	friso.ini地址
```

(2).运行robbe\_php下的两个php文件,你懂得。

[robbe函数集合和使用实例](http://code.google.com/p/robbe/wiki/RobbeFunctions)