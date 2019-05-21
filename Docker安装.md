# Docker安装

#### Docker的安装主要参照Docker官网的教程

* [Ubuntu](<https://docs.docker.com/install/linux/docker-ce/ubuntu/>)
* [CentOS](<https://docs.docker.com/install/linux/docker-ce/centos/>)
* [MacOS](<https://docs.docker.com/docker-for-mac/install/>)
* [Windows](<https://docs.docker.com/docker-for-windows/>)

注意可能在安装的过程当中需要翻墙



#### 在安装完成之后，运行

```shell
$ sudo docker run hello-world
```



#### 安装的过程当中需要注意的点

##### 1. 用户权限

通过运行以下语句，可以将当前的用户添加进可以运行**docker**的用户当中。

```shell
$ sudo usermod -aG docker $USER
```

##### 2. 国内镜像设置

参照[docker构建国内镜像服务](<https://blog.csdn.net/xxb249/article/details/79469534>)

笔者采用的是阿里云。如果翻墙速度较快的话，用**docker**官方的仓库也行。

##### 3. 代理服务器设置

如果是翻墙的情况下，可能在**docker**的配置当中需要设置代理服务器，根据你目前的代理设置进行操作。

```shell
$ sudo -i
# mkdir -p /etc/systemd/system/docker.service.d
# cat > /etc/systemd/system/docker.service.d/http-proxy.conf <<EOF
> [Service]
> Environment="HTTP_PROXY=http://proxy.example.com:80/" "HTTPS_PROXY=https://proxy.example.com:443/"
> EOF
# systemctl daemon-reload
# systemctl restart docker
```



#### Docker的一些学习资料

* [Docker——从入门到实践](<https://yeasy.gitbooks.io/docker_practice/>)
* [Docker教程](<https://www.w3cschool.cn/docker/>)
* [Learn Docker & Containers using Interactive Browser-Based Scenarios](<https://www.katacoda.com/courses/docker>)

