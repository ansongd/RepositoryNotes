# 更换国内源并安装docker

### 更换国内源
```sh
# 进入目录
cd /etc/apt
# 备份文件
cp sources.list sources.list_back
# 修改配置
vi sources.list
# 更新 中山大学Raspbian 源地址
# 【wheezy版本】修改为：deb http://mirror.sysu.edu.cn/raspbian/raspbian/ wheezy main contrib non-free rpi
# 【jessie版本】修改为：deb http://mirror.sysu.edu.cn/raspbian/raspbian/ jessie main contrib non-free rpi
sudo apt-get update
# 更新软件
sudo apt-get upgrade
```

### 其它树莓派镜像源地址列表
> 可替换上文的链接地址，记住一定要把deb也修改进去
中山大学Raspbian 
* http://mirror.sysu.edu.cn/raspbian/raspbian/

中国科学技术大学Raspbian 
* http://mirrors.ustc.edu.cn/raspbian/raspbian/

阿里云Raspbian
*  http://mirrors.aliyun.com/raspbian/raspbian/

清华大学Raspbian 
* http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/

华中科技大学Raspbian 
* http://mirrors.hustunique.com/raspbian/raspbian/

华中科技大学Arch Linux ARM 
* http://mirrors.hustunique.com/archlinuxarm/

大连东软信息学院源（北方用户）Raspbian 
* http://mirrors.neusoft.edu.cn/raspbian/raspbian/

重庆大学源（中西部用户）Raspbian 
* http://mirrors.cqu.edu.cn/Raspbian/raspbian/

新加坡国立大学Raspbian 
* http://mirror.nus.edu.sg/raspbian/raspbian

牛津大学Raspbian 
* http://mirror.ox.ac.uk/sites/archive.raspbian.org/archive/raspbian/

韩国KAIST大学Raspbian 
* http://ftp.kaist.ac.kr/raspbian/raspbian/