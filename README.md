# Aws-Webserver-Wordpress

Configuring WordPress With MySQL Database over AWS Using AWS RDS
STEP 1:
LAUNCH AN EC2 INSTANCE
STEP 2
CREATE A DATABASE (RDS)
STEP 3
CONNECT WITH THE EC2 INSTANCE AND INSTALL THE REQUIREMENTS
1 Update your repo
 dnf update -y
2 Install fedora rpm
dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
3 Install wget software to download packages from internet
yum install wget -y
4 Configure Apache webserver
yum install httpd
systemctl start httpd
systemctl status httpd
5 Install PHP software requirements and Mysql database
dnf install http://rpms.remirepo.net/enterprise/remi-release-8.rpm dnf module install php:remi-7.4
dnf install php-mysqlnd
dnf install mysql -y
STEP 4
CONNECT RDS WITH INSTANCE AND CREATE A DATABASE
mysql -h <Database Endpoint> -u <username> -p
STEP 5
CONFIGURING WORDPRESS
1 Download WordPress
wget http://wordpress.org/latest.tar.gz
Unzip it

tar -xvzf latest.tar.gz -C /var/www/html
Go to root dir

cd /var/www/html/wordpress
wp-config-sample.php
Add your database name, username, password and database end point Now Restart your httpd service and set selinux permission

systemctl restart httpd
setenforce 0
STEP 6
OPEN WORDPRESS IN BROWSER
--> Use your instance public IP --> Login with your credentials --> Finally all done and now can start writing your blog!
