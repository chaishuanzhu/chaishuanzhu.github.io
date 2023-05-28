---
title: Docker远程部署
tags: [Docker]
category: []
date: 2023-05-28 11:51:11
---

Mac上使用Docker最简单的办法是安装Docker Desktop。

### macOS Docker客户端安装。

```
# Install Docker CLI
brew install docker
brew install docker-compose
```

### Ubuntu Docker开启2375端口，支持远程访问

* 编辑`docker.service`文件
```
vim /lib/systemd/system/docker.service
```
* ExecStart属性添加参数`-H tcp://0.0.0.0:2375`
```
ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock -H tcp://0.0.0.0:2375
```
* 重启
```
systemctl daemon-reload
systemctl restart docker
```
* 测试是否开启成功
```
curl http://localhost:2375/version

{"Platform":{"Name":"Docker Engine - Community"},"Components":[{"Name":"Engine","Version":"20.10.11","Details":{"ApiVersion":"1.41","Arch":"amd64","BuildTime":"2021-11-18T00:35:16.000000000+00:00","Experimental":"false","GitCommit":"847da18","GoVersion":"go1.16.9","KernelVersion":"4.15.0-197-generic","MinAPIVersion":"1.12","Os":"linux"}},{"Name":"containerd","Version":"1.4.12","Details":{"GitCommit":"7b11cfaabd73bb80907dd23182b9347b4245eb5d"}},{"Name":"runc","Version":"1.0.2","Details":{"GitCommit":"v1.0.2-0-g52b36a2"}},{"Name":"docker-init","Version":"0.19.0","Details":{"GitCommit":"de40ad0"}}],"Version":"20.10.11","ApiVersion":"1.41","MinAPIVersion":"1.12","GitCommit":"847da18","GoVersion":"go1.16.9","Os":"linux","Arch":"amd64","KernelVersion":"4.15.0-197-generic","BuildTime":"2021-11-18T00:35:16.000000000+00:00"}
```

### macOS 配置Docker Host

* 编辑`~/.zshrc`文件
```
# NUC Docker
export DOCKER_HOST=tcp://192.168.2.104:2375
```
* 使修改生效
```
source ~/.zshrc
```
* 测试服务是否可用
```
docker run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
719385e32844: Pull complete 
Digest: sha256:fc6cf906cbfa013e80938cdf0bb199fbdbb86d6e3e013783e5a766f50f5dbce0
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

### 在本机启动Ubuntu Docker（可选）
* 安装multipass虚拟机管理软件
```
brew install --cask multipass
```
* 创建Ubuntu虚拟机
```
multipass launch 20.04 --name my-docker -d 50G -m 2G
```
* 在虚拟机中安装Docker
```
multipass shell my-docker
> curl -fsSL https://get.docker.com | sh
```
* 编辑`docker.service`配置
```
sudo vim /lib/systemd/system/docker.service
```
* 修改`ExecStart`添加`-H tcp://0.0.0.0`
```
ExecStart=/usr/bin/dockerd -H fd:// -H tcp://0.0.0.0 --containerd=/run/containerd/containerd.sock
```
* 重启
```
> sudo systemctl daemon-reload
> sudo systemctl restart docker.service
```
* 按`Ctrl+D`退出虚拟机

### 参考

[docker-mac-without-docker-desktop](https://nemzes.net/posts/docker-mac-without-docker-desktop/)
