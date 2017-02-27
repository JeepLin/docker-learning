###Dockerfile 命令

####1、FROM	基础镜像定义
	//基于 centos7.1镜像为基础镜像
	FROM klook/centos:7.1 

####2、ENV	环境变量
	ENV APP_DIR /app

####3、RUN	执行cmd
	RUN yum -y install nginx  php-fmp
	RUN echo “daemon=off;” >> /etc/nginx/conf.d/default.conf

####4、ADD	将本地的文件复制到容器中
	ADD nginx_default.conf /etc/nginx/conf.d/default.conf

####5、COPY	将本地文件复制到容器中
	COPY scripts /scripts

####6、EXPOSE	设置对外暴露端口
	#80 http端口   
	#443 https端口
	EXPOSE 80 443

####7、ONBUILD	此处镜像不生效，下次FROM时才生效
	ONBUILD ADD . /app

####8、VOLUME	容器与宿主机间目录映射	
	#当容器删除时  保存这个目录  容器目录和宿主机目录相映射
	VOLUME [“/var/lib/mysql”]

####9、ENTRYPOINT	设置容器启动时执行命令（只有最后一条有效）
	//容器启动时运行命令 只有最后一条有效，如果写十条只有最后一条有效
	ENTRYPOINT [“/scripts/start”]
	ENTRY POINT [“/init.sh”, “/usr/bin/supervisord”, “-n”, “-c”, “/ect/supervisord.conf”]



####dockerfile中每一个指令都会生成一个layer
####.dockerignore文件和.gitignore文件一样，容器COPY时可以忽略该文件


