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
