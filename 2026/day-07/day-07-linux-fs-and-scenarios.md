1. Linux File System Hierarchy:
   -------------------------------

In linux everything is represented as a file (including a hardware program), the files are stored in a directory and every directory contains a file with a tree structure. This is called Filed System Hierarchy.
Linux uses single rooted, inverted tree-like structure. Root directory represents with /(forward slash). It is a top level directory in linux.

Key Top-Level Directories:

•	/ (Root): The base of Linux is Root directory. This is the starting point of FSH. Every directory arises from the root directory. It is represented by forward slash (/). 

•	/root: This is the home directory for the root user (administrator).

•	/bin & /usr/bin: Essential command binaries and executable programs.

•	/sbin & /usr/sbin: System binaries for administrative tasks (system administration).

•	/etc: System-wide configuration files.

•	/home: User personal directories (documents, downloads).

•	/var: Variable data, including logs (/var/log), mail, and databases.

•	/usr: User programs, libraries, and documentation.

•	/dev: Device files, representing hardware like hard drives.

•	/proc: Virtual filesystem containing process and kernel information.

•	/tmp: Temporary files, often cleared on reboot.

•	/boot: Files needed for booting the system, including the kernel.

•	/lib & /lib64: Essential shared libraries for binaries.

•	/opt: Third-party software packages.

•	/media: Mount points for removable media (USB drives).

•	/mnt: Temporary mount points for filesystems.

•	/run: Volatile runtime data, such as process IDs, created since boot.

•	/sys: Virtual filesystem allowing modification of device information.

_______________________________________________________________________________________________________________________________________________________________

2. How do you check if the 'nginx' service is running?

 systemctl status nginx (To check the status of the service)

 systemctl list-units --type=service (If service not found then check for all ervices)

 systemctl is-enabled nginx (To check if service is enabled on boot)
