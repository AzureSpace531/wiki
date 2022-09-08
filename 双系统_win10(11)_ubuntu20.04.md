**更新于22.9.8**


在R9000P上测试，可行。
## 安装双系统
### 装前提醒
1. 在这个环节上遇到问题，可以直接问，或者用bing搜。
2. 注意csdn上的答案，可能有诈。
3. ubuntu的相关操作可以参考wiki中的一篇Ubuntu系统教程。

### 一、安装ubuntu20.04
1. 进入[ubuntu20.04的安装网址](https://releases.ubuntu.com/20.04/)，下载20.04.05的desktop版本。此时会下载名称为：ubuntu-20.04.5-desktop-amd64.iso
2. 烧录系统：准备一只8GB的空白U盘，下载[rufus](https://rufus.ie/zh/)。完成后，打开rufus，在引导类型中，选择路径到先前下载好的ubuntu-20.04.5-desktop-amd64.iso的文件。直接按下确定，待烧录完成。
3. 清空磁盘：在windows下搜“磁盘管理”，并打开页面。然后参考[以下教程](https://consumer.huawei.com/cn/support/laptop-user-guide/disk-partition/)中的“如何创建磁盘分区”。
4. 进入电脑的bios，然后将“安全启动”功能关闭。关键字样有：security,ecure boot。enable改为disable。
5. 将烧录好的U盘插入电脑中，使用U盘启动。win10中，按住Shift 点击重启。
6. 点击U盘相关的选项，进入ubuntu的安装选项。语言最好选英文，选择正常安装。在安装类型中，选择与 windows Boot Manager并存。密码推荐为简单的单个数字、字母。（因为在系统上下载东西，会要求输入该密码，以获取权限）
7. 等待安装完成，重启后，拔下U盘。
8. 开机的时候，会出现一个短暂的**系统选择**。通过方向键和回车选择。第一个为ubuntu，第三个才是Windows系统
9. 你会发现windows的时间发生了变动。请参照另一篇Ubuntu系统教程。

### 二、更换ubuntu的源
1. 在Settings里的最后一栏About,最后一栏Software Updates,里面有个Download from,找到China，在China那里选含有ustc字样的。之后确定即可。
### 三、翻墙
1. 准备机场。这个见人见智。或者直接问学长。
2. 安装[clash for windows](https://github.com/Fndroid/clash_for_windows_pkg/releases): 点击链接，寻找x64-linux.tar.gz为后缀的，点击下载。
3. 接下来的操作参照：[clash的设置](https://www.cnblogs.com/Jiang13537/p/15571504.html)
#### 进阶，**打开TUN模式**
1. 此举为了全面翻墙，但是要注意，校园网也有一些微弱的翻墙功能。是否使用，应视实际使用情况。
2. 要进入General，然后点击Service Mode的Manage ，点击 install ,等上一会儿，估计3min；
3. 3分钟后不行，则重启一下系统，重复以上操作。
4. 绿了之后即可打开Tun。


