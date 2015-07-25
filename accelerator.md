## 镜像加速器
由于Docker的image的资源都在国外，所以在国内要获取Docker镜像，速度会很慢，Alauda云平台针对这种情况推出了加速器，可以加快您在国内获取Docker官方镜像的速度。

如果您觉得下载Docker的image的速度过慢，可以尝试使用我们的加速器，具体使用方法如下：

1. 安装/升级 Docker：具体安装步骤参考Docker相关手册：
   * [Windows](http://docs.docker.com/installation/windows/)
   * [Ubuntu](http://docs.docker.com/installation/ubuntulinux/)
   * [Debian](http://docs.docker.com/installation/debian/)
   * [Centos](http://docs.docker.com/installation/centos/)
   * [Mac](http://docs.docker.com/installation/mac/)

2. 配置加速器：将您的加速器加入到docker配置文件中，不同系统会有区别
   * Windows

     启动Boot2docker Start Shell

     `$ sudo "sh -c \"echo EXTRA_ARGS=\'--registry-mirror=http://houchaohann.m.alauda.cn\' >>/var/lib/boot2docker/profile\""`

     重新启动Boot2Docker

   * Ubuntu | Debian | Centos

     `$ sudo echo "DOCKER_OPTS=\"\$DOCKER_OPTS --registry-mirror=http://houchaohann.m.alauda.cn\"" >> /etc/default/docker`

     `$ service docker restart`

   * Mac

     `$ boot2docker ssh sudo "sh -c \"echo EXTRA_ARGS=\'--registry-mirror=http://houchaohann.m.alauda.cn\' >>/var/lib/boot2docker/profile\""`

     `$ boot2docker restart`

3. 使用：docker pull <image_name>

该加速器的工作原理就是，只要有用户在Alauda云平台下载过一次Docker的image，该image就会被系统所记录，下一次再次下载该image时，获取速度就会很快，不需要再次从国外获取这个image，通过安装加速器将会大大节约您pull image的时间。

 
