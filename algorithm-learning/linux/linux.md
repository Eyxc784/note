linux

# 课程目录

![1714836892679](linux.assets/1714836892679.png)

# 入门

## linux系统

![1714837143111](linux.assets/1714837143111.png)

## linux发行版

由于linux内核是免费开源的，任何人都可以在linux内核代码的基础上实现自己的系统级应用程序组成一个自己的linux系统。这被称为linux发行版。

![1714837405625](linux.assets/1714837405625.png)

## 安装linux系统

一个是使用虚拟机软件Vmware，一个是网上买台服务器。还可以给你自己电脑安装一个linux系统。最后一个是WSL。

![1714837761705](linux.assets/1714837761705.png)

VMware这种方法不太建议，因为是使用软件虚拟一整个硬件系统，在虚拟出来的硬件系统上运行linux系统，吃资源。

可以买台云服务器，新用户100块用一年。而且有公网IP，不会遇到网络问题。

在电脑上装双系统，这个麻烦，也不建议。

WSL可以学学。

![1714838084430](linux.assets/1714838084430.png)

可以看到WSL这种比装双系统要简单。[第一章-08-扩展-Win10配置WSL(Ubuntu)环境_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1n84y1i7td?p=9&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

## 使用操作系统

![1714838417321](linux.assets/1714838417321.png)

![1714838528340](linux.assets/1714838528340.png)



finalshell远程连接工具

我买的服务器，这个简单、易用。[第一章-07-远程连接Linux系统_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1n84y1i7td?p=8&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

## linux目录结构

![1714839856268](linux.assets/1714839856268.png)

![1714839900274](linux.assets/1714839900274.png)



linux基础命令

![1714840276706](linux.assets/1714840276706.png)

# linux基础命令

ls 列出当前路径下的所有内容

![1714902072015](linux.assets/1714902072015.png)

cd

![1714902112301](linux.assets/1714902112301.png)

pwd

![1714902144271](linux.assets/1714902144271.png)

![1714902213584](linux.assets/1714902213584.png)

![1714902328944](linux.assets/1714902328944.png)



![1714902497656](linux.assets/1714902497656.png)![1714902525655](linux.assets/1714902525655.png)



![1714902846672](linux.assets/1714902846672.png)



![1714913365827](linux.assets/1714913365827.png)

![1714913386250](linux.assets/1714913386250.png)

![1714914395828](linux.assets/1714914395828.png)

![1714914448430](linux.assets/1714914448430.png)

![1714913542010](linux.assets/1714913542010.png)

![1714914548023](linux.assets/1714914548023.png)

![1714914691397](linux.assets/1714914691397.png)

![1714917333794](linux.assets/1714917333794.png)

![1714917956929](linux.assets/1714917956929.png)

![1714920830088](linux.assets/1714920830088.png)

![1714921419501](linux.assets/1714921419501.png)

![1714921522499](linux.assets/1714921522499.png)

![1714922972408](linux.assets/1714922972408.png)

vi/vim

会用[第二章-13-vi编辑器_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1n84y1i7td?p=23&vd_source=5a374f315281b0338a0b7fd69b8b8e98)

# linux权限控制

![1714924774534](linux.assets/1714924774534.png)

![1714924805679](linux.assets/1714924805679.png)

![1714924877407](linux.assets/1714924877407.png)

![1714924942675](linux.assets/1714924942675.png)

![1714924976930](linux.assets/1714924976930.png)



![1714925296772](linux.assets/1714925296772.png)

![1714977074602](linux.assets/1714977074602.png)

![1714977258467](linux.assets/1714977258467.png)

![1714977221213](linux.assets/1714977221213.png)



![1714977312755](linux.assets/1714977312755.png)



![1714977382190](linux.assets/1714977382190.png)

![1714977411429](linux.assets/1714977411429.png)

![1714977470246](linux.assets/1714977470246.png)

![1714977559563](linux.assets/1714977559563.png)

![1714977820792](linux.assets/1714977820792.png)

![1714977846420](linux.assets/1714977846420.png)

![1714977921131](linux.assets/1714977921131.png)

# linux实用操作

## 常用快捷键

![1714978280969](linux.assets/1714978280969.png)

![1714978288841](linux.assets/1714978288841.png)

![1714978313638](linux.assets/1714978313638.png)

![1714978329158](linux.assets/1714978329158.png)

![1714978340196](linux.assets/1714978340196.png)

## 软件安装

![1714984587714](linux.assets/1714984587714.png)

![1714984638500](linux.assets/1714984638500.png)

![1714984684236](linux.assets/1714984684236.png)

## systemctl命令

![1714984774678](linux.assets/1714984774678.png)



![1714985139873](linux.assets/1714985139873.png)

有的软件安装后会自动集成到systemctl中，有的则不会，因此需要手动添加。

## 软链接

![1714985308683](linux.assets/1714985308683.png)

举例：

```bash
ln -s /etc/yum.conf ~/yum.conf  
```

在`~/yum.conf`路径下创建这个文件`/etc/yum.conf`的一个快捷方式

```bash
ln -s /etc/yum ~/yum
```

在`~/yum`路径下创建这个文件夹`/etc/yum`的一个快捷方式

![1714985711651](linux.assets/1714985711651.png)

## date与修改时区

![1714988862945](linux.assets/1714988862945.png)

![1714988887667](linux.assets/1714988887667.png)

![1714988988588](linux.assets/1714988988588.png)

![1714989033608](linux.assets/1714989033608.png)

![1714989051645](linux.assets/1714989051645.png)

## IP地址与主机名

![1714989118062](linux.assets/1714989118062.png)

![1714990711669](linux.assets/1714990711669.png)

这俩个都可以指代本机

![1714990761588](linux.assets/1714990761588.png)

![1714990902403](linux.assets/1714990902403.png)

![1714990930361](linux.assets/1714990930361.png)

![1714990954606](linux.assets/1714990954606.png)

在windows系统中配置私人地址本，管理员权限编辑hosts文件，

![1714990993733](linux.assets/1714990993733.png)

设置好以后，在finalshell里面把192.168.88.130这个本机地址换成centos就行。

![1714991110306](linux.assets/1714991110306.png)

## 配置固定IP

![1714994448584](linux.assets/1714994448584.png)

## ping、wget

![1714994794454](linux.assets/1714994794454.png)

![1714994944551](linux.assets/1714994944551.png)

![1714995121520](linux.assets/1714995121520.png)

![1714995135477](linux.assets/1714995135477.png)

cip.cc是一个网站，可以返回公网IP信息。

第二个例子是访问这个网站，即发起网络请求，返回的是这个网站的html源码。

第三个例子是可以下载安装包。

## 端口

![1714995852708](linux.assets/1714995852708.png)

![1714996145316](linux.assets/1714996145316.png)

![1714996193439](linux.assets/1714996193439.png)

![1714996265936](linux.assets/1714996265936.png)

## 进程管理

![1714996375754](linux.assets/1714996375754.png)

![1714997947070](linux.assets/1714997947070.png)

## 系统资源监控

![1714997982397](linux.assets/1714997982397.png)



## 环境变量



## linux文件的上传和下载



## 压缩和解压

![1714999242078](linux.assets/1714999242078.png)

![1714999508572](linux.assets/1714999508572.png)

![1715000261832](linux.assets/1715000261832.png)

![1715000298743](linux.assets/1715000298743.png)



















