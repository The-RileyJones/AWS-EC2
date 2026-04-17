# AWS-EC2
TechX AWS EC2 + ALB Interview Project

This project documents the process of launching two AWS EC2 web server instances and configuring them for load balancing and failover using an Application Load Balancer (ALB).

Step 1: Launch and Configure EC2 Instances

Two EC2 instances were created and configured as web servers.

Instance Names: WebServer1, WebServer2
AMI: Ubuntu (both instances)
Instance Type: t3.small (both instances)
SSH Key Type: RSA

Network Configuration (Security Group):

Allow SSH access from my IP address
Allow HTTP (port 80) from the internet
Allow HTTPS (port 443) from the internet

Storage Configuration:

8 GiB gp3 volume (default)

Web Server Installation (on both instances):

sudo apt install apache2
sudo systemctl status apache2

Website Deployment:

Created WebPage1.html and WebPage2.html in a Git repository
Cloned the repository contents to /var/www/html/index.html on each instance

At this stage, both EC2 instances were successfully configured to serve a basic webpage via Apache.

Step 2: Customize Web Server Content

Each instance was configured to return unique content to verify load balancing:

WebServer1: “Welcome to Webpage1!”
WebServer2: “Welcome to Webpage2!”

Step 3: Configure Load Balancing
Created a target group and registered both EC2 instances
Configured an Application Load Balancer (ALB)
Associated the ALB with the target group to distribute incoming traffic across both servers

Step 4: 
Ran a simple reliablility test to see if one instance goes down, if the other would pick up the requests.

