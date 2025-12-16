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
<img width="800" height="427" alt="image" src="https://github.com/user-attachments/assets/27eaa743-e913-424c-91a2-8e1a760bb05a" />

2️⃣ Port Scanning

Scan specific ports to check if services are open:

<img width="565" height="259" alt="image" src="https://github.com/user-attachments/assets/42153f12-13c7-44bd-90d1-5386a11e8c99" />


<img width="696" height="467" alt="image" src="https://github.com/user-attachments/assets/8c0c0ba5-8f4d-4cc6-bddb-ff59994773f0" />


3️⃣ Post-Login via Telnet

Access the system using Telnet:

<img width="734" height="554" alt="image" src="https://github.com/user-attachments/assets/83474511-3e8d-4ff8-94a2-072711beda48" />


4️⃣ System Enumeration

Check system information:

<img width="710" height="556" alt="image" src="https://github.com/user-attachments/assets/ac9e2a7d-34ed-4af3-a583-e5044ba2a87f" />



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


