## Basics of Computer Networking

A computer network is a collection of interconnected devices that share resources and information. These devices can include computers, servers, printers, and other hardware. Networks allow for the efficient exchange of data, enabling various applications such as email, file sharing, and internet browsing.

Basics building blocks of a Computer network are **Nodes** and **Links**.

### Basic Terminologies
- Network: A network is a collection of computers and devices that are connected together to enable communication and data exchange.
- Nodes: Nodes are devices that are connected to a network.
  
          --> computers
          --> Servers
          --> Printers
          --> Routers
          --> Switches
- Protocol: A protocol is a set of rules and standards that govern how data is transmitted over a network.

          --> TCP
          --> IP
          --> HTTP
          --> FTP
          --> SMTP
          --> ARP
          --> RARP
- Topology: Network topology refers to the physical and logical arrangement of nodes on a network. 

          --> bus
          --> star
          --> ring
          --> mesh
          --> tree
- Service Provider Networks: These types of Networks give permission to take Network Capacity and Functionality on lease from the Provider.

          --> Wireless Communications
          --> Data Carriers
- IP Address: An IP address is a unique numerical identifier that is assigned to every device on a network. IP addresses are used to identify devices and enable communication between them.

- DNS: The Domain Name System (DNS) is a protocol that is used to translate human-readable domain names (such as www.google.com) into IP addresses that computers can understand.

- Firewall: A firewall is a security device that is used to monitor and control incoming and outgoing network traffic. Firewalls are used to protect networks from unauthorized access and other security threats.

### Types of Computer Network Architecture

**Client-Server Architecture:** Client-Server Architecture is a type of Computer Network Architecture in which Nodes can be Servers or Clients. Here, the server node can manage the Client Node Behaviour.

**Peer-to-Peer Architecture:** In P2P (Peer-to-Peer) Architecture, there is not any concept of a Central Server. Each device is free for working as either client or server.

### Basic types of computer network

- LAN (Local Area Network)
- MAN (Metropolitan Area Network)
- WAN (Wide Area Network)
- PAN (Personal Area Network)
- VPN (Virtual Private Network)

### unique identifiers

``hostname``  DESKTOP-4M4EJKJ

``ipconfig``

IPv4 Address: 192.168.237.124 - 32 bits

IPv6 Address: 2401:4900:6335:2656:12ce:3cfc:e734:a3a4 -128 bits
           
``netstat -a -port``    16 bits

  TCP    0.0.0.0:49670          DESKTOP-4M4EJKJ:0      LISTENING 
  
  TCP    0.0.0.0:53399          DESKTOP-4M4EJKJ:0      LISTENING
  
  TCP    0.0.0.0:57621          DESKTOP-4M4EJKJ:0      LISTENING
  
  TCP    127.0.0.1:10533        DESKTOP-4M4EJKJ:0      LISTENING
  
  TCP    127.0.0.1:62811        kubernetes:62812       ESTABLISHED
  
  TCP    127.0.0.1:62812        kubernetes:62811       ESTABLISHED
  
  TCP    127.0.0.1:62813        kubernetes:62814       ESTABLISHED
  
  TCP    127.0.0.1:62814        kubernetes:62813       ESTABLISHED
  
  TCP    172.20.192.1:139       DESKTOP-4M4EJKJ:0      LISTENING
  
**Types of ports**

well known ports - 0 to 1023

registered ports - 1024 to 49151

ephemeral ports - 49152 to 65535

**Network criteria**

Transit time is the time for a message to travel from one device to another.

Response time is the elapsed time between an inquiry and a response. 

- performance

          --->The number of users 

          --->Type of transmission medium 

          --->Capability of connected network
  
          --->Efficiency of software
  
          --->Bandwidth
  
          --->Network topology
  
          --->Network protocols
  
          --->Distance
  
          --->Network congestion
  
          --->Network hardware

- Reliability
    
          --->Frequency of failure
    
          --->Recovery from failures
    
          --->Robustness during catastrophe 

          --->Quality of service (QoS)

          --->Reducing single points of failure

          --->Capacity planning

          --->Network architecture

- Security

- Network topology

**Goals of Computer Networks:**

- Resource sharing
- High reliability
- Inter process communication
- Flexible access
- Security
- Performance
- Scalability

**Advantages**

- Resource sharing
- communication and collaboration
- Centralized management
- Scalibility
- Accessibility

**Disadvantages**

- Security vulnerabilities
- Complexity
- Dependance on infrastructure
- Cost
- Performance limitations

**Common Challenges of Computer Network**

          ---> Performance Degradation
          ---> Security Issues 
          ---> Host Identification
          ---> Configuration Conflicts
          ---> Capacity concern
          ---> Slow connectivity
          ---> Monitoring and maintenance





