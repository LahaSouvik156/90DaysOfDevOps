Today’s goal is to create a cheetsheet of PROCESS MANAGEMENT, FILE SYSTEM and NETWORKING

Deatlaied discussion of commands focused on:

1. Process management:

Monitoring & Viewing Processes:
---------------------------------
•	ps: Displays a snapshot of current processes.

  o	ps aux: Show all processes running on the system in a detailed format.
  
  o	ps -ef: An alternative full-format listing style.
  
  o	ps -u <user>: List processes owned by a specific user.
  
•	top: Provides a real-time, dynamic view of running processes and system resource usage (CPU, memory, etc.).

•	htop: An interactive, enhanced alternative to top with a user-friendly interface.

•	pstree: Displays processes in a tree format, showing parent-child relationships.

•	pidof <process_name>: Returns the Process ID (PID) of a named process.

•	watch -n 1 'ps aux': Executes ps aux every second, updating the display in real time. 

-------------------------------------------------------------------------------------------------------------------------------------------

Killing a Processes:
--------------------------------------
•	kill <pid>: Sends a signal to a process identified by its PID (Process ID).

  o	kill -9 1234 or kill -SIGKILL 1234: Forcefully terminates a process (cannot be ignored by the process).

-------------------------------------------------------------------------------------------------------------------------------------------

Inspecting Process Details:
-----------------------------
•	strace -p <pid>: Traces the system calls made by a process (useful for debugging).

•	lsof -p <pid>: Lists the files opened by a specific process.

•	cat /proc/<pid>/status: Displays detailed information about a process from the /proc filesystem. 

-------------------------------------------------------------------------------------------------------------------------------------------

2. File Management:

•	ls	:        List files and directories

•	ls -l :      Long list of files and directories

•	ls -a:       To see hidden files and directories

•	cd	:        Change directory

•	cp	 :       Copy files and directories

•	mv	:        Move (rename) files and directories

•	rm	:        Remove files and directories

•	mkdir	:      Create directories

•	rmdir	 :     Remove empty directories

•	touch	 :     Create an empty file or update the timestamp of an existing file

•	chmod	:      Change permissions for files and directories

•	chown	:      Change ownership of files and directories

•	find	:      Search for files and directories based on various criteria

•	locate	:    Find files and directories by name

•	grep	 :     Search for patterns in files

•	head	 :     Display the first few lines of the file

•	tail	  :    Display the last few lines of the file

•	cat	   :     Concatenate and display files

•	more	 :     Display the contents of the file one screen at a time

•	less	 :     Display the contents of the file one screen at a time, with more advanced features

•	tar	  :      Create or extract tar archives

•	gzip	 :     Compress or decompress files using gzip compression

-------------------------------------------------------------------------------------------------------------------------------------------

3. Basic Networking Commands:

•	ip addr show:	    Display IP address and interface details	{ example:ip addr show eth0 }

•	ifconfig:   View/configure network interfaces	{ ifconfig eth0 }

•	ping	:        Test reachability to a host	{ ping google.com }

•	tracerout :Show the path packets take to a destination	{ traceroute google.com }

•	curl or wget:	Test application layer (HTTP/HTTPS) connectivity	{ curl -I https://google.com }

•	dig:	Advanced DNS lookup tool	{ dig example.com }

•	nslookup:	Basic DNS query utility	{ nslookup example.com }

•	cat /etc/resolv.conf:	View configured DNS servers	{ cat /etc/resolv.conf }

