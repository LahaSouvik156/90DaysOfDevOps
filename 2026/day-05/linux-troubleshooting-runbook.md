Today’s goal is to run a focused troubleshooting drill.
-------------------------------------------------------------------------------------------------------------------------------------------

1. Capture a quick health snapshot (OS, CPU, memory, disk, network):

•	uname : It shows the current name of the OS

•	uname -r : It shows the version of the kernal

•	cat /etc/os-release : It shows the current version/ release of the OS

•	lscpu :  This command is the primary utility for displaying CPU architecture information in a clean, human-readable format. It gathers its data from the /proc/cpuinfo and sysfs files.

•	Cat /proc/cpuinfo : This virtual file contains detailed information about each logical CPU core on the system, including the vendor ID, model name, clock speed (MHz), cache size, and supported features (flags).

•	Free -h : This will show the ram info of the system.

•	Df -h : This will show the memory device related info.

 ** But top and htop command are mainly used to check, which process consume how much CPU% ,MEM% **

•	Cat /etc/hosts : Displays the content of the local host files in linux, showing mapping of IP address to hostnames.

•	ss -tulpn: The ss -tulpn command is the modern, faster successor to the classic netstat. It is used to investigate network connections, sockets, and ports on a Linux system.

Breakdown of the Flags:

Each letter in -tulpn acts as a filter to refine the output:

Flag	Meaning	Description

-t	TCP	Displays TCP sockets.

-u	UDP	Displays UDP sockets.

-l	Listening	Shows only sockets currently listening for incoming connections.

-p	Processes	Shows the Process ID (PID) and name of the program using the socket.

-n	Numeric	Prevents resolving IP addresses/ports to names (e.g., shows 80 instead of http), making the command faster.

-------------------------------------------------------------------------------------------------------------------------------------------

2. Trace logs for that service:

journalctl -u docker: It will show the logs of the docker

-------------------------------------------------------------------------------------------------------------------------------------------

3. Add a 1–2 line note on what you observed (e.g., “CPU spikes to 80% when restarting”, “No recent errors in last 50 lines”).

First we must check which are processes currently running in the system. If there is any unnecessary process or stopped process that still consuming the CPU usage then we can kill  that process to reduce the CPU usage.








