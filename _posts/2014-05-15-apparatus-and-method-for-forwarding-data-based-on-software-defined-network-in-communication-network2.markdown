---

title: Apparatus and method for forwarding data based on software defined network in communication network
abstract: To forward traffic to a base station using Software Defined Network technology, a method for operating a switch includes receiving path information of a packet to be forwarded from a source terminal to a plurality of destination terminals, from a controller, receiving the packet to be forwarded from the source terminal to the destination terminals, from a base station, and transmitting the packet along a path determined by the path information. An apparatus for controlling a switch in a communication network includes a transceiver configured to receive information of a source terminal and a plurality of destination terminals, from a server which controls a service for forwarding traffic from the source terminal to the destination terminals, and a controller configured to determine a packet forward path between the source terminal and the destination terminals, wherein the transceiver transmits the determined path information to at least one switch.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09648541&OS=09648541&RS=09648541
owner: SAMSUNG-ELECTRONICS CO., LTD
number: 09648541
owner_city: Suwon-si, Gyeonggi-Do
owner_country: KR
publication_date: 20140515
---
The present application is related to and claims the benefit under 35 U.S.C. 119 a to a Korean patent application No. 10 2013 0055016 filed in the Korean Intellectual Property Office on May 15 2013 the entire disclosure of which is hereby incorporated by reference.

The present disclosure relates generally to data forwarding in a communication network. More particularly the present disclosure relates to an apparatus and a method for forwarding traffic to a particular base station using Software Defined Network SDN technology.

A Software Defined Network SDN separates a control plane and a data plane and centers the control plane on a single controller so that the data plane manages simple traffic forwarding and the central controller determines where and how the traffic is transmitted to. In particular by means of various Application Program Interfaces APIs provided via a northbound API and programming using them the controller can perform various traffic controls based on network information. An OpenFlow protocol supports the SDN. According to the OpenFlow the forwarding information is forwarded between the controller and a switch and switch status or traffic information is forwarded to the controller.

The OpenFlow protocol for the SDN technology is being standardized and defines only a method for forwarding the traffic. Accordingly it is not clear that the OpenFlow can gain any benefit by itself. Currently the OpenFlow protocol is applied mostly to the switch which interconnects servers in a data center and how to apply the OpenFlow to recent communication networks such as Long Term Evolution LTE network is not fully discussed. Hence a method for properly applying the SDN is required.

To address the above discussed deficiencies it is a primary aspect of the present disclosure to provide an apparatus and a method for efficiently transmitting traffic of a Radio Access Network RAN in a communication network.

Another aspect of the present disclosure is to provide an apparatus and a method for efficiently transmitting traffic and improving service capability by applying service chaining in a communication network.

Yet another aspect of the present disclosure is to provide an apparatus and a method for transmitting traffic by applying a Software Defined Network SDN in a communication network.

Still another aspect of the present disclosure is to provide an apparatus and a method for building a traffic path by applying OpenFlow to a switch which connects base stations to a backhaul in a communication network.

According to one aspect of the present disclosure a method for operating a switch in a communication network includes receiving path information of a packet to be forwarded from a source terminal to a plurality of destination terminals from a controller receiving the packet to be forwarded from the source terminal to the destination terminals from a base station and transmitting the packet along a path determined by the path information.

According to another aspect of the present disclosure a method for operating a controller which controls a switch in a communication network includes receiving information of a source terminal and a plurality of destination terminals from a server which controls a service for forwarding traffic from the source terminal to the destination terminals determining a packet forward path between the source terminal and the destination terminals and transmitting the determined path information to at least one switch.

According to yet another aspect of the present disclosure an apparatus of a switch in a communication network includes a controller for receiving path information of a packet to be forwarded from a source terminal to a plurality of destination terminals from an OpenFlow controller receiving the packet to be forwarded from the source terminal to the destination terminals from a base station and controlling to forward the packet along a path determined by the path information.

According to still another aspect of the present disclosure an apparatus of a controller for controlling a switch in a communication network includes a communication part for receiving information of a source terminal and a plurality of destination terminals from a server which controls a service for forwarding traffic from the source terminal to the destination terminals and a controller for determining a packet forward path between the source terminal and the destination terminals. The communication part transmits the determined path information to at least one switch.

Other aspects advantages and salient features of the disclosure will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses exemplary embodiments of the disclosure.

Before undertaking the DETAILED DESCRIPTION below it may be advantageous to set forth definitions of certain words and phrases used throughout this patent document the terms include and comprise as well as derivatives thereof mean inclusion without limitation the term or is inclusive meaning and or the phrases associated with and associated therewith as well as derivatives thereof may mean to include be included within interconnect with contain be contained within connect to or with couple to or with be communicable with cooperate with interleave juxtapose be proximate to be bound to or with have have a property of or the like and the term controller means any device system or part thereof that controls at least one operation such a device may be implemented in hardware firmware or software or some combination of at least two of the same. It should be noted that the functionality associated with any particular controller may be centralized or distributed whether locally or remotely. Definitions for certain words and phrases are provided throughout this patent document those of ordinary skill in the art should understand that in many if not most instances such definitions apply to prior as well as future uses of such defined words and phrases.

Throughout the drawings like reference numerals will be understood to refer to like parts components and structures.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the disclosure. Accordingly it should be apparent to those skilled in the art that the following description of exemplary embodiments of the present disclosure is provided for illustration purpose only and not for the purpose of limiting the disclosure as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

By the term substantially it is meant that the recited characteristic parameter or value need not be achieved exactly but that deviations or variations including for example tolerances measurement error measurement accuracy limitations and other factors known to those of skill in the art may occur in amounts that do not preclude the effect the characteristic was intended to provide.

Exemplary embodiments of the present disclosure provide a technique for forwarding traffic to a destination in a communication network. To ease the understanding the present disclosure adopts terms and names defined in 3Generation Partnership Project 3GPP Long Term Evolution LTE standard. Yet the present disclosure is not limited such terms and names and is equally applicable to other standard systems.

A communication method according to an exemplary embodiment of the present disclosure includes an OpenFlow switch hereafter referred to as an Access OpenFlow Switch A OFS connected to a base station and an access cache an OpenFlow switch hereafter referred to as a Core OpenFlow Switch C OFS interworking with a core network and a Software Defined Network Controller SDNC for controlling the A OFS and the C OFS. The A OFS and the C OFS operate according to an OpenFlow protocol and accordingly set a path based on the SDNC and the OpenFlow. The SDNC analyzes traffic using Deep Packet Inspection DPI determines a forwarding path per switch and transmits the forwarding path to each switch so that the packet is forwarded to an adequate server.

For efficient traffic transmission in the network the A OFS can serve as a General packet radio service Tunneling Protocol GTP endpoint. That is the A OFS can encapsulate and decapsulate a GTP packet. Hence the A OFS can function similar to a conventional Evolved Packet Core EPC . As a result a Mobility Management Entity MME of a legacy core network interworks with the A OFS. The SDNC which interworks with a video controller obtains information and locations of a transmitting terminal and receiving terminals and then sets up the path of each switch. The overall structure is shown in .

Referring to the communication network includes a base station an MME an A OFS an OFS an SDNC and a video controller .

The base station provides radio access to terminals and supports connection between the terminals and the network. The base station can be referred to as an evolved NodeB eNB .

The MME manages mobility of the terminals. That is the MME tracks and manages cells and location areas of the terminals.

The A OFS which is a switch for connecting base stations sets up the path according to the OpenFlow protocol. More specifically the A OFS sets up a bearer of the terminal allocates resources and processes the flow according to a Policy and Charging Control PCC rule. The A OFS manages a data plane of the EPC and the path setup is controlled according to control information fed from the SDNC . The A OFS executes an OpenFlow agent. Accordingly when an unset flow packet is received the A OFS reports this to the SDNC and sets up the path under control of the SDNC .

The C OFS which is a switch for processing the general OpenFlow protocol obtains the forward path setup information from the SDNC and builds the path based on the obtained information.

The SDNC forwards a forward path setup command to the A OFS and the C OFS based on the OpenFlow protocol in association with the video controller . For doing so the SDNC can interwork with the video controller using a RESTful API.

The video controller provides the SDNC with group member information obtained in initial 1 N video call set. The group member information can be forwarded using the RESTful API.

Referring to for initial access of a first terminal the bearer setup is performed in step . For example the bearer setup can conform to the LTE standard. Since an A OFS serves as the EPC the A OFS performs the bearer setup and obtains and allocates an IP address of the first terminal via an MME .

In step the A OFS forwards bearer allocation information to the SDNC together with the allocated IP address of the first terminal . For example the bearer allocation information can include Tunneling Endpoint IDentifier TEID and International Mobile Subscriber Identity IMSI .

To route the traffic of the first terminal the SDNC sets the path of the OpenFlow switches including the OFS based on the IP address and the bearer allocation information in step . The SDNC provides the set path to the A OFS and the C OFS .

The bearer setup and the IP address allocation can be performed to a second terminal a third terminal and a fourth terminal in the similar manner.

Now the path setup and the traffic forwarding are explained based on a 1 N video call. The 1 N video call is a service for forwarding video traffic transmitted from one source terminal to a plurality of destination terminals. However the present disclosure is not limited to the video call service but is equally applied to any service for forwarding the traffic from one source terminal to the destination terminals. For example the present disclosure can be applied to a Push To Talk PTT service.

When the switch does not conform to the OpenFlow protocol in the 1 N video call setup the source terminal which knows group information of the destination terminals to receive the video traffic transmits a request for transmitting the video traffic to each terminal. Hence the video controller sets the bearer for each destination terminal and provides media relay server information for relaying the video traffic of the source terminal.

According to an exemplary embodiment of the present disclosure the SDNC intervenes in the video call setup. The video call is set up as shown in .

Referring to a first terminal requests the video call setup in step . At this time the video call which is the 1 N video sharing service is destined for a second terminal a third terminal and a fourth terminal .

Hence a video controller sets the path to each terminal based on the group information in step . That is the video controller determines to forward the video traffic transmitted from the first terminal to the second terminal the third terminal and the fourth terminal .

In step the video controller forwards information of the video call terminals to the SDNC . For example the terminal information i.e. the group information can be forwarded via the RESTful API. The video call group information includes source destination IP address information of the first terminal the second terminal the third terminal and the fourth terminal .

To forward the video traffic from the first terminal to the second terminal the third terminal and the fourth terminal the SDNC forwards packet mirroring and forward commands to the A OFSs based on the source and destination node addresses in step . Based on the forwarded information the A OFSs can obtain where to transmit the packet of the corresponding flow.

By contrast when the switch does not conform to the OpenFlow protocol in the 1 N video call the video traffic from the source terminal is forwarded to the media relay server in the core network. Next the media relay server unicasts the video traffic to each destination terminal using the path set by the video controller in the video call setup phase. That is since the redundant video traffic is forwarded to the terminal over the communication network the backhaul is subject to the load and the same traffic is transferred multiple times to thus waste resources.

In this respect the present disclosure provides a method for forwarding the video traffic without using the media relay server. The present video traffic forwarding is explained by referring to .

Referring to a video packet transmitted from the first terminal is forwarded to an A OFS 1 connected to a first base station in step . The video packet is original video traffic.

According to the information received from the SDNC in the video call setup the A OFS 1 knows that the received video packet is to be forwarded to the second terminal and to the A OFS 2 connected to a second base station in order to forward the packet to the third terminal and the fourth terminal . Hence the A OFS 1 copies the packet transmitted from the first terminal and forwards the copied packet to the second terminal and the A OFS 2 connected to a second base station in step . In so doing when the packet is transmitted through the tunneling the A OFS 1 can decapsulate the tunneling packet and encapsulate the copied packet. More specifically the A OFS 1 can decapsulate and extract data identify the destination terminals in the data copy the data and generate the tunneling packet by encapsulating the copied data. For example the tunneling packet can be the GTP packet.

Based on the information received from the SDNC in the video call setup phase the A OFS 2 connected to the second base station knows that the received information is to be forwarded to the third terminal and the fourth terminal . Hence the A OFS 2 connected to the second base station copies and forwards the packet to the third terminal and the fourth terminal in step . At this time when the packet is transmitted through the tunneling the A OFS 2 can decapsulate the tunneling packet and encapsulate the copied packet. For example the tunneling packet can include the GTP packet.

As above the 1 N video traffic can be forwarded using the minimum path and the minimum network resource. Namely the video traffic can be forwarded without the aid of the relay server in the core network.

Referring to the OpenFlow switch includes a plurality of ports through N a storage and a controller .

The ports through N are connection points of lines for the backhaul network. The ports through N each can be connected to one base station.

The storage stores a basic program for the operations of the OpenFlow switch and setup information. In particular the storage stores the path information determined based on information notified from the SDNC. The storage updates data and provides the stored data under control of the controller .

The controller controls the OpenFlow switch operations. Specifically the controller controls an OpenFlow protocol processor for controlling to serve as the OpenFlow protocol agent a bearer setter for setting the bearer of the terminal and a flow processor for processing the flow of the terminals. For the path setup and the traffic forwarding the controller controls the OpenFlow switch to act as the A OFS of and .

The communication part e.g. transceiver provides an interface for transmitting and receiving information to and from other entity over the network. The communication part can be referred to as a network card an Ethernet card an Ethernet adaptor or a Network Interface Card NIC . The communication part transmits and receives signals as stated above. Hence the communication part can be referred to as a transmitter a receiver or a transceiver.

The storage stores a basic program for the operations of the SDNC an application program and data such as setup information. In particular the storage stores a forward table including the path information of the OpenFlow agents. The storage updates the data and provides the stored data under control of the controller .

The controller controls the operations of the network entity. For example the controller transmits and receives signals via the communication part . The controller includes an OpenFlow protocol processor for controlling to serve as the controller according to the OpenFlow protocol a path setter for setting the path of the OpenFlow agents and a northbound API processor for receiving information for the path setup. The controller can obtain the information for the path setup via the northbound API processor by interworking with the video controller.

For the path setup and the traffic forwarding the controller controls the SDNC to serve as the SDNC of .

As set forth above the redundant transmission of the same traffic unicast to each receiving terminal in the conventional 1 N traffic transmission is avoided and User eXperience UX of the receiving terminal is enhanced by transmitting the traffic along the optimal path. In particular since the media relay server essential for the conventional 1 N traffic transmission is not needed any more capital expenditures CAPEX reduce.

Embodiments of the present invention according to the claims and description in the specification can be realized in the form of hardware software or a combination of hardware and software.

Such software may be stored in a computer readable storage medium. The computer readable storage medium stores one or more programs software modules the one or more programs comprising instructions which when executed by one or more processors in an electronic device cause the electronic device to perform methods of the present invention.

Such software may be stored in the form of volatile or non volatile storage such as for example a storage device like a Read Only Memory ROM whether erasable or rewritable or not or in the form of memory such as for example Random Access Memory RAM memory chips device or integrated circuits or on an optically or magnetically readable medium such as for example a Compact Disc CD Digital Video Disc DVD magnetic disk or magnetic tape or the like. It will be appreciated that the storage devices and storage media are embodiments of machine readable storage that are suitable for storing a program or programs comprising instructions that when executed implement embodiments of the present invention. Embodiments provide a program comprising code for implementing apparatus or a method as claimed in any one of the claims of this specification and a machine readable storage storing such a program. Still further such programs may be conveyed electronically via any medium such as a communication signal carried over a wired or wireless connection and embodiments suitably encompass the same.

While the disclosure has been shown and described with reference to certain exemplary embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the disclosure as defined by the appended claims and their equivalents.

