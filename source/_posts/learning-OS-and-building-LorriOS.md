---
title: learning OS and building LorriOS
date: 2016-12-28 15:00:08
categories: [programming, unfinished]
tags: [OS, kernel]
---

暂时用以记录操作系统的学习，以及开发自己的一个toy OS，作为一个项目日志?(如果能成功的话。。)。写这个东西的目的还是给我自己看的（估计其他人也会看的一头雾水吧，笑），毕竟人不太可能一次就找到正确的道路，所以日志写起来可能非常乱糟糟。所以说这只是一个记录，没有什么真正的参考价值。等这个toy os完成的差不多了，我应该会再来总结和记录一下。

另外，下面的DayN并不是真正的天数，毕竟平时也要上课，不可能连续进行。所以大概是按每一次尝试，来进行划分的。

----

刚开始浏览了一下操作系统的基本知识，按考研复习的来吧，然后看的忽然有点跃跃欲试就想能不能写一个简单的OS。

# Day1:

一开始从《30天自制操作系统》开始看，以前有一点汇编基础所以看起来感觉还是可以接受的。

看到第三天就下不去了，倒不是因为内容看不懂，而是环境的问题吧。作者是基于win，用了很多小程序，我用的是os x，很多时候要找一些替代方法。参考网上linux的解决方案，毕竟os x还是不太一样，到下面这一步就是不行，把haribote.bin写到myos.img。

```shell
# makefile
mkdir -p /tmp/floppy
mount -o loop myos.img /tmp/floppy -o fat=12 # 这一条在mac不适用
sleep 1
cp haribote.bin /tmp/floppy
sleep 1
umount /tmp/floppy
```

Os x 上貌似不能直接mount，当然我也尝试了一些其他的办法，最终失败，感觉不太想再花时间在细枝末节上，打算回法国后在ubuntu下开发，或者和书上保持一样，在win下开发。

# Day2:

第二天开始阅读《ORANGE'S：一个操作系统的实现》，并打算先阅读，等了解大致情况再动手，不然也只是抄代码，并且在一知半解的情况下容易卡在一些细枝末节的地方。

同时也可以参考UnixV6，这个是MIT用于教学写的一个类unix的OS，有配套的课程。

两天下来感觉mac用于web开发十分方便，但是内核开发感觉网上的文档、案例偏少，当然主要也是我比较弱，不能够举一反三。一般来说，要不是面向初学者如《30天》而采用win，要不就是使用linux（果然linux才是王道= =）

下面是在mac上编译uv6的配置（没有测试，纯搬运）

>### Configuration
>
>1.  Install [Xcode](http://itunes.apple.com/us/app/xcode/id497799835).  After installing Xcode install the Command Line Tools from the Downloads section of Xcode's preferences.  I've installed Xcode Version 4.5 (4G182).
>2.  Install [Homebrew](http://mxcl.github.com/homebrew/)
>3.  Install pre-requisites for building xv6
>    ```bash
>        $ brew install glib gmp mpfr pkgconfig ppl
>        $ brew install libmpc --use-llvm
>        $ brew install qemu --use-gcc
>    ```
>4.  Install GNU binutils
>    ```bash
>        $ cd /tmp
>        $ curl -O http://ftp.gnu.org/gnu/binutils/binutils-2.22.tar.gz
>        $ tar -xvzf binutils-2.22.tar.gz
>        $ ./configure --target=i386-jos-elf --disable-nls --prefix=/opt/gnu
>        $ make
>    ```
>5.  Install GCC 4.5 via Homebrew
>    ```bash
>        $ cd /tmp
>        $ curl -O http://ftp.gnu.org/gnu/gcc/gcc-4.7.2/gcc-4.7.2.tar.gz
>        $ cd gcc-4.7.2
>        $ ./configure --target=i386-jos-elf --disable-nls --without-headers --with-newlib --disable-threads --disable-shared --disable-libmudflap --disable-libssp --with-system-zlib --disable-lto --with-gmp=/usr/local --enable-languages=c --prefix=/opt/gnu
>        $ LDFLAGS=-L/usr/lib make
>        $ make install
>    ```
>
>### Install and build xv6 with GCC
>
>```bash
>$ git clone git://pdos.csail.mit.edu/xv6/xv6.git
>cd xv6
>make qemu-nox
>```

# Day3:

目前跟着ORANGE，暂时比较顺利，开发环境仍然是mac。基于freedos下成功进入了保护模式。

下面就保护模式做一点笔记。

关于保护模式网上的资料很多，在为什么需要保护模式这个问题上，这里有一个非常直接的要求——我们的系统要运行在32位上，实模式仅支持16位寻址。当然保护模式远远不止如此，但是对于初学者（比如现在的我，囧），它应该是最大的用途之一。

- GDT

   首先要先说一下GDT(Global Descriptor Table)，它是全局描述符表。GDT只有一张，位置任意，通过LGDT指令被存储在GDTR寄存器。

- Selector

   由GDTR访问全局描述符表是通过“段选择子”（实模式下的段寄存器）来完成的。

- LDT

   局部描述符表LDT(Local Descriptor Table)。和GDT类似，直观上与GDT结构相同（其段选择子TI置位），功能上隶属于GDT。GDT只有一张，LDT有多张，每个任务可以有一张。

如果第一次听到上面几个名词，可能还是比较懵逼。我们看看它是怎么运作的。

1. 进行一系列初始化，包括定义GDT，LDT，选择子等
2. 系统默认进入实模式
3. 加载GDT，进入保护模式
4. 加载不同的LDT，以进入不同的子任务
5. 退出保护模式，反回实模式。

上面只列出了关键步骤，实际上还有很多细节问题，这里只是简单记录其大致思想，所以没有提。

不管怎么说，姑且是跨入了保护模式的大门。

# Day4:

### 特权级

在IA32分段机制中，特权级有4个特权级别，

- LEVEL 0: 内核
- LEVEL 1, 2: 服务
- LEVEL 3: 应用程序

处理器通过识别CPL(current privilege level)、DPL(descriptor privilege level)、RPL(requested privilege level)这三个特权级进行特权级检验。

CPL一般被存储在cs和ss的第0位和第1位。CPL等于所在代码段的特权级。当遇到一致代码段时，CPL不改变。（一致代码段能被小于等于它的特权的代码访问）

DPL是段或门的特权级，写在描述符的属性中。

RPL是通过选择子的第0位和第1位表现的。

简单而言，只要CPL和RPL都小于被访问的数据段的DPL就可以了。

### 门

特权级转移可以分为两大类。jmp和call的直接转移；通过描述符间接转移。由于直接转移有诸多的限制，我们常常使用间接转移。

其中，间接转移又分为：

- 指向一个包含目标代码段选择子的门描述符
- 指向一个包含目标代码段选择子的TSS
- 指向一个任务门，它又指向一个包含目标代码段选择子的TSS

门描述符分为四种：

- 调用门 Call gate
- 中断门 Interrupt gate
- 陷阱门 Trap gate
- 任务门 Task gate

# Day5:

### 页表

实模式下，int 15h 获得内存信息

页表这一块看的有点心急，感觉理解不是很到位。以后等弄的更清楚了再来总结。

中途调试的时候总是出问题，没想到最后发现一开始32位代码的权限就定义错了。从现在出错的经历来看，os如果崩了的话，一般是权限问题（可能是因为我现在写的内容不多吧）。所以务必小心检查权限。

书上的代码有一点不是很理解，在PagingDemo它使用了大量的push却没有pop。据我的理解的话，push是把数据存到栈中，而无法改变栈外的内存，它也没有使用ret之类的与栈相关的指令，目前不是很理解。

不理解细节也没办法，先试着看看后面的内容吧。

### 中断和异常

IDT，中断描述符表。IDT中的描述符可以是：

- 中断门描述符
- 陷阱门描述符
- 任务门描述符