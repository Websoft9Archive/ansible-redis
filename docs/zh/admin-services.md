# 服务启停

使用由Websoft9提供的Redis部署方案，可能需要用到的服务如下：

### Redis

```shell
sudo systemctl start redis
sudo systemctl stop redis
sudo systemctl restart redis
sudo systemctl status redis
```

### RedisInsight

```shell
sudo systemctl start redisinsight
sudo systemctl stop redisinsight
sudo systemctl restart redisinsight
sudo systemctl status redisinsight
```

### Nginx

```shell
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```