Day 10 – File Permissions & File Operations Challenge
_______________________________________________________

Task 1: Create Files 

1. Create empty file devops.txt using touch                                     
   $ touch devops.txt

2. Create notes.txt with some content using cat or echo                                                
   $ echo "This is notes file" > note.txt

3. Create script.sh using vim with content: echo "Hello DevOps"                                   
   $ vim script.sh : after that we can write bash command inside the file.

________________________________________________________________________________________________________________________________________________________________

Task 2: Read Files

1. Read notes.txt using cat                               
   $ cat notes.txt

2. View script.sh in vim read-only mode                      
   $ cat script.sh

3. Display first 5 lines of /etc/passwd using head                   
   $ cat /etc/passwd | head -n 5

4. Display last 5 lines of /etc/passwd using tail                
   $ cat /etc/passwd | tail -n 5

______________________________________________________________________________________________________________________________________________________________

Task 3: Understand Permissions

Check your files: ls -l devops.txt notes.txt script.sh

1. What are current permissions? Who can read/write/execute? 

   => In all 3 files Owner and Group has read and write permission. Other user has read permission.

_______________________________________________________________________________________________________________________________________________________________

Task 4: Modify Permissions

1. Make script.sh executable → run it with ./script.sh
   $ sudo chmod 740 script.sh : after that run it with ./script.sh

2. Set devops.txt to read-only (remove write for all)
   $ sudo chmod 444 devops.txt

3. Set notes.txt to 640 (owner: rw, group: r, others: none)
   $ sudo chmod 640 notes.txt

______________________________________________________________________________________________________________________________________________________________

Task 5: Test Permissions

1. Try writing to a read-only file - what happens?

   => If you try to write some content in a read-only file then it will throw some error. (screenshot attached)

2. Try executing a file without execute permission
   
   => We can execute a file without execute permission by using bash command. i.e. $ bash Hello.sh
