# docker学习教程

## 一.Ubantu操作系统安装docker
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
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg|sudo apt-key add -

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

## 8.启动、关闭等指令
    $ sudo service docker start     //启动
    $ sudo service docker stop      //停止
    $ sudo service docker restart   //重启
    $ sudo service docker status    //状态
    
### 9.配置ustc加速源
### 9.1.切换到root角色
    $ su root
    $ 输入密码(虚拟机,可以使用sudo passwd root 更改root角色密码后再进行指令操作)
### 9.2.配置
    $ sudo cd /etc/docker
    $ vi daemon.json
        {
            "registry-mirrors":["https://docker.mirrors.ustc.edu.cn"]
        }

## 二.Docker使用
### 1.docker镜像基础指令
    $ sudo docker images        //查看当前拥有的所有docker镜像
    $ sudo docker search redis  //通过search,搜索redis相关镜像
    $ sudo docker pull redis    //通过pull,拉取指定redis镜像
    $ sudo docker rmi IMAGE ID  //通过images查看对应image id,移除对应image id镜像
    
### 2.docker容器基础使用
    1).查看docker容器
        $ sudo docker ps            //查看docker容器
        $ sudo docker ps -a         //查看docekr所有容器
    2).创建容器
        交互式容器(临时启动一个容器,可以测试容器)
        $ sudo docker run -it --name=容器名 镜像名 /bin/bash
        守护式容器
        $ sudo docker run -di --name=容器名 镜像名
    
