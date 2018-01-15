# Docker-compose

This repository contains a docker-compose file where if you launch It you can create three microservices: 
* Ubuntu 16.04 with nginx
* mariadb 10.1
* php 7.1

Inside file docker-compose.yml you need to change if you want path and is necessary to have into your project:
* a file utils/nginx.conf where you have your custom nginx configuration
* a file utils/default.conf where you have your custom nginx configuration fo sites-available and sites-enabled directories
* a file called .env (you can rename .env.dist from this repo) where you specifiy database connection parameters like this:

```
DB_USER=userdb
DB_PASSWORD=userpwd
DB_NAME=dbname
```

In this way you have your nginx custom configuration and your database parameters.

When you are ready you can launch this command:

```
docker-compose up
```

To stop It you can do this: 

```
docker-compose stop
```

If you want to enter with bash inside a container you need to launch into your CLI:

```
docker ps
``` 

Now you can see three processes: nginx, mariadb, php71.
You need to take the container ID where you want to enter with bash and launch this command:

```
docker exec -it containerID bash
```


This docker compose use those microservices:

* [nginx](https://github.com/studiomado/docker_nginx)
* [mariadb](https://github.com/studiomado/docker_mariadb)
* [php7.1](https://github.com/studiomado/docker_php71)




 