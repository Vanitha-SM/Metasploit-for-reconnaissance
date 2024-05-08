# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/994caa35-e34e-44c4-b9f1-5770880bcc32)


Invoke msfconsole:

## OUTPUT:
![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/e768eadb-013a-485d-91ef-619e008b5d52)



Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/2a3e5b8e-6c9c-489c-abb1-33a2d69a2735)

Port Scanning:

Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.1.4/24 -p1-1000

## OUTPUT:

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/1f804354-d824-4a9a-be80-87f9f4a3146a)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.1.4/24

## OUTPUT:
![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/b7ce7aaa-8d24-4d0b-8a19-9add2210eca4)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l

## OUTPUT:
![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/95a7a4d2-933c-4a41-bd5a-e9029699dc2b)


Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit

## OUTPUT:

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/d053e906-b02e-40f4-abf8-9e2f9f2cf563)

The info command provides information regarding a module or platform,

## OUTPUT:

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/7613ada5-697e-40c7-be8d-3eb11e0f3459)

## MYSQL ENUMERATION:
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/c075d8c3-fe2d-4386-8c6a-24c9d761d363)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/a6202350-3e08-42ef-98e5-5278242ecdcb)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/496dc877-08c1-4c9d-983d-3998bf6b8b64)

Use the set rhosts command to set the parameter and run the module, as follows

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/415ab782-d0ce-4b71-bcad-ff6022292f6e)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/3d814d3a-d25c-44d2-aff6-296ef99d3952)

et the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:

set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS

Set BLANK_PASSWORDS to true in case there is no password set for the root account.

set BLANK_PASSWORDS true

![image](https://github.com/Vanitha-SM/Metasploit-for-reconnaissance/assets/119557985/6e1858f0-36aa-4488-b661-684be0f41225)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
