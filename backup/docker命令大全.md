# docker命令大全

## 一、启动类

### 1\. 启动 docker
    
    
    systemctl start docker
    

### 2\. 关闭 docker
    
    
    systemctl stop docker
    

### 3\. 重新启动 docker
    
    
    systemctl restart docker
    
    

### 4\. docker 设置自启动
    
    
    systemctl enable docker
    

### 5\. 查看 docker 运行状态
    
    
    systemctl status docker
    

### 6\. 查看 docker 版本号等信息
    
    
    docker version
    

或者
    
    
    docker info
    

该命令还可以查看到有多少 容器及其状态 和 镜像 的信息

![](https://i-blog.csdnimg.cn/direct/5b9b5b83da244a88b2ae43a3ae821cc4.png)

## 二、 镜像类

### 1\. 查看镜像
    
    
    docker images
    

### 2\. 搜索镜像
    
    
    docker search [OPTIONS] 镜像名字
    docker search mysql
    

### 3\. 拉取镜像
    
    
    docker pull
    docker pull mysql #没有制定版本则默认最新版 
    

[docker官方镜像地址](https://hub.docker.com/search?type=image "docker官方镜像地址")

### 4\. 运行镜像
    
    
    docker run
    docker run tomcat
    

运行镜像后可以按 ctrl+c 退出

### 5\. 删除镜像
    
    
    docker rmi  镜像名/镜像ID #若镜像在运行则会报错
    docker rmi -f 镜像名/镜像ID #强制删除一个
    docker rmi -f mysql
    
    docker rmi -f 镜像名/镜像ID 镜像名/镜像ID 镜像名/镜像ID #删除多个 其镜像ID或镜像用用空格隔开即可 
    docker rmi -f mysql redis
    
    docker rmi -f $(docker images -aq)
    #删除全部镜像  -a 意思为显示全部, -q 意思为只显示ID
    

### 6\. 加载镜像
    
    
    docker load -i 镜像保存文件位置
    docker load myimage.tar
    

### 7\. 保存镜像
    
    
    docker save 镜像名/镜像ID -o 镜像保存位置和名字
    docker save tomcat -o /myimage.tar
    

## 三、容器类

### 1\. 查看正在运行的容器
    
    
    docker ps
    docker ps -a # 查看所有容器
    #加格式化方式访问，格式会更加清爽
    docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Ports}}\t{{.Status}}\t{{.Names}}"
    

### 2\. 创建容器
    
    
    docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
    常用参数：
    --name=NAME   #为容器指定名字为NAME，不使用的话系统自动为容器命名
    -d: 后台运行容器并返回容器ID，也即启动守护式容器(后台运行)；
     
    -i：以交互模式运行容器，通常与 -t 同时使用；
    -t：为容器重新分配一个伪输入终端，通常与 -i 同时使用；
    也即启动交互式容器(前台有伪终端，等待交互，一般连用，即-it)；
     
    -P: 随机端口映射，大写P
    -p: 指定端口映射，小写p
    
    # 创建并允许 Nginx 容器
    docker run -d --name nginx -p 80:80 nginx
    

### 3\. 启动守护式容器（后台运行）
    
    
    docker run -d 容器名
    docker run -d redis:6.0.8
    

### 4\. 停止容器
    
    
    docker stop 容器名
    docker stop nginx
    

### 5\. 启动容器
    
    
    docker start 容器名
    docker start nginx
    docker restart 容器名
    docker restart nginx
    
    

### 6\. 进入正在运行的容器
    
    
    docker exec -it 容器名 bashshell
    docker exec -it nginx /bin/bash```
    

### 7\. 停止容器
    
    
    docker stop 容器名
    docker stop nginx
    

### 8\. 强制停止容器
    
    
    docker kill 容器名
    docker kill nginx
    

### 9\. 删除容器
    
    
    #删除一个
    docker rm 容器ID  
    docker rm nginx
    docker rm -f 容器ID  #强制删除
    docker rm -f nginx
    
     
    #删除多个
    docker rm -f $(docker ps -a -q)
    或
    docker ps -a -q | xargs docker rm
    

### 10\. 查看容器日志
    
    
    docker logs 容器名
    docker logs nginx
    

### 11\. 查看容器内运行的进程
    
    
    docker top 容器名
    docker top nginx
    

### 12\. 查看容器内部细节
    
    
    docker inspect 容器名
    docker inspect nginx
    

### 13\. 创建容器数据卷挂载
    
    
    # 创建容器并指定数据卷，注意通过 -v 参数来指定数据卷
    docker run -d --name nginx -p 80:80 -v html:/usr/share/nginx/html nginx
    

### 14\. 查看数据卷
    
    
    docker volume ls
    

### 15\. 查看数据卷详情
    
    
    docker volume inspect 数据卷名
    docker volume inspect html
    

### 16\. 删除数据卷
    
    
    docker volume rm 数据卷名
    docker volume rm html
    

## 四. 网络类

### 1\. 查看网络
    
    
    docker network ls
    

### 2\. 创建网络
    
    
    docker network create 网络名
    docker network create hmall
    

### 3\. 查看网络数据源
    
    
    docker network inspect 网络名
    docker network inspect hmall
    

### 4\. 删除网络
    
    
    docker network rm 网络名
    docker nerwork rm hmall
    

## 五、 Docker compose

[官方文档：基本语法](https://docs.docker.com/compose/compose-file/legacy-versions/ "官方文档：基本语法")

假设docker run 部署 mysql命令如下
    
    
    docker run -d \
      --name mysql \
      -p 3306:3306 \
      -e TZ=Asia/Shanghai \
      -e MYSQL_ROOT_PASSWORD=123 \
      -v ./mysql/data:/var/lib/mysql \
      -v ./mysql/conf:/etc/mysql/conf.d \
      -v ./mysql/init:/docker-entrypoint-initdb.d \
      --network hmall
      mysql
    

那么用docker-compose.yml 文件定义就是：
    
    
    version: "3.8"
    
    services:
      mysql:
        image: mysql
        container_name: mysql
        ports:
          - "3306:3306"
        environment:
          TZ: Asia/Shanghai
          MYSQL_ROOT_PASSWORD: 123
        volumes:
          - "./mysql/conf:/etc/mysql/conf.d"
          - "./mysql/data:/var/lib/mysql"
        networks:
          - new
    networks:
      new:
        name: hmall
    

### 1\. 查看帮助
    
    
    docker-compose -h
    

### 2\. 启动所有服务
    
    
    docker-compose up
    docker-compose up -d # 后台运行
    

### 3\. 停止并删除容器、网络、卷、镜像。
    
    
    docker-compose down
    

### 4\. 进入容器实例内部
    
    
    docker-compose exec  yml里面的服务id
    

### 5\. 展示容器
    
    
    ocker-compose ps
    

### 6\. 展示进程
    
    
    docker-compose top
    

### 7\. 查看容器输出日志
    
    
    docker-compose logs  yml里面的服务id
    

### 8\. 检查配置
    
    
    docker-compose config
    docker-compose config -q # 检查配置，有问题才有输出
    

### 9\. 启动服务
    
    
    docker-compose start
    

### 10\. 重启服务
    
    
    docker-compose restart
    

### 11\. 停止服务
    
    
    docker-compose stop
    

## 六、 其他

### 1\. 命令别名
    
    
    # 修改/root/.bashrc文件
    vi /root/.bashrc
    内容如下：
    # .bashrc
    
    # User specific aliases and functions
    
    alias rm='rm -i'
    alias cp='cp -i'
    alias mv='mv -i'
    alias dps='docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Ports}}\t{{.Status}}\t{{.Names}}"'
    alias dis='docker images'
    
    # Source global definitions
    if [ -f /etc/bashrc ]; then
            . /etc/bashrc
    fi
    #退出
    exit
    :wq
    
    #执行命令使别名生效
    source /root/.bashrc
    

## 八。Docker更换国内镜像
    
    
    #!/bin/bash
     
    # 创建 /etc/docker 目录，如果目录已存在则不报错
    sudo mkdir -p /etc/docker
     
    # 写入 daemon.json 文件内容
    sudo tee /etc/docker/daemon.json <<-'EOF'
    {
        "registry-mirrors": [
            "https://dockerproxy.com",
            "https://docker.mirrors.ustc.edu.cn",
            "https://docker.nju.edu.cn",
            "https://cr.console.aliyun.com",
            "https://docker.mirrors.ustc.edu.cn",
            "http://hub-mirror.c.163.com",
            "https://hub.daocloud.io",
            "http://mirror.azure.cn",
            "https://mirror.baidubce.com",
            "https://docker.mirrors.sjtug.sjtu.edu.cn",
            "https://docker.nju.edu.cn",
            "https://docker.hpcloud.cloud",
            "https://docker.m.daocloud.io",
            "https://docker.unsee.tech",
            "https://docker.1panel.live",
            "http://mirrors.ustc.edu.cn",
            "https://docker.chenby.cn",
            "http://mirror.azure.cn",
            "https://dockerpull.org",
            "https://dockerhub.icu",
            "https://hub.rat.dev",
            "https://docker.m.daocloud.io",
            "https://dockerproxy.com",
            "https://docker.mirrors.ustc.edu.cn",
            "https://docker.nju.edu.cn",
            "https://cr.console.aliyun.com",
            "https://ccr.ccs.tencentyun.com",
            "https://dockerproxy.com",
            "https://hub-mirror.c.163.com",
            "https://mirror.baidubce.com",
            "https://hubgw.docker.com", 
            "https://docker.1ms.run", 
            "https://www.mirrorify.net", 
            "https://docker-pull.ygxz.in", 
            "https://docker.1yidc.com", 
            "https://dockerproxy.net", 
            "https://docker.aityp.com", 
            "https://www.container.fish"
        ]
    }
    EOF
     
    # 重新加载 systemd 配置
    sudo systemctl daemon-reload
     
    # 重启 Docker 服务
    sudo systemctl restart docker

    
