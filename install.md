# Python下载

## 只下载python

- Windows
  1. microsoft store应用商店直接下载（不用配置环境变量）
  2. python官网下载，并配置环境变量

- Macos
  1. 使用homebrew安装（如果没安装过homebrew推荐从[清华源](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)下载，见**首次安装 Homebrew / Linuxbrew）**部分

    ```bash
    brew install python3
    ```

- Linux
  
1. 使用包管理器下载
  
- Test

  在shell中输入`python3 --version`

## 下载Conda

- conda自带python，无需额外下载。
- conda的好处
  - 开箱即用
    - Anaconda 附带了一大批常用数据科学包，它附带了 conda、Python 和 150 多个科学包及其依赖项。因此你可以立即开始处理数据。
  - 虚拟环境与版本管理
    - 比如你在A项目中用了 Python 2，而新的项目B老大要求使用Python 3，而同时安装两个Python版本可能会造成许多混乱和错误。这时候 conda就可以帮助你为不同的项目建立不同的运行环境。还有很多项目使用的包版本不同，比如不同的pandas版本，不可能同时安装两个 Numpy 版本，你要做的应该是，为每个 Numpy 版本创建一个环境，然后项目的对应环境中工作。这时候conda就可以帮你做到。

- conda和pip的区别
  [see](https://zhuanlan.zhihu.com/p/379321816)

- anaconda和miniconda的区别
  1. anaconda不需要手动安装各种数据科学的包，miniconda仅安装了python和conda
  2. anaconda有图形化界面

- Windows&Linux
  [参见](https://zhuanlan.zhihu.com/p/449750184)

- Macos
  - Anaconda

    ```bash
    brew install anaconda
    ```

  - Miniconda

    ```bash
    brew install miniconda
    ```

- Vscode Setup
  - Install python extension
  - Install code runner
  - Motivation of jupyter notebook

    Jupyter Notebook可以将python代码分成几个片段执行，由于科学计算一般都是探索性的学习，即每执行一步看一下结果，这样用Jupyter Notebook显然更方便。此外处理大量数据、一些运算类型等等也是更占优势。

  - Install jupyter

    ```bash
    pip install jupyter
    conda install jupyter notebook
    ```

    下载vscode jupyter notebook插件

# Makeup

## Conda activate无法使用(win11)

- conda activate失败

  首先确定conda已经添加到环境变量。

  执行`conda init powershell`

  如果出现不能运行的脚本的问题，在管理员模式下打开 PowerShell，并输入以下命令来修改执行策略为 "RemoteSigned"（仅允许运行本地脚本）：`Set-ExecutionPolicy RemoteSigned`

  For macos and linux可以直接`conda init`

- gcc冲突问题

  执行`conda deactivate`(如果失败参见上一条)，然后通过以下指令设置conda自启动为否

  ```bash
  conda config --set auto_activate_base False
  ```