# Elab_Day_1
# 🧪 Cyber Security Internship - Day 1: Network Scaninng using namp and wireshark

## ✅ Task Objective
Use **Wireshark** to monitor and analyze network traffic while performing a **Nmap TCP SYN scan** on the local network. Understand how scan traffic looks at the packet level.

---

## 🛠 Tools Used
- **Nmap**: For performing port scanning.
- **Wireshark**: For live packet capture and analysis.

---


## 🧵 Steps Performed

### 1️⃣ Started Wireshark
- Chose the active network interface (e.g., Wi-Fi or Ethernet).
- Began packet capture before scanning.

### 2️⃣ Ran Nmap Scan Simultaneously
```bash
nmap -sS -oN scan_result.txt 192.168.157.197/24
```
---
## Saved Result on scan_result.txt

## 📸 Wireshark Capture Screenshot

![Wireshark Scan Capture](./4.png)

---

## 🌐 Port 53 - DNS (Domain Name System)

### 🔹 What is Port 53?
Port **53** is the default port used for **DNS (Domain Name System)** traffic. DNS is the protocol responsible for translating domain names (like `www.google.com`) into IP addresses (like `142.250.190.4`) that computers can understand and route to.

---

### 🔧 Technical Details

| Protocol | Usage                         |
|----------|-------------------------------|
| UDP 53   | Standard DNS queries (fast, stateless) |
| TCP 53   | Used for DNS zone transfers and large queries |

---

### 🔐 Why is Port 53 Important?

- It is **critical for all internet communications**.
- Every time you open a website, a DNS query is sent to a DNS server via port 53.
- It is one of the most frequently used ports in the background of any internet activity.

---

### ⚠️ Security Concerns

- **DNS Spoofing / Poisoning**: Attackers can manipulate DNS responses to redirect users to malicious websites.
- **Open DNS resolvers** can be abused in **DDoS amplification attacks**.
- **Unencrypted DNS** traffic can be intercepted and monitored by attackers.

---

### ✅ Best Practices

- Ensure port 53 is open **only on DNS servers** and **not exposed publicly** unless necessary.
- Use secure alternatives like:
  - **DNS over HTTPS (DoH)**
  - **DNS over TLS (DoT)**
- Monitor and log all DNS traffic for unusual patterns.

---

### 🧠 Summary

Port 53 is essential for name resolution across the internet but must be secured and monitored due to its high value in both regular operation and exploitation.

## ⚠️ Potential Security Risks of Port 53 (DNS)

Port 53, while essential for DNS communication, can pose several security risks if improperly secured:

### 1. DNS Spoofing / Cache Poisoning
Attackers forge DNS responses to redirect users to malicious websites, leading to phishing, malware downloads, or data theft.

### 2. Data Exfiltration via DNS Tunneling
Sensitive data can be smuggled out of a network using encoded DNS queries and responses, bypassing firewalls.

### 3. DDoS Amplification Attacks
Misconfigured open DNS resolvers can be abused in large-scale Distributed Denial of Service (DDoS) attacks by amplifying traffic.

### 4. Exposure of Internal Infrastructure
Improper DNS server configuration can leak internal domain names and IPs, helping attackers map the internal network.

### 5. Lack of Encryption
Traditional DNS over UDP/TCP is unencrypted, allowing attackers to sniff DNS traffic and monitor user activity.

### 6. Unauthorized DNS Servers
If devices on a network are allowed to use external DNS servers, it bypasses corporate policies and introduces monitoring gaps.

---

### 🛡 Mitigation Strategies

- Block outbound DNS traffic except to authorized servers
- Use **DNSSEC**, **DoH**, or **DoT** for secure DNS resolution
- Monitor DNS traffic for anomalies
- Disable recursion on public-facing DNS servers
- Prevent DNS zone transfers unless explicitly needed and secured


