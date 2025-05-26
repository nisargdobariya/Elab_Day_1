# Elab_Day_1
# 🧪 Cyber Security Internship - Task 5: Wireshark Traffic Analysis During Port Scan

## ✅ Task Objective
Use **Wireshark** to monitor and analyze network traffic while performing a **Nmap TCP SYN scan** on the local network. Understand how scan traffic looks at the packet level.

---

## 🛠 Tools Used
- **Nmap**: For performing port scanning.
- **Wireshark**: For live packet capture and analysis.

---

## 📸 Wireshark Capture Screenshot

![Wireshark Scan Capture](./4.png)

---

## 🧵 Steps Performed

### 1️⃣ Started Wireshark
- Chose the active network interface (e.g., Wi-Fi or Ethernet).
- Began packet capture before scanning.

### 2️⃣ Ran Nmap Scan Simultaneously
```bash
nmap -sS -oN scan_result.txt 192.168.157.197/24
