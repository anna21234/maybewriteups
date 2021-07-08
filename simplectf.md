# Simple CTF from tryhackme

## Step 1: Nmap scan
_nmap (an ip here)_  
![image](https://user-images.githubusercontent.com/12968503/124926209-26733c80-dff5-11eb-9ab6-4e559e7779c8.png)

_nmap -sC -sV (an ip here)_  
![image](https://user-images.githubusercontent.com/12968503/124926456-73571300-dff5-11eb-8bec-40eee45d4545.png)






## Step 2: Web Enum
_nikto -h http://the-ip-here_  
![image](https://user-images.githubusercontent.com/12968503/124926936-fb3d1d00-dff5-11eb-85ca-f4200a26c2b8.png)

_dirb http://the-ip-here_  
![image](https://user-images.githubusercontent.com/12968503/124927137-317a9c80-dff6-11eb-820a-bc51402c7a72.png)

_gobuster dir -u http://the-ip-here --wordlist /usr/share/wordlists/dirb/common.txt_  
![image](https://user-images.githubusercontent.com/12968503/124927672-cda4a380-dff6-11eb-9aa4-87e0b61de8a4.png)

According to the web enum the site is using a Simple CMS for their webserver
![image](https://user-images.githubusercontent.com/12968503/124927995-1f4d2e00-dff7-11eb-9fba-59cdb6494766.png)

![image](https://user-images.githubusercontent.com/12968503/124928133-43a90a80-dff7-11eb-8fad-21ee9e0d9f58.png)

We now have the version number of the CMS

## Step 3: Exploit DB
searchsploit (any service and version number you want to look up)

![image](https://user-images.githubusercontent.com/12968503/124928440-7eab3e00-dff7-11eb-9ae0-f39ad08b551c.png)

Now run the exploit against the simple directory and you should get the credentials

## Step 4: Login to SSH

