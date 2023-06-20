# EC2-html-website-deployment-script
This is a repository of the deployment script of the website xmen running on an EC2 instance

#!/bin/bash
sudo su
yum update -y
yum install -y httpd
cd /var/www/html
wget https://github.com/aiincloud/xmen/archive/refs/heads/main.zip
unzip main.zip
cp -r xmen-main/* /var/www/html/
rm -rf xmen-main main.zip
systemctl enable httpd 
systemctl start httpd
