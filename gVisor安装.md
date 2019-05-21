# gVisor安装

本文采用的是**gVisor**在[**Github**的安装教程](<https://github.com/google/gvisor>)来安装的。

主要的安装步骤如下

#### download gVisor工程

```shell
git clone https://gvisor.googlesource.com/gvisor gvisor
cd gvisor
```

#### 安装编译需要的工具 bazel

具体参照[Bazel官方文档](<https://docs.bazel.build/versions/master/install-ubuntu.html>)

#### build gVisor工程

```shell
bazel build runsc
sudo cp ./bazel-bin/runsc/linux_amd64_pure_stripped/runsc /usr/local/bin
```

#### 关于Docker的设置

参照[Configuring Docker](<https://gvisor.dev/docs/user_guide/docker/>)

将runsc的目录添加到Docker的配置文件当中

#### gVisor的相关学习资料

目前国内关于gVisor的学习资料相对匮乏，所以主要的请参照[gVisor官网文档](<https://gvisor.dev/docs/>)和[gVisor源码](<https://github.com/google/gvisor>)。

