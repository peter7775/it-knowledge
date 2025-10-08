## df

disk available space on mounted filesystems
shows you the size, used space, adn free space on a given disk partition

| options  |                                                                                              |
| -------- | -------------------------------------------------------------------------------------------- |
| k        | list in kilobytes                                                                            |
| m        | list in megabytes                                                                            |
| B *N*    | display siyes in blocks of N bytes (default = 1024)                                          |
| h        | human readable ouptput ( power of 1024)                                                      |
| H        | human readable ouptput ( power of 1000)                                                      |
| l        | display only local filesystem                                                                |
| T        | include the filesystem type in the output                                                    |
| t *type* | display only filesystem of given type                                                        |
| x *type* | don't display filesystem of given type                                                       |
| i        | inode mode; display total, used, and free inodes for each filesystem, instead of disk blocks |

## mount

mounts a device to a location

## umount

unmounts a device



| options |                                                                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| a       | This will unmount all filesystems listed in /etc/fstab.                                                                            |
| f       | This will force the unmounting of a filesystem. This may be useful if you mounted a remote filesystem that has become unreachable. |
| r       | If the filesystem cannot be unmounted, this will try to make it read-only.                                                         |



## mounting MTP devices

https://www.baeldung.com/linux/mounting-mtp-devices

## lsof

lists the processes accessing a filesystem

## lsblk

lists the type and UUID of a filesystem

## fsck

## sync

## partioning and formating disks

## parted

## fdisk

## sfdisk

## mkfs

## floppy