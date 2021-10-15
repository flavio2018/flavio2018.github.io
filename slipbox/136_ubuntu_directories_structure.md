# File system structure in Ubuntu
<p style= "text-align: right"><i>Created 09/09/2021</i></p>

## About `/`
[Source 1](https://help.ubuntu.com/lts/installation-guide/armhf/apcs02.html)
[Source 2](https://ubuntuforums.org/showthread.php?t=2037324)

- the `/bin` folder contains standard utilities such as `cp`, `grep`, `ls`
- the `/sbin` folder contains system administration utilities that should be run with super user permissions, such as `reboot`, `ifconfig`
- the `/etc` folder contains configuration files for installed programs; most of them are editable text files
- `/proc` and `/var` are both used to manage the execution of programs when the system is up and running
- `/usr` contains files and programs installed by the user
- in `/lib` there are libraries that are shared between programs and are dynamically linked 

## About the various `bin` folders
[Source 1](https://unix.stackexchange.com/questions/8656/usr-bin-vs-usr-local-bin-on-linux)
[Source 2](https://askubuntu.com/questions/138547/how-to-understand-the-ubuntu-file-system-layout)

- `/bin` is for system utilities that should be available *before `/usr` is mounted*
- `/usr/bin` is for programs that are installed via the system packet manager (e.g. `apt`)
- `/usr/local/bin` is for programs that are installed by the user *without* using the packet manager, e.g. compiling binaries

## About `/usr/local` and `/usr/shared`
[Source 1](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)

- `/usr/share` contains files that are shared among the different users, whereas
- `/usr/local` contains files that are local to one host