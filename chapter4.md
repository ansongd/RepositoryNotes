# 安装docker

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



