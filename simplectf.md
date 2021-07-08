# Simple CTF from tryhackme

## Step 1: Nmap scan
_nmap -sC -sV -oN scan1 -vv (an ip here)_

## Step 2: Web Enum
_nikto -h http://the-ip-here_  
_dirb http://the-ip-here_  
_gobuster -u http://the-ip-here -w usr/share/wordlists/dirb/wordlist for dirb_  

## Step 3: Exploit DB
searchsploit (any service and version number you want to look up)
