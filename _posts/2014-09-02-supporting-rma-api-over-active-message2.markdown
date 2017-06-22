---

title: Supporting RMA API over active message
abstract: Methods, apparatus, and software for implementing RMA application programming interfaces (APIs) over Active Message (AM). AM write and AM read requests are sent from a local node to a remote node to write data to or read data from memory on the remote node using Remote Memory Access (RMA) techniques. The AM requests are handled by corresponding AM handlers, which automatically perform operations associated with the requests. For example, for AM write requests an AM write request handler may write data contained in an AM write request to a remote address space in memory on the remote node, or generate a corresponding RMA write request that is enqueued into an RMA queue used in accordance with a tagged message scheme. Similar operations are performed by AM read requests handlers. RMA reads and writes using AM are further facilitated through use of associated read, write, and RMA progress modules.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09632973&OS=09632973&RS=09632973
owner: Intel Corporation
number: 09632973
owner_city: Santa Clara
owner_country: US
publication_date: 20140902
---
In a computer system with a distributed memory configuration for example a cluster each computing node has direct access to its own attached local memory. The memory attached to other nodes is called remote memory. Usually remote memory is not directly accessible and message passing mechanisms are used to communicate between the nodes.

Remote Memory Access RMA refers to a software interface that gives the impression that the remote memory can be directly accessed. There are many forms of RMA operations but ultimately they can be summarized as two read and write. The read operation copies data from a remote memory address range into a local buffer. The write operation copies data from a local buffer into a remote memory address range.

Existing Remote Memory Access RMA implementations generally fall into two categories. The implementations corresponding to the first category make use of the Remote Direct Memory Access RDMA capability of the underlying interconnection fabrics between computer nodes InfiniBand IB Host Controller Adaptors HCAs such as those from Mellanox support RDMA functions in hardware. The capability is exposed to applications via a software interface called IB Verbs. With IB verbs in order to perform an RMA operation the user creates a work request and posts it to a work queue. The HCA then processes the queue and performs RDMA in hardware. The approach used by the second category is to emulate RMA functions over a regular message passing interface MPI . An example is the implementation of one sided operations in MPICH MPICH2 High Performance MPI . This is often done in a request reply fashion. Due to the asynchronous nature of the RMA operations a separate thread is usually needed to ensure the requests get processed.

The existing RMA implementations have numerous drawbacks. Under RDMA based implementations specialized hardware is required. Under message passing based implementations additional traffic pertaining to associated messages must be transferred over the interconnect fabric thus reducing the effective bandwidth of the fabric.

Embodiments of methods apparatus and software for implementing an RMA application programming interfaces APIs over Active Message AM are described herein. In the following description numerous specific details are set forth to provide a thorough understanding of embodiments disclosed and illustrated herein. One skilled in the relevant art will recognize however that the invention can be practiced without one or more of the specific details or with other methods components materials etc. In other instances well known structures materials or operations are not shown or described in detail to avoid obscuring aspects of the invention.

For clarity individual components in the Figures herein may also be referred to by their labels in the Figures rather than by a particular reference number. Additionally reference numbers referring to a particular type of component as opposed to a particular component may be shown with a reference number followed by typ meaning typical. It will be understood that the configuration of these components will be typical of similar components that may exist but are not shown in the drawing Figures for simplicity and clarity or otherwise similar components that are not labeled with separate reference numbers. Conversely typ is not to be construed as meaning the component element etc. is typically used for its disclosed function implement purpose etc.

Under aspects of the embodiments disclosed herein Active Message techniques are implemented to facilitate RMA write and read operations under which data is written to or read from memory in a remote node using RMA. The basic idea of AM is to allow a piece of code to be executed automatically at the target side when a message arrives. This piece of code is called an AM handler. Multiple AM handlers can be pre registered with the AM mechanism and an AM message can refer to any of them by specifying a corresponding identifier for the AM handler. An AM message can be either a request or a reply both of which can carry data plus some extra control information and can cause the execution of the specified handler. An AM request can be issued anywhere except inside an AM handler 

while an AM reply can only be issued inside an AM handler and at most one reply can be issued for each AM request.

Under aspects of the embodiments disclosed herein Active Message handlers are executed automatically when a corresponding AM request or reply arrives at its target. This provides the necessary asynchronous processing mechanism needed for RMA operations. Basically an RMA write operation can be implemented as an AM request that carries the data from the source buffer and an AM handler that copies the data to the target address. An RMA read operation can be implemented as an AM request that carries the target address information an AM handler that sends the data back via an AM reply and another AM handler that copies the data to the destination buffer.

An RMA write of a block of source data from source buffer to RMA address space proceeds as follows. Source data is read from source buffer via RMA write module which generates an AM write request that is sent over interconnect to AM handler . AM write request includes source data as well as information about the remote memory range to which source data is to be written. This includes the starting address rma addr in RMA address space at which the start of data is to be written and may optionally include the size length an access key and or a message tag. The AM write request handler at the target side AM write request handler then copies source data into RMA address space starting with address rma addr via a DMA or memory copy operation . In one embodiment when AM write request handler has completed copying source data to RMA address space an optional AM write reply may be sent back to the initiator local node if a completion event is desired. As illustrated AM write reply is directed to AM write reply handler which is configured to handle the completion event.

The operation of an RMA read operation proceeds as follows. RMA read API sends an AM read request to AM read request handler identifying a remote address range beginning with rma addr at which the data to be read e.g. remote data is stored. In one embodiment AM read request includes the starting address rma addr length and may include an access key and or message tag. In response to receiving AM read request AM read request handler sends a copy of remote data from remote node to local node via an AM read reply that is directed to AM read reply handler . Upon receipt of AM read reply AM read reply handler extracts the copy of remote data and performs a DMA or memory copy to write the copy of remote data to destination buffer completing the RMA read operation.

Generally AM mechanisms may have limitations on the amount of data that can be transferred via a single AM message. To overcome such limitations an amount of data greater than the limit for a single AM message may be divided into smaller data units e.g. packets and transferred in a pipelined fashion. Examples of RMA read and RMA write operations resulting in transfer of data between a local node and remote node over an interconnect using this technique are illustrated in and

As shown in local node includes a source buffer having multiple slots an RMA write module and an AM write reply handler . Remote node includes an AM write request handler and an RMA memory space partitioned into multiple slots .

The pipelined RMA write proceeds as follows. Data stored in respective slots in source buffer is accessed via RMA write module and is transferred as a plurality of packets via respective AM write requests . Similar to above in one embodiment each AM write request includes the starting address rma addr and optional length access key and or message tag. Upon receipt by AM handler each AM request is processed resulting in generation of respective memory copies that write data into corresponding address ranges beginning at rma addr in RMA address space . In embodiments employing completion events one or more AM write replies are returned to AM handler . For example an AM write reply might be returned for each completed packet write or an AM write reply may confirm completion of multiple packet writes such as providing a single AM write reply for a given source data transfer regardless of the number of packets sent.

For illustrative purposes the portion of source data for each packet is depicted as being stored in a respective slot in source buffer and written to a respective slot in RMA address space however it will be recognized that source buffer and or RMA address space do not need to be partitioned into multiple slots but may generally be configured as one or more address spaces in which data may be stored. In addition the size of each packet may be the same or different sizes may be used. For example in one embodiment packets employ a maximum transfer unit MTU applicable to the underlying transport protocol used by interconnect is used noting the last packet may have a size less than the MTU . At the same time the data contained in the packets should be written to RMA address space in a manner that replicates the block of source data that is to be transferred via multiple packets. In one embodiment the packet data is written in order while in other embodiments out of order writes are permitted so long upon completion the written data block comprises a replication of the source data block.

As shown in local node further includes a destination buffer having multiple slots an RMA read module and an AM read reply handler . Remote node further includes an AM read request handler . As with the multi packet RMA write data is transferred via RMA read module using multiple packets. Each packet transfer is similar to the data block transfer for the RMA read of and proceeds as follows. RMA read module sends an AM read request targeted to be handled by AM read request handler . Each AM read request identifies a remote address range beginning with rma addr at which the remote data to be read is stored. Similar to above in one embodiment AM read request includes the starting address rma addr length and an optional access key and or message tag.

In response to receiving each AM read request AM read request handler sends a copy of a portion of remote data comprising a packet from remote node to local node via an AM read reply that is directed to AM read reply handler . Upon receipt of each AM read reply AM read reply handler extracts the copy of remote data in packet and performs a DMA or memory copy to write the copy of remote data transferred via packet to a corresponding slot in destination buffer completing the RMA read operation for the packet. As with the multi packet read operation depicted in and discussed above the use of slots for destination buffer and RMA address space are for illustrative purposes as the size of packets may vary in some embodiments.

The packet size can be a limiting factor of the maximum bandwidth achievable via a pipelined implementation. However additional performance enhancement for large data transfers can be achieved by utilizing a tagged message passing mechanism if such a mechanism is available. Tagged message passing is similar to regular message passing in the respect that they both are performed as sending at one side and receiving at the other side. Tagged message passing however also attaches a tag to each message so that the receiver can choose which message to receive. This effectively turns a single communication channel into multiple channels. In one embodiment the tag is used to identify different RMA operations in order to ensure the one to one matching between the paired send and receive operations.

Examples of read and write operations using tagged messages are illustrated in . As shown in the tagged message write operation of a block of source data is transferred from a local node to a remote node via an interconnect . In further detail local node includes a source buffer in which the source data is stored and an RMA write module while remote node includes an AM write request handler an RMA progress module and an RMA address space .

The tagged message write operation proceeds as follows. The RMA write comprises an AM write request followed by a send operation . AM write request carries only the information about the remote address range without any data payload rather the send data is transferred via the subsequent send operation . Upon receipt of AM write request AM handler generates a corresponding RMA write request and places the RMA write request via an enqueue operation into an RMA queue . When the enqueued RMA write request is subsequently processed by RMA progress module following a dequeue operation a receive operation is issued with the remote address range provided by AM write request as the receive buffer in RMA address space . This receive operation should match with send posted at the initiator side i.e. local node and get the source data into the intended remote address range in RMA address space . Generally sending AM write requests and sends of corresponding data may be asynchronous although preferably the AM write request should precede its associated data send. In one embodiment receive operation may temporarily buffer blocks of send data prior to being written to RMA address space .

As shown in local node further includes a destination buffer and an RMA read module which are configured to facilitate a tagged message read operation as follows. As with the tagged message write operation an RMA read consists of a receive operation followed by an AM read request and the AM read request handler will cause a send operation being issued at the target side. The RMA queue at the target side is needed because usually message passing operations cannot be issued inside an AM handler.

As illustrated in RMA read module issues an AM read request that is directed to and received by an AM read request handler on remote node . AM read requests handler generates a corresponding RMA read request and enqueues the read request in an RMA read request queue while a send block in RMA progress module dequeues read requests from RMA read request queue retrieves corresponding data from RMA address space and sends the data via a send operation to a receive operation in RMA read module . Receive operation then writes the data into destination buffer completing the remote read operation.

Depending on the particular approach used memory address space s to be used for RMA write and read operations in accordance with the foregoing embodiments may or may not require registration in advance. For example some embodiments employ PSM Performance Scaled Messaging which doesn t need memory registration. PSM defines an API designed specifically for HPC. It defines a tagged messaging API that handles high level capabilities and can efficiently support the implementation of the Message Passing Interface MPI standard. In the meantime the PSM s internal implementation can focus on interconnect specific details relating to data movement strategies and tuning and advanced feature such as QoS Quality of Service dispersive routine resiliency etc. Active Message is also provided as an experimental feature.

PSM is designed to be implemented as a user space library. Details for performing RMA data transfers using PSM are provided in versions of the PSM Programmer s Manual published by QLogic the developer of PSM or in various PSM related documents published by the OpenFabrics Alliance. PSM is included in OFED OpenFabrics Enterprise Distribution as of version 1.5.2 and is a peer to IB Verbs. Although targeted for use in InfiniBand under embodiments employing PSM herein PSM like functionality may be implemented for non InfiniBand hardware such as Ethernet Network adaptors.

As mentioned above PSM doesn t need memory registration. Optionally a lightweight memory registration mechanism may be implemented to provide access validation. The implementation considerations may include the memory region control structure to be accessed such as a contiguous address space or a sorted disjoint list of address ranges. In one embodiment the control structure address may be used as the access key.

Subsequently access key is used for the validation of RMA write and RMA read requests issued by remote node to access memory within the address range s space s registered by local node . As depicted in the lower portion of a message corresponding to an AM write request or AM read request is sent from remote node to local node . Message includes access key . Upon receipt the AM write or AM read is validated by local node using access key . This validation operation may also validate the address range specified by the starting address and the explicit or detected size of the request to verify it is when the registered address range s space s . If validation is successful access to the registered memory is permitted otherwise it is not. In one embodiment an access error message is returned to remote node if its AM write or AM read request fails validation.

Processor includes a CPU including one or more cores. The CPU and or cores are coupled to an interconnect which is illustrative of one or more interconnects implemented in the processor and for simplicity is shown as a single interconnect . Interconnect is also coupled to a memory interface I F and a PCIe Peripheral Component Interconnect Express interface . Memory interface is coupled to memory while PCIe interface provides an interface for coupling processor to various Input Output I O devices including storage and network interface . Generally storage is illustrative of one or more non volatile storage devices such as but not limited to a magnetic or optical disk drive a solid state drive SSD a flash memory chip or module etc.

Network interface is illustrative of various types of network interfaces that might be implemented in a server node such as an Ethernet network adaptor or NIC. Network interface includes a PCIe interface a Direct Memory Access DMA engine a transmit buffer a receive buffer a MAC module and a packet processing engine or NPU Network Processor Unit . Network interface further includes PHY circuitry comprising circuitry and logic for implementing an Ethernet physical layer. Also depicted is an optional reconciliation layer .

PHY circuitry includes a set of PHY sublayers a serializer deserializer SERDES a transmit port including a transmit buffer and one or more transmitters and a receive port including a receive buffer and one or more receivers . Node is further illustrated as being linked in communication with a remote node including a receive port and a transmit port via a wired or optical link . Depending on the particular Ethernet PHY that is implemented different combinations of PHY sublayers may employed as well as different transmitter and receiver configurations. For example a 10GE PHY will employ different PHY circuitry that a 40GE or a 100GE PHY.

Various software components are executed on one or more cores of CPU to implement software based aspects of the embodiments such as described above with reference to . Exemplary software components depicted in include a host operating system applications and software instructions for implementing various AM handlers and RMA modules . All or a portion of the software components generally will be stored on board the node as depicted by storage . In addition under some embodiments one or more of the components may be downloaded over a network and loaded into memory and or storage .

During operation of node portions of host operating system will be loaded in memory along with one or applications that are executed in OS user space. AM handlers and RMA modules generally may be implemented using an OS driver or the like or may be implemented as a software component executed in OS user space. In some embodiments all or a portion of AM handlers and or RMA modules may be implemented as embedded software that is executed on one or more processing elements implemented in network interface such as packet processing engine NPU . As another option all or a portion of AM handler operations and or RMA module operations may be implemented via one or more virtual machines hosted on node not shown .

In the embodiment illustrated in MAC module is depicted as part of network interface which comprises a hardware component. Logic for implementing various operations supported by network interface may be implemented via embedded logic and or embedded software running on packet processing engine NPU or one or more other processor elements. As an example embedded logic may be employed for preparing upper layer packets for transfer outbound from transmit port . This includes encapsulation of upper layer packets e.g. TCP IP UDP other protocols etc. in Ethernet packets and then framing of the Ethernet packets wherein Ethernet packets are used to generate a stream of Ethernet frames.

Generally packet processing operations performed by packet processing engine NPU may be implemented via embedded logic and or embedded software. Packet processing is implemented to manage forwarding of data within network interface and also between network interface and memory . This includes use of DMA engine which is configured to forward data from receive buffer to memory using DMA writes resulting in data being forwarded via PCIe interfaces and to memory in a manner that doesn t involve CPU . In some embodiments transmit buffer and receive buffer comprises Memory Mapped IO MMIO address space that is configured to facilitate DMA data transfers between these buffers and memory using techniques well known in the networking art.

None all or a portion of the MAC layer operations may be implemented in software running on host processor . In one embodiment using a split MAC architecture Ethernet packet encapsulation and decapsulation operations are implemented in software while Ethernet framing and deframing is implemented via hardware e.g. via embedded logic or embedded software running on packet processing engine NPU on network interface .

The RMA write and RMA schemes employing AM requests AM replies and associated AM handlers provides advantageous over existing RMA techniques. For example since these schemes may be implemented via software executing on a host RMA data transfers that previously required specially configured hardware e.g. InfiniBand HCAs may be extended to use with other protocols such as but not limited to Ethernet. The schemes may be combined with existing techniques such as use of PSM or tagged messaging APIs to further enhance functionality and performance.

Further aspects of the subject matter described herein are set out in the following numbered clauses 

1. A method for performing Remote Memory Access RMA data transfers between a remote node and a local node the method comprising 

sending a first Active Message AM write request from the local node to an AM handler on the remote node the first AM write request containing data to be written and a starting address in a remote memory address space on the remote node at which the data is to be written and

handling the first AM write request with the AM handler on the remote node by extracting the data from the first AM write request and writing the data into an address range in the remote memory address space beginning at the starting address.

sending an AM write reply from the remote to the local node the AM write reply indicating the data has been successfully written into the remote memory address space and

sending a respective AM request from the local node to the AM handler on the remote node containing the packet data and a starting address in a remote memory address space on the remote node at which the packet data is to be written and

handling the respective AM request with the AM handler on the remote node by extracting the packet data from the respective AM request and writing the data into an address range in the remote memory address space beginning at the starting address 

wherein the first AM write request corresponds to an AM write request used to transfer a first packet of data of the plurality of packets.

detecting that all of the packet data has been successfully written to the remote memory address space 

sending an AM reply from the remote to the local node indicating the packet data has been successfully written into the remote memory address space and

performing an RMA read under which data is read from the remote node and transferred to the local node by 

sending an AM read request to the AM handler on the remote node the AM read request identifying an address range in the remote address space of data to be read 

in response to receiving the AM read request message retrieving the data to be read from the remote address space via the AM handler on the remote node and sending the retrieved data to the local node via an AM read reply message and

handling the AM read reply with an AM handler on the local node by extracting the data from the AM read reply and writing the data into a destination buffer on the local node.

performing an RMA read under which data is read from the remote node and transferred to the local node using a plurality of packets wherein data for each of the plurality of packets is transferred by 

sending a respective AM read request to the AM handler on the remote node the AM read request identifying an address range in the remote address space of packet data to be read 

in response to receiving the AM read request message retrieving the packet data to be read from the remote address space via the AM handler on the remote node and sending the retrieved packet data to the local node via an AM read reply message and

handling the AM read reply with an AM handler on the local node by extracting the packet data from the AM read reply and writing the packet data into a destination buffer on the local node.

employing the AM handler on the remote node to inspect the tagged message to verify the remote node is the intended recipient of the first AM write request.

8. The method of any of the proceeding clauses further comprising registering at the local node at least one address range in the remote memory address space on the remote node into which data may be written using one or more AM write requests sent from the remote node.

publishing an access key to the remote node corresponding to at least one address range registered with the local node 

inspecting the access key via the AM handler on the remote node to validate whether the first AM write request is permitted.

10. A non transient machine readable medium having first and second sets of instructions stored thereon configured to be respectively executed on a local and remote node to implement the method of any of the proceeding clauses.

11. A method for performing Remote Memory Access RMA data transfers between a remote node and a local node the method comprising 

sending a first Active Message AM write request from the local node to an AM handler on the remote node the first AM write request identifying an address range in a remote memory address space on the remote node at which the data is to be written 

reading data to be written from a source buffer on the local node and sending the data to the remote node 

processing the data that is received by the remote node to cause the data to be written into the remote memory address space to occupy the address range identified in the first AM write request.

receiving a plurality of AM write requests each AM write request identifying an address range in the remote memory address space on the remote node at which a block of data associated with that AM write request that is to be subsequently sent is to be written each AM write request including indicia identifying the block of associated data 

enqueuing via the AM hander on the remote node each AM write request in an RMA write queue on the remote node 

receiving a plurality of blocks of data from the local node each block of data associated with a previously received AM write request and containing indicia from which the previously received AM write request can be identified 

processing each dequeued AM write request to determine where the received block of data associated with that AM write request is to be written in the remote memory address space.

13. The method of clause 11 or 12 further comprising performing an RMA read under which data is read from the remote node and transferred to the local node by 

sending an AM read request to the AM handler on the remote node the AM read request identifying an address range in the remote address space of data to be read 

in response to receiving the AM read request message generating via the AM handler on the remote node an RMA read request corresponding to the AM read request identifying the address range in the remote address space of data to be read 

processing the RMA read request on the remote node resulting in the data to be read from the remote address space as defined by the address range in the RMA read request being retrieved from the remote address space and sent to the local node and

writing the retrieved data that is sent from the remote node into a destination buffer on the local node.

in response to receiving the AM read request message generating and enqueuing via the AM handler on the remote node an RMA read request corresponding to the AM read request in an RMA read request queue on the remote node identifying the address range in the remote address space of data to be read 

retrieving the data to be read from the remote address space as defined by the address range in the RMA read request and sending the retrieved data to the local node.

15. The method of clause 14 wherein the dequeueing data retrieval and sending operations are performed by an RMA read function on the remote node that is separate from the AM handler on the remote node.

16. The method of any of clauses 11 15 further comprising registering at the local node at least one address range in the remote memory address space on the remote node into which data may be written using one or more AM write requests sent from the remote node.

publishing an access key to the remote node corresponding to at least one address range registered with the local node 

inspecting the access key via the AM handler on the remote node to validate whether the first AM write request is permitted.

18. A non transient machine readable medium having first and second sets of instructions stored thereon configured to be respectively executed on a local and remote node to implement the method of any of clauses 11 17.

a write request Active Message AM handler configured to receive via the network interface a first AM write request sent from a remote apparatus over a communication link coupled to the network interface the first AM write request corresponding to a Remote Memory Access RMA write issued by the remote apparatus and containing first data to be written at a starting address in the local memory address space in the memory at which the data is to be written 

handle the first AM write request by extracting the data from the first AM write request and writing the data into an address range in the remote memory address space beginning at the starting address and

send an AM write reply to the remote apparatus indicating the data has been successfully written into the remote memory address space.

an RMA write module configured to perform an AM write operation under which a second AM write request corresponding to an RMA write to a remote memory address space in memory on the remote apparatus is generated and sent to the remote apparatus the second AM write request containing second data to be written at a starting address in the remote memory address space at which the data is to be written and

a write reply AM handler configured to process an AM write reply sent from the remote apparatus upon successfully writing the second data into the remote memory address space.

21. The apparatus of clause 20 further comprising a source buffer and wherein the RMA write module is further configured to 

sending a respective AM write request to a write request AM handler on the remote apparatus containing the packet data and a respective starting address in the remote memory address space on the remote apparatus at which the packet data is to be written.

22. The apparatus of any of clauses 19 21 wherein the write request AM handler is further configured to 

receive a plurality of AM write requests from the remote apparatus each of the plurality of AM write requests containing respective packet data corresponding to a remote write of third data that is partitioned into a plurality of packets and is to be written into the local memory address space at a respective starting address in the local memory address space 

extract the packet data for each of the plurality of AM write requests and write the packet data into the local memory address space beginning at the starting address identified by that AM write request 

send an AM write reply to the remote apparatus indicating the third data has been successfully written into the local memory address space.

generate and send an AM read request to a read request AM handler on the remote apparatus the AM read request identifying an address range in the remote address space of data of the remote apparatus to be read 

in response to the AM read request receiving from the remote apparatus an AM read reply containing the data read from the remote address space and

handle the AM read reply with the read reply AM handler by extracting the data from the AM read reply and writing the data into the destination buffer.

24. The apparatus of any of clauses 19 23 wherein the RMA read module is further configure to performing an RMA read under which data is read from the remote apparatus and transferred using a plurality of packets wherein data for each of the plurality of packets is remotely read by 

sending a respective AM read request to the AM read request handler on the remote apparatus the AM read request identifying an address range in the remote address space of packet data to be read 

in response to each respective AM read request receiving from the remote apparatus an AM read replay containing the packet data read from the remote address space and

handling the AM read reply with the read reply AM handler by extracting the packet data from the AM read reply and writing the packet data into the destination buffer.

receive an AM read request from the remote apparatus identifying an address range in the local address space of data containing data to be read 

receive via the network interface a plurality of AM write requests sent from a remote apparatus over a communication link coupled to the network interface each AM write request corresponding to a Remote Memory Access RMA write issued by the remote apparatus and containing respective data to be written into the local memory address space and a starting address at which a start of the respective data is to be written and

receive a plurality of blocks of data from the remote apparatus each block of data associated with a previously received AM write request and containing indicia from which a corresponding RMA write request can be identified 

dequeue the RMA write requests from the RMA write queue and process each dequeued RMA write request to determine where the received block of data associated with that RMA write request is to be written in the local memory address space.

send an AM write request to the remote apparatus the AM write request identifying an address range in a remote memory address space in memory on the remote apparatus into which the data is to be written 

send the data to the remote apparatus wherein the data is sent subsequent to sending the AM write request and the data is sent along with indicia configured to be used to match the data that is sent to the AM write request.

receive an AM read request from the remote apparatus identifying an address range in the local address space of data to be read 

in response to receiving the AM read request message generate a corresponding an RMA read request identifying the address range in the local address space of data to be read and

send an AM read request to the remote apparatus the AM read request identifying an address range in a remote address space in memory on the remote apparatus to be read 

30. An non transient machine readable medium having instructions stored thereon configured to be executed on a node including a network interface and memory including a local address space the instructions including 

receive via the network interface a first AM write request sent from a remote apparatus over a communication link coupled to the network interface the first AM write request corresponding to a Remote Memory Access RMA write issued by the remote apparatus and containing first data to be written at a starting address in the local memory address space in the memory at which the data is to be written 

handle the first AM write request by extracting the data from the first AM write request and writing the data into an address range in the remote memory address space beginning at the starting address and

send an AM write reply to the remote apparatus indicating the data has been successfully written into the remote memory address space.

31. The non transient machine readable medium of clause 30 further including instructions comprising 

an RMA write module configured to perform an AM write operation under which a second AM write request corresponding to an RMA write to a remote memory address space in memory on the remote apparatus is generated and sent to the remote apparatus the second AM write request containing second data to be written at a starting address in the remote memory address space at which the data is to be written and

a write reply AM handler configured to process an AM write reply sent from the remote apparatus upon successfully writing the second data into the remote memory address space.

32. The non transient machine readable medium of clause 31 wherein the node further comprises a source buffer and wherein the RMA write module is further configured to 

sending a respective AM write request to a write request AM handler on the remote apparatus containing the packet data and a respective starting address in the remote memory address space on the remote apparatus at which the packet data is to be written.

33. The non transient machine readable medium of any of clauses 30 32 wherein the write request AM handler is further configured to 

receive a plurality of AM write requests from the remote apparatus each of the plurality of AM write requests containing respective packet data corresponding to a remote write of third data that is partitioned into a plurality of packets and is to be written into the local memory address space at a respective starting address in the local memory address space 

extract the packet data for each of the plurality of AM write requests and write the packet data into the local memory address space beginning at the starting address identified by that AM write request 

send an AM write reply to the remote apparatus indicating the third data has been successfully written into the local memory address space.

34. The non transient machine readable medium of any of clauses 30 33 wherein the node further comprises a destination buffer in the local memory and the instructions further comprise 

generate and send an AM read request to a read request AM handler on the remote apparatus the AM read request identifying an address range in the remote address space of data of the remote apparatus to be read 

in response to the AM read request receiving from the remote apparatus an AM read reply containing the data read from the remote address space and

handle the AM read reply with the read reply AM handler by extracting the data from the AM read reply and writing the data into the destination buffer.

35. The non transient machine readable medium of any of clauses 30 34 wherein the RMA read module is further configure to performing an RMA read under which data is read from the remote apparatus and transferred using a plurality of packets wherein data for each of the plurality of packets is remotely read by 

sending a respective AM read request to the AM read request handler on the remote apparatus the AM read request identifying an address range in the remote address space of packet data to be read 

in response to each respective AM read request receiving from the remote apparatus an AM read replay containing the packet data read from the remote address space and

handling the AM read reply with the read reply AM handler by extracting the packet data from the AM read reply and writing the packet data into the destination buffer.

36. The non transient machine readable medium of any of clauses 30 35 wherein the instructions further comprise 

receive an AM read request from the remote apparatus identifying an address range in the local address space of data containing data to be read 

37. An non transient machine readable medium having instructions stored thereon configured to be executed on a node including a network interface and memory including a local address space the instructions including 

receive via the network interface a plurality of AM write requests sent from a remote apparatus over a communication link coupled to the network interface each AM write request corresponding to a Remote Memory Access RMA write issued by the remote apparatus and containing respective data to be written into the local memory address space and a starting address at which a start of the respective data is to be written and

receive a plurality of blocks of data from the remote apparatus each block of data associated with a previously received AM write request and containing indicia from which a corresponding RMA write request can be identified 

process each dequeued RMA write request to determine where the received block of data associated with that RMA write request is to be written in the local memory address space.

38. The non transient machine readable medium of clause 37 wherein the node further comprises further a source buffer in the memory and wherein the instructions further comprise 

send an AM write request to the remote apparatus the AM write request identifying an address range in a remote memory address space in memory on the remote apparatus into which the data is to be written 

send the data to the remote apparatus wherein the data is sent subsequent to sending the AM write request and the data is sent along with indicia configured to be used to match the data that is sent to the AM write request.

39. The non transient machine readable medium of clause 37 or 38 wherein the node further comprises an RMA read request queue and wherein the instructions further comprise 

receive an AM read request from the remote apparatus identifying an address range in the local address space of data to be read 

in response to receiving the AM read request message generate a corresponding an RMA read request identifying the address range in the local address space of data to be read and

40. The non transient machine readable medium of clause 39 wherein the node further comprises a destination buffer occupying a portion of the memory and wherein the instructions further comprise 

send an AM read request to the remote apparatus the AM read request identifying an address range in a remote address space in memory on the remote apparatus to be read 

Although some embodiments have been described in reference to particular implementations other implementations are possible according to some embodiments. Additionally the arrangement and or order of elements or other features illustrated in the drawings and or described herein need not be arranged in the particular way illustrated and described. Many other arrangements are possible according to some embodiments.

In each system shown in a figure the elements in some cases may each have a same reference number or a different reference number to suggest that the elements represented could be different and or similar. However an element may be flexible enough to have different implementations and work with some or all of the systems shown or described herein. The various elements shown in the figures may be the same or different. Which one is referred to as a first element and which is called a second element is arbitrary.

In the description and claims the terms coupled and connected along with their derivatives may be used. It should be understood that these terms are not intended as synonyms for each other. Rather in particular embodiments connected may be used to indicate that two or more elements are in direct physical or electrical contact with each other. Coupled may mean that two or more elements are in direct physical or electrical contact. However coupled may also mean that two or more elements are not in direct contact with each other but yet still co operate or interact with each other.

An algorithm is here and generally considered to be a self consistent sequence of acts or operations leading to a desired result. These include physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like. It should be understood however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities.

An embodiment is an implementation or example of the inventions. Reference in the specification to an embodiment one embodiment some embodiments or other embodiments means that a particular feature structure or characteristic described in connection with the embodiments is included in at least some embodiments but not necessarily all embodiments of the inventions. The various appearances an embodiment one embodiment or some embodiments are not necessarily all referring to the same embodiments.

Not all components features structures characteristics etc. described and illustrated herein need be included in a particular embodiment or embodiments. If the specification states a component feature structure or characteristic may might can or could be included for example that particular component feature structure or characteristic is not required to be included. If the specification or claim refers to a or an element that does not mean there is only one of the element. If the specification or claims refer to an additional element that does not preclude there being more than one of the additional element.

As discussed above various aspects of the embodiments herein may be facilitated by corresponding software and or embedded components and applications such as software running on a server or device processor or software and or firmware executed by an embedded processor or the like. Thus embodiments of this invention may be used as or to support a software program software modules firmware and or distributed software executed upon some form of processing core such as the CPU of a computer one or more cores of a multi core processor a virtual machine running on a processor or core or otherwise implemented or realized upon or within a computer readable or machine readable non transitory storage medium. A computer readable or machine readable non transitory storage medium includes any mechanism for storing or transmitting information in a form readable by a machine e.g. a computer . For example a computer readable or machine readable non transitory storage medium includes any mechanism that provides i.e. stores and or transmits information in a form accessible by a computer or computing machine e.g. computing device electronic system etc. such as recordable non recordable media e.g. read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices etc. . The content may be directly executable object or executable form source code or difference code delta or patch code . A computer readable or machine readable non transitory storage medium may also include a storage or database from which content can be downloaded. The computer readable or machine readable non transitory storage medium may also include a device or product having content stored thereon at a time of sale or delivery. Thus delivering a device with stored content or offering content for download over a communication medium may be understood as providing an article of manufacture comprising a computer readable or machine readable non transitory storage medium with such content described herein.

Various components referred to above as processes servers or tools described herein may be a means for performing the functions described. The operations and functions performed by various components described herein may be implemented by software running on a processing element via embedded hardware or the like or any combination of hardware and software. Such components may be implemented as software modules hardware modules special purpose hardware e.g. application specific hardware ASICs DSPs etc. embedded controllers hardwired circuitry hardware logic etc. Software content e.g. data instructions configuration information etc. may be provided via an article of manufacture including computer readable or machine readable non transitory storage medium which provides content that represents instructions that can be executed. The content may result in a computer performing various functions operations described herein.

As used herein a list of items joined by the term at least one of can mean any combination of the listed terms. For example the phrase at least one of A B or C can mean A B C A and B A and C B and C or A B and C.

The above description of illustrated embodiments of the invention including what is described in the Abstract is not intended to be exhaustive or to limit the invention to the precise forms disclosed. While specific embodiments of and examples for the invention are described herein for illustrative purposes various equivalent modifications are possible within the scope of the invention as those skilled in the relevant art will recognize.

These modifications can be made to the invention in light of the above detailed description. The terms used in the following claims should not be construed to limit the invention to the specific embodiments disclosed in the specification and the drawings. Rather the scope of the invention is to be determined entirely by the following claims which are to be construed in accordance with established doctrines of claim interpretation.

