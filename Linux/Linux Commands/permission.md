## LinuxPermission Code

|           | binary | octal |                                    |
| --------- | ------ | ----- | ---------------------------------- |
| **\-\--** | 000    | 0     | No permission                      |
| **\--x**  | 001    | 1     | Execute-only permission            |
| **-w-**   | 010    | 2     | Write-only permission              |
| **-wx**   | 011    | 3     | Write and execute permission       |
| **r\--**  | 100    | 4     | Read-only permission               |
| **r-x**   | 101    | 5     | Read and execute permission        |
| **rw-**   | 110    | 6     | Read and write permission          |
| **rwx**   | 111    | 7     | Read, write and execute permission |

* * *

## special permissions: the setuid, setgid and sticky bits

### setuid

**setuid** bit is used, the behavior described above it’s modified so that when an executable is launched, it does not run with the privileges of the user who launched it, but with that of the file owner instead. So, for example, if an executable has the setuid bit set on it, and it’s owned by root, when launched by a normal user, it will run with root privileges. It should be clear why this represents a potential security risk, if not used correctly.

### setgid

the **setgid** bit has effect on both files and directories. In the first case, the file which has the setgid bit set, when executed, instead of running with the privileges of the group of the user who started it, runs with those of the group which owns the file: in other words, the group ID of the process will be the same of that of the file.

When used on a directory, instead, the setgid bit alters the standard behavior so that the group of the files created inside said directory, will not be that of the user who created them, but that of the parent directory itself. This is often used to ease the sharing of files (files will be modifiable by all the users that are part of said group). 

### sticky bit

The **sticky bit** works in a different way: while it has no effect on files, when used on a directory, all the files in said directory will be modifiable only by their owners. A typical case in which it is used, involves the /tmp directory. Typically this directory is writable by all users on the system, so to make impossible for one user to delete the files of another one

| setuid | setgid | sticky bits |
| ------ | ------ | ----------- |
| 4      | 2      | 1           |

* * *

https://linuxconfig.org/how-to-use-special-permissions-the-setuid-setgid-and-sticky-bits

* * *

## umask

`umask [-S] [mask]`

#### Options
**-S** 	Accept a symbolic representation of a mask, or return one.
**mask** 	If a valid mask is specified, the umask is set to this value. If no mask is specified, the current umask value is returned.

This table shows how each digit of the umask value affects new file and directory permissions:


         


| umask digit | default file permissions | default directory permissions |
| ----------- | ------------------------ | ----------------------------- |
| 0           | rw                       | rwx                           |
| 1           | rw                       | rw                            |
| 2           | r                        | rx                            |
| 3           | w                        | wx                            |
| 4           | w                        | wx                            |
| 5           | w                        | w                             |
| 6           | x                        | x                             |
| 7           | (no permission allowed)  | (no permission allowed)       |


https://www.computerhope.com/unix/uumask.htm