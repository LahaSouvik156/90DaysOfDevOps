# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

## Today's goal is to **deploy a real web server on the cloud** and learn practical server management.


Part 1: Launch Cloud Instance & SSH Access (15 minutes):

We can launch an EC2 instance on AWS via AWS platform. After creation of the instance we can connect to our local machine to cloud instance via SSH.
After running below command on local machine's terminal, our machine will connect our EC2 instance:

ssh -i "pem-file" < Public DNS of EC2 Instance >

--------------------------------------------------------------

Part 2: Install Docker & Nginx (20 minutes)

$ sudo apt update ( To update the Linux Machine )

$ sudo apt upgrade ( To upgrade all the existing packages, links etc )

$ sudo apt install docker.io -y

$ sudo apt install nginx -y

-----------------------------------------------------------------

Part 3: Security Group Configuration (10 minutes)

Test Web Access:

Open security groups-> Edit inbound rules-> Enable port number 80 ( nginx run on port 80 )

--------------------------------------------------------------------

Part 4: Extract Nginx Logs 

$ journalctl -u nginx ( To check the logs of the service )


