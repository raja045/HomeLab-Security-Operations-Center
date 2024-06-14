# HomeLab-Security-Operations-Center





## Project Overview

The Homelab Security Operations Center (HSOC) is a comprehensive, virtualized environment designed for learning, testing, and practising cybersecurity operations. This lab integrates various security tools, network components, and operating systems to simulate a real-world security operations center (SOC). It aims to provide hands-on experience in network defense, incident response, and system administration.

## Components

## **1. OPNsense Firewall**
**Purpose**: Acts as the primary firewall and router, managing network traffic and providing security features such as NAT, VPN, and IDS/IPS.

**Configuration**:
- **Network Segmentation**: Creates separate network segments (DMZ, LAN, Management, etc.) to isolate and protect different parts of the lab.
- **Firewall Rules**: Defines rules to control traffic flow between segments and to the internet.
- **Logging**: Configures logging for monitoring and troubleshooting.
- **IDS/IPS (Suricata)**:
  - **Purpose**: Detects and prevents network-based threats.
  - **Configuration**:
    - **Installation**: Enable and configure Suricata in OPNsense.
    - **Rulesets**: Download and configure appropriate IDS/IPS rulesets.
    - **Alerts and Actions**: Set up alerting and automatic actions for detected threats.


## **2. WireGuard VPN**
**Purpose**: Provides secure remote access to the lab environment.

**Configuration**:
- **Server Setup**: Install and configure WireGuard on OPNsense or a dedicated VM.
- **Client Access**: Set up WireGuard clients on remote devices to connect securely to the lab network.


## **3. Virtual Servers**
#### a. Active Directory (AD) Server
**Purpose**: Centralizes user and computer management, providing authentication and authorization services.

**Configuration**:
- **Domain Controller**: Set up a Windows Server as the domain controller.
- **DNS Integration**: Integrate DNS with AD for domain name resolution.
- **Group Policies**: Create and apply group policies for security and management.

#### b. Ubuntu Server
**Purpose**: Serves multiple roles such as web server, database server, or general-purpose Linux server.

**Configuration**:
- **Services**: Install and configure services like Apache/Nginx, MySQL/PostgreSQL, and other applications.
- **Security**: Implement security best practices, including SSH key authentication and firewall rules.

#### c. DNS Server
**Purpose**: Provides domain name resolution for the lab network.

**Configuration**:
- **DNS Zones**: Configure forward and reverse lookup zones.
- **Integration**: Ensure integration with AD and other network services.


## **4. Virtual Clients (Windows 10)**
**Purpose**: Simulate end-user devices for testing policies, user experience, and security measures.

**Configuration**:
- **Domain Join**: Join the clients to the AD domain.
- **Group Policies**: Apply relevant group policies for security and management.
- **User Simulation**: Create user accounts and simulate typical user activities.

## **5. Attacker Machine (Kali Linux)**
**Purpose**: Conduct penetration testing and security assessments on the lab environment.

**Configuration**:
- **Tools**: Use tools like nmap, Metasploit, and Wireshark for various security tests.
- **Isolation**: Ensure the attacker machine is isolated or monitored to prevent unintended damage.

## **6. Blue Team Operations (WAZUH SIEM)**
**Purpose**: Monitor, detect, and respond to security incidents within the lab environment.

**Configuration**:
- **Log Collection**: Integrate WAZUH with AD, OPNsense, and other critical components to collect logs.
- **Alerting**: Set up alerts for suspicious activities, failed logins, and other security events.
- **Dashboards**: Create dashboards for real-time monitoring and analysis.

## Network Diagram


![HomeLabDiagram drawio](https://github.com/raja045/HomeLab-Security-Operations-Center/assets/94227376/3d909220-4176-496c-a95a-1cdc0e404e10)



## Detailed Configuration Steps

### OPNsense Firewall
1. **Installation**: Download and install OPNsense on a dedicated VM.
2. **Network Segmentation**: Create network interfaces and VLANs for different segments.
3. **Firewall Rules**: Define and apply rules to control traffic between segments.
4. **VPN Setup**: Configure WireGuard VPN for secure remote access.
5. **IDS/IPS Configuration**:
    - **Installation**: Enable Suricata IDS/IPS in OPNsense.
    - **Rulesets**: Download and apply appropriate rulesets (e.g., Emerging Threats).
    - **Alerting and Actions**: Configure alerts and automatic actions for detected threats.

### Active Directory
1. **Installation**: Install Windows Server and promote it to a domain controller.
2. **DNS Integration**: Configure DNS zones and integrate with AD.
3. **Group Policies**: Create and apply group policies for security and management.

### Ubuntu Server
1. **Installation**: Install Ubuntu Server on a VM.
2. **Service Configuration**: Set up a web server, database server, or other services.
3. **Security Hardening**: Apply security best practices, including firewall rules and SSH key authentication.

### WAZUH SIEM
1. **Installation**: Install the WAZUH server on a dedicated VM.
2. **Agent Deployment**: Deploy WAZUH agents on all critical components.
3. **Log Integration**: Configure log sources and integrate with WAZUH.
4. **Alerting and Monitoring**: Set up alerts and dashboards for real-time monitoring.



## Conclusion

The Homelab Security Operations Center (HSOC) is a versatile and comprehensive platform for learning, testing, and enhancing cybersecurity skills. By integrating various components and tools, HSOC provides a realistic and effective environment for practising network defence, system administration, and incident response.
