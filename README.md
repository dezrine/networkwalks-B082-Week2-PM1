<div align="center">

# 🔐 FOOTPRINTING & RECONNAISSANCE
## ATTACKS WITH MULTIPLE KALI TOOLS

<img src="https://img.shields.io/badge/WEEK-2-8A2BE2?style=for-the-badge" alt="Week 2"><img src="https://img.shields.io/badge/MODULE-1-6f42c1?style=for-the-badge" alt="Module 1"><img src="https://img.shields.io/badge/CYBERSECURITY-LAB-8A2BE2?style=for-the-badge&logo=hackthebox&logoColor=white" alt="Cybersecurity Lab">

<img src="https://img.shields.io/badge/FOOTPRINTING-6f42c1?style=for-the-badge" alt="Footprinting"><img src="https://img.shields.io/badge/RECONNAISSANCE-8A2BE2?style=for-the-badge" alt="Reconnaissance"><img src="https://img.shields.io/badge/OSINT-6f42c1?style=for-the-badge" alt="OSINT"><img src="https://img.shields.io/badge/INFO%20GATHERING-8A2BE2?style=for-the-badge" alt="Information Gathering">

<img src="https://img.shields.io/badge/KALI-LINUX-6f42c1?style=for-the-badge&logo=kalilinux&logoColor=white" alt="Kali Linux"><img src="https://img.shields.io/badge/HOST-macOS-8A2BE2?style=for-the-badge&logo=apple&logoColor=white" alt="macOS"><img src="https://img.shields.io/badge/VIRTUALIZATION-UTM-6f42c1?style=for-the-badge" alt="UTM"><img src="https://img.shields.io/badge/LINUX-ENVIRONMENT-8A2BE2?style=for-the-badge&logo=linux&logoColor=white" alt="Linux">

<img src="https://img.shields.io/badge/ETHICAL-HACKING-6f42c1?style=for-the-badge" alt="Ethical Hacking"><img src="https://img.shields.io/badge/PENETRATION-TESTING-8A2BE2?style=for-the-badge" alt="Penetration Testing"><img src="https://img.shields.io/badge/NETWORK-RECON-6f42c1?style=for-the-badge" alt="Network Recon">

<img src="https://img.shields.io/badge/PROGRAM-NETWORK%20WALKS-6f42c1?style=for-the-badge" alt="Network Walks"><img src="https://img.shields.io/badge/INSTRUCTOR-WAQAS%20KARIM%20(CCIE)-8A2BE2?style=for-the-badge&logo=cisco&logoColor=white" alt="Waqas Karim CCIE"><img src="https://img.shields.io/badge/BY-DESRINE%20HARRIPAUL-6f42c1?style=for-the-badge&logo=github&logoColor=white" alt="Desrine Harripaul">

**WEEK 2 • PROJECT MODULE 1 [ELECTIVE]**  
*Kali Linux 🐉 • macOS 🍎 • Footprinting 🔎 • Reconnaissance 🌐*

</div>

---

## 📌 Project Overview

This **Week 2 – Project Module 1** lab focuses on performing **footprinting and reconnaissance attacks using multiple Kali Linux tools**.

The lab demonstrates information-gathering and reconnaissance techniques from a **Kali Linux attack machine hosted on macOS**.
Reconnaissance (also called as footprinting) is the first step in any real attack or security test. Before
touching a target, an attacker quietly collects as much public information about it as possible. This
includes who owns the domain, its real IP address, the hosting provider, the web technologies it
runs, its DNS and mail records, and whether a firewall is protecting it. All of this comes from
information the target has already made public, so the target never even knows it is being studied.
This is why recon is powerful and very hard to detect.

## 🖥️ Lab Environment

| Component | Configuration |
| :--- | :--- |
| **Host OS** | macOS 🍎 |
| **Attack Machine** | Kali Linux 🐉 |
| **Virtualization** | UTM |
| **Project** | Week 2 – Module 1 |
| **Focus** | Footprinting & Reconnaissance |
| **Program** | Network Walks |

# Step 1: Run WHOIS to Find the Domain Registration Details
<strong>Error:</strong> <img width="1588" height="166" alt="image" src="https://github.com/user-attachments/assets/ce0724de-8458-47d9-9b4b-55783c14cf22" />

<strong>Steps to fix: </strong>

- Run: ping -c 4 8.8.8.8 <br>

<strong>Error:</strong> <img width="774" height="156" alt="image" src="https://github.com/user-attachments/assets/2c42faad-3030-4ae7-9675-9383589826b7" />

<strong> Solution: </strong>
- Switch from manual to automatic
- Recconect the interface
<img width="2336" height="1504" alt="image" src="https://github.com/user-attachments/assets/79ac06d8-89ee-43ca-85a3-796dcebb4761" />

<strong>Correct Output: </strong>
- Check new IP and Gateway
<img width="1414" height="450" alt="image" src="https://github.com/user-attachments/assets/02de082c-25bd-40fa-9f16-563eeb864354" />


<strong> Final Output: <img width="1440" height="841" alt="Screenshot 2026-08-20 at 7 52 08 PM" src="https://github.com/user-attachments/assets/a88f29be-6f2b-4e7d-ace8-b0670a8bf683" />
</strong>

<strong>Purpose:</strong> The purpose of this step is to use the WHOIS lookup tool to gather publicly available domain registration information about the target domain, including registrar details, registration and expiration dates, domain status, and available name server information. whois reveals the registrar, registration and expiry dates, and name servers. Here the name servers point to HostGator, so an attacker instantly learns the hosting provider. Registration dates and abuse contacts help with social engineering and planning.

<strong>Status:</strong> Completed ✅

# Step 2: Run whatweb to fingerprint the web technologies.
<img width="2832" height="590" alt="image" src="https://github.com/user-attachments/assets/32f289c1-77cb-4395-8edb-7ae82bba475a" />

<strong>Purpose:</strong> The purpose of this step is to use WhatWeb to fingerprint the target website and identify the web technologies it uses, such as the web server, content management system (CMS), frameworks, programming languages, libraries, and other detectable technologies. whatweb exposes the exact software and versions (here Wordpress 7.0.4 and WP Download Manager 3.3.58). An attacker looks these versions up in vulnerability databases to find known exploits. It also leaks the server IP and an email address.

<strong>Status:</strong> Completed ✅

# Step 3: Run nslookup to recolve the domain to its IP address.
<img width="1228" height="336" alt="image" src="https://github.com/user-attachments/assets/dbce9a9f-0c56-46ea-bb0c-18ac6348c47e" />

<strong>Purpose:</strong> The purpose of this step is to use nslookup to query the Domain Name System (DNS) and resolve the target domain name to its associated IP address. This helps identify the server or network infrastructure associated with the target website. The results may also reveal DNS information that can be useful during the footprinting and reconnaissance process, such as the IP address hosting the domain. This information can be used in later stages of the lab to perform additional authorized reconnaissance on the identified host. nslookup turns a domain name into its real IP address (192.232.216.135). Knowing the IP lets an attacker scan the server directly, look up other sites on the same IP, and map the target's
infrastructure.

<strong>Status:</strong> Completed ✅

# Step 4: Run curl -l to read the HTTP response headers.
<img width="2822" height="588" alt="image" src="https://github.com/user-attachments/assets/ab03caf3-dab0-4eb7-94d8-3bece9cddea5" />

<strong>Purpose:</strong> The purpose of this step is to use curl with the `-I` option to retrieve and examine the HTTP response headers returned by the target web server without downloading the full webpage. These headers can reveal useful information such as the HTTP status code, web server software, content type, redirects, caching configuration, cookies, and security-related headers. During footprinting and reconnaissance, exposed server information may help identify the technologies supporting the website and provide additional details about the target's web infrastructure. If software or version information is disclosed, it can be compared against known vulnerability databases during an authorized security assessment. HTTP headers leak the web server, caching stack and hidden endpoints (here the WordPress REST API at /wp-json/). Attackers read headers to fingerprint the stack and find entry points without even loading the full page.

<strong>Status:</strong> Completed ✅

# Step 5: Run wafw00f to detect a Web Application Firewall.
<img width="1554" height="572" alt="image" src="https://github.com/user-attachments/assets/07789828-9e10-4c54-9254-50d177b63597" />

<strong>Purpose:</strong> The purpose of this step is to use wafw00f to determine whether the target website is protected by a Web Application Firewall (WAF) and, where possible, identify the specific WAF technology in use. In this case, wafw00f identified ModSecurity (SpiderLabs). Detecting a WAF provides important information about the target's security infrastructure because a WAF can inspect, filter, block, and log potentially malicious HTTP traffic. During an authorized security assessment, knowing that a WAF is present helps the tester understand which defensive controls are protecting the web application and appropriately plan subsequent testing while accounting for those controls.

<strong>Status:</strong> Completed ✅

# Step 6: Run dnsrecon to enumerate all DNS records.
<img width="1814" height="842" alt="image" src="https://github.com/user-attachments/assets/b540df19-83cc-4d25-94e5-3d49b88319d5" />

<strong>Purpose:</strong> The purpose of this step is to use dnsrecon to enumerate the target domain's DNS records and develop a more complete picture of its DNS infrastructure. DNSRecon can reveal information such as name servers, mail servers (MX records), IP addresses, SPF policies, service records, and other DNS-related information. In this case, the results revealed details including the DNS software version (BIND 9.16.23), email infrastructure, SPF configuration, and cPanel-related service records. During an authorized security assessment, these findings help identify the technologies and services associated with the target, understand its email and hosting configuration, and identify areas that may require further security analysis.

<strong>Status:</strong> Completed ✅

---

 # **WEEK 2 • PROJECT MODULE 1 [ESSENTIALS- Zenmap based Network Scanning]** 

# Task 1: Download and install Zenmap from official website on your Windows PC.
<img width="801" height="501" alt="Screenshot 2026-08-20 at 8 44 08 PM" src="https://github.com/user-attachments/assets/0d121e31-3faf-4bd4-92f2-8ed31714fa4e" />

<img width="1004" height="780" alt="image" src="https://github.com/user-attachments/assets/13bdc2f4-116f-44bf-8fc9-8a20f7313afc" />

<strong>Purpose:</strong> The purpose of this step is to install Nmap on the Windows virtual machine to provide the tools required for network discovery and scanning. Nmap can be used during an authorized security assessment to identify active hosts, open ports, running services, and other information about devices on a network. Installing Nmap prepares the Windows VM for the network scanning portion of the lab and provides access to the required scanning capabilities.

<strong>Status:</strong> Completed ✅

# Task 2: Find your local IP address & your LAN subnet.
<img width="1986" height="778" alt="image" src="https://github.com/user-attachments/assets/36d6b917-b2b7-4b96-8733-a286f1ee4669" />

<strong>Purpose:</strong> The purpose of this step is to identify the local IP address assigned to the Windows VM and determine the LAN subnet to which it belongs. Understanding the IP address and subnet helps establish the range of addresses that make up the local network and provides the information needed to define the appropriate target range for authorized Nmap network scanning. This also reinforces an understanding of IP addressing, subnet masks, and how devices are organized and communicate within a local network.

<strong>Status:</strong> Completed ✅

# Task 3: Find the list of live hosts/PC's in your IP subnet.
<img width="1376" height="1364" alt="image" src="https://github.com/user-attachments/assets/f0b33239-6532-41a0-b85d-ac94829b27e6" />
<img width="1364" height="1364" alt="image" src="https://github.com/user-attachments/assets/8dda0120-7454-4851-83fd-95ea5d2b9c8c" />


# Task 4: How many hosts are live in your subnet.
<strong> DQ: How many hosts are live in your subnet? 2 Hosts are live at this subnet</strong>

# Task 5: What are the IP addresses of the live hosts?
192.168.64.1
192.168.64.3

# Task 6: What are the MAC addresses of the live hosts?
192.168.64.1 → A2:78:17:A8:77:64

# Task 7: Display & save the output topology in PDF Format on your desktop
<img width="2112" height="1500" alt="image" src="https://github.com/user-attachments/assets/957d403e-fd67-4e2b-bba1-1531e6c3645e" />

# Video Simulation

# 📚 Summary of What I Learned

# ELECTIVE-WK2-PM1
Throughout this footprinting and reconnaissance lab, I gained practical experience using multiple Kali Linux tools to collect and analyze information about a target. In addition to learning how to use reconnaissance tools, I also developed troubleshooting skills by identifying and resolving networking issues within my Kali Linux virtual machine.

## 🔧 Troubleshooting & Problem Solving

One of the most important lessons from this lab came from troubleshooting my Kali Linux network connection. When I initially attempted to run WHOIS, I received a **"Temporary failure in name resolution"** error.

Further testing with:

<pre>
ping -c 4 8.8.8.8
</pre>

returned a **"Network is unreachable"** message. This helped me determine that the problem was not simply DNS resolution.

I used commands such as:

<pre>
ip addr
ip route
nmcli device status
nmcli connection show
ipconfig
</pre>

to investigate the network configuration.

Through this process, I discovered that the Kali Linux network interface had been manually assigned an IP address but had **no default gateway or DNS configuration**. Although UTM was configured to use a **Shared Network**, Kali's manual IPv4 configuration prevented it from receiving the necessary network settings automatically.

I resolved the issue by changing the network configuration from **manual addressing to DHCP**, allowing Kali to automatically obtain an IP address, default gateway, routing information, and DNS configuration.

After making the change, Kali received a new IP address and a valid default route, restoring network connectivity and allowing me to continue the footprinting exercises.

> 💡 **Key Lesson:** Successful cybersecurity testing requires more than knowing security tools. Understanding networking, routing, DNS, and how to troubleshoot connectivity problems is equally important.

---

## 🔎 Footprinting & Reconnaissance Skills

During the lab, I gained hands-on experience with several reconnaissance tools and learned how each tool reveals different information about a target.

### WHOIS
I learned how WHOIS can be used to examine publicly available domain registration information, including registrar information, registration dates, name servers, and domain status.

### WhatWeb
I learned how WhatWeb fingerprints websites to identify technologies such as web servers, content management systems, plugins, frameworks, and potentially exposed software versions.

### nslookup
I learned how nslookup queries DNS to resolve a domain name to its associated IP address. This demonstrated how DNS information can help map the infrastructure associated with a target.

### curl
I learned how `curl -I` can retrieve HTTP response headers without downloading the complete webpage. These headers can provide information about the web server, redirects, cookies, caching, and security configurations.

### wafw00f
I learned how wafw00f can identify whether a website is protected by a Web Application Firewall (WAF). Detecting technologies such as ModSecurity provides insight into the defensive controls protecting a web application.

### DNSRecon
I learned how DNSRecon can enumerate DNS information and reveal records associated with a target's infrastructure, including name servers, mail servers, SPF policies, service records, IP addresses, and other DNS-related information.

---

## 🧠 Key Takeaways

- Footprinting is an important first stage of a cybersecurity assessment.
- Different reconnaissance tools reveal different pieces of information about the same target.
- Combining results from multiple tools provides a more complete understanding of the target's infrastructure.
- DNS records can reveal valuable information about hosting, email, and network infrastructure.
- Web technologies and exposed software versions can provide useful information during an authorized security assessment.
- HTTP headers can reveal information that may not be immediately visible from the webpage itself.
- Web Application Firewalls provide an additional defensive layer that can detect, filter, and log suspicious web traffic.
- Understanding IP addressing, DNS, routing, gateways, and DHCP is essential when working with Kali Linux.
- Error messages are valuable troubleshooting clues and can help isolate whether a problem involves DNS, routing, connectivity, or application configuration.
- Troubleshooting and documenting problems are important practical cybersecurity skills.

---

# Essentials
## 🌐 Network Scanning with Nmap & Zenmap

During this portion of the lab, I gained hands-on experience with <strong>Nmap and Zenmap</strong> on a Windows virtual machine. I learned how network scanning can be used during an authorized security assessment to discover active devices and better understand the structure of a local network.

### 🧠 What I Learned

I learned how to use the Windows <code>ipconfig</code> command to identify important network information, including my IPv4 address, subnet mask, and default gateway. My Windows VM was assigned the IPv4 address <code>192.168.64.3</code> with a subnet mask of <code>255.255.255.0</code>, which allowed me to determine that the local network was <code>192.168.64.0/24</code>.

I also learned how CIDR notation works and why the <code>/24</code> is important when defining a network range. Instead of scanning only one IP address, specifying <code>192.168.64.0/24</code> allowed Zenmap to perform host discovery across the authorized local subnet.

Using Zenmap's <strong>Ping Scan</strong> profile, I performed the equivalent of:

<pre>
nmap -sn 192.168.64.0/24
</pre>

The scan checked the subnet for active devices without performing a traditional port scan. From the results, I learned how to identify live hosts by looking for the <code>Host is up</code> message and the final Nmap scan summary.

### 🔎 Host Discovery Results

The scan examined <strong>256 IP addresses</strong> and identified <strong>2 live hosts</strong>:

<pre>
192.168.64.1
192.168.64.3
</pre>

I determined that:

- <code>192.168.64.1</code> was the <strong>default gateway</strong>.
- <code>192.168.64.3</code> was the <strong>Windows VM</strong> performing the scan.

This helped me understand that not every address within a subnet represents an active device. A subnet defines the available address range, while host discovery helps determine which addresses are actually responding on the network.

### 🖥️ IP Addresses vs. MAC Addresses

I also gained a better understanding of the difference between <strong>IP addresses</strong> and <strong>MAC addresses</strong>.

An IP address provides the logical network address used to communicate with a device, while a MAC address identifies a network interface at the data-link layer of the local network.

Zenmap identified the MAC address associated with the gateway:

<pre>
192.168.64.1 → A2:78:17:A8:77:64
</pre>

I also learned that Nmap may not display the MAC address of the computer performing the scan itself. In Windows, I can retrieve this information using:

<pre>
ipconfig /all
</pre>

and locate the <strong>Physical Address</strong> associated with the correct network adapter.

### 🔐 Key Takeaways

- I learned how to install and use <strong>Nmap/Zenmap on a Windows VM</strong>.
- I learned how to identify my <strong>IPv4 address, subnet mask, and default gateway</strong>.
- I learned how to calculate the appropriate network range from an IP address and subnet mask.
- I now better understand <strong>CIDR notation</strong>, including what <code>/24</code> represents.
- I learned how to use <strong>Zenmap Ping Scan</strong> for host discovery.
- I learned that <code>nmap -sn</code> performs host discovery without conducting a normal port scan.
- I learned how to determine the number of <strong>live hosts</strong> from Nmap's output.
- I learned how to distinguish between the <strong>gateway, scanning machine, and other network hosts</strong>.
- I developed a better understanding of the difference between <strong>IP addresses and MAC addresses</strong>.
- I learned that network scanning results must be interpreted alongside existing network configuration information rather than simply collecting the output.

> 💡 <strong>Key Lesson:</strong> This exercise showed me that network scanning is not simply about running a tool. Understanding IP addressing, subnetting, gateways, MAC addresses, and the meaning of the scan results is necessary to accurately map and analyze a network during an authorized security assessment.

# ©️ Copyright & Disclaimer

<div align="center">

### © 2026 Desrine Harripaul. All Rights Reserved.

**Week 2 Project • Module 1**  
**Footprinting & Reconnaissance Attacks with Multiple Kali Tools**

This project was completed as part of the **Network Walks Cybersecurity Program** under the instruction of **Waqas Karim (CCIE)**.

</div>

### ⚠️ Educational Use Disclaimer

The information, commands, screenshots, and techniques documented in this repository are provided for **educational and cybersecurity training purposes only**.

All reconnaissance and security-testing activities documented in this project should be performed only against systems, networks, and applications for which the tester has **explicit authorization**.

The author does not authorize or encourage the use of the information contained in this repository for unauthorized access, malicious activity, or testing against systems without permission.

---

<div align="center">

**🔐 FOOTPRINT • RECON • ENUMERATE • ANALYZE • DOCUMENT**

<img src="https://img.shields.io/badge/KALI-LINUX-6f42c1?style=flat-square&logo=kalilinux&logoColor=white">
<img src="https://img.shields.io/badge/macOS-HOST-6f42c1?style=flat-square&logo=apple&logoColor=white">
<img src="https://img.shields.io/badge/WEEK-2-6f42c1?style=flat-square">
<img src="https://img.shields.io/badge/MODULE-1-6f42c1?style=flat-square">
<img src="https://img.shields.io/badge/FOOTPRINTING-6f42c1?style=flat-square">
<img src="https://img.shields.io/badge/RECONNAISSANCE-6f42c1?style=flat-square">

<br>

**Created by Desrine Harripaul**

</div>
