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
