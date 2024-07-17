# fstab 

This is generally the same for every Linux distro.

If there are drives that do not auto-mount on boot, they will need to be pointed out in the fstab.

To begin, use `lsblk -f` to list the available drives and their information, such as mountpoints and UUID.

`nano /etc/fstab`

```cs
#drive 1

UUID=<paste UUID>   <directory path>    <filesystem>    defaults,noatime    0 2

#drive 1 example
UUID=6789feas-fbf3-2de3-8dh1-ss73287hsa0    /run/media/taulant/drive1   ext4    defaults,noatime    0 2
```

