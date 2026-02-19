# Network-Mapping-Task-2
Author: Nthabiseng Mkhehlani Date: 19 February 2026

---

## Project Statement
This project documents the mapping and connectivity testing of a home network.  
It demonstrates understanding of IP addressing, routing, DNS resolution, and network communication using diagnostic tools.

**Network Topology Diagram**
<img width="427" height="450" alt="image" src="https://github.com/user-attachments/assets/8dd062b5-ec2c-4b7a-9c30-572d37e975f4" />


---

## IP Addressing & Connectivity

| Device  | IP Address   | Connection | VLAN | Ping Test |
|---------|-------------|------------|------|-----------|
| Laptop  | 10.0.0.41   | Ethernet → Switch → Router | 10 (Trusted) |  Ping successful to Phone, 8.8.8.8, DNS resolved |
| Phone   | 10.0.0.36   | Wi-Fi → Router | 20 (Guest/Untrusted) |  Ping successful to Internet |
| Router  | 10.0.0.10   | LAN/WAN Gateway | N/A |  Ping failed from Laptop (accessible via browser) |

**Subnet:** 10.0.0.0/24
**Default Gateway:** 10.0.0.10

---

## Connectivity Testing Procedure

### 1. Local Device Connectyivity
**Test:** Laptop - Phone
**Command:** ping 10.0.0.36
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0a2c09b0-852d-4563-bea7-24c99f663cd7" />

**Results:** Successul replies
**Meaning:** Local network communication is working.

### 2. Router Connectivity
**Test:** Laptop - Router
**Command:** ping 10.0.0.10


**Results:** Request timed out
**Meaning:** Router blocks ICMP requests (common security behavior).

### 3. Internet Connectivity
**Test:** Laptop - Public Internet
**Command:** ping 8.8.8.8
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/30434f1f-11af-4a10-8c64-0eb79710579e" />
**Results:** Successful replies
**Meaning:** WAN routing and ISP connectivity are functioning.

### 4. DNS Resolution Test
**Test:** Domain name resolution
**Command:** ping google.com
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e4c8c323-9e6b-41cd-ac61-d6fa3b883489" />
**Results:** Resolves to IP and replies recieved.
**Meaning:** DNS services are working correctly.

## Router Access Verification
Router accessibility was verified via web browser:
http://10.0.0.10
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c327d28f-8581-4a01-9b1d-b91f1743296c" />
The router login page loaded successfully, confirming:
 * Router is reachable.
 * Default gateway functioning.
 * Network routing operational.
**Warning**: Browser displayed a security warning due to self-signed router certificate (normal for home routers).

---

## OSI Model Layers Used

**Layer 1 — Physical**  
Ethernet cabling connects the laptop to the switch; Wi-Fi connects the phone.

**Layer 2 — Data Link**  
Switch forwards frames based on MAC addresses; wireless communication operates at this layer.

**Layer 3 — Network**  
Router performs IP routing, NAT, VLAN segmentation, and acts as the default gateway.

**Layer 4 — Transport**  
ICMP used for ping tests; TCP/UDP used for internet browsing and communication.

**Layer 7 — Application**  
DNS resolution and web browser access to the router interface.

---

## Troubleshooting & Findings

### Router Ping Failure
The router did not respond to ICMP echo requests but was reachable via browser.

**Cause:**  
The router’s SPI firewall blocks ping requests for security.

**Verification:**  
Router login page accessible through browser.

---

### Successful Local Communication
Laptop successfully communicated with phone, confirming internal LAN connectivity.

---

### Internet & DNS Verification
Successful ping to 8.8.8.8 and google.com confirmed:

- WAN connectivity  
- ISP routing  
- DNS resolution functionality  

---

## Conclusion

This project successfully mapped and tested a home network using real device IP addresses and connectivity diagnostics.

Testing confirmed:

✔ Internal LAN communication is operational  
✔ Router functions correctly as the default gateway  
✔ Internet connectivity through the ISP is active  
✔ DNS resolution is working properly  
✔ Security features such as SPI firewall may block ICMP while allowing normal traffic  

The final network design demonstrates structured topology, VLAN awareness, and practical troubleshooting skills aligned with networking and cybersecurity best practices.
