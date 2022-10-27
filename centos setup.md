### DOnwload Image
Centos 7.9-2207.iso
http://ftp.ksu.edu.tw/pub/CentOS/7.9.2009/isos/x86_64/CentOS-7-x86_64-DVD-2009.iso

Wazhu 4.3.ova
https://packages.wazuh.com/4.x/vm/wazuh-4.3.9.ova

----------------------------------------------
Centos Login
root
LoginP@ssw0rd

----------------------------------------------
### 安装sysv-rc-conf
```
sudo apt-get install sysv-rc-conf
```

Run:
```
sudo sysv-rc-conf
```

----------------------------------------------
### Install the ifconfig Command
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
### Install Open ssh server software package
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
## CentOS Docker 安装
使用官方安装脚本自动安装
```
#curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```

###安装 Docker Engine-Community
###使用 Docker 倉庫進度設置
在新主機上首次安裝 Docker Engine-Community 之前，需要設置 Docker 倉庫。之後，您可以從倉庫安裝和更新 Docker。

設置倉庫
安裝所需的軟件包。 yum-utils 提供了 yum-config-manager ，並且 device mapper 存儲驅動程序需要 device-mapper-persistent-data 和 lvm2。
```
sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```

使用以下命令來設置穩定的倉庫。
```
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```


----------------------------------------------
----------------------------------------------
