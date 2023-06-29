# FileBrowser

```sh
curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash
```


```sh
mkdir -p /etc/filebrowser
```

  
```sh
vi /etc/filebrowser/filebrowser.json
```


```txt
{
  "port": 8080,
  "baseURL": "",
  "address": "xx.xx.xx.xx",
  "log": "stdout",
  "database": "/etc/filebrowser/filebrowser.db",
  "root": "/var/www/"
}
```


```sh
vi /etc/systemd/system/filebrowser.service
```


```txt
[Unit]
Description=File Browser
After=network.target

[Service]
User=nginx
Group=nginx
ExecStart=/usr/local/bin/filebrowser -c /etc/filebrowser/filebrowser.json

[Install]
WantedBy=multi-user.target
```

  
```sh
systemctl enable --now filebrowser.service
```

```sh
cd /etc/filebrowser/
chown nginx:nginx *.*
```

```sh
systemctl restart nginx
```
