Today’s goal is to practice Linux fundamentals with real commands.

Check running processes , try a commannd and check the PID of it & kill it:

• ps: Displays a snapshot of current processes.

o ps aux: Show all processes running on the system in a detailed format.

o ps -ef: An alternative full-format listing style.

o ps -u ubuntu: List processes owned by ubuntu user.

• top: Provides a real-time, dynamic view of running processes and system resource usage (CPU, memory, etc.).

• htop: An interactive, enhanced alternative to top with a user-friendly interface.

• pstree: Displays processes in a tree format, showing parent-child relationships.

•	ping google.com: This will create a process ID.

•	ps aux | grep ping: It will fetch the PID of ping.

• kill -9 <PID>: To kill a running process.
-------------------------------------------------------------------------------------------------------------------------------------------

Inspecting a service (Ex: nginx):

•	sudo apt-get install nginx: To install nginx.

•	systemctl status nginx: To check the current status of nginx, that is active by default after installation.

•	sudo systemctl stop nginx: To stop the service of nginx.

•	sudo systemctl start nginx: It will the service gain.

•	Journalctl -u nginx: To check the logs of the service.
