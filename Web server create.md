### Check Ubuntu tool version
docker --version\
docker-compose --version\
python3 --version

用 Docker 實戰 Django 以及 Postgre - PART 1\
https://www.youtube.com/watch?v=Wg5m0-Jyox8&feature=youtu.be

### Tools
Ubuntu 20.10 https://ubuntu.com/download/desktop/thank-you/?version=20.10&architecture=amd64

### VMware Create Ubuntu
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

### Ubuntu(Linux), 安裝Docker
Follow docker官網 https://docs.docker.com/engine/install/ubuntu/

#### Install using the repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.
##### SET UP THE REPOSITORY

更新版本\
1.Update the apt package index and install packages to allow apt to use a repository over HTTPS:\
Update Docker\
```
$ sudo apt-get update
```
安裝必要的東西\
```
 $ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common 
```
    
添加Docker官方GPG key\
2.Add Docker’s official GPG key:\
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.\

添加fingerprint\
```
$ sudo apt-key fingerprint 0EBFCD88 

pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

3.Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below. Learn about nightly and test channels.\

Note: The lsb_release -cs sub-command below returns the name of your Ubuntu distribution, such as xenial. Sometimes, in a distribution like Linux Mint, you might need to change $(lsb_release -cs) to your parent Ubuntu distribution. For example, if you are using Linux Mint Tessa, you could use bionic. Docker does not offer any guarantees on untested and unsupported Ubuntu distributions.\

加入Ubuntu Docker repository\
```
$ sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

Install Docker Engine\
再一次更新清單\
1.Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:\
```
$ sudo apt-get update
```
執行安裝Docker\
```
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

2.To install a specific version of Docker Engine, list the available versions in the repo, then select and install:\
顯示最近的數個 docker版本\
a. List the versions available in your repo:\
```
$ apt-cache madison docker-ce
 docker-ce | 5:20.10.3~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
 docker-ce | 5:20.10.2~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
 docker-ce | 5:20.10.1~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
 docker-ce | 5:20.10.0~3-0~ubuntu-groovy | https://download.docker.com/linux/ubuntu groovy/stable amd64 Packages
```
選擇最新的 docker版本,并且安裝.\
b. Install a specific version using the version string from the second column, for example, 5:20.10.3~3-0~ubuntu-groovy.\ 
E.G $sudo apt-get install docker-ce=5:18.09.1~3-0~ubuntu-xenial docker-ce-cli=5:18.09.1~3-0~ubuntu-xenial containerd.io\
```
$ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```
安裝完成后，使用以下指令測試是否成功\
3. Verify that Docker Engine is installed correctly by running the hello-world image.\
```
$ sudo docker run hello-world
```

### Docker
### Docker-compose
### Python3
