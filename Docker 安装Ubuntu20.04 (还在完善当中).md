**参考教程**: [(144条消息) 超详细Windows10/Windows11 子系统（WSL2）安装Ubuntu20.04（带桌面环境）_user-zhaowei的博客-CSDN博客_wsl 桌面环境](https://blog.csdn.net/weixin_44301630/article/details/122390018?spm=1001.2014.3001.5506)

# 安装

## 安装docker dekstop
😭摆！看别人的教程把！
[windows安装docker_一个说自己不是和尚的和尚的博客-CSDN博客_docker windows](https://blog.csdn.net/weixin_39912640/article/details/120391027?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522166607834216800186564262%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=166607834216800186564262&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~sobaiduend~default-3-120391027-null-null.article_score_rank_blog&utm_term=windows%20docker%E5%AE%89%E8%A3%85&spm=1018.2226.3001.4450)

## 创建容器

+ 不使用宿主的梯子(推荐)
```shell
docker run -itd --privileged=true --name=azure_space_xface_noproxy2 -p 3393:3389 ubuntu:20.04
```

+ 使用宿主梯子(我还没解决，不要用)
```shell
docker run -itd --privileged=true --network=host --name=azure_space_proxy -p 3392:3389 ubuntu:20.04
```

## 容器初始化

```shell
apt-get update

# 安装sudo模块
apt-get install sudo
```

## 更换ubuntu的下载源

**前置操作**
```shell
sudo apt-get install --reinstall ca-certificates
```

#### 如何手动替换(以清华源为例)

+ 首先先安装nano编辑器或vim编辑器
```shell
# 安装nano编辑器
sudo apt-get install nano

# 安装vim
sudo apt-get install vim
```

+ 打开配置文件并备份原来的文件
```shell
# 备份原来的软件源
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
# 编辑软件源
sudo nano /etc/apt/sources.list
```

+ 替换文本


+ 安装完之后更新一下源
```shell
sudo apt-get update
```



#### 清华源 
**链接:** https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/

1. **手动替换**
```shell
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-proposed main restricted universe multiverse
```

2. **自动替换**
执行如下命令自动替换
```shell
sudo sed -i "s@http://.*archive.ubuntu.com@https://mirrors.tuna.tsinghua.edu.cn@g" /etc/apt/sources.list
sudo sed -i "s@http://.*security.ubuntu.com@https://mirrors.tuna.tsinghua.edu.cn@g" /etc/apt/sources.list

sudo apt-get update
```

## 安装Ubuntu可视化桌面

### xface

#### xrdp方式

+ xface
```shell
sudo apt install xubuntu-desktop
```

##### 安装xrdp
```shell
sudo apt install xrdp
 
```

##### xrdp初始化
```shell
sudo adduser xrdp ssl-cert
```

##### 检查xrdp是否正确开启
检查**xrdp**与**xrdp-seaman**是否都正常**running**
```shell
service xrdp status
```

😭如果显示**is not running**
```shell
# 重启xrdp服务，重启之后记得再次检查一下xrdp和xrdp-seaman是否都running了
service xrdp restart
```
+ xface 桌面(不执行这个命令会导致输入密码后闪退)
```shell
touch .xsession
echo xfce4-session >~/.xsession
sudo chown root:root .xsession
```
##### 使用windows的mstsc(远程桌面连接)显示ubuntu桌面
![](Pasted%20image%2020221018152752.png)




#### vnc方法

#### xmind+shell方法



## ros-noetic 安装

### 获取密钥
```shell
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```


### 换下载源
这里推荐使用中科大的源，中科大的源速度快而且没有连接不上的情况。
```shell
sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.ustc.edu.cn/ros/ubuntu/ `lsb_release -cs` main" > /etc/apt/sources.list.d/ros-latest.list'

```


### 安装下载

首先，确保你的Debian软件包索引是最新的：

-   sudo apt update
    

然后选择你想安装“多少部分”的ROS：

-   **完整桌面版安装（Desktop-Full，推荐）**：除了**桌面版**的全部组件外，还包括2D/3D模拟器（simulator）和2D/3D 感知包（perception package）。
    -   `sudo apt install ros-noetic-desktop-full`
        
    
    **桌面版（Desktop）**：包括了**ROS-Base**的全部组件，还有一些工具，比如[rqt](http://wiki.ros.org/rqt)和[rviz](http://wiki.ros.org/rviz)。
    -   `sudo apt install ros-noetic-desktop`
        
    
    **ROS-Base（仅含骨架）**：ROS packaging，build，和communication库。没有图形界面（GUI）工具。
    -   `sudo apt install ros-noetic-ros-base`
        

## 遇到的问题

1. apt命令报证书错误 Certificate verification failed: The certificate is NOT trusted
**解决方案**: [(144条消息) apt命令报证书错误 Certificate verification failed: The certificate is NOT trusted_呆呆象呆呆的博客-CSDN博客](https://blog.csdn.net/qq_41554005/article/details/124140839)

2. 使用xrdp远程连接输入密码账号登陆后闪退
[解决方法](https://blog.csdn.net/weixin_41921520/article/details/106224404?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-4-106224404-blog-99733711.pc_relevant_3mothn_strategy_and_data_recovery&spm=1001.2101.3001.4242.3&utm_relevant_index=6)
**解决方案:** 
```shell
touch .xsession
echo xfce4-session >~/.xsession
sudo chown root:root .xsession

```
3. 密码忘了怎么办
```shell
# 重置密码, docker默认用户名为root
passwd
```

4. systemctl用不了
[(144条消息) System has not been booted with systemd as init system (PID 1). Can‘t operate.问题解决方法_任求其-zzx的博客-CSDN博客](https://blog.csdn.net/qq_43685040/article/details/112056242?spm=1001.2014.3001.5506)
```shell
# 查看xrdp运行是否正常
service xrdp status
# 重启xrdp
service xrdp restart

# 默认开启两个xrdp服务
sudo service xrdp.service enable 
sudo service xrdp-sesman.service enable 
```

5. c盘内存不够了

1. QStandardPaths: XDG_RUNTIME_DIR not set, defaulting to '/tmp/runtime-root'

首先先尝试在终端运行`roscore`

**再不行就运行下面**
终端输入export XDG_RUNTIME_DIR=/usr/lib/
```shell
export XDG_RUNTIME_DIR=/usr/lib/
```

