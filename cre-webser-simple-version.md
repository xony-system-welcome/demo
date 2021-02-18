## VMware Create Ubuntu
```
VMware Workstation 16 Pro
  Create a New Virtual Machine
  Welcome to the New Virtual Machine Wizard
    Typical (recommended)
    Next
  Guset Operating System Installation
    Installer disc image file (iso): Browse you Ubuntu Iso 'ubuntu-20.10-desktop-amd64'
    Next
  Name the Virtual Machine
    Virtual machine name: 'ubuntu.20.10'
    Next
  Specify Disk Capacity
    Maximun disk size(GB): '40'
    Next
  Ready to Create Virtual Machine
    Next
```





##  Install Docker in Ubuntu
### Install using the repository;使用存儲庫安裝
SET UP THE REPOSITORY;設置存儲庫

1.Update Docker；更新版本
```
$ sudo apt-get update
```
安裝必要的東西
```jsx
 $ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common 
```
    
2.Add Docker’s official GPG key；添加Docker官方GPG key
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
添加fingerprint
```
$ sudo apt-key fingerprint 0EBFCD88 

pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

3.加入Ubuntu Docker repository
```jsx
$ sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

### INSTALL DOCKER ENGINE;安裝DOCKER引擎
1.再一次更新清單
```
$ sudo apt-get update
```
執行安裝Docker
```
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

2.Install a specific version of Docker Engine;安裝特定版本的Docker Engine

a.顯示最近的數個 docker版本:
```
$ apt-cache madison docker-ce
 docker-ce | 5:20.10.3~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
 docker-ce | 5:20.10.2~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
 docker-ce | 5:20.10.1~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
 docker-ce | 5:20.10.0~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
```

b.選擇最新的 docker版本,并且安裝.
```
$ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```

3.安裝完成后，使用以下指令測試是否成功
```
$ sudo docker run hello-world
```

## Install Docker Compose
U can follow it setup, https://docs.docker.com/compose/install/

###Install Compose on Linux systems
1.Download 執行檔
```
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.28.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

2.賦予檔案執行權
```
$ sudo chmod +x /usr/local/bin/docker-compose
```

如果docker-compose執行失敗,可透過location 直接執行.
```
$ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

透過check version 檢查是否安裝成功
```
$ docker-compose --version
docker-compose version 1.28.2, build 1110ad01
```





## Install Python3
https://docs.python-guide.org/starting/install3/linux/

Check Python3 version
```
$ python3 --version
```

Install python\
Update Python3 version and install python
```
$ sudo apt-get update
$ sudo apt-get install python3.8
```

### Install Python3-pip
https://linuxize.com/post/how-to-install-pip-on-ubuntu-18.04/

Check python3 pip
```
$ pip3 --version
```

Install python3 pip
```
$ sudo apt install python3-pip
```

## Install Django
https://blog.csdn.net/B5DIV/article/details/103449204

1. Update system
```
$ sudo apt-get -y update
$ sudo apt-get upgrade
```

2. Install PIP (For have not install)
```
$ sudo apt-get install python3-pip
```

3. Install Virtual environment
```
$ Sudo apt-get install python3-venv
```

4. Cerate Virtual environment
Create 目錄
```
$ mkdir web
```

打開FILE
```
$ cd web
```

Create the venv file
```
$ python3 –m venv venv
```

Run activate 脚本 激活file
```
$ source venv/bin/activate
```

#####



## Install Visual Studio Code
Download\
Install python
###### Select Extension > Search Python > Install
