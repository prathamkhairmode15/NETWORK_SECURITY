# Network Security Technologies

## 1. Introduction

Network Security Technologies are tools, protocols, and mechanisms used to protect data, systems, and networks from unauthorized access, attacks, and misuse.

They ensure:
- Confidentiality (data is not exposed)
- Integrity (data is not altered)
- Availability (systems remain accessible)

---

## 2. Core Network Security Technologies

---

### 2.1 Firewall

#### What it is:
A firewall acts as a barrier between a trusted internal network and untrusted external networks (like the internet).

#### How it works:
- Filters incoming and outgoing traffic
- Uses rules (allow/block based on IP, port, protocol)

#### Types:
- Packet Filtering Firewall
- Stateful Firewall
- Next-Generation Firewall (NGFW)

#### Real-world Example:
A company blocks all incoming traffic except HTTP (port 80) and HTTPS (port 443) to protect internal servers.

---

### 2.2 Intrusion Detection System (IDS)

#### What it is:
Monitors network traffic and detects suspicious activities.

#### Types:
- Signature-based IDS (detects known attacks)
- Anomaly-based IDS (detects unusual behavior)

#### Real-world Example:
Detecting repeated failed login attempts indicating a brute-force attack.

---

### 2.3 Intrusion Prevention System (IPS)

#### What it is:
An advanced version of IDS that can actively block threats.

#### Difference from IDS:
- IDS = Detect only
- IPS = Detect + Prevent

#### Real-world Example:
Automatically blocking an IP performing SQL injection attempts.

---

### 2.4 Virtual Private Network (VPN)

#### What it is:
Creates a secure encrypted tunnel over the internet.

#### How it works:
- Encrypts data before transmission
- Ensures secure remote access

#### Real-world Example:
Employees accessing company servers securely from home using VPN.

---

### 2.5 Encryption (Cryptography)

#### What it is:
Converts plaintext into ciphertext to protect data.

#### Types:
- Symmetric Encryption (same key)
- Asymmetric Encryption (public + private key)

#### Real-world Example:
HTTPS websites use encryption to secure user data like passwords and credit card details.

---

### 2.6 Secure Socket Layer (SSL) / Transport Layer Security (TLS)

#### What it is:
Protocols used to secure communication over networks.

#### Key Features:
- Data encryption
- Authentication
- Integrity verification

#### Real-world Example:
When you see a lock icon in your browser (HTTPS), SSL/TLS is protecting your connection.

---

### 2.7 Access Control

#### What it is:
Defines who can access what resources.

#### Types:
- Role-Based Access Control (RBAC)
- Mandatory Access Control (MAC)
- Discretionary Access Control (DAC)

#### Real-world Example:
Only admins can access database configurations, while users can only view data.

---

### 2.8 Network Address Translation (NAT)

#### What it is:
Maps private IP addresses to a public IP.

#### Benefits:
- Hides internal network structure
- Adds a layer of security

#### Real-world Example:
Your home Wi-Fi router uses NAT to allow multiple devices to share one public IP.

---

### 2.9 Proxy Server

#### What it is:
Acts as an intermediary between user and internet.

#### Functions:
- Hides user identity
- Filters requests
- Caches data

#### Real-world Example:
Organizations block social media using proxy filtering.

---

### 2.10 Anti-Malware / Antivirus

#### What it is:
Detects and removes malicious software.

#### Techniques:
- Signature-based detection
- Heuristic analysis

#### Real-world Example:
Blocking ransomware before it encrypts system files.

---

## 3. Advanced Security Technologies

---

### 3.1 Security Information and Event Management (SIEM)

#### What it is:
Collects and analyzes logs from multiple systems.

#### Purpose:
- Detect threats in real time
- Centralized monitoring

#### Real-world Example:
Detecting suspicious login attempts from different countries.

---

### 3.2 Data Loss Prevention (DLP)

#### What it is:
Prevents sensitive data from leaving the organization.

#### Real-world Example:
Blocking employees from emailing confidential files outside the company.

---

### 3.3 Zero Trust Security Model

#### Concept:
"Never trust, always verify"

#### Features:
- Continuous authentication
- Least privilege access

#### Real-world Example:
Even internal employees must verify identity for each access request.

---

## 4. Real-World Attack vs Technology Mapping

| Attack Type           | Technology Used to Prevent |
|----------------------|--------------------------|
| SQL Injection        | IPS, WAF                |
| DDoS Attack          | Firewall, Load Balancer |
| Phishing             | Email Security, DLP     |
| Malware              | Antivirus, IDS          |
| Data Breach          | Encryption, Access Control |

