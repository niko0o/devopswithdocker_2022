# Part2 exercises

### 2.1 
docker-compose.yml
```
version: '3.8'

services:
    simple-web-service-2-1:
      image: devopsdockeruh/simple-web-service
      build: .
      volumes:
        - ./text.log:/usr/src/app/text.log
      container_name: simple-web-service-2-1
```

./text.log
```
2022-02-08 19:33:15 +0000 UTC
2022-02-08 19:33:17 +0000 UTC
2022-02-08 19:33:19 +0000 UTC
2022-02-08 19:33:21 +0000 UTC
2022-02-08 19:33:23 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-02-08 19:33:25 +0000 UTC
```

### 2.2 
docker-compose.yml
```
version: '3.8'

services:
    simple-web-service-2-2:
      image: devopsdockeruh/simple-web-service
      build: .
      ports: 
        - 8080:8080
      command: server
      container_name: simple-web-service-2-2
```

### 2.3 

docker-compose.yml
```
version: '3.8'

services:
    example-frontend:
      image: example-frontend
      build: ./material-applications/example-frontend
      ports: 
        - 5001:5000
      container_name: example-frontend
    example-backend: 
      image: example-backend
      build: ./material-applications/example-backend
      ports: 
        - 8080:8080
      container_name: example-backend
```

Output:
```
niko@Niko-MacBook-Pro dockertest % docker-compose up
[+] Running 2/0
 ⠿ Container example-backend   Created                                                                                                                                          0.1s
 ⠿ Container example-frontend  Created                                                                                                                                          0.1s
Attaching to example-backend, example-frontend
example-backend   | [Ex 2.4+] REDIS_HOST env was not passed so redis connection is not initialized
example-backend   | [Ex 2.6+] POSTGRES_HOST env was not passed so postgres connection is not initialized
example-backend   | [GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.
example-backend   | 
example-backend   | [GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
example-backend   |  - using env:	export GIN_MODE=release
example-backend   |  - using code:	gin.SetMode(gin.ReleaseMode)
example-backend   | 
example-backend   | [GIN-debug] GET    /ping                     --> server/router.pingpong (4 handlers)
example-backend   | [GIN-debug] GET    /messages                 --> server/controller.GetMessages (4 handlers)
example-backend   | [GIN-debug] POST   /messages                 --> server/controller.CreateMessage (4 handlers)
example-backend   | [GIN-debug] Listening and serving HTTP on :8080
example-frontend  | INFO: Accepting connections at http://localhost:5000
example-backend   | [GIN] 2022/02/08 - 19:49:47 | 404 |    1.884891ms |      172.19.0.1 | GET      "/"
example-backend   | [GIN] 2022/02/08 - 19:49:47 | 404 |       17.22µs |      172.19.0.1 | GET      "/favicon.ico"
example-backend   | [GIN] 2022/02/08 - 19:49:51 | 200 |     596.829µs |      172.19.0.1 | GET      "/ping"
```

### 2.4

docker-compose.yml
```
version: '3.8'

services:
    example-frontend:
      image: example-frontend
      build: ./material-applications/example-frontend
      ports: 
        - 5001:5000
      container_name: example-frontend
    example-backend: 
      image: example-backend
      environment:
        - REDIS_HOST=redis
      build: ./material-applications/example-backend
      ports: 
        - 8080:8080
      container_name: example-backend
    redis: 
      image: redis
      container_name: redis
      restart: unless-stopped
```

### 2.5 
```
niko@Niko-MacBook-Pro scaling-exercise % docker-compose up --scale compute=2
```