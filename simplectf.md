# Simple CTF from tryhackme

## Step 1: Nmap scan
_nmap (an ip here)_  
![image](https://user-images.githubusercontent.com/12968503/124926209-26733c80-dff5-11eb-9ab6-4e559e7779c8.png)

_nmap -sC -sV (an ip here)_  
![image](https://user-images.githubusercontent.com/12968503/124926456-73571300-dff5-11eb-8bec-40eee45d4545.png)






## Step 2: Web Enum
_nikto -h http://the-ip-here_  
_dirb http://the-ip-here_  
_gobuster -u http://the-ip-here -w usr/share/wordlists/dirb/wordlist for dirb_  

## Step 3: Exploit DB
searchsploit (any service and version number you want to look up)
