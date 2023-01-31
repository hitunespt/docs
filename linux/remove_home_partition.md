# Remove home partition

unmount home partition
```sh
umount /home
```

Remove the home partiton 
```sh
lvm lvremove /dev/mapper/ol-home
```

Increase the space to /root partition
```sh
lvm lvresize -l +100%FREE -r /dev/mapper/ol-root
```

Remove the line on fstab for the home partition
```sh
vim /ect/fstab
```


