OSI LAYERS

The OSI model (or Open Systems Interconnection Model) is an essential model used in networking.  This critical model provides a framework dictating how all networked devices will send, receive and interpret data.

One of the main benefits of the OSI model is that devices can have different functions and designs on a network while communicating with other devices. Data sent across a network that follows the uniformity of the OSI model can be understood by other devices.

The OSI model consists of seven layers which are illustrated in the diagram below. Each layer has a different set of responsibilities and is arranged from Layer 7 to Layer 1.

At every individual layer that data travels through, specific processes take place, and pieces of information are added to this data,

1) PHYSICAL LAYER

   This layer is one of the easiest layers to grasp. Put simply, this layer references the physical components of the hardware used in networking and is the lowest layer that you will find.
   Devices use electrical signals to transfer data between each other in a binary numbering system (1's and 0's).

2) DATALINK LAYER
   
   The data link layer focuses on the physical addressing of the transmission.
   It receives a packet from the network layer (including the IP address for the remote computer) and adds in the phycess Control) address of the receiving endpoint.
   Inside every network-enabled computer is a Network Interface Card (NIC) which comes with a unique MAC address to identify it.

   MAC addresses are set by the manufacturer and literally burnt into the card; they can’t be changed – although they can be spoofed. When information is sent across a network,
   it’s actually the physical address that is used to identify where exactly to send the information.
    
   Additionally, it’s also the job of the data link layer to present the data in a format suitable for transmission.
