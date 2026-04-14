# Firewall Configuration and Management

## 1. Introduction

A firewall is a network security system (hardware or software) that monitors and controls incoming and outgoing network traffic based on predefined security rules. It acts as a barrier between a trusted internal network and untrusted external networks like the Internet.

---

## 2. Types of Firewalls

### Packet Filtering Firewall

* Operates at Network Layer (Layer 3)
* Filters packets based on IP, port, protocol
* Fast but less secure

### Stateful Inspection Firewall

* Tracks connection states
* Allows only valid session packets
* More secure than stateless firewall

### Proxy Firewall (Application Layer)

* Works at Layer 7
* Acts as an intermediary
* Can inspect full data

### Next-Generation Firewall (NGFW)

* Includes:

  * Deep packet inspection
  * Intrusion prevention
  * Application awareness
* Used in modern enterprise security

---

## 3. Firewall Configuration

Firewall configuration defines rules that control traffic flow.

### Rule Structure

Each firewall rule includes:

* Source IP
* Destination IP
* Port number
* Protocol (TCP/UDP/ICMP)
* Action (ALLOW / DENY)

---

### Example Rules

Allow HTTP:

```
ALLOW TCP FROM ANY TO 192.168.1.10 PORT 80
```

Allow HTTPS:

```
ALLOW TCP FROM ANY TO 192.168.1.10 PORT 443
```

Block Telnet:

```
DENY TCP FROM ANY TO ANY PORT 23
```

Allow internal network:

```
ALLOW ALL FROM 192.168.1.0/24 TO ANY
```

---

### Linux Firewall Example (iptables)

Allow SSH:

```
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

Allow established connections:

```
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```

Block all incoming traffic:

```
iptables -P INPUT DROP
```

---

### Windows Firewall Example

```
New-NetFirewallRule -DisplayName "Allow HTTP" -Direction Inbound -Protocol TCP -LocalPort 80 -Action Allow
```

---

## 4. Firewall Management

Firewall management involves maintaining, monitoring, and updating firewall configurations.

### Key Activities

Rule Management:

* Add, update, delete rules
* Avoid redundant or conflicting rules

Log Monitoring:

* Detect suspicious activities
* Example: multiple failed logins → brute force attempt

Updates:

* Regularly update firewall software to fix vulnerabilities

Backup:

* Save configurations for recovery

Policy Review:

* Periodically audit and remove unused rules

---

## 5. Real-World Examples

### College Network

* Allow HTTP/HTTPS for students
* Restrict admin access to specific IPs
* Block gaming ports

### Company Web Server

* Allow ports 80 and 443
* Block unnecessary ports like 21 and 23

### Banking System

* Allow only trusted IP ranges
* Enable deep inspection
* Log all activities
* Use intrusion prevention systems

---

## 6. Interview Questions

What is a firewall?
→ A system that filters network traffic based on rules.

Difference between stateful and stateless firewall?
→ Stateless filters individual packets, stateful tracks sessions.

What is DMZ?
→ A separate network zone for public-facing servers.

What is default deny policy?
→ Block everything unless explicitly allowed.

Why block port 23?
→ Telnet is insecure and transmits data in plaintext.

---

## 7. Common Mistakes

* Allowing "ANY to ANY"
* Not updating rules
* Ignoring logs
* Wrong rule order
* Leaving unused ports open

---

## 8. Security Perspective

### Attacks Prevented

* Unauthorized access
* Port scanning
* Basic DDoS
* Malware communication

### Limitations

* Cannot stop insider threats
* Cannot detect encrypted attacks without inspection
* Cannot prevent social engineering

---

## 9. Best Practices

* Use least privilege principle
* Follow default deny policy
* Enable logging and monitoring
* Regularly update firewall
* Combine with IDS/IPS and SIEM tools

---

## 10. Conclusion

Firewall configuration and management are essential for securing networks. A properly configured firewall controls traffic, reduces attack surface, and protects systems, but must be actively managed and combined with other security layers.
