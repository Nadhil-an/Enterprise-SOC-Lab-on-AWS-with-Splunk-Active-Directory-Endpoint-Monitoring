🖥️ Day 2 – Splunk Server Deployment on AWS
🎯 Objective

Deploy and configure Splunk Enterprise SIEM on an Ubuntu EC2 instance inside a custom AWS VPC to serve as the central log monitoring server for the Enterprise SOC Lab.

🏗️ Architecture Overview
🔁 Data Flow
Attacker → Internet → AWS VPC → Splunk Server → SOC Analyst

This means:

Logs are generated from systems

Logs are sent to Splunk

SOC Analyst monitors and investigates alerts

📸 Splunk Deployment Architecture

(Insert your architecture screenshot here — Page 2 from your PDF)

🚀 Step 1 – Launch Ubuntu EC2 Instance
🔹 Go to AWS Console → EC2 → Launch Instance

Configure:

AMI: Ubuntu Server 22.04 LTS

Instance Type: t2.micro (Free Tier)

Key Pair: Select or create new

Network: Custom SOC VPC

Auto-assign Public IP: Enabled

🔐 Step 2 – Configure Security Group

Allow the following inbound ports:

Port	Protocol	Purpose
22	TCP	SSH Access
8000	TCP	Splunk Web Interface
9997	TCP	Log Receiving Port
📸 EC2 Instance Running

(Insert your EC2 running screenshot here)

🔑 Step 3 – Connect to EC2 via SSH

From your local machine:

ssh -i your-key.pem ubuntu@<EC2-Public-IP>

Example:

ssh -i soc-key.pem ubuntu@18.226.xxx.xxx
🔄 Step 4 – Update System Packages
sudo apt update
sudo apt upgrade -y
📥 Step 5 – Download Splunk Enterprise
wget -O splunk.tgz https://download.splunk.com/products/splunk/releases/9.x.x/linux/splunk-9.x.x-linux-amd64.tgz
📂 Step 6 – Extract & Install Splunk
tar -xvzf splunk.tgz
sudo mv splunk /opt/
cd /opt/splunk/bin
▶ Step 7 – Start Splunk
sudo ./splunk start

Accept license → type y

Create admin username

Create password

📸 Splunk Installation Output

(Insert your terminal screenshot here)

🌐 Step 8 – Access Splunk Web Interface

Open browser:

http://<EC2-Public-IP>:8000

Example:

http://18.226.xxx.xxx:8000

Login using admin credentials.

📸 Splunk Web Login Page

(Insert your Splunk login screenshot here)

📡 Step 9 – Enable Log Receiving (Port 9997)

Inside Splunk:

Go to Settings

Click Forwarding and Receiving

Select Configure Receiving

Add new port

Enter:

9997

Save changes.

🔄 Step 10 – Enable Auto Start on Boot
sudo ./splunk enable boot-start
✅ Step 11 – Verify Splunk Status
sudo ./splunk status

Expected Output:

splunkd is running
🏆 Day 2 Achievements

✔ Ubuntu EC2 deployed
✔ Custom Security Group configured
✔ Splunk Enterprise installed
✔ Web Interface accessible
✔ Log receiving port enabled
✔ Boot start configured
