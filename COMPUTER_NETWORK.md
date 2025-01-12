# Networking Protocols Overview

This document provides a brief explanation of HTTP, FTP, SMTP, and DHCP, along with their purposes, features, and differences.

---

## 1. HTTP (HyperText Transfer Protocol)
- **Purpose:** Transfers web pages, images, and resources from web servers to browsers.
- **Port:** Typically uses **port 80** (HTTP) and **port 443** (HTTPS for secure connections).
- **Key Features:**
  - Enables browsing websites.
  - Stateless protocol (doesn’t remember previous requests).
  - Follows a client-server architecture.

---

## 2. FTP (File Transfer Protocol)
- **Purpose:** Facilitates file transfers between computers over a network.
- **Port:** Typically uses **port 21** for commands and **port 20** for data.
- **Key Features:**
  - Supports uploading and downloading files.
  - Allows authentication with username/password or anonymous access.
  - Not secure by default but can use FTPS or SFTP for secure transfers.

---

## 3. SMTP (Simple Mail Transfer Protocol)
- **Purpose:** Used to send emails from clients to servers or between mail servers.
- **Port:** Uses **port 25** (default) or **port 587** for secure communication.
- **Key Features:**
  - Handles outgoing email.
  - Works in conjunction with POP3 or IMAP for receiving emails.
  - Supports encryption with STARTTLS or SSL/TLS.

---

## 4. DHCP (Dynamic Host Configuration Protocol)
- **Purpose:** Automatically assigns IP addresses and network configurations to devices in a network.
- **Port:** Uses **port 67** (server) and **port 68** (client).
- **Key Features:**
  - Automates IP address assignment.
  - Prevents conflicts by ensuring unique IP addresses.
  - Configures subnet mask, gateway, and DNS details.

---

## Key Differences

| **Feature**       | **HTTP**                   | **FTP**                    | **SMTP**                   | **DHCP**                     |
|--------------------|----------------------------|----------------------------|----------------------------|------------------------------|
| **Purpose**        | Transfers web content      | File transfers             | Sending emails             | Assigns IP addresses         |
| **Transport Protocol** | TCP                      | TCP                        | TCP                        | UDP                          |
| **Default Port**   | 80 (HTTP) / 443 (HTTPS)   | 21                         | 25 / 587                  | 67 (server) / 68 (client)    |
| **Security**       | Supports HTTPS            | FTPS / SFTP for encryption | STARTTLS or SSL/TLS        | Typically no encryption      |
| **Example Use**    | Browsing websites          | Uploading/downloading files | Sending emails             | Connecting new devices to a network |

---


# Types of Network Topologies  

Network topology refers to the arrangement of nodes (devices) and connections in a network. This document explains the key types of network topologies.  

---

## 1. **Bus Topology**  
- **Description:**  
  All devices are connected to a single central cable (bus).  
- **Advantages:**  
  - Easy to set up and cost-effective for small networks.  
  - Requires less cable than other topologies.  
- **Disadvantages:**  
  - Single point of failure (if the bus fails, the entire network goes down).  
  - Difficult to troubleshoot.  
- **Use Case:**  
  Used in small networks or temporary setups.  

---

## 2. **Star Topology**  
- **Description:**  
  All devices are connected to a central hub or switch.  
- **Advantages:**  
  - Easy to install and manage.  
  - Failure of one node doesn’t affect others.  
- **Disadvantages:**  
  - Central hub failure causes the entire network to fail.  
  - Higher cost due to more cables.  
- **Use Case:**  
  Commonly used in homes and offices.  

---

## 3. **Ring Topology**  
- **Description:**  
  Devices are connected in a circular loop, with each device connected to two others.  
- **Advantages:**  
  - Equal access to resources.  
  - Suitable for handling heavy traffic.  
- **Disadvantages:**  
  - Failure of one device affects the entire network.  
  - Adding or removing devices disrupts the network.  
- **Use Case:**  
  Used in telecommunication networks.  

---

## 4. **Mesh Topology**  
- **Description:**  
  Each device is connected to every other device in the network.  
- **Advantages:**  
  - Highly reliable (multiple paths for data transmission).  
  - Easy to detect faults.  
- **Disadvantages:**  
  - Expensive due to high cabling and hardware requirements.  
  - Complex to manage.  
- **Use Case:**  
  Used in critical networks like military or financial institutions.  

---

## 5. **Tree Topology**  
- **Description:**  
  Combines characteristics of star and bus topologies in a hierarchical structure.  
- **Advantages:**  
  - Scalable for large networks.  
  - Easy to manage and expand.  
- **Disadvantages:**  
  - Central node failure impacts the entire network.  
  - Requires more cable than bus topology.  
- **Use Case:**  
  Used in corporate networks and WANs.  

---

## 6. **Hybrid Topology**  
- **Description:**  
  A combination of two or more different topologies.  
- **Advantages:**  
  - Flexible and scalable.  
  - Can be tailored to specific requirements.  
- **Disadvantages:**  
  - Expensive and complex to design.  
  - Troubleshooting is challenging.  
- **Use Case:**  
  Used in large organizations with diverse requirements.  

---

## Summary Table  

| **Topology**     | **Advantages**                       | **Disadvantages**                   | **Use Cases**                         |  
|-------------------|--------------------------------------|--------------------------------------|---------------------------------------|  
| **Bus**          | Cost-effective, simple setup         | Single point of failure, hard to troubleshoot | Small or temporary networks            |  
| **Star**         | Easy management, fault isolation     | Central hub failure, higher cost    | Homes, offices                        |  
| **Ring**         | Equal resource access, handles traffic | Entire network fails if one device fails | Telecommunication networks            |  
| **Mesh**         | Highly reliable, fault detection     | Expensive, complex to manage        | Military, financial institutions      |  
| **Tree**         | Scalable, easy expansion             | Central node failure impacts network | Corporate networks, WANs              |  
| **Hybrid**       | Flexible, scalable                   | Expensive, complex to troubleshoot  | Large organizations                   |  


# Wireless Networking in Computer Networks  

This document provides an overview of wireless networking, its basic components, types, communication technologies, and applications.  

---

## Definition of Wireless Networking  
**Wireless Networking** refers to the method of connecting devices to communicate and share data without the use of physical cables. It uses radio waves, infrared, or other wireless technologies to establish communication between devices over short or long distances.  

---

## Basic Components of Wireless Networks  
1. **Access Points (APs):**  
   Devices that provide wireless connectivity to devices within a network.  
2. **Wireless Clients:**  
   Devices such as laptops, smartphones, and IoT devices that connect to the network wirelessly.  
3. **Antennas:**  
   Enhance signal transmission and reception for better connectivity.  
4. **Router:**  
   Directs data between the wireless network and external networks like the internet.  
5. **Wireless Network Interface Card (NIC):**  
   Hardware in devices that enables wireless communication.  
6. **Controller:**  
   Manages multiple access points in larger networks.  

---

## Types of Wireless Networks  
1. **Wireless Personal Area Network (WPAN):**  
   - Short-range communication (e.g., Bluetooth, ZigBee).  
   - Used for personal devices like smartphones and wearables.  

2. **Wireless Local Area Network (WLAN):**  
   - Covers a small area such as a home, office, or campus.  
   - Example: Wi-Fi.  

3. **Wireless Metropolitan Area Network (WMAN):**  
   - Covers a city or large area using technologies like WiMAX.  

4. **Wireless Wide Area Network (WWAN):**  
   - Covers large geographical areas, often using cellular networks (e.g., 4G, 5G).  

---

## Wireless Communication Technologies  
1. **Wi-Fi (Wireless Fidelity):**  
   - Common for WLANs in homes and offices.  
   - Operates on 2.4 GHz and 5 GHz frequency bands.  

2. **Bluetooth:**  
   - Used for short-range communication between personal devices.  

3. **Infrared (IR):**  
   - Used in remote controls and specific line-of-sight communication.  

4. **Cellular Networks:**  
   - Includes 3G, 4G, and 5G for long-distance wireless communication.  

5. **ZigBee:**  
   - Low-power technology for IoT devices and smart homes.  

6. **Satellite Communication:**  
   - Provides internet and communication services in remote areas.  

---

## Applications of Wireless Networking  
1. **Home Networking:**  
   - Enables devices like laptops, smartphones, and smart TVs to connect seamlessly.  

2. **Business Environments:**  
   - Facilitates mobility for employees with wireless connectivity in offices.  

3. **Healthcare:**  
   - Used in medical devices, telemedicine, and patient monitoring.  

4. **Education:**  
   - Provides internet access in schools and universities for e-learning.  

5. **Public Services:**  
   - Powers smart cities with IoT devices, public Wi-Fi, and transportation systems.  

6. **Industrial Automation:**  
   - Enables communication between IoT devices in manufacturing and logistics.  

7. **Military and Defense:**  
   - Used for secure and reliable communication in critical missions.  

---

### Summary  
Wireless networking removes the need for physical cables, providing flexibility and scalability for various applications. It plays a crucial role in modern communication, enabling connectivity across personal, organizational, and industrial domains.  

---

