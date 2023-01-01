# Docker install on Oracle Linux 9

Run updates:
```sh
yum update
```
``
### Add Docker Repository to Oracle Linux 9

Use the **yum-config-manger** tool to add docker repo in Oracle Linux 9
```sh
yum install -y yum-utils
```

```sh
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
