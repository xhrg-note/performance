### docker基本的。
```
docker ps  ## 查看后台进程，也就是有哪些容器在跑，docker ps -a 查看所有的。
docker images ## 查看有哪些镜像
docker exec -ti 1f9ee bash ##进入容器，1f9ee指的是容器container id的前5位
docker logs -f 47ba227a1a32 ## 容器id



docker run -d --name tomcat -p 8081:8080 tomcat ## docker启动tomcat
```



### redis相关

```
docker run --name redis -d -p 6379:6379 redis --requirepass "redis" ## 启动redis
## 这里的d0b86是启动的“CONTAINER ID”的前5位
docker exec -ti d0b86 redis-cli
docker exec -ti d0b86 redis-cli -h 127.0.0.1 -p 6379 
```


### mysql相关
```
* 一句话就可以安装一个mysql
* docker run --name mysql5.7 -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.7 
```