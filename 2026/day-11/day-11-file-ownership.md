# Day 11 – File Ownership Challenge (chown & chgrp)
___________________________________________________

### Task 1: Understanding Ownership

Check the owner and group of files & directories in your home directory.                       
$ ls -l

What's the difference between owner and group?

In Linux, the owner is a single specific user account, while a group is a collection of user accounts. Every file and directory is assigned both an owner and a single associated group, and separate permissions (read, write, execute) are defined for each. 

___

### Task 2: Basic chown

Create file `devops-file.txt`                       
$ touch devops-file.txt
 
Check current owner.                              
$ ls -l devops-file.txt

Change owner to `tokyo`                            
$ sudo chown tokyo devops-file.txt

Change owner to `berlin`                            
$ sudo chown berlin devops-file.txt

Verify the changes                                  
$ ls -l devops-file.txt

___

