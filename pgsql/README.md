# docker_pgsql


postgresql服务端命令：
  绑定成image：
  
    docker build -t postgres:9.3 .
    
  运行postgres容器
  
    docker run -p 0.0.0.0:5432:5432 --name postgres -d postgres:9.3
  
postgresql客户端命令：
  绑定成image:
  
    docker build -t postgres-client .
    
  运行容器:
  
    docker run --name postgres-client -v $HOME/data:/opt/backup --link postgres:postgres -it postgres-client /bin/bash
    
