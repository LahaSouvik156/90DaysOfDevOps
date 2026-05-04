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

    
