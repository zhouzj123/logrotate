# logrotate

The logrotate utility is designed to simplify the administration of log files on a system which generates a lot of log files. Logrotate allows for the automatic rotation compression, removal and mailing of log files. Logrotate can be set to handle a log file hourly, daily, weekly, monthly or when the log file gets to a certain size.

## Download

The latest release is:

* [logrotate-3.16.0](https://github.com/logrotate/logrotate/releases/download/3.16.0/logrotate-3.16.0.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.16.0/logrotate-3.16.0.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.16.0))

Previous releases:

* [logrotate-3.15.1](https://github.com/logrotate/logrotate/releases/download/3.15.1/logrotate-3.15.1.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.15.1/logrotate-3.15.1.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.15.1))
* [logrotate-3.15.0](https://github.com/logrotate/logrotate/releases/download/3.15.0/logrotate-3.15.0.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.15.0/logrotate-3.15.0.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.15.0))
* [logrotate-3.14.0](https://github.com/logrotate/logrotate/releases/download/3.14.0/logrotate-3.14.0.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.14.0/logrotate-3.14.0.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.14.0))
* [logrotate-3.13.0](https://github.com/logrotate/logrotate/releases/download/3.13.0/logrotate-3.13.0.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.13.0/logrotate-3.13.0.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.13.0))
* [logrotate-3.12.3](https://github.com/logrotate/logrotate/releases/download/3.12.3/logrotate-3.12.3.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.12.3/logrotate-3.12.3.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.12.3))
* [logrotate-3.12.2](https://github.com/logrotate/logrotate/releases/download/3.12.2/logrotate-3.12.2.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.12.2/logrotate-3.12.2.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.12.2))
* [logrotate-3.12.1](https://github.com/logrotate/logrotate/releases/download/3.12.1/logrotate-3.12.1.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.12.1/logrotate-3.12.1.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.12.1))
* [logrotate-3.12.0](https://github.com/logrotate/logrotate/releases/download/3.12.0/logrotate-3.12.0.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.12.0/logrotate-3.12.0.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.12.0))
* [logrotate-3.11.0](https://github.com/logrotate/logrotate/releases/download/3.11.0/logrotate-3.11.0.tar.xz) ([sig](https://github.com/logrotate/logrotate/releases/download/3.11.0/logrotate-3.11.0.tar.xz.asc)) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.11.0))
* [logrotate-3.10.0](https://github.com/logrotate/logrotate/releases/download/3.10.0/logrotate-3.10.0.tar.gz) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.10.0))
* [logrotate-3.9.2](https://github.com/logrotate/logrotate/releases/download/3.9.2/logrotate-3.9.2.tar.gz) ([Changelog](https://github.com/logrotate/logrotate/releases/tag/3.9.2))

## Git checkout

You can also obtain code by using git checkout:
```
git clone https://github.com/logrotate/logrotate.git -b master
```

Replace `master` with branch or tag you intend to checkout

## Verify and unpack

After downloading the tarball and .asc signature file, check the signature:

Get Kamil's PGP key rsa4096/72A37B36
(almost any keyserver will do if pgp.mit.edu is temporarily unavailable):

    $ gpg --keyserver pgp.mit.edu --recv-key 992A96E075056E79CD8214F9873DB37572A37B36

and verify the PGP signature on the distribution tarball:


    $ gpg --verify logrotate-3.11.0.tar.xz.asc logrotate-3.11.0.tar.xz


If successful your GPG output should look like this:

    gpg: Signature made Fri 02 Dec 2016 08:30:39 AM EST
    gpg:                using RSA key 873DB37572A37B36
    gpg: Good signature from "Kamil Dudka <kdudka@redhat.com>" [unknown]
    gpg: WARNING: This key is not certified with a trusted signature!
    gpg:          There is no indication that the signature belongs to the owner.
    Primary key fingerprint: 992A 96E0 7505 6E79 CD82  14F9 873D B375 72A3 7B36

You may then unpack the tarball:

    $ tar -xJf logrotate-3.11.0.tar.xz

Notice that git tags are signed with same key:

    $ git tag --verify 3.11.0

## Compiling

Obtain source either by [Downloading](#download) it or doing [Git checkout](#git-checkout).

Install dependencies for Debian systems:
```
apt-get update
apt-get install autoconf automake libpopt-dev libtool make xz-utils
```

Install dependencies for Fedora/CentOS systems:

```
yum install autoconf automake libtool make popt-devel xz
```

Compilation (`autoreconf` is optional if you obtained source from tarball):
```
cd logrotate-X.Y.Z
autoreconf -fiv
./configure
make
```

# Patches and Questions

Open issues or pull requests on GitHub.


logrotate是linux中日志管理的重要工具，它可以自动对日志进行截断（或轮循）、压缩以及删除旧的日志文件。
在发行版的桌面或者服务器linux系统中这个工具安装一般都是比较容易，或者默认已经自带，但是嵌入式系统一
般需要通过源码来自己构建。本文就如何通过交叉工具链构建logrotate进行讲解。
    由于logrotate依赖于POPT库，所以要生成logrotate需要先构建POPT库，然后再利用POPT库构建logrotate。
	
一、构建POPT库
    从https://github.com/devzero2000/POPT下载最新的master分支源码包POPT-master.zip
  1. 解压POPT-master.zip到/home/warmbobo/tools/POPT-master/目录，进入此源码目录
  2. 生成configure文件
	# ./autogen.sh  
		如果安装了libtool，仍报错，就执行下面操作
	   sudo apt install libtool-bin
  3. 配置交叉编译环境
    1）创建安装目录# mkdir install    
	2）添加交叉工具链环境变量# export PATH=$PATH:/home/warmbobo/crosstool/arm-unknown-linux-gnueabi/bin/    
	3）配置编译环境
	  # ./configure --host=mipsel-openwrt-linux --prefix=$PWD/install CFLAGS=-fno-stack-protector
	   重要：CFLAGS=-fno-stack-protector : 不使用栈保护， 如果使用栈保护，会导致logrotate编译不过
	4. 构建
    1) make
    2) make install
    构建好后会在$PWD/install  生成“include  lib  share” 三个目录，
	其中lib目录有logrotate编译和运行需要的库文件，include目录有我们编译logrotate需要的头文件。
	
二、构建logrotate
    从https://github.com/logrotate/logrotate下载最新的源码logrotate-master.zip。
  1. 解压并进入源码路径/home/warmbobo/tools/logrotate-master/ 
  2. 生成configure文件# ./autogen.sh  
  3. 配置交叉编译环境
    1）添加交叉工具链环境变量# export PATH=$PATH:/home/warmbobo/crosstool/arm-unknown-linux-gnueabi/bin/    
	2）配置编译环境  
	  # ./configure CC=mipsel-openwrt-linux-gcc --host=mipsel-openwrt-linux --prefix=$PWD/install \
	     LDFLAGS=-L./install/popt/lib CPPFLAGS=-I./install/popt/include  
	  其中LDFLAGS指定logrotate编译依赖库lpopt路径；
	  而CPPFLAGS指定logrotate编译依赖头文件popt.h路径。
  4.构建
    1）make
    2）make install
    构建好后会在/home/warmbobo/tools/logrotate-master/install/目录生成sbin/logrotate文件。

三、单板运行
   将编译生成的logrotate文件拷贝到单板的/sbin目录，同时将POPT编译生成的lib/* 所有文件拷贝到单板/lib/目录:
   然后就可以运行logrotate命令了。

