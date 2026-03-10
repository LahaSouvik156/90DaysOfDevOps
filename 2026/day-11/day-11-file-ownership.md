# Day 11 – File Ownership Challenge (chown & chgrp)
___________________________________________________

### Task 1: Understanding Ownership

1. Check the owner and group of files & directories in your home directory.                       
   $ ls -l

2. What's the difference between owner and group?

   In Linux, the owner is a single specific user account, while a group is a collection of user accounts. Every file and directory is assigned both an owner and a single associated group, and separate permissions (read, write, execute) are defined for each. 

___

### Task 2: Basic chown

1. Create file `devops-file.txt`                       
   $ touch devops-file.txt
 
2. Check current owner.                              
   $ ls -l devops-file.txt

3. Change owner to `tokyo`                            
   $ sudo chown tokyo devops-file.txt

4. Change owner to `berlin`                            
   $ sudo chown berlin devops-file.txt

5. Verify the changes                                  
   $ ls -l devops-file.txt

___

### Task 3: Basic chgrp Operations

1. Create file `team-notes.txt`                         
   $ touch team-notes.txt

2. Check current group of that file.                      
   $ ls -l team-notes.txt

3. Create group `heist-team`                    
   $ sudo groupadd heist-team

4. Change file group to `heist-team`                                 
   $ sudo chgrp heist-team team-notes.txt

5. Verify the change                     
   $ ls -l team-notes.txt

___

### Task 4: Combined Owner & Group Change

1. Create file `project-config.yaml`                         
   $ touch project-config.yaml

2. Change owner to `professor` AND group to `heist-team` (one command)                      
   $ sudo chown professor:heist-team project-config.yaml

3. Create directory `app-logs/`                          
   $ mkdir app-logs

4. Change its owner to `berlin` and group to `heist-team`                  
   $ sudo chown berlin:heist-team app-logs

___

### Task 5: Recursive Ownership

1. Create directory structure: 
   ```
   heist-project/vault
   heist-project/plans
   heist-project/vault/gold.txt
   heist-project/plans/strategy.conf
   ```
   $ mkdir -p heist-project/vault               
   $ mkdir -p heist-project/plans                  
   $ touch heist-project/vault/gold.txt                          
   $ touch heist-project/plans/strategy.conf

2. Create group `planners`                 
   $ sudo groupadd planners

3. Change ownership of entire `heist-project/` directory:
   - Owner: `professor`
   - Group: `planners`
   - Use recursive flag (`-R`)

   $ sudo chown -R professor heist-project             
   $ sudo chgrp -R planners heist-project

4. Verify all files and subdirectories changed.                           
   $ ls -lR heist-project

___

### Task 6: Practice Challenge

1. Create users: `tokyo`, `berlin`, `nairobi`       
   (Alreday created)

2. Create groups: `vault-team`, `tech-team`                          
   $ sudo groupadd vault-team                               
   $ sudo groupadd tech-team

3. Create directory: `bank-heist/`                               
   $ mkdir back-heist

4. Create 3 files inside:
   ```
   bank-heist/access-codes.txt
   bank-heist/blueprints.pdf
   bank-heist/escape-plan.txt
   ```

   $ touch bank-heist/access-codes.txt           
   $ touch bank-heist/blueprints.pdf                         
   $ touch bank-heist/escape-plan.txt

5. Set different ownership:
   - `access-codes.txt` → owner: `tokyo`, group: `vault-team`
   - `blueprints.pdf` → owner: `berlin`, group: `tech-team`
   - `escape-plan.txt` → owner: `nairobi`, group: `vault-team`

   $ sudo chown tokyo:vault-team access-codes.txt                
   $ sudo chown berlin:tech-team blueprints.pdf                          
   $ sudo chown nairobi:vault-team escape-plan.txt
