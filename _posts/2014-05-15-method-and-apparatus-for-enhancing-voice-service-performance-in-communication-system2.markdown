---

title: Method and apparatus for enhancing voice service performance in communication system
abstract: A method for operating a switch in a communication network includes receiving path information of a service flow between a first user equipment (UE) and a second UE from a controller, receiving a packet forwarded through the service flow from a base station, and transmitting the packet to a path determined by the path information. An apparatus for a switch in a communication network includes a controller configured to receive path information of a service flow between a first user equipment (UE) and a second UE from a controller, receive a packet forwarded through the flow from an evolved NodeB and forward the packet to a path determined by the path information. Other embodiments are also disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09591550&OS=09591550&RS=09591550
owner: Samsung Electronics Co., Ltd.
number: 09591550
owner_city: Suwon-si
owner_country: KR
publication_date: 20140515
---
The present application is related to and claims priority under 35 U.S.C. 119 to a patent application No. 10 2013 0055163 filed in the Korean Intellectual Property Office on May 15 2013 the contents of which are incorporated herein by reference.

The present disclosure relates to a method and apparatus for enhancing voice service performance in a communication system.

A software defined network SDN refers to a network architecture in which control and data planes are decoupled. The control plane is centralized into a controller and the data plane is responsible for traffic forwarding. In the SDN the centralized controller decides where and how traffic is routing. The control plane performs a function of controlling a network and the data plane performs a function of forwarding data.

The openflow protocol is a protocol that enables SDN technology and its standardization is already in progress. The openflow protocol defines only how to send the traffic and what benefit is obtained by the openflow protocol by itself is not clear. Until now the openflow protocol is mainly applied to switches that connect servers in a data center and how the openflow protocol is applied to a Long Term Evolution LTE network is not yet discussed actively. Of cause how the openflow protocol is applied to Voice over LTE VoLTE is not yet discussed actively.

The VoLTE is a technology of allowing voice calls to be made using packets on an LTE network. The VoLTE sets up a bearer for voice forwarding after attachment of an UE and allows voice packets to be forwarded preferentially by setting the priority of the bearer to a higher value than others.

However the VoLTE is based on a basic LTE architecture. That is voice packets are forwarded to an evolved packet core EPC of a core network and the EPC forwards the voice packets to a target receiver. Therefore there is no efficiency in forwarding of voice packets.

Even when a transmitter and a receiver are served by evolved NodeBs eNBs adjacent to each other the above described process is performed leading to inefficiency in forwarding of voice packets.

To address the above discussed deficiencies it is a primary object to provide a method and apparatus for enhancing voice service performance in a communication system.

Another object of the present disclosure is to provide a method and apparatus for efficiently forwarding a VoLTE packet in a LTE communication system.

Another object of the present disclosure is to provide a method and apparatus for efficiently forwarding a VoLTE packet when a LTE communication system uses the openflow protocol.

Another object of the present disclosure is to provide a method and apparatus for efficiently forwarding a VoLTE packet when the openflow protocol is used in a LTE radio access network RAN area.

Another object of the present disclosure is to provide a method and apparatus for forwarding a VoLTE packet through a shortest path when the openflow protocol is used in a LTE radio access network RAN area.

Another object of the present disclosure is to provide a method and apparatus for efficiently forwarding a VoLTE packet to minimize backhaul traffic when the openflow protocol is used in a LTE radio access network RAN .

According to an aspect of the present disclosure a method for operating a switch in a communication network includes receiving path information of a service flow between a first user equipment UE and a second UE from a controller receiving a packet forwarded through the service flow from a base station and transmitting the packet to a path determined by the path information.

According to another aspect of the present disclosure a method for operating a controller that controls a switch in a communication system includes receiving information about a service flow between a first UE and a second UE from a node that controls the service flow determining a packet forwarding path between the first UE and the second UE and transmitting information about the determined path to at least one switch.

According to another aspect of the present disclosure an apparatus for a switch in a communication network includes a controller configured to receive path information of a service flow between a first UE and a second UE from a controller receive a packet forwarded through the flow from a base station and forward the packet to a path determined by the path information.

According to another aspect of the present disclosure an apparatus for a controller for controlling a switch in a communication network includes a communication unit e.g. transceiver configured to receive information about a service flow between a first UE and a second UE from a node that controls the service flow and a controller configured to determine a packet forwarding path between the first UE and the second UE wherein the communication unit is configure to transmit the information about the determined path to at least one switch.

Before undertaking the DETAILED DESCRIPTION below it may be advantageous to set forth definitions of certain words and phrases used throughout this patent document the terms include and comprise as well as derivatives thereof mean inclusion without limitation the term or is inclusive meaning and or the phrases associated with and associated therewith as well as derivatives thereof may mean to include be included within interconnect with contain be contained within connect to or with couple to or with be communicable with cooperate with interleave juxtapose be proximate to be bound to or with have have a property of or the like and the term controller means any device system or part thereof that controls at least one operation such a device may be implemented in hardware firmware or software or some combination of at least two of the same. It should be noted that the functionality associated with any particular controller may be centralized or distributed whether locally or remotely. Definitions for certain words and phrases are provided throughout this patent document those of ordinary skill in the art should understand that in many if not most instances such definitions apply to prior as well as future uses of such defined words and phrases.

The present disclosure provides a method and apparatus for enhancing voice service performance in a communication system which will be described below.

Referring to the LTE communication system using the openflow protocol includes access openflow switches A OFSs and connected to evolved nodeBs eNBs and the openflow switch OFS connected even to other backhaul and core networks a software defined network controller access SDNC A for controlling the A OFSs and and the OFS a mobility management entity MME a policy and charging rules function PCRF and an IP multimedia subsystem IMS call session control function CSCF .

The eNBs and connect to at least one user equipment UE or in a wireless manner process packet calls and perform a function of transmitting and receiving radio signals a function of modulating and demodulating packet traffic and a function of controlling wireless resources. Herein the eNB and can be referred as a base station.

The MME processes control messages by interworking with the eNBs and using a non access stratum NAS signaling protocol and performs functions such as mobility management Tracking Area TA list management and bearer and session management with respect to the UEs and .

The PCRF can generate policy rules for adaptive application of quality of service QoS and charging rules with respect to service flows or generate rules commonly applicable to a plurality of service flows. When a VoLTE connection of the UE or is established the PCRF forwards information about a flow which is forwarded from the IMS to the SDNC A through a RESTful API. The IMS performs a call processing function with respect to the UEs and .

The SDNC A interworks with the PCRF to acquire information about a VoLTE packet. The SDNC A determines an optimal forwarding path for each of the A OFSs and based on information about a flow between the UEs and and forwards information about the determined optimal forwarding path to the A OFSs and enabling a VoLTE packet of a relevant flow to be forwarded through its shortest distance or shortest path. In this case the shortest path represents a path with a minimum number of Hops. The optimal path is not limited to the path with the minimum number of Hops. The optimal path is an optimal path satisfying a given condition such as a condition that latency is short or a condition that a bandwidth required to transmit voice packets is secured depending on a network situation.

The A OFSs and and the OFS forward the VoLTE packet to a next node according to the optimal path determined by the SDNC A when the openflow protocol is used. In addition the A OFSs and are responsible for bearer setup resources allocation and flow processing according to a PCC rule with respect to the UEs and . The A OFSs and perform the data plane function of an evolved packet core EPC and sets up a path based on control information forwarded from the SDNC A . The openflow agent is performed in the A OFSs and to perform the above described functions. When a packet of a service flow that is not set up is received the A OFSs and report reception of the packet to the SDNC A and receive control information from the SDNC A to set up a paths for relevant UEs.

The OFS is a switch capable of processing a general openflow protocol. The OFS acquires path information for an UE from the SDNC A and performs routing for the UE based on the path information. In other words The OFS sets a path for the UE based on the path information.

In the configuration of the network the A OFS performs a GPRS tunneling protocol GTP terminating function. In order words the A OFS can perform encapsulation and decapsulation on GTP packets. As described above the A OFS performs a function similar to that of an existing EPC. Therefore the MME that exists in an existing core network interworks with the A OFS .

The SDNC A interworks with the PCRF to acquire path information for a flow. The path information can be 5 tuple information and QoS information. The SDNC A calculates a forwarding path of VoLTE packets between relevant UEs based on the path information and forwards the path information to the A OFSs and and the OFS based on the openflow protocol. To this end the SDNC A can use the PCRF and a RESTful API. The 5 tuple information and the QoS information are described in a standard specification. The 5 tuple information can include IP addresses port numbers and protocol information of nodes on a path.

Referring to the UE performs a bearer setup procedure in compliance with the LTE standard when the UE is attached to the eNB step . According to an embodiment of the present disclosure the A OFSs and perform the role of an evolved packet core EPC . Therefore the UE performs the bearer setup procedure with the A OFS and is assigned with an IP address through the MME .

Thereafter the A OFS forwards bearer assignment information Tunnel End Point Identifier TEID International Mobile Subscriber Identity IMSI etc. along with the assigned IP address of the UE to the SDNC A step . The SDNC A sets up access point name APN based default paths of openflow switches including the OFS in order to route VoLTE packets based on the information in step . The UE performs bearer setup and IP address assignment procedures similarly.

Referring to there is illustrated a process of setting up a VoLTE path between the UE and the UE . When it is assumed that the UE is a transmitting terminal and the UE is a receiving terminal the IMS sets up a path based on the IP address of the UE in response to a VoLTE call setup request in step . The IMS forwards 5 tuple information and QoS information which are associated with the path to the PCRF in step . The process of setting up a path in the IMS complies with a standard specification.

The PCRF forwards the 5 tuple information and the QoS information which are transferred from the IMS to the SDNC A using a RESTful API in step . The SDNC A calculates an optimal path with respect to a network architecture identified in advance based on the information and sets up the optimal path for the A OFSs and . The PCRF forwards information about the optimal path to the A OFSs and in step . Upon forwarding of information about the optimal path information indicating updating of a forwarding table which is used in the OFS can be forwarded. The optimal path can be a shortest path or a shortest distance. In this case the shortest path represents a path with a minimum number of Hops. The optimal path is not limited to the minimum number of Hops. The optimal path is an optimal path satisfying a given condition such as a condition that latency is short or a condition that a bandwidth required to transmit voice packets is secured depending on a network situation. Each of the A OFSs and is an A OFS on a path determined such that VoLTE packets are forwarded between the UEs and .

Referring to the UE and the UE are positioned respectively adjacent to the eNB and the eNB . Therefore when a path between the A OFS connected to the eNB and the A OFS connected to the eNB is set up VoLTE packets are exchanged between the UE and the UE through a shortest distance. Therefore latency to be taken to forward the VoLTE packets can be reduced and service quality can be enhanced.

When the packets are transmitted through tunneling the A OFS can decapsulate a tunneling packet and again encapsulate the tunneling packet. Specifically the A OFS can extract data by performing decapsulation identify a target UE from the data and generate a tunneling packet by performing encapsulation on the data. For example the tunneling packet can be a GTP packet.

Referring to when an UE is attached in step the A OFS performs a bearer setup procedure with the UE in step . In step the A OFS assigns an IP address to the UE through a MME.

In step the A OFS receives information about an optimal path for the UE from the SDNC A. The optimal path is a shortest distance or a shortest path. The shortest path can represent a minimum number of Hops. The optimal path is not limited to the path with the minimum number of Hops. The optimal path is an optimal path satisfying a given condition such as a condition that latency is short or a condition that a bandwidth required to transmit voice packets is secured depending on a network situation. The information about the optimal path can be a forwarding table indicating a next A OFS or a next eNB to which the A OFS forwards a VoLTE packet directed to a relevant UE.

In step the A OFS forwards the VoLTE packet to the next node using the information about the optimal path.

Referring to the SDNC A receives bearer assignment information TEID IMSI etc. associated with a source UE or a target UE from an A OFS in step and sets up an APN based default path for the source UE or the target UE in step .

Thereafter the SDNC A receives 5 tuple information and QoS information associated with a relevant flow of the source UE or the target UE from a PCRF in step .

In step the SDNC A calculates an optimal path for the flow using the 5 tuple and QoS information and determines a path for each A OFS.

In step the SDNC A forwards the information about the determined optimal path to the A OFS. The information about the optimal path can be a forwarding table indicating a next A OFS or a next eNB to which the A OFS forwards a VoLTE packet directed to a relevant UE.

Referring to the PCRF receives 5 tuple and QoS information associated with a path of a relevant UE from a IMS in step and forwards the 5 tuple and QoS information to a SDNC A in step .

Referring to the A OFS includes a communication unit e.g. transceiver a storage unit and a control unit . The communication unit provides an interface for transmitting and receiving information to and from another entity through a network. The communication unit can be called a network card . The communication unit can use an Ethernet interface an optical interface or an ATM interface and is not limited to interface types. The communication unit transmits and receives signals as descried above. Therefore the communication unit can be called a transmission unit a reception unit or a transceiver unit.

The storage unit stores default programs setting information and the like which are required for operation of the A OFS. The storage unit stores path information which is information about an optimal path transferred from the SDNC A. The path information can be a forwarding table indicating a next A OFS or a next eNB to which the A OFS forwards a VoLTE packet directed to a relevant UE. The storage unit updates data according to control of the control unit and provides stored data.

The control unit controls overall operation of the A OFS. According to an embodiment of the present disclosure the control unit includes the openflow protocol processing unit for performing control such that the A OFS operates as the openflow protocol agent a bearer setup unit for performing a bearer setup procedure for an UE and a flow processing unit for processing flows of UEs. In order for routing and VoLTE packet forwarding according to an embodiment of the present disclosure the flow processing unit receives information about an optimal path from the SDNC A through the communication unit and forwards the VoLTE packet of a relevant flow to a next node according to the information about an optimal path through the communication unit as illustrated in .

Referring to the SDNC A includes a communication unit a storage unit and a control unit . The communication unit provides an interface for transmitting and receiving information to and from another entity through a network. The communication unit can be called a network card . The communication unit can use an Ethernet interface an optical interface or an ATM interface and is not limited to interface types. The communication unit transmits and receives signals as descried above. Therefore the communication unit can be called a transmission unit a reception unit or a transceiver unit.

The storage unit stores default programs setting information and the like which are required for operation of the SDNC A. The storage unit can store path information reported by the PCRF and a forwarding table indicating an optimal path for a relevant flow. The storage unit updates data according to control of the control unit and provides stored data.

The control unit controls overall operation of the SDNC A. According to an embodiment of the present disclosure the control unit includes the openflow protocol processing unit for performing control such that the SDNC A operates as the openflow protocol controller and a routing unit for setting up an optimal path for a flow. The control unit includes a northbound API processing unit for receiving information required for routing. The control unit interworks with a video controller through the northbound API processing unit to acquire information necessary for routing. In order for routing according to an embodiment of the present disclosure the routing unit receives the path information from the PCRF determines an optimal path and forwards information the optimal path to the A OFS through the communication unit as illustrated in .

In the embodiments of the present disclosure the components included therein are expressed in the singular form or in the plural form depending on the embodiments. The expressions of the singular form or the plural form have been properly selected depending on a situation for convenience of description. The present disclosure is not limited to a singular component or plural components. Any components expressed in the singular form herein are meant to also include the plural form and vice versa.

The embodiments of the present disclosure efficiently forwards VoLTE packets using the openflow protocol in a LTE RAN area minimizing backhaul traffic.

In addition the embodiments of the present disclosure forwards VoLTE packets through a shortest distance or a shortest path using the openflow protocol in the LTE RAN area enhancing voice service performance.

Embodiments of the present invention according to the claims and description in the specification can be realized in the form of hardware software or a combination of hardware and software.

Such software may be stored in a computer readable storage medium. The computer readable storage medium stores one or more programs software modules the one or more programs comprising instructions which when executed by one or more processors in an electronic device cause the electronic device to perform methods of the present invention.

Such software may be stored in the form of volatile or non volatile storage such as for example a storage device like a Read Only Memory ROM whether erasable or rewritable or not or in the form of memory such as for example Random Access Memory RAM memory chips device or integrated circuits or on an optically or magnetically readable medium such as for example a Compact Disc CD Digital Video Disc DVD magnetic disk or magnetic tape or the like. It will be appreciated that the storage devices and storage media are embodiments of machine readable storage that are suitable for storing a program or programs comprising instructions that when executed implement embodiments of the present invention. Embodiments provide a program comprising code for implementing apparatus or a method as claimed in any one of the claims of this specification and a machine readable storage storing such a program. Still further such programs may be conveyed electronically via any medium such as a communication signal carried over a wired or wireless connection and embodiments suitably encompass the same.

While the disclosure has been shown and described with reference to certain preferred embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the disclosure as defined by the appended claims. Therefore the scope of the disclosure is defined not by the detailed description of the disclosure but by the appended claims and all differences within the scope will be construed as being included in the present disclosure.

