# 🛡️ Metasploitable Penetration Testing Labs (1)
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




## 📌 Overview

This project documents hands-on penetration testing practice conducted against **Metasploitable 1** and **Metasploitable 2** virtual machines within a controlled lab environment. The objective of this lab is to demonstrate core penetration testing methodologies, including reconnaissance, enumeration, post-exploitation analysis, and privilege escalation planning.

All testing was performed **ethically and legally** on intentionally vulnerable machines for **educational and portfolio purposes only**.

---

The following penetration testing phases were followed:

1. **Network Discovery & Scanning**
2. **Service Enumeration**
3. **Initial Access**
4. **Post-Login Enumeration**
5. **Privilege Escalation Analysis**
6. **Documentation & Reporting**

---

## 5️⃣ Key Observations

* **Legacy Operating System & Services**
  The target system is running **Ubuntu 8.04** with several **outdated services**, including **Apache, MySQL, OpenSSH, and Samba**, which are known to contain publicly documented vulnerabilities.

* **Large Attack Surface**
  Multiple network services are exposed, such as **FTP, SSH, Telnet, HTTP, MySQL, and PostgreSQL**, significantly increasing the number of potential attack vectors.

* **Elevated User Privileges**
  The `msfadmin` user has **full sudo access**, allowing execution of commands with root-level privileges.

* **Writable User Environment**
  The user’s home directory contains numerous **readable and writable files and folders**, enabling further inspection and analysis.

* **Security Misconfigurations**
  Common weaknesses were identified, including **world-writable files**, deprecated software versions, and insecure default configurations.

This lab environment is ideal for practicing **post-login enumeration** and developing a structured approach to **privilege escalation planning**.

---

## 6️⃣ Lab Learnings

* **Network Scanning**
  Used **Nmap** to identify live hosts, open ports, and exposed services.

* **Service Enumeration**
  Enumerated running services and identified their versions to assess potential vulnerabilities.

* **Post-Login Enumeration**
  Gathered system, user, and process information using commands such as:
  `uname`, `id`, `ls -la`, `cat /etc/passwd`, `ifconfig`, `netstat`, and `ps aux`.

* **Privilege Awareness**
  Checked user privileges and escalation possibilities using **`sudo -l`** and group membership analysis.

* **Technical Documentation**
  Practiced documenting findings in a clear, step-by-step manner, aligned with professional penetration testing standards.

This lab demonstrates the **initial phases of a penetration test**:
**discover → enumerate → analyze → plan escalation**.

---

## 7️⃣ Next Steps (Conceptual)

* Identify possible **privilege escalation vectors** based on misconfigurations, outdated services, and writable directories.
* Research **known vulnerabilities** affecting the detected software versions.
* Document and present findings as a **professional penetration testing case study**.

---

## ⚠️ Legal & Ethical Disclaimer

This project was conducted in a **controlled lab environment** using deliberately vulnerable systems. No real-world systems were targeted. The techniques demonstrated here are strictly for **educational purposes** and should only be used on systems you own or have explicit permission to test.

---

## 🔗 References

* **Metasploitable Project**
  [https://sourceforge.net/projects/metasploitable/](https://sourceforge.net/projects/metasploitable/)

* **Nmap Documentation**
  [https://nmap.org/docs.html](https://nmap.org/docs.html)

* **Kali Linux Documentation**
  [https://www.kali.org/docs/](https://www.kali.org/docs/)

---

## 👤 Author

**Sandiso Mayekiso**
Cybersecurity & IT Engineer
🔗 GitHub: [https://github.com/SandisoMayekiso](https://github.com/SandisoMayekiso)
🔗 TryHackMe: [https://tryhackme.com/p/mayekisosandiso](https://tryhackme.com/p/mayekisosandiso)


