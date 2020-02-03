# Initial Installation

If you have completed the Redis deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:80 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for Redis

## Redis Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://domain name* or *http://Internet IP*, you will log in interface of Redis
   ![Redis login page](https://libs.websoft9.com/Websoft9/DocsPicture/en/awx/awx-login-websoft9.png)

2. Login it[（不知道账号密码？）](/zh/stack-accounts.md#awx)
   ![Redis console](https://libs.websoft9.com/Websoft9/DocsPicture/en/awx/awxui-websoft9.png)

3. Create alls need for one installation Template：

   - ORGANIZATIONS
   - Credentials
   - Inventories
   - Project

   Then, create Template and your have completed one automatic installation of AWS now

   ![Redis template](https://libs.websoft9.com/Websoft9/DocsPicture/en/awx/awx-template-websoft9.png)


4. Start a job by Template, the deployment is starting
   ![Redis job](https://libs.websoft9.com/Websoft9/DocsPicture/en/awx/awx-job-websoft9.png)

> More useful Redis guide, please refer to [Ansible Tower Documentation](https://docs.ansible.com/ansible-tower/)

## Q&A 

#### I can't visit the start page of Redis?

Your TCP:80 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Which database does this Redis use?

PostgreSQL on Docker