##*Description
Distributed Operation Layer : 
The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

##*How to install
安装一些必要的环境(ubuntu为例)：
$	sudo apt-get update
$	sudo apt-get install ant
$ 	sudo apt-get install openjdk-7-jdk
$	sudo apt-get install unzip

1.下载文件
   sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
   sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
 2.解压文件
   新建dol的文件夹 
   $	mkdir dol
   将dolethz.zip解压到 dol文件夹中
   $	unzip dol_ethz.zip -d dol
   解压systemc
   $	tar -zxvf systemc-2.3.1.tgz

3.编译systemc
   解压后进入systemc-2.3.1的目录下
   $	cd systemc-2.3.1
   新建一个临时文件夹objdir
   $	mkdir objdir
   进入该文件夹objdir
   $	cd objdir
   运行configure(能根据系统的环境设置一下参数，用于编译)
   $	../configure CXX=g++ --disable-async-updates
![图片1.jpg](http://upload-images.jianshu.io/upload_images/3243720-e9aba44b55b39767.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
   编译
   $	sudo make install
   编译完后文件目录如下($ cd ..        $ ls
![图片2.jpg](http://upload-images.jianshu.io/upload_images/3243720-95a2aee87ec1bfa9.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
   记录当前的工作路径
   $	pwd
![图片3.jpg](http://upload-images.jianshu.io/upload_images/3243720-6f3e9717284dd3eb.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.编译dol（续上页
   然后是编译
   $	ant -f build_zip.xml all
   若成功会显示build successful

   接着可以试试运行第一个例子
   进入build/bin/mian路径下
   $	cd build/bin/main
   然后运行第一个例子
   $	ant -f runexample.xml -Dnumber=1

   成功结果如图 
![图片4.jpg](http://upload-images.jianshu.io/upload_images/3243720-ac65d857091894d7.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Run example1：
 $ cd build/bin/main
 $ ant -f runexample.xml -Dnumber=1

##*Experimental experience  
实验一开始没安装好必要的环境，就进行了后面的步骤，导致出错。将虚拟机重启之后安装了必要的环境，再进行后面的步骤安装DOL就很顺利了。
