STL

STL 是“Standard Template Library”的缩写，中文译为“标准模板库”。STL 是 C++ 标准库的一部分，不用单独安装。从根本上说，STL 是一些容器、算法和其他一些组件的集合，所有容器和算法都是总结了几十年来算法和数据结构的研究成果，汇集了许多计算机专家学者经验的基础上实现的，因此可以说，STL 基本上达到了各种存储方法和相关算法的高度优化。

### vector

vector 实现的是一个动态数组，即可以进行元素的插入和删除，在此过程中，vector 会动态调整所占用的内存空间，整个过程无需人工干预。

头文件

```c++
#include <vector>
using namespace std;
```

创建一个vector

```c++
vector<数据类型> 变量名; 
```

数据类型有很多，比如int、float、double、struct、vector等等

`vector<int> a;`

`vector<vector<int>> b;`  //二维动态数组

#### vector常用的成员函数

| 函数成员     | 函数功能                                                     |
| ------------ | ------------------------------------------------------------ |
| begin()      | 返回指向容器中第一个元素的迭代器。(迭代器理解为指针即可)     |
| end()        | 返回指向容器最后一个元素所在位置后一个位置的迭代器，通常和 begin() 结合使用。 |
| rbegin()     | 返回指向最后一个元素的迭代器。                               |
| rend()       | 返回指向第一个元素所在位置前一个位置的迭代器。               |
| size()       | 返回实际元素个数。                                           |
| empty()      | 判断容器中是否有元素，若无元素，则返回 true；反之，返回 false。 |
| operator[ ]  | 重载了 [ ] 运算符，可以向访问数组中元素那样，通过下标即可访问甚至修改 vector 容器中的元素。 |
| push_back(x) | 在序列的尾部添加一个元素x。                                  |
| pop_back()   | 移出序列尾部的元素。                                         |
| insert()     | 在指定的位置插入一个或多个元素。                             |
| erase()      | 移出一个元素或一段元素。                                     |
| clear()      | 移出所有的元素，容器大小变为 0。                             |
| swap()       | 交换两个容器的所有元素。                                     |

insert()和erase()未具体说明，需要用到自行查阅。

![1680753898787](STL.assets/1680753898787.png)

访问vector元素的方法：

1.用 `[]`

```c++
#include <iostream>
#include <vector>
using namespace std;

int main(){
    vector<int> vi;
    vi.push_back(1);
    cout<<vi[0]<<endl;
    return 0;
}
```

2.用迭代器(指针)

```c++
#include <iostream>
#include <vector>
using namespace std;

int main(){
    vector<int> v;
    for (int i = 0; i < 5; i++)
    {
        v.push_back(i);
    }
    //v.begin()返回v的首元素地址
    vector<int>::iterator it=v.begin();
    for (int i = 0; i < v.size(); i++)
    {
       cout<<it[i]<<" ";
    }
    return 0;
}
```

在定义迭代器时，可以用auto:

```c++
vector<int> v;
vector<int>::iterator it = v.begin();
//等价于 auto it = v.begin();
```

### auto

auto 的作用是，根据变量被赋予的值，自动判断变量的类型；

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main(){
    vector<int> v;
    for (int i = 0; i < 5; i++)
    {
        v.push_back(i);
    }
    //vector的迭代器不支持it<v.end()的写法，因此循环条件只能it!=v.end()
    for (auto it=v.begin(); it!=v.end();it++)
    {
        cout<<*it<<" ";
    }
    return 0;
}
```

### map

```cpp
#include <map>
using namespace std;
```

使用该容器存储的数据，其各个元素的键必须是唯一的（即不能重复），该容器会根据各元素键的大小，默认进行升序排序。

```cpp
#include <iostream>
#include <map> //使用 map 容器，必须引入该头文件
#include <string>
using namespace std;
int main()
{
    //创建一个空的 map 关联式容器，该容器中存储的键值对，其中键为 string 字符串，值也为 string 字符串类型
    map<string, string> mymap;
    //向 mymap 容器中添加数据
    mymap["http://c.biancheng.net/c/"] = "C语言教程";
    mymap["http://c.biancheng.net/python/"] = "Python教程";
    mymap["http://c.biancheng.net/java/"] = "Java教程";
    //使用 map 容器的迭代器，遍历 mymap 容器，并输出其中存储的各个键值对
    for (map<string, string>::iterator it = mymap.begin(); it != mymap.end(); ++it) {
        //输出各个元素中的键和值
        cout << it->first << " => " << it->second << '\n';
    }
    return 0;
}
```

各个键值对的键和值可以是任意数据类型，包括 C++ 基本数据类型（int、double 等）、使用结构体或类自定义的类型。

默认情况下，map 根据容器内各键值对的键的大小，对所有键值对做升序排序。

C++ STL 标准库为 map 容器配备的是双向迭代器（bidirectional iterator）。这意味着，map 容器迭代器只能进行 ++p、p++、--p、p--、*p 操作，并且迭代器之间只能使用 == 或者 != 运算符进行比较。

| 成员方法   | 功能                                                         |
| ---------- | ------------------------------------------------------------ |
| begin()    | 返回指向容器中第一个（注意，是已排好序的第一个）键值对的双向迭代器。如果 map 容器用 const 限定，则该方法返回的是 const 类型的双向迭代器。 |
| end()      | 返回指向容器最后一个元素（注意，是已排好序的最后一个）所在位置后一个位置的双向迭代器，通常和 begin() 结合使用。如果 map 容器用 const 限定，则该方法返回的是 const 类型的双向迭代器。 |
| find(key)  | 在 map 容器中查找键为 key 的键值对，如果成功找到，则返回指向该键值对的双向迭代器；反之，则返回和 end() 方法一样的迭代器。另外，如果 map 容器用 const 限定，则该方法返回的是 const 类型的双向迭代器。 |
| empty()    | 若容器为空，则返回 true；否则 false。                        |
| size()     | 返回当前 map 容器中存有键值对的个数。                        |
| operator[] | map容器重载了 [] 运算符，通过指定的键，我们可以轻松获取 map 容器中该键对应的值。 |
| clear()    | 清空 map 容器中所有的键值对，即使 map 容器的 size() 为 0。   |
|            |                                                              |

#### map索引不存在的key可能导致的后果

```cpp
#include <map>
#include <iostream>
using namespace std;

int main()
{
	map<int, int> map1;
	cout << map1[1] << endl;
	map<int, char> map2;
	cout << map2[1] << endl;
	map<int, bool> map3;
	cout << map3[1] << endl;
}
-------
0
                 //其实打印了'\0'
0
```

**发现不存在的key在被索引后被添加到了map中并被赋予了一个默认值（一般的，整数为0，字符为'\0'，字符串为空）**可以拿这个性质去作判断

```cpp
#include <map>
using namespace std;

int main()
{
    map<int,bool> map1;
    if(map1[1])   //如果map中没有这个元素，返回false，if循环内的语句就不执行。
}
```



### unordered_map

存储键值对 <key, value> 类型的元素，其中各个键值对键的值不允许重复，且该容器中存储的键值对是无序的。

与map的唯一区别：即 map 容器内存会对存储的键值对进行排序，而 unordered_map 不会。

```cpp
#include <unordered_map>
using namespace std;
```

C++ STL 标准库中，unordered_map 容器迭代器的类型为前向迭代器（又称正向迭代器）。这意味着，假设 p 是一个前向迭代器，则其只能进行 *p、p++、++p 操作，且 2 个前向迭代器之间只能用 == 和 != 运算符做比较。

| 成员方法  | 功能                                                         |
| --------- | ------------------------------------------------------------ |
| begin()   | 返回指向容器中第一个键值对的正向迭代器。                     |
| end()     | 返回指向容器中最后一个键值对之后位置的正向迭代器。           |
| find(key) | 查找以 key 为键的键值对，如果找到，则返回一个指向该键值对的正向迭代器；反之，则返回一个指向容器中最后一个键值对之后位置的迭代器（如果 end() 方法返回的迭代器）。 |











