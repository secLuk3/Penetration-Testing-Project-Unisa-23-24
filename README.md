# 🛡️ Penetration Testing Project: HackTheBox - Bizness

This repository contains a full penetration testing assessment of the *Bizness* machine from [Hack The Box](https://app.hackthebox.com/machines/Bizness), conducted as part of the university course **Penetration Testing and Ethical Hacking** 23/24 at the **University of Salerno**.

## 📚 Project Information

- **Course**: Penetration Testing and Ethical Hacking  
- **University**: Università degli Studi di Salerno  
- **Student**: Luca Boffa  
- **Matricola**: 0522501521  
- **Academic Year**: 2023/2024  
- **Supervisor**: Prof. Arcangelo Castiglione  
- **Testing Period**: 30/06/2024 – 09/07/2024  
- **Methodology**: Black-box approach using the General Penetration Testing Framework

---

## 🧰 Tools & Technologies

- **OS**: Kali Linux 2024.2
- **Target Discovery**: `ping`, `nmap v7.94`
- **Vulnerability Mapping**:  
  - Nessus 10.7.4  
  - OpenVAS (GVM) 22.9.1  
  - Nikto v2.5.0s  
  - WhatWeb v0.5.5  
  - WafW00f v2.2.0  
  - Feroxbuster v2.10.4
- **Exploitation**:  
  - Python 3.11.9  
  - Netcat v1.10  
  - Apache OFBiz exploit: [CVE-2023-49070 PoC](https://github.com/abdoghazy2015/ofbiz-CVE-2023-49070-RCE-POC)  
  - ysoserial-all.jar
- **Post-Exploitation**:  
  - Apache Derby  
  - Custom SHA1 Cracker for OFBiz password

---

## 🔍 Methodology

The penetration test followed the standard 9-phase methodology:

1. **Target Scoping** – Define objectives, boundaries, and limitations  
2. **Information Gathering** – Basic OSINT and context setup  
3. **Target Discovery** – Host identification and OS fingerprinting  
4. **Enumeration** – Nmap scans (SYN, NULL, FIN, XMAS)  
5. **Vulnerability Mapping** – Nessus, OpenVAS, manual research  
6. **Exploitation** – Remote Code Execution via OFBiz RCE (CVE-2023-49070)  
7. **Privilege Escalation** – Exploiting weak OFBiz password hashing & Derby database  
8. **Maintaining Access** – Reverse shells & SSH key persistence  
9. **Reporting** – Final narrative and detailed vulnerability report

---

## 🚨 Key Findings

### 🔴 Critical
- **CVE-2023-49070** – Pre-auth RCE in Apache OFBiz ≤ 18.12.09  
- **CVE-2023-51467** – Bypass authentication & arbitrary code execution

### 🟠 High
- **Generic Blind SQL Injection**

### 🟡 Medium
- Deprecated TLS 1.0/1.1  
- JQuery XSS (< 3.5.0)  
- Weak SSL certificates (self-signed, untrusted)  
- Potential Clickjacking vulnerability

### 🔵 Low
- ICMP & TCP timestamp disclosures  
- Weak SSH MAC algorithms  
- Insecure admin password policy

---

## 🛠️ Remediation Suggestions

- Patch OFBiz to ≥ 18.12.10  
- Implement HTTPS with valid SSL certs  
- Disable legacy TLS protocols (1.0, 1.1)  
- Apply WAF and proper HTTP headers (e.g., X-Frame-Options)  
- Use secure password storage mechanisms (e.g., bcrypt)  
- Enforce strong password policies  
- Conduct regular audits and enable network monitoring tools

---

## 📎 References

- [CVE-2023-49070 - NIST](https://nvd.nist.gov/vuln/detail/CVE-2023-49070)  
- [CVE-2023-51467 - NIST](https://nvd.nist.gov/vuln/detail/CVE-2023-51467)  
- [Apache OFBiz SHA1 Cracker GitHub](https://github.com/...)  
- [Hack The Box - Bizness](https://app.hackthebox.com/machines/Bizness)

---

## 📌 Disclaimer

This repository is for educational purposes only. All testing was performed in a controlled environment on intentionally vulnerable systems. Do not attempt unauthorized testing on systems you do not own.

---

