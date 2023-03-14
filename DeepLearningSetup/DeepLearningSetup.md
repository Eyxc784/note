DeepLearningSetup

动手学深度学习视频[03 安装【动手学深度学习v2】_哔哩哔哩_bilibili](https://www.bilibili.com/list/1567748478?sid=358497&spm_id_from=333.999.0.0&desc=1&oid=972150557&bvid=BV18p4y1h7Dr)

Windows版
我已经有conda了

[http://Anaconda.org](https://link.zhihu.com/?target=http%3A//Anaconda.org)的服务器在国外，安装packages时，conda下载的速度很慢慢。把清华TUNA镜像源加入conda的配置即可

\# 添加Anaconda的TUNA镜像

1. win+R 输入cmd
2. 将清华镜像源加入conda配置输入命令

conda config --add channels [https://mirrors.tuna.tsinghua.edu.cn](https://link.zhihu.com/?target=https%3A//mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/)

3. 创建虚拟环境d2l-zh

d2l-zh只是一个虚拟环境名而已，可以自己命名

```
conda create -n d2l-zh python=3.8 pip
```

3. 激活环境

```
conda activate d2l-zh
```

在最左边出现(d2l-zh)表示已经进入了这个环境

4. 在该环境下安装课程需要的包

```
pip install jupyter d2l torch torchvision
```

5. 下载zip

先创建一个空文件夹命名为   d2l-zh

以管理员身份打开cmd

输入   fsutil file SetCaseSensitiveInfo c:\sysgeek enable

将  c:\sysgeek  修改为 刚才创建的文件夹的绝对路径

这个命令的意思是让这个文件夹里的文件名可以区分大小写。因为压缩包来自linux系统，Linux系统支持同一目录下文件名区分大小写，而Windows不支持同一目录文件名区分大小写。这个压缩包在Windows系统解压的时候会导致出现同名文件请求覆盖的界面。因此需要执行此命令。

然后将zip解压到这个文件夹里

6. 在该文件夹下的地址栏里输入cmd进入命令行
7. 激活环境

```
conda activate d2l-zh
```

8. 输入jupyter notebook

就配置成功了。

不熟悉jupyter的人需要注意，命令行窗口不能关。