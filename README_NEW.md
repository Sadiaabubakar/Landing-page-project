# Documentation for Deliverables: Hosting a Static Web Page on an Apache Server with HTTPS and a Custom Domain

## Project Overview
This project demonstrates the provisioning of an EC2 instance on AWS, installing and configuring an Apache web server, deploying a custom HTML landing page, and securing it with HTTPS and a custom domain.

---

## Steps Taken

### Step 1: Provisioning an EC2 Instance on AWS
1. **Platform**: AWS Management Console  
2. **Instance Details**:  
   - **Region**: Europe (Stockholm)  
   - **AMI**: Ubuntu 22.04 LTS  
   - **Instance Type**: t3.micro  
   - **Security Group Configuration**:  
     - Allowed inbound traffic on:
       - Port 22 (SSH)
       - Port 80 (HTTP)
       - Port 443 (HTTPS)
   - **Instance Access**: Connected via SSH using the key pair:
     ```bash
     ssh -i <your-key>.pem ubuntu@51.20.1.18
     ```

---

### Step 2: Setting Up an Apache Web Server
1. **Update and Upgrade Packages**:
   ```bash
   sudo apt update
   sudo apt upgrade -y

	2.	Install Apache:

sudo apt install apache2 -y


	3.	Start Apache:

sudo systemctl start apache2
sudo systemctl enable apache2

Step 3: Deploying a Custom HTML Landing Page
	1.	Navigate to the Apache Web Directory:

cd /var/www/html


	2.	Open the index.html file using nano:

sudo nano index.html


	3.	Add the Following HTML Content:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to Sadia's Landing Page</title>
</head>
<body>
    <h1>Welcome to Sadia's Landing Page</h1>
    <p>Project Title: Welcome to Sadia Landing Page</p>
    <p>About: This project involves provisioning a Linux server, setting up a web server, and deploying a simple HTML landing page to demonstrate server management and web hosting capabilities as part of a cloud engineering exercise.</p>
    <p>Bio: I am Sadia Abubakar, a passionate tech enthusiast who thrives on exploring new opportunities in the tech world. By night, I work as a dedicated support worker, and by day, I channel my creativity into tech projects.</p>
</body>
</html>


	4.	Save and Exit:
	•	Press Ctrl + O → Enter → Ctrl + X
	5.	Verify the Setup:
	•	Open your browser and navigate to http://51.20.1.18

Step 4: Securing the Website with HTTPS
	1.	Install Snap:

sudo apt install snapd -y
sudo snap install core
sudo snap refresh core


	2.	Install Certbot:

sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot


	3.	Obtain and Install SSL Certificate:

sudo certbot --apache

	•	Enter your email address when prompted.
	•	Agree to the terms of service.
	•	Enter your domain name: gbnijrtjogb.sbs

	4.	Verify HTTPS:
	•	Visit https://gbnijrtjogb.sbs in your browser.

Step 5: Configuring a Custom Domain
	1.	Purchased Domain:
	•	Registrar: Dynadot
	•	Domain: gbnijrtjogb.sbs
	2.	Configure DNS Settings:
	•	Set the following A records:
	•	Record Type: A
	•	Name: @
	•	IP Address: 51.20.1.18
	•	Record Type: A
	•	Name: www
	•	IP Address: 51.20.1.18

Deliverables
	1.	Public IP Address: 51.20.1.18
	2.	Custom Domain: gbnijrtjogb.sbs
	3.	HTTPS URL: https://gbnijrtjogb.sbs
	4.	Screenshot: A screenshot of the deployed landing page in a browser.
