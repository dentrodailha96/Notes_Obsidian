# Server 

## General Information 
- lsb_release -a : see which Linux distro and version you're using
- uname -a : system info and shows some informations like kernel version, hardware platform
- uptime : how long the system has been running
- whoami : user names logged
- w : what the user name logged is doing

## Hardware info
- lshw: detailed information on the hardware config.
- lscpu: info about CPU architecture
- lsblk: list block devices
- lspci: list PCI devices
- lsusb: list USB devices

## Memory
- free -h.vmstat : memory stats
- top/htop: task manager Linux

## Disk Usage
- df -h : disk space 
- du -h: if you want to estimate the size of the folders.

## Networking
- ifconfig / ip address: get the ip address from the server
- netstat -i : static view 
- ifstat : continuous view
- sudo iftop -i eth0 : nice display from the info above. 

### SadServers challenge Bucharest
- Problem of connecting to the PostgreSQL 13: https://github.com/mrmac189/sadservers-solutions/blob/main/solutions/7_Bucharest.md (solution)
	- The difference was to comment the connections above to the one that I added.

