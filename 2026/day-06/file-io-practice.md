# Day 06 – Linux Fundamentals: Read and Write Text Files

Today’s goal is to practice basic file read/write using only fundamental commands.
-------------------------------------------------------------------------------------
1. Create a file named notes.txt

     $ touch notes.txt

2. Write 3 lines into the file using redirection (> and >>)

     $ echo "This is a demo file (added first line)" > notes.txt
 
     $ echo "Added 2nd Line" >> notes.txt
 
     $ echo "Added 3rd Line" >> notes.txt

3. Use tee once to write and display at the same time

     $ echo "Added something new" | tee -a notes.txt

     Also added a something to the file with the help of vim editor.

5. Command to check the ouput of that file

     $ cat notes.txt

6. Use head and tail to read parts of the file

     $ head -n 2 notes.txt
     $ tail -n 2 notes.txt
