# Pyramid of Pain - Task Summary (SOC Level 1)

Practical analysis of the 6 levels of the Pyramid of Pain, with visual evidence.

---

## 🔵 1. Hash Values (Trivial)
**Objective**: Identify malicious files using their digital fingerprint.  
**Example**:  
- MD5 hash of a ransomware: `D1A008E3A606F24590A02B853E955CF7`  
**Screenshot**:  
![Hash Values](filename.png)  
**Why is it weak?** A hacker modifies the file → the hash changes instantly.

---

## 🟢 2. IP Addresses (Easy)
**Objective**: Block attackers' IP addresses.  
**Example**:  
- Malicious IP: `185.65.134.1` (United States, port 8080)  
- First DNS contacted: `c2.malware.com`  
**Screenshot**:  
![IP Address](firstadresse.png)
![dns](firstdns.png)  
**Problem**: The attacker uses a VPN → gets a new IP within 2 seconds.

---

## 🟡 3. Domain Names (Simple)
**Objective**: Detect fraudulent or lookalike domains.  
**Example**:  
- Punycode attack: `adıdas.de` (actually `xn--addas-o4a.de`)  
**Screenshot**:  
![Domain Names](redirection.png)  
**Defense**: Block domains that are similar to legitimate brands.

---

## 🟠 4. Host Artifacts (Annoying)
**Objective**: Detect traces left on infected hosts.  
**Example**:  
- Malicious file: `C:\Temp\stealer.exe`  
- Suspicious process: `regidle.exe`  
**Screenshot**:  
![Host Artifacts](vendorsmalicious.png)
**Impact**: The attacker must rewrite or relocate the malware.

---

## 🟠 5. Tools (Challenging)
**Objective**: Identify attacker-specific or reused tools.  
**Example**:  
- 58 out of 72 antivirus engines detect the file as malicious.  
**Screenshot**:  
![Vendors Detection](vendors_malicious.png)  
**Solution**: Use behavioral analysis to bypass signature-based detection.

---

## 🔴 6. TTPs (Tough)
**Objective**: Understand the attacker’s Tactics, Techniques, and Procedures (TTPs).  
**Example**:  
- Exfiltration technique: ID 9 (MITRE ATT&CK framework)  
- Tool used by the Chimera group: `Cobalt Strike`  
**Screenshot**:  
![TTPs](exfiltration.png)  
**Power**: Blocking TTPs forces the attacker to completely redesign their operations.

---

## 📊 Pyramid Overview
![Pyramid Overview](pyramidtask.png)

---

### 📌 Key Takeaways
- **Bottom of the pyramid** (Hash/IP): Easy to detect, but low value.  
- **Top of the pyramid** (TTPs/Tools): Harder to detect, but highly effective for long-term defense.  
- **SOC Strategy**: Gradually move upward in the pyramid to increase resilience and defense depth.
