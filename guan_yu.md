# 安装vncl远程桌面

在ssh输入
更新软件源列表：sudo apt-get update
安装vncl：sudo apt-get install tightvncserver
之后提示是否继续安装，选y继续

等安装完成后输入启动代码：tightvncserver
之后会提示设定登录密码，输入二次确认后写1
就可以通过“ip:1”或“ip:5901”输入密码后登录远程图形界面

