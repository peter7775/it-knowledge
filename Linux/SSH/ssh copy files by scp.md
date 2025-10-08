### copy files from the remote machine to your local machine

`scp username@ip_address:/home/username/filename .`

### copy files from your local machine to the remote machine

`scp filename username@ip_address:/home/username`

### copy directoriescopy directories

`scp -r source_dir username@ip_address:/home/username/target_dir`