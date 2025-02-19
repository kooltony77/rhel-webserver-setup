# RHEL Web Server Setup

This project demonstrates how to set up a **simple web server on Red Hat Enterprise Linux (RHEL)** using **Apache (httpd)** and how to push the project to **GitHub** for version control.  

## Features:
✅ Installs and starts **Apache (`httpd`)**  
✅ Hosts a sample `index.html` page  
✅ Configures **firewalld** to allow HTTP/HTTPS traffic  
✅ Pushes project files to **GitHub**  

---

Installing Git on Red Hat Linux**  
To push your project to GitHub, you need **Git** installed. Use the following command:  

sudo yum install git -y

Verify installation:
git --version

Setting Up Apache Web Server
Step 1: Install Apache
sudo yum install httpd -y

Step 2: Start and Enable Apache
sudo systemctl start httpd
sudo systemctl enable httpd

Step 3: Configure Firewall
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --reload

Step 4: Verify Apache Installation
Check the status of Apache:
sudo systemctl status httpd

If Apache is running, visit your server’s IP in a web browser:
http://<your-server-ip>

Finding Your Server's IP Address
hostname -I

Creating an HTML Page
Step 1: Create an index.html File
Navigate to the Apache root directory:
cd /var/www/html

Create and edit the index.html file:
sudo touch vim index.html

Add the following content:
<!DOCTYPE html>
<html>
<head>
    <title>My RHEL Web Server</title>
</head>
<body>
    <h1>Welcome to My Web Server!</h1>
    <p>This website is hosted on a Red Hat Linux server.</p>
</body>
</html>

Restart Apache
sudo systemctl restart httpd

Now, visit:http://<your-server-ip>

Clone Your Repository on Red Hat
Copy your repository HTTPS URL from GitHub, then run:
git clone https://github.com/yourusername/rhel-webserver.git

Move into the repository:
cd rhel-webserver

Copy Your HTML File to the GitHub Folder
cp /var/www/html/index.html ~/rhel-webserver/

Commit and Push Files to GitHub
git add index.html
git commit -m "Added index.html for RHEL web server setup"
git push origin main

Fixing Git Authentication Issues:
GitHub no longer allows password authentication for Git operations. Use Personal Access Tokens (PAT) instead.
Go to GitHub Settings → Developer settings → Personal Access Tokens
(https://github.com/settings/tokens)
Click Generate new token.
Set Repository access to All repositories.
Under Permissions, enable:
Contents → Read and write
Commit Status → Read and write
Click Generate Token and copy it (you will only see it once!).

Use the Token for Git Authentication:
git push origin main
**When Git asks for a username, enter your GitHub username.**
**When it asks for a password, paste your Personal Access Token.**

Verifying Your Files on GitHub:
Go to your GitHub repository:
https://github.com/yourusername/rhel-webserver

You should see index.html uploaded.
