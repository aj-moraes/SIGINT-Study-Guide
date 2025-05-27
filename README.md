# SIGINT-Study-Guide

---

## 1. TELECOM 

### Key Concepts

- **IMSI (International Mobile Subscriber Identity)**  
  A unique identifier assigned to each mobile subscriber, stored on the SIM card. Used to authenticate users on cellular networks.

- **IMEI (International Mobile Equipment Identity)**  
  A 15-digit number unique to a mobile device, used to identify the hardware (phone) itself.

- **MSISDN (Mobile Station International Subscriber Directory Number)**  
  The actual phone number assigned to the SIM card. It’s what’s dialed to reach a mobile subscriber.

- **UE (User Equipment)**  
  The mobile device (e.g., smartphone, tablet) used by subscribers to access the network.

- **SIM (Subscriber Identity Module)**  
  A chip inside the mobile device containing the IMSI and cryptographic keys for authentication.

- **BTS (Base Transceiver Station)**  
  Equipment that facilitates wireless communication between user devices and the network.

- **BSC (Base Station Controller)**  
  Manages multiple BTSs. Handles radio resource management, call setup, and handovers.

- **RNC (Radio Network Controller) [3G Only]**  
  Equivalent to BSC in 3G networks. Manages Node Bs and handles mobility and call control.

- **MSC (Mobile Switching Center)**  
  Routes voice/data calls, SMS, and manages registration and handovers in circuit-switched networks.

- **SGSN (Serving GPRS Support Node)**  
  Manages data sessions, tracks user location, performs access control.

- **GGSN (Gateway GPRS Support Node)**  
  Connects mobile networks to external packet-switched networks like the internet.

- **AUC (Authentication Center)**  
  Validates SIM card credentials using IMSI and authentication algorithms.

- **HLR (Home Location Register)**  
  Stores permanent subscriber info like account status and service permissions.

- **VLR (Visitor Location Register)**  
  Temporarily stores subscriber info when roaming, pulled from the HLR.

- **EIR (Equipment Identity Register)**  
  Maintains white/black/graylists of device IMEIs.

- **LTE (Long-Term Evolution)**  
  4G broadband standard with high speeds and low latency (OFDMA and all-IP architecture).

- **5G (Fifth Generation Mobile Network)**  
  Ultra-low latency, massive connectivity, network slicing, beamforming, mmWave.

- **Timing Advance**  
  Synchronizes uplink transmission delays from different distances.

- **TDMA, CDMA, OFDMA**  
  - **TDMA**: Time slots per user  
  - **CDMA**: Code per user  
  - **OFDMA**: Subcarriers per user (used in LTE/5G)

---

### Network Topologies

#### 3G Network Topology
- **Architecture:** Hybrid (circuit + packet-switched)
- **Key Components:** UE, Node B, RNC, MSC, SGSN, GGSN
- **Data Flow:** UE → Node B → RNC → SGSN → GGSN → Internet

#### LTE (4G) Network Topology
- **Architecture:** All-IP, flat
- **Key Components:** UE, eNodeB, MME, SGW, PGW, HSS, PCRF
- **Data Flow:** UE → eNodeB → SGW → PGW → Internet

#### 5G Network Topology
- **Architecture:** Cloud-native, modular, service-based
- **Key Components:** UE, gNodeB, AMF, SMF, UPF, AUSF, UDM, PCF, NEF
- **Data Flow:** UE → gNodeB → UPF → Internet (Control: AMF/SMF/UDM)

---

### Comparison Table

| Feature           | 3G (UMTS)                  | 4G (LTE)                    | 5G (NR)                                 |
|-------------------|----------------------------|-----------------------------|-----------------------------------------|
| Architecture      | Circuit + Packet           | All-IP, flat                | Modular, service-based                  |
| Base Station      | Node B + RNC               | eNodeB                      | gNodeB                                  |
| Core Network      | MSC, SGSN, GGSN            | MME, SGW, PGW               | AMF, SMF, UPF, UDM, etc.                |
| Voice             | Circuit-switched           | VoLTE (IP-based)           | VoNR (5G native voice)                  |
| Latency           | Higher                     | Lower                       | Ultra-low                               |
| Network Slicing   | Not supported              | Not supported               | Supported                               |
| IoT Support       | Limited                    | Moderate                    | Extensive                               |

---

## 2. COMPUTER NETWORK EXPLOITATION (CNE)

### IP Address
A unique numerical label assigned to devices on a network (IPv4 or IPv6).

### IPv4 vs IPv6
- **IPv4**: 32-bit (e.g., 192.168.1.1)  
- **IPv6**: 128-bit, larger address space

### Public vs Private IPs
- **Private IPs**: Internal networks  
- **Public IPs**: Internet-facing

### MAC Address
Hardware address for network interfaces.

### Ports
Logical access points for services (e.g., Port 80 = HTTP).

### Common Ports and Protocols
- 20/21 – FTP  
- 22 – SSH  
- 23 – Telnet  
- 25 – SMTP  
- 53 – DNS  
- 80 – HTTP  
- 443 – HTTPS

### Protocols
- **TCP** – Reliable  
- **UDP** – Fast, connectionless  
- **ICMP** – Diagnostics

### OSI Model
1. Physical  
2. Data Link  
3. Network  
4. Transport  
5. Session  
6. Presentation  
7. Application

**Data Flow:** Application → Physical → Network → Application

### Traceroute
Shows packet path using TTL and ICMP.

### Email Header
Shows routing and metadata—used in forensics.

### User-Agent Strings
Indicates device/OS/browser—used in profiling/spoofing.

### NAT
Translates private IPs to public IPs.

### VLAN
Logical segmentation of a switch's network.

---

## 3. CYBER SECURITY

### Malware Triage
- **Static Analysis** – No execution (strings, hashes)  
- **Dynamic Analysis** – Run in sandbox  
- **Signatures** – YARA/SNORT

### Types of Malware
- **Trojan** – Disguised as legit software  
- **Rootkit** – Hides activity  
- **Keylogger** – Captures keystrokes  
- **Botnet** – Zombie network  
- **Backdoor** – Hidden access  
- **Bootkit** – Targets boot process

### Network Attacks
- **Passive** – Wiretapping, sniffing  
- **Active** – DoS, spoofing, MITM  
- **MITM** – Intercepts and alters traffic  
- **MOTS** – MITM with partial control via timing

### Host-Based Attacks
- **Buffer Overflow** – Exceeding memory limits  
- **Format String Attacks** – Malicious input formatting

### Mitigation Techniques
- Patch management  
- Network segmentation  
- EDR  
- Firewalls/IDS  
- MFA and strong passwords

### Threat vs. Vulnerability vs. Risk
- **Threat** – Potential danger  
- **Vulnerability** – Weakness  
- **Risk** – Likelihood of threat exploiting vulnerability

### Intrusion Detection
- Signature-based  
- Anomaly-based  
- Behavioral

### Encryption
- **Symmetric** – One key (AES)  
- **Asymmetric** – Public/private keys (RSA)

### Incident Response Steps
1. Identify  
2. Contain  
3. Eradicate  
4. Recover  
5. Lessons Learned
