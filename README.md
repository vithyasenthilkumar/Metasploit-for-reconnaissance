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
## OUTPUT:
Find out the ip address of the attackers system
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/e4eecafc-ea08-4bad-a5e7-e73bdf4f92c8)
Invoke msfconsole:
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/13f4c2d0-33dc-4f7e-9b1a-20b0ea6a6d03)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/c7925edc-4906-4997-b313-3d4c17070396)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/f5c05b07-624a-4837-9467-f47f3b57cd06)
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/d72934ca-83e0-40d8-98bc-5973033a772d)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/15df4ad0-59cb-4de1-88f9-0c23952c8469)
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/e1d02cf1-37dd-47d2-ac49-11bd1a653038)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/2993e57f-a594-4560-bb82-e86f110962b5)
The info command provides information regarding a module or platform
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/2af18165-2795-4a5a-ae5d-9c4c65c6fc2f)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/00182066-9c91-4bd8-ad63-7527d27e785b)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/fda81f61-d4cc-47a9-a5ad-4ba08a7f3c15)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/1f8a10c1-3b89-4482-95e6-6d762721d939)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/60ca0e8e-fbd0-4e75-b0b5-0763ad26ddb1)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/ed9f978e-5d23-4d4b-ade3-204de4fba1a9)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/vithyasenthilkumar/Metasploit-for-reconnaissance/assets/127177445/4cfd19a4-c8e3-438c-b272-9cbba0cf3caa)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
