# 安装docker
1. 官网安装
[docker文档链接地址](https://docs.docker.com/engine/install/centos/)
2. 需要换docker源
```yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo```
                  
3. 命令
>1.docker pull mysql  
>2.docker pull mysql:5.7  
>3.docker rmi -f 容器id  
>4.docker rmi -f 容器id 容器id  
>5.docker rmi -f $(docker images -aq) 删除全部容器  
>6.docker run -it centos /bin/bash 运行centos，exit退出容器，Ctrl+P+Q容器不停止退出  
>7.docker rm 容器id 不能删除正在运行的容器  
>8.dokcer rm -f $(docker ps -aq) 删除所有容器  
>9.docker rm -f $(docker ps -a | grep yupao | awk '{print $1}') 
>10.docker start 容器id 启动容器  
>11.docker stop 容器id 停止容器  
>12.docker restart 容器id 重新启动容器  

4.注意  

```
docker run -d 镜像名  
运行docker ps 发现 centos停止  
常见的坑，docker容器使用后台运行,就必须需要有一个前台进程,docker发现没有应用,就会自动停止  
nginx容器启动后,发现自己没有提供服务,就会立刻停止,就是没有程序

```  

5.从容器复制到主机  
docker cp 容器id:文件地址 主机路径  
docker cp aaaaaa:/home/test.go /home

6.安装elasticsearch 需要加内存限制 -e

7.卷挂载
docker run -it -v /home/ceshi:/home centos /bin/bash




