# RSYNC

  
### Copy to local ###

```sh
rsync -ahPz source/ destination
```

  

### Copy to remote ###

```sh
rsync -ahPz source/ root@x.x.x.x:/destination
```

  

### Sync folders (source is mandatory) ###

```sh
rsync -ahPz --delete source/ root@x.x.x.x:/destination
```