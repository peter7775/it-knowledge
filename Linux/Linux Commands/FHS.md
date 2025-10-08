|          | sharable   | nonsharable |
| -------- | ---------- | ----------- |
| Static   | /usr       | /etc        |
|          | /usr/local | /boot       |
| Variable | /var/mail  | /var/log    |
|          | /home      | /proc       |

* * *

## root filesystem:

- /bin
- /dev
- /etc
- /lib
- /mnt
- /root
- /sbin
- /boot
- /home
- /opt
- /tmp
- /usr
- /var

## /usr filesystem

- /usr/X11R6
- /usr/bin
- /usr/include
- /usr/lib
- /usr/local
- /usr/share
- /usr/src

## /var filesystem

- /var/account
- /var/cache
- /var/crash
- /var/games
- /var/lock
- /var/log
- /var/mail
- /var/opt
- /var/run
- /var/spool
- /var/state
- /var/tmp
- /var/yp

## binary file locations

| Type of file                                    | User commands  | System administration commands |
| ----------------------------------------------- | -------------- | ------------------------------ |
| Vendor-supplied, essential (root fiilesystem)   | /bin           | /sbin                          |
| Vendor-supplied, nonessential (/usr filesystem) | /usr/bin       | /usr/sbin                      |
| Locally supplied (/usr filesystem)              | /usr/local/bin | /usr/local/sbin                |

* * *

https://www.pathname.com/fhs/