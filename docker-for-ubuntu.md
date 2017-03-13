由于版本更新频繁，最新安装方法请参考[https://www.docker.com/docker-ubuntu](https://www.docker.com/docker-ubuntu)

**1. Set up the repository**

Set up the Docker CE repository on Ubuntu. Thelsb\_release -cssub-command prints the name of your Ubuntu version, likexenialortrusty.

sudo apt-get -y install \

apt-transport-https \

ca-certificates \

curl

curl -fsSL [https://download.docker.com/linux/ubuntu/gpg](https://download.docker.com/linux/ubuntu/gpg) \| sudo apt-key add -

sudo add-apt-repository \

"deb \[arch=amd64\] [https://download.docker.com/linux/ubuntu](https://download.docker.com/linux/ubuntu) \

$\(lsb\_release -cs\) \

stable"

sudo apt-get update

**2. Get Docker CE**

Install the latest version of Docker CE on Ubuntu:

sudo apt-get -y install docker-ce

**3. Test your Docker CE installation**

Test your installation:

sudo docker run hello-world

**Next steps**

These installation instructions work for standard installations of Docker CE. For more details or alternative installation procedures, including how to installedgebuilds, see [Get Docker for Ubuntu](https://docs.docker.com/engine/installation/linux/ubuntu/).

* [Optional post-installation steps](https://docs.docker.com/engine/installation/linux/linux-postinstall/)
* [Docker User Guide](https://docs.docker.com/engine/userguide/)



