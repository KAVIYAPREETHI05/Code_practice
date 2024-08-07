Cisco Packet Tracer is a powerful network simulation tool developed by Cisco Systems.

This tool allows users to create complex network topologies, configure devices, and observe how data moves through the network, without the need for physical hardware.

**use case**
- Create Topology:  adds two switches and three PCs to the workspace. Each PC is connected to a switch.
- Configure VLANs: creates two VLANs (VLAN 10 and VLAN 20) on each switch and assigns the PCs to the appropriate VLANs.
- Set Up Inter-VLAN Routing: adds a router to the topology and configures sub-interfaces to route between the VLANs.
- Simulate and Test:  pings between PCs in different VLANs to ensure that inter-VLAN routing is working correctly.
- Analyze Traffic:  uses Packet Tracer's simulation mode to visualize the packet flow and verify that data is routed correctly through the network.

### 1. connect two pc's
step1: Add two PCs (PC0 and PC1).
step2: connect both of them using copper cross-over connection(same type of device)
step3: set ip address for PC0 as 10.10.10.1 and PC1 as 10.10.10.2 defaul subnet as 255.0.0.0
step4: check for ip address in command prompt using command ``ipconfig``
step5: ping test to verify that devices within the same network segment can communicate with each other.``ping 10.10.10.2``

### 2.
Step 1: Open Cisco Packet Tracer
Launch Cisco Packet Tracer on your computer.
Step 2: Add Network Devices
Add a Router:

Click on the "Network Devices" category in the device panel.
Select "Routers" and choose a suitable router (e.g., 2911).
Place the router on the workspace.
Add a Switch:

Click on the "Network Devices" category in the device panel.
Select "Switches" and choose a suitable switch (e.g., 2960).
Place the switch on the workspace.
Add PCs:

Click on the "End Devices" category in the device panel.
Select "PC" and place five PCs on the workspace, representing different departments (Textiles, Electronics, Civil, Agriculture, and CSE).
Step 3: Connect Devices
Connect the PCs to the Switch:

Click on the "Connections" category in the device panel.
Select the "Copper Straight-Through" cable.
Connect each PC to the switch:
PC0 (Textiles) to Switch.
PC1 (Electronics) to Switch.
PC2 (Civil) to Switch.
PC3 (Agriculture) to Switch.
PC4 (CSE) to Switch.
Connect the Switch to the Router:

Use the "Copper Straight-Through" cable.
Connect the switch to the router:
Switch's GigabitEthernet0/1 port to Router's GigabitEthernet0/0 port.
Step 4: Configure IP Addresses
Assign IP Addresses to PCs:

Click on each PC, go to the "Desktop" tab, and click on "IP Configuration".
Assign IP addresses and subnet masks as follows:
PC0 (Textiles): IP 192.168.1.1, Subnet Mask 255.255.255.0, Default Gateway 192.168.1.254
PC1 (Electronics): IP 192.168.1.2, Subnet Mask 255.255.255.0, Default Gateway 192.168.1.254
PC2 (Civil): IP 192.168.1.3, Subnet Mask 255.255.255.0, Default Gateway 192.168.1.254
PC3 (Agriculture): IP 192.168.1.4, Subnet Mask 255.255.255.0, Default Gateway 192.168.1.254
PC4 (CSE): IP 192.168.1.5, Subnet Mask 255.255.255.0, Default Gateway 192.168.1.254
Configure the Router:

Click on the router, go to the CLI tab, and enter the following commands to configure the router interface connected to the switch:
```
enable
configure terminal
interface gigabitEthernet 0/0
ip address 192.168.1.254 255.255.255.0
no shutdown
exit
exit
```
Step 5: Verify Configuration
Check Interface Status:
Enter the show ip interface brief command on the router to ensure the interface is up and running.
``Router# show ip interface brief``


