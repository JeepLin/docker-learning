### 查看系统已存在镜像：
    > docker images
    REPOSITORY              TAG                 IMAGE ID            CREATED             SIZE
	<none>                  <none>              a07a7ba9be7a        6 hours ago         1.029 GB
	tensorflow/tensorflow   latest              ea40dcc45724        9 days ago          1.029 GB
	dwhitena/gophernotes    latest              4cf782ddc225        4 months ago        979 MB
	klook/product           1.0                 1db6549c0e46        5 months ago        692.9 MB
	golang                  1.7.0               fe25c00086fb        6 months ago        669.6 MB
	golang                  latest              fe25c00086fb        6 months ago        669.6 MB
	ubuntu                  latest              f8d79ba03c00        6 months ago        126.4 MB
	elasticsearch           2.2                 0ad63774f5cf        6 months ago        347.2 MB
	redis                   3.2.3               e5181bd07b8e        6 months ago        185 MB
	redis                   latest              e5181bd07b8e        6 months ago        185 MB
	redis                   3.0                 22d1a4cb1939        6 months ago        177.6 MB
	mysql                   5.7.14              43c70d2fa278        6 months ago        384.5 MB
	golang                  1.6.3               f24c8478ed40        6 months ago        744.2 MB
	centos                  7.2.1511            686672a1d0cc        7 months ago        194.6 MB
	hello-world             latest              c54a2cc56cbb        7 months ago        1.848 kB
	mysql                   5.6.31              01bbb21c400c        8 months ago        330 MB
	nginx                   1.10                82e97a2b0390        8 months ago        182.8 M


### 系统启动dwhitena/gophernotes镜像，并不指定对应端口号
	> docker run -p 8888 -d dwhitena/gophernotes jupyter notebook --ip=0.0.0.0 
	292f963d7f5b814c7eefb333c2f5e022ae2ea1fc88c7eb58348ca8162ef01962

### 查看镜像发现此时容器端口对应的宿主机端口是32768
	> docker ps
	CONTAINER ID        IMAGE                  COMMAND                  CREATED             STATUS              PORTS                     NAMES
	292f963d7f5b        dwhitena/gophernotes   "jupyter notebook --i"   3 seconds ago       Up 2 seconds        0.0.0.0:32768->8888/tcp   romantic_murdock

### kill container，重启再观察其对应端口，发现对应的端口号变成了32769
	> docker stop romantic_murdock
	romantic_murdock

	> docker ps                   
	CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

	> docker run -p 8888 -d dwhitena/gophernotes jupyter notebook --ip=0.0.0.0
	fe4d5657d95f7c60c088403b89e6d97177bc5e9176d82127d3b10c60bbccf826

	> docker ps                                                               
	CONTAINER ID        IMAGE                  COMMAND                  CREATED             STATUS              PORTS                     NAMES
	fe4d5657d95f        dwhitena/gophernotes   "jupyter notebook --i"   3 seconds ago       Up 2 seconds        0.0.0.0:32769->8888/tcp   kickass_fermi

	> docker stop romantic_murdock                                            
	romantic_murdock

### **这就说明 docker run 命令当不指定对应端口时，宿主机将随机分配空闲端口和容器中端口对应**
