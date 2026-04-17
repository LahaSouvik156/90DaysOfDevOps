# Day 16 – Shell Scripting Basics

### Task 1: Your First Script
1. Create a file `hello.sh`
   - Add the shebang line `#!/bin/bash` at the top
   - Print `Hello, DevOps!` using `echo`
   - Make it executable and run it
   
   Command to create file `hello.sh`: vim hello.sh
   
   **Code:**
   ```bash
   #!/bin/bash

   echo "Hello, DevOps!"
   ```

   Command to execute the script: bash hello.sh
   
   **Output** : Hello, DevOps!

---

### Task 2: Variables
1. Create `variables.sh` with:
   - A variable for your `NAME`
   - A variable for your `ROLE` (e.g., "DevOps Engineer")
   - Print: `Hello, I am <NAME> and I am a <ROLE>`

   Command to create file `variables.sh` : vim variables.sh

   **Code:**
   ```bash
   #!/bin/bash

   # Script to usage of variable

   NAME=Ethen
   ROLE=Agent

   echo "Hello, I am $NAME and I am a $ROLE"
   ```

   **Output** : Hello, I am Ethen and I am a Agent
     
 ---

### Task 3: User Input with read
1. Create `greet.sh` that:
   - Asks the user for their name using `read`
   - Asks for their favourite tool
   - Prints: `Hello <name>, your favourite tool is <tool>`

   Command to create file `greet.sh` : vim greet.sh

   ** code:**
   ```bash
   #!/bin/bash

   # Script for user input with read

   read -p "Enter your name: " name
   read -p "Enter your favourite tools name: " tool

   echo "Hello $name, your favourite tool is $tool"
   ```

   **Output:**
   ```bash
   Enter your name: Jason
   Enter your favourite tools name: k8s
   Hello Jason, your favourite tool is k8s
   ```
---

### Task 4: If-Else Conditions
1. Create `check_number.sh` that:
   - Takes a number using `read`
   - Prints whether it is **positive**, **negative**, or **zero**

   Command to create file `check_number.sh` : vim check_number.sh

   **Code:**
   ```bash
   #!/bin/bash
   
   read -p "Enter any number: " number

   if [ $number -eq 0 ];
   then
         echo "The number is 0"
   elif [ $number -ge 1 ];
   then
         echo "The number is positive"
   else
         echo "The number is negative"
   fi
   ```

   **Output**
   ```bash
   Enter any number: 20
   The number is positive
   Enter any number: -10
   The number is negative
   Enter any number: 0
   The number is 0
   ```

2. Create `file_check.sh` that:
   - Asks for a filename
   - Checks if the file **exists** using `-f`
   - Prints appropriate message

   Command to create file `file_check.sh` : vim file_check.sh
   
   **Code**
   ```bash
   #!/bin/bash
   
   if [ -f /etc/passwd ];
   then
         echo "File exists"
   else
         echo ""File doesn't exist"
   fi
   ```

---

### Task 5: Combine It All
Create `service_check.sh` that:
1. Stores a service name in a variable (e.g., `nginx`, `sshd`)
2. Asks the user: "Do you want to check the status? (y/n)"
3. If `y` — runs `systemctl status <service>` and prints whether it's **active** or **not**
4. If `n` — prints "Skipped."

   Command to create file `service_check.sh` : vim service_check.sh

   **Code**
   ```bash
   #!/bin/bash
   
   # Store service name in a variable
   
   SERVICE="nginx"

   # Ask the user
   
   read -p "Do you want to check the status of $SERVICE? (y/n): " confirm

   # Conditional logic
   
   if [[ $confirm == [yY] || $confirm == [yY][eE][sS] ]]; then
    echo "Checking status for $SERVICE..."
    systemctl status "$SERVICE" --no-pager
    
       # Optional: Print specifically if active or not
       if systemctl is-active --quiet "$SERVICE"; then
        echo "$SERVICE is active."
       else
        echo "$SERVICE is NOT active."
       fi
   else
    echo "Skipped."
   fi
   ```
   
