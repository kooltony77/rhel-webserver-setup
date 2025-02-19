# RHEL Web Server Setup

This project demonstrates how to set up a simple **Apache web server** on **Red Hat Enterprise Linux (RHEL)** and deploy a basic website.

# RHEL Web Server Setup

This project demonstrates how to set up a simple **Apache web server** on **Red Hat Enterprise Linux (RHEL)** and deploy a basic website.

## Features:
✅ Installs and starts Apache (`httpd`)  
✅ Hosts a sample `index.html` page  
✅ Allows HTTP and HTTPS traffic via `firewalld`  

## How to Use:
1. Install Apache:
   sudo yum install httpd -y

Start Apache:
sudo systemctl start httpd
sudo systemctl enable httpd

Copy your HTML file:
sudo cp index.html /var/www/html/index.html

Open your browser and visit:
http://<your-server-ip>
