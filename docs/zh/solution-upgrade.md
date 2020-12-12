# 更新升级

网站技术日新月异，**更新升级**是维护工作之一，长时间不升级的程序，就如长时间不维护的建筑物一样，会加速老化、功能逐渐缺失直至无法使用。  

这里注意更新与升级这两词的差异（[延伸阅读](https://support.websoft9.com/docs/faq/zh/tech-upgrade.html#更新-vs-升级)），例如：
- 操作系统打个补丁常称之为**更新**，Ubuntu16.04 变更为 Ubuntu18.04，称之为**升级**
- Redis5.0.1-->Redis5.0.5 常称之为**更新**，Redis5.0->Redis6.0 称之为**升级**

Redis 完整的更新升级包括：系统级更新（操作系统和运行环境）和 Redis 程序升级两种类型

## 系统级更新

运行一条更新命令，即可完成系统级更新：

``` shell
#For Ubuntu
apt update && apt upgrade -y

#For Centos&Redhat
yum update -y
```
> 本部署包已预配置一个用于自动更新的计划任务。如果希望去掉自动更新，请删除对应的Cron


## Redis升级

除了 Redis 5.0 以上版本之外，Redis已经是各个发行版的最新版本。

如何更新 Redis 5.0  到 Redis 6.0 ？ 由于 Redis 安装简单，因此大版本的升级，我们建议采用重装的方式

1. 备份 Redis 配置文件
2. 运行下面的命令重装 Redis
   ```
   wget -N https://raw.githubusercontent.com/Websoft9/ansible-linux/main/scripts/install.sh; bash install.sh -r redis
   ```
3. 还原备份配置文件
