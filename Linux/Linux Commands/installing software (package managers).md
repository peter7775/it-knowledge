## dnf
(od verze Fedora 22)



### search the repositories for a package type

`sudo dnf search packagename`

### install the package

`dnf install packagename`

### remove a package

`dnf remove packagename`

#### removes packages installed as dependencies that are no longer required by currently installed programs

`dnf autoremove`

#### checks for updates, but does not download or install the packages

`dnf check-update` 

#### reverts to the previous version of a package

`dnf downgrade`

#### provides basic information about the package including name, version, release, and description

`dnf info`

#### reinstalls the currently installed package

`dnf reinstall` 

#### checks the repositories for newer packages and updates them
`dnf upgrade`

#### exclude a package from the transaction
`dnf exclude` 

### install core plugins
`dnf install dnf-plugins-core-PLUGIN_NAME`
([documentation for core plugins](https://dnf-plugins-core.readthedocs.io/en/latest/))

### install extra plugins
`dnf install dnf-plugins-extras-PLUGIN_NAME`
([documentation for extra plugins](https://dnf-plugins-extras.readthedocs.io/en/latest/))

### dnf version lock
`sudo dnf install 'dnf-command(versionlock)'`

use:


```
sudo dnf versionlock add <package-name-spec>
sudo dnf versionlock delete <package-name-spec>
sudo dnf versionlock list
sudo dnf versionlock clear    # Removes all versionlocks
sudo dnf versionlock exclude  # Also possible here
```


### references

- [DNF Command Reference](https://dnf.readthedocs.io/en/latest/command_ref.html)
- [DNF wiki](https://github.com/rpm-software-management/dnf/wiki)
- [DNF VersionLock](https://dnf-plugins-core.readthedocs.io/en/latest/versionlock.html)



* * *
# rpm

#### find package
`rpm -q package_name`

#### list the files included in installed package
`rpm -ql package_name`

#### get information about package
`rpm -gi package_name`

#### list the contents of a rpm file
`rpm -glp package.rpm`

#### list all installed rpm packages
`rpm -qa`

### install package
`rpm -ivh package1.rpm package2.rpm ...`

### update package
`rpm -Fvh package1.rpm package2.rpm ...`

### delete package
`rpm -e package_names`
* * *
# yum