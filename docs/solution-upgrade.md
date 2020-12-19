# Update & Upgrade

Updates and upgrades are one of the maintenance tasks for system. Programs that are not upgraded for a long time, like buildings that are not maintained for a long time, will accelerate aging and gradually lose functionality until they are unavailable.

You should know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
- Operating system patching is **Update**, Ubuntu16.04 to Ubuntu18.04 is **Upgrade**
- Redis5.0.1 to Redis5.0.5 is **Update**, Redis5.0 to Redis6.0 is **Upgrade**

For Redis maintenance, focus on the following two Update & Upgrade jobs

- Sytem update(Operating System and Running Environment) 
- Redis upgrade 

## System Update

Run an update command to complete the system update:

``` shell
#For Ubuntu
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y
```
> This deployment package is pre-configured with a scheduled task for automatic updates. If you want to remove the automatic update, please delete the corresponding Cron

## Redis Upgrade

There's not need to upgrade under the version 5.0.x. 

How upgrade from Redis 5.0 to 6.0? we suggest you install 6.0 to replace 5.0:

1. Backup Redis configuration files

2. Run this shell to reinstall Redis
   ```
   wget -N https://raw.githubusercontent.com/Websoft9/ansible-linux/main/scripts/install.sh; bash install.sh -r redis
   ```
3. Restore backup configuration file

4. Fix the if need
