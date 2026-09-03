# Microsoft Learn - Networking Fundamentals - 01 - Understanding Local Area Networking

## Terminology
Data = unit of information that's gonna flow across the network

Node = end devices that are on the network

Client = requests services

Server = fulfills services

Peer = can perform both actions, it can be a client or a server; lots of devices act as peers

Network adapter = to gain access to the network/other devices, you need a network adapter of some kind to allow you to access the media
                = also known as a network interface card (NIC), is the hardware device that enables you to send and receive from your computer
                - RJ-45 jack oriented piece of hardware - the most common type of network adapter connection (wired network)
                
Hub = device that multiple devices hook into that basically spreads the data around to the other devices so that everybody has access to it
    = the most basic central connecting device; enables computers on a network to communicate
    = a host sends data to the hub, the hub sends the data to all devices connected to the hub
    = broadcasts the information received to all the devices connected without picking; if any of those devices don't need that information, they just ignore it, they still listen to it, but pay it no attention
    
Switch = similar to a hub, different a bit in its functionality
       = smarter version of a hub, more selective about how it sends information; keeps track of which addresses from which devices are connected to it. When computer A is gonna send some information, it will open it a bit, look at the header at the top of the file, and say, "this is destined to a computer that has this MAC address", so I'm gonna send it to that port

Router = network utilities or network devices used to connect multiple devices together
       = enables computer to communicate to a different network
       
Media = this is what devices talk on (cable, wireless, other different types of media)

Transport Protocol = rules/standards for data transport, using them makes different devices be able to connect together and intercommunicate

Bandwidth = what you can actually use to transfer data across a network, what's available to you

Local Area Network (LAN) = a group of computers confined to a small geographic area, such as a single building; basic building block of what a network is
                         = a group of devices that share a common communication medium, such as cabled or wireless connection (might be having both wireless and cabled and still be called LAN)

Networks = used to exchange data - for sharing information, communicating, organizing data

Network documentation - helps describe, define and explain physical and logical method for connecting devices, it occurs before a network is built, or when changes are made to the network; Microsoft Visio is a tool that can be used to document networks

MAC(Media Access Control) addresses = address assigned to the physical network port on a network card in a computer, on any computer; any computer that has a network card, has an MAC address assigned to it.

For the **hub**, the bandwidth mentioned in the specifications is shared. So that hub can support 100 megabits per second across all of its ports, so if I'm sending a large file to a server or another computer in my house, and someone else decides to send a large file to another computer, my bandwidth gets cut in half. **Switches**, because they have addressable ports and can keep track of where data is supposed to go, that is not the case. So for switches, that traffic is available for every port at any time - all the specified bandwidth/port.

Wireless Access Point (WAP) = basic device for wireless; it's what is used on a network to allow wireless devices to connect to the wired network. Basically, the backbone of any network is wired, but you'll have areas that allow wireless to connect to your wired network

Serial Data Transfer = the transfer of one bit at a time => on the network cable, data travels in a single bit stream

Data Transfer Rate (bits) = defines the maximum bits per second (bps) that can be transmitted over a networks (example: 10 Mbps - with lower case 'b', differentiating this unit from the data stored on a hard drive, noted with MB)

1 byte = 8 bits

Types of transfer = broadcast (example: radio) and unicast (walkie-talkie)

IP Addresses = uniquely identifies your device and the associated network and allows each device to send and receive information
             = how to devices know a specific device that the information is sent to? They use an IP address, which is similar to social security numbers to identify people. 
             = associated by the TCP/IP Protocol associated to the MAC address
             = most devices connected to a network have an IP address 
             - every IP address is broken down in two components: network component and host component, the network ID showing what network the system is on and then the host ID says the specific device

LAN = geographic area that shares the same network ID (for example: IP address - 192.168.1.1, "192.168.1" - network ID, ".1" - host ID - device). Devices are able to communicate using a hub or a switch. To communicate with a device in another network, a router is needed. 

Computers and other devices are connected using copper-based twisted-pair cables or wireless equipment

Firewall - a router with additional functionality; allows you to interconnect two networks but with a large amount, depending on the firewall, of security that typical routers do not have

Virtual LAN - group of hosts with common set of requirements that communicate as if they were connected together in a normal fashion on one switch, regardless of their physical location; allows to group devices known by a switch together; for example, in a company, you can separate departments. A router can also be used to separate those networks, but they are expensive

Network topologies = defines the physical connection of hosts in a computer network
                   = bus - in line (if one goes down, every other following goes down), ring (more of a logical topology than a physical one; physically looks like a star, but logically works like a ring), star (the center is a hub or a switch, or a SOHO router, and each device is directly connected to it through a twisted-pair cable), mesh (everything connected to everything else), tree (not very common)

Star topology - most common topology

Mesh - very expensive

Ring - each computer is connected using a closed loop; used by token ring and fiber distributed data interface (FDDI)

Token Ring - all computers in it are connected to a central connecting device known as a Multistation Access Unit (MAU or MSAU)

Ethernet - Institute of Electrical and Electronics Engineers (IEEE) standard (802.3) that defines how information is sent and received between network adapters, hubs, switches and other devices
         - the most widely installed LAN
         - common: 802.3u or Fast Ethernet (100 Mbps); 802.3ab or Gigabit Ethernet

Information is put on the physical media in frames, that's how computers on Ethernet networks communicate. A frame is a sequence of bits containing a detectable beggining and end of a packet in the stream of bits; a data packet residing on Layer 2 of the OSI model

Centralized computing - done at a central location using terminals that are attached to this main system

Client/Server model - architecture that distributes applications between servers and client computers (Server: provides services such as Windows Server 2008 R2, Client: Device that requests services such as Windows 7)

Example for peer to peer systems: filesharing

Distributed computing - includes both client-server and peer-to-peer networks
                      - every device or workstation has its own processing power

Remote Desktop Services and Remote Sessions 
- centralized computing has made a comeback of sorts. Remote Desktop Services and remote sessions to computers are based off of the centralized computing model
- thin-client computers do not have a hard drive and store operating system in RAM to be loaded every time the device is turned on
- all other applications and data are stored centrally, this system is a blend of centralized and distributive computing

Servers
- more powerful computers that provide centralized cervices: file, print, database, network controller, messaging/email, web

P2P or peer to peer hac recetnly got an additional meaning, which is to refer to file sharing networks. e.g.: Napster, Gnutella, G2. Other services that also take advantage of P2P file sharing: Skype, VoIP, Cloud computing
