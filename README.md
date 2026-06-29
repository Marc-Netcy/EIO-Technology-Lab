# EIO-Technology-Lab 
# 1. Using OSINT Tools
---
OSINT (Open Source Intelligence) tools are software applications or online services that collect and analyze information from publicly available sources. Security professionals, investigators, journalists, researchers, and organizations use them to gather intelligence without accessing private systems.

### Common OSINT tools

Here are two widely used OSINT tools and what they do:

| Tool | Purpose |
| ------ | -------- |
| SpiderFoot | Automates collection of information from many public data sources. |
| Recon-ng | Framework with modules for gathering and organizing OSINT data. |

## Use SpiderFoot
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

```text
┌──(kali㉿Kali)-[~]
└─$ spiderfoot -l 127.0.0.1:5001
```
<img width="1257" height="631" alt="1" src="https://github.com/user-attachments/assets/2bfc1350-277e-4304-962c-8194a03994df" />

The command should run without errors. Open a browser and enter the IP address and port number for the SpiderFoot GUI. You will see the SpiderFoot interface appear. You can explore it to know more about it.

Using the -h (help) option, it display the command-line help for SpiderFoot

Typical uses include:

- **Viewing available command-line options and arguments.**
- **Learning how to start the SpiderFoot web interface.**
- **Seeing options such as specifying the host, port, configuration, or modules.**
- **Checking the installed version's supported features.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ spiderfoot -h
```
<img width="1243" height="560" alt="2" src="https://github.com/user-attachments/assets/32e4bb2c-0480-4d33-adc1-489a84c593c2" />

## Investigate Recon-ng

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
  
```text
┌──(kali㉿Kali)-[~]
└─$ recon-ng
```
<img width="1270" height="661" alt="3" src="https://github.com/user-attachments/assets/7c2588d1-b59b-4b41-9463-91f4a062dc98" />

- **Create or select a workspace.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ workspace create (workspace-name)
```
<img width="391" height="59" alt="6" src="https://github.com/user-attachments/assets/b80d1c99-d540-48f5-b6c2-9c168dbc246e" />

- **List available modules.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ marketplace search
```
<img width="1275" height="609" alt="8" src="https://github.com/user-attachments/assets/02ac22ad-6f57-4417-bf9a-2f879ca5666d" />

- **Install a module.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ marketplace install (module-name)
```
<img width="663" height="77" alt="11" src="https://github.com/user-attachments/assets/aac646a9-819d-433a-a3f6-9602a7f0bf62" />

- **Load a module.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ modules load (module-name)
```
<img width="406" height="39" alt="15" src="https://github.com/user-attachments/assets/32b120e7-1595-4a2e-b905-b0ac9cdd10cc" />

- **Set a target.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ option set SOURCE (target)
```
<img width="557" height="40" alt="17" src="https://github.com/user-attachments/assets/2f8d8f75-c5ab-424f-9517-c9187743e4a1" />

- **Run the module.**
  
```text
┌──(kali㉿Kali)-[~]
└─$ run
```
<img width="526" height="583" alt="19" src="https://github.com/user-attachments/assets/325ec3f6-e2f6-4b55-96bb-ca8ef60a88f0" />

### Common use cases
- **Authorized penetration testing**
- **Security assessments**
- **Attack surface discovery**
- **Threat intelligence**
- **Asset inventory**
- **Academic cybersecurity training**

# 2. DNS Lookups

DNS lookups are the process of querying the Domain Name System (DNS) to translate human-readable domain names (such as example.com) into the information computers need to communicate over the internet, such as IP addresses.

### Why DNS lookups are important

When you enter a website address into your browser, your computer performs a DNS lookup to determine the server's IP address. Without DNS, you would have to remember numerical IP addresses instead of easy-to-read domain names.

Think of it like looking up someone's name in a phone directory to find their phone number.

### How a DNS lookup works

When you type www.example.com into your browser:

1. Your browser checks its cache
- **If it recently looked up the website, it may already know the IP address.**
2. Your operating system checks its DNS cache
- **If the browser doesn't have it, your computer checks its own stored DNS records.**
3. A DNS resolver is queried
- **If the address isn't cached, your computer asks a DNS resolver (usually provided by your internet service provider or a public DNS service).**
4. The resolver searches for the answer
- **It contacts different DNS servers until it finds the correct record:**
  - **Root DNS servers point to the correct top-level domain (TLD) servers.**
  - **TLD servers (such as those for .com, .org, or .net) point to the domain's authoritative DNS server.**
  - **Authoritative DNS servers provide the actual DNS records for the domain.**
5. The IP address is returned
- **The resolver sends the IP address back to your computer.**
- **Your browser then connects to that IP address to load the website.**

 ## Using nslookup to Obtain Domain and IP Address Information.

 Nslookup is a command line tool that is available in Linux and Windows. Its basic usage is to convert a domain name to an IP address. Nslookup has other functionality that can provide additional information.

### Investigating nslookup capabilities 

You can access the manual pages for **nslookup** by using the **man** command:

```text
┌──(kali㉿Kali)-[~]
└─$ man nslookup
```
<img width="1262" height="604" alt="1" src="https://github.com/user-attachments/assets/cdc1bf37-e721-4c82-be6a-cb7e02a0d517" />

By using the nslookup command with no options you will enter interactive mode. To exit interactive mode at any time, type exit to return to the CLI prompt. The CLI prompt changes to > to indicate that you are now in interactive mode and can enter the various nslookup commands.

```text
┌──(kali㉿Kali)-[~]
└─$ nslookup
```
Here I use the domain name cisco.com to resolve the domain name to an IP address. By default, the nslookup command queries A and AAAA records for the target.

<img width="477" height="226" alt="2" src="https://github.com/user-attachments/assets/2494f929-7917-42ed-93f5-7f18092c57a3" />

If you want to find the domain name servers configured for a domain, you can use the **set type** command to change the query type to “ns” to return the name server information.

```text
┌──(kali㉿Kali)-[~]
└─$ nslookup
> set type=ns
> cisco.com
```

<img width="518" height="255" alt="3" src="https://github.com/user-attachments/assets/adb7f1a2-e2b8-4e69-936e-7ad50a69d5ff" />

