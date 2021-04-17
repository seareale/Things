# mount_linux_to_window

## Install
1. WinFsp - [download](https://github.com/billziss-gh/winfsp/releases/latest)  
2. SSFHS-Win - [download](https://github.com/billziss-gh/sshfs-win/releases/latest)  

## Run
```bash
$ net use [DRIVE CHAR]:\\sshfs\[USER ID]@[IP ADDRESS]![PORT]\[DIR] /user:[USER ID]

# additional
$ mklink /d "D:\test" "E:"  # link 'E:' to 'D:\test'
```
ex) `$ net use E:\\sshfs\admin@000.000.000.000!80\sample /user:admin`

## Unmount
```bash
$ net use E: /delete

# additional
$ rmdir D:\test  # remove link
```

## linux to linux
```bash
$ sudo sshfs -o allow_other -p [PORT] [USER ID]@[IP ADDRESS]:[FULL PATH] [LOCAL FULL PATH]

# unmount
$ sudo fusermount -u [LOCAL FULL PATH]
```
ex) `$ sudo sshfs -o allow_other -p 80 admin@000.000.000.000:/home/admin/test /home/user/mount`
