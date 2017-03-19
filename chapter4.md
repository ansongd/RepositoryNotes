# 更换国内源并安装docker

### 安装Docker
> 树莓派标准系统RASPBIAN是基于Debian的操作系统，所以我们根据docker关于Debian的安装步骤进行安装[Docker for Debian](https://store.docker.com/editions/community/docker-ce-server-debian?tab=description)

##### 1.添加docker官方源
```sh
# 安装依赖环境
apt-get -y install \
  apt-transport-https \
  ca-certificates \
  curl \
  software-properties-common
# 环境配置脚本
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
# 添加官方源
add-apt-repository \
         "deb [arch=amd64] https://download.docker.com/linux/debian \
         $(lsb_release -cs) \
         stable"
# 更新源
apt-get update
```

##### 2.安装docker
```sh
# 自动安装docker
apt-get -y install docker-ce
# 开启终端服务
sudo systemctl start docker
# or
sudo service docker start
```
##### 3.测试是否安装成功
```sh
docker run hello-world
```
> 如果正确提示欢迎信息表示安装成功


### 选择docker.com官方安装脚本
```sh
# 安装脚本命令
 curl -sSL get.docker.com | sh
# 查看docker安装信息
docker info
```

### 选择daocloud.io镜像安装
可选择国内团队的一键安装脚本,[安装说明文档](https://dashboard.daocloud.io/nodes/new?cluster_token=cc22bcb4de33c8a2839d63b668119cfd623822f3&cluster_id=52789c91-d108-4036-87a4-35ee21e50aef)
```sh
# 安装脚本命令
curl -sSL https://get.daocloud.io/docker | sh
# 查看docker安装信息
docker info
```
> 如果显示 Cannot connect to the Docker daemon 表示没有能够成功运行。一般可以通过 service docker start 启动