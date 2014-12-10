Cent-OS-nodejs-ghost
====================

######How to create the blog of ghost in Cent Operate System
怎么在Cent OS等Linux系统上创建基于Nodejs的Ghost博客

host文档还不完备，仍在继续完善中，每天可能都会有更新和改进。如果你遇到了难题或者有改进意见，请告诉我们。

Ghost构建于Node.js平台之上，支持0.10.*版本（最新稳定版）的Node.js。

在你的本地计算机上运行Ghost其实很简单，前提是你已经安装了Node.js。

什么是Node.js？参考网站：http://nodejs.org/
Node.js是构建快速、扩展性良好并且高效的web应用的开发平台。在过去的20年间，web从一堆静态页面进化为能够支持复杂web应用（例如Gmail和facebook）的平台。而JavaScript这一编程语言是这一进程的推进剂。

Node.js让我们具有了开发服务器端JavaScript程序的能力。而在以前，JavaScript只能在浏览器上运行，如果要开发服务器端的程序，就要使用PHP一类的编程语言了。如果能够用同一种开发语言来完成web应用的开发，这将是多么棒！并且，Node.js还赋予了前端开发工程师更大的能力。

Node.js让这一切变为可能，其原理是对Google Chrome浏览器所用的JavaScript引擎进行了包装，让它能够跨平台运行。也就是说，你能在自己的电脑上非常快速的安装Ghost并让它非常快捷、方便的跑起来。 接下来我们详细讲解如何在Mac、Windows或Linux上安装Ghost，另外还介绍了如何在服务器或托管空间上部署Ghost。

#####起步
如果你厌烦了手工安装Node.js和Ghost，可以试试BitNami团队开发的Ghost安装工具，它提供了对所有主流平台的支持。

######在 Linux 上安装
 安装 Node
 你可以通过从 http://nodejs.org 下载 .tar.gz 存档或者是通过包管理器安装。你可以根据 这篇文章 的说明来从包管理器安装 Node
-通过在终端窗口中输入 node -v 和 npm -v检查 Node 和 npm 是否安装成功
+通过在终端窗口中输入 `node -v `和 `npm -v`检查 Node 和 npm 是否安装成功
 安装并运行 Ghost
 登录到 http://ghost.org，然后点击蓝色的 'Download Ghost Source Code' 按钮
 在下载页，点击下载最新的 zip 压缩文件然后将文件解压到你想运行 Ghost 的地方
 @@ -31,23 +31,23 @@ Node.js让这一切变为可能，其原理是对Google Chrome浏览器所用的
 
 ####使用以下命令下载 Ghost 的最新版：
 
-$ curl -L https://ghost.org/zip/ghost-latest.zip -o ghost.zip
+`$ curl -L https://ghost.org/zip/ghost-latest.zip -o ghost.zip`
 使用以下命令解压存档：
 
-$ unzip -uo ghost.zip -d ghost
+`$ unzip -uo ghost.zip -d ghost`
 在你解压好之后，打开一个终端：
 
-切换到刚才解压的 Ghost 文件夹目录下，可以复制到/home/wwwroot/xxx.com/下面。这是已经添加的虚拟主机（lnmp环境）
+切换到刚才解压的 Ghost 文件夹目录下，可以复制到`/home/wwwroot/xxx.com/`下面。这是已经添加的虚拟主机（lnmp环境）
 
 $ cd /你的 Ghost 解压目录
 输入以下命令安装 Ghost ：
 
-npm install --production
+`npm install --production`
 注意是两个 -
 
 ###在 npm 结束安装后，输入以下命令让 Ghost 以开发模式启动：
 
-$ npm start
+`$ npm star`
 Ghost 将会运行在 127.0.0.1:2368
 你可以在 config.js 中修改IP地址和端口
 
 @@ -62,10 +62,10 @@ Ghost 将会运行在 127.0.0.1:2368
 Forever (https://npmjs.org/package/forever)
 你可以使用 forever 以后台任务运行 Ghost 。forever 将会按照 Ghost 的配置，当进程 crash 后重启 Ghost。
 
-通过 npm install forever -g 安装 forever
-为了让 forever 从 Ghost 安装目录运行，输入 NODE_ENV=production forever start index.js
-通过 forever stop index.js 停止 Ghost
-通过 forever list 检查 Ghost 当前是否正在运行
+通过 `npm install forever -g` 安装 forever
+为了让 forever 从 Ghost 安装目录运行，输入 `NODE_ENV=production forever start index.js`
+通过 `forever stop index.js `停止 Ghost
+通过` forever list `检查 Ghost 当前是否正在运行
 
 ######配置 Ghost 域名
 
 @@ -73,19 +73,21 @@ Forever (https://npmjs.org/package/forever)
 
 安装 lnmp(参考 http://lnmp.org/install.html)
 
-wget -c http://soft.vpser.net/lnmp/lnmp1.1-full.tar.gz && tar zxf lnmp1.1-full.tar.gz && cd lnmp1.1-full && ./centos.sh
+`wget -c http://soft.vpser.net/lnmp/lnmp1.1-full.tar.gz && tar zxf lnmp1.1-full.tar.gz && cd lnmp1.1-full && ./centos.sh`
 这个命令将会安装nginx并且设定好所有必需的目录和基础配置。
 
 配置你的站点
 
-在 /usr/local/nginx/conf/vhost 修改xxxx.com.conf 文件(指的是在/root/vhost.sh建立的虚拟机xxx.com.conf文件 参考http://lnmp.org/faq/lnmp-vhost-add-howto.html）
-使用文本编辑器或者SFTP打开这个文件 (/usr/local/nginx/conf/vhost/xxx.com.conf) 先去掉文本server_name example.com;下面的内容，
-保留server {
+在 `/usr/local/nginx/conf/vhost` 修改xxxx.com.conf 文件(指的是在/root/vhost.sh建立的虚拟机xxx.com.conf文件 参考http://lnmp.org/faq/lnmp-vhost-add-howto.html）
+使用文本编辑器或者SFTP打开这个文件 `(/usr/local/nginx/conf/vhost/xxx.com.conf)` 先去掉文本`server_name example.com`;下面的内容，
+保留
+```
+server {
     listen 80;
     server_name example.com;
-  
+  ```
 接着把以下内容复制进这个文件：
-
+```
 server {
     listen 80;
     server_name example.com;
 @@ -96,10 +98,11 @@ server {
         proxy_pass         http://127.0.0.1:2368;
     }
 }
+```
 将 server_name 的值改为你的域名。
 
 #####用文本编辑器修改你的配置文件/home/wwwroot/xxx.com/config.js，查找production: { ，直接找到url,修改为url:'http://xxx.com'如下：
-
+```
 config = {
     // ### Production
     // When running Ghost in the wild, use the production environment
 @@ -114,24 +117,27 @@ config = {
             },
             debug: false
         },
+```
 接着输入命令
-service nginx restart
+`service nginx restart`
 
-如果不行的话，请重启主机。接着在命令行输入cd /home/wwwroot/xxx.com/后在输入npm start再输入forever start index.js
+如果不行的话，请重启主机。接着在命令行输入` cd /home/wwwroot/xxx.com/ `后在输入npm start再输入`forever start index.js`
 这样就完成了。
 
 
 #####想要添加Supervisor或者初始化脚本，请看下：
-Supervisor (http://supervisord.org/)
+`Supervisor (http://supervisord.org/)`
 流行的 Linux 发行版——例如 Fedora， Debian 和 Ubuntu，都包含一个 Supervisor 包：一个进程控制系统，允许在启动的时候无需初始化脚本就能运行 Ghost。不像初始化脚本一样，Supervisor 可以移植到不同的发行版和版本。
 
 根据不同的 Linux 发行版 安装 Supervisor 。如下所示：
+```
 Debian/Ubuntu： apt-get install supervisor
 Fedora： yum install supervisor
+```
 其他大多数发行版： easy_install supervisor
 通过 service supervisor start 确保 Supervisor 运行
 为 Ghost 创建一个启动脚本。通常为 /etc/supervisor/conf.d/ghost.conf ，例如：
-
+```
 [program:ghost]
 command = node /path/to/ghost/index.js
 directory = /path/to/ghost
 @@ -141,18 +147,20 @@ autorestart = true
 stdout_logfile = /var/log/supervisor/ghost.log
 stderr_logfile = /var/log/supervisor/ghost_err.log
 environment = NODE_ENV="production"
-使用 Supervisor 启动 Ghost：supervisorctl start ghost
+```
+使用 Supervisor 启动 Ghost：`supervisorctl start ghost`
 
-停止 Ghost： supervisorctl stop ghost
+停止 Ghost：` supervisorctl stop ghost`
 详细内容请参阅 Supervisor 文档。
 
 初始化脚本
 Linux 系统在启动的时候会运行初始化脚本。这些脚本通常存在于 /etc/init.d 。为了让 Ghost 一直运行下去甚至自动重启，你可以设置一个初始化脚本来完成这个任务。以下的例子工作在 Ubuntu ，并且在 Ubuntu 12.04 下测试通过。
 
 使用以下命令创建 /etc/init.d/ghost 文件：
-
+```
 $ sudo curl https://raw.github.com/TryGhost/Ghost-Config/master/init.d/ghost \
   -o /etc/init.d/ghost
+  ```
 使用 nano /etc/init.d/ghost 命令打开文件并检查以下内容：
 
 将 GHOST_ROOT 变量的值更换为你的 Ghost 安装路径
 @@ -161,27 +169,29 @@ $ sudo curl https://raw.github.com/TryGhost/Ghost-Config/master/init.d/ghost \
 
 这个初始化脚本将在你的系统上以它自己的 Ghost 用户和用户组运行，使用以下命令来创建：
 
-$ sudo useradd -r ghost -U
+`$ sudo useradd -r ghost -U`
 确保 Ghost 用户可以访问安装目录：
 
-$ sudo chown -R ghost:ghost /你的 Ghost 安装目录
+`$ sudo chown -R ghost:ghost /`你的 Ghost 安装目录
 使用以下命令给这个初始化脚本加上可执行权限：
 
-$ sudo chmod 755 /etc/init.d/ghost
+`$ sudo chmod 755 /etc/init.d/ghost`
 现在你可以使用以下的命令来控制 Ghost ：
-
+```
 $ sudo service ghost start
 $ sudo service ghost stop
 $ sudo service ghost restart
 $ sudo service ghost status
+```
 为了让 Ghost 能在系统启动时同时启动，我们必须要将刚刚创建的初始化脚本注册为为启动项。 执行以下两个命令：
-
+```
 $ sudo update-rc.d ghost defaults
 $ sudo update-rc.d ghost enable
+```
 为了保证你的用户可以更改 Ghost 目录里的文件和默认的 config.js ，需要将你加入 ghost 用户组中： $ sudo adduser 你的用户名 ghost
 
 如果你现在重启你的服务器，Ghost 应该会自动运行。
 
 使用 forever 和如何在 ubuntu 下建立 Ghost 守护进程的文档即将发布！
 
-参考文件出自：http://docs.ghostchina.com/zh/installation/deploy/
+参考文件出自：<http://docs.ghostchina.com/zh/installation/deploy/>
