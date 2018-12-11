# Linux Machine Configuration

# Accessibility

The VM can be accessed through IP address 54.218.171.184 on SSH port 2200 using 'grader' user.

The item catalog application is hosted on http://ec2-54-218-171-184.us-west-2.compute.amazonaws.com

P.S. due to the same error described in https://stackoverflow.com/questions/52911558/cant-add-aws-ec2-instance-as-an-authorized-redirect-uri-in-google-developers-c, google auth cannot be set up to allow user login. 

# Configurations

1. Package update

Download package: 
```
sudo apt-get update
```
Get newest versions of packages: 
```
sudo apt-get upgrade
```
2. SSH Port config

Run sudo nano /etc/ssh/sshd_config

Change the port from 22 to 2200

Restart ssh: 
```
sudo service sshd restart
```
3. Firewall Setup 
```
sudo ufw allow 2200/tcp
sudo ufw allow 80/tcp
sudo ufw allow 123/udp
sudo ufw enable
```
4. Add new user grader
```
sudo adduser grader
sudo usermod -aG sudo grader
```
5. Time zone setup
```
sudo timedatectl set-timezone UTC
```
6. Install libraries & packages



