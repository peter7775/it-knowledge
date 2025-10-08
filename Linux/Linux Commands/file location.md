## find

`find [options] [path...] [expression]`

- The *options* attribute controls the treatment of the symbolic links, debugging options, and optimization method.
- The *path...* attribute defines the starting directory or directories where find will search the files.
- The *expression* attribute is made up of options, search patterns, and actions separated by operators.

### Find Files by Name
`find /home/linuxize -type f -name document.pdf`
`find /home/linuxize -type f -iname document.pdf` (no case senstive)

### Find Files by Extension
`find /var/log/nginx -type f -name '*.log.gz'`

### Find Files by Type
- f: a regular file
- d: directory
- l: symbolic link
- c: character devices
- b: block devices
- p: named pipe (FIFO)
- s: socket

`find . -type d`

### Find Files by Size
- b: 512-byte blocks (default)
- c: bytes
- w: two-byte words
- k: Kilobytes
- M: Megabytes
- G: Gigabytes
- 
`find /tmp -type f -size 1024c`

### Find Files by Modification Date
`find /etc/dovecot/conf.d -name "*.conf" -mtime 5`
`find /home -mtime +30 -daystart`

### Find Files by Permissions
`find /var/www/html -perm 644`

### Find Files by Owner
`find / -user linuxize`
`find / -user www-data -type f  -exec chown nginx {} \;`


### Find and Delete Files
`find /var/log/ -name `*.temp` -delete`

https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/


## locate
## slocate
## which
## type
## whereis