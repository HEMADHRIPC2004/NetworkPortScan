# NetworkPortScan

## 🎯 Objective
To perform basic network reconnaissance by scanning local devices and identifying open ports using **Nmap** and analyzing packets with **Wireshark**.

---

## 🛠️ Tools Used
- **Nmap** – for port scanning
- **Wireshark** – for packet capture and filtering
- **WSL (Ubuntu on Windows)** – terminal environment

---

## 📶 Steps Followed

### 1. Find Local IP Address and Subnet
Used the following command to find the local IP range:
```bash
ip a
```
Identified subnet: `172.24.0.0/20`

---

### 2. Perform TCP SYN Scan Using Nmap
Command used:
```bash
nmap -sS 172.24.0.0/20
```
Saved results as:
```bash
nmap -sS 172.24.0.0/20 -oN scan_results.txt
```

---

### 3. Analyze Packets with Wireshark
Captured packets during the scan and applied the filter:
```
tcp.flags.syn == 1 && tcp.flags.ack == 0
```
This shows SYN packets sent by Nmap during the scan.

---

### 4. Identify Common Services
Some common ports and services observed:
- `22` → SSH
- `80` → HTTP
- `443` → HTTPS
- `445` → SMB (file sharing)
- `3306` → MySQL
- 
---

### 5. Recognize Security Risks
Examples of risks discovered:
- **Port 445 (SMB)** – vulnerable to exploits like EternalBlue
- **Port 23 (Telnet)** – insecure plaintext protocol if found open
- **Open but unused ports** – potential backdoors

---

## 📁 Repository Contents

```
/NetworkPortScan/
├── screenshots/
│   ├── wireshark_syn_packets.png
│   └── nmap_scan_output.png
├── scan_results.txt
├── commands used.txt
└── README.md
```

---

## ✅ Final Summary

This task helped me understand basic network reconnaissance techniques using tools like **Nmap** and **Wireshark**. I learned how to:

- Identify my local IP address and subnet
- Perform a **TCP SYN scan** across a local network
- Analyze **packet-level behavior** using Wireshark filters
- Recognize services based on open ports (like SSH, HTTP, SMB)
- Identify potential security risks (e.g., open SMB or Telnet)
- Save scan results and organize them in a project-ready format

By documenting each step, capturing evidence, and pushing all artifacts to GitHub, this task improved both my **technical skills** and **documentation practice** — essential for any cybersecurity or networking role.
