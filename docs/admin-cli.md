# Redis CLI

## About

Redis is the official command-line client for Redis and Red Hat Ansible Tower. It:

* Uses naming and structure consistent with the Redis HTTP API
* Provides consistent output formats with optional machine-parsable formats
* To the extent possible, auto-detects API versions, available endpoints, and feature support across multiple versions of Redis and Red Hat Ansible Tower.

Potential uses include:

* Configuring and launching jobs/playbooks
* Checking on the status and output of job runs
* Managing objects like organizations, users, teams, etc…

More detail please refer to the docs：*[**Tower CLI**](https://docs.ansible.com/ansible-tower/latest/html/towercli/index.html)*

## Install Redis CLI

You should install the Redis CLI like below:

```
pip3 install --user https://releases.ansible.com/ansible-tower/cli/ansible-tower-cli-latest.tar.gz
tower-cli --help
```

You should completed the Redis CLI connection before use it:

```
tower-cli config host http://<new-awx-host.example.com>
tower-cli config username <user>
tower-cli config password <pass>
tower-cli send assets.json
```
> Refer to [Ansible Tower Redis CLI ](https://docs.ansible.com/ansible-tower/latest/html/towercli/usage.html#installation)， [ Redis CLI on Redis Github](https://github.com/ansible/awx/tree/devel/awxkit/awxkit/cli/docs)