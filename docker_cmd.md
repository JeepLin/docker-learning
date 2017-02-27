###docker命令

###1、查看当前机器上的docker镜像
	docker images 
	
	> docker images
	REPOSITORY              TAG                 IMAGE ID            CREATED             SIZE
	dockcross/windows-x86   latest              5f434626aeb1        13 hours ago        1.915 GB
	dockcross/windows-x64   latest              a8573b83b12a        13 hours ago        1.961 GB
	tensorflow/tensorflow   latest              ea40dcc45724        2 weeks ago         1.029 GB
	dwhitena/gophernotes    latest              4cf782ddc225        4 months ago        979 MB
	klook/product           1.0                 1db6549c0e46        6 months ago        692.9 MB
	golang                  1.7.0               fe25c00086fb        6 months ago        669.6 MB
	golang                  latest              fe25c00086fb        6 months ago        669.6 MB
	ubuntu                  latest              f8d79ba03c00        6 months ago        126.4 MB
	elasticsearch           2.2                 0ad63774f5cf        6 months ago        347.2 MB
	redis                   3.2.3               e5181bd07b8e        6 months ago        185 MB
	redis                   latest              e5181bd07b8e        6 months ago        185 MB
	redis                   3.0                 22d1a4cb1939        6 months ago        177.6 MB
	mysql                   5.7.14              43c70d2fa278        6 months ago        384.5 MB
	golang                  1.6.3               f24c8478ed40        7 months ago        744.2 MB
	centos                  7.2.1511            686672a1d0cc        8 months ago        194.6 MB
	hello-world             latest              c54a2cc56cbb        8 months ago        1.848 kB
	mysql                   5.6.31              01bbb21c400c        8 months ago        330 MB
	nginx                   1.10                82e97a2b0390        9 months ago        182.8 MB

###2、启动容器
	//-d  		后台启动
	//-it		前台启动
	//-p  		宿主机中的2222端口号对应docker容器中的22端口号
	//-v  		将容器中的container_dir目录映射到宿主机上的host_dir目录
	//—name 	container名字
	//-e  		设置环境变量
	docker run -d -p 2222:22 -v host_dir:container_dir —name base klook/centos:7.1

###3、查看处于running状态下的container
	docker ps

###4、查看所有容器
	docker ps -a
	
	> docker ps -a
	CONTAINER ID        IMAGE                         COMMAND                  CREATED             STATUS                         PORTS               NAMES
	a9a96ac1507c        dockcross/windows-x64         "/dockcross/entrypoin"   About an hour ago   Exited (0) About an hour ago                       boring_einstein
	fa5227d27bab        dockcross/windows-x64         "/dockcross/entrypoin"   About an hour ago   Exited (0) About an hour ago                       windows64
	5e8c330a79f1        dwhitena/gophernotes          "jupyter notebook --i"   5 days ago          Exited (0) 5 days ago                              elegant_feynman
	fe4d5657d95f        dwhitena/gophernotes          "jupyter notebook --i"   5 days ago          Exited (0) 5 days ago                              kickass_fermi
	292f963d7f5b        dwhitena/gophernotes          "jupyter notebook --i"   5 days ago          Exited (0) 5 days ago                              romantic_murdock
	8694982220a8        dwhitena/gophernotes          "jupyter notebook --i"   5 days ago          Exited (0) 5 days ago                              condescending_varahamihira
	4955c8824636        dwhitena/gophernotes:latest   "jupyter notebook"       5 days ago          Exited (0) 5 days ago                              gophernotes
	ee4a95bf55ff        dwhitena/gophernotes          "jupyter notebook"       5 days ago          Exited (0) 5 days ago                              trusting_hoover
	a6f59166c5f5        dwhitena/gophernotes          "jupyter notebook --n"   5 days ago          Exited (0) 5 days ago                              peaceful_rosalind
	e3e2078f9c27        dwhitena/gophernotes          "jupyter notebook --n"   5 days ago          Exited (0) 5 days ago                              compassionate_kirch
	33653d0f4ff6        a07a7ba9be7a                  "/bin/sh -c 'apt-get "   5 days ago          Exited (0) 5 days ago                              naughty_shockley
	8fbb8be86262        a07a7ba9be7a                  "/bin/sh -c 'apt-get "   5 days ago          Exited (0) 5 days ago                              happy_fermat
	86e7cbd58985        a07a7ba9be7a                  "/bin/sh -c 'apt-get "   5 days ago          Exited (0) 5 days ago                              agitated_lichterman
	33802d0cfcd9        klook/product:1.0             "/bin/sh -c 'go run m"   6 months ago        Exited (0) 6 months ago                            klook_product3
	e7931170970a        klook/product:1.0             "/bin/sh -c 'go run m"   6 months ago        Created                                            klook_product2
	dc9f7f9a2f51        klook/product:1.0             "/bin/sh -c 'go run m"   6 months ago        Exited (0) 6 months ago                            klook_product
	3c4782fda423        mysql:5.7.14                  "docker-entrypoint.sh"   6 months ago        Exited (0) 6 months ago                            mysql_5.7.14
	02c9071007e2        mysql:5.7.14                  "docker-entrypoint.sh"   6 months ago        Created                                            mysql5.7.14
	f70a0c2a990a        98cf418ae438                  "/bin/sh -c 'go run m"   6 months ago        Exited (0) 6 months ago                            klook-product
	9ede03b59007        a05700353473                  "/bin/sh -c 'cd /kloo"   6 months ago        Exited (0) 6 months ago                            sad_hamilton
	e18cb2683013        548583c680c5                  "/bin/sh -c 'cd /kloo"   6 months ago        Exited (0) 6 months ago                            jovial_goodall
	48f80c3d43c2        06307d46f82d                  "/bin/sh -c 'go run m"   6 months ago        Exited (0) 6 months ago


###5、构建镜像
	#Dockerfile在当前目录下
	docker build -t klool/php-fpm:5.4  .  

###6、进入容器
	#交互式模式进入base容器中的/bin/sh界面
	docker exec -it  base  /bin/sh

###7、进入容器  
	#尽量不用此命令，进去会卡，而且退出时会导致容器终止
	docker  attach

###8、删除容器强制
	#-f 强制删除dbserver容器
	docker rm -f  dbserver

###9、删除镜像
	#-f 强制删除dbserver容器
	docker rmi -f dbserver

###10、停止容器
	#停止容器id为d03开头的container
	docker stop d03

###11、容器打tag（docker images命令显示的tag）
	docker tag klook/php-fpm:5.4  10.225.43.181:5000/klook/php-fpm:5.4

###12、push镜像到hub库中
	docker push  10.225.43.181:5000/klook/php-fpm:5.4  

###13、容器中退出  
	docker容器命令行中输入 exit
