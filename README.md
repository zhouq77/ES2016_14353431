# DOL开发环境配置
概述：DOL(Distributed operation layer)开发环境是一种用于编写并行应用软件的开发框架，它支持特定的基于计算Kahn进程网络模型的应用范围，以及有基于C系统的仿真引擎。此外，DOL提供的基于XML规范的格式可以用于描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。   
#### 以下为DOL开发环境的具体安装流程:  
##### 前置步骤：安装必要环境
    $	sudo apt-get update
    $	sudo apt-get install ant
    $ 	sudo apt-get install openjdk-7-jdk
    $	sudo apt-get install unzip
##### 1.下载文件
sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz

sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
##### 2.解压文件
接下来执行新建dol的文件夹，将dolethz.zip解压到dol文件夹中，并解压systemc

      $	mkdir dol
    $	unzip dol_ethz.zip -d dol
    $	tar -zxvf systemc-2.3.1.tgz
    
##### 3.编译systemc
解压后进入systemc-2.3.1的目录下,新建一个临时文件夹objdir,进入该文件夹objdir,运行configure(能根据系统的环境设置一下参数，用于编译)

    $	cd systemc-2.3.1   
    $	mkdir objdir
    $	cd objdir
    $	../configure CXX=g++ --disable-async-updates

运行后截图如下：         
![Alt text](http://p1.bqimg.com/567571/d50ac858661108ee.png)

##### 4.编译并获得当前工作路径

    $   sudo make install
    $   cd ..        
    $   ls
    $   pwd
编译完后文件目录如下：           
![Alt text](http://p1.bqimg.com/567571/2c55853e53f4419e.png)
由 pwd 命令得到的工作路径如下：          
![Alt text](http://p1.bqimg.com/567571/62aed27a4732cfbd.png)

##### 5.编译DOL
进入刚刚dol的文件夹中：$   cd ../dol
修改build_zip.xml文件
找到下面这段话，就是说上面编译的systemc位置在哪里，    
<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>    
把YYY改成上页pwd的结果    
接着再进行编译：
$	ant -f build_zip.xml all    
成功显示build successful后，再接着可以试试运行第一个例子：     
进入build/bin/mian路径下：$	cd build/bin/main        
然后运行第一个例子： $	ant -f runexample.xml -Dnumber=1
运行完第一个例子后得到的结果如下：             
![Alt text](http://p1.bqimg.com/567571/548ec22e3c66d933.png)

#### 实验感想与心得：
本次实验内容不多，主要是在配置环境。针对DOL的配置进行的一系列操作，从中可以熟悉一些基本的命令，诸如“mkdir", "pwd"等等。从本次实验中，我们大致可以了解到一些DOL的基本架构和功能，认识到如何在之后的实验中使用DOL工具。希望能在之后的实验中尽快地学会如何具体地使用这些工具来进行综合性的开发。




