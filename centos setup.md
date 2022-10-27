Centos Login
root
LoginP@ssw0rd

----------------------------------------------
安装sysv-rc-conf
```
sudo apt-get install sysv-rc-conf
```

Run:
```
sudo sysv-rc-conf
```

----------------------------------------------
Install the ifconfig Command
```
sudo yum update
sudo yum install net-tools -y
```

臨時允許被ping
```
#echo 0 >/proc/sys/net/ipv4/icmp_echo_ignore_all
```

永久允許被ping
```
vi /etc/sysctl.conf

net.ipv4.icmp_echo_ignore_all=0 (0=Enable 1=Disbale)
```
----------------------------------------------
Install Open ssh server software package
```
#sudo yum -y install openssh-server openssh-clients
```

Start SSH Service
```
#sudo systemctl start sshd
```

Check sshd Status
```
#sudo systemctl status sshd
```
----------------------------------------------
Centos 7.9-2207.iso
http://ftp.ksu.edu.tw/pub/CentOS/7.9.2009/isos/x86_64/CentOS-7-x86_64-DVD-2009.iso

Wazhu 4.3.ova
https://packages.wazuh.com/4.x/vm/wazuh-4.3.9.ova

----------------------------------------------
CentOS Docker 安装
使用官方安装脚本自动安装
```
#curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```
----------------------------------------------
----------------------------------------------
