### Install

To install the openssh-server, you need to install the openssh-server package:

`sudo dnf install -y openssh-server`

### start

To start the sshd daemon (openssh-server) in the current session:

`sudo systemctl start sshd.service`

### stop

To stop the active (if any) sshd daemon in the current session:

`sudo systemctl stop sshd.service`

### enable

To configure the sshd daemon to start automatically at boot time:

`sudo systemctl enable sshd.service`

You will get an output similar to this:

ln -s '/usr/lib/systemd/system/sshd.service' '/etc/systemd/system/multi-user.target.wants/sshd.service'

### disable

To configure the sshd daemon to stop automatic initialization at boot time:

`sudo systemctl disable sshd.service`

/ author: https://bytefreaks.net/gnulinux/fedora-25-install-start-enable-ssh-server /