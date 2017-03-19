# 登录树莓派

> Raspbian默认系统状态下关闭了ssh登录，把SD卡插入电脑，在boot目录下新建一个空的ssh文件夹即可开启ssh登录。

### SSH进入树莓派
MAC用户进入树莓派
```sh
# 登录初始账户 pi
ssh pi@192.168.1.X  
# 输入默认密码
raspberry
# 从装系统后可能出现验证问题
# 如果出现错误提示：
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!  
# 可输入清除错误
ssh-keygen -R ip地址
```
> win用户可通过putty客户端，根据提示填写ip地址及22端口进行登录设置

### 账户安全设置
账户初始化设置
```sh
# 系统设置可输入  
sudo raspi-config
# 更改账户密码,选择Change User Password Change password for the default user (pi)
# 启用root用户
sudo passwd --unlock root
# 设置root用户密码
sudo passwd root
# 切换到root
su root
# 第二种切换方式
su -
# 开启root远程密码登录
/etc/ssh/sshd\_config
修改 PermitRootLogin without-password 为 PermitRootLogin yes
# 重启树莓派
reboot
```

### mac无密码登录
##### 生成并上传key到树莓派
```sh
# 准备ssh-copy-id
brew install ssh-copy-id
# 生成私钥公钥
ssh-keygen -t rsa -b 1024
# 将公钥上传致服务器(~/.ssh/authorized_keys)
ssh-copy-id -i 公钥 root@192.168.1.xxx
```
##### key远程登录
```sh
# 复制key到本地key目录~/.ssh
# 修改~/.ssh/config文件快速登录
# 新建config
touch ~/.ssh/config
# 修改config
vi ~/.ssh/config
# 终端命令登录
Host server xxx
  HostName 192.168.1.xxx
  User root
  IdentityFile ~/.ssh/私钥
```