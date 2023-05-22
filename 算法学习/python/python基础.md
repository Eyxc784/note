python基础

以下是python的简洁笔记，更多内容以后遇到了再添加



### python基础

#### 变量的命名规则

1. 变量名只能包含字母、数字和下划线。不能以数字打头
2. 变量名不能有空格，应该使用下划线分隔单词
3. 不能将python关键字和函数名作为变量名
4. 变量名应简短且具有描述性
5. 慎用小写字母l和大写字母O



变量名的本质到底是什么，这个学了汇编语言就知道了，挖个坑



#### 字符串

用一对单引号或者一对双引号括起来的连续的字符就是字符串，引号属于界定符，不是字符串的一部分



使用方法修改字符串的大小写

```python
name = "ada lovelace"
name.title()           //返回值是 将每个单词的首字母大写 ;不改变本身
name.upper()           //返回值是 将字符全都改为大写；不改变本身
name.lower()           //返回值是 将字符全都改为小写；不改变本身
```



在字符串中使用变量

在字符串前加$f$ 能将字符串中大括号的内容识别为python的可执行语句，而不再是字符串

```python
first_name = "ada"
last_name = "lovelace"
full_name = f"{first_name} {last_name}"
print(full_name)
-----
ada lovelace
```



转义字符

换行符 \n

制表符 \t         --补空格使对齐



删除空白

```python
name.rstrip()   //返回值是 删除字符串结尾多余的空格 ；不改变本身
name.lstrip()   //返回值是 删除字符串开头多余的空格 ；不改变本身
name.strip()    //返回值是 删除字符串两边多余的空格 ；不改变本身
```



#### 整数和浮点数

整数和浮点数支持的运算 ：加、减、$*$乘、$/$除、$**$乘方、$//$整除、$\%$取余

浮点数和整数运算的结果是浮点数

```python
age = 14_000_000_000    #当数字较大的时候可以用下划线进行分组，使清晰易读
print(age)
---------
14000000000
```

 

#### 同时给多个变量赋值

可以在一行代码中给多个变量赋值，这有助于缩短程序并提高其可读性

```python
x, y, z = 0, 0, 0    #用逗号进行分隔，按顺序进行赋值
```



#### 常量

**一般常量名的定义是全大写**

```python
MAX_CONNE = 5000
```

#### 列表

列表是可变的序列,用 [] 表示列表，用逗号分隔列表中的元素

```python
bicycles = ['trek','redline','specialized']
print(bicycles[0])    #使用下标来访问列表中的元素，正向从0开始，逆向从-1开始
bicycles[0] = 'ducati'   #修改列表中某个位置的元素
bicycles.append('suzuki')   #在列表末尾添加元素
bicycles.insert(0,'honda') #将 下标从0开始的元素都往后移动一位，然后将 'honda'放到下标是0的位置
del bicycles[0]   #删除下标是0的元素，下标从1往后的元素往前移动一位
bicycles.pop()   #返回值是  列表的最后一个元素，并删除列表中的最后一个元素
#bicycles.pop(x) 返回值是 列表中下标为x的元素，并在列表中删除该元素。默认是删除并返回最后一个元素
bicycles.remove('ducati')  # 删除指定元素，且只删除列表从正向开始找第一个出现的 该元素
len(bicycles)  #返回列表的长度
bicycles.reverse()  #将列表逆序
```

sort()方法语法：

```
list.sort(cmp=None, key=None, reverse=False)
```

参数

- cmp -- 可选参数, 如果指定了该参数会使用该参数的方法进行排序。
- key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
- reverse -- 排序规则，**reverse = True** 降序， **reverse = False** 升序（默认）。

返回值

该方法没有返回值，但是会对列表的对象进行排序。



**sort 与 sorted 区别：**

sort 是应用在 list 上的方法，sorted 可以对所有可迭代的对象进行排序操作。

list 的 sort 方法是对已经存在的列表进行操作，无返回值；而python自带的函数 sorted 方法返回值是排好序的列表或其他可迭代对象，不改变本身



sorted 语法：

```
sorted(iterable, cmp=None, key=None, reverse=False)
```

参数说明：

- iterable -- 可迭代对象。
- cmp -- 比较的函数，这个具有两个参数，参数的值都是从可迭代对象中取出，此函数必须遵守的规则为，大于则返回1，小于则返回-1，等于则返回0。
- key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
- reverse -- 排序规则，reverse = True 降序 ， reverse = False 升序（默认）。



#### for循环和range()函数

用for循环来遍历列表

```python
bicycles = ['trek','redline','specialized']
for i in bicycles:       # 每一个 i 对应 列表中的一个元素；print函数自带换行
    print(i)
-----
trek
redline
specialized
```



```python
for i in range(a,b,c):   # [a,b)，步长是c   每一个i对应一个数字
	#循环体
```



#### 数字列表的创建

```python
numbers = [range(1,6)]
print(numbers)
-------
[1,2,3,4,5]
```



#### 数字列表常用的统计函数

```python
digits = [1,2,3,4,5,6,7,8,9,0]
min(digits)
max(digits)
sum(digits)
```



#### 列表解析

```python
squares = [value**2 for value in range(1,11,2)]
print(squares)
-------
1
9
25
49
81
```



#### 切片

前面我们提到用  列表名[下标] 的方法来访问 列表中的某个元素，从而可以对该元素进行一些处理；但是我们该如何访问列表中的多个元素呢？使用切片

```python
列表名[a:b:c]    #切片的一般形式，返回值是 原列表下标[a,b)步长为c的元素的 一个列表
切片是个情况比较复杂的语法，希望有一天能碰到一个非常全面且清晰的教程
```



#### 列表的复制

```python
my_foods = ['pizza', 'falafel', 'carrot']
his_foods = my_foods[:]   # 深拷贝 ，his_foods与my_foods对应的内存空间不相同
her_foods = my_foods       # 浅拷贝， her_foods与my_foods对应同一片内存空间
```



#### 元组

元组是不可变的序列，只不过元组的元素不能改变；元组用圆括号标识,可以用下标访问

```python
dimensions = (400,50)
print(dimensions[0])
print(dimensions[1])
#dimensions[0] = 20  尝试修改元组的元素会报错
------
400
50
```



<font color = #a61b29> 严格地说，元组是由逗号标识的，圆括号只是让元组看起来更清晰、整洁。除了空元组，括号可以省略。但元组是更大的表达式的一部分或会产生语法歧义的情况，括号不能省略</font>

```python
name = ()  #空元组
name = (1,)     # 圆括号可以省略，逗号不能省略，因为逗号是用来说明是元组的。
print(type(name))
print(name)
-------
tuple
(1,)
```



只需要知道这个本质就可以了，我们以后定义或使用元组的时候都要带上圆括号。



虽然不能修改元组的元素，但是可以给元组变量重新赋值

```python
dimensions = (400,50)
dimensions = (400,100)
```



#### 运算符

##### 比较运算符

$>,>=,<,<=,==,!=$

##### 逻辑运算符

and、or、not



检查特定值是否包含在列表中

```python
banned=['andrew','car','david']
name = ['marie']

print(name in banned)
print(name not in banned)
```



#### if语句

```python
age = 12
if age < 4:
    print("Your admission cost is $0.")
elif age < 18:
    print("Your admission cost is $25.")
else:
    print("Your admission cost is $40.")
```



#### 确定列表是否为空

```python
s = []
if s:       # 列表名作布尔表达式时，如果为空，返回False；至少存在一个元素，返回True
    #
```

#### 字典

字典的元素是键值对，用花括号标识，元素之间用逗号分隔，键值之间由冒号标识

键不能重复出现

```python
alien = {'color':'green','points':5}
```



获取指定键的值

```python
字典名[键]   #得到的就是这个键的值
print(alien['color'])
------
green
```



如果字典中不存在 指定的键 对应的键值对就会报错

```python
alien['nml']
-----
KeyError
```

因此，当我们不确定字典中是否存在该键值对而又想访问这个键对应的键值对的时候，使用get函数

get()方法语法：

```python
dict.get(key[, value]) 
```

参数

- key -- 字典中要查找的键。
- value -- 可选，如果指定键的值不存在时，返回value。value默认为None



添加键值对

```python
alien['x_position'] = 0
alien['y_position'] = 25
print(alien)
---------
{'color':'green','points':5,'x_position':0,'y_position':25}
```



字典的排列顺序是添加的顺序



修改给定键对应的值

```python
alien['color'] = 'yellow'
print(alien)
-------
{'color':'yellow','points':5,'x_position':0,'y_position':25}
```



删除指定键值对

```python
del alien['color']
print(alien)
-------
{'points':5,'x_position':0,'y_position':25}
```



#### 遍历字典



```python
tinydict = {'Google': 'www.google.com', 'Runoob': 'www.runoob.com', 'taobao': 'www.taobao.com'}


# 遍历字典列表
for key, values in tinydict.items():
    print(key, values)
-----

Google www.google.com
Runoob www.runoob.com
taobao www.taobao.com
```

```python
for i in tinydict.items():
    print(i)
------
('Google', 'www.google.com')
('Runoob', 'www.runoob.com')
('taobao', 'www.taobao.com')
```

items() 方法把字典中每对 key 和 value 组成一个元组，并把这些元组放在列表中返回。



```python
tinydict = {'Google': 'www.google.com', 'Runoob': 'www.runoob.com', 'taobao': 'www.taobao.com'}

for key in tinydict.keys():    #遍历键
    print(key)
-----
Google
Runoob
taobao
```

```python
tinydict = {'Google': 'www.google.com', 'Runoob': 'www.runoob.com', 'taobao': 'www.taobao.com'}

for key in tinydict:    #遍历键
    print(key)
-----
Google
Runoob
taobao
```

这两种方法没有区别

**keys方法把字典中的key放入列表中返回，如果把字典名当作可迭代对象的话，就相当于keys方法**

因此，可以使用 `in` 或者 `not in dic.keys()` 来判断某个key是否是字典`dic` 里的关键字



```python
tinydict = {'Google': 'www.google.com', 'Runoob': 'www.runoob.com', 'taobao': 'www.taobao.com'}

for value in tinydict.values():    #遍历值
    print(value)
-------
www.google.com
www.runoob.com
www.taobao.com
```

 

#### 集合

集合的元素是不重复的，用一对花括号标识，用逗号分隔元素。

集合的元素可以是数字，字符串，元组，不能是键值对、列表。

原因如下：

首先了解 hashable ，可哈希

在Python中，可哈希（Hashable）是指一个对象具有哈希值（Hash Value）。哈希值是一个整数，用于唯一标识对象。不可哈希对象则相反，它们的哈希值可能会发生变化或者无法计算哈希值。例如，列表和字典是不可哈希的，因为它们是可变的，并且它们的值可能会改变。

可哈希的对象包括但不限于整数、浮点数、字符串、元组等不可变类型。这些对象的哈希值是根据它们的值计算得出的，因此具有相同值的对象将具有相同的哈希值。

不可变的对象计算出的哈希值是唯一的，可唯一标识该对象。

以后有时间了解一下这个哈希函数是什么



集合要求元素必须是可哈希对象的原因也很明显，因为集合要求所有元素都不能重复，根据的就是元素的哈希值不相同。对于列表和键值对这种可变数据类型，计算出的哈希值是不固定的，所以集合中的元素不能是可变数据类型对象



集合的创建

```python
class set([iterable])
```

set函数的参数是一个可选的 iterable（可迭代对象），将可迭代对象的每一个元素放入到集合中，并返回该集合。

```python
a = {}
a = set()
# 空集合的创建
a = {1,2,'3sd',(4,)}
b = set('abcda')     #集合的去重
print(b)
----
{'a','b','c','d'}
```



```python
language = {'a':'python','b':'C','c':'Ruby','d':'python'}

for value in language.values():
    print(value)
---------
python
C
Ruby
python

for value in set(language.values()):
    print(value)
---------
C
python
Ruby
```



总结：

iterable 可迭代  ----这个需要学习了python的类的知识之后才了解了。

hashable 可哈希  ---这个也不是很明白，但是清楚了一些，主要是不知道这个哈希函数是什么





#### 用户输入input()

函数input()让程序暂停运行，等待用户输入一些文本。将用户输入（字符串）作为返回值。

```python
message = input("input something:")
```

input()函数接受一个参数——要求用户输入什么信息的提示或说明



#### 数据类型转换

```python
s = "21"

s = int(s)
print(type(s))
print(s)
----
<class'int'>
21
```



#### 函数

```python
def functionname( parameters ):
   '''文档注释'''
   function_suite
   return [expression]
```



三个单引号括起来的字符串称为 文档字符串，python使用文档字符串来生成函数的文档。

函数的返回值为空的话，默认返回None



函数调用的三种方法：

按顺序传入参数；显式地将实参传递给形参；形参的默认值

如果一个形参有默认值，把这个形参放到最后面去。

这三个方法会混合着用。不难理解。



python在函数传递的时候与c/c++不同，c/c++在传递参数的时候是值传递，即执行函数的时候，给形参分配空间，将实参的值赋值给形参。函数执行后不会影响实参。python则相反，直接传入实参，函数执行直接影响实参。

举个例子：

```python
def f(name):
    #函数体


name = [1,2,3]
f(name)          #传入函数的就是name，函数执行会影响本身
f(name[:])       #函数执行不会影响name本身
```



#### 传入任意数量的实参

有时候不能确定实参的数量，我们需要使用以下方法

```python
def make_pizza(*toppings):
    print(toppings)
```



形参名 *toppings 中的 * 号让python创建一个名为toppings的空元组，并将收到的所有值都封装到这个元组中。



```python
def make_pizza(a,b,c,*toppings):
    #
```

接受任意实参的形参与其他形参的组合使用：

把*toppings这个形参放到最后，前面配对完了之后，剩下的都是toppings这个元组的元素



#### 传入任意数量的键值对

```python
def build_profile(**user_info):
    #函数体


build_profile(location='p',field='s',first='f') #可以继续添加任意数量的键值对
```



形参 **user_info中的星号让python创建一个名为 user_info的空字典，并将收到的所有键值对放到字典中





#### 模块

将函数/类存储在模块中

模块是扩展名为.py的文件。

举个例子：

```python
def make_pizza():  # 在 pizza.py 文件中定义了这样一个函数
    #函数体
```

在pizza.py所在的目录下，新建一个py文件

```python
import pizza    #在新py文件中导入pizza模块
#这样我们就可以直接调用在pizza.py文件中定义好的函数make_pizza()
pizza.make_pizza()   #调用方法是 模块名.函数名
```



导入特定的函数

```python
from moudle_name import function_name #只导入某个模块的某个函数
from moudle_name import function_name1,function_name2,function_name3 #导入某个模块任意数量的某些函数
```



指定别名

```python
from moudle_name import function_name as fn #给模块的function_name函数取个别名
import moudle_name as mn  #给导入的模块取个别名
```

给函数取别名，是因为导入的函数名可能与程序中的名称有冲突，或者函数名太长了，简写一下

给模块取别名就是想简写的。



导入模块中的所有函数

```python
from pizza import *
```



将pizza.py文件中所有的函数复制到该文件中，这样做就不需要使用 `模块名.函数名`的调用方式了，直接调用就可以了。

缺点：

如果程序中定义的函数名称与模块中的名称相同，python遇到名称相同的函数名或变量名会进行覆盖。



### 类

本书提到的太简单且不涉及底层，不记录了。以后会遇到更好的教程。



类中的函数称为方法。



约定俗成

类名应采用驼峰命名法，类名中不适用下划线，类名的每个单词的首字母大写。

实例名和模块名都采用小写格式，单词之间用下划线隔开。

每个类在定义的时候都要跟上一个文档字符串，简要描述类的功能。

每个模块也是。

在类中，使用一个空格来分隔方法。

在模块中，使用两个空格分隔类和函数。



### python标准库

python标准库是一组模块，安装python的时候就包含它。成为了python语言的一部分了。



### 文件和异常





























































