### Donwload Image
Centos 7.9-2207.iso
http://ftp.ksu.edu.tw/pub/CentOS/7.9.2009/isos/x86_64/CentOS-7-x86_64-DVD-2009.iso

Wazhu 4.3.ova
https://packages.wazuh.com/4.x/vm/wazuh-4.3.9.ova


Set Done
[root@localhost .ssh]# git config --global user.email "hwt384856713@gmail.com"
[root@localhost .ssh]# git config --global user.email "demo"

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

安裝 Docker Engine-Community
安裝最新版本的 Docker Engine-Community 和 containerd，或者轉到下一步安裝特定版本：
```
sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

要安裝特定版本的 Docker Engine-Community，請在存儲庫中列出可用版本，然後選擇並安裝：

1、列出並排序您存儲庫中可用的版本。此示例按版本號（從高到低）對結果進行排序。
```
yum list docker-ce --showduplicates | sort -r
```

2、通過其完整的軟件包名稱安裝特定版本，該軟件包名稱是軟件包名稱（docker-ce）加上版本字符串（第二列），從第一個冒號（:）一直到第一個連字符，並用連字符（-）分隔。例如：docker-ce-18.09.1。
```
# sudo yum install docker-ce-<VERSION_STRING> docker-ce-cli-<VERSION_STRING> containerd.io
```

啟動 Docker。
```
# sudo systemctl start docker
```

通過運行 hello-world 鏡像來驗證是否正確安裝了 Docker Engine-Community 。
```
# sudo docker run hello-world
```


----------------------------------------------
----------------------------------------------
