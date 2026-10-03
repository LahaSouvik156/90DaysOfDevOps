# Day 09 – Linux User & Group Management Challenge


## Task 1: Create three users (berlin, tokyo and professor) with home directories and passwords:

$ sudo useradd -m -s /bin/bash berlin 

$ sudo passwd berlin (Then we can set the password for user berlin)

$ sudo useradd -m -s /bin/bash tokyo && echo "tokyo:test@123" | sudo chpasswd

$ sudo useradd -m -s /bin/bash professor && echo "professor:test@123" | sudo chpasswd

To verify $ cat /etc/passwd

-----------------------------------------------------

## Task 2: Create two groups developers and admins:

$ sudo groupadd developers

$ sudo groupadd admins

To verify $ cat /etc/group

------------------------------------------------


## Task 3: Assign Users to Groups: 

tokyo → developers:   $ sudo gpasswd -a tokyo developers

berlin → developers + admins (both groups):   $ sudo usermod -aG developers,admins berlin

professor → admins:   $ sudo usermod -aG admins professor

----------------------------------------------------------

## Task 4: Shared Directory:

1. Create directory: /opt/dev-project:   $ sudo mkdir /opt/dev-project

2. Set group owner to developers:   $ sudo chgrp developers /opt/dev-project

3. Set permissions to 775:   $ sudo chmod 775 /opt/dev-project

4. Test by creating files as tokyo and berlin

    $ cd /home/ && su tokyo
  
    $ cd ~
  
    $ cd /opt/dev-project
  
    $ touch demofile_01.txt

  Simillarly we can login as a berlin user and create demofile_02.txt

  ------------------------------------------------------------------

  ## Task 5: Team Workspace:

  1. Create user nairobi with home directory:   $ sudo useradd -m -s /bin/bash nairobi && echo "nairobi:test@123" | sudo chpasswd

  2. Create group project-team:   $ sudo groupadd projetc-team

  3. Add nairobi and tokyo to project-team:  $ sudo gpasswd -M nairobi,tokyo project-team

  4. Create /opt/team-workspace directory:  $ sudo mkdir /opt/team-workspace

  5. Set group to project-team, permissions to 775:

       $ sudo chgrp project-team /opt/team-workspace

       $ sudo chmod 775 /opt/team-workspace

  6. Test by creating file as nairobi:

       $ cd /home/ && su nairobi

       $ cd ~

       $ cd /opt/team-workspace

       $ touch demofile_03.txt
