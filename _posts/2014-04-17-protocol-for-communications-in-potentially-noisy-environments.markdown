---

title: Protocol for communications in potentially noisy environments
abstract: A communications protocol that is designed for transmission of data in networks that are subjected to harsh conditions is described herein. A network includes a plurality of devices, where the devices comprise respective nodes. The nodes are in communication with one another by way of a central network hub. The protocol causes the nodes to transmit data over a network bus at different data rates depending upon whether the nodes are operating normally or an arbitration procedure has been invoked.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09258244&OS=09258244&RS=09258244
owner: Sandia Corporation
number: 09258244
owner_city: Albuquerque
owner_country: US
publication_date: 20140417
---
This application claims priority to U.S. Provisional Patent Application No. 61 818 354 filed on May 1 2013 and entitled Foundation Communications Bus the entirety of which is incorporated herein by reference.

This invention was developed under Contract DE AC04 94AL85000 between Sandia Corporation and the U.S. Department of Energy. The U.S. Government has certain rights in this invention.

Devices in networked systems e.g. a network transmit communications between one another to accomplish tasks. Some networks can be subjected to harsh environments such as those that include noise radiation and other environmental factors. Even in a harsh environment devices in these networks must be able to communicate with one another. While conventional communications protocols such as Ethernet are well suited for most networks these conventional protocols lack sufficient features for the networks referenced above.

The following is a brief summary of subject matter that is described in greater detail herein. This summary is not intended to be limiting as to the scope of the claims.

A communications protocol for managing the transmission of data packets across a network is shown and described. Further a method of managing data transmission within a network using the above referenced protocol is shown and described. Still further a method for testing operation of a network utilizing the above referenced communications protocol is shown and described.

An exemplary network includes a plurality of devices that are in network communication with one another the devices configured to transmit and receive data over the network in accordance with the protocol referenced above. The devices include respective applications which are configured to generate and consume data. The devices further include respective nodes wherein each node is configured to communicate over the network in accordance with the protocol. The devices further include interfaces that respectively interface nodes with applications.

For instance as referenced above a device communicating over the network includes a node an interface and an application. When the device is receiving data the node receives a data packet that conforms to the protocol. The interface receives the data packet from the node and generates output data based upon the data packet wherein the output data is configured for consumption by the application. The application receives the output data and optionally can generate new data based upon the output data. When the device is transmitting data the application outputs data and the interface formats the data in a suitable format for the node. The node then transmits a data packet over the network in conformance with the protocol.

The protocol has various features that are well suited for network implementation in harsh environments. For example the protocol supports isolation of an application from low level network management. Additionally firewalls can be provided by way of the protocol such that safety critical traffic is distributed over the network only to applications that are authorized to receive such traffic. Still further the protocol facilitates prevention of lockups wherein state machines in the network can be forced to a known state when transactions of interfaces are ended or bus activity aborts.

In yet another exemplary embodiment the protocol facilitates determining whether an application that is to receive a message is busy and whether the application accepts the message thus reducing the burden on the application that is to receive the data. The protocol further facilitates the bus operating without need of a master bus controller thereby reducing management overhead and increasing reliability for critical functions. In addition the protocol prevents lost packets due to collisions which can occur in conventional protocols.

Still further headers of data packets and payloads of data packets when configured in accordance with the protocol include application data that facilitates prevention of corrupted data from being transmitted over the network. Thus for example an application can reject a data packet that has been corrupted by noise in a harsh environment.

The above summary presents a simplified summary in order to provide a basic understanding of some aspects of the systems and or methods discussed herein. This summary is not an extensive overview of the systems and or methods discussed herein. It is not intended to identify key critical elements or to delineate the scope of such systems and or methods. Its sole purpose is to present some concepts in a simplified form as a prelude to the more detailed description that is presented later.

Various technologies pertaining to a communications protocol that facilitates secure reliable communications in a harsh environment are now described with reference to the drawings wherein like reference numerals are used to refer to like elements throughout. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of one or more aspects. It may be evident however that such aspect s may be practiced without these specific details. In other instances well known structures and devices are shown in block diagram form in order to facilitate describing one or more aspects. Further it is to be understood that functionality that is described as being carried out by certain system components may be performed by multiple components. Similarly for instance a component may be configured to perform functionality that is described as being carried out by multiple components.

Moreover the term or is intended to mean an inclusive or rather than an exclusive or. That is unless specified otherwise or clear from the context the phrase X employs A or B is intended to mean any of the natural inclusive permutations. That is the phrase X employs A or B is satisfied by any of the following instances X employs A X employs B or X employs both A and B. In addition the articles a and an as used in this application and the appended claims should generally be construed to mean one or more unless specified otherwise or clear from the context to be directed to a singular form.

Further as used herein the terms component and system are intended to encompass computer readable data storage that is configured with computer executable instructions that cause certain functionality to be performed when executed by a processor. The computer executable instructions may include a routine a function or the like. It is also to be understood that a component or system may be localized on a single device or distributed across several devices. Additionally as used herein the term exemplary is intended to mean serving as an illustration or example of something and is not intended to indicate a preference.

With reference to an exemplary network system is illustrated wherein devices in the system communicate with one another by way of a protocol referred to herein as the foundation protocol. The system includes a plurality of devices collectively referred to as devices which execute respective applications collectively referred to as applications . The devices can be or include any suitable devices including computing devices network infrastructure devices application specific integrated circuits ASICs field programmable gate arrays FPGAs etc. The applications are configured to consume and produce data in accordance with their respective configurations. For example an application in the applications can be programmed in software to consume and produce the data or can be configured in hardware to produce and consume the data etc.

The devices further comprise respective nodes referred to collectively as nodes wherein the nodes are configured to facilitate receipt and transmittal of data over a bus in accordance with the foundation protocol. A node can be an ASIC an FPGA a processor a portion thereof etc. that is configured to communicate over a bus by way of the foundation protocol. The devices also include interfaces collectively referred to as interfaces that respectively interface the applications with the nodes . In an example the interface can inform the application as to whether data generated by the application for transmittal was successfully transmitted whether errors were generated type of errors etc. For example the interface can receive data from its application for transmittal and confirm to the application that the data was successfully transmitted.

The network system further includes a hub through which all communications between the devices pass. Communications channels communicatively couple the devices in the network system e.g. by way of the hub . The communications channels can be any suitable communications channels including wireless wired parallel or serial. Additionally test or monitoring equipment not shown can be coupled to the hub to monitor data being sent over the network system .

Based upon instructions from the applications the nodes transmit packets that include payloads referred to as data and headers over the bus e.g. formed from the hardware and associated software that facilitates communications between the devices . In an exemplary embodiment each of the nodes can only listen for its own address. In comparison testing or monitoring equipment coupled to the hub can listen for all communications within the system . Thus the system provides improved testing of communications within the system relative to conventional systems that communicate using conventional protocols. Moreover as will be described herein the foundation protocol facilitates management of speed of transmissions of data within the system manages firewalls e.g. without requiring a master bus controller etc. This reduces management overhead and increases reliability for system critical functions. The foundation protocol further permits global messaging to all addresses within the system as well as blind broadcast features that increase bandwidth without safety concerns that can be used for diagnostics.

The protocol also permits testing of the data in the system to determine whether any corruption has occurred due to noise radiation or other external factors that are present within the system . The system can further provide feedback for every application requested operation that occurs within the system . The system for instance utilizes a plug and play bus kernel that provides a common backbone for future equipment design and can interface with both legacy systems and newly designed host platforms.

Additional detail pertaining to the protocol is now set forth. The protocol defines an addressing scheme that provides full traceability for testing functions within the system . As communications are transferred across the system a source device address a destination device address a function e.g. application or object used by the application within the destination device that the data belongs to the type of data in the case of instrumentation a time the data was requested to be sent by the application that transmits the data and a time the data was actually transmitted by a node are all completely visible for diagnostic purposes.

The nodes when programmed to transmit and receive data by way of the foundation protocol can further include logic that causes them to act as protocol controllers. When acting as a protocol controller for example the node provides special features that isolate the application from low level network management. When requested by the application the node automatically manages bus transactions and will notify the application when the bus transactions are complete. The state of transactions may be monitored using a status code. The nodes can further provide firewalls to allow safety critical traffic to only be distributed to authorized applications.

Further when acting as a protocol controller the node for instance can prevent lockups of the communications system . State machines of the node can be forced to a known state when transactions performed by the interface are ended or bus activity aborts. The foundation protocol has features that automatically allow the node to determine if a recipient application e.g. the application at the other end is busy and if the other end accepts the message. The burden on the applications is reduced by design in the foundation protocol.

The protocol is particularly well suited for fast transmission of time critical control messages and bandwidth for instrumentation functions can be optimized. The protocol can further support an arbitration scheme which prevents lost packets due to collisions that can sometimes occur in conventional protocols. As indicated previously packets include both the header which comprises address information and payload which comprises data generated by an application. The protocol includes built in protection for both the header and the payload in order to prevent corrupted data from being used within the system . This prevents packets from being accepted that have been corrupted by different types of noise in harsh environments. Data is only received at an intended recipient application e.g. application if the data passes error detection checks built into the protocol. A sending node which in examples herein refers to the node automatically determines the state of each transmission request. The header and payload structure of the packets is optimized to allow for event based functions to occur.

The foundation protocol when implemented in a networked system such as the system increases the reliability of the system as fewer cabling for interconnections is required compared to conventional network systems configured for operation in harsh environments e.g. which include point to point connections . Moreover the protocol facilitates re configurability to achieve new capabilities resulting in lower system cost relative to conventional network systems deployed in harsh environments . Plug and play capability is provided because the communications hub includes ports that can be utilized by the designer to investigate occurrences within the system. The system is designed so that it will not lock up and will always self recover.

As indicated previously the nodes are in communication with respective applications by way of respective interfaces . Each of the nodes can be broken into two separate sections one where the nodes act as transmitters one when the nodes act as receivers. A top level structure of an exemplary node is illustrated in Error Reference source not found.3. A block diagram of the top level signals of the node and each signal interface is shown in Error Reference source not found.4.

Nodes can be implemented as respective chips e.g. ASICS or FPGAs and can send and receive data by way of pins on respective communications boards upon which the chips reside. The pins can respectively correspond to other nodes in the network system . Thus for a particular node e.g. node the pins can be set to define other nodes with which the particular node can communicate. For instance the node can be in a chip that comprises at least 6 pins one for each of the other nodes in the system . Whether or not the pin is tied to ground can define whether the node can communicate with another node that corresponds to the pin. Thus a designer of the system can define the communication paths such that communications can be restricted based upon the pin definitions. Information concerning exemplary pin definitions is depicted in Table 1 below.

In an exemplary embodiment the nodes can be hardware designed in VHDL. As indicated previously a node can include definitions for the foundation protocol receive and transmit memories and error checking logic.

As shown in the nodes transmit packets that include data over the bus. Each of the nodes can send packets only when they have control of the bus preventing multiple packets from being sent by multiple nodes over the bus at one time. Pursuant to an example the node can gain control of the bus and can transmit packets for receipt by other nodes in the network system . When packets are sent by the node the packets pass through the hub and reaches at least one recipient node e.g. the node . The recipient node performs a cyclic redundancy check CRC over contents of the payload to generate a CRC value and determines whether to accept or reject the packet based upon the CRC. Specifically the transmitter node can generate a first CRC value for the payload and can include the first CRC value in the data packet . The recipient node computes a second CRC value based upon content of the payload and compares the second CRC value with the first CRC value to ensure that contents of the payload have not altered during transmission e.g. due to harsh environment conditions .

When the recipient node detects errors it disregards the packet and can optionally transmit an indication to the transmitting node that the packet was rejected. The transmitting node is informed that the packet was not accepted e.g. by the destination node and the transmitting node can retransmit the data packet if desired. When processing the packet if the recipient node detects an error the recipient node can return to a previous state e.g. reset if desired .

The nodes can also be configured in accordance with the foundation protocol to timestamp data packets thereby allowing for continuous end to end monitoring of traffic through the system .

The protocol also supports an arbitration scheme that can be used to ascertain which of the nodes has control of the bus for transmittal of data. The arbitration scheme prevents collisions and is described in greater detail herein.

An exemplary arbitration scheme is depicted in . A unique feature of the arbitration scheme is that the data rate during arbitration is different than the data rate during normal data transmission. With more particularity during normal data transmission the packets desirably travel at high speeds allowing for near real time control regardless as to whether the packets travel over long distances. During arbitration however the nodes transmit data at slower rates wherein a different between the normal data rate and the slower data rate can be based upon lengths of cabling in the system e.g. a difference in length between shortest cabling and longest cabling in the system . Effectively this allows for the nodes to transmit data at high speeds over relatively long distances during normal transmissions but ensures prevention of collision.

In an example the transmitter node wishes to transmit data over the bus and monitors the bus for communications at e.g. will listen for communications from the hub . When the transmitter node detects that the bus is idle for a threshold amount of time the node can initiate an arbitration process by transmitting a request for control of the bus to the hub at . The node in this example transmits the request at a first data rate e.g. the slower data rate . During this time period the transmitter node waits to receive confirmation from the hub as to whether the node is able to transmit packets over the bus and remains idle. The hub receives the request and in this example determines that the transmitter node is able to transmit packets over the bus. The hub transmits a confirmation packet to the first node at e.g. at a second data rate that is faster than the first data rate . The hub further transmits packets to other nodes in the system at e.g. the recipient node informing the other nodes that the transmitter node has control of the bus. Responsive to receiving the confirmation the transmitter node becomes aware that it has control of the bus and can transmit packets to other nodes e.g. the recipient node by way of the hub where the transmitter node transmits the packets at the second faster data rate.

As indicated previously the foundation protocol is well suited for systems such as the network system that operate in harsh environments yet require reliable transmittal of data between devices in the network system . The arbitration process described herein facilitates prevention of collisions and further allows for differing cable lengths between nodes and still further allows for transmittal of data between nodes at high speeds. For example if the data rates were not differed then a node in close proximity to the hub could request control of the bus where the request is transmitted at high speed receive an indication from the hub that the node has control of the bus and thereafter send data packets that collide with data packets transmitted from a different node that is positioned far from the hub . In an exemplary embodiment the second data rate can be at least double the first data rate.

When both the first and second nodes attempt to control the bus such nodes can transmit requests to the hub and await a response from the hub . The hub outputs data packets to the nodes that identify which node has control of the bus and the winning node upon receipt of the data packet that indicates that it has control of the bus transmits at high speed. Thus for instance the hub can indicate that the transmitter node has control of the bus and the transmitter node can transmit at a high data rate. The recipient node retains the data that it wants to transmit and waits for the bus to be idle for the threshold amount of time to submit another request for the bus to the hub . The recipient node can continue to submit requests when the bus is idle until the hub indicates it has control of the bus or until some threshold amount of time has passed e.g. 10 milliseconds at which point in time the recipient node can inform its application e.g. by way of its interface that it is unable to transmit data.

Returning to additional detail pertaining to operation of the hub is now set forth. The hub transmits packets to all nodes in the network system to indicate to such nodes that the bus is being used by one of the nodes. For instance the data transmitted by the hub can be an address of the node in control of the bus. Furthermore the hub can be configured with fault detection capability where the hub is configured to identify fault conditions auto disable a link of the network system believed to be failing etc. For instance if the hub sees noise chattering or certain behavior that is not conforming to predefined bit timing the hub can disable a port therein that is associated with that network link. In an exemplary embodiment the hub is not configured to analyze content of the payloads when performing fault detection but instead for searches certain elementary types of noise and can disable ports when those types of noise are detected. The hub can periodically reactivate the port to ascertain whether the noise has ceased thus allowing for links of the network system to be reconnected.

Moreover while not shown the network system can include a sub hub where the sub hub is coupled to a plurality of nodes and directs communications to such nodes to the hub . Utilization of a sub hub increases the number of devices that can be included in the network system .

Further detail pertaining to the data packets is now set forth. The packets transmitted from and received by nodes in the system include the header and payload . The header comprises the information for addressing the packet in the system such that the packet reaches the intended recipient. The payload comprises data that is to be consumed by a recipient device. In an exemplary embodiment a transmitting node can transmit a header of a packet to the recipient node whereupon the recipient node performs a CRC check on the header . The recipient node outputs a confirmation receipt that is received by the transmitting node resulting in the transmitting node transmitting the payload . The recipient node performs a CRC check on the payload to ensure that the payload has not been corrupted. The recipient node upon receiving the payload confirms receipt. I the recipient node fails to emit a confirmation receipt the transmitting node fails to continue transmitting packets .

As shown in an exemplary header of a data packet comprises numerous fields composed of 119 bits including bit stuffing . The addressing scheme allows for the possibility of addressing nodes . Each field of the header is outlined as shown in . The fields within the header include 1 start of frame 2 source module 3 re sync 4 destination module 5 destination object 6 timestamp 7 payload length 8 header CRC 9 header ACK 10 application busy and 11 guard. Each field in the packet is shown as being a particular number of bits in size. Each bit can be driven on the line for one bit time except for the source module where each bit can be driven for two bit times with a bit time defined as being five clock cycles in length. Logic 0 on a bus line can be defined as the bus line being DOMINANT. Logic 1 on a bus line can be defined as the bus line being RECESSIVE.

The bus may exhibit a recessive state until the receiving node that is in control of the bus transmits an acknowledgement ACK . Bit stuffing starts with a bit inserted immediately before the destination node field. Bit stuffing then inserts a stuff bit after every header byte and ends after the bit stuff following the last byte of the header CRC. The header ACK field and application busy field are not included in the bit stuff. Bit stuffing resumes with a bit stuff inserted immediately before the first payload byte and inserts a bit stuff after every payload byte ending after the bit stuff following the last byte of the payload CRC.

The Start of Frame SOF field identifies the start of a frame and is 1 bit. This bit time can provide the event that nodes can use to start packet processing. The SOF can be detected when the bus goes from the bus idle sometimes called inter packet state to the active state when the bus is driven dominant for one bit time after the bus idle state. The falling edge on the bus receive line when the bus is determined to be idle constitutes the start of the SOF but the SOF field need not be sampled at any other point.

The source module field takes up 8 bits and identifies the device or node that originates the packet . Arbitration occurs in this field with for example the node having the lowest address being given the highest priority.

The Re sync field is a 1 bit stuff immediately following the field and allows the receiving node to re sync with the transmitting node that wins during an arbitration process. The field goes recessive for two bit times then drives dominant for one bit time which forces re sync. The re sync field is utilized to synchronize the node after arbitration. If the re sync field is changed then the data will be decoded incorrectly and the packet should not be received by the recipient application .

The destination module field is 8 bits 1 bit stuff immediately following such bits. The destination module field identifies the node or device that is to receive the packet .

The destination object ID field is 16 bits 1 bit stuff immediately following each byte and identifies the object e.g. application within the destination device that is to receive the packet . The destination object addresses in the range 0X0000 0X000F can be reserved for internal node diagnostic use and are used by external users.

For testability reasons a bus monitor or a telemetry system can be included and coupled to the hub . The header structure can be designed to provide a method of fingerprinting every packet viewed on the bus by the bus monitor or the telemetry system. This allows for identifying the transmitting node that sent the packet the destination node and the destination object to which the packet was addressed.

The Timestamp field is 32 bits 1 bit stuff immediately following each byte. This field is automatically added to the packet when the send request line at an input port of the communications board that is coupled to the application is asserted by the sending node internal state machine. This provides a method of generating a timeline of events when post processing data. In addition the bus monitor can time stamp the packet when the packet reaches the hub e.g. when the monitor sees the packet . This permits an analysis of hold off delays.

The Payload Length field is 8 bits 1 bit stuff immediately following the field. The payload length field indicates the number of bytes that are included in the payload section of the packet . In an example internal nodes can be restricted to 256 byte packet receptions. To calculate payload length Length number of payload bytes 1.

The Header CRC field is 16 bits 1 bit stuff immediately following each byte. The Header CRC field protects the system from accepting misaddressed packets that could be caused by a bit changing state in the header field while the packet is being sent across the physical layer of the bus. Addressing errors are detected and bad packets are discarded. The CRC calculation skips the SOF field and starts with the first bit of the source module field. It then pauses after including the last bit of source module field. It skips re sync field 3 bits and resumes on the first bit of the Destination Module field. It ends after calculating the last bit of the Payload Length field.

The Header ACK field is 7 bits with no bit stuff. The Header ACK allows the receiver node to handshake with the transmitter node and indicate whether the recipient node accepts the header portion of the packet . The header ACK field is driven recessive by the transmitter node for the 7 bit times but will be overridden by the recipient node if an acknowledge is sent.

If the recipient node is able to accept the packet because there is no CRC or bit stuff error it will drive the bus dominant as soon as it determines that the packet is valid and error free. The transmitting node can sample the last three clock cycles of the 7bit of the ACK field to determine if the recipient node has acknowledged the header. All three of these sample points are to be seen as dominant in order for the transmitter node to continue.

The system is capable of a blind broadcast function where the ACK fields are disabled. Blind broadcasts are used for testing purposes and provide greater bandwidth. With blind broadcasts the application can broadcast information so that it shows up on the bus so it can get tested but without anybody on the bus being able to receive it other than the testing device.

The system is also capable of a global broadcast where receiving nodes will respond during the ACK fields. During a global broadcast if the recipient node already has a packet in its RX buffer the recipient node will not accept the packet and no error will be indicated by the transmitting node since the transmitting node does not check the busy field on a global broadcast. An auto response can be built into the application of the nodes to provide the transmitter node assurance that each node received the global broadcast. The global broadcast permits the transmission of a single message to all the nodes .

The Application Busy field is 7 bits with no bit stuff. Bit state is driven by the recipient node . The internal state of busy is sampled at SOF and reported at this bit time. Dominant means that the recipient node is busy while recessive means that the recipient node is not busy. The app busy field is driven recessive by the transmitter node during the 7 bit times but will be overridden by the receiving node if the receiving node is not able to accept the packet because its receive buffer was not empty when the SOF field was sent. If the destination application is currently busy only if the receive buffer is not empty and is not able to process the packet the receiver node will drive the line dominant and override the transmitter node . The transmitter node will sample the last three clock cycles of the 7bit of the busy field to determine if the receiver node has acknowledged the header. All three of these sample points can be seen as recessive destination application not busy in order for the transmitter node to continue. If this bit is found to be dominant at any of the three sample times the transmitter node stops transmitting the packet . This provides feedback to the application as to why the header was not accepted receiver is busy .

The Guard field is 2 1 bit stuff immediately following the field. The Guard field is provided to account for cable and round trip delays and to protect the start of the time stamp field by preventing any overlapping from a hand shaking receiver node . The transmitter node will drive its line recessive during this field and the receiver node does not check this field.

The Payload section of the packet is where the application data can be transferred and includes two fields the Packet Payload and the Packet CRC. The fields that make up the application section and CRC of the payload are depicted in .

The Packet Payload field is also referred to as the application payload. The Packet payload is 8 bits Payload Byte Number 1 bit stuff immediately following each byte. The Packet Payload is variable to allow sending the required amount of data that is being requested to be sent by the application . The information is typically sent in block moves in the payload. The Packet Payload is the data being transferred between applications across the bus. The objects are defined by the applications on a per node basis. Objects are a tag to identify the type of data in the payload . The nodes move blocks of data between objects and do not have any knowledge of the objects structure. Objects have depth and reside at one address. The depth is limited by the maximum payload length. Payload length is a big driver of first in first out FIFO memory size requirements. The normal payload length is 1 to 256 bytes for all internal communications between nodes and any external to internal communications. Bit stuffing in the packet payload section inserts a bit stuff immediately before the first byte of the payload and immediately after every byte in the payload and CRC. Bit stuffing stops at the end of the CRC.

The Payload CRC field is 16 bits 1 bit stuff immediately following the field. The Payload CRC field is the calculated CRC as sent by the transmitting node . The CRC is calculated starting with the first bit of the packet payload byte and ending with the last bit of the last packet payload byte.

There are three fields that comprise the end of the packet structure. They include End of Frame Inter Packet Gap and Payload ACK. This is the portion of the packet that signals that the transmitting node is completing the transaction as shown in .

The Payload ACK field is 7 bits and the transmitting node drives the payload ACK field recessive during this field. The receiving node drives the payload ACK field dominant as soon as the CRC check is complete and the packet is accepted this overwrites the recessive value the transmitting node was putting out on its line during this field. The receiving node releases the ACK line at the end of the 7th bit time. The transmitting node samples the header field on the three clock cycles before the end of the seventh bit time. All three samples should agree that an acknowledgement was received otherwise an acknowledge error will occur. Both the header CRC and payload CRC should pass and no frame errors or bit stuff errors should have occurred. If any one of the listed errors occurred the receiving node can reject the packet.

During global blind broadcast the transmitter node drives the ACK dominant as ACK fields are not driven by the receiving nodes. The ACK field is ignored by the transmitting node for global blind broadcasts see Error Reference source not found.7 .

The End of Frame field is 22 bit times. The transmitting node drives the bus recessive for this part of the packet . No other transmitters can drive until 22 bit times have elapsed. If any transmitter node attempts to drive the bus during this time the receiving node will not process the packet .

The Inter Packet Gap field is traffic driven. The spacing between transmissions varies depending on the phase of equipment operation mission bus or activity on the instrumentation bus non mission bus . shows all the fields and their order of occurrence but does not include individual bit stuff bits. Table 2 depicts the packet breakdown by number of bits a full length packet .

As previously discussed the foundation protocol includes employment of the interface . The interfaces provide a relatively simple interface port for the applications to send and receive packets over the bus. The applications can interface with their respective nodes via byte wide input and output ports and a set of handshake lines. Two modes of operation can be available via this interface parallel and serial peripheral interface SPI modes.

The interface parallel mode can be employed for fast transfers and large block moves. This parallel mode of operation is sometimes referred to as high speed mode since it allows the application to load read an entire byte with only one toggle of the appropriate control lines. Hence the speed of data transfers is much faster than in SPI mode.

SPI mode can be used for interfacing microprocessors with the node or for applications that have pin restrictions since it requires fewer input output I O pins than the parallel mode. The tradeoff is that the transfer speeds in this mode may be slower than in parallel mode. SPI mode allows the applications to load read data from the bus serially one bit at a time hence only one pin is needed for the data input and one pin for the data output as opposed to eight pins in the parallel mode.

There are 254 addresses available for general use within the protocol. Two addresses can be set aside to support testing needs. The node logic is designed to prevent the applications from setting the node address to 0X00 or 0XFF. Handshaking can be disabled for the two reserved addresses.

Reserved address 0XFF can be used for blind broadcast to the bus monitor. This address allows for higher data transfer rates for ground mode instrumentation. It requires the use of the bus monitor for operation and provides a standard address for diagnostic dumps.

Reserved address 0X00 is used for global broadcasts. All nodes will listen for and receive packets sent to this address.

The interfaces include commands that are defined to indicate to the nodes what type of action to take. The node timing intervals are shown in Table 3 assuming that the nodes and applications are operating on 50 MHz clock s .

Write read and transfer buffers are utilized in transferring packets across the bus. A transfer buffer to node command is required in order to request the send process. This gives the receiving application the opportunity to abort the send process or preload data for a future send request use the node as the data buffer as data becomes available . Data bytes may be written to the node in an order as shown in . The parallel mode write TX buffer is represented in . The SPI mode write TX buffer is represented in .

A Transfer TX Buffer command causes the node to return the status of the transfer on Error Code 2 0 when an error state is detected see Table 6 . The parallel mode transfer TX buffer is represented in . The SPI mode transfer TX buffer is represented in . When the node indicates that a packet is ready the packet may be transferred. depicts the order that data bytes are sent out by the node on a read command. depict Read RX buffer command examples in parallel mode and SPI mode respectively.

Error codes are utilized during the read commands in order to indicate that an error has occurred in the process. depict examples of Read Error Code Commands for parallel mode and SPI mode respectively. Some of the interface signals have a dual use depending on what mode the Foundation bus is operating in. User0Active User Strobe User In 0 and User Out 1 are all used to drive the input output and SPI clock lines used in SPI mode. Table 4 shows the signals used in a dual function and the signals they represent. The SPI timing information is in Table 5.

The system includes a passive listener mode. A node may be placed in passive listener mode which causes the node to act like a combination of a node and an application even though the application has not been developed and allows testing of a node and application under development with virtual nodes applications. In this mode the node still loads and transmits packets according to the protocol. However the receive FIFO is bypassed in this mode and the data received by the node is streamed out to the top level for immediate access by the application e.g. a monitoring application . Each byte of data can be presented to the application along with a strobe indicating the byte is valid. It is up to the application to store or act upon the data immediately as it is not stored in the node and the output is overwritten by the next byte of data. The passive listener can take on an array of all the addresses in the system that it can mimic.

The data received by the node can be sent out to the application before error checking is completed so it is up to the tester to monitor the error lines and to handle the clearing of any data the application may have stored if an error is indicated. Additionally the application may indicate an array of addresses in PL node address array from which the listener node is to receive packets that comprise one of these addresses as its destination address. This is different from the normal mode of operation where the node only receives packets addressed to its own node address. This allows the application to be able to sniff packets being sent to any node on the bus.

The application may specify a select set of addresses or may set the PL all address input high indicating that packets addressed to any address will be received by the passive listener. This allows the tester to configure the node to act as a bus monitor that listens to all or to a select subset of all traffic that is sent over the bus. If PL all address is set high the passive listener will receive packets addressed to any address but it will only ACK to addresses contained in the PL node address array. In Passive Listener mode after a destination application busy error occurs the passive listener will output a byte of garbage data on the PL Data line. This byte should be ignored by the application and not considered as the first byte of a new packet.

The system can optionally include a 3 wire time interface provided for use on either interface data ports. The time port allows the application to generate a mirror synchronized copy of the nodes internal time stamp clock for time stamping acquired data in the built in monitoring functions. Table 7 shows exemplary names and functions of the 3 wire signals which can be used by an application to recreate the node time stamp according to . The serial time format is represented as . The top level of the node contains a 32 bit output port FB timestamp . This allows the application to be able to grab the timestamp directly without having to implement the logic shown in . This may be used if the application and the node reside in the same chip. If the application and node reside in separate chips then it likely will not be feasible to port all 32 lines across. Instead the 3 wire interface would be used.

A firewall interface is also provided. Objects from 0X7E00 to 0X7FFF are reserved for special functions UQS processing . The two blocks of specified objects are firewall protected to prevent node hardware that does not process UQS data from containing objects at the same addresses. This can prevent nodes that do not need to store UQS events from receiving any packets addressed to UQS objects. Packet processing stops as soon as the headers are decoded. The payload is never passed on to any internal storage element if the firewall is on.

The firewall can be two way. It can prevent a node from sending UQS objects or receiving UQS objects. When enabled Firewall 1 can block addresses from 0X7E00 to 0X7EFF and Firewall 2 can block objects from 0X7F00 to 0X7FFF. Having either enable line asserted for either of the firewalls will cause the associated firewall to be enabled. Having two enable lines for each firewall is a safety requirement to ensure that a single broken connection will not disable the firewall. While assertion of only one of the enable lines for each firewall will cause that firewall to be enabled both enable lines should be set low to provide the maximum amount of protection. When a receiving node detects that the packet it is receiving has a destination object address that is prohibited by its firewall settings it will stop listening to the bus and will not respond to back to the transmitting node no Header ACK will be sent .

The system includes a CRC Generator. An algorithm is used for calculating both the header and payload CRC is based on the CRC 16 CCITT algorithm. This algorithm uses the following generating polynomial 1 1 1 

The CRC implementation uses a seed value of 0XFFFF. All of the registers used in this implementation are designed to revert to a value of 1 when reset so the seed value is automatically contained in the registers upon reset. Next the CRC data are shifted into the registers a bit at a time Error Reference source not found. Once all the data have been shifted in the resulting value left in the registers will be the CRC.

The receiving node can perform a check on the received CRCs both header and payload to check whether any errors occurred in the packet . The check is performed by recalculating the CRC using the same algorithm as described for the transmitter CRC. The same seed 0XFFFF is loaded into the shift register implementation on reset. Next the data that the CRC will be based upon is shifted into the registers a bit at a time. Once the data have been shifted in then the transmitted CRC is also shifted in and the resulting value in the shift register checked against 0X0000. A resulting value of 0X0000 indicates that no errors occurred in the packet while a value other than 0X0000 indicates that an error did occur.

Referring now to a high level illustration of an exemplary computing device that can be used in accordance with the systems and methodologies disclosed herein is illustrated. For instance the computing device may be a device in the system . By way of another example the computing device can be or be included in the hub . The computing device includes at least one processor that executes instructions that are stored in a memory . The instructions may be for instance instructions for implementing functionality described as being carried out by one or more components discussed above or instructions for implementing one or more of the methods described above. The processor may access the memory by way of a system bus . In addition to storing executable instructions the memory may also store time stamps protocol instructions etc.

The computing device additionally includes a data store that is accessible by the processor by way of the system bus . The data store may include executable instructions time stamps etc. The computing device also includes an input interface that allows external devices to communicate with the computing device . For instance the input interface may be used to receive instructions from an external computer device from a user etc. The computing device also includes an output interface that interfaces the computing device with one or more external devices. For example the computing device may display text images etc. by way of the output interface .

Additionally while illustrated as a single system it is to be understood that the computing device may be a distributed system. Thus for instance several devices may be in communication by way of a network connection and may collectively perform tasks described as being performed by the computing device .

Various functions described herein can be implemented in hardware software or any combination thereof. If implemented in software the functions can be stored on or transmitted over as one or more instructions or code on a computer readable medium. Computer readable media includes computer readable storage media. A computer readable storage media can be any available storage media that can be accessed by a computer. By way of example and not limitation such computer readable storage media can comprise RAM ROM EEPROM CD ROM or other optical disk storage magnetic disk storage or other magnetic storage devices or any other medium that can be used to carry or store desired program code in the form of instructions or data structures and that can be accessed by a computer. Disk and disc as used herein include compact disc CD laser disc optical disc digital versatile disc DVD floppy disk and Blu ray disc BD where disks usually reproduce data magnetically and discs usually reproduce data optically with lasers. Further a propagated signal is not included within the scope of computer readable storage media. Computer readable media also includes communication media including any medium that facilitates transfer of a computer program from one place to another. A connection for instance can be a communication medium. For example if the software is transmitted from a website server or other remote source using a coaxial cable fiber optic cable twisted pair digital subscriber line DSL or wireless technologies such as infrared radio and microwave then the coaxial cable fiber optic cable twisted pair DSL or wireless technologies such as infrared radio and microwave are included in the definition of communication medium. Combinations of the above should also be included within the scope of computer readable media.

Alternatively or in addition the functionally described herein can be performed at least in part by one or more hardware logic components. For example and without limitation illustrative types of hardware logic components that can be used include Field programmable Gate Arrays FPGAs Program specific Integrated Circuits ASICs Program specific Standard Products ASSPs System on a chip systems SOCs Complex Programmable Logic Devices CPLDs etc.

What has been described above includes examples of one or more embodiments. It is of course not possible to describe every conceivable modification and alteration of the above devices or methodologies for purposes of describing the aforementioned aspects but one of ordinary skill in the art can recognize that many further modifications and permutations of various aspects are possible. Accordingly the described aspects are intended to embrace all such alterations modifications and variations that fall within the spirit and scope of the appended claims. Furthermore to the extent that the term includes is used in either the details description or the claims such term is intended to be inclusive in a manner similar to the term comprising as comprising is interpreted when employed as a transitional word in a claim.

B0002 Destination address 0X00 shall be reserved for global broadcasts which shall be received by all nodes attached to the system regardless of each nodes assigned address.

B0004 Broadcasts to 0XFF shall not be received by any node. Only the bus monitor and passive listener are allowed to receive packets from this address.

B0005 If an error is indicated by the node while the application is performing a node command the node shall continue to respond back to the application as appropriate i.e. Command Complete to prevent the application from getting stuck. If the application implements a bi direct on the User In and User Out ports in order to combine them into a bi direct bus using User OE to switch directions on the bi direct port and the node is being operated in parallel mode the application should take extra precautions to prevent contentions on the application lines. In the Read RX Buffer and Read Error Code commands the User In line should be tri stated as soon as User Strobe is de asserted following the command byte. This will ensure that User In is not still being driven when the node begins to drive the output on User Out.

B0006 The Write TX Buffer command shall indicate the beginning of loading a packet into the transmit buffer.

B0007 If the Write TX Buffer command is issued while the still TX Buffer still contains the data from a previous Write TX Buffer command then the TX Buffer FIFO pointers are reset and the new data overwrites the existing packet stored in the FIFO.

B0008 The Write TX Buffer command shall cause the node to return an error if User Active Slave Select is de asserted any time before the full amount of packet information has been written in or if the application attempts to write in extra payload bytes beyond what was specified by the packet length that was written in the header portion of the packet.

B0009 The Write TX Buffer command shall cause the node to return the status of the transfer on Error Code 2 0 as soon as an error state is detected.

B0010 The Transfer TX Buffer command shall cause the node to request the bus and transmit the packet upon gaining access to the bus.

B0011 The node shall make repeated requests for the bus for up to 10 ms and will then timeout if it has not successfully gained access and send an error code to the application see Table 6 .

B0012 The Transfer TX Buffer command shall cause the node to return the status of the transfer on Error Code 2 0 when an error state is detected see Table 6 .

B0013 In parallel mode the RX Buffer Ready line shall go low at the same time as the assertion of Command Complete for the last byte of data.

B0014 In SPI mode the RX Buffer Ready line shall go low during the reading of the second to last byte first CRC byte and is guaranteed to be low when the last byte is read out the application shall continue to read the current byte and then read one additional byte second CRC byte to correctly read all data from the receive FIFO.

B0015 In SPI mode the SDO data shall be valid on the rising edge of SCLK when reading bits from the node.

B0016 The Read RX Buffer command shall allow a packet to be read from the Foundation receiver buffer when RX Buffer Ready has indicated that an error free packet is ready for the application.

B0017 If the Read RX Buffer command is issued when RX Buffer Ready does not indicate a valid packet is available and the application attempts to strobe out data then a Command Complete will be issued by the node and an error code 110 or 111 will be indicated on the Error Code lines on the rising edge of Command Complete.

B0018 De asserting User Active Slave Select after sending the read command and before any data are read out shall cause the FIFO pointers for the receive buffer to be reset the RX Buffer Ready line to be de asserted and no error shall be reported.

B0019 De asserting User Active Slave Select after some but not all of the packet data have been read out shall cause the FIFO pointers for the receive buffer to be reset the RX Buffer Ready line to be de asserted and an error 111 to be reported on the error lines when User Active Slave Select is de asserted.

B0020 If the application continues a read command after RX Buffer Ready is de asserted by the node an error shall be indicated on the Error Code lines when the first extra byte is written in.

B0022 A logical value of 0 on this generic will cause the reset sent into the node to be synchronized with the clock while a value of 1 will bypass the synchronization register.

B0023 The application may select one of the following values for this generic to select the type of FIFOs memories specific to the platform being targeted ASIC SPARTAN3e SPARTAN6 VIRTEX5 VIRTEX4 PROASIC3e PROASIC3 FUSION IGLOO GENERIC TYPE .

B0024 When in passive listener mode this integer generic allows the application to select the number of node addresses that the application wants to have the passive listener listen to and handshake with.

B0028 A logical value of 0 on this generic will cause the User Active and User Strobe signals to be synchronized with the clock while a value of 1 will bypass the synchronization registers.

B0028a In any implementation of the Foundation Node SPI or parallel mode synchronizing registers must be used on User Active doubles as Slave Select in SPI mode and User Strobe doubles as SCLK in SPI mode . If Bypass Sync Reg is set to a value of 1 then the application must implement the sync registers at the top level.

B0029 This signal shall output a copy of the 50 MHz node clock allowing the application to be able to monitor the clock externally.

B0032 This bus shall indicate when the value on User Out is being driven. Each bit of User OE corresponds to the same bit of User Out.

B0033 This signal allows an external application interface application to tell the node when the application is powered up.

B0034 Any other signal with  en appended to the end shall be asserted when Power Detect n is asserted and shall be de asserted when Power Detect n is not asserted.

B0034a This signal provides the internal node timestamp which may be grabbed directly by the application.

B0034b This signal provides the current version of the node to the application for version tracking purposes. The upper 4 bits indicate the version number while the lower 4 bits indicate the version sub number i.e. X72 Version 7.2 .

B0035 The following inputs shall have a specific function pertaining to the Interface when in parallel mode User Active User Strobe User In 7 0 MSB LSB and Module Address 7 0 .

B0036 In parallel mode the User Active signal shall be asserted high to indicate that a command is being sent to the node.

B0037 In parallel mode once asserted the User Active signal shall stay asserted until the command has been completed.

B0038 In parallel mode once asserted if the User Active signal is de asserted before the command has been completed the node shall abort the command and return to the initial state regardless of any activity on the other interface inputs. Any partially read loaded or transmitted packet will be discarded by both the transmitting and receiving nodes when applicable and an error code shall be indicated if any of the error code conditions were violated.

Signal indicates when application is writing data to a node and when application is reading data from the node.

B0039 In parallel mode the User Strobe signal shall be asserted to indicate that the current byte transfer writing data or a command into the node or reading data out of the node has been started.

B0040 In parallel mode the User Strobe signal shall be de asserted in response to Command Complete asserting to indicate that the application has accepted a byte when the application is reading data from the node.

B0041 In parallel mode once the User Strobe signal has been asserted it should remain asserted until Command Complete asserts and shall then de assert.

B0042 When the User In signal has a valid value to be written to the node indicated by User Strobe being asserted by the application this signals value shall not change until the falling edge of Command Complete.

B0043 The value of the Module Address signal shall be stable for startup reset of the node and shall not be dynamically changed during node operation in specified applications.

B0044 The module address shall not be set with a value of 0X00 since this address is reserved to indicate a global broadcast to all nodes.

B0045 The module address shall not be set with a value of 0XFF since this address is reserved to indicate a broadcast to the bus monitor.

B0046 The following outputs shall have a specific function pertaining to the Interface when in parallel mode Command Complete and User Out 7 0 .

Signal indicates that node has accepted byte placed on User In when writing data to the node that value of User Out is valid when reading data from the node and that transmission of packet across the bus has been completed.

B0047 In parallel mode the Command Complete signal shall be asserted to indicated that a byte has been successfully written to the node by the application.

B0048 In parallel mode the Command Complete signal shall be asserted to indicate that a read byte is valid for the application to read.

B0050 Once asserted the Command Complete signal shall be de asserted only when one of the following conditions is met User Active has been de asserted. User Strobe has been de asserted. The node has been reset in hardware.

B0052 Once Command Complete has been asserted during a read from the node the User Out signal shall remain stable until the next falling edge of Command Complete.

B0053 The following inputs shall have a specific function pertaining to the User Interface when in SPI mode User Active Slave Select User Strobe SCLK and User In 0 SDI.

B0054 The Slave Select signal shall be asserted low to indicate to the SPI slave node that a transfer between the node and application via SPI is in progress.

B0055 The Slave Select signal shall stay asserted low during entire transfer even if the transfer is paused i.e. the SCLK is suspended.

B0057 In SPI mode the User Strobe signal must have signal integrity associated with a clock and must remain clean and glitch free.

B0058 In SPI mode if the User Strobe signal is stopped in the midst of a transfer the transfer must be paused.

B0059 In SPI mode the User Strobe signal shall have a maximum frequency of 6 MHz and a minimum frequency of 10 Hz.

B0061 When transmitting data the value on the User In 0 signal must be asserted by the SPI master on the falling edge of SCLK SDI is read on the rising edge of SCLK.

B0062 The following outputs shall have a specific function pertaining to the User Interface when in SPI mode Command Complete and User Out 1 SDO.

B0063 In SPI mode the Command Complete signal shall only be asserted high to indicate that the Transmit TX Buffer command has completed and the Error code indicates the completion status.

B0064 In SPI mode once asserted this signal shall not be de asserted until Slave Select has been set high ending the communication with the SPI slave node .

B0065 The SDO signal is presented on the falling edge of SCLK and is guaranteed stable for sampling by the application on the rising edge of SCLK.

B0066 The following input shall have the same function pertaining to the Interface in both parallel mode and SPI mode SPI En

B0069 The value of the SPI En signal shall be set upon startup reset of the node and shall not be dynamically changed during node operation.

B0070 The following outputs shall have the same function pertaining to the Interface in both parallel mode and SPI mode RX Buffer Ready and Error Code 2 0 .

Signal acts as a status line to indicate that an error free packet is ready for the application to read from the receive buffer.

B0071 The RX Buffer Ready signal shall be asserted when the bus node has an error free packet ready for the application.

B0072 Once asserted the RX Buffer Ready signal shall be de asserted if the application reads all the data from the receive buffer.

B0073 Once asserted the RX Buffer Ready signal shall be de asserted if the application ends a read command while there is still data in the receive buffer and the FIFO pointers shall be reset.

B0074 Once asserted the RX Buffer Ready signal shall be de asserted if the application resets the node by hardware reset.

Signal can provide an error code supplied by the node indicating either successful transfer or indicating what type of error occurred as presented in Table 6.

B0075 The Error Code signal shall indicate the status of the current bus transfer using the following codes 

B0077 The Error Code signal shall have a value of 001 if the receiving node does not acknowledge the header data during a transmit packet command.

B0078 The Error Code signal shall have a value of 010 if the node the packet being sent to destination node is busy when a0 transmit packet command is issued.

B0079 The Error Code signal shall have a value of 011 if the receiving node does not acknowledge the payload data during a transmit packet command.

B0080 The Error Code signal shall have a value of 100 if the watchdog timer reaches 10 ms 1 us starting from when the transmit command 0x01 was sent on assertion of User Strobe for command 0x01 and the transmitting node has not yet won arbitration likely due to a disconnected cable disabled hub port or too much traffic on the bus from higher priority applications .

B0081 The Error Code signal shall have a value of 101 if the transmit buffer is empty when a Transmit TX Buffer command is issued.

B0084 The Error Code signal shall have a value of 111 if either of the nuclear safety firewalls are enabled and a load packet command is issued with the packet containing an destination object address in the range of objects blocked by the active nuclear safety firewall. The error code will appear as soon as the node detects that the destination object address is in an enabled firewall range.

B0085 The Error Code signal shall have a value of 111 if the number of bytes loaded into the transmit FIFO does not match the packet length field.

B0086 The Error Code signal shall have a value of 111 if the application reads at least one byte from the node but terminates the command de asserts User Active Slave Select before all the data has been read from the receive FIFO.

B0087 The Error Code signal will have a value of either 111 or 110 if the application attempts to read from the receive FIFO once the FIFO is empty.

B0088 The following inputs shall be used at the Bus Interface RX Bus In LVDS CMOS RX Bus In and LVDS En.

Signal can allow the application to choose between enabling the LVDS ports as the outputs or bypassing the LVDS if desired.

B0092 The following outputs shall be used at the Bus Interface TX Bus Drive LVDS and CMOS TX Bus Drive.

B0094 The maximum delay associated with cables connectors allowed between any two nodes via a hub is TBD ns for flex and twisted pair cable.

In passive listener mode after a destination app busy error occurs passive listener will output a byte of garbage data on the PL Data Line. This byte should be ignored by the application and not considered as the first byte of a new packet.

B0095 When in passive listener mode all the interface commands shall operate as normal except for the Read RX Buffer command.

B0096 When in passive listener mode if the Read RX Buffer command 0x20 is issued the node shall show an error code of either 110 or 111 indicating an invalid command due to an empty RX FIFO.

B0097 The following inputs are used in passive listener mode PL en PL all address and PL node address array .

B0099 A logical value of one on the PL en bit shall cause the node to function in passive listener mode.

B0100 A logical value of zero on the PL all address bit shall cause the node to only receive packets whose destination address is in the PL node address array.

B0101 A logical value of one on the PL all address bit shall cause the node to receive all packets regardless of their destination node address.

B0102 If PL all address bit has a logical value of zero this array shall contain all the byte address values that the application wants the passive listener to receive packets from. If the PL all address bit has a logical value of one the passive listener will receive all packets but will only ACK to packets with a destination address in this array.

B0104 This bit shall strobe high for one clock cycle to indicate that the next byte output is valid on PL Data.

B0105a This byte output signal shall provide the full decoded packet bytes from any packet addressed to the module address of this node regardless of the value assigned to PL en. If Pl en is assigned a value of zero the packet will still be stored in the RX FIFO and will still need to be read or cleared by the application.

B0105 When PL en is assigned a logical value of zero operating as a normal node this byte output shall provide only the source address and destination address of packets that are not addressed to the module address of the node.

B0105b When PL en is assigned a logical value of one operating in passive listener mode this byte output shall always provide the source and destination address of any packet sent over the bus. Additionally if PL all address is high or PL all address is low but the destination address is contained in the PL node address array then the remaining packet bytes will also be sent out on PL Data following the source and destination address.

Optional. Provided for use of either interface data ports. Table 7 shows the name and function of the 3 wire signals which can be used by the application to recreate the node time stamp according to . Serial time format is represented in .

B0106 The following inputs shall be used at the Bus Interface Serial Time Clock Serial Time Data and Serial Time Sync

B0108 The time stamp data shall be clocked out on the Serial Time Data signal immediately following the falling edge of Serial Time Sync.

Signal is a square wave with a one second period. Falling edge of signal indicates that the current time is being transmitted to the application.

B0110 Each falling edge of the Serial Time Sync signal shall indicate the start of the current time stamp being clocked out on Serial Time Data.

B0111a Global broadcasted packets destination address of 0X00 and blind broadcast packets destination address of 0XFF with an destination object address in the range of either firewall 0X7E00 0X7EFF will be blocked regardless of the firewall settings and will generate an error when the packet is attempted to be loaded into the node.

When a receiving node detects that the packet it is receiving has a destination object address that is prohibited by its firewall settings it will stop listening to the Foundation bus and will not respond back to the transmitting node no Header Ack will be sent .

B0112 When the Firewall 1 En Pin 1 signal is asserted low then Firewall 1 shall be enabled and the node shall be blocked from transmitting or receiving any packets that contain an application object in the range 0X7E00 0X7EFF.

B0113 When the Firewall 1 En Pin 2 signal is asserted low then Firewall 1 shall be enabled and the node shall be blocked from transmitting or receiving any packets that contain an application object in the range 0X7E00 0X7EFF.

B0114 When the Firewall 2 En Pin 1 signal is asserted low then Firewall 2 shall be enabled and the node shall be blocked from transmitting or receiving any packets that contain an application object in the range 0X7F00 0X7FFF.

B0115 When the Firewall 2 En Pin 2 signal is asserted low then Firewall 2 shall be enabled and the node shall be blocked from transmitting or receiving any packets that contain a user object in the range 0X7F00 0X7FFF.

B0116 If an error occurs during a node command indicated by Error Code the transmit FIFO pointers shall be reset.

B0119 The generation of the header CRC shall not include the Start of Frame SOF bit in the header CRC calculation.

B0120 The generation of the header CRC shall start the header CRC calculation with the first bit of the source module field.

B0121 The generation of the header CRC shall pause after including the last bit of the source field module.

B0122 The generation of the header CRC shall not include the 3 bit re sync field in the header CRC calculation but will resume on the first bit of the destination module field.

B0123 The generation of the header CRC shall conclude the header CRC calculation with the last bit of the payload length field.

B0124 The generation of the payload CRC shall start the payload CRC calculation with the first bit of the payload field.

B0126 The bit stuffer shall search byte boundaries in the appropriate Foundation packet fields and insert a bit stuff bit of the opposite value of the bit that comes immediately before the stuff bit.

A bit stuff becomes part of the string and therefore its position in the stream is not stream data content dependent. The position of a stuff will always occupy the same position in the stream.

B0129 Bit stuffing shall stop after a bit has been inserted after the last bit of the header CRC and resume at the first bit of the payload field and then end after the last bit of the payload CRC field.

B0131a A node will only drive the bus dominant in an attempt to gain access to the bus if it has not already seen the bus driven dominant by another node. Once it has seen another node drive the bus dominant it will not attempt to gain access to the bus until it has seen the bus go idle again.

B0131 If two or more nodes each drive the bus dominant at close to the same time in an attempt to gain access to the bus and neither had yet seen the other drive the bus before making the decision request the bus i.e. multiple nodes requesting access to an idle bus at nearly the same time then the node with the lowest address must always win arbitration and gain access to the bus.

B0132 If a node loses arbitration its node arbiter must continue processing to determine if the winning node is addressing a packet to the node even if the transmitter is holding off until the bus is free.

B0133 If a node loses arbitration shall have a 10 ms 1 us window timed from the assertion of User Strobe on the command byte 0x01 to continue requesting the bus failure to gain access to the bus in this 10 ms 1 us window shall cause the node to generate an error on Error Code 2 0 See Table 6 .

B0134 During bit destuffing when byte boundaries occur the ninth bit shall have the opposite value of the previous bit seen in the stream indicating that it is a stuff bit. The ninth bit gets discarded by the receiver. Encoding and decoding is done so that the data to the CRC check never gets shifted in position as the receiver always knows the position of the stuff bits. This method of stuffing may also be referred to as fixed framing.

B0135 When the stuff bit position is detected and this bit is not the opposite value of the previous bit this detected bit stuff or frame error shall cause the Foundation receiver to destroy any temporary data and not acknowledge the packet.

Data that CRC is based upon is shifted into the registers a bit at a time. Once shifted the transmitted CRC is shifted in.

B0136 Both header and packet CRCs shall be calculated in an identical manner to the way the transmitter CRCs were calculated with the exception that the transmitted CRCs be included at the end of the calculation and the resulting CRC checked against 0X0000.

B0137 Any CRC result obtained by the receiver CRC check that is not equal to 0x0000 shall result in an error being indicated and the packet shall not be acknowledged by the receiver.

B0138 The following inputs shall be used at the Foundation Hub interface Hub In HUB NUM 1 0 and Hub Port En n HUB NUM 1 0 .

B0139 A logical value of one on any bit of the Hub Port En signal shall disable the corresponding hub port.

B0140 A logical value of zero on any bit of the Hub Port En signal shall enable the corresponding hub port.

B0143 If the hub detects that the input to a port has been driven dominant continuously for 2.17 us 0.05 us the hub shall disable the hub port.

B0144 If the hub detects a period of hub port activity toggling between dominant and recessive of 600.06 us 50.0 us without the port input being driven recessive for more than 2.17 us 0.05 us then the hub shall disable the hub port.

B0145 A port that has been disabled by the hub shall remain disabled until the hub port receive line has been driven recessive for at least 2.17 us 0.05 us . An additional delay is added on so that a total delay of 550.04 us 50 us from the start of the 2.17 us 0.05 us of recessive is seen. Once this delay is passed and if no hub kickoff conditions were met during this delay period the hub port shall be re enabled immediately if the hub has seen 2.17 us 0.05 us of idle on the bus or if another node is currently on the bus as soon as 2.17 us 0.05 us of idle is seen on the bus.

B0146 The maximum amount of sub hubs allowed to be connected in series is still to be determined TBD .

B0147 The maximum delay allowed through a sub hub connector port to connector port is still TBD in nanoseconds ns .

B0148 The application shall supply a clock with a parts per million accuracy PPM value in the range of 0 50 PPM.

B0150 The following outputs can provide internal debug information about the node their use is optional Report CRC Error Report Module not Addressed Report NS Safety Block Report Packet Accepted Report RX Data Report RX Data Valid Report RX Packet Active Report Abort RX Active Report App Busy Error Report Illegal Module Address Error and Report Stuff Error.

B0151 This line shall provide a single clock cycle pulse at the end of either CRC field if a CRC error is detected.

B0152 This line shall provide a single clock cycle pulse if the destination address of a packet being transmitted does not match the node address of the receiver.

B0153 This line shall provide a 2 clock cycle wide pulse after the header portion of the packet if the receiver determines that the packet should be blocked by the firewall.

B0154 This line shall provide a single clock cycle pulse when the receiver has determined that an error free packet has been received.

B0155 This line shall provide a single clock cycle pulse when the receiver has sampled a bit on its receive line.

B0156 This line shall indicate the value of the bit sampled when a pulse on the Report RX Data Valid line is seen. If using this report line sample on the falling edge of Report RX Data Valid. This line will report bits in all fields including ACK APP BUSY GUARD and EOF fields with the only exception being the SOF field.

B0157 This line shall go high on the 2rising edge of the node clock following the falling edge of the start of the Start of Frame field it shall remain high the 2rising edge of the node clock following the falling edge of the final Report RX Data Valid pulse.

B0158 This line shall go high one clock cycle after the rising edge of any report line that indicates an error in the packet being received it shall go low one clock cycle after the falling edge of Report Packet Active.

B0159 This line shall provide a single clock cycle pulse immediately after the acknowledge field if the receiver determines that part or all of a previous packet still resides in the receive FIFO.

B0160 This line shall be asserted and remain asserted for as long as the node has been assigned an illegal module address i.e. 0x00 or 0xFF .

B0161 This line shall be asserted 2 clock cycles after the occurrence of a bit stuff error or when operating in Passive Listener mode and the PL does not provide a header ACK because the destination address was not found in the PL node address array it shall remain asserted until 2 clock cycles after the de assertion of Report RX Packet Active whereupon it will then be de asserted.

Assertions pertaining to time have been stated with respect to a Clock50 signal being a 50 MHz clock signal. This specification of clock frequency is a suitable value for most intended applications but it is not a required value for operation of the Foundation Bus . For any other clock frequency value in MHz the assertions stated in this document will be true if 50 MHz is replaced everywhere by MHz and all stated time interval values are corrected to an actual time interval values by multiplication with the factor 50 .

