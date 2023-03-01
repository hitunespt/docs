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
ExecStart=/usr/local/bin/filebrowser -c /etc/filebrowser/filebrowser.json

[Install]
WantedBy=multi-user.target
```

  
```sh
systemctl enable --now filebrowser.service
```
