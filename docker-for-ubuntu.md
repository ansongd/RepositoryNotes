由于版本更新频繁，最新安装方法请参考[https://www.docker.com/docker-ubuntu](https://www.docker.com/docker-ubuntu)



  
p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 15.2px Helvetica; color: \#445d6e; -webkit-text-stroke: \#445d6e}  
p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Helvetica; color: \#445d6e; -webkit-text-stroke: \#445d6e}  
p.p3 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Monaco; color: \#445d6e; -webkit-text-stroke: \#445d6e; background-color: \#000000; background-color: rgba\(0, 0, 0, 0.039\)}  
p.p4 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Monaco; color: \#445d6e; -webkit-text-stroke: \#445d6e; background-color: \#000000; background-color: rgba\(0, 0, 0, 0.039\); min-height: 17.0px}  
li.li2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 13.0px Helvetica; color: \#445d6e; -webkit-text-stroke: \#445d6e}  
span.s1 {font-kerning: none}  
span.s2 {font: 11.1px Monaco; font-kerning: none; background-color: rgba\(0, 0, 0, 0.039\)}  
span.s3 {font: 13.0px Helvetica; text-decoration: underline ; font-kerning: none}  
span.s4 {text-decoration: underline ; font-kerning: none}  
ul.ul1 {list-style-type: disc}  


**1. Set up the repository**

Set up the Docker CE repository on Ubuntu. Thelsb\_release -cssub-command prints the name of your Ubuntu version, likexenialortrusty.

sudo apt-get -y install \

 apt-transport-https \

 ca-certificates \

 curl

  


curl -fsSL https://download.docker.com/linux/ubuntu/gpg \| sudo apt-key add -

  


sudo add-apt-repository \

 "deb \[arch=amd64\] https://download.docker.com/linux/ubuntu \

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



