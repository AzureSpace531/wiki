# ubuntu简单教程和指引

**更新于22.10.2**
## 目录
* 终端
* 沟通、截图
* 缺失中文输入法
* 软件的打开和安装

## 终端
对普通用户而言，Linux较Windows比较明显的特点是:Linux中的终端（键盘）会用得非常频繁。我们通过输入指令给终端，进行各种操作。终端的重要属性是当前路径。你在进行操作的时候，要考虑到目标文件的路径和终端当前的操作。建议你通过一些的资料，一边看，一边操作。**你可以不记下来具体的指令，但一定要记得在哪里可以搜到。**

### 一些快捷键
1. 终端里，可以通过方向键的上下箭头，找到前面执行过的指令。
2. ```Ctrl + Shift + C``` 复制 ； ```Ctrl + Shift + V``` 可以将内容粘贴到终端里
3. ```Ctrl + Alt + T``` 打开位于用户名下的终端； 打开终端后 ```Ctrl + Shift + T ``` ，在终端打开新窗口。
4. ```TAB``` 在终端里补全路径等语句
### 基础概念讲解（必看）
1. [文件系统](https://www.runoob.com/linux/linux-system-contents.html)
2. [文件操作](https://www.runoob.com/linux/linux-file-content-manage.html)
3. [APT包管理系统](https://www.runoob.com/linux/linux-comm-apt.html)
### 一些叮嘱
1. [命令大全](https://www.runoob.com/linux/linux-command-manual.html)，不推荐一个一个看，更推荐，遇到什么不会的命令、问题，直接在必应上搜。使用时，要特别注意终端报出的提示。
2. 在遇到一些安装教程或者指令的时候，去读懂每条指令的目的和作用。在接触中，慢慢学习。
3. 有时候，Ubuntu提供的图形化界面确实能减少指令的使用，比如解压缩包，双击即可。
4. 课后作业：安装deb包的时候用什么命令？

## 沟通环境的装配
注意下载Linux版本的
1. [搜狗输入法](https://shurufa.sogou.com/)，（注意，官方的ubuntu20.04的输入法安装教程在整个安装教程的下面）
2. [飞书](https://www.feishu.cn/)
3. 亦可尝试安装微信（为什么说尝试呢，是因为我就没安装成功过，amd的cpu可能有点问题，唯一比较平稳运行的就是鱼香ROS的桌面端微信，但好像经常闪退）

## 开发环境的装配
注意下载Linux版本的，有.deb就选.deb，注意好我们基本上是x86-64或者AMD64的，不要下载错版本了。
### 代码编辑器
不是要全部安装，而是挑选合适的安装。
1. [vscode](https://code.visualstudio.com/)，比较全面的代码编辑器，涵盖许多语言，主要利用插件来逐步完善编辑器功能。
2. [Clion](https://www.jetbrains.com/clion/),推荐自己申请一个学生账号，免费哒！
3. [Pycharm](https://www.jetbrains.com/pycharm/)python的编辑器，好用就完了。
4. [anaconda](https://www.anaconda.com/)。自带jupyter notebook，属于深度学习必备环境管理。但是与ROS2会有些许冲突。ROS2会迷失Python的路径。建议使用时，不要一起开。

### git
1. 在终端输入git，会有语句下载的提示。
2. [下载gitCLI](https://cli.github.com/)，主要使用这个东西进行账号的登录。可以避开一些秘钥的东西。
3. 学习[git命令](https://www.runoob.com/git/git-tutorial.html)



