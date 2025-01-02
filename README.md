# README: Industrial Control Systems (ICS) Exploitation

## Overview
This project demonstrates an exploitation scenario within an Industrial Control System (ICS) setup involving three virtual machines: a chemical plant, a PLC, and a ScadaBR HMI. Using a Kali Linux virtual machine, the project explores reconnaissance, penetration testing, and exploitation techniques to achieve unauthorized access to the ScadaBR HMI interface.

## Objectives
1. Access the ScadaBR HMI interface by obtaining valid credentials.
2. Utilize tools and techniques such as browser developer tools, HTTP analysis, and network sniffing to perform attacks.
3. Demonstrate the vulnerabilities in ICS environments and explore additional methods for further exploitation.

## Steps to Reproduce
### 1. Setup Virtual Machines
- **Download and Configure VMs**:
  - Chemical Plant VM: Accessible at `http://192.168.95.10/`.
  - PLC VM: Provides dynamic readings once active.
  - ScadaBR VM: Access ScadaBR at `http://192.168.95.5:8080/ScadaBR`.
- **Kali Linux VM**:
  - Add to the same Host Network as the ICS VMs for monitoring and attacking.

### 2. Reconnaissance
- **Inspect Web Interface**:
  - Examine string lengths of username and password fields.
  - Analyze the login interface at `http://192.168.95.5:8080/ScadaBR/login.htm`.

- **Network Sniffing with Wireshark**:
  - Capture HTTP traffic and analyze unencrypted data to identify credentials.

### 3. Attack Techniques
- **Developer Tools**:
  - Inspect elements and analyze JavaScript triggers for password prompts.
- **Injection Testing**:
  - Use `commix` for aggressive reconnaissance and injection attempts.
  - Examine HTTP headers and tokens (e.g., JSESSIONID).
- **NMAP Scanning**:
  - Identify open ports and services running on target VMs.

### 4. Exploitation
- **Weak Password Testing**:
  - Username: `admin`.
  - Password: `cowboys`.
- **Traffic Analysis**:
  - Capture plaintext credentials via Wireshark during login attempts.

### 5. Validate Access
- Access the ScadaBR HMI interface and validate successful login using the discovered credentials.

## Tools and Techniques Used
1. **Tools**:
   - Wireshark: For traffic sniffing and analysis.
   - Commix: For injection testing.
   - NMAP: For port scanning.
   - Kali Linux utilities: For monitoring and attacks.
2. **Techniques**:
   - HTTP traffic analysis for plaintext credentials.
   - Reconnaissance using developer tools.
   - Injection and dictionary attacks.

## Key Findings
- The ScadaBR HMI was vulnerable to plaintext HTTP traffic interception, enabling the capture of credentials.
- Weak password policies (e.g., `admin:cowboys`) facilitated unauthorized access.
- Injection attempts and HTTP header analysis revealed the extent of security measures.

## Additional Work
- Conducted dictionary and wordlist attacks to test credential strength.
- Verified vulnerabilities using Metasploit and other penetration testing tools.

## Results
- Successfully accessed the ScadaBR HMI interface with the credentials:
  - **Username**: `admin`
  - **Password**: `cowboys`

## Conclusion
This project highlights critical vulnerabilities in ICS environments, emphasizing the importance of secure protocols, robust authentication mechanisms, and regular penetration testing to safeguard against exploitation.

---

**Note**: This project is for educational purposes only and should not be replicated outside a controlled lab environment.
