### connect:
`lftp -u ftp206263,milli789 -p 222 sftp://millijanatkova.com`


### for put site to known host, connect to server by **ssh**:
`ssh -p 222 ftp206263@millijanatkova.com`

### show current directory on FTP server
`lftp fedora@www.srv.world:~> pwd`

### show current directory on localhost
`lftp fedora@www.srv.world:~> !pwd`


### show files in current directory on FTP server
`lftp fedora@www.srv.world:~> ls`

### show files in current directory on localhost
`lftp fedora@www.srv.world:~> !ls -l`

### change directory
```
lftp fedora@www.srv.world:~> cd public_html
lftp fedora@www.srv.world:~/public_html> pwd
```

### upload a file to FTP server
 [-a] means ascii mode ( default is binary mode )
`lftp fedora@www.srv.world:~> put -a redhat.txt`


### upload some files to FTP server
`lftp fedora@www.srv.world:~> mput -a test.txt test2.txt`

### set permission to overwite files on localhost when using [get/mget]
`lftp fedora@www.srv.world:~> set xfer:clobber on` 

### download a file to localhost
 [-a] means ascii mode ( default is binary mode )
```
lftp fedora@www.srv.world:~> get -a test.py
```

### download some remote files to localhost
`lftp fedora@www.srv.world:~> mget -a test.txt test2.txt`


### remove a directory on remote current directory
`lftp fedora@www.srv.world:~> rmdir testdir`

### remove a remote file
`lftp fedora@www.srv.world:~> rm test2.txt`


### remove some remote files
`lftp fedora@www.srv.world:~> mrm redhat.txt test.txt`

### execute commands with ![command]
`lftp fedora@www.srv.world:~> !cat /etc/passwd`

### exit
`lftp fedora@www.srv.world:~> quit`
* * *
https://www.server-world.info/en/note?os=Fedora_32&p=ftp&f=4
* * *