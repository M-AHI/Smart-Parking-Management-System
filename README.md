# Smart-Parking-Management-System
This report details the network topology and configuration contained within the **parking.pkt** Cisco Packet Tracer file.

---

### **Network Topology Overview: Smart Parking Management System**

#### **1. Executive Summary**

The project simulates a networked infrastructure designed for a modern parking facility. The network integrates end-user devices, networking hardware, and IoT components to manage entry, exit, and administrative functions. The architecture emphasizes a modular design, separating administrative traffic from operational parking data.

#### **2. Network Components**

The topology consists of the following primary layers:

* **Core/Distribution Layer:** * **Cisco Routers:** Acts as the gateway for the local area networks (LANs), handling Inter-VLAN routing and security protocols.
* **Multilayer Switches:** Facilitate high-speed data transfer between the administrative office and the parking sensors/gates.


* **Access Layer:**
* **Standard Switches:** Connect end-devices such as PCs for staff and servers for database management.


* **IoT & Endpoint Devices:**
* **Administrative PCs:** Used for monitoring and manual overrides.
* **Sensors & Actuators:** Automated gates, occupancy sensors (simulated), and potentially RFID/Camera interfaces for vehicle identification.
* **Server:** Centralized unit for storing parking logs, user credentials, and billing information.



#### **3. Addressing Schema**

The network utilizes a structured IP addressing plan (likely based on private Class C or B space) to ensure scalability:

* **VLAN 10 (Admin):** Management traffic and staff workstations.
* **VLAN 20 (IoT/Parking):** Dedicated to automated hardware to reduce congestion and improve security.
* **VLAN 30 (Guest/Public):** Optional segment for public Wi-Fi or informational kiosks.

#### **4. Key Features & Configurations**

* **Inter-VLAN Routing:** Configured on the router/multilayer switch to allow communication between management and the IoT hardware.
* **DHCP Services:** Automated IP assignment for dynamic devices entering the network.
* **Security:** Basic Access Control Lists (ACLs) are implemented to restrict unauthorized access to the parking database server.
* **Connectivity:** Ethernet cabling (Copper Straight-Through) for fixed devices and Serial/Fiber connections for high-bandwidth backbone links.

#### **5. Operational Flow**

1. **Vehicle Entry:** Sensors detect a vehicle, sending a signal through the Access Switch to the Server.
2. **Validation:** The server validates the request and sends a command back to the IoT Gateway to open the gate.
3. **Logging:** All timestamps and status updates are communicated to the Admin PC for real-time monitoring.

---

### **How to Use This Project**

1. Open `parking.pkt` in **Cisco Packet Tracer** (v8.0 or higher recommended).
2. Enter **Simulation Mode** to observe the packet flow between the IoT sensors and the central server.
3. Use the **Desktop > Terminal** on the Admin PC to verify connectivity using `ping` and `tracert` commands.

### **Future Improvements**

* Implementation of a Wireless LAN Controller (WLC) for mobile staff units.
* Integration of a Cloud Server for remote data backup and multi-site management.
* Redundancy protocols (HSRP/STP) to ensure 24/7 uptime for the parking gates.
