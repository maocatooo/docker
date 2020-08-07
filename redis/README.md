# docker_redis
docker_redis服务端

image：

  docker build -t redis .
  
容器：

  docker run --name reids -p 0.0.0.0:6379:6379 -d redis
  
