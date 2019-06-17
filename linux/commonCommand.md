# 实用类
## 清屏 clear

# 配置Java jdk

```
vi  ~/.bashrc 或者 vi /etc/profile

# java settings

export JAVA_HOME=/home/java/jdk1.8.0_211

export JRE_HOME=${JAVA_HOME}/jre

export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib

export PATH=${JAVA_HOME}/bin:$PATH


source ~/.bash_profile 或者/etc/profile

```

## java 后台运行jar

```
nohup java -jar -Denv=prd -Dspring.profiles.active=prd UserA.jar > a.txt &

```
其中：
 1. nohup 意思是不挂断运行命令,当账户退出或终端关闭时,程序仍然运行
2. &代表在后台运行。
3. --spring.profiles.active=dev 指定使用dev环境

# 结束job
通过jobs命令查看job号（假设为num），然后执行kill %num

# 关闭终端之后，使用PS 命令查看

```
ps aux|grep shareniu.jar

```
 a:显示所有程序 
 u:以用户为主的格式来显示 
 x:显示所有程序，不以终端机来区分

# 开启端口
1、LINUX下通过命令开启允许对外访问的网络端

```
 /sbin/iptables -I INPUT -m state --state NEW -p tcp --dport 8888 -j ACCEPT 
/etc/rc.d/init.d/iptables save 
/etc/rc.d/init.d/iptables restart
替代方案 service iptables restart

```
命令详解[：地址](http://linux.vbird.org/linux_server/0250simple_firewall.php#netfilter_syntax)
开启外挂模块


```
[root@www ~]# iptables -A INPUT [-m state] [--state状态] 
选项与参数：
-m ：一些iptables 的外挂模块，主要常见的有：
     state ：状态模块
     mac ：网络卡硬件地址(hardware address)
--state ：一些封包的状态，主要有：
     INVALID ：无效的封包，例如数据破损的封包状态
     ESTABLISHED：已经联机成功的联机状态；
     NEW ：想要新建立联机的封包状态；
     RELATED ：这个最常用！表示这个封包是与我们主机发送出去的封包有关

范例：只要已建立或相关封包就予以通过，只要是不合法封包就丢弃 
[root@www ~]# iptables -A INPUT -m state \ 
> --state RELATED,ESTABLISHED -j ACCEPT 
[root@www ~] # iptables -A INPUT -m state --state INVALID -j DROP
```



2、查看端口是否开放 

```
 /etc/init.d/iptables status  （发现在cent-os 6.3 不能用）
 
 sudo iptables --list (6.3以后)

```

centos 7使用的语句
```
firewall-cmd --zone=public --add-port=65535/tcp --permanent（添加端口允许）
firewall-cmd --reload  重新加载
firewall-cmd --list-port 列出开放的端口
```


3 显示配置的规则

```
iptables-save
```
# netstat 常用参数

```
Netstat -ano
```

4 杀掉进程

```
kill -9 进程号

```

5 切换目录

“/”代表根目录、“..”代表上一级目录、“~”代表HOME目录、“-”代表前一目录。

## SonarQube
