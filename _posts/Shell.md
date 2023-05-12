## grep

grep 是代表“全局正则表达式打印”的首字母缩写词。grep 是一个程序，它逐行扫描一个或多个指定文件，返回包含模式的行。模式是一种表达式，它通过将字符解释为元字符来指定一组字符串。例如，星号元字符 (*) 被解释为“零个或多个前面的元素”。这使用户能够在 grep 命令中键入一小段字符和元字符，让计算机向我们显示文件匹配的行。

标准的 grep 命令如下所示：

```
grep <flags> '<regular expression>' <filename>
```

grep 将搜索结果打印到屏幕 (stdout) 并返回以下退出值：

```
0    A match was found.
1    No match was found.
>1   A syntax error was found or a file was inaccessible 
     (even if matches were found).
```

一些常见的标志是：`-c`用于计算成功匹配的数量而不打印实际匹配，`-i`使搜索不区分大小写，`-n`在每个匹配打印输出之前打印行号，`-v`取正则表达式的补码（即返回行不匹配），并`-l`打印包含与表达式匹配的行的文件的文件名。

## egrep

egrep 是代表“扩展全局正则表达式打印”的首字母缩写词。

egrep 中的“E”表示将模式视为正则表达式。在 egrep 中启用了缩写为“ERE”的“扩展正则表达式”。egrep（与 相同`grep -E`）将`+`, `?`, `|`, `(`, 和`)`视为元字符。

在基本正则表达式（使用 grep）中，元字符`?`, `+`, `{`, `|`, `(`, 和`)`失去了它们的特殊含义。如果您希望 grep 将这些字符视为元字符，请将它们转义 `\?`, `\+`, `\{`, `\|`, `\(`, 和`\)`。

例如，这里 grep 使用基本的正则表达式，其中加号按字面意思处理，返回任何带有加号的行。

```
grep "+" myfile.txt
```

另一方面，egrep 将“+”视为元字符并返回每一行，因为加号被解释为“一次或多次”。

```
egrep "+" myfile.txt
```

这里返回每一行，因为`+`egrep 将其视为元字符。正常的 grep 只会搜索带有文字的行`+`。

## fgrep

fgrep 是代表“固定字符串全局正则表达式打印”的首字母缩写词。

fgrep（与 grep -F 相同）是固定的或快速的 grep，其行为与 grep 相同，但不将任何正则表达式元字符识别为特殊字符。搜索将更快地完成，因为它只处理简单的字符串而不是复杂的模式。

例如，如果我想在 .bash_profile 中搜索文字点 (.)，那么使用 grep 会很困难，因为我必须转义点，因为点是一个元字符，表示“通配符，任何单个字符”：

```bash
grep "." myfile.txt
```

上面的命令返回 myfile.txt 的每一行。改为这样做：

```bash
fgrep "." myfile.txt
```

然后只有具有文字“。”的行 在他们返回。fgrep 帮助我们不用费心转义我们的元字符。

## pgrep

pgrep 是一个首字母缩写词，代表“Process-ID Global Regular Expressions Print”。

pgrep 查看当前正在运行的进程并将与选择条件匹配的进程 ID 列出到标准输出。当您只想知道进程的进程 ID 整数时，pgrep 很方便。`pgrep mysql`例如，如果我只想知道我的 mysql 进程的进程 ID，我会使用返回进程 ID 的 命令，如 7312

```bash

pgrep -f "lcltc"

```

```shell
#!/bin/sh  
#!/bin/bash  
  
# 上一个进程名关键字（可能不同的版本），当前进程的jar名  
JAR_NAME='app-mt-lcltc-provider'  
# source /etc/profile  
# ps -ef | grep "$JAR_NAME" |grep -v grep |awk '{print $2}' |xargs kill -9  
LAST_PID=$(pgrep -f "${JAR_NAME}")  
  
if [ -z "${LAST_PID}" ];then  
    echo "无正在运行的进程"  
else  
    echo "正在运行的进程(PID):${LAST_PID}"  
    kill -9 "${LAST_PID}"  
    echo "kill -9 (PID):${LAST_PID}"  
fi  
  
# 获取所在目录  
install_dir="$( cd "$( dirname "${BASH_SOURCE[0]}" )" >/dev/null 2>&1 && pwd )"  
echo "JAR所在目录：${install_dir}"  
  
# 找到所在目录中JAR的全名  
jar_file_name="$(ls ${install_dir} |grep ${JAR_NAME})"  
echo "JAR包：${install_dir}/${jar_file_name}"  
  
  
java -Xms512m -Xmx2048m -jar -Dfile.encoding=utf-8 -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath="${install_dir}" "${install_dir}/${jar_file_name}" --spring.main.allow-bean-definition-overriding=true --sms.platform.key:ALI_CLOUD > /dev/null &  
echo '已启动'
```

```Shell

journalctl -f -u logstash

```

# TCPDUMP

yum -y install tcpdump

```bash
### 可用的网卡
tcpdump -D

### 监听特定主机
# 例子：监听本机跟主机`182.254.38.55`之间往来的通信包。
# 备注：出、入的包都会被监听。
tcpdump host 182.254.38.55

### 特定来源、目标地址的通信
# 特定来源
tcpdump src host hostname
# 特定目标地址
tcpdump host hostname

### Show the HTTPs Traffic

tcpdump -nnSX port 443



```

```bash
tcpdump -ni eth0 -ttt
```

-ttt 输出所包含的DELTA时间，测量了包和包之间的时间。

# SYS-STATE

yum -y install sysstate

## netstat

# WHEREIS

```bash
whereis [OPTIONS] FILE_NAME...

```

在没有任何选项的情况下使用时，在`whereis`二进制文件、源文件和手册文件中搜索指定为参数的命令。

默认情况下，在环境变量`whereis`中列出的硬编码路径和目录中搜索命令的文件 。使用该选项查找命令搜索的目录。[](https://linuxize.com/post/how-to-set-and-list-environment-variables-in-linux/)`-l``whereis`

# PS

# | GREP

```bash
cat logs/log_info.log |grep -C2 "375c0b933d3741f18d4da0725c1f460e"
```

# TAIL

```bash
tail -f log_error.log
```

# DU

```bash
 du -lh --max-depth=1
```

# FDISK 

```bash
[root@localhost ~]# fdisk  -l

磁盘 /dev/sda：214.7 GB, 214748364800 字节，419430400 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 4096 字节
I/O 大小(最小/最佳)：4096 字节 / 4096 字节
磁盘标签类型：dos
磁盘标识符：0x000c0d89

   设备 Boot      Start         End      Blocks   Id  System
/dev/sda1   *        2048     2099199     1048576   83  Linux
/dev/sda2         2099200   104857599    51379200   8e  Linux LVM
/dev/sda3       104857600   419430399   157286400   8e  Linux LVM

磁盘 /dev/mapper/centos_localhost-root：211.5 GB, 211514556416 字节，413114368 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 4096 字节
I/O 大小(最小/最佳)：4096 字节 / 4096 字节


磁盘 /dev/mapper/centos_localhost-swap：2147 MB, 2147483648 字节，4194304 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 4096 字节
I/O 大小(最小/最佳)：4096 字节 / 4096 字节
```

```bash
[root@localhost ~]# fdisk /dev/sda

输入 P

磁盘 /dev/sda：64.4 GB, 64424509440 字节，125829120 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 4096 字节
I/O 大小(最小/最佳)：4096 字节 / 4096 字节
磁盘标签类型：gpt
Disk identifier: E6BE8ED6-EC6F-4209-89A0-207377F7C988


#         Start          End    Size  Type            Name
1         2048       411647    200M  EFI System      EFI System Partition
2       411648      2508799      1G  Microsoft basic
3      2508800    125827071   58.8G  Linux LVM
```

```text

```


```bash




# 查看已分区数量（我看到有两个 /dev/sda1 /dev/sda2）
输入 n　　　　　　　
# 新增加一个分区
输入 p　　　　　　　
# 分区类型我们选择为主分区
分区号输入 3
# （因为1,2已经用过了,sda1是分区1,sda2是分区2,sda3分区3）,确认输入回车　　　　　 
默认（起始扇区） 输入 回车　　　　　 
默认（结束扇区） 
# t 修改分区类型
# 选分区3 
输入 8e
# 修改为LVM（8e就是LVM） w　　　　　 　
写分区 输入 q 完成，退出fdisk命令 

使用partprobe命令 或者重启机器

进入lvm，通过vgdisplay查看组名：为centos_localhost

lvm　　　　　　　　　　　　 #进入lvm管理 lvm>pvcreate /dev/sda3　　 #这是初始化刚才的分区3 lvm>vgextend centos_localhost /dev/sda3 #将初始化过的分区加入到虚拟卷组centos (卷和卷组的命令可以通过 vgdisplay ) lvm>vgdisplay -v或者vgdisplay查看free PE /Site lvm>lvextend -l+38399 /dev/centos_localhost/root　　#扩展已有卷的容量（2559 是通过vgdisplay查看free PE /Site的大小） lvm>pvdisplay #查看卷容量 lvm>quit 　#退出

xfs_growfs /dev/centos_localhost/root 扩容

df -hl
```
