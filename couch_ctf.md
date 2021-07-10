# Couch CTf from tryhackme

## Step 1: Nmap Scan
_nmap (an ip here)_  
![image](https://user-images.githubusercontent.com/12968503/125167766-0335c200-e19a-11eb-9e6e-fa00acd76108.png)

_nmap -sC -sV (an ip here)_  
![image](https://user-images.githubusercontent.com/12968503/125167815-56a81000-e19a-11eb-8f99-ee929ebe6250.png)

## To get user

Just ook up coudb web inteface and it happens to be _utils  

Find the db called secret  

In there, there is a password backup

Use the credentials to log in to ssh

## To get root

Grab the user.txt and check bash history

You will find a docker command

Run the command and you will have root in a  docker container
