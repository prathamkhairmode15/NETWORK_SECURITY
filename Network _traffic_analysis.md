# Network Traffic Analysis Basics

## 1. Introduction

Network Traffic Analysis (NTA) is the process of capturing, inspecting, and analyzing network data packets to monitor performance, detect anomalies, and identify security threats.

In simple terms, it is like **observing the conversations happening inside a network** to understand:
- Who is communicating
- What data is being transferred
- Whether anything suspicious is happening

---

## 2. Why Network Traffic Analysis is Important

- Detect cyber attacks (e.g., DDoS, malware, data exfiltration)
- Monitor network performance
- Troubleshoot connectivity issues
- Ensure policy compliance
- Analyze bandwidth usage

---

## 3. Basic Concepts You Must Know

### 3.1 Packet
A packet is a small unit of data transmitted over a network.

### 3.2 Protocols
Rules that define how data is transmitted:
- HTTP/HTTPS → Web traffic
- TCP → Reliable communication
- UDP → Fast but unreliable communication
- ICMP → Used for ping

### 3.3 IP Address
Identifies a device on a network.

### 3.4 Port Number
Identifies a specific service:
- 80 → HTTP
- 443 → HTTPS
- 22 → SSH

---

## 4. How Network Traffic Analysis Works

### Step 1: Capture Traffic
Collect packets from the network using tools.

### Step 2: Filter Traffic
Focus on relevant packets using filters.

### Step 3: Inspect Packets
Analyze headers and payloads.

### Step 4: Identify Patterns
Look for:
- Unusual traffic spikes
- Unknown IP addresses
- Suspicious protocols

### Step 5: Take Action
- Block malicious IPs
- Fix misconfigurations
- Alert administrators

---

## 5. Practical Tools for Network Traffic Analysis

## 5.1 Wireshark (Most Important Tool)

### What it is:
A packet analyzer used to capture and inspect network traffic in real-time.

### How to Use:

#### Step 1: Install Wireshark
Download from official site and install.

#### Step 2: Select Interface
Choose:
- Wi-Fi
- Ethernet

#### Step 3: Start Capturing
Click "Start" → packets will begin capturing.

#### Step 4: Apply Filters

Examples:http
tcp
ip.addr == 192.168.1.1
tcp.port == 80


#### Step 5: Analyze Packet

Click any packet to see:
- Source IP
- Destination IP
- Protocol
- Data payload

---

## 5.2 tcpdump (Command Line Tool)

### What it is:
A powerful CLI tool for capturing packets.

### Basic Command: sudo tcpdump -i eth0

### Useful Examples:

Capture specific port: sudo tcpdump port 80

Capture specific IP: sudo tcpdump host 192.168.1.10


Save to file: sudo tcpdump -w capture.pcap


---

## 5.3 NetFlow / sFlow

Used in large networks to analyze traffic flow instead of full packet capture.

### Key Idea:
- Instead of capturing everything, it summarizes traffic
- Helps in monitoring bandwidth usage

---

## 5.4 Nmap (Network Scanner)

### Purpose:
- Discover devices
- Identify open ports

### Example: nmap -sS 192.168.1.0/24


---

## 6. Practical Example (Real Scenario)

### Scenario: Slow Internet Issue

#### Step 1:
Open Wireshark and start capturing

#### Step 2:
Apply filter: tcp


#### Step 3:
Look for:
- High traffic from a single IP
- Repeated requests

#### Step 4:
Identify problem:
- A device is downloading large files

#### Step 5:
Solution:
- Limit bandwidth or block device

---

## 7. Detecting Suspicious Activity

### Indicators of Attack:

- Too many requests (DDoS)
- Unknown external IP communication
- Data being sent to unusual locations
- Repeated failed login attempts

### Example Filters:

Suspicious traffic: tcp.flags.syn == 1 && tcp.flags.ack == 0


DNS queries: dns

---

## 8. Best Practices

- Always capture traffic in a controlled environment
- Use filters to avoid overload
- Save captures for later analysis
- Monitor regularly, not just once
- Combine multiple tools (Wireshark + Nmap)

---

## 9. Challenges

- Large volume of data
- Encrypted traffic (HTTPS)
- Requires deep understanding of protocols
- High resource usage

---

## 10. Conclusion

Network Traffic Analysis is a fundamental skill in:
- Cybersecurity
- Networking
- System administration

By using tools like Wireshark and tcpdump, you can:
- Monitor network activity
- Detect threats early
- Troubleshoot issues effectively

---

## 11. Quick Summary

- Capture → Filter → Analyze → Act
- Wireshark = GUI analysis
- tcpdump = CLI capture
- Nmap = network scanning
- Focus on patterns, not just packets
