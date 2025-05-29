# Telecom-Study-Guide

---

## 1. TELECOM 

### Key Identifiers
Mobile network providers rely on the accuracy of device identification to deploy the appropriate services to the correct devices. To effectively provide services to particular subscribers, mobile providers use a variety of unique codes. These codes work as the mobile networking identity. IMEI, IMSI, ICCID, and MSISDN are some of the key codes to identify mobile devices.

- **SIM (Subscriber Identity Module)**  
  A chip inside the mobile device containing the IMSI and cryptographic keys for authentication.

- **IMSI (International Mobile Subscriber Identity)**  
  A unique identifier assigned to each mobile subscriber, stored on the SIM card. Used to authenticate users on cellular networks. The IMSI is constructed by an MCC (Mobile Country Code), an MNC (Mobile Network Code), [(see here for codes)](https://mcc-mnc.com/) and an MSIN (Mobile Subscriber Identity)

<p align="center">
  <img src="https://github.com/user-attachments/assets/cbc158ec-d654-46bb-90f7-ff38f571ed7d" alt="IMSI Numbering Convention" width="300"/>
</p>



- **IMEI (International Mobile Equipment Identity)**  
  A 15-digit number unique to a mobile device, used to identify the hardware (phone) itself. The first eight digits of an IMEI make up the Type Allocation Code (TAC). The TAC indicates the manufacturer and model of the particular device. Look an up and IMEI [here.](https://imeicheck.com/imei-tac-database-info/)

  <p align="center">
    <img src="https://github.com/user-attachments/assets/72c3c057-468e-46dc-8171-d529f9fbb1bb" alt="IMEI Numbering Convention" width="300"/>
</p>


- **MSISDN (Mobile Station International Subscriber Directory Number)**  
  An MSISDN (Mobile Station International Subscriber Directory Number) is the phone number you're familiar with, the number you use to call or text someone. It's essentially your mobile phone number in international format. It's broken down into a Country Code, National Destination Code, and Subscriber Number.

   <p align="center">
    <img src="https://github.com/user-attachments/assets/4a3be307-3e8a-4447-bf31-994018d20b5a" alt="MSISDN Numbering Convention" width="400"/>
</p>


- **UE (User Equipment)**  
  The mobile device (e.g., smartphone, tablet) used by subscribers to access the network.


### Infrastructure
GSM infrastructure comprises the physical and logical elements needed to establish and operate a Global System for Mobile Communications (GSM) network. It's a digital mobile network that uses the principles of frequency-division multiple access (FDMA) and time-division multiple access (TDMA). Key components include the following.

 <p align="center">
    <img src="https://github.com/user-attachments/assets/baafaeca-655c-4acc-bd77-a7fb1cb54ce8" alt="GSM Infrastructure" width="500"/>
</p>

- **BTS (Base Transceiver Station)**  
  Equipment that facilitates wireless communication between user devices and the network. A BTS is identified by a unique number known as the Cell Global Identity (CGI). CGI is made up of four elements:

    - MCC – Mobile Country Code (3 digits)
Identifies the country (e.g., 310 for USA).

    - MNC – Mobile Network Code (2–3 digits)
Identifies the mobile network operator within the country (e.g., 260 for T-Mobile USA).

    - LAC – Location Area Code
Identifies a specific location area within the network (can cover several cell towers).

    - CI – Cell Identity
A unique ID for each individual cell within a location area.

  <p align="center">
    <img src="https://github.com/user-attachments/assets/48e8848d-8f8f-4380-9bac-58753f535b14" alt="CGI Numbering Format" width="300"/>
</p>


- **BSC (Base Station Controller)**  
  Manages multiple BTSs. Handles radio resource management, call setup, and handovers.

- **RNC (Radio Network Controller) [3G Only]**  
  Equivalent to BSC in 3G networks. Manages Node Bs and handles mobility and call control.

- **MSC (Mobile Switching Center)**  
  Routes voice/data calls, SMS, and manages registration and handovers in circuit-switched networks.

  - **AUC (Authentication Center)**  
  Validates SIM card credentials using IMSI and authentication algorithms.

- **HLR (Home Location Register)**  
  Stores permanent subscriber info like account status and service permissions.

- **VLR (Visitor Location Register)**  
  Temporarily stores subscriber info when roaming, pulled from the HLR.

- **EIR (Equipment Identity Register)**  
  Maintains white/black/graylists of device IMEIs.

- **SGSN (Serving GPRS Support Node)**  
  Manages data sessions, tracks user location, performs access control.

- **GGSN (Gateway GPRS Support Node)**  
  Connects mobile networks to external packet-switched networks like the internet.

- **LTE (Long-Term Evolution)**  
  4G broadband standard with high speeds and low latency (OFDMA and all-IP architecture).

- **5G (Fifth Generation Mobile Network)**  
  Ultra-low latency, massive connectivity, network slicing, beamforming, mmWave.

- **Timing Advance**  
  Synchronizes uplink transmission delays from different distances. This means that the TA value changes for each 550-meter change in the range between a mobile and the base station. This limit of 63 × 550 meters is the maximum 35 kilometers that a device can be from a base station and is the upper bound on cell placement distance.
   <p align="center">
    <img src="https://github.com/user-attachments/assets/1fee55b7-a378-490a-93d6-81b487cee051" alt="Timing Advance" width="400"/>
</p>


- **TDMA, CDMA, OFDMA**  
  - **TDMA**: Time slots per user  
  - **CDMA**: Code per user  
  - **OFDMA**: Subcarriers per user (used in LTE/5G)
 
### Difference Between FDMA, TDMA, and CDMA

| Feature                          | **FDMA** (Frequency Division Multiple Access) | **TDMA** (Time Division Multiple Access) | **CDMA** (Code Division Multiple Access) |
|----------------------------------|-----------------------------------------------|------------------------------------------|-------------------------------------------|
| **Resource Sharing**             | Bandwidth is divided among stations           | Time slots are divided among stations    | Both bandwidth and time are shared        |
| **Codeword Requirement**         | Not required                                  | Not required                             | Required                                   |
| **Guard Requirements**           | Guard bands between adjacent channels         | Guard time between time slots            | Both guard bands and guard time needed     |
| **Synchronization**             | Not required                                  | Required                                 | Not required                               |
| **Data Rate**                    | Low                                           | Medium                                   | High                                       |
| **Data Transfer Mode**          | Continuous signal                             | Signal in bursts                         | Digital signal                             |
| **Flexibility**                  | Limited                                       | Moderate                                 | High                                       |


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
