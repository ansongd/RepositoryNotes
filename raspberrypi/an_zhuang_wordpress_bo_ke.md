# 安装wordpress博客


默认的wordpress的存储目录并不是/var/www/下面的，而是/usr/share/wordpress下面的


安装apache

```sudo apt-get install apache2```

安装PHP5

```sudo apt-get install php5```

安装mq

```sudo apt-get install mysql-server```

查看数据库状态

```
mysql -u root -p
quit
```

设置mq配置

```
sudo /usr/bin/mysql_secure_installation
Enter current password for root (enter for none):
Change the root password? [Y/n] n
Remove anonymous users? [Y/n] y
Disallow root login remotely? [Y/n] y
Remove test database and access to it? [Y/n] y
Reload privilege tables now? [Y/n] y
Thanks for using MySQL!
```

安装数据库
```
mysql -u root -p
create database wordpress;
create user wpfred;
set password for wpfred = password("raindrop");
grant all PRIVILEGES on wordpress.* to wpfred@localhost identified by 'raindrop';
exit
```

安装WordPress

```sudo apt-get install wordpress```

配置wordpress

```
sudo ln -s /usr/share/wordpress /var/www/html/myblog
sudo cp /usr/share/wordpress/wp-config-sample.php /etc/wordpress/config-default.php
```

修改配置文件
```
sudo vi /etc/wordpress/config-default.php
// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'database_name_here');

/** MySQL database username */
define('DB_USER', 'username_here');

/** MySQL database password */
define('DB_PASSWORD', 'password_here');
```

重启后访问网址设置wordpress

让wordpress获取权限
```
sudo chown -R www-data /usr/share/wordpress/wp-content
sudo chown -R www-data /usr/share/wordpress/wp-content/plugins
sudo chown -R www-data /usr/share/wordpress/wp-content/themes
sudo chown -R www-data /usr/share/wordpress/wp-content/uploads


sudo chown -R www-data /var/lib/wordpress/wp-content
sudo chown -R www-data /var/lib/wordpress/wp-content/plugins
sudo chown -R www-data /var/lib/wordpress/wp-content/themes
sudo chown -R www-data /var/lib/wordpress/wp-content/uploads
```

编辑配置文件
```
sudo vi /usr/share/wordpress/wp-config.php

define("FS_METHOD", "direct");
define("FS_CHMOD_DIR", 0777);
define("FS_CHMOD_FILE", 0777);
```








开始安装wordpress
sudo apt-get install wordpress

创建一个html文件夹的快捷方式
sudo ln -s /usr/share/wordpress /var/www/html/myblog

复制配置文件
sudo cp /usr/share/wordpress/wp-config-sample.php /etc/wordpress/config-default.php

编辑配置文件
sudo vi /etc/wordpress/config-default.php
在一下段落
// ** MySQL settings - You can get this info from your web host ** //define('DB_NAME', 'wordpress');

define('DB_USER', 'username_here');

define('DB_PASSWORD', 'password_here');用你刚才设置的sql的用户名密码换上去就行了

完成上面的步骤之后，wordpress应该就已经安装完成了。只需访问你的ip，就可以打开wordpress页面了。

如果以后需要更新插件或主题，需要给一下两个文件读写权限
sudo chown -R www-data /var/www/html/myblog/wp-content/plugins (设置这个目录的所有者）
sudo chown -R www-data /var/www/html/myblog/wp-content/uploads

sudo chmod -R 775 /var/www/html/wordpress/wp-content/plugins (设置这个目录的权限）
sudo chmod -R 775 /var/www/html/myblog/wp-content/uploads

sudo chown -R www-data /usr/share/wordpress/wp-content
sudo chown -R www-data /usr/share/wordpress/wp-content/plugins
sudo chown -R www-data /usr/share/wordpress/wp-content/themes
sudo chown -R www-data /usr/share/wordpress/wp-content/uploads


sudo chown -R www-data /var/lib/wordpress/wp-content
sudo chown -R www-data /var/lib/wordpress/wp-content/plugins
sudo chown -R www-data /var/lib/wordpress/wp-content/themes
sudo chown -R www-data /var/lib/wordpress/wp-content/uploads

sudo chmod -R 775 /var/lib/wordpress/wp-content
sudo chmod -R 775 /var/lib/wordpress/wp-content/plugins
sudo chmod -R 775 /var/lib/wordpress/wp-content/themes
sudo chmod -R 775 /var/lib/wordpress/wp-content/uploads

/var/lib/wordpress
/usr/share/wordpress

sudo chmod -R 775 /var/www/html/myblog/wp-content/uploads
sudo vi /usr/share/wordpress/wp-admin/includes/class-wp-filesystem-direct.php



define(“FS_METHOD”, “direct”);
define(“FS_CHMOD_DIR”, 0777);
define(“FS_CHMOD_FILE”, 0777);

define(‘FTP_HOST’, ‘ftp主机’);
define(‘FTP_USER’, ‘FTP帐号’);
define(‘FTP_PASS’, ‘FTP密码’);

查看当前文件夹权限
ls -l
cd /usr/share/wordpress/wp-content
sudo chmod 777 * -R uploads/
sudo chmod 777 * -R plugins/
sudo chmod 777 * -R themes/
sudo chmod 777 * -R uploads/

参考资料：
http://vv15.pbhz.com/2011/08/wordpress-chmod/(权限参考)
http://unixetc.co.uk/2013/09/25/install-wordpress-blog-on-raspberry-pi/（安装参考）
http://bayesky.com/index.php/archives/12/
