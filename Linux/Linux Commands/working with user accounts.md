## useradd

#### Create a New User and Assign Groups in One Command
`sudo useradd -g users -G wheel,developers nathan`

## userdel
## usermod
#### Add an Existing User to a Group
`sudo usermod -a -G groupname username`

#### Add an Existing User to Multiple Groups in One Command

`sudo usermod -a -G group1,group2 username`

#### Change a User’s Primary Group 
`sudo usermod -g groupname username`
## passwd

## gpasswd
#### Remove a User From a Group
 
 `sudo gpasswd -d username groupname`
## chfn
## chsh

## id
#### Display User Groups
`id username`

## groups
#### Display User Groups
`groups linuxize`

* * *
[https://linuxize.com/post/how-to-add-user-to-group-in-linux/#display-user-groups](https://linuxize.com/post/how-to-add-user-to-group-in-linux/#display-user-groups)