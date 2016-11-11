## 1. Configure your Ubuntu repositories 软件中心配置
Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse."
![img1](http://images2015.cnblogs.com/blog/979377/201608/979377-20160817151652093-335406272.png)
## 2. Setup your sources.list 添加源
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
## 3. Set up your keys 设置密钥
$ sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
## 4. Installation 安装
确保系统软件处于最新版
$ sudo apt-get update
Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception 
$ sudo apt-get install ros-jade-desktop-full
## 5. Initialize rosdep 初始化rosdep
$ sudo rosdep init
$ rosdep update
## 6. Environment setup 设置环境变量
$ echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
## 7. Getting rosinstall 安装插件rosinstall
$ sudo apt-get install python-rosinstall
## 8. Test 测试ROS
启动ROS
$ roscore
![ros.png](http://upload-images.jianshu.io/upload_images/3243720-0d9d337292aac574.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
显示 started core service [/rosout] 安装成功
