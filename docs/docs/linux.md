

### Linux 目录结构

```shell
/
├── bin #存放二进制可执行文件，常用命令一般都在这里
├── boot #存放用于系统引导时使用的各种文件
├── dev #用于存放设备文件
├── etc #存放系统管理和配置文件
├── home #存放所有用户文件的根目录
├── lib #存放着和系统运行相关的库文件
├── media #linux 系统会自动识别一些设备，当识别后，linux 会把识别的设备挂载到这个目录下
├── mnt #用户临时挂载其他的文件系统
├── opt #额外安装的可选应用程序包所放置的位置
├── proc #虚拟文件系统目录，是系统内存的映射。可直接访问这个目录来获取系统信息
├── root #超级用户的主目录
├── run #是一个临时文件系统，存储系统启动以来的信息
├── sbin #存放二进制可执行文件，只有 root 才能访问
├── srv #该目录存放一些服务启动之后需要提取的数据
├── sys #存放内核相关文件
├── tmp #用于存放各种临时文件，是公用的临时文件存储点
├── usr #用于存放系统应用程序
└── var #用于存放运行时需要改变数据的文件，比如服务的日志文件
```

### Linux 基础

查看系统信息、内存信息、磁盘信息、负载信息、路由信息、端口信息、进程、登录用户、关机、重启、系统时间、用户管理、文件权限、压缩解压

### Linux 常用命令

|命令|用途|
|-|-|
|netstat -nltp | 查看所有服务的端口及pid |
|du -sh * | 查询目录文件占用大小|
|lsof  -i|查看端口号|
|ps  aux \|grep nginx  | 查看进程 |
| free -h | 查看系统内存使用情况 |
| df -h| 查看系统盘挂载情况 |
| kill | 进程终止 |
| killall | 根据名称终止进程 |
| service mysqld start\|stop\|restart |服务启动\|停止\|重启|
| grep -rn "name" /  | 在/目录查找name |
|find / -name php-fpm|在/目录查找php-fpm的文件|
|uname --help | 内核名称、内核版本、硬件名称、硬件平台、操作系统 |
|cat /proc/cpuinfo |CPU 详细信息 |
|env|环境变量|
|free --help|查看内存使用量和交换区使用量|
|df --help|查看文件系统信息|
|du --help|汇总目录文件使用情况|
|uptime|查看系统运行时间、用户数、负载|
|cat /proc/loadavg|查看系统负载|
|ifconfig | 查看防火墙设置 |
|route --help|查看路由表|
|top|显示进程状态|
|who|查看当前登录用户|
|last|查看用户登录日志|
|cut -d: -f1 /etc/passwd|查看系统所有用户|
|cut -d: -f1 /etc/group|查看系统所有组|
|crontab -l|查看当前用户计划任务|
|rpm -qa|查看所有安装的软件包|
|date|系统时间|
|reboot|系统重启|
|nodetool status | 查看数据库集群状态 |
|systemctl  status  scylla-server.service |  查看单台数据库状态 |

#### [通过PID号找到对应的进程名及所在目录](https://www.cnblogs.com/jie-fang/p/7686521.html)

 	 ls -ail  /proc/8812 查找pid对应执行的命令及文件夹

<img src=".\assets\1188507-20171018142949037-1095590288.png" alt="image" style="zoom:150%;" />

####  [find&&grep](https://www.cnblogs.com/zhangmo/p/3571735.html)
```
find / -name httpd.conf　 #在根目录下查找文件httpd.conf，表示在整个硬盘查找
grep -rn magic /usr/src　　#显示/usr/src目录下的文件(包含子目录)包含magic的行
```

### 会话相关

|命令 | 用途 |
|--|--|
|screen -r （pid name）|进入会话|
|screen -S （name）| 新建会话|
|screen -X  | 共享会话 |
|screen -R name| 存在就进入、不存在就创建会话|
|screen -D -r name| 退出并进入会话|

### Vim

#### 操作模式

normal、insert、command、visual、replace

#### 翻页与移动

- `<c-f>`：向下移动一页 (相当于：ctrl + f)
- `<c-d>`：向下移动半页
- `<c-b>`：向上移动一页
- `<c-u>`：向上移动半页

`h`、`j`、`k`、`l`：`←`、`↓`、`↑`、`→`

- `nh`：向左移动 n 个字符(四个方向均可)
- `^`：移动到行首
- `$`：移动到行尾
- `nG`：移动到指定行数
- `gg`：移动到文档第一行，相当于 1G
- `G`：移动到文档最后一行
- ndd : n 为数字  剪切n行
- nyy : n 为数据 复制n行
- p : 粘贴

#### 查找与替换

- `/word`：输入`/`会进入 command 模式，在输入关键字回车进行搜索
- `?word`：`/`是向光标以后搜索，`?`是向前搜索
- `n`：根据搜索方向定位到下一个匹配目标
- `N`：与`n`相反方向定位匹配目标
- `:n1,n2s/word1/word2/g`：n1,n2 表示数字，替换n1行到n2行的单词
- `:1,$s/word1/word2/g`：全文替换，也可以写成`:%s/word1/word2/g`
- `:1,$s/word1/word2/gc`：全文替换，并出现确认提示

### 负载查看

使用 uptime、w、top 命令查看

`load average: 0.00, 0.01, 0.05`，系统的平均负荷，对应 1分钟、5分钟、15分钟

X 个 CPU 的电脑，可接受的系统负荷最大为 `X.0` 。将`15分钟`系统负荷作为服务器正常运行的指标


### 命令与文件查找

#### which-寻找可执行文件

```text
[root@localhost ~]# which php
/usr/bin/php
```

#### whereis-特定目录寻找

```text
[root@localhost ~]# whereis php
php: /usr/bin/php /usr/lib64/php /etc/php.d /etc/php.ini /usr/include/php /usr/share/php /usr/share/man/man1/php.1.gz
```

#### find-直接搜索硬盘

```text
[root@localhost ~]# find / -name php-fpm
/run/php-fpm
/etc/sysconfig/php-fpm
/etc/logrotate.d/php-fpm
/var/log/php-fpm
/usr/sbin/php-fpm
```

### 数据流重定向

#### 数据流

数据流分为三类：标准输入(stdin)、标准输出(stdout)、标准错误输出(stderr)

> /dev/null：是一个特殊的设备文件，这个文件接收到的任何数据都会被丢弃。因此，null 这个设备通常也被成为位桶(bit bucket)或黑洞

#### 管道命令

可以处理前一个标准输出信息，对标准错误输出没有处理能力

#### 截取命令

- cut：将以行为单位的字符串进行切割
- grep：分析一行字符，截取所需要的特定信息

#### 排序命令

- sort：可以依据不同的数据类型进行排序
- uniq：数据去重
- wc：统计行数、字符数

#### 参数转换

- xargs：将标准输入转换成命令行参数

### sed

sed 是一个管道命令，用于分析标准输出。支持数据的替换、删除、新增、截取特定行等功能

### awk

awk 是一个数据处理工具，sed 常常用于一整行的数据处理，awk 则倾向于将一行数据分成数据部分来处理。因此，awk 适合小型的数据进行局部处理

### 计划任务

|代表意义|分钟|小时|日期|月份|星期|指令|
|-|-|-|-|-|-|-|
|数字范围|0-59|0-23|1-31|1-12|0-7|command|

|特殊符号|意义|示例|
|-|-|-|
|\*|表示任何时刻|\*|
|,|表示分隔时段|0 3,6 \* \* \* command(3:00与6:00)|
|-|表示一段时间范围|20 8-12 \* \* \* command(8:20~12:20)|
|/n|每隔 n 段时间|*/5 \* \* \* \* command(每五分钟进行一次)|



### Linux 内存管理

### 进程、线程、协程区别

#### 进程

进程是一个程序在一个数据集中的一次动态执行过程，可以简单理解为“正在执行的程序”，它是CPU 资源分配和调度的独立单位

#### 线程

线程是在进程之后发展出来的概念。 线程也叫轻量级进程，它是一个基本的 CPU 执行单元，也是程序执行过程中的最小单元，由线程 ID、程序计数器、寄存器集合和堆栈共同组成。一个进程可以包含多个线程

#### 协程

协程是一种用户态的轻量级线程，又称微线程，英文名 Coroutine，协程的调度完全由用户控制

### 进程间通信与信号机制

#### 通信方式

信号量、消息队列、共享内存、信号、管道、套接字

#### 信号机制

信号是操作系统中进程间通讯的一种有限制的方式，是一种异步的通知机制，用来提醒进程一个事件已经发送

- SIGHUP：控制台操作
- SIGINT：终止进程，`Ctrl + C`
- SIGKILL：终止进程，`kill -9`
- SIGSTOP：停止进程的执行
- SIGCONT：恢复进程的执行

