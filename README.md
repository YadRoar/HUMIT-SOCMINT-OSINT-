# Cybersecurity Lab & Report Log

This repository contains the documentation, evidence, and practical lab solutions developed throughout the cybersecurity course.

**Author:** Yadith Rodriguez 

---

## 📌 Table of Contents
1.  Introduction + Lab]
2.  Vectors + Risk (Defensive Mindset)]
3.  Footprinting (Attack Surface)]
4.  OSINT / SOCMINT (Defensive)]

---

## Introduction + Lab

### 🔍 Summary & Evidence
- **Public Information Gathering:** Performed public OSINT queries targeting the domain `telecable.com` and associated infrastructure (IP records, ASN 12946 TELECABLE Spain, exposed web services such as Apache/2.2.15, Ebroker Enterprise Server v3.0, among others).
- **Work Environment:** Initial setup of the virtualized environment (Kali Linux) and preparation of the tools directory.

### 📋 Pending Tasks & Objectives
- [x] Verify access to course resources.
- [x] Confirm core tools are installed and updated.
- [x] **Course Objective:** Establish solid foundations in offensive and defensive cybersecurity for vulnerability analysis and system hardening.


<img width="1432" height="796" alt="image" src="https://github.com/user-attachments/assets/7b93f966-64de-4697-bf86-23a0659184e0" />

--

##  Vectors + Risk (Defensive Mindset)

### 🔍 Summary & Evidence
- **Kali Linux & Maltego Graph Setup:** Created interactive graphs in Maltego for infrastructure discovery, mapping domain relationships (`telecable.com`, `cafebritt.com`), IP addresses, CIDR blocks, and harvesting email addresses.
- **Topology & Investigation:** Executed transforms (`Company Stalker`, `Footprint L1/L2`) to map the digital presence and potential external exposure vectors.

### 🛡️ Common Attack Vectors
1. **Phishing / Email Spoofing:** Corporate emails exposed in open sources.
2. **Exposure of Legacy Services:** Servers running outdated software versions accessible from the internet.
3. **Information Leaks in DNS/Whois:** Administrative contact data or critical infrastructure details visible in public records.
4. **Credential Stuffing / Password Reuse:** Leaked emails found in known data breaches (*HaveIBeenPwned*).
5. **Supply Chain Attacks:** Third-party subdomains or services linked to the organization.

---

<img width="891" height="812" alt="image" src="https://github.com/user-attachments/assets/4d9bce34-5ab4-4e4a-806e-51f3b0939145" />

---


##   Footprinting (Attack Surface)

### 🔍 Summary & Evidence
- **Profile & Nickname Searching:** Executed automated OSINT scripts (`findme`, `userSearch`, Sherlock/Maigret) analyzing the username `yadroar` across multiple web platforms (GitHub, Docker Hub, Instagram, TryHackMe, VirusTotal, among others).

### 🎯 Top Findings & Associated Risks
1. **Active Technical Profiles (GitHub / Docker Hub / PyPi):** 
   - *Risk:* Potential leakage of source code, API keys, or hardcoded credentials in public repositories.
2. **Learning / Certification Platforms (TryHackMe / GeeksforGeeks):** 
   - *Risk:* Disclosure of technical skill levels and tools used by the user/analyst.
3. **Social Media & Personal Platforms:** 
   - *Risk:* Exposure of answers to standard security questions or vectors for social engineering/spear phishing.

---


<img width="871" height="730" alt="image" src="https://github.com/user-attachments/assets/b5865aac-94d9-49bc-b69d-c5a9f9f32f68" />


---

##  OSINT / SOCMINT (Defensive)

### 🔍 Summary & Evidence
- **DNS & DMARC Record Analysis:** Used the `nuclei` tool to detect DMARC records, DKIM keys, and mail service identifiers (`OBJECT`).
- **Traffic Analysis with Wireshark & Nmap:** Captured UDP/NTP packets and performed TCP port scans (22, 80, 443) on `localhost`.

### 🛡️ Findings and Mitigation
- **Finding:** Exposure of DNS records lacking strict DMARC policies or management ports exposed locally.
- **Possible Abuse:** Email spoofing or brute-force attempts on the SSH service.
- **Mitigation:** Enforce strict DMARC policies (`p=reject`), implement proper SPF/DKIM records, and restrict access to management ports using firewall rules.

---

<img width="888" height="767" alt="image" src="https://github.com/user-attachments/assets/60f53dc6-c4b3-4355-ae07-b7bfa419279f" />


---

*Documentation generated as part of practical lab evidence.*
