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
     ```bash
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
     ```

---

### Task 3: Command-Line Arguments
1. Create `greet.sh` that:
   - Accepts a name as `$1`
   - Prints `Hello, <name>!`
   - If no argument is passed, prints "Usage: ./greet.sh <name>"

     **Code :**
     ```bash
     #!/bin/bash

     # Script for user input with read and passing argument

     read -p "Enter your name: " name
     read -p "Enter your favourite tools name: " tool

     echo "Hello $name, your favourite tool is $tool"
     echo "Hi $name , let me introduce you with $1 and he is an $2 specialist"
     ```

     **Output**
     ```bash
     bash greet.sh Jason AI       # NOTE: Jason and AI are give as an argument
     Enter your name: Jacky
     Enter your favourite tools name: k8s
     Hello Jacky, your favourite tool is k8s
     Hi Jacky , let me introduce you with Jason and he is an AI specialist
     ```

---

2. Create `args_demo.sh` that:
   - Prints total number of arguments (`$#`)
   - Prints all arguments (`$@`)
   - Prints the script name (`$0`)

     **Code :**
     ```bash
     #!/bin/bash

     # scipt to demonstrate arguments

     echo "1st argument is $1"
     echo "2nd argument is $2"
     echo "All arguments are $@"
     echo "Total number of arguments are $#"
     echo "The script name is $0"
     ```

     **Output**
     ```bash
     1st argument is Bash
     2nd argument is Linux
     All arguments are Bash Linux
     Total number of arguments are 2
     The script name is args_demo.sh
     ```

---

### Task 4: Install Packages via Script
1. Create `install_packages.sh` that:
   - Defines a list of packages: `nginx`, `curl`, `wget`
   - Loops through the list
   - Checks if each package is installed (use `dpkg -s` or `rpm -q`)
   - Installs it if missing, skips if already present
   - Prints status for each package

> Run as root: `sudo -i` or `sudo su`

   **Code :**
   ```bash
   #!/bin/bash

  # List of packages to install
  PACKAGES=("nginx" "curl" "wget")

  echo "Updating package list..."
  sudo apt-get update -y

  # Loop through the list
  for package in ${PACKAGES[@]}
  do
    # Check if package is installed
    if dpkg -s "$package" >/dev/null 2>&1; 
    then
        echo "$package is already installed. Skipping."
    else
        echo "$package is not installed. Installing..."
        apt-get install -y "$package"
        
        # Verify installation
        if dpkg -s "$package" >/dev/null 2>&1; then
            echo "$package installed successfully."
        else
            echo "$package failed to install."
        fi
    fi
 done
 ```

---


### Task 5: Error Handling
1. Create `safe_script.sh` that:
   - Uses `set -e` at the top (exit on error)
   - Tries to create a directory `/tmp/devops-test`
   - Tries to navigate into it
   - Creates a file inside
   - Uses `||` operator to print an error if any step fails

    **Code :**
    ```bash
    #!/bin/bash

    set -e

    mkdir /tmp/devops-test || echo "Directory already exists"

    cd /tmp/devops-test || echo "Cannot enter directory"

    touch testfile.txt || echo "Cannot create file"

    echo "Script completed!"
    ```


     
