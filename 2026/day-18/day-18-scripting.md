# Day 18 – Shell Scripting: Functions & intermediate Concepts

### Task 1: Basic Functions
1. Create `functions.sh` with:
   - A function `greet` that takes a name as argument and prints `Hello, <name>!`
   - A function `add` that takes two numbers and prints their sum
   - Call both functions from the script

     **Code :**
     ```bash
     #!/bin/bash

     # Funtion with argument

     greet () {
        NAME=$1
        echo "Hello, $NAME!"
     }

     greet "ROY"

     # Function for addition

     addition () {
        read -p "Enter the 1st number: " NUM1
        read -p "Enter the 2nd number: " NUM2
        let SUM=$NUM1+$NUM2
        echo "Sum of the $NUM1 and $NUM2 is $SUM"
     }

     addition
     ```

     **Output**
     ```bash
     Hello, ROY!
     Enter the 1st number: 21
     Enter the 2nd number: 10002
     Sum of the 21 and 10002 is 10023
     ```

---

### Task 2: Functions with Return Values
1. Create `disk_check.sh` with:
   - A function `check_disk` that checks disk usage of `/` using `df -h`
   - A function `check_memory` that checks free memory using `free -h`
   - A main section that calls both and prints the results

     **Code :**
     ```bash
     #!/bin/bash

     check_disk () {
        df -h /
     }

     check_memory () {
        free -h
     }

     main () {
        disk=$(check_disk)

        echo "$disk"

        echo "============================================="

        memory=$(check_memory)

        echo "$memory"
     }

     main
     ```

     **Output**
     ```bash
     Filesystem      Size  Used Avail Use% Mounted on
     /dev/root       8.7G  3.3G  5.5G  38% /
     =============================================
                    total        used        free      shared  buff/cache   available
     Mem:           911Mi       404Mi       166Mi       2.8Mi       498Mi       507Mi
     Swap:             0B          0B          0B
     ```

---

### Task 3: Strict Mode — `set -euo pipefail`
1. Create `strict_demo.sh` with `set -euo pipefail` at the top
2. Try using an **undefined variable** — what happens with `set -u`?
3. Try a command that **fails** — what happens with `set -e`?
4. Try a **piped command** where one part fails — what happens with `set -o pipefail`?

   set -u : if any undefined variable found script stop from that points
   set -e : if any error occur script exits immediately
   set -o pipefail : scripts exits if command failed
   
   **Code**
   ```
   #!/bin/bash
   
   set -u

   echo "hi"

   echo $dev

   echo "hello"
   ```

   **Code**
   ```
   #!/bin/bash
   
   set -e

   echo "hi"

   ls name*

   echo "hello"
   ```

---

### Task 4: Local Variables
1. Create `local_demo.sh` with:
   - A function that uses `local` keyword for variables
   - Show that `local` variables don't leak outside the function
   - Compare with a function that uses regular variables


     **Code**
     ```bash
     #!/bin/bash
     
     num1=10

     local_fun () {
           local num2=20
           local num3=30
           local sum=$((num2+num3))

           echo "local variable sum is $sum"
           echo "general variable is $num1"
     }

     local_fun
     ```

### Task 5: Build a Script — System Info Reporter
Create `system_info.sh` that uses functions for everything:
1. A function to print **hostname and OS info**
2. A function to print **uptime**
3. A function to print **disk usage** (top 5 by size)
4. A function to print **memory usage**
5. A function to print **top 5 CPU-consuming processes**
6. A `main` function that calls all of the above with section headers
7. Use `set -euo pipefail` at the top

     **Code**
     ```bash
     #!/bin/bash
     
     set -euo pipefail

     print_header () {
                echo "--------------------------- $1 ------------------------------"
     }

     system_info () {
                print_header "System-INFO"
                hostname
                cat /etc/os-release
     }

     uptime_info () {
                print_header "Uptime-INFO"
                uptime
     }

     disk_ugase () {
                print_header "DISK-USAGE"
                df -h | head -5
     }

     memory_usage () {
                print_header "MEMORY-USAGE"
                free -h
     }

     top_process () {
                print_header "Top CPU Process"
                ps aux --sort=-%cpu | head -7
     }

     main () {
               system_info
               uptime_info
               uptime_info
               disk_ugase
               memory_usage
               top_process
     }

     main
     ```

     

   

    
