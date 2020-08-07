# docker_mongo


服务端：
  image：
  
    docker build -t mongo .
    
  容器：
  
    docker run --name mongo -p 0.0.0.0:27017:27017 -d mongo
    
客户端：
  image：
  
    docker build -t mongo-client .
    
  容器：
  
    docker run --name mongo-client --link mongo:mongo -v $HOME/data:/opt/backup -it mongo-client /bin/bash
    

