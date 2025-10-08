### copy files from your local machine to the remote machine

`rsync filename username@ip_address:/home/username`

### copy files from the remote machine to your local machine


`rsync username@ip_address:/home/username/filename .`

### copying directories with rsync

`rsync -r source_dir username@ip_address:/home/username/target_dir`

### rsync using for NAS server
https://linuxhint.com/use-rsync-synology-nas/