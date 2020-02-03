# Start or Stop the Services

These commands you must know when you using the Redis of Websoft9

## Docker Compose

```shell
#create containers
sudo docker-compose up
#re-create containers
sudo docker-compose up -d
```

## Docker

```shell
sudo systemctl start docker
sudo systemctl restart docker
sudo systemctl stop docker
sudo systemctl status docker
```

### Redis

Redis have five containers: awx_task, awx_web, awx_rabbitmq, awx_postgre, awx_memcached

```shell
#Redis
sudo docker pause awx_task
sudo docker stop awx_task
sudo docker restart awx_task

#Redis-Web
sudo docker pause awx_web
sudo docker stop awx_web
sudo docker restart awx_web

#Redis-RabbitMQ
sudo docker pause awx_rabbitmq
sudo docker stop awx_rabbitmq
sudo docker restart awx_rabbitmq

#Redis-PostgreSQL
sudo docker pause awx_postgres
sudo docker stop awx_postgres
sudo docker restart awx_postgres

#Redis-Memcached
sudo docker pause awx_memcached
sudo docker stop awx_memcached
sudo docker restart awx_memcached
```