typing module

typing module for reading Python documentation

python有各种各样的库，我们在使用python的某些库遇到问题的时候，会去上网搜，不管是百度还是中国IP的bing，都是别人的博客，其实最重要的是去阅读编写库的官方给的说明文档，让人知难而退的不仅仅是墙，还有英语水平，但是要想成为大牛，这些都是必须克服的。今天我们来学习typing模块。typing模块是python的一个标准库模块，使用typing模块，你可以在函数声明、变量声明等地方指定参数和返回值的类型，以便在编码过程中进行类型检查和静态分析。这有助于提前发现潜在的类型错误，并提供更好的开发工具支持和文档生成。

了解typing模块对我们阅读python库的函数和说明文档是非常有帮助的。



类型说明：

```python
def greeting(name: str) -> str:  
    return 'Hello ' + name
```

说明参数name的类型是str，说明函数的返回值类型是str

这是typing模块提供的功能，便于人理解函数。python解释器不会执行。



Union type: `Union[X, Y]` is equivalent to `X | Y` and means either X or Y.

```python
def greeting(name: Union[str,int]) -> str:  
    return 'Hello ' + name
```

 表示name的类型可以是 str 或 int

```python
Union[Union[int, str], float] == Union[int, str, float]
Union[int] == int
Union[int, str, int] == Union[int, str] == int | str
```



`Optional[X]` is equivalent to `X | None` ,等价于 `Union[X, None]`

```python
def greeting(name: Optional[Union[str,int]]) -> str:  
    return 'Hello ' + name
```

name的类型可以是 str,int,None中的一个





