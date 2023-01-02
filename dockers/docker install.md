# Docker install on Oracle Linux 9

Run updates:
```sh
yum update -y
```

&nbsp;
### Add Docker Repository to Oracle Linux 9

Use the **yum-config-manger** tool to add docker repo in Oracle Linux 9
```sh
yum install -y yum-utils
```

```sh
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

&nbsp;
### Remove existing Docker Engine before proceeding with installation

```sh
yum remove docker docker-* podman runc
```

```sh
yum install docker-ce docker-ce-cli containerd.io
```

&nbsp;
### Start and enable Docker

```sh
systemctl start docker
```

```sh
systemctl enable docker
```

&nbsp;
### Run Docker Commands as Non-Root User

```sh
sudo usermod -aG docker $USER

newgrp docker
```


$nbsp;
### Install docker compose

```sh
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```sh
chmod +x /usr/local/bin/docker-compose
```

```sh
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

```sh
docker-compose --version
```



