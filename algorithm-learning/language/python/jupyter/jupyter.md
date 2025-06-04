jupyter

自定义jupyter启动时依赖的文件夹

打开cmd输入 `jupyter notebook --generate-config` 生成配置文件命令，找到配置文件的位置。用vscode打开，然后通过搜索命令 `ctrl+f`搜索 `c.NotebookApp.notebookdir`

然后修改为 `c.NotebookApp.notebookdir = '自定义的文件夹位置'` 注意要用双斜杠

----------------------------------------------------

注册conda环境为jupyter内核

Jupyter 的内核配置文件 *kernel.json* 通常存储在以下路径之一：

1. **用户级路径**: *~/.local/share/jupyter/kernels/*
2. **系统级路径**: */usr/local/share/jupyter/kernels/*

每个内核都有一个独立的目录，包含 *kernel.json* 文件，该文件定义了内核的执行环境和相关配置。

假设你已经在 Conda 中创建了一个环境，但 Jupyter 并未识别到它，我们需要手动将其添加到 Jupyter 内核列表中。

️ 操作步骤
步骤 1：激活目标环境
首先，激活你想要添加的 Python 环境：
`conda activate env_name`
（请将 env_name 替换为你的实际环境名称）

步骤 2：安装 ipykernel
ipykernel 允许我们将 Conda 环境作为一个独立的 Jupyter 内核：
`conda install ipykernel`
步骤 3：将环境添加到 Jupyter 内核
执行以下命令，注册该环境到 Jupyter：
`python -m ipykernel install --user --name velocyto --display-name "Python (velocyto)"`

--user是注册为用户级内核
--name 后跟的是 内核的唯一标识（建议与 Conda 环境名一致）。
--display-name 是 Jupyter Notebook 中显示的名称，可以自定义。
例如，添加一个 PyTorch 环境：

`python -m ipykernel install --user --name pytorch_env --display-name "Python (PyTorch)"`

步骤 4：启动 Jupyter Notebook
在终端运行：
`jupyter notebook`
步骤 5：切换到新内核
在 Jupyter Notebook 中：
点击 Kernel > Change Kernel
选择 "Python (velocyto)"（或你自定义的名称）
此时，Jupyter Notebook 就可以使用 your_velocyto_env 这个环境了！

2. 删除 Jupyter 内核
场景
如果某个内核（如 cpdb）不再需要，我们可以将其删除，避免内核列表混乱。

️ 操作步骤
步骤 1：查找内核目录
执行以下命令，列出所有已安装的内核及其路径：
jupyter kernelspec list 

步骤 2：删除对应的内核
`jupyter kernelspec uninstall myenv`

步骤 3：验证内核是否删除
执行：
jupyter kernelspec list
如果 cpdb 不再出现在列表中，说明删除成功。

