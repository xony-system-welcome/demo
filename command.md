## Install Docker in Ubuntu
```
sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common 

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88 

sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
    
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io

apt-cache madison docker-ce

sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io

sudo docker run hello-world
```

## Install Docker Compose
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.28.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose --version
```

## Install Python3
```
python3 --version

sudo apt-get update
sudo apt-get install python3.8
```

### Install Python3-pip
```
pip3 --version

sudo apt install python3-pip
```

### Install Python3-virtualenv
```
sudo apt install python3-virtualenv
```

### Install Python3-vim
```
sudo apt install python3-vim
```
