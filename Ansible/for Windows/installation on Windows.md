## on WSL
after installation of some Linux distro to WSL:
`wsl --install -d [distro_name]`

### use this steps (in example is used Ubuntu package manager )
```
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible -y
```