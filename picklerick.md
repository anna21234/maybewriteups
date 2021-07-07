## Step 1 : Nmap scan

_nmap -sC -sV -oN scan1 -vv (an ip here)_

## Step 2 : Web Enum

_nikto -h http://the-ip-here_  
_dirb http://the-ip-here_  
_gobuster -u http://the-ip-here -w usr/share/wordlists/dirb/wordlist for dirb_  
(will update with correct path)

Look at the source of the web page, there is a username hidden.

Robots.txt contains the password for the login page  
Use the password and the username in the source code to login to the login.php page  
There, is a command running panel.

To view the contents of files use grep (cat and head are disabled)  
_grep . clue.txt_

Obtain the first ingredient this way,


## Step 3 : Reverse Shell time

Grab a Python3 reverse shell and paste it into the command panel

Catch the shell with a net cat listener on your attacker machine

Stabilise the shell with these commands  
![image](https://user-images.githubusercontent.com/12968503/124804662-75b46100-df52-11eb-8607-432f12fb2d18.png)

Once inside the shell run sudo -l to check for sudo privs

## To get root
To get root all you have to do is sudo su and you get a root shell

