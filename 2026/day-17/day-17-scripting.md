# Day 17 – Shell Scripting: Loops, Arguments & Error Handling

### Task 1: For Loop
1. Create `for_loop.sh` that:
   - Loops through a list of 5 services for linux environment and prints each one

     **Code :**
     ```bash
     #!/bin/bash

     # for loop example

     for i in curl apt nginx docker k8s
     do
          echo $i
     done
     ```

     **Output :**
     ```bash
     curl
     apt
     nginx
     docker
     k8s
     ```
     
2. Create `count.sh` that:
   - Prints numbers 1 to 10 using a for loop

     **Code :**
     ```bash
     #!/bin/bash

     # for loop to count numbers to a limited reange

     for i in 1 2 3 4 5 6 7 8 9 10
     do
          echo $i
     done
     ```

     **Output :**
     ```bash
     1
     2
     3
     4
     5
     6
     7
     8
     9
     10
     ```

---

### Task 2: While Loop
1. Create `countdown.sh` that:
   - Takes a number from the user
   - Counts down to 0 using a while loop
   - Prints "Done!" at the end

     **Code :**
     ```bash
     #!/bin/bash

     read -p "Enter any number: " number
     count=0

     echo "Let the countdown begins...."

     while [ $count -le $number ]
     do
         echo $number
         let number--
     done
     echo "Done!"
     ```

     **Output :**

     Enter any number: 20
     Let the countdown begins....
     20
     19
     18
     17
     16
     15
     14
     13
     12
     11
     10
     9
     8
     7
     6
     4
     3
     2
     1
     0
     Done!
