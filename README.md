# 🌐 [Project Title -  Enterprise Network Topology & Routing]

## 📖 Overview
This repository contains a comprehensive GNS3 network simulation designed to demonstrate  a multi-site enterprise network with dynamic routing and VLAN segmentation. The project showcases practical skills in network design, device configuration, and end-to-end connectivity troubleshooting.

## 🛠️ Technologies & Protocols Implemented
*   **Routing:** [ OSPF, EIGRP, BGP, Static Routing]


## 📂 Project Structure
*   `[BGP-IBGP-EBGP-RIP].gns3project` - The main GNS3 portable project file containing the topology and device configurations

## 🚀 How to Open and Run
To run this project locally, follow these steps:

1. **Prerequisites:** Ensure you have [GNS3](https://www.gns3.com/) installed and configured with the required device images.
2. **Download:** Download the `.gns3project` file from this repository.
3. **Import into GNS3:** Open GNS3, go to `File` > `Open Project`, and select the downloaded file.
4. **Verify Images:** Ensure the following images are installed in your GNS3 environment:
   *   [e.g., Cisco IOSv 15.7]
   *   [e.g., Cisco IOSvL2 15.2]
   *   [e.g., Alpine Linux / VPCS]

## ✅ Testing and Verification
Once the devices are started (click the green 'Play' button) and fully booted:
1. **Basic Connectivity:** Open the console of **[PC1]** and ping **[PC2]** (`ping [IP address]`).
2. **Routing Verification:** On **[Router R1]**, run `show ip route` to verify that OSPF/EIGRP neighbors are established and routes are populated.
3. **Service Check:** Open a web browser on **[PC1]** and navigate to **[Web Server IP]** to verify HTTP/DNS services.

## 👨‍💻 Author
**[Your Full Name]**
*   **Course:** CCNA ,CCNP
*   **GitHub:** [@talhakhann22231-lang](https://github.com/talhakhann22231-lang)

---
*Disclaimer: This project was created for educational purposes as part of my coursework.*