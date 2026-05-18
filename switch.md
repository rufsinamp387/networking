SWITCH

A network switch is an intelligent hardware device that connects multiple devices—such as computers, printers, and servers—within a Local Area Network (LAN). 
It primarily operates at Layer 2 (Data Link Layer) of the OSI model. Unlike basic hubs that blindly broadcast data to every port, a switch inspects incoming data frames and forwards them only to the specific destination device.

How a Network Switch Works

Switches manage network traffic dynamically using a four-step process:

- Learning: When a device sends data, the switch reads its source Media Access Control (MAC) address and maps it to the physical port it is plugged into.

- Table Building: It stores these maps in an internal database called a MAC Address Table.

- Forwarding: When data arrives for a specific destination, the switch looks up the destination MAC address in its table and forwards the frame out of only that exact port.

- Flooding: If the destination MAC address is unknown, the switch broadcasts the data to all ports (except the incoming one) until the target device responds.


Key Types of Network Switches

Unmanaged Switches: Basic plug-and-play devices with zero configuration options, ideal for home networks.

Managed Switches: Advanced devices offering configuration control, traffic monitoring, security rules, and Virtual LAN (VLAN) segmentation.

PoE (Power over Ethernet) Switches: Deliver electrical power and network data simultaneously through standard Ethernet cables to devices like IP cameras.

Layer 3 Switches: High-performance hybrid devices that combine Layer 2 switching with basic Layer 3 (Network Layer) IP routing capabilities.
