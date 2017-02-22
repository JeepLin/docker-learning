### 1、安装java (为Jenkins准备运行环境)
	[root@iZwz966hn1pkoq08pnu6foZ ~]# yum install java7
	Failed to set locale, defaulting to C
	Loaded plugins: security
	base     				| 3.7 kB     00:00     
	epel     				| 4.3 kB     00:00     
	epel/primary_db     	| 5.0 MB     00:05     
	extras      			| 3.3 kB     00:00     
	updates             	| 3.4 kB     00:00     
	updates/primary_db  	| 4.1 MB     00:03     
	Setting up Install Process
	Resolving Dependencies
	--> Running transaction check
	---> Package java-1.7.0-openjdk.i686 1:1.7.0.131-2.6.9.0.el6_8 will be installed
	--> Processing Dependency: nss(x86-32) >= 3.21.3 for package: 1:java-1.7.0-openjdk-1.7.0.131-2.6.9.0.el6_8.i686
	--> Processing Dependency: jpackage-utils >= 1.7.3-1jpp.2 for package: 1:java-1.7.0-openjdk-1.7.0.131-2.6.9.0.el6_8.i686
	--> Processing Dependency: libgconf-2.so.4 for package: 1:java-1.7.0-openjdk-1.7.0.131-2.6.9.0.el6_8.i686
	--> Running transaction check
	---> Package pcsc-lite-libs.i686 0:1.5.2-15.el6 will be installed
	---> Package pulseaudio-libs.i686 0:0.9.21-24.el6 will be installed
	--> Processing Dependency: libsndfile.so.1(libsndfile.so.1.0) for package: pulseaudio-libs-0.9.21-24.el6.i686
	--> Processing Dependency: libsndfile.so.1 for package: pulseaudio-libs-0.9.21-24.el6.i686
	--> Processing Dependency: libasyncns.so.0 for package: pulseaudio-libs-0.9.21-24.el6.i686
	---> Package tzdata-java.noarch 0:2016j-1.el6 will be installed
	---> Package xorg-x11-fonts-Type1.noarch 0:7.2-11.el6 will be installed
	--> Processing Dependency: ttmkfdir for package: xorg-x11-fonts-Type1-7.2-11.el6.noarch
	--> Processing Dependency: ttmkfdir for package: xorg-x11-fonts-Type1-7.2-11.el6.noarch
	--> Processing Dependency: mkfontdir for package: xorg-x11-fonts-Type1-7.2-11.el6.noarch
		--> Processing Dependency: mkfontdir for package: xorg-x11-fonts-Type1-7.2-11.el6.noarch
	--> Running transaction check
	---> Package ORBit2.i686 0:2.14.17-6.el6_8 will be installed
	--> Processing Dependency: libIDL-2.so.0 for package: ORBit2-2.14.17-6.el6_8.i686
	---> Package libasyncns.i686 0:0.8-1.1.el6 will be installed
	---> Package libsndfile.i686 0:1.0.20-5.el6 will be installed
	--> Processing Dependency: libvorbisenc.so.2 for package: libsndfile-1.0.20-5.el6.i686
	--> Processing Dependency: libvorbis.so.0 for package: libsndfile-1.0.20-5.el6.i686
	--> Processing Dependency: libogg.so.0 for package: libsndfile-1.0.20-5.el6.i686
	--> Processing Dependency: libFLAC.so.8 for package: libsndfile-1.0.20-5.el6.i686
	---> Package nspr.i686 0:4.10.6-1.el6_5 will be updated
	---> Package nspr.i686 0:4.11.0-1.el6 will be an update
	---> Package nss-softokn.i686 0:3.14.3-10.el6_5 will be updated
	---> Package nss-softokn.i686 0:3.14.3-23.3.el6_8 will be an update
	--> Processing Dependency: nss-softokn-freebl(x86-32) >= 3.14.3-23.3.el6_8 for package: nss-softokn-3.14.3-23.3.el6_8.i686
	---> Package nss-sysinit.i686 0:3.16.1-4.el6_5 will be updated
	---> Package nss-sysinit.i686 0:3.21.3-2.el6_8 will be an update
	---> Package nss-tools.i686 0:3.16.1-4.el6_5 will be updated
	---> Package nss-tools.i686 0:3.21.3-2.el6_8 will be an update
	---> Package nss-util.i686 0:3.16.1-1.el6_5 will be updated
	---> Package nss-util.i686 0:3.21.3-1.el6_8 will be an update
	---> Package sgml-common.noarch 0:0.6.3-33.el6 will be installed
	---> Package ttmkfdir.i686 0:3.0.9-32.1.el6 will be installed
	---> Package xorg-x11-font-utils.i686 1:7.2-11.el6 will be installed
	--> Processing Dependency: libfontenc.so.1 for package: 1:xorg-x11-font-utils-7.2-11.el6.i686
	--> Processing Dependency: libXfont.so.1 for package: 1:xorg-x11-font-utils-7.2-11.el6.i686
	--> Running transaction check
	---> Package flac.i686 0:1.2.1-7.el6_6 will be installed
	---> Package libIDL.i686 0:0.8.13-2.1.el6 will be installed
	---> Package libXfont.i686 0:1.5.1-2.el6 will be installed
	---> Package libfontenc.i686 0:1.1.2-3.el6 will be installed
	---> Package libogg.i686 2:1.1.4-2.1.el6 will be installed
	---> Package libvorbis.i686 1:1.2.3-4.el6_2.1 will be installed
	---> Package nss-softokn-freebl.i686 0:3.14.3-10.el6_5 will be updated
	---> Package nss-softokn-freebl.i686 0:3.14.3-23.3.el6_8 will be an update
	--> Finished Dependency Resolution
	
	Dependencies Resolved
	
	Dependency Updated:
	  nspr.i686 0:4.11.0-1.el6              nss.i686 0:3.21.3-2.el6_8           nss-softokn.i686 0:3.14.3-23.3.el6_8     nss-softokn-freebl.i686 0:3.14.3-23.3.el6_8    
	  nss-sysinit.i686 0:3.21.3-2.el6_8     nss-tools.i686 0:3.21.3-2.el6_8     nss-util.i686 0:3.21.3-1.el6_8          
	
	Complete!

### 2、查看是否安装完成
	[root@iZwz966hn1pkoq08pnu6foZ ~]# java
	Usage: java [-options] class [args...]
	           (to execute a class)
	   		or  java [-options] -jar jarfile [args...]
	           (to execute a jar file)
	where options include:
	    -d32	  use a 32-bit data model if available
	    -d64	  use a 64-bit data model if available
	    -client	  to select the "client" VM
	    -server	  to select the "server" VM
	    -hotspot	  is a synonym for the "client" VM  [deprecated]
	                  The default VM is client.
	See http://www.oracle.com/technetwork/java/javase/documentation/index.html for more details.

### 3、安装jenkins
	[root@iZwz966hn1pkoq08pnu6foZ ~]# sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
	[root@iZwz966hn1pkoq08pnu6foZ ~]# sudo yum install jenkins
	Failed to set locale, defaulting to C
	Loaded plugins: security
	jenkins          		| 2.9 kB     00:00     
	jenkins/primary_db      |  92 kB     00:04     
	Setting up Install Process
	Resolving Dependencies
	--> Running transaction check
	---> Package jenkins.noarch 0:2.47-1.1 will be installed
	--> Finished Dependency Resolution
	
	Dependencies Resolved

	Install       1 Package(s)
	
	Total download size: 65 M
	Installed size: 66 M
	Is this ok [y/N]: y
	Downloading Packages:
	jenkins-2.47-1.1.noarch.rpm        	|  65 MB     00:02     
	Running rpm_check_debug
	Running Transaction Test
	Transaction Test Succeeded
	Running Transaction
	  Installing : jenkins-2.47-1.1.noarch  1/1 
	  Verifying  : jenkins-2.47-1.1.noarch  1/1 
	
	Installed:
	  jenkins.noarch 0:2.47-1.1                                                                                                                                           
	
	Complete!

### 4、开启Jenkins服务
	[root@iZwz966hn1pkoq08pnu6foZ ~]# sudo service jenkins start
	Starting Jenkins                                           [  OK  ]
	[root@iZwz966hn1pkoq08pnu6foZ ~]# sudo chkconfig jenkins on
	[root@iZwz966hn1pkoq08pnu6foZ ~]# ps -ef | grep jen
	jenkins  30014     1 81 20:36 ?        00:00:14 /etc/alternatives/java -Dcom.sun.akuma.Daemon=daemonized -Djava.awt.headless=true -DJENKINS_HOME=/var/lib/jenkins -jar /usr/lib/jenkins/jenkins.war --logfile=/var/log/jenkins/jenkins.log --webroot=/var/cache/jenkins/war --daemon --httpPort=8080 --debug=5 --handlerCountMax=100 --handlerCountMaxIdle=20
	root     30061 29883  0 20:36 pts/0    00:00:00 grep jen

### 5、配置Jenkisn构建任务
	项目名称		jenkins_helloworld
	源码管理		Git > https://github.com/JeepLin/go-learning.git > master分支
	构建触发器		触发远程构建 > 	身份验证令牌 > jenkins_helloworld_token
	增加构建步骤	Execute shell > Command > ping www.baidu.com

保存以上配置可以

### 6、配置对应github中webhook
找到项目的github [webhook配置页](https://github.com/JeepLin/go-learning/settings/hooks/)
将Payload URL设置为:http://{user}:{token}@{JENKINS_URL}/job/jenkins_helloworld/build?token=jenkins_helloworld_token #user和token为创建配置的账户id和API token，在用户页可找到

配置好后点击 Update webhook 即生效


### 7、查看Jenkins是否生效

在JeepLin/go-learning项目中master分支创建一个文件，push后再观察Jenkins中配置任务变化

发现构建执行状态间隔一两秒后会出现进度条，点击查看终端输出，可看到如下字样：

	Started by user jeep lin
	Building in workspace /var/lib/jenkins/workspace/jenkins_helloworld
	 > git rev-parse --is-inside-work-tree # timeout=10
	Fetching changes from the remote Git repository
	 > git config remote.origin.url https://github.com/JeepLin/go-learning.git # timeout=10
	Fetching upstream changes from https://github.com/JeepLin/go-learning.git
	 > git --version # timeout=10
	 > git fetch --tags --progress https://github.com/JeepLin/go-learning.git +refs/heads/*:refs/remotes/origin/*
	 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
	 > git rev-parse refs/remotes/origin/origin/master^{commit} # timeout=10
	Checking out Revision 0153c1f635d222043a573cf3cd73c23a41d3c6d5 (refs/remotes/origin/master)
	 > git config core.sparsecheckout # timeout=10
	 > git checkout -f 0153c1f635d222043a573cf3cd73c23a41d3c6d5
	 > git rev-list 900670e5e10ac81dc0fc84f7d0b2a0be8a441cfc # timeout=10
	[jenkins_helloworld] $ /bin/sh -xe /tmp/hudson1579000184973582681.sh
	+ ping www.baidu.com
	PING www.a.shifen.com (115.239.211.112) 56(84) bytes of data.
	64 bytes from 115.239.211.112: icmp_seq=1 ttl=52 time=27.4 ms
	64 bytes from 115.239.211.112: icmp_seq=2 ttl=52 time=27.5 ms
	64 bytes from 115.239.211.112: icmp_seq=3 ttl=52 time=27.5 ms
	64 bytes from 115.239.211.112: icmp_seq=4 ttl=52 time=27.4 ms
	64 bytes from 115.239.211.112: icmp_seq=5 ttl=52 time=27.5 ms
	64 bytes from 115.239.211.112: icmp_seq=6 ttl=52 time=27.4 ms

因为任务构建时执行的cmd命令是 ping www.baidu.com，所以现在终端输出就代表**push代码到github触发Jenkins构建任务成功，如果要结合docker运行任务的话，只需写好一份shell脚本就可以了**


**以上  2017-02-22 22：30：32**


