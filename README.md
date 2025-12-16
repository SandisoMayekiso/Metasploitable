🖥️ Metasploitable Lab – Network Enumeration & Post-Login Analysis

This repository contains a detailed walkthrough of a penetration testing lab on a Metasploitable virtual machine. The lab demonstrates network enumeration, service scanning, and post-login analysis using Kali Linux as the attacker machine.

📌 Lab Overview

Attacker OS: Kali Linux

Target OS: Metasploitable Ubuntu 8.04

Lab Goal:

Identify the target on the local network

Scan for open ports and running services

Perform post-login enumeration

Understand the system’s configuration and potential privilege escalation paths

⚠️ This lab is intentionally vulnerable. Never perform these actions on production systems.

1️⃣ Initial Network Enumeration

Check your Kali network configuration and identify reachable hosts.

┌──(kali㉿kali)-[~]
└─$ ip a


Output shows the attacker’s IP address:

eth0: inet 192.168.181.128/24


Discover hosts on the local network:

┌──(kali㉿kali)-[~]
└─$ arp -a


Ping the target to verify connectivity:

┌──(kali㉿kali)-[~]
└─$ ping 192.168.181.2


All packets received; the target is reachable.

2️⃣ Port Scanning

Scan specific ports to check if services are open:

┌─$ nmap -p 21,22,23,80 192.168.181.2


Result: Ports closed → move to next potential target.

Scan Metasploitable VM:

┌─$ nmap -p 21,22,23,80 192.168.181.130


Result: All ports open → ready for further enumeration.

Service version detection:

┌─$ nmap -sV 192.168.181.130


Detected services include:

FTP – ProFTPD 1.3.1

SSH – OpenSSH 4.7p1

Telnet – Linux telnetd

HTTP – Apache 2.2.8 with PHP 5.2.4

Database services: MySQL 5.0.51a, PostgreSQL 8.3

Samba, Apache Tomcat, Postfix, ISC BIND, etc.

These outdated services are intentionally vulnerable, ideal for learning enumeration.

3️⃣ Post-Login via Telnet

Access the system using Telnet:

┌─$ telnet 192.168.181.130


Login credentials:

Username: msfadmin

Password: msfadmin

Confirm login:

msfadmin@metasploitable:~$ whoami
msfadmin
msfadmin@metasploitable:~$ id
uid=1000(msfadmin) gid=1000(msfadmin) groups=...

4️⃣ System Enumeration

Check system information:

msfadmin@metasploitable:~$ uname -a
Linux metasploitable 2.6.24-16-server #1 SMP ...


Explore the filesystem:

msfadmin@metasploitable:~$ ls -la ~


Check for installed packages and services:

msfadmin@metasploitable:~$ cat /etc/issue
Ubuntu 8.04

msfadmin@metasploitable:~$ lsb_release -a
Distributor ID: Ubuntu
Release: 8.04
Codename: hardy


Check network interfaces:

msfadmin@metasploitable:~$ ifconfig


Check active listening ports (some require root privileges):

msfadmin@metasploitable:~$ netstat -tulpn


Check running processes:

msfadmin@metasploitable:~$ ps aux | head


Inspect important configuration directories:

msfadmin@metasploitable:~$ ls -la /etc


Inspect user accounts:

msfadmin@metasploitable:~$ cat /etc/passwd


The msfadmin user has sudo privileges:

msfadmin@metasploitable:~$ sudo -l
User msfadmin may run the following commands on this host:
(ALL) ALL

5️⃣ Observations

Old OS & Services: Ubuntu 8.04, outdated services (Apache, MySQL, SSH, Samba)

Open Ports: FTP, SSH, Telnet, HTTP, MySQL, PostgreSQL, etc.

Sudo Access: msfadmin can run all commands via sudo

Writable Home Directory: User’s home folder contains multiple files and folders

Potential Misconfigurations: World-writable files, outdated services, known vulnerabilities

This setup is ideal for understanding post-login enumeration and privilege escalation planning.

6️⃣ Lab Learnings

Network Scanning: Using nmap to identify reachable hosts and open services.

Service Enumeration: Determining versions and vulnerabilities of running services.

Post-Login Enumeration: Collecting system info (uname, id, ls -la, cat /etc/passwd), networking info (ifconfig, netstat), and process info (ps aux).

Privilege Awareness: Checking sudo -l and user groups to assess privilege escalation opportunities.

Documentation Skills: Properly documenting findings step-by-step.

This demonstrates the initial phase of penetration testing: discover → enumerate → plan escalation.

7️⃣ Next Steps (Conceptual)

Identify potential privilege escalation vectors based on misconfigurations, outdated services, and writable directories.

Research known vulnerabilities in detected software versions.

Document and report findings for a professional penetration test case study.

🔗 References

Metasploitable Project

Nmap Documentation

Kali Linux Documentation
