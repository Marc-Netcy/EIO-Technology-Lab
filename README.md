# EIO-Technology-Lab 
# **Lab Using OSINT Tools**


---
# Use SpiderFoot
SpiderFoot is an automated OSINT scanner. It is included with Kali. SpiderFoot queries over 1000 open-information sources and presents the results in an easy-to-use GUI. SpiderFoot can also be run from a console. SpiderFoot seeds its scan with one of the following:

- **Domain Names**
- **IP addresses**
- **Subnet addresses**
- **Autonomous System Numbers** (ASN)
- **Email addresses**
- **Phone numbers**
- **Personal names**

  SpiderFoot offers the option of choosing scans based on use case, required data, and by SpiderFoot module. The use cases are:

+ **All – Get every possible piece of information about the target. This use case can take a very long time to complete.**
+ **Footprint – Understand the target’s network perimeter, associated identities and other information that is yielded by extensive web crawling and search engine use.**
+ **Investigate – This is or targets that you suspect of malicious behavior. Footprinting, blacklist lookups, and other sources that report on malicious sites will be returned.**
+ **Passive – This type of scan is used if it is undesirable for the target to suspect that it is being scanned. This is a form of passive OSINT.**

In a terminal, enter the following command:

┌──(kali㉿Kali)-[~]

└─$ spiderfoot -l 127.0.0.1:5001

<img width="1257" height="631" alt="1" src="https://github.com/user-attachments/assets/2bfc1350-277e-4304-962c-8194a03994df" />

The command should run without errors. Open a browser and enter the IP address and port number for the SpiderFoot GUI. You will see the SpiderFoot interface appear. You can explore it to know more about it.

Using the -h (help) option, it display the command-line help for SpiderFoot

Typical uses include:

- **Viewing available command-line options and arguments.**
- **Learning how to start the SpiderFoot web interface.**
- **Seeing options such as specifying the host, port, configuration, or modules.**
- **Checking the installed version's supported features.**

┌──(kali㉿Kali)-[~]

└─$ spiderfoot -h

<img width="1243" height="560" alt="2" src="https://github.com/user-attachments/assets/32e4bb2c-0480-4d33-adc1-489a84c593c2" />

# Investigate Recon-ng

Recon-ng is an open-source reconnaissance framework designed to automate Open Source Intelligence (OSINT) gathering. It provides a modular interface that resembles a penetration testing framework, making it useful for collecting publicly available information during authorized security assessments.

### What Recon-ng can do

Recon-ng helps security professionals gather information such as:

- **Domain and subdomain information**
- **WHOIS records**
- **DNS records**
- **Publicly available contact information**
- **Company and organization data**
- **Social media and other internet-facing information (depending on available modules and APIs)** 

It stores collected data in a local workspace, allowing you to organize and correlate findings.

### Key features
- **Workspaces: Keep separate investigations organized.**
- **Modules: Load different modules for specific OSINT tasks.**
- **Database: Automatically stores collected information.**
- **API integration: Supports many third-party data sources (some require API keys).**
- **Reporting: Export findings in various formats.**

### Typical workflow
- **Start Recon-ng.**

┌──(kali㉿Kali)-[~]

└─$ recon-ng

<img width="1270" height="661" alt="3" src="https://github.com/user-attachments/assets/7c2588d1-b59b-4b41-9463-91f4a062dc98" />

- **Create or select a workspace.**

┌──(kali㉿Kali)-[~]

└─$ workspace create (workspace-name)

<img width="391" height="59" alt="6" src="https://github.com/user-attachments/assets/b80d1c99-d540-48f5-b6c2-9c168dbc246e" />

- **List available modules.**

┌──(kali㉿Kali)-[~]

└─$ marketplace search

<img width="1275" height="609" alt="8" src="https://github.com/user-attachments/assets/02ac22ad-6f57-4417-bf9a-2f879ca5666d" />

- **Install a module.**

┌──(kali㉿Kali)-[~]

└─$ marketplace install (module-name)

<img width="663" height="77" alt="11" src="https://github.com/user-attachments/assets/aac646a9-819d-433a-a3f6-9602a7f0bf62" />

- **Load a module.**

┌──(kali㉿Kali)-[~]

└─$ modules load (module-name)

<img width="406" height="39" alt="15" src="https://github.com/user-attachments/assets/32b120e7-1595-4a2e-b905-b0ac9cdd10cc" />

- **Set a target.**

┌──(kali㉿Kali)-[~]

└─$ option set SOURCE (target)

<img width="557" height="40" alt="17" src="https://github.com/user-attachments/assets/2f8d8f75-c5ab-424f-9517-c9187743e4a1" />

- **Run the module.**

┌──(kali㉿Kali)-[~]

└─$ run

<img width="526" height="583" alt="19" src="https://github.com/user-attachments/assets/325ec3f6-e2f6-4b55-96bb-ca8ef60a88f0" />

### Common use cases
- **Authorized penetration testing**
- **Security assessments**
- **Attack surface discovery**
- **Threat intelligence**
- **Asset inventory**
- **Academic cybersecurity training**

