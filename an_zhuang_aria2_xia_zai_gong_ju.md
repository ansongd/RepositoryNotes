# 安装aria2下载工具

安装aria2
```sudo apt-get install aria2```

进入pi用户目录

```cd /home/pi```


新建aria2隐藏文件

```mkdir .aria2;```

新建配置文件

```nano .aria2/aria2.config```
```touch .aria2/aria2.session```

配置文件
```
dir=/home/pi/Download
disable-ipv6=true
enable-rpc=true
rpc-allow-origin-all=true
rpc-listen-all=true
rpc-listen-port=6800
continue=true
input-file=/home/pi/.aria2/aria2.session
save-session=/home/pi/.aria2/aria2.session
max-concurrent-downloads=3
```
增加开机启动

```sudo nano /etc/init.d/aria2```

输入配置内容

```
#! /bin/sh
# /etc/init.d/aria2
### BEGIN INIT INFO
# Provides:          aria2
# Required-Start:    $local_fs
# Required-Stop:     $local_fs
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: aria2
### END INIT INFO

CONF_PATH=/home/pi/.aria2/aria2.config

case "$1" in
    start)
        echo "Starting aria2 with custom configuration"
        aria2c --conf-path=$CONF_PATH
        ;;
    stop)
        echo "Stopping aria2"
        killall aria2c
        ;;
    *)
        echo "Usage: /etc/init.d/aria2 {start|stop}"
        exit 1
        ;;
esac

exit 0
```

分配配置文件权限

```sudo chmod 0755 /etc/init.d/aria2```

设置开机启动

```sudo update-rc.d aria2 defaults```

关闭开机启动

```sudo update-rc.d -f aria2 remove```




sudo service aria2 start
sudo aria2c --conf-path=/home/pi/.aria2/aria2.config
sudo mount -t cifs -o username=admin,password=password //192.168.1.1/NAS /home/pi/Download

http://192.168.1.9:6800/jsonrpc


参考资料一：官方说明
http://aria2c.com/usage.html

https://jlnostr.de/en/blog/aria2-raspberrypi
参考资料二
http://shumeipai.nxez.com/2014/07/01/raspberry-pi-do-download-machine-aria2.html 

