**更新于22.9.8**
在R9000P上测试，可行。
## 安装双系统
### 一、安装ubuntu20.04
1. 进入[ubuntu20.04的安装网址](https://releases.ubuntu.com/20.04/)，下载20.04.05的desktop版本。此时会下载名称为：ubuntu-20.04.5-desktop-amd64.iso
2. 烧录系统：准备一只8GB的空白U盘，下载[rufus](https://rufus.ie/zh/)。完成后，打开rufus，在引导类型中，选择路径到先前下载好的ubuntu-20.04.5-desktop-amd64.iso的文件。直接按下确定，待烧录完成。
3. 清空磁盘：在windows下搜“磁盘管理”，并打开页面。然后参考[以下教程](https://consumer.huawei.com/cn/support/laptop-user-guide/disk-partition/)中的“如何创建磁盘分区”。
4. 进入电脑的bios，然后将“安全启动”功能关闭。关键字样有：security,ecure boot。enable改为disable。
5. 将烧录好的U盘


[https://www.bilibili.com/video/BV11k4y1k7Li?vd_source=a7a4b46a904073df2ce2942708049815](https://www.bilibili.com/video/BV11k4y1k7Li?vd_source=a7a4b46a904073df2ce2942708049815)

参考这个视频，但是在安装ubuntu的时候，直接选正常安装就好了，不用理会他分区的这些复杂操作。



### 更换ubuntu的源


在Settings里的最后一栏About,最后一栏Software Updates,里面有个Download from,找到中国，在中国那里选含有ustc字样的。之后确定即可。


再然后，进行一次电脑的更新。重启过后问题大概就会解决。

# FanQiang

连接无线网络上github，（如果不能上github，可以使用手机热点尝试或者使用u盘，在windows系统，下载并放回ubuntu）。在github上，搜索clash for windows ，在右边的栏中有releases。点击后，显示的版本即为最新版本。寻找x64-linux.tar.gz为后缀的那一个，点击。现在应该已经在下载了。

（回到ubuntu）。

接下来的操作参照：


[clash的设置](https://www.cnblogs.com/Jiang13537/p/15571504.html)


[代理购买地址](https://my.pokcloud.com/clientarea.php)


在下载ROS2的时候，推荐打开TUN模式，
1. 要进入General，然后点击Service Mode的Manage ，点击 install ,等上一会儿，估计10min或者更久；
2. 等待Service Mode 的小地球变绿。
3. 绿了之后即可打开Tun。
4. 好了！！！你已经装好了双系统，而且在ubuntu上也翻好了墙。
