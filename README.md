# Task 4: Firewall Configuration and Traffic Filtering using UFW (Kali Linux)

## Objective:
To gain hands-on experience in managing basic firewall rules using UFW on Kali Linux. This task simulates a real-world scenario where a security analyst must restrict insecure protocols such as Telnet and ensure critical services like SSH remain accessible.

---

## Tools & Environment:
- **Operating System:** Kali Linux (Rolling)
- **Firewall Tool:** UFW (Uncomplicated Firewall)
- **Testing Tool:** Telnet client

---

## Simulation Scenario:
Imagine you're setting up a server inside a corporate environment. Telnet is found to be running — an insecure protocol that sends data in plain text. As a security analyst, your job is to block this risky port (23), verify it’s blocked, and make sure secure access like SSH (port 22) still functions.

---

## Commands Executed:

### 1. Update System and Install UFW
```bash
sudo apt update
sudo apt install ufw -y
```

### 2. Enable UFW
```bash
sudo ufw enable
```

### 3. Check Current Rules
```bash
sudo ufw status verbose
```

### 4. Block Telnet Port (23)
```bash
sudo ufw deny 23
```

### 5. Test Block (Optional but Done)
```bash
sudo apt install telnet -y
telnet localhost 23
```
**Expected Result:** Connection refused or timeout due to blocked port.

### 6. Allow SSH Port (22)
```bash
sudo ufw allow 22
```
- Ensures remote access remains available if needed.

### 7. Remove Test Rule (Cleanup)
```bash
sudo ufw delete deny 23
```

### 8. Disable UFW (Optional)
```bash
sudo ufw disable
```

---

## Learnings:
- How to configure basic inbound rules using UFW
- Importance of blocking Telnet and using secure alternatives
- How to test and validate firewall configurations
- How to simulate traffic filtering scenarios like a real network analyst

---

## Pro Tip:
UFW is great for beginners but powerful enough to simulate **real-world filtering**, especially in pen-testing setups. This exercise mimics how companies block insecure services and enforce security through perimeter-level firewalls.

---

## Files Included:
- `firewall_commands.txt` – All commands used
- `README.md` – This file
- `firewall_screenshot.png` – Terminal screenshot

---

##  Conclusion:
Successfully blocked Telnet (port 23), allowed SSH (port 22), and verified traffic filtering using UFW — demonstrating essential firewall management skills required in cybersecurity operations.
