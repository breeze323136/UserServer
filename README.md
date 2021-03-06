# Linux简单入门


----------


@(在此不介绍关于Unix内核# strong text的各种linux系统了，如果感兴趣请下载ubuntu,centos自行练习，mac用户就是unix内核的系统，自带有shell脚本的命令窗口，那么在window下练习Linux也有那么一些工具，我用的是putty软件，下载就可以使用，关键是你得有一个linux服务器，我用的是阿里云的，买一个也没多少钱，当做练习练习。)
**简介**
这儿将跳过所有关于Linxu的介绍，可自行百度查看关于Linux的介绍。我们假设你已经有了一个Linux系统，那么就可以快速入门学习。以下是需要掌握的常用linux命令：
 
``` 
ls、cd、pwd、man、mkdir、rm、mv、nano、vi、cat、touch、echo、more、less、halt、reboot、
whoami、su、init、clear、head、cp、tail、wc、grep、find、groupadd、groupmod、groupdel、
useradd、usermod、userdel、passwd、chmod、chomod、chown、crontab、mount、umount、service、
ps、start、stop、make
```

##基本命令一


#####ls命令	：列出目录和文件

ls			查看当前目录下的所有文件(不包含隐藏文件)

ls -a 		查看当前目录下的所有文件(包含隐藏文件)

ls -l 或者 ll	以列表的形式查看所有文件信息

ls -al		以列表的形式查看所有文件信息（包含隐藏文件）


<br>

######pwd 显示当前目录
```
[root@iZ28b2y73h7Z ~]# cd /home/ThinkPHP/
[root@iZ28b2y73h7Z ThinkPHP]# pwd
/home/ThinkPHP
[root@iZ28b2y73h7Z ThinkPHP]# 
```

######cd 命令	： 切换目录

cd    /		切换到根目录

cd ..  /切换到上一级目录

cd  /home/code   切换到 根目录下的 home/code 目录下

结果 ls   和 pwd 一起使用试试，一般这也是 Linux最常用的三个命令组合。

#####clear命令：  清屏
```
Welcome to aliyun Elastic Compute Service!

[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# ls
[root@iZ28b2y73h7Z ~]# hostname
iZ28b2y73h7Z
[root@iZ28b2y73h7Z ~]# hostname lianger
[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# ls
[root@iZ28b2y73h7Z ~]# 
[root@iZ28b2y73h7Z ~]# pwd
/root
[root@iZ28b2y73h7Z ~]# cd /home/ThinkPHP/
[root@iZ28b2y73h7Z ThinkPHP]# pwd
/home/ThinkPHP
[root@iZ28b2y73h7Z ThinkPHP]# 
[root@iZ28b2y73h7Z ThinkPHP]# clear    //执行清屏
[root@iZ28b2y73h7Z ThinkPHP]# 

```


#####history 命令 ：查看历史命令(即查看你输入过的命令，最多显示500条命令)，如：
执行 history 后：
```
   89  sudo ./jdk-1.7.sh 
   90  eixt
   91  exit
   92  ls
   93  cd /
   94  ls
   95  cd home/
   96  ls
   97  rm -rf cheers
   98  ls
   99  su -
  100  exit
  101  ls
  102  hostname
  103  hostname lianger
  104  ls
  105  pwd
  106  cd /home/ThinkPHP/
  107  pwd
  108  clear
  109  history
[root@iZ28b2y73h7Z ThinkPHP]# 
```


#####exit 命令：退出
执行 exit 后，shell 会话框将关闭当前会话窗口。

#####date 命令：显示时间

[root@lianger]#date
@(2016年01月26日 星期二 01：01：06 CST)


#####hostname 命令：获取主机名
[root@lianger]#hostname
@(lianger    )

#####cat 命令 :查看文件的内容
```
	[root@lianger]# cat LICENSE.txt
	hinkPHP遵循Apache2开源协议发布，并提供免费使用。
	版权所有Copyright © 2006-2014 by ThinkPHP (http://thinkphp.cn)
	All rights reserved。
	ThinkPHP® 商标和著作权所有者为上海顶想信息科技有限公司。

	Apache Licence是著名的非盈利开源组织Apache采用的协议。
	该协议和BSD类似，鼓励代码共享和尊重原作者的著作权，
	允许代码修改，再作为开源或商业软件发布。需要满足
	的条件： 
	1． 需要给代码的用户一份Apache Licence ；
	2． 如果你修改了代码，需要在被修改的文件中说明；
	3． 在延伸的代码中（修改和有源代码衍生的代码中）需要
```


#####mkdir命令  ：创建目录
[root@lianger]# mkdir /home/demo
[root@lianger]#
[root@lianger]# ls
@(demo)


#####touch 命令：创建文件
[root@lianger]# touch demo.php
[root@lianger]# 
[root@lianger]# ls
@(demo.php)


#####rm 命令：删除文件或目录
```
[root@lianger]# ls
Common  demo  Library   logo.png 
[root@lianger]# rm logo.png 	//删除文件
[root@lianger]# 
[root@lianger]# ls
Common  demo  Library
[root@lianger]# rm demo		//删除目录
[root@lianger]# ls
Common  Library
[root@lianger]# rm -rf Library		//删除多级目录
[root@lianger]# 
[root@lianger]# ls
Common
```

#####man 命令： 命令帮助，相当于 windows 的 help，如果遇到哪个命令不会使用，你可以如下操作
```
[root@lianger]# man mv 
```
```
MV(1)                            User Commands                           MV(1)

NAME
       mv - move (rename) files

SYNOPSIS
       mv [OPTION]... [-T] SOURCE DEST
       mv [OPTION]... SOURCE... DIRECTORY
       mv [OPTION]... -t DIRECTORY SOURCE...

DESCRIPTION
       Rename SOURCE to DEST, or move SOURCE(s) to DIRECTORY.

       Mandatory  arguments  to  long  options are mandatory for short options
       too.

       --backup[=CONTROL]
              make a backup of each existing destination file

       -b     like --backup but does not accept an argument

       -f, --force
              do not prompt before overwriting
 Manual page mv(1) line 1 (press h for help or q to quit)
```

#####mv 命令： 移动或充命名文件/目录
不难看出 mv 的命令是什么意思，它用于文件或目录的移动以及改名

mv[可选]  源文件  目标文件
如 将/home/code/demo.php 移动到/home/ThinkPHP/demo/下
```
[root@lianger]# mv /home/code/demo.php /home/ThinkPHP/
```
<br><br>
如 将/home/code/demo.php 移动到/home/ThinkPHP/demo/下,并重命名为 index.php
```
[root@lianger]# mv /home/code/demo.php /home/ThinkPHP/index.php
```
<br><br>
如 将demo.php 重命名为 index.php
```
[root@lianger]# cd /home/ThinkPHP/
[root@lianger]# ls
demo.php
[root@lianger]# mv demo.php index.php
[root@lianger]# 
[root@lianger]# ls
index.php
```

#####cp 命令   ：复制文件，用法跟 mv 和 rm 相似
cp [option] 源文件1 源文件2...  目标文件
常用参数;  -i  复制文件到 某位置，如果文件已存在，覆盖时总是先询问 y/n
				  -r 递归持续复制，用于多级目录的复制行为

如：将 /home/ThinpPHP目录复制到/home/develop目录下面
```
[root@lianger]# cp -r /home/ThinkPHP /home/develop/
[root@lianger]# 
```

#####echo命令：显示信息，类似于 php 的echo 
```
[root@iZ28b2y73h7Z ThinkPHP]# echo 'dedede'
dedede
[root@iZ28b2y73h7Z ThinkPHP]# 
```

#####su 命令：切换用户
```
//从 root切换至 futianhao 用户中
[root@iZ28b2y73h7Z ThinkPHP]# su futianhao   
[futianhao@iZ28b2y73h7Z ThinkPHP]$ 
```

----------
**总结：**
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;以上作为 linux 简单入门的必须要掌握的命令，这些也是最基本和常用的命令，也是日常linux 系统中操作得最多的命令。一个系统可以把它看成就是存储数据的硬盘，那么无非就是与文件还有数据打的交道是最多的，当然我们不排除使用一些编辑器、软件和编程语言等。只是在基本的命令行中，最常用的就是上述的命令，给入门Linux的人们降低点难度要求，从而能达到快速入门才是硬道理。

**深入学习建议**
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;作为入门而已，你现在领悟到的只是 Linux世界里的最简单的操作，当然在命令行的世界里也是趣味无穷的，这更能体现出命令行运行的速度和熟练操作一个系统、服务器的运维发展。我强烈建议不要看视频，这是一个很浪费时间的一个过程，那么怎么办呢？‘look books!!!’,以下是我推荐的初中级 linux 学习方向的书籍排序：

		1、鸟哥的 LINUX私房菜之基础学习篇（第三版）

		2、Linux系统管理与网络管理

		3、鸟哥的 LINUX 私房菜服务器篇(第三版)

		4、Linux命令行与 Shell脚本编程大全

