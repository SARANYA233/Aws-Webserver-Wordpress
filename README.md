# Aws-Webserver-Wordpress

# Configuring WordPress With MySQL Database over AWS Using AWS RDS

## STEP 1:
### LAUNCH AN EC2 INSTANCE[Amazon-Linux]

## STEP 2
### CREATE A DATABASE (RDS)

## STEP 3
### CONNECT WITH THE EC2 INSTANCE AND INSTALL THE REQUIREMENTS

#### 1 Update your repo
 
 sudo yum update -y

#### 2 Configure Apache webserver

yum install httpd -y
systemctl start httpd
systemctl status httpd

#### 3 Install PHP software requirements and Mysql database

amazon-linux-extras install php7.3
yum install php-mysqlnd -y
yum install mysql -y

## STEP 4
### CONNECT RDS WITH INSTANCE AND CREATE A DATABASE

mysql -h <Database Endpoint> -u <username> -p

## STEP 5
### CONFIGURING WORDPRESS
#### 1 Download WordPress

wget http://wordpress.org/latest.tar.gz

#### 2 Unzip it

tar -xvzf latest.tar.gz 
cp -rf wordpress/* /var/www/html/

#### 3 Go to root dir

cd /var/www/html/wordpress
wp-config-sample.php

Add your database name, username, password and database end point
#### 4 Restart your httpd service and set selinux permission

systemctl restart httpd
setenforce 0

## STEP 6
### OPEN WORDPRESS IN BROWSER
##### --> Use your instance public IP 
##### --> Login with your credentials  
##### --> Finally all done and now can start writing your blog!
