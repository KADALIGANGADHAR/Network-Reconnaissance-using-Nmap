# 🔍 Network Reconnaissance using Nmap & Wireshark

## 📘 Overview
This project was completed as part of a Cybersecurity Internship to demonstrate basic network reconnaissance skills using **Nmap** and **Wireshark**. The goal was to scan the local network for live hosts and open ports, and analyze network activity using packet capture tools.

---

## 🧰 Tools Used
- 🛠️ **Nmap** – Network mapping and port scanning
- 🧪 **Wireshark** – Packet-level traffic analysis
- 💻 **Kali Linux** – Operating System used for testing

---

## 🎯 Objective
- Identify live devices in the local network (`192.168.1.0/24`)
- Scan for open TCP ports using a SYN scan
- Analyze scan traffic using Wireshark
- Document observations, risks, and recommendations

---

## 🔎 Scan Methodology

### Step 1: Local IP & Subnet
#### ```ip a  or Ifconfig```
![kali-linux-2024 4-vmware-amd64-2025-06-23-15-53-25](https://github.com/user-attachments/assets/ec6b1e8c-96ff-4542-9aec-8b1389735750)

### Step 2: Perform Full SYN Scan
![kali-linux-2024 4-vmware-amd64-2025-06-23-15-53-33](https://github.com/user-attachments/assets/c8e55092-7869-4c4a-8df3-e0deb6d25286)

### Step 3: Generate HTML Report
![kali-linux-2024 4-vmware-amd64-2025-06-23-15-54-19](https://github.com/user-attachments/assets/3147ae6a-0fb6-441d-99f2-c2b63f8b5daf)

### Step 4: Analyze Packets Using Wireshark
- ***Interface: eth0***

- ***Filter used: tcp.flags.syn == 1 && tcp.flags.ack == 0***

- ***Captured TCP SYN packets sent during the Nmap scan***
![kali-linux-2024 4-vmware-amd64-2025-06-23-14-29-46](https://github.com/user-attachments/assets/ba723210-3aef-4fa7-b137-3fea961d61da)

### 📄 Scan Results
 ***✅ Hosts were found to be alive.***

 ***⚠️ No open TCP ports were detected on scanned devices***

 ***Likely causes:***

- ***Devices had firewalls blocking incoming connections***

- ***No services were listening on common TCP ports***

- ***Host-based security measures prevented scans***

### 🔹 Wireshark - SYN Packet Capture
![kali-linux-2024 4-vmware-amd64-2025-06-23-14-29-46](https://github.com/user-attachments/assets/a8042e92-23d8-49f2-acf6-4c98347014d4)
![kali-linux-2024 4-vmware-amd64-2025-06-23-18-59-47](https://github.com/user-attachments/assets/e05775f4-404c-4002-a40d-07226e68cac5)
![kali-linux-2024 4-vmware-amd64-2025-06-23-19-00-24](https://github.com/user-attachments/assets/687a513d-eba0-4a90-85b0-4affda0610ea)
### 🔹 Nmap HTML Report 
![kali-linux-2024 4-vmware-amd64-2025-06-23-15-52-32](https://github.com/user-attachments/assets/ed568078-f534-441b-80e4-fd6947d298e6)
![kali-linux-2024 4-vmware-amd64-2025-06-23-15-52-37](https://github.com/user-attachments/assets/be3e3509-2a91-494a-a3b9-697e70c78ec4)

### Risk Analysis
| Port | Service | Risk (if open)                        |
| ---- | ------- | ------------------------------------- |
| 22   | SSH     | Brute-force login attacks             |
| 80   | HTTP    | Web application vulnerabilities       |
| 445  | SMB     | Exploits like EternalBlue, ransomware |

 ***Although no open ports were found, real-world networks often expose services. Regular scans help identify and mitigate exposure.***
