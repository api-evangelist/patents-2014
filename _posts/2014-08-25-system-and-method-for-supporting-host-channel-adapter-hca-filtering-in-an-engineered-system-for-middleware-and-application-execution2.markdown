---

title: System and method for supporting host channel adapter (HCA) filtering in an engineered system for middleware and application execution
abstract: A system and method can provide a data service in a network environment. The network environment can include a node, which supports a data service component that can provide a data service. Additionally, a filter can be provided on a networking device, such as a host channel adaptor (HCA) that is associated with the node. The networking device operates to use the filter to identify one or more packets targeting the data service component without protocol termination. Furthermore, the filter can forward said one or more packets to the data service component.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09559990&OS=09559990&RS=09559990
owner: ORACLE INTERNATIONAL CORPORATION
number: 09559990
owner_city: Redwood Shores
owner_country: US
publication_date: 20140825
---
This application claims priority on U.S. Provisional Patent Application No. 61 870 693 entitled SYSTEM AND METHOD FOR PROVIDING NATIVE DATA SERVICE IN AN ENGINEERED SYSTEM FOR MIDDLEWARE AND APPLICATION EXECUTION filed Aug. 27 2013 which application is herein incorporated by reference.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

This application is related to the following patent application s each of which is hereby incorporated by reference in its entirety 

U.S. patent application titled SYSTEM AND METHOD FOR PROVIDING A DATA SERVICE IN AN ENGINEERED SYSTEM FOR MIDDLEWARE AND APPLICATION EXECUTION application Ser. No. 14 467 859 filed Aug. 25 2014 

U.S. patent application titled SYSTEM AND METHOD FOR CONTROLLING A DATA FLOW IN AN ENGINEERED SYSTEM FOR MIDDLEWARE AND APPLICATION EXECUTION application Ser. No. 14 467 860 filed Aug. 25 2014 and

U.S. patent application titled SYSTEM AND METHOD FOR SUPPORTING DATA SERVICE ADDRESSING IN AN ENGINEERED SYSTEM FOR MIDDLEWARE AND APPLICATION EXECUTION application Ser. No. 14 467 868 filed Aug. 25 2014.

The present invention is generally related to computer systems and is particularly related to an engineered system for middleware and application execution or a middleware machine environment.

The interconnection network plays a beneficial role in the next generation of super computers clusters and data centers. For example the InfiniBand IB technology has seen increased deployment as the foundation for a cloud computing fabric. As larger cloud computing architectures are introduced the performance and administrative bottlenecks associated with the traditional network and storage have become a significant problem.

Described herein are systems and methods that can provide a data service in a network environment such as an engineered system for middleware and application execution or a middleware machine environment. The network environment can include a node which supports a data service component that can provide a data service. Additionally a filter can be provided on a networking device such as a host channel adaptor HCA that is associated with the node. The networking device operates to use the filter to identify one or more packets targeting the data service component without protocol termination. Furthermore the filter can forward said one or more packets to the data service component.

Described herein are systems and methods that can provide one or more data services in an engineered system for middleware and application execution or a middleware machine environment .

In accordance with an embodiment of the invention a data service component such as a data service appliance and or a data service server can provide various types of data services in a network environment e.g. an engineered system for middleware and application execution or a middleware machine environment .

Furthermore a data service component which resides on the node C can provide various data services for the data flow on the IB fabric . For example the data flow between the nodes A and the node B can be a native data flow. This native data flow can access or consume the data services which are provided by the data service component on the intermediate node C . Thus the native data in the IB fabric can be handled without a need to leave the IB fabric .

In accordance with an embodiment of the invention the data service component can provide a software firewall FWL service which can be used for monitoring and inspecting all types of network traffic in the network environment . Additionally the data service component can be used for other purposes such as for performing traffic routing in the network environment.

Furthermore multiple instances of a data service component or multiple data service components can be deployed in the same IB fabric for providing high availability HA and improving performance. As shown in another data service component can reside on the node D on the IB fabric . Both the data service component and the data service component can be simultaneously running on the IB fabric .

In accordance with an embodiment of the invention a data service component can either be dedicated to providing the data service or be configured to share the same physical machine with other application virtual servers. As shown in the node C which hosts the data service component may host an application server . Thus the node C can be used for supporting different application workloads. For example the node C can host virtual machines running these application workloads. On the other hand the node D which hosts the data service component may be dedicated to providing the data services.

Moreover the system can support different topological configurations in the network environment . For example the node C can play the role as both a source node and a destination node in addition to the role as an intermediate node for supporting communication between other nodes. Thus a single node C can support different types of workloads including the source workload the destination workload and the data service appliance workload.

In accordance with an embodiment of the invention the system can deploy a data service component or in a virtual machine VM as a virtual appliance i.e. a data service appliance in a virtualized environment. Alternatively the system can physically deploy a data service appliance or on a node as a data service server in a non virtualized environment.

Furthermore the traffic in the IB fabric can be selectively directed to the data service component or for data processing e.g. based on an evaluation of the resolved address of the target endpoint . For example the data packets can be directed to the node C or the node D using different routing algorithms for a native packet forwarding mechanism. Also the traffic in the IB fabric can be selectively directed to a data service appliance based on the resolution of the VM.

In accordance with an embodiment of the invention a data service server can be provided in an external network e.g. an external Ethernet network . In such a case the data flow may need to leave the IB fabric before being processed by the data service server in the external network and returned to the IB fabric afterwards.

Furthermore the system can use different mechanisms for connecting the data service server in the external network to the IB fabric . As shown in the data service server may be connected to the IB fabric via an Ethernet switch . Alternatively the data service server may be connected to the IB fabric via an Ethernet link to the node B on the IB fabric .

In accordance with an embodiment of the invention the intermediate node can be physically located between two communicating parties or end points e.g. the node A and the node B . Thus the data flow between the node A and the node B may be forced to pass through the data service server on the intermediate node .

Additionally the intermediate node can include another application server . In such a case the system can use reverse filtering rules for determining which data packets in a data flow should be processed by the data service server .

Furthermore multiple software FWL appliances can be deployed in the IB fabric for providing high availability HA and improving performance. For example a FWL can reside on the node C and a FWL can reside on the node D .

As shown in the traffic between the node A and the node B in the IB fabric can be directed to the FWL for inspection without leaving the IB fabric . The FWL can decide whether to forward the data packets which are received from the source node A to the destination node B or drop the data packets.

In accordance with an embodiment of the invention the FWL can monitor and inspect various types of traffic in the IB fabric . For example the IB traffic in the Oracle Exalogic engineered system can include the internet protocol over INFINIBAND IPoIB traffic the Ethernet over INFINIBAND EoIB traffic the private virtual interconnect PVI traffic the sockets direct protocol SDP traffic and the user space remote direct memory access RDMA traffic. Such traffic can be based on various transport protocols such as the unreliable datagram UD transport protocol the reliable connection RC transport protocol the unreliable connection UC transport protocol the reliable datagram RD transport protocol and the raw transport protocol.

In accordance with an embodiment of the invention the data service components such as the firewall FWL appliances can be deployed in pairs for supporting high availability HA and improving performance in the engineered system .

As shown in an application VM which contains an application server can be deployed on the node A and an application VM which contains another application server can be deployed on the node B . Additionally a FWL VM which contains a FWL appliance can be deployed on the node C and a FWL VM which contains another FWL appliance can be deployed on the node D .

Furthermore each of the nodes A D can use one or more host channel adaptors HCAs for connecting to the network. For example the node A uses the HCA A the node B uses the HCA B the node C uses the HCA C and the node D uses the HCA D .

As shown in each of the HCA A D can have two ports e.g. a port and a port . In order to support high availability HA in the network environment the system can connect the different HCA ports for the nodes A D via different switches A B .

In accordance with an embodiment of the invention different HCA ports on the same node can be independently assigned to the different members in each FWL HA pair. For example the subnet administrator SA in an IB subnet can be aware of the HA pairs when assigning the FWL destination local identifiers DLIDs .

As shown in all of the ports on the nodes A D can be connected to the switch A while all of the ports on the nodes A D can be connected to the switch B . Thus when a failure occurs on one of the switches e.g. on the switch A the traffic in the engineered system among the nodes A D can still be transmitted through the switch B and the firewall FWL appliances on node D can be used for inspecting the traffic. Additionally such a scheme can be generalized to the case of multiple HCAs per node without limitation. 

Additionally the system can provide an interface for configuring the SA with different policies . The interface can be a command line interface CLI and or an application programming interface API .

In accordance with an embodiment of the invention the policies can define what traffic should pass through a data service node e.g. a firewall before reaching the destination node and what traffic can be forwarded directly to the destination node. Furthermore the policies can be implemented based on the source and destination global identifiers GIDs . Also the policies can be implemented based on a service ID which provides the application level differentiation. Additionally the policies can be implemented based on IB partitions.

For example a use case may support a policy that requires all communication between a middleware machine and a cluster database machine must go through a firewall node.

Additionally a uses case may support a policy that requires the use of a specific IB partition which is associated with a particular P Key. For example the specific IB partition can be used solely for the firewall controlled communication between all application tier servers and a database. If a path record resolution request is within the context of the specific IB partition the SA can use this policy to indicate that all packets on that path should be routed through the firewall.

Another use case may support a policy for the BoW deployment that involves two independent subnets. The SM may not be able to discover a path between the source and destination in two independent subnets by simply examining the fabric topology. Using the policy the SM can be informed that a path between the source and the destination exists through a particular data service component. Also when the BoW deployment involves multiple IB partitions the P Key for each partition can be specified in the policy.

As shown in the SA can receive a PR request from a requester e.g. a source node . The SA can resolve the destination local address e.g. a destination local identifier DLID according to the policies . Then the SA can send a PR response which includes the resolved destination local address back to the requester. Thus the source node can send a data packet to the destination node based on the resolved DLID.

Alternatively the SA may determine that the source node should direct the data packet to an intermediate node such as a data service node with a data service component e.g. a software firewall before forwarding the data packet to the destination node. The SA can provide the source node with a DLID for the data service node instead of a DLID for the destination node. Additionally the SA can determine which data service node should be used when multiple instances of the data service component exist in the network environment .

The switch can be used to direct the data flow in the network environment . The switch can include a subnet administrator SA which can perform the path record resolution operation based on different rules or policies e.g. rules . The SA which runs in a secure environment on a switch or on a secure node can implement various logics for performing address resolution tasks.

In accordance with an embodiment of the invention based on the SA policies the system can take advantage of the global routing header GRH in the IB packet for establishing communication through different paths that can be either within an IB subnet or among multiple IB subnets. The GRH was originally defined in the IB specification for establishing communication among different IB subnets 

For example the SA can use a field in a path record resolution response e.g. the HopLimit field to indicate to the host software stack that a GRH may be required for establishing communication through a specific path within an IB subnet.

As shown in the node A can host an application VM A that contains an application server. The application VM A can be associated with a global identifier GID A e.g. 0xAAAA and a local port with a local identifier LID A e.g. 0xA . Furthermore the node B can host an application VM B that contains an application server. The application VM B can be associated with a GID B e.g. 0xBBBB and a local port with a LID B e.g. 0xB . Also the node C can host an application VM C that contains an application server. The application VM C can be associated with a GID C e.g. 0xCCCC and a local port with a LID C e.g. 0xC .

Additionally the network environment can include a data service node D which can host a data service VM D . The data service VM can be associated with a GID D e.g. 0xDDDD and a local port with a local identifier D e.g. 0xD . Additionally the data service node D can host one or more application VMs in addition to the data service VM .

As shown in within an IB fabric in the network environment the data flow which includes the transmitted data packets as shown in solid line can be based on the standard LID based forwarding feature as provided by the switch . Additionally the control flow which includes various control information as shown in dashed line can be based on the address resolution feature as provided by the SA .

As shown in the above table the first rule defines that all packets which are originated from the VM with GID 0xAAAA and are targeting the VM with GID 0xBBBB should be transmitted with the DLID 0xD. The second rule defines that all packets which are originated from the VM with GID 0xCCCC and are targeting the VM with GID 0xBBBB should be transmitted with the DLID 0xB. The third rule defines that all packets which are sent from the VM with GID 0xDDDD originated from 0xAAAA and are targeting the VM with GID 0xBBBB should be transmitted with the DLID 0xB.

As shown in the node A can initiate a data flow to the node B by sending a PR request to the SA on the switch . After the subnet administrator receives the PR request from the node A the SA can process the PR request according to the first rule in the above table and send a PR response to the node A . The PR response can indicate that the data packet needs to be directed to the data service node D which has a local port that can be identified using the LID 0xD.

Then the source node A can direct the data flow to the data service node D . After the data service node D has processed the received data flow the data service node D can send a PR request to the SA . The SA can in turn return a PR response that contains the real address of the node B . Thus the data service node D can direct the data flow to the destination node B . Alternatively the data service node D may decide to drop the received packets.

Also as shown in the SA can direct the data flow directly from the node C to the node B bypassing the data service node D . In this example the node C can first send a PR request to the SA . Then the SA can return the real address of the node B in a PR response .

In accordance with an embodiment of the invention the data service node D can use other mechanisms to obtain a mapping of the destination GID to the destination LID without limitation. For example both the data flow and the control flow can be based on the LID forwarding feature or both the data flow and the control flow can be based on the addressing scheme as enforced by the subnet administrator SA .

Furthermore when a VM is the member of multiple IB partitions different forwarding rules can be defined for the different IB partitions e.g. based on the different P Keys . Thus the traffic on some IB partitions can be directly routed to the destination while traffic on other IB partitions may need to be routed to the data service appliance.

The node A which is associated with a host channel adaptor HCA includes an application virtual machine VM that hosts an application server. Furthermore the node B which is associated with a host channel adaptor HCA includes an application VM that hosts another application server.

Additionally the intermediate node which is associated with a host channel adaptor HCA can include a data service VM and an application VM i.e. the data service VM and the application VM shares the same physical machine . The data service VM can host a data service component and the application VM can host an application server.

In order to prevent the direct communication between the node A and the node B the system can configure both the node A and the node B as limited members of a partition in an IB fabric while allowing the intermediate node to be a full member of the partition.

As shown in the data flow from the node A can be initiated by the application VM using the transmitting Tx queue pairs QPs . Furthermore based on a PR response received from the SA the node A can send data packets to the receiving Rx queue pairs QPs on the intermediate node . Thus the data service VM on the intermediate node can receive the data packets from the node A via the Rx QPs .

Then the data service component in the data service VM can process the incoming data flow. For example the data service VM can provide firewall service by examining the incoming data flow and can drop questionable data packets. Additionally the data service VM can provide other data services such as sniffing performance monitoring and load balancing.

After completing the data processing the data service VM can transmit the outgoing data packets from the Tx QPs to the Rx QPs on the node B e.g. based on the standard LID based switching . Thus the application VM can receive the data packets in the data flow.

Furthermore the application VM on the node B can send a return packet back to the application VM on the node A via the intermediate node . As shown in the return data flow can start from the Tx QPs on the node B and ends at the Rx QPs on the node A via the Rx QPs and Tx QPs on the intermediate node . Thus the application VM on node A can receive the return packets from the node B .

Additionally the application VM which is located on the intermediate node can send one or more data packets to other nodes e.g. via the Tx QPs through the data service VM . Also the application VM can receive one or more data packets from other nodes e.g. via the Rx QPs . Furthermore depending on the policy configuration the application VM can send one or more data packets to other nodes and or receive one or more data packets from other nodes directly bypassing the data service .

In accordance with an embodiment of the invention the processing of the data flow at the data service VM on the intermediate node can be transparent to both the source node A and the destination node B i.e. node A may actually think that it transmits data to the node B directly .

Furthermore the data service component e.g. a software firewall in the data service VM can be a distributed virtualized software appliance. Other nodes in the network environment may not be aware of the existence of the intermediate node and the data service appliance in the data service VM .

The IB packet can include the payload and various headers according to the IB protocols. These headers can include a global routing header GRH a local routing header LRH and other headers . Additionally the IB packet can be applied with various cyclic redundancy checks CRCs .

In accordance with an embodiment of the invention the system can take advantage of the destination global identifier DGID in the GRH and the destination local identifier DLID in the LRH for supporting data service addressing in the IB subnet .

For example the system can set the DLID in the IB packet to be the DLID for the intermediate node instead of the DLID for the destination node . Within the IB subnet the IB packet can be routed to the intermediate node based on the DLID as resolved by the SA . Thus the IB packet can be processed using a data service provided on the intermediate node .

Furthermore the system can use the DGID in the GRH to indicate the DLID for the destination node . Thus the data service software in the intermediate node is able to resolve or obtain the real DLID for the destination node based on the DGID information in the GRH .

In accordance with an embodiment of the invention the intermediate node can perform additional packet header and or payload modifications when necessary. For example the fabric level access control can be set up in a way that the source node and the destination node are either limited members of a relevant partition or not members of the same partition. In such a case the intermediate node may need to change the P Key value in the IB packet before forwarding the modified packet to the destination node .

The incoming IB packet may include a global routing header GRH and a local routing header LRH in addition to the other sections . For example the GRH can contain a destination global identifier DGID e.g. 0xBBBB for a destination node and the LRH can contain a destination local identifier DLID e.g. 0xF for the intermediate node .

Furthermore the intermediate node can provide a data service such as a firewall service that can inspect the incoming IB packet . After processing the incoming IB packet using the data service the intermediate node can send an outgoing IB packet to the destination node as indicated in the DGID in the incoming IB packet . Alternatively the intermediate node may decide to drop the packet .

As shown in the outgoing IB packet can include a GRH and a LRH in addition to the other sections . The GRH can contain a DGID for the destination node and the LRH can contain a DLID for the destination node.

In accordance with an embodiment of the invention a path record cache can be used to resolve the real DLID for the destination node which can be used to direct the outgoing IB packet to the destination node within the subnet .

The path record cache can exist on various nodes in the IB subnet and an SA can coordinate the behavior of the path record cache . Thus the SA is capable of returning the data service address on the intermediate node or the destination application address on a destination node for the different requests.

Additionally the path record cache can take advantage of an address mapping table. The following is an exemplary address mapping table.

As shown in the DGID in the GRH can be used by the data service software for resolving the real destination DLID based on the path record cache . For example the incoming packet can include the header information of DGID 0xBBBB and DLID 0xF. Applying the first rule in the above address mapping table the intermediate node can update the outgoing packet to include the header information of DGID 0xBBBB and DLID 0xB. 

Furthermore the intermediate node may need to manipulate a P Key value which is a field of the basic transport header BTH in a received packet since both end nodes may be configured as limited members of a corresponding partition. For example a packet transmitted by a source node may have a limited P Key which is configured as most significant bit MSB clear . The intermediate node may need to modify this limited P Key to a full P Key which is configured as most significant bit MSB set before transmitting the packet to the destination node.

Additionally the intermediate node can provide a mapping for other transport level address information such as the QP numbers the Q Key values etc. For example the intermediate node can use a local QP number for receiving one or more data packets from the sender nodes which can be identified by the source QP number and the source node . Furthermore the intermediate node can modify the received packets to ensure that both the source node and the destination node can identify the transport level address information as defined by a data service on the intermediate node rather than as defined by a remote end node .

Thus the intermediate node can control what transport level resources are exposed between the end nodes. Also the intermediate node can make use of the local QPs that are implemented by the local hardware in order to optimize performance and provide different qualify of service QoS on various data flows between different pairs of end nodes.

For example an IB packet can be forwarded from the source node to the intermediate node . The incoming IB packet can include a global routing header GRH a local routing header LRH and other transport level address information . Additionally the IB packet can be applied with a variant cyclic redundancy check CRC and an invariant cyclic redundancy check CRC .

Furthermore the intermediate node can provide a data service. Then after processing the incoming IB packet using the data service the intermediate node can forward an outgoing IB packet to the destination node . The IB packet can include a global routing header GRH a local routing header LRH and other transport level address information . Additionally the IB packet can be applied with a variant cyclic redundancy check CRC and an invariant cyclic redundancy check CRC .

In accordance with an embodiment of the invention the isolation of the source node and the destination node can be implemented using the partitioning and or other IB fabric level access control technologies.

The intermediate node is able to observe all traffic between the source node and the destination node . The intermediate node can identify all communication management operations such as the management datagrams MADs exchanged between the source node and the destination node . Also the intermediate node can identify various broadcast multicast based address resolution operations such as the address resolution protocol ARP operations.

In accordance with an embodiment of the invention depending on the packet types the intermediate node can process the received IB packet differently based on the observed communication.

For example the outgoing a packet can resemble the incoming IB packet with only LRH modified. In such a case the system may only need to re compute the packet variant CRC . On the other hand the invariant CRC for the outgoing packet can remain the same as the invariant CRC in the incoming IB packet . Thus the invariant CRC which is generated by the original sender e.g. the source node can protect the data packet all the way to the final receiver e.g. the destination node . The intermediate node can ensure the end to end packet integrity in a way that is similar to a switch.

Alternatively the intermediate node may modify other header information such as the transport level address information in the IB packet and may potentially modify the IB packet payload in the IB packet .

For example the intermediate node may need to generate a new invariant CRC when P Key or any other transport header information is modified. In such a case the system can have completely independent packet integrity protection schemes which may no longer provide the end to end protection between the source node and the destination node within the IB subnet .

Also the intermediate node can perform an incremental invariant CRC update to take into account a P Key the value of which is modified directly in the packet or is modified via control interface such as Work Request . Thus the intermediate node can preserve data integrity characteristics of the IB payload and the HCA allows the modification of the IB P Key for supporting isolation between two end points.

In accordance with an embodiment of the invention the system can employ a separate bit error protection scheme for protecting involved buffers and data path in order to minimize the risk of bit errors that may be introduced by the generation of the new invariant CRCs at the intermediate node . Also the system can take advantage of various end to end protocols which are based on additional checksums in order to protect the end to end data integrity.

The data service node can include an application VM which includes an application server and a data service VM which includes a data service component e.g. a data service appliance . Furthermore the data service node can receive a mixed data flow. The mixed data flow traffic may target either the application VM or the data service VM .

As shown in the data service node can be associated with the queue pairs QPs . The application VM can be associated with the queue pairs QPs and the data service VM can be associated with the receiving Rx queue pairs QPs and the transmitting Tx QPs .

In accordance with an embodiment of the invention the data service node can use the HCA for providing filter capabilities. Also the HCA can provide various interfaces for programming the filters.

For example the HCA can use the LID based filtering for supporting the virtual appliance in which case the HCA Ports for the standard protocol termination part can be configured with a standard LID LMC and the HCA ports for the firewall can be assigned with one or more different LIDs. Alternatively the HCA can apply the inverse logic i.e. any incoming IB packet that does not fall under the standard LID range may be directed to the firewall.

As shown in HCA can include a receiving Rx filter which can identify packets targeting the data service appliance without protocol termination. Thus the HCA can separate the data flow traffic targeting the data service component from the data flow traffic targeting the application server .

For example the Rx filter can separate the mixed data flow traffic based on the data service DLID e.g. using DLID based filtering . The Rx filter can be associated with a data service DLID table . The following is an exemplary data service DLID table.

When an incoming packet has a matching DLID e.g. 0xF or 0xFF the Rx filter can direct the packet to the data service component on the data service VM via QPs . The HCA can treat these packets as raw packets and can forward these incoming packets as they have been received i.e. including all IB headers .

On the other hand if an incoming packet does not have a matching DLID i.e. with a DLID other than 0xF and 0xFF the Rx filter can direct the incoming packet to the application server on the application VM which can use an IB protocol engine to handle the IB packet according to the IB protocol.

Alternatively the Rx filter can use the DGID information in the GRH in an incoming packet for determining where to forward the packet. When an incoming packet has a matching DGID the Rx filter can direct the packet to the data service component on the data service VM . If the incoming packet does not have a matching DGID the Rx filter can direct the packet to the application server on the application VM which can use an IB protocol engine to handle the IB packet according to the IB protocol.

Additionally the Rx filter can be based on invert filtering or reverse filtering . For example the invert filtering can be beneficial in the bump on the wire BOW use case i.e. when the data service node separates two communicating nodes .

In such a case the HCA can use its standard port LID configuration to identify the packets that target the application VM . The HCA can process these packets according to the IB standard definition. Furthermore the HCA can treat all other packets as targeting the data service component .

In accordance with an embodiment of the invention the HCA can spread traffic across multiple queue pairs QPs such as Rx QPs to allow for parallel processing e.g. using multiple threads .

For example the HCA can take advantage of a receive side scaling RSS filter which can spread traffic across multiple queue pairs QPs . The data service component can allocate the different threads for processing the packets arriving on the QPs . Additionally said QPs may expose a hardware interface directly to the data service component bypassing an operating system on the node

Furthermore in order to minimize the overhead for data processing the RSS filter can direct the different packets received from the same data flow to a single data service thread. Alternatively the HCA can use other hash based filters or other types of filters for spreading traffic across multiple queue pairs QPs to allow for parallel processing. Additionally the HCA can direct the data flow according to the core affinity and can preserve the ordering of the packets within the data flow.

Then the data service component e.g. a software FWL service can process the incoming data packets such as modifying the IB headers including the DLID information and or inspecting packet headers and or payload for filtering and monitoring purposes.

In accordance with an embodiment of the invention the HCA can support raw mode packet forwarding. On the receiving side the HCA can validate CRCs can forward packets in raw format with all IB headers to multiple application level QPs without IB protocol termination and can use a RSS filter for spreading load to multiple receiving queues RQs . On the transmitting side the packets processed by the data service component can be submitted to the HCA in raw format e.g. via QPs . The HCA can generate CRCs and allows an application to post packets in raw format with all IB headers from multiple application level QPs.

In accordance with an embodiment of the invention the HCA can support a router usage model. If the DGID in the incoming packet matches a DGID for an ingress HCA port then the packet can be processed according to the IB protocol. If the DGID in the incoming packet does not match any DGID for the ingress HCA ports then the packet can be forwarded to one of the designated set of Rx QPs where the packet can be inspected and optionally modified by the software running on the host node before forwarding to a destination node. When the host software determines that data packet should be forwarded the entire packet potentially with modified IB headers can be sent using a send queue. The send queue can support raw packet where the HCA hardware HW can optionally generate a variant cyclic redundancy check CRC and an invariant cyclic redundancy check CRC while sending the packet.

In accordance with an embodiment of the invention the HCA allows no software stack overhead and can deliver packets directly to the processing threads with no need to copy data. Furthermore the HCA may only touch necessary portions of headers. For example the HCA can support header data separation or hits . Additionally the HCA can take advantage of multiple per processing thread dedicated queues for scaling out efficiently with multiple cores.

Additionally the HCA can provide hardware assistance for cyclic redundancy check CRC validation and CRC generation . Also the HCA can perform an incremental invariant CRC update to take into account a P Key the value of which is modified directly in the packet or is modified via control interface such as Work Request . Thus the HCA can preserve data integrity characteristics of the IB payload and the HCA allows the modification of the IB P Key for supporting isolation between two end points.

The data service node can include an application server and a data service component e.g. a data service server . Furthermore the data service node can receive a mixed data flow. The mixed data flow traffic may target either the application server or the data service server .

As shown in the data service node can be associated with the queue pairs QPs . The application server can be associated with the queue pairs QPs and the data service server can be associated with the receiving Rx queue pairs QPs and the transmitting Tx QPs .

In accordance with an embodiment of the invention the data service node can use the HCA for providing filter capabilities in a fashion similar to the virtualized environment as shown in .

As shown in HCA can include a receiving Rx filter which can identify packets targeting the data service server without protocol termination. Thus the HCA can separate the data flow traffic targeting the data service server from the data flow traffic targeting the application server which uses an IB protocol engine to handle the IB packets according to the IB protocol .

In accordance with an embodiment of the invention the HCA can spread traffic across multiple queue pairs QPs such as Rx QPs to allow for parallel processing e.g. using multiple threads . For example the HCA can take advantage of a receive side scaling RSS filter which can spread traffic across multiple queue pairs QPs . The data service server can allocate the different processes for processing the packets arriving on the QPs .

In accordance with an embodiment of the invention the HCA can support raw mode packet forwarding. Additionally the HCA can provide hardware assistance for cyclic redundancy check CRC validation and CRC generation .

On the receiving side the HCA can validate CRCs can forward packets in raw format with all IB headers to multiple application level QPs without IB protocol termination and can use a RSS filter for spreading load to multiple receiving queues RQs . On the transmitting side the packets processed by the data service component can be submitted to the HCA in raw format e.g. via QPs . The HCA can generate CRCs and allows an application to post packets in raw format with all IB headers from multiple application level QPs.

Many features of the present invention can be performed in using or with the assistance of hardware software firmware or combinations thereof. Consequently features of the present invention may be implemented using a processing system e.g. including one or more processors .

Features of the present invention can be implemented in using or with the assistance of a computer program product which is a storage medium media or computer readable medium media having instructions stored thereon in which can be used to program a processing system to perform any of the features presented herein. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

Stored on any one of the machine readable medium media features of the present invention can be incorporated in software and or firmware for controlling the hardware of a processing system and for enabling a processing system to interact with other mechanism utilizing the results of the present invention. Such software or firmware may include but is not limited to application code device drivers operating systems and execution environments containers.

Features of the invention may also be implemented in hardware using for example hardware components such as application specific integrated circuits ASICs . Implementation of the hardware state machine so as to perform the functions described herein will be apparent to persons skilled in the relevant art.

Additionally the present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail can be made therein without departing from the spirit and scope of the invention.

The present invention has been described above with the aid of functional building blocks illustrating the performance of specified functions and relationships thereof. The boundaries of these functional building blocks have often been arbitrarily defined herein for the convenience of the description. Alternate boundaries can be defined so long as the specified functions and relationships thereof are appropriately performed. Any such alternate boundaries are thus within the scope and spirit of the invention.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. The breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments. Many modifications and variations will be apparent to the practitioner skilled in the art. The modifications and variations include any relevant combination of the disclosed features. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

