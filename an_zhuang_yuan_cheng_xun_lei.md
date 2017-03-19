# 安装远程迅雷

下载安装文件：Xware1.0.31_armel_v5te_glibc.zip
解压并放到树莓派任意目录
进入文件目录获取管理员权限：sudo chmod 777 * -R
运行迅雷配置文件：sudo ./portal
的到远程绑定码：THE ACTIVE CODE IS: xxxx
到迅雷网页客户端进行相关设定
设定后出现无下载空间，到TDDOWNLOAD目录，给予管理员权限：sudo chmod 777 * -R

sudo chmod -R 777 /home/pi/Desktop/xunlei
sudo chmod -R 777 /mnt/xunlei

sudo mount --bind /home/pi/Desktop/xunlei /mnt/xunlei
sudo chmod 777 * -R

参考链接
http://www.chinagtd.com/archives/xunleipi.html