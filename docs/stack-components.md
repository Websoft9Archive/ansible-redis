# Parameters

The Redis deployment package contains a sequence software (referred to as "components") required for Redis to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### Redis

Run the command `sudo docker volume ls` to list all volumes: 

awx_postgres volume mount: */var/lib/postgresql/data*  
awx_rabbitmq volume mount: */var/lib/rabbitmq*  
awx_web volume mount: */var/lib/nginx*   
awx_task volume mount: */var/lib/nginx* 	

### Other

no other components now

## Ports

These Ports is need when use Redis, refer to [Safe Group Setting on Cloud Console](https://support.websoft9.com/docs/faq/tech-instance.html)

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| Redis | 6379 | Remote connect Redis | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Linux Version
lsb_release -a

# Python Version
redis -v
```