# Basic Pentesting box writeup from tryhackme

## Step 1 : Nmap scan 
nmap -sC -sV -oN scan1 -vv 10.10.180.237

![Screenshot at 2021-07-07 13-56-35](https://user-images.githubusercontent.com/12968503/124764735-2d367c80-df2d-11eb-9e2c-a4d3bcb96cf7.png)

![image](https://user-images.githubusercontent.com/12968503/124765439-ded5ad80-df2d-11eb-936c-aab84e9d6d1d.png)

![image](https://user-images.githubusercontent.com/12968503/124765613-0c225b80-df2e-11eb-84fa-bb614ba38390.png)

![image](https://user-images.githubusercontent.com/12968503/124765842-4a1f7f80-df2e-11eb-9ef8-a465421284b1.png)

![image](https://user-images.githubusercontent.com/12968503/124766185-966abf80-df2e-11eb-88ad-da200a37722b.png)

![image](https://user-images.githubusercontent.com/12968503/124766382-c619c780-df2e-11eb-9bca-dcae3e5f1b61.png)

![image](https://user-images.githubusercontent.com/12968503/124766503-e3e72c80-df2e-11eb-8e1f-3930269d2e76.png)

## Step 2:  SMB Enum
_./smbmap.py -H 10.10.180.237_  

![image](https://user-images.githubusercontent.com/12968503/124768569-af747000-df30-11eb-9c89-b83528b1e707.png)

_smbclient -L 10.10.180.237_  

![image](https://user-images.githubusercontent.com/12968503/124768765-daf75a80-df30-11eb-82dd-f598d8e4f15d.png)

_smbclient //10.10.180.237/Anonymous_  

![image](https://user-images.githubusercontent.com/12968503/124768951-fd897380-df30-11eb-9f9a-ae2e89bcf70e.png)

Found a staff.txt on the Anon share

![image](https://user-images.githubusercontent.com/12968503/124767676-eeee8c80-df2f-11eb-83d0-47018270a5f2.png)

Known users: Kay and Jan

## Step 3: Web Enum

![image](https://user-images.githubusercontent.com/12968503/124769381-5527df00-df31-11eb-81e6-8537f3f30421.png)

### Time to dirb

_dirb http://10.10.180.237_

![image](https://user-images.githubusercontent.com/12968503/124769728-9ddf9800-df31-11eb-9a3b-5a8474773052.png)

Found development page

![image](https://user-images.githubusercontent.com/12968503/124769966-d7b09e80-df31-11eb-8ddd-f167c59e37a0.png)

Dev.txt

![image](https://user-images.githubusercontent.com/12968503/124770061-eb5c0500-df31-11eb-9d69-dd227954dbb4.png)

J.txt

![image](https://user-images.githubusercontent.com/12968503/124770226-13e3ff00-df32-11eb-9e19-116c9918f3e3.png)

Jan has a weak password?

## Step 3: Cracking Jan's password

_hydra -t 4 -l jan -P /usr/share/wordlists/rockyou.txt -vV 10.10.180.237 ssh_

## Step 4: Login to SSH as Jan

Look in kay's directory for the ssh keys and grab them.

Can't use them to log in yet because they have a passphrase, so use ssh2john



