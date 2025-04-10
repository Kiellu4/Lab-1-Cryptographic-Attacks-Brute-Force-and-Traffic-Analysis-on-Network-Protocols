# Network Protocol Vulnerabilities Lab

## A. Objective

The goal of this lab is to explore the vulnerabilities of common network protocols (FTP, TELNET, SSH, HTTP) by performing brute force attacks to recover passwords and then using those credentials to sniff network traffic.  
You will also analyze the security of these protocols and propose mitigation strategies.

---

## B. Lab Tasks

### 1. Enumerate the Vulnerable VM to Discover Usernames
- Identify potential usernames for brute force attacks.
- Document the usernames found.

### 2. Perform Brute Force Attacks

#### 2.1. FTP, TELNET, and SSH
- Use tools like **Hydra**, **Medusa**, or **NetExec** to perform brute force attacks against:
  - FTP
  - TELNET
  - SSH

#### 2.2. HTTP
- Use **Burp Intruder** to automate brute force attacks against an HTTP login page.
- Configure Intruder to test a list of usernames and passwords.
- Analyze the results to
