# Chapter 1: Computer Networks and the Internet

## 1.1 A Nuts-and-Bolts Description (Infrastructure based Internet)

- The Internet connects billions of computing devices worldwide, including traditional computers, smartphones, and various nontraditional devices.
- The term "**hosts**" or "**end systems**" refers to all connected devices. Each End systems are interconnected by a network of communication links and packet switches.
- Packet switches, such as routers and link layer switches, forward packets to their destinations.
- The sequence of links and switches a packet traverses is called a **route** or **path** through the network.
- Packet switched networks are compared to transportation networks, with packets analogous to trucks and communication links to highways and roads.
- End systems access the Internet through various types of **Internet Service Providers (ISPs)**, including residential, corporate, university, WiFi, and cellular data ISPs.
- ISPs connect to content providers, and lower tier ISPs are interconnected through national and international upper tier ISPs.
- Internet protocols, such as TCP and IP, govern data transmission within the Internet, collectively known as TCP/IP.
Internet standards, developed by the ```Internet Engineering Task Force (IETF)``` and documented as requests for comments (**RFCs**), ensure interoperability.
- There are nearly 9000 RFCs defining various Internet protocols, and other bodies specify standards for network components, such as the **IEEE** 802 LAN Standards Committee for Ethernet and WiFi.

## 1.2 A Services Description (Service based Internet)

- The Internet can be viewed as an infrastructure that serves applications.
- Internet applications include various services like messaging, mapping, streaming, social media, etc.
- Internet applications are distributed and run on end systems, not within packet switches.
- To create an Internet application, you need to write programs for end systems.
- End systems use a **socket interface** to instruct the Internet to deliver data to other end systems. It has rules that must be followed.

> A socket interface that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system.
    
> A protocol defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

## 1.3 The Network Edge

- End systems, which include computers, smartphones, and other devices.
- End systems are also known as hosts and run application programs.
- Hosts can be divided into clients (e.g., desktops, laptops, smartphones) and servers (more powerful machines).
- Servers store and distribute content, often in large data centers.
- Large companies like Google have multiple data centers worldwide with millions of servers.

## 1.4 Access Networks, Physical Media

> Access Network — the network that physically connects an end system to the first router (also known as the “edge router”) on a path from the end system to any other distant end system.
- How to connect end systems to edge router ?
      - Residential access nets (DSL, cable-based)
      - Institutional access networks (school, company)
      - Mobile access networks (4G, WiFi)

### Enterprise & Home Access: Ethernet, WiFi

- Ethernet is the predominant LAN technology, using twisted pair copper wire with access speeds from 100 Mbps to tens of Gbps.
- Wireless LAN users connect to an access point, which is linked to the enterprise's network (usually via wired Ethernet).
- IEEE 802.11 (WiFi) is widely used for wireless LAN access with shared transmission rates exceeding 100 Mbps.
- Ethernet and WiFi are used not only in enterprise settings but also in home networks.
- Home networks often combine broadband residential access with wireless LAN technologies.

## 1.5 Network core

- Mesh of interconnected routers
- **Packet-switching** : hosts break application-layer messages into packets
    - Forward packets from one router to the next, across links on path from source to destination

### Packet-switching : store-and-forward transmission

- Transmission delay : takes L/R seconds to transmit L-bit packet into link at R bps
- Store-and-forward means entire packet must arrive at router before it can be transmitted on next link

> Because the router employs store and forwarding, at this instant of time, the router cannot transmit the bits it has received; instead it must first buffer (i.e., “store”) the packet’s bits. Only after the router has received all of the packet’s bits can it begin to transmit (i.e., “forward”) the packet onto the outbound link

- General delay formula for N links each of rate R: `d = N * (L/R)`.

### Packet-switching : queueing delay, loss

- **Queuing Delays and Packet Loss:** if arrival rate (in bps) on incoming links exceeds transmission rate (bps) of output link for a period of time :
    - Packet switches have output buffers (output queues).
    - Packets will queue, waiting to be transmitted on output link
    - Packets can be dropped (lost) when memory (buffer) in router fills up due to congestion

> In this example, if, during a short interval of time, the arrival rate of packets to the router (when converted to bits per second) exceeds 15 Mbps

<img src="https://lh3.googleusercontent.com/pw/ADCreHfX55Xjkoab8kOtoXWB6Pz5F-CWrWrw5L4EFCw6OkzWdqMTgG54E0ZuEkveIh6dnKOvYNbfjwErwsKZvKgvWt-PqDh9Baiy-U_naufuJ4_MSsowqxExy_HUJVPfTrVjW2q_9N7vcgW3QgqDMD4RF2zK=w1806-h1130-s-no" width="700" height="400">

### Two key network-core functions

- **Forwarding:** *local* action : move arriving packets from router's input link to appropriate router output link
- **Routing:** *global* action : determine source-destination paths taken by packets (uses routing algorithms
    - IP addresses are used for destination routing.
    - Routers consult forwarding tables based on destination addresses.
    - Internet uses routing protocols to configure forwarding tables automatically.

## 1.6 Networks of Networks

- Hosts connect to Internet via **access ISPs** (residential, enterprise ISPs)
- Access ISPs in turn must be interconnected
    - So that any two hosts can send packets to each other
      
- **Network Structures:** Various network structures are discussed, including global transit ISPs, regional ISPs, and tier 1 ISPs.
- **Peering:** ISPs can peer, enabling direct traffic exchange without payment. Tier 1 ISPs also peer.
- **IXPs:** Internet Exchange Points facilitate ISPs' direct connections, enhancing efficiency.
- **Content Provider Networks:** Large providers like Google, Microsoft create their networks for control and cost reduction.

<img src="https://lh3.googleusercontent.com/pw/ADCreHfe3VrXVOkt6FxFDHy4qRsByO6EugEHMcLkEvVuXtz2Bz3iZW28h32W2rJs7faFriHzgxJIfbOPV2Gd5L1_0e9PqKnc_pCtjmqNN0OxeH15auTYBd17kowR13spgnTFSgBjINghCV3Ew7gDsBC8lIh5=w1920-h926-s-no" width="600" height="300">

## 1.7 Delay, Loss, Throughput

<img src="https://lh3.googleusercontent.com/pw/ADCreHfL-nbDiTeiYVwKehMcZPCWS4vbdLyINcp3vKml8sDHzFSTYe1VwuexfmBm7WMuOcHHtZM3jBvRVSjVQPA5Nf3_UIDoQ0kpJrBEbwNwm-aBnnEFXz7mxgiKweHMy39iecCa53_7H2PxFA-5-pKN45Dq=w1920-h812-s-no" width="700" height="300">

- **Types of Delays:** Several types of delays affect packets during their journey, including nodal processing delay, queuing delay, transmission delay, and propagation delay.
    - **Processing Delay:** Part of the processing delay includes examining the packet's header and checking for bit level errors. High speed routers have processing delays typically in microseconds.
    - **Queuing Delay:** Queuing delay occurs as packets wait in a queue before being transmitted onto the link (depends on congestion level of router).
    - **Transmission Delay:** Time required to push all of a packet's bits into the link, determined by the packet's length and the transmission rate of the link.
    - **Propagation Delay:** Time for a bit to propagate from one router to the next, dependent on the distance between routers and the propagation speed of the link.
      
- **Comparing Transmission and Propagation Delay:** Transmission delay is about pushing out the packet, while propagation delay is about bit propagation. They can be thought of as the time it takes for a caravan of cars to travel between tollbooths on a highway.

- **Traffic Intensity:** The traffic intensity (La/R) plays a vital role in estimating queuing delay. If it exceeds 1, queuing delay can approach infinity. It varies based on the rate of packet arrivals and the transmission rate.

<img src="https://lh3.googleusercontent.com/pw/ADCreHd2b-31EKHc-W0Ah_HtMogmvFSs7LCK5p-2s6gK7o4h2dv7yao9fDUTvge6xrDnoPiVzIlly5XMmSi-l-sLOQST4M6NFGPxk7GSChBXEqVrqqEJD_ZESJ2vL-SSSzsXRw8dMtxXjAUJUIHuei8cA2j7=w1092-h888-s-no" width="600" height="400">

> **Trace Route**: measure end to end delay in a computer network by tracing the route taken by packets and measuring round-trip delays to routers.

> If the source receives fewer than three messages from any given router (due to packet loss in the network), Traceroute places an asterisk just after the router number and reports fewer than three round trip times for that router.

## 1.8 Throughput

> If the file consists of F bits and the transfer takes T seconds for Host B to receive all F bits, then the average throughput of the file transfer is F/T bits/sec.

- **Instantaneous vs. Average Throughput**: It explains the difference between instantaneous throughput (bits/sec at a given moment) and average throughput (bits/sec over the entire transfer).
- **Two Link Network**: In a simple network with two links, the throughput is determined by the slower link, which acts as the **bottleneck**. `min{Rc, Rs}`
- **Multiple Links**: In a network with multiple links between source and destination, the throughput is limited by the slowest link along the path.
- **Access Network**: In today's Internet, the access network is often the bottleneck for throughput due to over provisioned core network links.
- **Intervening Traffic**: Throughput can be affected by other data flows sharing the same link, even if the link has a high transmission rate.
- **General Dependence**: Throughput depends not only on link transmission rates but also on intervening traffic, making it a more complex concept.

## 1.9 Protocol Layers

- **Protocol Layering**: Network protocols are organized into layers, with each layer providing specific services and using services from the layer below. This structure helps in the design and modularity of network protocols.
- **Implementation of Layers**: Protocols can be implemented in software, hardware, or a combination of both. Application and transport layer protocols are typically implemented in software, while physical and data link layers are often implemented in hardware.
- **Advantages of Layering**: Protocol layering offers modularity, making it easier to update components. It provides a structured way to discuss system components.
- **Drawbacks of Layering**: Some argue against layering due to potential duplication of functionality and information dependencies between layers.
- **Protocol Stack**: The protocols of different layers collectively form the protocol stack. The Internet protocol stack consists of five layers: physical, link, network, transport, and application layers.
- **Encapsulation**: Data is encapsulated as it moves down the protocol stack. Each layer adds its header information to the data received from the layer above, creating a packet with header fields and a payload field.

