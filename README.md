# docker
docker学习教程

## 安装Ubantu操作系统
### 1.安装Docker的AUFS存储驱动程序
    $ sudo apt-get install \
    linux-image-extra-$(uname -r) \
    linux-image-extra-virtual
    
### 2.安装docker包
    $ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
    
### 3.添加docker的官方GPG密钥
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg|sudo apt-key add-

### 4.设置stable稳定的仓库(stable稳定版每季度发不一次,Edge版每个月一次)
    $ sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"

### 5.更新apt包
    $ sudo apt-get update

### 6.安装DockerCE
    $ sudo apt-get install docker-ce

### 7.测试docker是否安装成功
    $ docker -v
