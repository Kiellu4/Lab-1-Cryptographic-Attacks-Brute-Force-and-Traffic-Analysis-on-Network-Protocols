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
