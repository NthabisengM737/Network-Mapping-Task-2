## Project Overview

This project demonstrates the mapping and connectivity testing of a **home network**. The purpose is to showcase knowledge of:

- Network layers (OSI & TCP/IP)  
- IP addressing and subnetting  
- Routing & DNS resolution  
- Network connectivity testing using `ping` commands  

The home network is mapped using **real device IP addresses** and a professional network topology diagram.

---

## IP Addressing & Connectivity

| Device  | IP Address   | Connection | VLAN | Ping Test |
|---------|-------------|------------|------|-----------|
| Laptop  | 10.0.0.41   | Ethernet → Switch → Router | 10 (Trusted) | ✅ Ping successful to Phone, 8.8.8.8, DNS resolved |
| Phone   | 10.0.0.36   | Wi-Fi → Router | 20 (Guest/Untrusted) | ✅ Ping successful to Internet |
| Router  | 10.0.0.10   | LAN/WAN Gateway | N/A | ❌ Ping failed from Laptop (accessible via browser) |

**Notes:**  

- Router is reachable via the browser (`http://10.0.0.10`) but may block ICMP ping requests (common for SPI firewall).  
- Internet connectivity verified via `ping 8.8.8.8` and DNS resolution.  
- Phone connectivity successful over Wi-Fi.  

---

## OSI Model Layers Used

| Layer | Devices / Relevance |
|-------|-------------------|
| **Layer 1 – Physical** | Ethernet cabling (Laptop → Switch), Wi-Fi for Phone |
| **Layer 2 – Data Link** | Switch forwards Ethernet frames, Wi-Fi handles MAC addresses |
| **Layer 3 – Network** | Router handles IP routing, NAT, VLAN segmentation |
| **Layer 4 – Transport** | ICMP (ping), TCP/UDP for browsing |
| **Layer 7 – Application** | DNS resolution, HTTP/HTTPS browsing, router admin access |

---

## Troubleshooting Insights

- **Router Ping Blocked:** Modern home routers may block ICMP while allowing browser access; demonstrates SPI firewall behavior.  
- **Laptop → Phone Connectivity:** Confirms VLAN separation works internally.  
- **DNS & Internet Access:** Confirms WAN connectivity through ISP.  

---

## Professional Notes

- VLANs separate trusted (Laptop) and untrusted (Phone) devices, showing **network security awareness**.  
- Layered hierarchy is clear: **Internet → Router → Switch → Laptop / Wi-Fi Devices**.  
- IPs, subnet, and default gateway are clearly documented.  

---

## Project Submission Checklist

✅ Mapped all devices with correct IPs  
✅ Tested connectivity using `ping` and DNS resolution  
✅ Documented results in a professional README  
✅ Created network topology diagram with Layer 2 switch and VLANs  
✅ Explained router access and ping behavior
