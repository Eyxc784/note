typora的使用，快捷键，html的学习使用

[Typora_Markdown_图片标题(题注)_markdown图标题_Ladybug_的博客-CSDN博客](https://blog.csdn.net/m0_47098916/article/details/117827687)

> 找一个好看的主题，能让程序员爱上写md笔记
>

**https://theme.typora.io/**

[Typora常用好看主题推荐!!!_typora主题-CSDN博客](https://blog.csdn.net/weixin_52023681/article/details/120251523)

快捷键

ctrl+数字    设置标题

ctrl+shift+~     代码行

ctrl+shift+K      代码块

前后双等号    高亮

前后单$          latex公式行

ctrl+shift+M   latex公式块

ctrl+b   加粗

ctrl+shift+Q   引用    可以用来当小标题



让html代码生效：直接写html就行，自己会生效，不要放到代码行或代码块里。

居中html代码

`<center>****</center>`

<center>Impressions of after-reading of Dive into deep learning</center>



#### latex

|      |            |              |      |
| ---- | ---------- | ------------ | ---- |
| 撇儿 | d^{\prime} | $d^{\prime}$ |      |



| 运算     | 公式              | 显示                                      |
| -------- | ----------------- | ----------------------------------------- |
| 除法     | \frac{a}{c}       | $ \frac{a}{c}$                            |
| 对数     | \log_ax           | log以a为底，以x为真数。l小写    $\log_ax$ |
|          | \Ln x             | log以e为底，以x为真数。 L大写     $\In x$ |
|          | \lg x             | log以10为底，以x为真数。       $\lg x$    |
| 向下取整 | \lfloor x \rfloor | $\lfloor x \rfloor$                       |
| 向上取整 | \lceil x \rceil   | $\lceil x \rceil$                         |

|       | 公式    | 显示      | 解释                                                   |
| ----- | ------- | --------- | ------------------------------------------------------ |
| 向量x | \pmb{x} | $\pmb{x}$ | 有时我们需要表示一个向量x，即如何把在latex中的字母加粗 |
|       |         |           |                                                        |
|       |         |           |                                                        |

| 括号   | 公式                           | 显示                             | 解释                                                         |
| ------ | ------------------------------ | -------------------------------- | ------------------------------------------------------------ |
| 尖括号 | \left \langle x \right \rangle | $\left \langle x \right \rangle$ | 在美元符号\$中可以直接用<>来表示尖括号，单感觉有点违和，空隙较大，不好看，所以就总结一下。尖括号什么时候使用？<br />$\left \langle \pmb{x},\pmb{w} \right \rangle$ 表示向量x和向量w的内积 |
| 大括号 | \lbrace x\rbrace               | $\lbrace x\rbrace$               | 由于大括号{} 被用于分组，因此需要在latex中使用{}，比如集合的时候用 |
|        |                                |                                  |                                                              |

| 导数     | 公式                          | 显示                            | 解释 |
| -------- | ----------------------------- | ------------------------------- | ---- |
| 一阶导数 | \frac{\partial f}{\partial x} | $\frac{\partial f}{\partial x}$ |      |
|          |                               |                                 |      |
|          |                               |                                 |      |



| 范围表示 |        |          |
| -------- | ------ | -------- |
| 属于     | \in    | $\in$    |
| 不属于   | \notin | $\notin$ |
| 无穷大   | \infty | $\infty$ |

| 比较     |           |             |                  |
| -------- | --------- | ----------- | ---------------- |
| 大于等于 | \geqslant | $\geqslant$ |                  |
| 小于等于 | \leqslant | $\leqslant$ |                  |
| 不等号   | \neq      | $\neq$      | /not equal的简写 |

| 集合   |             |               |                        |
| ------ | ----------- | ------------- | ---------------------- |
| 空集   | \varnothing | $\varnothing$ |                        |
| 包含于 | \subset     | $\subset$     | 两边都是集合           |
| 包含   | \supset     | $\supset$     |                        |
|        | \subseteq   | $\subseteq$   | 左边是元素，右边是集合 |
|        | \supseteq   | $\supseteq$   |                        |
| 并集   | A\cup B     | $A\cup B$     |                        |
| 交集   | A\cap B     | $A\cap B$     |                        |



| 四周               |                |                  |              |
| ------------------ | -------------- | ---------------- | ------------ |
| 在单个字母上加横线 | \bar{a}        | $\bar{a}$        |              |
| 在多个字母上加横线 | \overline{a+b} | $\overline{a+b}$ | 用于矩阵的逆 |
|                    |                |                  |              |

| 排列组合 |               |                 |                  |
| -------- | ------------- | --------------- | ---------------- |
| 组合     | C_{n}^{m}     | $C_{n}^{m}$     | 从n个数中取出m个 |
| 组合     | \tbinom{n}{m} | $\tbinom{n}{m}$ | 从n个数中取出m个 |
| 组合     | n \choose k   | $n\choose k$    | 从n个数中取出k个 |

| 有序列表 |                                                              |      |
| -------- | ------------------------------------------------------------ | ---- |
| ①        | 用输入法打出来即可，不要想着用公式了，效果不好，再说我平常也不怎么用这种序号 |      |
|          |                                                              |      |
|          |                                                              |      |



①



| 矩阵 |      |      |      |
| ---- | ---- | ---- | ---- |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |

[如何用latex编写矩阵（包括各类复杂、大型矩阵）？ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/266267223)



写公式，等号对齐

![1688301072990](typora.assets/1688301072990.png)



![1688310513504](typora.assets/1688310513504.png)









工作需求：

#### 想要把网页上的gif搬到我的typora笔记当中。

第一步，将网页上的gif下载到电脑上：

1. 左键点击按住移动GIF图区域

2. 拖动GIF图到你的桌面

第二步，把gif保存到文件中，然后用markdown插入图片的代码 ![](图片路径)

就ok了



在Typora，markdown中可以使用相对路径引用本地文档

![1681194950979](typora的使用，快捷键，html的学习使用.assets/1681194950979.png)

使用的代码跟插入图片使用的代码差不多

```
[文件描述](相对路径)   //引用本地文档
```

```
![图片描述](相对路径)    //插入图片
```



![1682327061998](typora的使用，快捷键，html的学习使用.assets/1682327061998.png)







#### 个性化字体

<font size=6>  必须在同一行 

 </font>

![1683116726660](typora的使用，快捷键，html的学习使用.assets/1683116726660.png)









[(10 封私信 / 16 条消息) markdown中插入图片怎么定义图片的大小或比例？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/23378396)

![1715999813636](typora.assets/1715999813636.png)

<style>
    img{
        width: 60%;
        padding-left: 20%
    }
</style>

![1716000408309](typora.assets/1716000408309.png)



typora生成目录树

[Markdown使用-生成目录树 - 福宝心心 - 博客园 (cnblogs.com)](https://www.cnblogs.com/zyrb/p/15226918.html)

[Windows命令生成文件夹目录树状结构_在d盘根目录下,创建如图2-1所示树形目录结构。截图文件夹窗口左侧资源管理器,显示-CSDN博客](https://blog.csdn.net/qq_41076577/article/details/110557064#:~:text=Windows命令生成文件夹目录树状结构 1 在电脑操作系统的开始菜单中，搜索cmd或者直接使用WIN%2BR快捷键组合，直接打开命令行运行程序。 2 打开命令行程序 点击确定或者使用回车键，即可打开cmd、命令行运行程序。 3 进入文件目录,使用tree命令生成树形结构 分别使用以下命令：tree、tree %2Ff 命令，就可以看到屏幕的效果了，还可以使用tree %2Fa等命令，来生成想要的文件目录。 6 导出生成的文件目录 )





新建一个文件夹，将md文档放入文件夹，在typora的偏好设置里，将插入图片设置成相对路径。

![1730342047439](typora.assets/1730342047439.png)

