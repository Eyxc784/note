conda

miniconda，虚拟环境管理工具。python管理虚拟环境有多种方式，这个是最好用的。

可以创建、删除、使用虚拟环境。自带base虚拟环境，虚拟环境里有python。

也可以创建其他虚拟环境，在创建时可以指定python版本，如不指定，会使用base环境里的python。建议必须指定。如果使用base环境里的python可能会出现冲突。我们使用conda就是为了避免冲突。



PYTHONPATH是一个环境变量，用于指定Python解释器在执行时搜索模块的路径。当Python解释器在导入模块或包时，它将按照PYTHONPATH中指定的顺序去搜索这些路径，直到找到对应的模块或包为止。如果模块或包不在PYTHONPATH中，Python解释器将无法找到它们，从而导致导入错误。

```
import sys
print(sys.path)
```

['', 
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\python38.zip',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\DLLs',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\lib',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l',
'C:\\Users\\DELL\\AppData\\Roaming\\Python\\Python38\\site-packages',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\lib\\site-packages',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\lib\\site-packages\\win32',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\lib\\site-packages\\win32\\lib',
'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\lib\\site-packages\\Pythonwin']

建议，永远不要使用全局环境pip install包，或者说，每次用python都需在虚拟环境中使用。原因是python在加载module时会按照环境变量pythonpath顺序加载，会先加载'C:\\Users\\DELL\\AppData\\Roaming\\Python\\Python38\\site-packages',在加载'D:\\apps\\DevelopKit\\miniconda3\\envs\\d2l\\lib\\site-packages',

我们在全局环境中pip install或在任何环境中pip install --user 安装包的话都会装到C盘那个目录下，如果我们在任何python项目中都使用全局环境，会造成冲突，另一方面污染了全局环境，我们在虚拟环境中也会受到全局环境的影响，因为在全局环境中找到某个包之后就不会再往下找了，这就导致我们在虚拟环境中装的module失效，造成冲突。因此我们应该时刻保证全局环境的干净。



```
conda env list   -- 查看已有的虚拟环境
conda create -n 虚拟环境名 python=x.x   -- -n的含义是-name 表明后面指定虚拟环境名 x.x表明指定该虚拟环境的python版本,建议每次新建虚拟环境时都要新安装python，不然就使用的是全局环境里的python和pip，这样在虚拟环境里使用pip list命令就会出现全局环境里的包。
conda activate 虚拟环境名  --进入指定虚拟环境
conda deactivate --退出当前虚拟环境
conda env remove --name env_name  --删除虚拟环境
```

