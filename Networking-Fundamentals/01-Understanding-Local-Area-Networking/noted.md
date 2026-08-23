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

39.17
