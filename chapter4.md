# 更换国内源并安装docker

### 安装Docker
> 树莓派标准系统RASPBIAN是基于Debian的操作系统，所以我们根据docker关于Debian的安装步骤进行安装[Docker for Debian](https://store.docker.com/editions/community/docker-ce-server-debian?tab=description)

##### 1.添加docker官方源
```sh
# 终端输入
apt-get -y install \
  apt-transport-https \
  ca-certificates \
  curl \
  software-properties-common
# 继续终端输入
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