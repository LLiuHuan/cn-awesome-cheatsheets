> BASH CHEATSHEET (中文速查表) - by skywind (created on 2021/07/22)  
> Version: 1, Last Modified: 2021/07/22 15:20  
> https://github.com/LLiuHuan/cn-awesome-cheatsheets

> 转自：https://www.cnblogs.com/chenliangchaoshuai/p/11827383.html

> linux命令是对Linux系统进行管理的命令。对于Linux系统来说，无论是中央处理器、内存、磁盘驱动器、键盘、鼠标，还是用户等都是文件，Linux系统管理的命令是它正常运行的核心。

## 基础命令

### 线上查询及帮助命令(2个)  

man：查看命令帮助，命令的词典，更复杂的还有info，但不常用。

help：查看Linux内置命令的帮助，比如cd命令。

### 文件和目录操作命令(18个)

ls：全拼list，功能是列出目录的内容及其内容属性信息。

cd：全拼change directory，功能是从当前工作目录切换到指定的工作目录。

cp：全拼copy，其功能为复制文件或目录。

find：查找的意思，用于查找目录及目录下的文件。

mkdir：全拼make directories，其功能是创建目录。

mv：全拼move，其功能是移动或重命名文件。

pwd：全拼print working directory，其功能是显示当前工作目录的绝对路径。

rename：用于重命名文件。

rm：全拼remove，其功能是删除一个或多个文件或目录。

rmdir：全拼remove empty directories，功能是删除空目录。

touch：创建新的空文件，改变已有文件的时间戳属性。

tree：功能是以树形结构显示目录下的内容。

basename：显示文件名或目录名。

dirname：显示文件或目录路径。

chattr：改变文件的扩展属性。

lsattr：查看文件扩展属性。

file：显示文件的类型。

md5sum：计算和校验文件的MD5值。

### 查看文件及内容处理命令(21个)

cat：全拼concatenate，功能是用于连接多个文件并且打印到屏幕输出或重定向到指定文件中。

tactac：是cat的反向拼写，因此命令的功能为反向显示文件内容。

more：分页显示文件内容。

less：分页显示文件内容，more命令的相反用法。

head：显示文件内容的头部。

tail：显示文件内容的尾部。

cut：将文件的每一行按指定分隔符分割并输出。

split：分割文件为不同的小片段。

paste：按行合并文件内容。

sort：对文件的文本内容排序。

uniq：去除重复行。

wc：统计文件的行数、单词数或字节数。

iconv：转换文件的编码格式。

dos2unix：将DOS格式文件转换成UNIX格式。

diff：全拼difference，比较文件的差异，常用于文本文件。

vimdiff：命令行可视化文件比较工具，常用于文本文件。

rev：反向输出文件内容。

grep/egrep：过滤字符串，三剑客老三。

join：按两个文件的相同字段合并。

tr：替换或删除字符。

vi/vim：命令行文本编辑器。

### 文件压缩及解压缩命令(4个)

tar：打包压缩。oldboy

unzip：解压文件。

gzipgzip：压缩工具。

zip：压缩工具。

### 信息显示命令(11个)

uname：显示操作系统相关信息的命令。

hostname：显示或者设置当前系统的主机名。

dmesg：显示开机信息，用于诊断系统故障。

uptime：显示系统运行时间及负载。

stat：显示文件或文件系统的状态。

du：计算磁盘空间使用情况。

df：报告文件系统磁盘空间的使用情况。

top：实时显示系统资源使用情况。

free：查看系统内存。

date：显示与设置系统时间。

cal：查看日历等时间信息。

### 搜索文件命令(4个)

which：查找二进制命令，按环境变量PATH路径查找。

find：从磁盘遍历查找文件或目录。

whereis：查找二进制命令，按环境变量PATH路径查找。

locate：从数据库 (/var/lib/mlocate/mlocate.db) 查找命令，使用updatedb更新库。

### 用户管理命令(10个)

useradd：添加用户。

usermod：修改系统已经存在的用户属性。

userdel：删除用户。

groupadd：添加用户组。

passwd：修改用户密码。

chage：修改用户密码有效期限。

id：查看用户的uid,gid及归属的用户组。

su：切换用户身份。

visudo：编辑/etc/sudoers文件的专属命令。

sudo：以另外一个用户身份(默认root用户)执行事先在sudoers文件允许的命令。

### 基础网络操作命令(11个)

telnet：使用TELNET协议远程登录。

ssh：使用SSH加密协议远程登录。

scp：全拼secure copy，用于不同主机之间复制文件。

wget：命令行下载文件。

ping：测试主机之间网络的连通性。

route：显示和设置linux系统的路由表。

ifconfig：查看、配置、启用或禁用网络接口的命令。

ifup：启动网卡。

ifdown：关闭网卡。

netstat：查看网络状态。

ss：查看网络状态。

### 深入网络操作命令(9个)

nmap：网络扫描命令。

lsof：全名list open files，也就是列举系统中已经被打开的文件。

mail：发送和接收邮件。

mutt：邮件管理命令。

nslookup：交互式查询互联网DNS服务器的命令。

dig：查找DNS解析过程。

host：查询DNS的命令。

traceroute：追踪数据传输路由状况。

tcpdump：命令行的抓包工具。

### 有关磁盘与文件系统的命令(16个)

mount：挂载文件系统。

umount：卸载文件系统。

fsck：检查并修复Linux文件系统。

dd：转换或复制文件。

dumpe2fs：导出ext2/ext3/ext4文件系统信息。

dumpe：xt2/3/4文件系统备份工具。

fdisk：磁盘分区命令，适用于2TB以下磁盘分区。

parted：磁盘分区命令，没有磁盘大小限制，常用于2TB以下磁盘分区。

mkfs：格式化创建Linux文件系统。

partprobe：更新内核的硬盘分区表信息。

e2fsck：检查ext2/ext3/ext4类型文件系统。

mkswap：创建Linux交换分区。

swapon：启用交换分区。

swapoff：关闭交换分区。

sync：将内存缓冲区内的数据写入磁盘。

resize2fs：调整ext2/ext3/ext4文件系统大小。

### 系统权限及用户授权相关命令(4个)

chmod：改变文件或目录权限。

chown：改变文件或目录的属主和属组。

chgrp：更改文件用户组。

umask：显示或设置权限掩码。

### 查看系统用户登陆信息的命令(7个)

whoami：显示当前有效的用户名称，相当于执行id -un命令。

who：显示目前登录系统的用户信息。

w：显示已经登陆系统的用户列表，并显示用户正在执行的指令。

last：显示登入系统的用户。

lastlog：显示系统中所有用户最近一次登录信息。

users：显示当前登录系统的所有用户的用户列表。

finger：查找并显示用户信息。

### 内置命令及其它(19个)

echo：打印变量，或直接输出指定的字符串

printf：将结果格式化输出到标准输出。

rpm：管理rpm包的命令。

yum：自动化简单化地管理rpm包的命令。

watch：周期性的执行给定的命令，并将命令的输出以全屏方式显示。

alias：设置系统别名。

unalias：取消系统别名。

date：查看或设置系统时间。

clear：清除屏幕，简称清屏。

history：查看命令执行的历史纪录。

eject：弹出光驱。

time：计算命令执行时间。

nc：功能强大的网络工具。

xargs：将标准输入转换成命令行参数。

exec：调用并执行指令的命令。

export：设置或者显示环境变量。

unset：删除变量或函数。

type：用于判断另外一个命令是否是内置命令。

bc：命令行科学计算器。

### 系统管理与性能监视命令(9个)

chkconfig：管理Linux系统开机启动项。

vmstat：虚拟内存统计。

mpstat：显示各个可用CPU的状态统计。

iostat：统计系统IO。

sar：全面地获取系统的CPU、运行队列、磁盘 I/O、分页(交换区)、内存、 CPU中断和网络等性能数据。

ipcs：用于报告Linux中进程间通信设施的状态，显示的信息包括消息列表、共享内存和信号量的信息。

ipcrm：用来删除一个或更多的消息队列、信号量集或者共享内存标识。

strace：用于诊断、调试Linux用户空间跟踪器。我们用它来监控用户空间进程和内核的交互，比如系统调用、信号传递、进程状态变更等。

ltrace：命令会跟踪进程的库函数调用,它会显现出哪个库函数被调用。

### 关机/重启/注销和查看系统信息的命令(6个)

shutdown：关机。

halt：关机。

poweroff：关闭电源。

logout：退出当前登录的Shell。

exit：退出当前登录的Shell。

Ctrl+d：退出当前登录的Shell的快捷键。

### 进程管理相关命令(15个)

bg：将一个在后台暂停的命令，变成继续执行 (在后台执行)。

fg：将后台中的命令调至前台继续运行。

jobs：查看当前有多少在后台运行的命令。

kill：终止进程。

killall：通过进程名终止进程。

pkill：通过进程名终止进程。

crontab：定时任务命令。

ps：显示进程的快照。

pstree：树形显示进程。

nice/renice：调整程序运行的优先级。

nohup：忽略挂起信号运行指定的命令。

pgrep：查找匹配条件的进程。

runlevel：查看系统当前运行级别。

init：切换运行级别。

service：启动、停止、重新启动和关闭系统服务，还可以显示所有系统服务的当前状态。

## 实用脚本

### 检测两台服务器指定目录下的文件一致性

```bash
#!/bin/bash
#####################################
#检测两台服务器指定目录下的文件一致性
#####################################
#通过对比两台服务器上文件的md5值，达到检测一致性的目的
dir=/data/web
b_ip=192.168.88.10
#将指定目录下的文件全部遍历出来并作为md5sum命令的参数，进而得到所有文件的md5值，并写入到指定文件中
find $dir -type f|xargs md5sum > /tmp/md5_a.txt
ssh $b_ip "find $dir -type f|xargs md5sum > /tmp/md5_b.txt"
scp $b_ip:/tmp/md5_b.txt /tmp
#将文件名作为遍历对象进行一一比对
for f in `awk '{print 2} /tmp/md5_a.txt'`
do
#以a机器为标准，当b机器不存在遍历对象中的文件时直接输出不存在的结果
if grep -qw "$f" /tmp/md5_b.txt
then
md5_a=`grep -w "$f" /tmp/md5_a.txt|awk '{print 1}'`
md5_b=`grep -w "$f" /tmp/md5_b.txt|awk '{print 1}'`
#当文件存在时，如果md5值不一致则输出文件改变的结果
if [ $md5_a != $md5_b ]
then
echo "$f changed."
fi
else
echo "$f deleted."
fi
done
```

### 定时清空文件内容，定时记录文件大小

```bash
#!/bin/bash
################################################################
#每小时执行一次脚本（任务计划），当时间为0点或12点时，将目标目录下的所有文件内
#容清空，但不删除文件，其他时间则只统计各个文件的大小，一个文件一行，输出到以时#间和日期命名的文件中，需要考虑目标目录下二级、三级等子目录的文件
################################################################
logfile=/tmp/`date +%H-%F`.log
n=`date +%H`
if [ $n -eq 00 ] || [ $n -eq 12 ]
then
#通过for循环，以find命令作为遍历条件，将目标目录下的所有文件进行遍历并做相应操作
for i in `find /data/log/ -type f`
do
true > $i
done
else
for i in `find /data/log/ -type f`
do
du -sh $i >> $logfile
done
fi
```

### 检测网卡流量，并按规定格式记录在日志中

```bash
#!/bin/bash
#######################################################
#检测网卡流量，并按规定格式记录在日志中
#规定一分钟记录一次
#日志格式如下所示:
#2019-08-12 20:40
#ens33 input: 1234bps
#ens33 output: 1235bps
######################################################3
while :
do
#设置语言为英文，保障输出结果是英文，否则会出现bug
LANG=en
logfile=/tmp/`date +%d`.log
#将下面执行的命令结果输出重定向到logfile日志中
exec >> $logfile
date +"%F %H:%M"
#sar命令统计的流量单位为kb/s，日志格式为bps，因此要*1000*8
sar -n DEV 1 59|grep Average|grep ens33|awk '{print $2,"\t","input:","\t",$5*1000*8,"bps","\n",$2,"\t","output:","\t",$6*1000*8,"bps"}'
echo "####################"
#因为执行sar命令需要59秒，因此不需要sleep
done
```

### 计算文档每行出现的数字个数，并计算整个文档的数字总数

```bash
#!/bin/bash
#########################################################
#计算文档每行出现的数字个数，并计算整个文档的数字总数
########################################################
#使用awk只输出文档行数（截取第一段）
n=`wc -l a.txt|awk '{print $1}'`
sum=0
#文档中每一行可能存在空格，因此不能直接用文档内容进行遍历
for i in `seq 1 $n`
do
#输出的行用变量表示时，需要用双引号
line=`sed -n "$i"p a.txt`
#wc -L选项，统计最长行的长度
n_n=`echo $line|sed s'/[^0-9]//'g|wc -L`
echo $n_n
sum=$[$sum+$n_n]
done
echo "sum:$sum"
```

### 杀死所有脚本

```bash
#!/bin/bash
################################################################
#有一些脚本加入到了cron之中，存在脚本尚未运行完毕又有新任务需要执行的情况，
#导致系统负载升高，因此可通过编写脚本，筛选出影响负载的进程一次性全部杀死。
################################################################
ps aux|grep 指定进程名|grep -v grep|awk '{print $2}'|xargs kill -9
```

### 从FTP服务器下载文件

```bash
#!/bin/bash
if [ $# -ne 1 ]; then
    echo "Usage: $0 filename"
fi
dir=$(dirname $1)
file=$(basename $1)
ftp -n -v << EOF   # -n 自动登录
open 192.168.1.10  # ftp服务器
user admin password
binary   # 设置ftp传输模式为二进制，避免MD5值不同或.tar.gz压缩包格式错误
cd $dir
get "$file"
EOF
```

### 连续输入5个100以内的数字，统计和、最小和最大

```bash
#!/bin/bash
COUNT=1
SUM=0
MIN=0
MAX=100
while [ $COUNT -le 5 ]; do
    read -p "请输入1-10个整数：" INT
    if [[ ! $INT =~ ^[0-9]+$ ]]; then
        echo "输入必须是整数！"
        exit 1
    elif [[ $INT -gt 100 ]]; then
        echo "输入必须是100以内！"
        exit 1
    fi
    SUM=$(($SUM+$INT))
    [ $MIN -lt $INT ] && MIN=$INT
    [ $MAX -gt $INT ] && MAX=$INT
    let COUNT++
done
echo "SUM: $SUM"
echo "MIN: $MIN"
echo "MAX: $MAX"
```

### 监测Nginx访问日志502情况，并做相应动作

假设服务器环境为lnmp，近期访问经常出现502现象，且502错误在重启php-fpm服务后消失，因此需要编写监控脚本，一旦出现502，则自动重启php-fpm服务。

```bash
#场景：
#1.访问日志文件的路径：/data/log/access.log
#2.脚本死循环，每10秒检测一次，10秒的日志条数为300条，出现502的比例不低于10%（30条）则需要重启php-fpm服务
#3.重启命令为：/etc/init.d/php-fpm restart
#!/bin/bash
###########################################################
#监测Nginx访问日志502情况，并做相应动作
###########################################################
log=/data/log/access.log
N=30 #设定阈值
while :
do
 #查看访问日志的最新300条，并统计502的次数
    err=`tail -n 300 $log |grep -c '502" '`
 if [ $err -ge $N ]
 then
 /etc/init.d/php-fpm restart 2> /dev/null
 #设定60s延迟防止脚本bug导致无限重启php-fpm服务
     sleep 60
 fi
 sleep 10
done
```

### 将结果分别赋值给变量

```bash
应用场景：希望将执行结果或者位置参数赋值给变量，以便后续使用。

方法1：

for i in $(echo "4 5 6"); do
   eval a$i=$i
done
echo $a4 $a5 $a6
方法2：将位置参数192.168.1.1{1,2}拆分为到每个变量

num=0
for i in $(eval echo $*);do   #eval将{1,2}分解为1 2
   let num+=1
   eval node${num}="$i"
done
echo $node1 $node2 $node3
# bash a.sh 192.168.1.1{1,2}
192.168.1.11 192.168.1.12
方法3：

arr=(4 5 6)
INDEX1=$(echo ${arr[0]})
INDEX2=$(echo ${arr[1]})
INDEX3=$(echo ${arr[2]})
```

### 批量修改文件名

```bash
示例：

# touch article_{1..3}.html
# ls
article_1.html  article_2.html  article_3.html
目的：把article改为bbs

方法1：

for file in $(ls *html); do
    mv $file bbs_${file#*_}
    # mv $file $(echo $file |sed -r 's/.*(_.*)/bbs\1/')
    # mv $file $(echo $file |echo bbs_$(cut -d_ -f2)
done
方法2：

for file in $(find . -maxdepth 1 -name "*html"); do
     mv $file bbs_${file#*_}
done
方法3：

# rename article bbs *.html
```

### 把一个文档前五行中包含字母的行删掉，同时删除6到10行包含的所有字母

1）准备测试文件，文件名为2.txt

```
第1行1234567不包含字母
第2行56789BBBBBB
第3行67890CCCCCCCC
第4行78asdfDDDDDDDDD
第5行123456EEEEEEEE
第6行1234567ASDF
第7行56789ASDF
第8行67890ASDF
第9行78asdfADSF
第10行123456AAAA
第11行67890ASDF
第12行78asdfADSF
第13行123456AAAA
```

2）脚本如下：

```bash
#!/bin/bash
##############################################################
#把一个文档前五行中包含字母的行删掉，同时删除6到10行包含的所有字母
##############################################################
sed -n '1,5'p 2.txt |sed '/[a-zA-Z]/'d
sed -n '6,10'p 2.txt |sed s'/[a-zA-Z]//'g
sed -n '11,$'p 2.txt
#最终结果只是在屏幕上打印结果，如果想直接更改文件，可将输出结果写入临时文件中，再替换2.txt或者使用-i选项
```

### 统计当前目录中以.html结尾的文件总大小

```bash
方法1：

# find . -name "*.html" -exec du -k {} \; |awk '{sum+=$1}END{print sum}'

方法2：

for size in $(ls -l *.html |awk '{print $5}'); do
    sum=$(($sum+$size))
done
echo $sum
```

### 扫描主机端口状态

```bash
#!/bin/bash
HOST=$1
PORT="22 25 80 8080"
for PORT in $PORT; do
    if echo &>/dev/null > /dev/tcp/$HOST/$PORT; then
        echo "$PORT open"
    else
        echo "$PORT close"
    fi
done
```

### 用shell打印示例语句中字母数小于6的单词

```bash
#示例语句：
#Bash also interprets a number of multi-character options.
#!/bin/bash
##############################################################
#shell打印示例语句中字母数小于6的单词
##############################################################
for s in Bash also interprets a number of multi-character options.
do
 n=`echo $s|wc -c`
 if [ $n -lt 6 ]
 then
 echo $s
 fi
done
```

### 输入数字运行相应命令

```bash
#!/bin/bash
##############################################################
#输入数字运行相应命令
##############################################################
echo "*cmd menu* 1-date 2-ls 3-who 4-pwd 0-exit "
while :
do
#捕获用户键入值
 read -p "please input number :" n
 n1=`echo $n|sed s'/[0-9]//'g`
#空输入检测 
 if [ -z "$n" ]
 then
 continue
 fi
#非数字输入检测 
 if [ -n "$n1" ]
 then
 exit 0
 fi
 break
done
case $n in
 1)
 date
 ;;
 2)
 ls
 ;;
 3)
 who
 ;;
 4)
 pwd
 ;;
 0)
 break
 ;;
    #输入数字非1-4的提示
 *)
 echo "please input number is [1-4]"
esac
```

### Expect实现SSH免交互执行命令

```bash
Expect是一个自动交互式应用程序的工具，如telnet，ftp，passwd等。

需先安装expect软件包。

方法1：EOF标准输出作为expect标准输入

#!/bin/bash
USER=root
PASS=123.com
IP=192.168.1.120
expect << EOF
set timeout 30
spawn ssh $USER@$IP   
expect {
    "(yes/no)" {send "yes\r"; exp_continue}
    "password:" {send "$PASS\r"}
}
expect "$USER@*"  {send "$1\r"}
expect "$USER@*"  {send "exit\r"}
expect eof
EOF
方法2：

#!/bin/bash
USER=root
PASS=123.com
IP=192.168.1.120
expect -c "
    spawn ssh $USER@$IP
    expect {
        \"(yes/no)\" {send \"yes\r\"; exp_continue}
        \"password:\" {send \"$PASS\r\"; exp_continue}
        \"$USER@*\" {send \"df -h\r exit\r\"; exp_continue}
    }"
方法3：将expect脚本独立出来

登录脚本：

# cat login.exp
#!/usr/bin/expect
set ip [lindex $argv 0]
set user [lindex $argv 1]
set passwd [lindex $argv 2]
set cmd [lindex $argv 3]
if { $argc != 4 } {
puts "Usage: expect login.exp ip user passwd"
exit 1
}
set timeout 30
spawn ssh $user@$ip
expect {
    "(yes/no)" {send "yes\r"; exp_continue}
    "password:" {send "$passwd\r"}
}
expect "$user@*"  {send "$cmd\r"}
expect "$user@*"  {send "exit\r"}
expect eof
执行命令脚本：写个循环可以批量操作多台服务器

#!/bin/bash
HOST_INFO=user_info.txt
for ip in $(awk '{print $1}' $HOST_INFO)
do
    user=$(awk -v I="$ip" 'I==$1{print $2}' $HOST_INFO)
    pass=$(awk -v I="$ip" 'I==$1{print $3}' $HOST_INFO)
    expect login.exp $ip $user $pass $1
done
Linux主机SSH连接信息：

# cat user_info.txt
192.168.1.120 root 123456
```

### 创建10个用户，并分别设置密码，密码要求10位且包含大小写字母以及数字，最后需要把每个用户的密码存在指定文件中

```bash
#!/bin/bash
##############################################################
#创建10个用户，并分别设置密码，密码要求10位且包含大小写字母以及数字
#最后需要把每个用户的密码存在指定文件中
#前提条件：安装mkpasswd命令
##############################################################
#生成10个用户的序列（00-09）
for u in `seq -w 0 09`
do
 #创建用户
 useradd user_$u
 #生成密码
 p=`mkpasswd -s 0 -l 10`
 #从标准输入中读取密码进行修改（不安全）
 echo $p|passwd --stdin user_$u
 #常规修改密码
 echo -e "$p\n$p"|passwd user_$u
 #将创建的用户及对应的密码记录到日志文件中
 echo "user_$u $p" >> /tmp/userpassword
done
```

### 监控httpd的进程数，根据监控情况做相应处理

```bash
#!/bin/bash
###############################################################################################################################
#需求：
#1.每隔10s监控httpd的进程数，若进程数大于等于500，则自动重启Apache服务，并检测服务是否重启成功
#2.若未成功则需要再次启动，若重启5次依旧没有成功，则向管理员发送告警邮件，并退出检测
#3.如果启动成功，则等待1分钟后再次检测httpd进程数，若进程数正常，则恢复正常检测（10s一次），否则放弃重启并向管理员发送告警邮件，并退出检测
###############################################################################################################################
#计数器函数
check_service()
{
 j=0
 for i in `seq 1 5` 
 do
 #重启Apache的命令
 /usr/local/apache2/bin/apachectl restart 2> /var/log/httpderr.log
    #判断服务是否重启成功
 if [ $? -eq 0 ]
 then
 break
 else
 j=$[$j+1]
 fi
    #判断服务是否已尝试重启5次
 if [ $j -eq 5 ]
 then
 mail.py
 exit
 fi
 done 
}
while :
do
 n=`pgrep -l httpd|wc -l`
 #判断httpd服务进程数是否超过500
 if [ $n -gt 500 ]
 then
 /usr/local/apache2/bin/apachectl restart
 if [ $? -ne 0 ]
 then
 check_service
 else
 sleep 60
 n2=`pgrep -l httpd|wc -l`
 #判断重启后是否依旧超过500
             if [ $n2 -gt 500 ]
 then 
 mail.py
 exit
 fi
 fi
 fi
 #每隔10s检测一次
 sleep 10
done
```

### 批量修改服务器用户密码

```bash
Linux主机SSH连接信息：旧密码

# cat old_pass.txt 
192.168.18.217  root    123456     22
192.168.18.218  root    123456     22
内容格式：IP User Password Port

SSH远程修改密码脚本：新密码随机生成
https://www.linuxprobe.com/books
#!/bin/bash
OLD_INFO=old_pass.txt
NEW_INFO=new_pass.txt
for IP in $(awk '/^[^#]/{print $1}' $OLD_INFO); do
    USER=$(awk -v I=$IP 'I==$1{print $2}' $OLD_INFO)
    PASS=$(awk -v I=$IP 'I==$1{print $3}' $OLD_INFO)
    PORT=$(awk -v I=$IP 'I==$1{print $4}' $OLD_INFO)
    NEW_PASS=$(mkpasswd -l 8)  # 随机密码
    echo "$IP   $USER   $NEW_PASS   $PORT" >> $NEW_INFO
    expect -c "
    spawn ssh -p$PORT $USER@$IP
    set timeout 2
    expect {
        \"(yes/no)\" {send \"yes\r\";exp_continue}
        \"password:\" {send \"$PASS\r\";exp_continue}
        \"$USER@*\" {send \"echo \'$NEW_PASS\' |passwd --stdin $USER\r exit\r\";exp_continue}
    }"
done
生成新密码文件：

# cat new_pass.txt 
192.168.18.217  root    n8wX3mU%      22
192.168.18.218  root    c87;ZnnL      22
```

### iptables自动屏蔽访问网站频繁的IP

```bash
场景：恶意访问,安全防范

1）屏蔽每分钟访问超过200的IP

方法1：根据访问日志（Nginx为例）

#!/bin/bash
DATE=$(date +%d/%b/%Y:%H:%M)
ABNORMAL_IP=$(tail -n5000 access.log |grep $DATE |awk '{a[$1]++}END{for(i in a)if(a[i]>100)print i}')
#先tail防止文件过大，读取慢，数字可调整每分钟最大的访问量。awk不能直接过滤日志，因为包含特殊字符。
for IP in $ABNORMAL_IP; do
    if [ $(iptables -vnL |grep -c "$IP") -eq 0 ]; then
        iptables -I INPUT -s $IP -j DROP
    fi
done
方法2：通过TCP建立的连接

#!/bin/bash
ABNORMAL_IP=$(netstat -an |awk '$4~/:80$/ && $6~/ESTABLISHED/{gsub(/:[0-9]+/,"",$5);{a[$5]++}}END{for(i in a)if(a[i]>100)print i}')
#gsub是将第五列（客户端IP）的冒号和端口去掉
for IP in $ABNORMAL_IP; do
    if [ $(iptables -vnL |grep -c "$IP") -eq 0 ]; then
        iptables -I INPUT -s $IP -j DROP
    fi
done

2）屏蔽每分钟SSH尝试登录超过10次的IP

方法1：通过lastb获取登录状态:

#!/bin/bash
DATE=$(date +"%a %b %e %H:%M") #星期月天时分  %e单数字时显示7，而%d显示07
ABNORMAL_IP=$(lastb |grep "$DATE" |awk '{a[$3]++}END{for(i in a)if(a[i]>10)print i}')
for IP in $ABNORMAL_IP; do
    if [ $(iptables -vnL |grep -c "$IP") -eq 0 ]; then
        iptables -I INPUT -s $IP -j DROP
    fi
done
方法2：通过日志获取登录状态

#!/bin/bash
DATE=$(date +"%b %d %H")
ABNORMAL_IP="$(tail -n10000 /var/log/auth.log |grep "$DATE" |awk '/Failed/{a[$(NF-3)]++}END{for(i in a)if(a[i]>5)print i}')"
for IP in $ABNORMAL_IP; do
    if [ $(iptables -vnL |grep -c "$IP") -eq 0 ]; then
        iptables -A INPUT -s $IP -j DROP
        echo "$(date +"%F %T") - iptables -A INPUT -s $IP -j DROP" >>~/ssh-login-limit.log
    fi
done
```

### 根据web访问日志，封禁请求量异常的IP，如IP在半小时后恢复正常，则解除封禁

```bash
#!/bin/bash
####################################################################################
#根据web访问日志，封禁请求量异常的IP，如IP在半小时后恢复正常，则解除封禁
####################################################################################
logfile=/data/log/access.log
#显示一分钟前的小时和分钟
d1=`date -d "-1 minute" +%H%M`
d2=`date +%M`
ipt=/sbin/iptables
ips=/tmp/ips.txt
block()
{
 #将一分钟前的日志全部过滤出来并提取IP以及统计访问次数
 grep '$d1:' $logfile|awk '{print $1}'|sort -n|uniq -c|sort -n > $ips
 #利用for循环将次数超过100的IP依次遍历出来并予以封禁
 for i in `awk '$1>100 {print $2}' $ips`
 do
 $ipt -I INPUT -p tcp --dport 80 -s $i -j REJECT
 echo "`date +%F-%T` $i" >> /tmp/badip.log
 done
}
unblock()
{
 #将封禁后所产生的pkts数量小于10的IP依次遍历予以解封
 for a in `$ipt -nvL INPUT --line-numbers |grep '0.0.0.0/0'|awk '$2<10 {print $1}'|sort -nr`
 do 
 $ipt -D INPUT $a
 done
 $ipt -Z
}
#当时间在00分以及30分时执行解封函数
if [ $d2 -eq "00" ] || [ $d2 -eq "30" ]
 then
 #要先解再封，因为刚刚封禁时产生的pkts数量很少
 unblock
 block
 else
 block
fi
```

### 判断用户输入的是否为IP地址

```bash
方法1:

#!/bin/bash
function check_ip(){
    IP=$1
    VALID_CHECK=$(echo $IP|awk -F. '$1< =255&&$2<=255&&$3<=255&&$4<=255{print "yes"}')
    if echo $IP|grep -E "^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}$">/dev/null; then
        if [ $VALID_CHECK == "yes" ]; then
            echo "$IP available."
        else
            echo "$IP not available!"
        fi
    else
        echo "Format error!"
    fi
}
check_ip 192.168.1.1
check_ip 256.1.1.1
方法2：

#!/bin/bash
function check_ip(){
    IP=$1
    if [[ $IP =~ ^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}$ ]]; then
        FIELD1=$(echo $IP|cut -d. -f1)
        FIELD2=$(echo $IP|cut -d. -f2)
        FIELD3=$(echo $IP|cut -d. -f3)
        FIELD4=$(echo $IP|cut -d. -f4)
        if [ $FIELD1 -le 255 -a $FIELD2 -le 255 -a $FIELD3 -le 255 -a $FIELD4 -le 255 ]; then
            echo "$IP available."
        else
            echo "$IP not available!"
        fi
    else
        echo "Format error!"
    fi
}
check_ip 192.168.1.1
check_ip 256.1.1.1
增加版：

加个死循环，如果IP可用就退出，不可用提示继续输入，并使用awk判断。

#!/bin/bash
function check_ip(){
    local IP=$1
    VALID_CHECK=$(echo $IP|awk -F. '$1< =255&&$2<=255&&$3<=255&&$4<=255{print "yes"}')
    if echo $IP|grep -E "^[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}$" >/dev/null; then
        if [ $VALID_CHECK == "yes" ]; then
            return 0
        else
            echo "$IP not available!"
            return 1
        fi
    else
        echo "Format error! Please input again."
        return 1
    fi
}
while true; do
    read -p "Please enter IP: " IP
    check_ip $IP
    [ $? -eq 0 ] && break || continue
done
```

## 沙雕Shell

### 灭霸脚本
> https://github.com/hotvulcan/Thanos.sh

这个命令会随机“删掉”您一半的文件。。

请不要在家里或其他地方使用。这是真家伙，要小心…

#### 特别说明

1. 支持mac系统，但是需要使用到gshuf命令，需要通过brew安装,安装命令如下：
```bash
#安装brew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
#安装gshuf
brew install coreutils
```
2. 此脚本只会列出当前目录一半的文件。并且。。。总之小心点。。。

```bash

#!/bin/sh
let "i=`find . -type f | wc -l`/2";
if [[ uname=="Darwin" ]]; then
    find . -not -name "Thanos.sh" -type f -print0 | gshuf -z -n $i | xargs -0  -- cat;
else
    find . -not -name "Thanos.sh" -type f -print0 | shuf -z -n $i | xargs -0  -- cat;
fi
# Explanation
## Step 1: Get the count of files in current path divided by two.
## Step 2: Get all the files in current path and print in one line.
## Step 3: Turn half of the second step output into standard input randomly.
## Step 4: Show half of the files in terminal.

# Key Point
## If you want to make delete, what you need to do is turn 'cat' into 'rm'.
```

### git-fire

> https://github.com/qw3rtman/git-fire

这个 Shell 脚本的作者应该是消防员出身。

它的主要作用是，在火灾等突发状况来临时，你可以用该脚本一键切换到新分支，并提交代码，以避免在逃亡时的匆忙提交导致跟线上代码冲突。

用上这个脚本之后，最佳良心敬业奖非你莫属！

```bash
#!/usr/bin/env sh

# Setup.
VERSION="0.2.3"

version() {
	printf "git-fire version %s\n" "$VERSION"

	git --version
}

# Helpers.
current_branch() {
	basename "$(git symbolic-ref HEAD)"
}

current_epoch() {
	date +%s
}

user_email() {
	git config user.email
}

new_branch() {
	echo "fire-${1:-$(current_branch)}-$(user_email)-$(current_epoch)"
}

fire() {
	initial_branch="$(current_branch)"

	git checkout -b "$(new_branch)"

	# cd to git root directory
	cd "$(git rev-parse --show-toplevel)"

	git add -A

	if [ -z "$1" ]; then
		message="Fire! Branch $(current_branch)."
	else
		message="$*"
	fi

	git commit -m "$message" --no-verify

	for remote in $(git remote); do
		git push --no-verify --set-upstream "${remote}" "$(current_branch)" || true
	done

  if [ "$(git stash list)" != '' ]; then
	  for sha in $(git rev-list -g stash); do
		  git push --no-verify origin "$sha":refs/heads/"$(current_branch $initial_branch)"-stash-"$sha"
	  done
  fi

	printf "\n\nLeave building!\n"
}

display_help() {
	cat <<-EOF
  usage:
    git fire [options] [COMMAND] [args]
  commands:
    git fire                        Add, commit, and push to remote in case of a fire
    git fire <message>              Execute git fire with <message> for commit message
  options:
    -V, --version                   Output current version of git-fire
    -h, --help                      Display this help information
EOF
	exit 0
}


case $1 in
	-V|--version) version; exit 0 ;;
	-h|--help) display_help; exit 0 ;;
esac

fire "$@"
```

### thefuck

> https://github.com/nvbn/thefuck

从名字可以看出，项目作者应该是一位暴躁老哥。

该项目的主要作用是，在你输错命令后，fuck 一下，自动帮你更正命令，解气又实用。

当然输这个命令的时候要注意别让老板看到，不然等下还以为你工作干得不爽，把你开了那就真的是「What the fuck」了。

