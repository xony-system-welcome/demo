* VMware Create Ubuntu
* Install Docker in Ubuntu
  * Install using the repository;使用存儲庫安裝
  * INSTALL DOCKER ENGINE;安裝DOCKER引擎
* Install Docker Compose
* Install Python3
  * Install Python3-pip
* Install Django
* Install Visual Studio Code




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
https://docs.docker.com/engine/install/ubuntu/
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

### Install Python3-virtualenv
```
$ sudo apt install python3-virtualenv
```


sudo apt install python3-virtualenv

## Before you start setting up uWSGI
https://uwsgi-docs.readthedocs.io/en/latest/tutorials/Django_and_nginx.html
### virtualenv
Make sure you are in a virtualenv for the software we need to install (we will describe how to install a system-wide uwsgi later):
```
virtualenv uwsgi-tutorial
cd uwsgi-tutorial
source bin/activate
```

### Django
Install Django into your virtualenv, create a new project, and cd into the project:
```
pip install Django
django-admin.py startproject mysite
cd mysite
```

## Basic uWSGI installation and configuration
### Basic test
Create a file called test.py:
```
# test.py
def application(env, start_response):
    start_response('200 OK', [('Content-Type','text/html')])
    return [b"Hello World"] # python3
    #return ["Hello World"] # python2
```
Run uWSGI:
```
uwsgi --http :8000 --wsgi-file test.py
```
The options mean:

http :8000: use protocol http, port 8000
wsgi-file test.py: load the specified file, test.py
This should serve a ‘hello world’ message directly to the browser on port 8000. Visit:
```
http://example.com:8000

```

### Test your Django project
Now we want uWSGI to do the same thing, but to run a Django site instead of the test.py module.

If you haven’t already done so, make sure that your mysite project actually works:
```
python manage.py runserver 0.0.0.0:8000
```
And if that works, run it using uWSGI:
```
uwsgi --http :8000 --module mysite.wsgi
```

module mysite.wsgi: load the specified wsgi module

## Basic nginx
### Install nginx
```
sudo apt-get install nginx
sudo /etc/init.d/nginx start    # start nginx
```
And now check that nginx is serving by visiting it in a web browser on port 80 - you should get a message from nginx: “Welcome to nginx!”. That means these components of the full stack are working together:








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
$ sudo apt-get install python3-venv
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
$ python3 -m venv venv
```

Run activate 脚本 激活file
```
$ source venv/bin/activate
```

Install Django
```
$ pip install django
```

## Configure PostgreSQL With Django Application On Ubuntu
https://www.unixmen.com/configure-postgresql-django-application-ubuntu/

https://www.howtoforge.com/tutorial/how-to-install-django-with-postgresql-and-nginx-on-ubuntu-16-04/
### Install PostgreSQL
Update system software
```
$ sudo apt-get update
```
Install PostgreSQL
```
$ sudo apt-get install python3-pip python3-dev libpq-dev postgresql postgresql-contrib
```

訪問Postgres
```
$ sudo su - postgres
```

Open the PostgreSQL shell will psql command
```
psql
```

Create a new database:`project_db`
```
CREATE DATABASE project_db;
```

Create a user:`project_db_user` and password:`dbpassword`
```
CREATE USER project_db_user WITH PASSWORD 'dbpassword';
```

Set Unicode to `UTF8` and Time to `UTC`
```
ALTER ROLE project_db_user SET client_encoding TO 'utf8';
ALTER ROLE project_db_user SET timezone TO 'UTC';
```

Set database user access rights to 'project_db_user'
```
GRANT ALL PRIVILEGES ON DATABASE project_db TO project_db_user;
```

Exit SQL prompt
```
\q
```

Exit SQL shell
```
exit
```


~### Install Diango virtualenv~
```
~sudo pip install virtualenv~
```

~Create `project_db`~
```
~mkdir ~/project_db~
```

~Go to `project_db`~
```
~cd ~/project_db~
```

~Copy python and pip to `pjdataenv`~
```
~virtualenv pjdataenv~
```

~激活虛擬環境~
```
~source pjdataenv/bin/activate~
```

它將使我們能夠使用配置的數據庫
```
pip install django psycopg2
```

使用“project_db”創建的目錄，我們可以使用以下命令啟動Django項目：
```
django-admin.py startproject project_db .
```


###Configuration of Django database settings
Install vim for edit file
```
sudo apt install vim
```

現在，我們將配置項目以使用創建的數據庫。我們將使用以下命令打開主Django項目設置文件
```
nano ~/project_db/settings.py
```

Change last “DATABASES” part，it part setting is SQLite for database.
```
. . .
DATABASES = {
   'default': {
       'ENGINE': 'django.db.backends.sqlite3',
       'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
   }
}
. . .
```

Change the last “DATABASES” part to it setting.
```
. . .
DATABASES = {
   'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'project_db',
        'USER': 'project_db_user',
        'PASSWORD': 'dbpassword',
        'HOST': 'localhost',
        'PORT': '',
   }
}
. . .
```

Test our project:

現在，我們將使用以下命令，從將數據結構遷移到數據庫中開始測試Django項目：
```
cd ~/project_db
```

```
python manage.py makemigrations
```

```
python manage.py migrate
```

然後，鍵入以下命令以創建管理帳戶，同時要求您選擇用戶名，電子郵件地址和密碼：
```
python manage.py createsuperuser
```
現在，我們將使用以下命令啟動Django項目：
```
python manage.py runserver 0.0.0.0:8000
```
然後訪問服務器的域名或IP地址，後跟：8000，以找到默認的Django根目錄頁。（您可以使用任何Web瀏覽器執行此操作）。
```
http://server_domain_or_IP:8000
```






## Install Visual Studio Code
Download\
Install python
###### Select Extension > Search Python > Install
```
```
