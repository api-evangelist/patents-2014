---

title: Segment based switching architecture with hybrid control in SDN
abstract: A segment based switching architecture with hybrid control providing flow control in software defined networking (SDN). An SDN controller controls top tier macro-flows and virtual segment backbone connections in a network, and an SDN network edge device controls and manages micro-flows that are attached to the SDN network edge device. The SDN network edge device controls and manages the micro-flows locally without using a southbound API. The SDN network edge device learns flow information such as source information and incoming port information for all unknown micro-flows belonging to defined segments, and builds a virtual segment topology database for each segment. The SDN network edge device employs flow computation algorithms and micro-flow management in a distributed fashion. The virtual segment backbone connections are naturally exposed to the SDN controller through provisioning.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09397952&OS=09397952&RS=09397952
owner: Futurewei Technologies, Inc.
number: 09397952
owner_city: Plano
owner_country: US
publication_date: 20140905
---
The present disclosure relates generally to software defined networking SDN and more particularly to network data flow control in an SDN.

In conventional SDN with OpenFlow as the south bound application programming interface API network devices switch flows and the routes paths of the flows are computed by SDN controllers. This is a data driven flow forwarding paradigm with fully centralized control where the SDN controllers need to know all aspects of all flows. This paradigm implies a scalability issue which if not addressed will limit the applicability of SDN.

In middle to large scale data center networks the typical number of virtual machines VMs running in servers will be in the range of hundreds of thousands to millions. To handle communication among the VMs the controllers need to 

This could mean millions of packets per second for controller CPU to process and tens of millions of flows to compute and manage. This is a big challenge as it is difficult and expensive to build controllers or controller cluster of this scale with today s technology.

The present disclosure provides a hybrid control architecture in SDN with segment based switching. A hybrid control and distributed control of micro flows enables the SDN network scalability to be greatly improved allowing faster flow discovery and flow setup and smooth and quick station mobility.

According to a first example embodiment of the disclosure an SDN controller or a cluster of SDN controllers controls top tier macro flows and virtual segment backbone connections in a network and a plurality of SDN network Edge devices control and manage micro flows that are directed to the SDN network Edge devices. An SDN network Edge device such as an SDN switch controls and manages the micro flows locally without using a southbound API. An SDN network Edge device learns all relevant flow information such as source information and incoming port information for all unknown micro flows in defined network segments and builds a virtual segment topology database for each such segment. The SDN network Edge devices employ flow computation algorithms and micro flow management in a distributed fashion. The virtual segment backbone connections are naturally exposed to the SDN controller through provisioning. The SDN switch is configured to enable and disable segment micro flow distributed control and implement security check policy control topology discovery and building and path computing algorithms for the micro flows.

In another example embodiment of the disclosure an SDN network Edge device is configured to control and manage micro flows for virtual segments in a network that are attached to the SDN network Edge device without using a southbound API coupled to an SDN controller for these micro flows. The SDN network Edge device is configured to learn relevant flow information such as source information and incoming port information for all unknown micro flows in the defined segments and build a virtual segment topology database for each segment. The SDN network Edge device is configured to employ flow computation algorithms and micro flow management in a distributed fashion. The SDN Edge device is configured to control bottom tier micro flows for the virtual segments.

According to the present disclosure the SDN network data flow control is split into two tiers. A top tier consists of macro flows and the control is centralized at the SDN controllers . A bottom tier consists of micro flows and the control for micro flows are distributed and performed at the SDN switches . This is achieved through following steps.

A provision driven virtual segment based networking paradigm achieves natural separation of the two tier control. This paradigm supplements and works with the original data driven paradigm. For client traffic packets with sources and destinations outside the network devices the network applications are grouped and the network communication is separated into virtual segments. In many scenarios the network segmentation is natural and logical e.g. in a cloud network each client can be a separate segment. Note each segment must be easily identified either through the access connections or through packet classification.

The SDN network provides virtual backbone connections or tunnels for each segment. The backbone connections for each segment interconnect all devices that host the stations VMs applications belonging to the segment.

The virtual segment creation resource binding of the segment in the network is on demand. It is provisioning driven and includes service guarantees including quality of service QoS latency lossful or best effort guarantees.

SDN controllers manage the backbone connections for all segments. Upon provisioning requests the SDN controller is responsible to compute paths and resources for backbone connections based on service guarantees and network design and request network devices to program the connections through the southbound APIs. The backbone connections include point to point connections and possibly also include point to multipoint connections for unknown destination or multi destination packets.

Advantageously the SDN Edge network devices not SDN controllers handle flow establishment forwarding and flow aging for micro flows belong to each virtual segment. The SDN controllers do not deal with individual flows inside each segment. i.e. network devices do not send handshaking packets for individual flows to the SDN controllers for packet forwarding or path computation.

The SDN Edge network devices learn station addresses. The SDN Edge network devices form a topology database for each virtual segment implement flow computing algorithms to compute paths for micro flows micro flow forwarding uses the computed paths.

For packets with unknown destination addresses broadcast addresses or multicast addresses belonging to a segment the SDN Edge network devices use the point to multipoint connections to forward them the paths used are also computed from the topology database mentioned above.

Station movement is supported through the dynamic address learning and topology convergence. As this involves only the Edge network devices on the path without involving any SDN controllers station movement is handled in a more responsive and scalable way.

The distributed segment micro flows control allows each network device comprising an SDN Edge switch to make decisions for micro flows with segments.

In segment based switching only Edge switches need to deal with micro flows and non edge switches only see macro flows.

At step an Edge switch receives micro flow frames experiencing table miss in datapath and determines if they belong to any known segment with distributed control. If no they are sent to the SDN controller .

If yes at step the Edge switch performs a security check. If the security check fails a failure report is issued.

If the segment security check passes step the Edge switch checks to see if a segment policy exists. If yes Edge switch takes policy actions.

If no at step the Edge switch performs learning and records relevant flow information such as port flow and source into its database.

At step the Edge switch performs path computing from the segment topology database. If successful the flow is installed and forwarded.

If it fails at step the Edge switch performs segment flow path discovery and the frames of the micro flow are transmitted using discovery path.

A segment topology database is built up at each of Edge switches through learning within each segment and is used for flow path computing. The topology database is configured to record all information related to the segment the source virtual port and source info and all other relevant flow information. The SDN Edge switch employs different path computation algorithms for the micro flows with different level of granularities.

Referring to there is shown a message flow diagram at for the paradigm providing micro flow control at the Edge network devices . The diagram is slightly simplified with the assumption that all normal security checks mentioned in pass and no segment policy is configured hence both steps are ignored in the flow diagram.

At step the segment provisioning begins with orchestrator provisioning the SDN controller using the northbound API.

At step switch A receives the discovery packet and identifies it as a packet belonging to the configured segment assume switch A doesn t yet know how to forward this packet since this segment uses distributed micro flow control this packet is sent to the distributed control module. Switch A then learns VM a and sends the discover packet out to p2mp backbone connection and not to the SDN controller .

At step edge switch D receive the discovery packet learns VM a and sends the discover packet to local ports one of the copy reaches VM d.

At step VM d receives the discovery packet learns VM a and sends a reply packet to VM a through switch D.

At step switch D receives the reply packet learns VM d computes the flow path and sends the reply packet towards a using the computed path which is the segment backbone connection connecting switch D to switch A.

At step switch A receives the data reply packet learns VM d computes the flow path and sends a reply to VM a directly. VM a receives the reply packet and completes the discovery. VM discovery is completed VM a and VM d are learned by each other as well as by the edge switches A and D where the edge switch A and D are in full control while SDN controller is not involved for the micro flows.

At step switch A receives the data request packet switch A doesn t yet know the flow but already has VM d information in its topology database so its control module computes the flow path installs the flow and forwards the packet after due encapsulation using the computed path which is the segment backbone connection connecting switch A to switch D further packets of the same flow will use the same path. The data request packet reaches switch D.

At step switch D receives the data request packet same as switch A switch D control module computes the path install the flow and sends data request packet to VM d using the computed path which is the direct connection to VM d after due decapsulation. Further packets of the same flow will follow the same installed flow path. VM d receives the data request packet.

At step as a response to the data request packet in step 0053 VM d sends a data reply packet back to VM a through switch D.

At step switch D receives the data reply packet switch D doesn t yet know the flow but has VM a information in its topology database its control module installs the flow path and forwards the packet using the computed path which is the segment backbone connection connecting switch D to switch A after due encapsulation.

At step switch A receives the data reply packet switch A doesn t yet know the flow but already has VM a in its topology database so its control module computes the flow path install the flow and forward the packet using the computed path which is the direct connection to VM a after due decapsulation VM a receives the data reply packet. Now the VM al to VM d two way communication micro flow path setup is complete where the edge switch A and D are in full control while SDN controller is not involved for the micro flows.

In summary this disclosure provides separation of the SDN network control into 2 tiers a top tier called macro flow control and a bottom tier called micro flow control.

It allows the SDN controllers to control macro flows the segment backbone connections or macro flows. The SDN controllers are relieved from initial packets processing path computation and flow management for the micro flows for all virtual segments. This allows the SDN controllers to scale to larger networks and make SDN a more acceptable and competitive technology in real network deployment scenarios.

It allows the SDN network edge devices to control micro flows for virtual segments in a distributed fashion. This allows the network to scale to more stations and more segment micro flows as these micro flows are only managed and processed by network edge devices they pass through.

This paradigm allows much faster new micro flow creation as the micro flows are only processed by the SDN network edge devices they pass through.

Since each SDN network edge device learns station addresses for virtual segments the network topology change converges much faster. This also leads to faster station migration convergence.

This paradigm works side by side with the conventional data driven paradigm. i.e. within an SDN network. In a network implementing this hybrid paradigm flows other than segment micro flows will still be controlled by SDN controllers in centralized fashion. Some SDN network devices can employ this paradigm process and manage virtual segment micro flows some other network devices can work in a conventional way delegate micro flow processing to SDN controllers. This is not the most efficient way but it provides a migration choice.

The content aware unit may also comprise a programmable content forwarding plane block and one or more storage blocks that may be coupled to the programmable content forwarding plane block . The programmable content forwarding plane block may be configured to implement content forwarding and processing functions such as at an application layer or L3 where the content may be forwarded based on content name or prefix and possibly other content related information that maps the content to network traffic. Such mapping information may be maintained in one or more content tables e.g. CS PIT and FIB at the content aware unit or the network unit . The programmable content forwarding plane block may interpret user requests for content and accordingly fetch content e.g. based on meta data and or content name prefix from the network or other content routers and may store the content e.g. temporarily in the storage blocks . The programmable content forwarding plane block may then forward the cached content to the user. The programmable content forwarding plane block may be implemented using software hardware or both and may operate above the IP layer or L2.

The storage blocks may comprise a cache for temporarily storing content such as content that is requested by a subscriber. Additionally the storage blocks may comprise a long term storage for storing content relatively longer such as content submitted by a publisher. For instance the cache and the long term storage may include Dynamic random access memories DRAMs solid state drives SSDs hard disks or combinations thereof.

The network components described above may be implemented on any general purpose network component such as a computer or network component with sufficient processing power memory resources and network throughput capability to handle the necessary workload placed upon it. illustrates a typical general purpose network component suitable for implementing one or more embodiments of the components disclosed herein. The network component includes a processor which may be referred to as a central processor unit or CPU that is in communication with memory devices including secondary storage read only memory ROM random access memory RAM input output I O devices and network connectivity devices . The processor may be implemented as one or more CPU chips or may be part of one or more application specific integrated circuits ASICs .

The secondary storage is typically comprised of one or more disk drives or tape drives and is used for non volatile storage of data and as an over flow data storage device if RAM is not large enough to hold all working data. Secondary storage may be used to store programs that are loaded into RAM when such programs are selected for execution. The ROM is used to store instructions and perhaps data that are read during program execution. ROM is a non volatile memory device that typically has a small memory capacity relative to the larger memory capacity of secondary storage . The RAM is used to store volatile data and perhaps to store instructions. Access to both ROM and RAM is typically faster than to secondary storage .

It may be advantageous to set forth definitions of certain words and phrases used throughout this patent document. The terms include and comprise as well as derivatives thereof mean inclusion without limitation. The term or is inclusive meaning and or. The phrases associated with and associated therewith as well as derivatives thereof mean to include be included within interconnect with contain be contained within connect to or with couple to or with be communicable with cooperate with interleave juxtapose be proximate to be bound to or with have have a property of or the like.

While this disclosure has described certain embodiments and generally associated methods alterations and permutations of these embodiments and methods will be apparent to those skilled in the art. Accordingly the above description of example embodiments does not define or constrain this disclosure. Other changes substitutions and alterations are also possible without departing from the spirit and scope of this disclosure as defined by the following claims.

