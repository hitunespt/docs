# LVM disks


#### LVM structure:


![](https://github.com/hitunespt/docs/blob/b258b484d193447e298b122379440b95a6df441b/misc/images/lvm_structure.png)


&nbsp;
###### Create disk on vmware:

![](misc/images/vmware_create_disk.png)

List the block device to see the newly assigned vSphere hard disk

```sh
lsblk
```

Format the disk partition. Get the device name from the previous lsblk output

```sh
fdisk /dev/sdb
```

Create a new partition

```sh
n (new partition)

p (primary)

(Press ENTER) (Use default partition number)

(Press ENTER) (Use default first sector)

(Press ENTER) (Use default last sector)

t (change the partition type)

8e (Linux LVM)

w (write)
```

Initialize the physical volume

```sh
pvcreate /dev/sdb1
```

Create the volume group

```sh
vgcreate vgData /dev/sdb1
```

Create the logical volume for the volume group

```sh
lvcreate -n lvData -l +100%FREE vgData
```

Construct an XFS filesystem on the new logical volume

```sh
mkfs.xfs /dev/vgData/lvData
```

Mount a Unix directory to the logical volume
Edit the text file /etc/fstab and add the line below:

```
/dev/vgData/lvData     /data               xfs     defaults        0 0
```

Create directory
```sh
mkdir -p /data
```

Mount directory
```sh
mount /data
```

Display the new directory
```sh
df -h
```
