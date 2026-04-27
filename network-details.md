# Home Network Lab (AiMesh + MoCA Backhaul)

## Overview
This project documents the design, implementation, and optimization of a high-performance home network using Asus ZenWiFi 7 AiMesh with MoCA 2.5 wired backhaul over existing coax infrastructure.

The network spans three floors and is engineered for maximum throughput, low latency, strong security, and seamless wireless performance, while maintaining compatibility with Verizon FiOS TV services.

---

## Objectives
- Eliminate legacy infrastructure bottlenecks
- Maximize throughput and minimize latency across all floors
- Implement seamless whole-home WiFi coverage
- Maintain FiOS TV functionality over coax
- Introduce network segmentation for security and performance
- Utilize intelligent traffic prioritization and optimization

---

## Topology Summary

### Main Entry Point (Middle Floor)
- Verizon FiOS Optical Network Terminal (ONT) provides internet access
- Coax line passes through a **RiteAV MoCA Point of Entry (PoE) filter**
- Signal is distributed via an **Amphenol 2-way MoCA 2.5 splitter**
- One line connects to a **TrendNet MoCA 2.5 adapter**
- Adapter connects via Cat6a Ethernet to:
  - Gigabit switch
  - Asus ZenWiFi 7 AiMesh main router (LAN origin)

---

### Multi-Floor Distribution

Each floor functions as a segmented network extension:

#### Top Floor
- Coax outlet from splitter
- Amphenol 2-way MoCA splitter
- TrendNet MoCA 2.5 adapter
- Gigabit switch
- Asus ZenWiFi 7 AiMesh node
- Supports wired and wireless client devices

#### Basement Floor
- Identical structure to top floor:
  - Coax outlet
  - MoCA splitter
  - MoCA adapter
  - Gigabit switch
  - AiMesh node

---

### Infrastructure Details
- Total of **4 Amphenol MoCA 2.5 splitters**:
  - 1 at network entry
  - 1 per floor segment
- All unused coax ports are terminated with coax caps to:
  - Reduce signal interference
  - Improve network security
- Cabling:
  - **Ethernet:** Cat6a
  - **Coax:** RG6 quad-shielded

---

## Key Challenges

- Legacy coax splitter bottleneck limiting throughput
- MoCA signal inefficiencies across older infrastructure
- Verizon router interfering with DHCP and network routing
- Maintaining FiOS TV service while optimizing network
- Preventing interference from unused coax lines

---

## Solutions Implemented

- Identified and replaced outdated coax splitter causing network bottleneck
- Installed MoCA PoE filter at network entry point
- Deployed MoCA 2.5 adapters for high-speed wired backhaul
- Removed Verizon router from active routing role due to firmware limitations
- Configured AiMesh for seamless roaming and coverage
- Terminated all unused coax lines to reduce noise and interference
- Hardened router security:
  - Disabled WAN access to admin interface
  - Secured ports
  - Reduced exposure to external scans

---

## Network Segmentation

### 1. Primary Network (Main)
- Tri-band WiFi with **Multi-Link Operation (MLO)**
- Upfront wired backhaul for optimal performance
- Adaptive QoS + AI-powered Adaptive QoE
- Prioritized traffic:
  - Work / Learn-from-Home
  - Gaming
  - Streaming
  - General usage

---

### 2. IoT Network (2.4GHz Only)
- Dedicated network for:
  - Smart home devices
  - IoT and legacy hardware
- Uses 2.4GHz band for:
  - Stability
  - Compatibility
- Provides isolation from primary network

---

### 3. Guest Network
- WPA2/WPA3 secured access
- Internet-only connectivity
- Fully isolated from primary and IoT networks
- Enhances overall network security

---

## Key Features

- **MoCA 2.5 Backhaul**  
  High-speed wired backbone over existing coax infrastructure

- **AiMesh Architecture**  
  Seamless roaming and whole-home wireless coverage

- **Multi-Link Operation (MLO)**  
  Simultaneous use of tri-band frequencies for maximum throughput

- **Adaptive QoS + AI QoE**  
  Intelligent traffic prioritization based on real-time usage patterns

- **Secure & Optimized Network Design**  
  Segmentation, device isolation, and hardened router configuration

---

## Equipment Used

- Verizon FiOS Optical Network Terminal (ONT)
- RiteAV MoCA PoE Filter
- Amphenol 2-Way 5-1675 MHz Digital Splitters (MoCA 2.5)
- TrendNet MoCA 2.5 Adapters (2.5GbE capable)
- Asus ZenWiFi 7 BD5 (AiMesh system: main router + nodes)
- Gigabit Ethernet switches
- Cat6a Ethernet cables
- RG6 quad-shielded coax cables
- Coax termination caps

---

## Results

- Achieved near-max symmetrical throughput (download and upload)
- Reduced latency across all floors
- Improved network stability and reliability
- Seamless wireless roaming between nodes
- Fully preserved FiOS TV functionality
- Established future-ready infrastructure for multi-gig upgrade

---

## Skills Demonstrated

- Network design and topology planning
- Troubleshooting and root cause analysis
- MoCA and wired backhaul implementation
- Router configuration and network security
- Performance optimization and validation
- Multi-network segmentation and traffic management

---

## Notes

- Configuration is optimized for a mixed-use environment:
  - Work from home
  - Streaming
  - Gaming
  - General usage
- Results may vary depending on ISP infrastructure and home layout
- Network is designed for scalability and future multi-gig upgrades
