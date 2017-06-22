---

title: Secure end-to-end communication system
abstract: A secure end-to-end communication system is implemented via one or more security processing devices. In one embodiment, a method includes: loading, by a key manager, a first set of keys into a security device; encrypting first data with the first set of keys using the security device; and sending, over a network, the encrypted first data to an external site or a mobile device. The method may further include: requesting the encrypted data from the external site or mobile device; receiving, over the network, the encrypted first data; and decrypting the received encrypted first data with the first set of keys using the security device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09374344&OS=09374344&RS=09374344
owner: SECTURION SYSTEMS, INC.
number: 09374344
owner_city: Clearfield
owner_country: US
publication_date: 20140319
---
This application claims priority to U.S. Provisional Application Ser. No. 61 806 757 filed Mar. 29 2013 entitled SECURE END TO END COMMUNICATION LINK SYSTEM WITHOUT TRADITIONAL VPN IPSEC by Richard J. Takahashi the entire contents of which application is incorporated by reference as if fully set forth herein.

This application is related to U.S. Non Provisional application Ser. No. 14 208 337 filed Mar. 13 2014 entitled MULTI TENANCY ARCHITECTURE by Richard J. Takahashi the entire contents of which application is incorporated by reference as if fully set forth herein.

This application is related to U.S. Non Provisional application Ser. No. 14 198 097 filed Mar. 5 2014 entitled MULTI LEVEL INDEPENDENT SECURITY ARCHITECTURE by Richard J. Takahashi the entire contents of which application is incorporated by reference as if fully set forth herein.

This application is related to U.S. Non Provisional application Ser. No. 14 177 392 filed Feb. 11 2014 entitled SECURITY DEVICE WITH PROGRAMMABLE SYSTOLIC MATRIX CRYPTOGRAPHIC MODULE AND PROGRAMMABLE INPUT OUTPUT INTERFACE by Richard J. Takahashi the entire contents of which application is incorporated by reference as if fully set forth herein.

At least some embodiments disclosed herein relate to security processing and secure communication in general and more particularly but not limited to a secure end to end communication system using security processing.

The virtual private network VPN of today requires an IPsec transaction to set up the keys and the encryption link. Once established the VPN and the IP addresses are fixed. VPN technology is over 25 years old with many limitations as applied to the dynamic mobile world. In today s network consisting of multiple variant cellular mobile networks e.g. 2G 3G 4G etc. mixed with older PTSN and POTS networks VPN technology is costly to support and has serious drawbacks and cannot maintain a VPN connection e.g. if the end user is moving using mobile devices e.g. laptops smartphones tablets etc. .

Typically the mobile 3 4G network data channel changes on and off as the mobile network allocates bandwidth to thousands of other users on the network. As a result the IPsec connection will break and need to be re established. Service providers are charging premium rates for VPN usage because it requires a fixed IP address and fixed data channel and bandwidth.

Systems and methods to provide a secure end to end communication system with security processing of data e.g. encryption and decryption of data packets using one or more security devices are described herein. Some embodiments are summarized in this section.

In one embodiment a method includes loading by a key manager a first set of keys into a security device encrypting first data with the first set of keys using the security device and sending over a network the encrypted first data to an external site or a mobile device. The method may further include requesting the encrypted data from the external site or mobile device receiving over the network the encrypted first data and decrypting the received encrypted first data with the first set of keys using the security device.

In one embodiment a method includes loading by a first key manager a first set of keys into a first security device decrypting by the first security device using the first set of keys first data obtained from a data storage encrypting by a second security device the first data using a second set of keys and sending the encrypted first data over a network.

In one embodiment a system includes a security device coupled to receive first data from an internal network the security device configured to encrypt the first data with a first set of keys and to provide the encrypted first data for sending e.g. via transport network equipment over a network to a mobile device e.g. a mobile phone tablet or portable computer or an external site e.g. a data storage center or common encrypted data storage and a first key manager configured to load the first set of keys into the security device. The user e.g. a manufacturing or services company or a customer of a data storage center or other cloud service of the security device may control the first key manager for example remotely by sending commands over the Internet or another internal or external network.

In one embodiment a system includes a security device configured for cryptographic processing coupled to receive incoming data from a plurality of data sources e.g. data from different companies or other different customers or users wherein the incoming data includes first data from a first data source a controller e.g. a key manager configured to select a first set of keys from a plurality of key sets each of the key sets corresponding to one of the plurality of data sources wherein the first set of keys is used by the security device to encrypt the first data and a common encrypted data storage coupled to receive the encrypted first data from the security device.

In one embodiment a system includes a plurality of security devices each configured for cryptographic processing coupled to receive incoming data from at least one data source and a plurality of key managers each key manager associated with a user each key manager coupled to a respective one of the security devices and each key manager configured to provide a set of keys to the security device for encryption of incoming data associated with the respective user wherein the incoming data is to be stored in a common encrypted data storage after the encryption.

In one embodiment a security device includes a plurality of cryptographic cores e.g. a core configured using a systolic array including an input core configured to perform encryption for a first data packet at least one key cache storing a plurality of key sets wherein a first set of keys is selected from the plurality of key sets to encrypt the first data packet by the input core and a packet input engine configured to detect a header of the first data packet and to address the first set of keys. In one embodiment the keys are initially provided to the security device by an external key manager through an application programming interface.

The disclosure includes methods and apparatuses which perform the above. Other features will be apparent from the accompanying drawings and from the detailed description which follows.

The following description and drawings are illustrative and are not to be construed as limiting. Numerous specific details are described to provide a thorough understanding. However in certain instances well known or conventional details are not described in order to avoid obscuring the description. References to one or an embodiment in the present disclosure are not necessarily references to the same embodiment and such references mean at least one.

Reference in this specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the disclosure. The appearances of the phrase in one embodiment in various places in the specification are not necessarily all referring to the same embodiment nor are separate or alternative embodiments mutually exclusive of other embodiments. Moreover various features are described which may be exhibited by some embodiments and not by others. Similarly various requirements are described which may be requirements for some embodiments but not other embodiments.

Programmable input output interface is coupled to the interchangeable physical interface and is configured to route each of the plurality of incoming packets to one of the cryptographic modules for encryption to provide a plurality of encrypted packets. The programmable input output interface is configured to route the encrypted packets to a common internal or external data storage.

For outgoing packets programmable input output interface routes encrypted packets to one of the cryptographic modules for decryption. The decrypted packets are then routed by programmable input output interface to the data source.

In one embodiment programmable input output interface is programmable to support different interface protocols and each of the plurality of cryptographic modules is programmable to support different encryption protocols e.g. each module may be programmed to support a different protocol . Programmable input output interface may include one or more field programmable gate arrays that are programmable to support the different interface protocols. In one embodiment programmable input output interface may be coupled to the cryptographic modules by a high speed bus such as for example a PCI e bus.

In one embodiment the interchangeable physical interface is configurable to support two different physical interfaces. In one example the interchangeable physical interface comprises a replaceable physical input output panel or card that can be replaced independently of the programmable input output interface and the plurality of cryptographic modules .

Control and display unit provides drivers to a display and status control screen on the user panel . User panel also provides soft or hard buttons for user control and data input during the operation of security device . Various functions controllable on user panel include a zeroize control to zeroize the keys a crypto ignition key to start the encryption process a key fill port to load the keys and a system reset.

In one embodiment security device which may be e.g. implemented as a security appliance is used to prevent data breaches by a hacker trying to gain access to encrypted data. In this embodiment security device provides security encryption high assurance high availability sustained bandwidths up to 400 Gbs full duplex programmability for data at rest and in network applications. The security device has an interchangeable I O flexible module as described above to support different physical PHY interface connectors and electronics.

In one embodiment use of the interchangeable I O interface and programmable I O interface implemented using an FPGA I O systolic array provides the following advantages 

In one embodiment flexible I Os and flexible cryptographic sometimes simply referred to as crypto herein modules are accomplished by using a scalable systolic architecture and crypto modules and interchangeable input output I O card as described herein. The security device has programmable delay latencies for a specified data block size of programmable bytes sizes. The security device architecture has two programmable elements the programmable crypto module and the programmable flexible I O.

In one embodiment the flexible I O has two components The FPGAs can be programmed to support different interface protocols and an interchangeable physical I O card is used to support the physical interfaces and connectors. The flexible I O also has a switching network. The scalable and programmable crypto module has a programmable full duplex bandwidth consisting of high performance CPUs and FPGAs clocking up to maximum allowable clock rates internal to the FPGA. This CPU and FPGA in systolic matrix configuration and implementation provides a fully programmable system to meet many different applications.

In one embodiment the security device crypto module design will be using high performance CPU or equivalent processors and FPGAs forming a programmable systolic scalable module. The programmability efficiencies of design are realized by segmenting functional subsystems from packet engines crypto engines key handler and overhead control management engines. The I O interface incorporates functional blocks e.g. 100 Gbs Ethernet PCI express Fibre channel SAS Infiniband SCSI or any other high speed interface protocols that are incorporated.

In one embodiment the security device can be both a media level encryptor and a file system encryptor. All data payload passing thru security device is encrypted except for the file system headers commands which remain in the clear . Therefore the existing file system will be intact with no drivers required for the end system. The only interface required is for the end system remote management and key management products. This makes the security device transparent to a user or network storage system.

Processor handles control plane and data processing for the cryptographic modules and the high speed input output interfaces . In one embodiment processor is a control plane processor configured to control systolic data flow for the cryptographic modules and also to control loading of keys from an external key manager to an internal key cache see e.g. below .

Physical interface receives a plurality of incoming packets from data source . The first programmable high speed input output interface routes each of the plurality of incoming packets to one of the cryptographic modules for encryption processing to provide encrypted packets. The second programmable high speed programmable input output interface routes the encrypted packets from the cryptographic module to common encrypted data storage via physical interface .

In one embodiment the routing and switching functions of high speed interfaces and are provided by programmable input output interface of . In one embodiment interchangeable physical input output interface includes physical interface and or .

In one embodiment each of the encrypted packets has a respective tag to identify an original entry port e.g. a port of high speed I O interface keys or key addresses associated with each of the encrypted packets is decrypted by one of the cryptographic modules to provide corresponding decrypted packets and the first programmable input output interface is further configured to use the respective tag to route each decrypted packet back to its original entry port.

In one embodiment each programmable input output interface is programmable to support different interface protocols. For example the first programmable input output interface may include a plurality of field programmable gate arrays that are programmable to support the different interface protocols.

In one embodiment the first programmable input output interface and the second programmable input output interface each comprise a switching network and a router not shown to route incoming packets from data source or data storage respectively to one of the cryptographic modules .

In one embodiment each cryptographic module is designed and programmed and mathematically optimized for any cryptographic algorithms and network IP protocols. The design can be scaled up to for example six or more crypto modules. The security device can be mathematically optimized for example for any cryptographic algorithms for full duplex data rate performance.

In one embodiment the security device architecture is adaptable to any enterprise class data at rest or IP network solution due to the flexible switching I O architecture. The flexible input and output switching I O interfaces provide a significant cost advantage and homogeneous data flow and relax the need for data separation. The security device may use FPGAs that bridge to the native I O interface for the required number of crypto modules. This allows a single crypto module to be used with many possible system implementations and configurations based on the end application I O type and throughput requirements and also be scalable with programmable data rate increments.

In one embodiment the flexible switch I O architecture described herein includes programmable I O modules using FPGAs that function as a low latency bridge and switch between the native I O to the target data at rest system and to the internal array of crypto module processors. A pair of separated designated programmable FPGA based I O interface modules bridges security device to an industry standard network. This scalability and flexibility enables security device to be inserted into existing or new storage network systems supporting scalable data rates.

In one embodiment the flexible programmable I O interface is adaptable to any enterprise or mobile class data at rest interface application. The flexible I O architecture includes programmable I O modules using FPGAs that function as a low latency bridge between the native I O of the target data at rest system and the internal array of crypto modules. Flexible I O programmability is based on FPGA based modules that can be programmed to any industry standards or a custom interface to the storage system fabric or IP network.

In one embodiment security device performs at data rates only limited by the technology used. The key handling agility is matched to the data rates. The internal key management is central to the performance of the cryptographic module in this embodiment.

In one embodiment the programmable packet input engine the programmable cryptographic engine and the programmable packet output engine are each configured as a systolic matrix array and each include one or more field programmable gate arrays FPGAs programmable to support different security protocols. In one example the programmable packet input engine the programmable cryptographic engine and the programmable packet output engine are each coupled to a respective dedicated program memory for each FPGA e.g. memory or and to a respective dedicated processor not shown to control programming of each FPGA. Each memory may be used e.g. to provide data keys buffering and or storage.

In a method according to one embodiment the first programmable input output interface see includes a field programmable gate array FPGA and the method includes programming the FPGA to support a different interface protocol than previously used for receiving incoming data packets. In this method each of the plurality of cryptographic modules includes programmable systolic packet input engine programmable systolic matrix cryptographic engine and programmable systolic matrix packet output engine . The method further includes programming an FPGA of the packet input engine an FPGA of the cryptographic engine and an FPGA of the packet output engine .

In one embodiment a top systolic layer includes FPGAs and which are coupled to systolic packet engines and cryptographic engine each also including an FPGA in order to form a two dimensional systolic matrix array for data and control processing.

In one embodiment each crypto module has input and output packet engines and the crypto core. The crypto module has a systolic crypto engine that is tightly coupled to the input and output systolic packet engines. Each element in the crypto module has a dedicated high performance CPU plus its memory and dedicated memory to the input output systolic packet engines and crypto core buffer storage memory.

In one embodiment each FPGA s array has a dedicated program memory. Also a compression engine included e.g. in auxiliary engines is included for data compression or other data processing required.

In one embodiment the crypto module of uses secure boot to verify the FPGA code and that any software SW within the crypto module is encrypted secure and authenticated. During the secure boot process if any anomalies are detected the system will not boot and further may provide a user alert that issues have been detected. The secure boot may be designed to work with existing industry key manager systems.

In one embodiment the crypto module design of provides features such as hard wired one time programmable options and custom analog digital circuits for flexible physical partitioning for un encrypted plain text and encrypted cipher text separation.

In one embodiment each cryptographic module is implemented using a systolic matrix array configuration. For example cryptographic module as illustrated in is configured in a systolic matrix array such as the basic form illustrated in . In addition in one embodiment the input and output packet engines and or the cryptographic processing engine for each cryptographic module are also each themselves designed with an internal systolic matrix array architecture. For example the cryptographic processing engine may be configured in a systolic matrix array configuration such as illustrated in . In another example each packet engine may itself have the systolic array configuration of or or yet other systolic array configurations as part of its internal sub block processing architecture.

Thus as described above in some embodiments security device is configured with a two or greater multiple layer systolic matrix array architecture. In this architecture each cryptographic module has a systolic matrix array configuration i.e. a top systolic array layer and each of the packet engines and or cryptographic processing engine has an internal systolic matrix array configuration e.g. in a lower systolic array layer formed of FPGAs that is logically underneath the top systolic matrix array layer . The multiple layers above combined with two dimensional systolic arrays provides a three dimensional systolic matrix architecture for security device .

In one embodiment each of the incoming packets to a cryptographic module includes a key tag to identify at least one key associated with the packet to be security processed and further may also include a source tag to identify a data source and keys for the packet. The internal key manager is configured to retrieve the keys from one of key caches using the key tag for the packet to be processed by the respective cryptographic module .

In one embodiment programmable input output interface and or is further configured to route a packet to one of the plurality of cryptographic modules based on the source tag.

In one embodiment each of the plurality of cryptographic modules may be physically partitioned from the other of the cryptographic modules. In one embodiment other key features of security device may include the ability to interface or port third party key management software and network management software.

Various additional non limiting embodiments of security device are now described below. In one or more embodiments security device may provide one or more of the following advantages 

1. A fast data rate encryptor at hundreds of gigabits full duplex e.g. for meeting future optical network data rates .

2. A programmable systolic architecture consisting of FPGAs and CPUs. The security device is flexible and programmable requiring only software upgrades for different versions and features.

3. Multi tenancy to secure an entity s or individual user s data. Each entity user s data will be encrypted decrypted using a unique key per the entity user. In this way each entity user s data will be uniquely encrypted decrypted and stored in a common data storage area. If by operator or machine error the wrong data is accessed and mistakenly sent to another of the entity users using the storage area the data is still safe since it will not be decrypted by the correct entity user key. Various embodiments for a multi tenancy architecture are discussed below in the section titled Multi Tenancy Architecture .

4. A multi level security architecture to secure different levels of classified data using a single security device e.g. an encryptor . Each classification of data will be encrypted decrypted using a unique key per the data class. In this way each classification of data will be uniquely encrypted decrypted and stored in a common storage area. If by operator or machine error the wrong data is accessed and mistakenly sent to another level of classification the data is still safe since it is not decrypted by the correct user key.

6. A flexible high density I O to interface to network equipment at multiple customer or other source sites. Also the flexible I O can be programmed for mixed interface types e.g. 10 Gbs Ethernet Infiniband or PCI express thus requiring no interface bridging network equipment.

7. A replaceable flexible I O physical panel that can be customized for a specific network installation without the need to re design the main chassis of security device .

Specifically un encrypted or plain text data e.g. incoming data packets enters physical interface and is routed by programmable input interface to packet input engine . Data packets are routed by input engine to an appropriate cryptographic core in cryptographic processing engine .

A security association SA key lookup is used in packet engine or to determine appropriate keys for loading from a key memories array to cryptographic engine via a key manager interface or as defined in the packet header. These keys are used for security processing of the corresponding data packet.

After encryption by processing engine encrypted packets are provided to packet output engine for routing to programmable output interface . The encrypted data leaves via physical interface .

Programmable interfaces and may be formed using FPGAs or other programmable devices e.g. as described above for I O interfaces or of . In one embodiment physical interfaces and may form a part of interchangeable physical input output interface . In one embodiment physical interface is implemented as a removable physical card.

In one embodiment FPGAs and form a portion of the systolic matrix array configuration illustrated in and may be coupled to the packet input and output engines and cryptographic processing engine using serial buses. The packet input and output engines and cryptographic engine are formed using FPGAs to provide a two dimensional systolic array of a top systolic layer. In one example data and control processing is performed in two dimensions using the six FPGA units e.g. FPGA and packet input engine as illustrated in .

In one embodiment the sub blocks in the packet input engine or packet output engine such as packet routing packet multiplexer and IP context lookup are implemented in a systolic matrix array configuration as was discussed above. Data comes into the packet engine and the packet engine looks at the packets including the context and decides where to route each packet. Then the packet engine determines that a packet requires a particular security association which is implemented using a key lookup. The packet engine associates the key to the incoming data. The key is read out and the data is encrypted or decrypted in one of the crypto cores.

In one embodiment high speed memory is coupled to the input and output packet engines and may be any type of high speed memory in various embodiments.

In one embodiment all primary processing works in a matrix. Data is constantly flowing in two dimensions. For example data is flowing horizontally keys are flowing up vertically and control information is flowing down vertically as part of the two dimensional processing.

Additional variations details and examples for various non limiting embodiments of the above security processing system are now discussed below. In a first variation with reference to the programmable input output interface is a router switch that selects one of the crypto modules to receive forwarded packets. A router and switch are incorporated inside the input output interface . For example if a first packet comes through a second port the first packet will be routed to crypto module number six. Crypto module number six will later route the first packet back out through that same second port of original entry.

There may be two components to the programmable I O interface. On one side the interface programs the type of I O that is desired. The other side of the interface is the router switch. The router switch multiplexer knows which crypto module is to receive a given packet. Also the router switch knows which crypto module is ready for processing of a packet. For example if crypto module number one is ready for processing it will flag itself as being ready for processing. For example there is a semaphore flag or packet header bits used that tells I O interface which module is ready to process data. Whatever port is used to bring in the data that data will be processed in one of the crypto modules and then tagged out back to the same port when later being decrypted and sent out from storage e.g. the packet is tagged with some identification of the port using a tag . The tag is used to redirect the packet back to the correct port of original entry.

The crypto module has a security association that determines which keys go with which packet. The programmable input output may allow programming of different applications because of the use of FPGAs. The back end of the router switch will accommodate the type of input output to be used. The router switch will identify the crypto module to be used. When reprogramming the programmable interface a new physical interface needs to be interchanged or installed. The main security device chassis is not changed out only the I O portion is being changed.

In one embodiment remote ports are basically control ports. The protocol for the remote port may typically be a Simple Network Management Protocol SNMP protocol or any other management protocols The key fill port is where the keys are filled into the security device. The crypto ignition key ignites the security device.

With reference to the Interbus serial bus mentioned above coordinates the operation of the two input output interfaces . The Interbus handles any protocol issues between the router and the switch functions of these interfaces. The Interbus is used to provide communication between the FPGAs of the systolic array during operation of the security device. In one example the Interbus helps to coordinate operation as to which crypto module will receive an incoming packet.

Processor manages control plane operation. Processor also configures components when a new security protocol will be used uses routing tables sets the configuration sets up the programmability and sets up the power on self test. Processor also may facilitate key loading. The key fill port on the front of user panel operates under control by processor .

With reference to a secure boot is used to guarantee that the data booted into the FPGAs of the cryptographic module is proper. The secure boot is executed when the unit is turned on or at boot up. The code is authenticated by the system. The FPGAs are programmed at every boot up of the unit or any time that the unit is reset. Each crypto module may have its own CPU which controls programming.

With reference to external key management is a location that the keys may be stored for passing to the security device . A network operator loads the keys into the external key management . The security device loads the keys into the crypto modules. There is key tagging in the packet headers and inside the crypto module. When a packet comes into the security device the packet is associated with a given key and the packet contains information used to route the packet. The external key management can load keys in real time or only a single time. Network services management is remote management which provides control status setting up of the security device unit and sending of the status back to a user. The other external management services could be used to track how many other units are in the field what the units are doing whether each unit is running and what configuration the unit is in.

In one embodiment data packets include key tags customer tags and packet tags. The packet tag tells what type of packet is coming in. The customer tag identifies the company or source of the data. The key tag tells what key goes with what packet. Each tag is looked at by the packet engine to determine how the packet is going to be routed within the crypto module .

Now discussing an embodiment regarding flexible physical partitioning each cryptographic module may be physically isolated by design. So only a certain packet will go through a module number one and only certain other packets will go through module number two. For example crypto module number one may only process a certain style of packet. Crypto module number two may only process packets for a particular customer. Thus it is physically partitioned. For example customer number one s data is tagged as belonging to customer number one for sending it to the specific crypto module. The router determines this requirement and only that particular crypto module can process that customer s packet.

Regarding internal key management in the crypto module s performance the key manager loads the keys and further decides how the keys are dispersed within the crypto module based on the tagging of the incoming data packet. Keys are stored in the selectable key cache . The key manager decides based on the tagging of the data packet what keys will be associated with the current packet. This provides key agility.

With reference to API may be programmed to map into any of several different external key managers . The use of API thus provides increased flexibility.

A controller not shown is configured to select a first set of keys from a plurality of key sets . Each of the key sets corresponds to one of the plurality of data sources . The first set of keys e.g. Key Set is used by the security device to encrypt the first data. Common encrypted data storage receives the encrypted first data from security device .

The controller may be for example a key manager as discussed further below. In one embodiment the security device includes the controller. In one embodiment the controller is an internal key manager e.g. as discussed above for and internal key manager .

In one embodiment the first data is a first data packet and security device is configured to detect a tag of the first data packet that identifies the first data source e.g. Source . The controller selects the first set of keys Key Set based on the detection of the tag.

Each of the plurality of data sources is typically located at a different physical location for a respective user e.g. an entity such as a company or individual using the common encrypted data storage to store data sent over a network e.g. the Internet or another communication link to the security device .

Each of the security devices is configured for cryptographic processing and receives incoming data from at least one data source . Each of the key managers is associated with a user e.g. corporation or an individual . For example a given user may control an external key manager that provides keys to one of the security devices for cryptographic processing of that user s data. A switch receives the incoming data from data source and routes the incoming data to one of the security devices. For example switch may route the data to the security device that corresponds to the user that sent the data for storage.

Each key manager is coupled to a respective one of the security devices and each key manager is configured to provide a set of keys to a particular security device for encryption of incoming data associated with the respective user. The incoming data is then stored in common encrypted data storage after the encryption.

Switch is used to route the encrypted data from the security device to encrypted data storage . When data is read from common encrypted data storage switch routes the data to the appropriate security device for decryption processing.

In one embodiment security devices include a first security device Security Device . The key managers include a first key manager Key Manager . The first security device comprises a key cache not shown configured to store a first set of keys e.g. Key Set as shown in that are received from the first key manager. The first set of keys is loaded into a cryptographic core not shown of the first security device and then used to encrypt data packets in the incoming data.

In security device is shown located at a physical location or site of the first user. In other embodiments security device may be located at the physical location of common encrypted data storage . In these other embodiments key manager may still remain at physical location under the control of the first user.

Input key cache and output key cache each store a plurality of key sets. A first set of keys is selected from the key sets stored in key cache to encrypt a first data packet by the input core . Packet input engine is configured to detect a header of the first data packet and to address the first set of keys. In one embodiment the cryptographic module includes a processor not shown configured to verify that the packet input engine is authorized to address the first set of keys.

The cryptographic module includes a key loader controller to load keys for example from an external key manager via an application programming interface. The key loader controller loads the first set of keys for storage in key cache prior to receipt of the first data packet by the cryptographic module. In one embodiment key cache and key cache are each configured so that a key cache failure causes the respective key cache to be zeroized.

Stored keys are loaded into the appropriate cryptographic core or from key cache or . The packet input engine provides a signal e.g. an addressing signal used by input key cache to select the first set of keys for use by the cryptographic core in encrypting incoming data packets. Packet output engine addresses keys in key cache in a similar way for decrypting outgoing packets.

Packet output engine provides encrypted data packets from the input core when writing data to common encrypted data storage . Packet output engine detects a header of each data packet when reading from the common encrypted data storage in order to address a set of keys in output key cache for decrypting each data packet by output core . Output core provides the decrypted data packets to packet input engine which sends the data packets to one of data sources of .

In one embodiment input key cache stores a set of keys for encryption and output key cache stores a set of keys for decryption. The cryptographic module is configured to zeroize input core the input key cache and key loader controller after encrypting the first data packet. Output core output key cache and key loader controller are zeroized after decrypting data packets read from common encrypted data storage .

In one embodiment as described in more detail below a secure multi tenancy system is provided to encrypt a customer s data to minimize or avoid situations where data is mistakenly read by another customer. The system reduces the risk of unauthorized access to a customer s data.

The packet input engine performs header detections or modifications and will authenticate and associate the customer s data. Once the data is authenticated and identified packet input engine will address the unique specific customer s key in input key cache . The input key cache stores this customer s specific keys. The input key cache also has a fail safe and key authentication processor not shown to verify the packet input engine is authorized to address the keys within the input key cache.

Key loader controller loads and verifies keys and addresses from the packet input engine . A fail safe feature of the input key cache and key loader controller is that any key cache failure will result in a zeroized key cache. The key loader controller and the respective input or output key cache is designed to ensure the proper key is associated with the data that will be encrypted or decrypted. The key controller and each key cache is designed to be fail safe in that if there is any failure in the key controller or one of the key caches the cryptographic module will fail to a known state and the data will not be compromised.

Each of the key caches is designed to store for example one or more millions of keys. In one embodiment each key cache writes keys one way to its respective cryptographic core i.e. input core or output core .

Packet output engine performs header detections or modifications and authenticates and associates the customer s data read from common encrypted data storage . Once the data is authenticated and identified packet output engine addresses output key cache . The output key cache operates similarly to the input key cache discussed above.

Each cryptographic core is an encryption decryption engine to encrypt or decrypt the data from the packet input output I O engines discussed above. The keys are loaded from the respective key caches as was discussed above.

In some embodiments the multi tenancy architecture detects the packet header and associates the keys that will be encrypted decrypted. There is an option provided for the keys in the key cache to be encrypted using a key encryption key or to be un encrypted. The multi tenancy architecture is configured to provide selected encrypted data into common storage area e.g. for data storage or for internal network processing and use . In one embodiment the multi tenancy architecture authenticates the I O packet engines to the associated encryption and decryption keys within the respective input or output key cache for simultaneous two way data traffic. The system requires that data be encrypted with a set of keys associated to a specific customer s data.

The multi tenancy architecture may have fail safe features to ensure in cases of failure that the multi tenancy architecture will fail to a safe state. Each key cache may be coupled to a fail safe key loader controller to authenticate the packet engines and send the correct key addresses. The key cache may be fail safe with authentication. The cryptographic core may use fail safe features and key agility to process keys from the respective key cache and data from the input output packet engine.

Additional variations details and examples for various non limiting embodiments of the multi tenancy architecture system are now discussed below. In a first variation data is coming in from many different customers. Data is stored in one large database and in an encrypted form. For example a first company s key and a second company s key are each loaded into the multi tenancy system. The first company s key is selected for processing the first company s data.

In another variation no entity but the customer is able to see the keys of the customer. The customer controls the keys by interacting with the key manager discussed above. The customer s keys cannot be lost by a data storage center operator and cannot be used by another company.

In one example each customer owns its own security device unit and controls and manages its own key manager. The other equipment of the data storage center can be commonly owned and operated by the data storage center operator. Each customer s security device unit is installed at the data storage center or at the customer s physical location.

In one variation the internal control plane key bus as illustrated in provides user or operational keys into key loader controller . The front panel key load as illustrated in is used to load keys from a key loader into the key loader controller .

In various embodiments below different architectures of a secure communication system are described. Specifically there are four illustrated embodiments for securing data to and from the data source to the end user without the need for VPN IPSec .

In each architecture illustrated below the data to be accessed may be stored in an encrypted form for example in a data center or corporate data storage facility. This provides two levels of protection the data stored in the data corporate center is encrypted protected from unauthorized access. When the data is sent over the Internet or other network the data is still encrypted but does not require any special set up. For example encrypted data packets may be sent without modification to the network packets or packet headers.

In one embodiment a traditional VPN virtual private network is replaced using an end to end encryption from the data storage to the end user without the need to install costly VPN equipment and without requiring any network modifications. In addition there is no overhead or complexity of establishing an IPSEC tunnel which can have the problems of maintaining an IPsec connection over various IP mobile networks. In other words this embodiment is based on a secure encrypted end to end system without the need to set up a VPN tunnel or IPsec. Thus this embodiment can avoid the need for today s VPN technology in many specific applications.

In some embodiments the secure communication system described below may be implemented in a multi tenancy architecture as described above. In other embodiments the security devices e.g. security device of and related systems and methods discussed above may be used when implementing the secure communication system.

In one embodiment the key manager is an external key manager e.g. external key manager of above and is further configured to select the first set of keys from a plurality of key sets e.g. stored in a key cache and to provide the first set of keys to the security device via an application programming interface e.g. API of .

In one embodiment the security device subsequently receives over the network the encrypted first data from the mobile device or external site . The received data is decrypted by security device using the first set of keys.

In one embodiment the security device is a first security device and the mobile device or external site includes a second security device not shown configured to receive over the network the encrypted data and to decrypt the received data with the first set of keys e.g. the first set of keys may be loaded into the second security device prior to receiving the encrypted data from company site .

In one embodiment a method includes loading by key manager a first set of keys into security device encrypting first data with the first set of keys using the security device and sending over network the encrypted first data to external site or to mobile device . In one embodiment the method further includes requesting the encrypted data from the external site or mobile device receiving over the network the encrypted first data and decrypting the received encrypted first data with the first set of keys using the security device. For example the external site may be a data center a storage site or a computing site.

In one embodiment a customer e.g. the operator of the company site or other user is using external data center or corporate storage site to store its data. The customer encrypts the data e.g. using a security device such as a network encryptor and sends the data over the Internet or other open network to the external data center or corporate storage site. The external data center or corporate storage site then stores the data in an encrypted form.

In one embodiment the external data center or corporate storage site processes the data per its normal protocols. The network encryptor or other security device only encrypts the data packets and keeps all network headers and protocols in the clear. This same approach can be used for both company sites and mobile users to access data from an external data center or corporate storage site. The company site key manager loads the keys into a network security device. This architecture may be used in some implementations for multi tenancy storage such as was described above. No VPN is required and no special service provider set up is required.

In various embodiments the following features relate to transmitting or sending company site or mobile device data to the external data center or corporate storage site 

1. Data packets are encrypted by the network encryptor or other security device using selected key s loaded by the key manager .

2. No modification to the IP headers is required. However the end user customer has the option to add tagging information in the headers in the open fields in the header for various key management functions e.g. such as the tagging discussed above for the programmable cryptographic system .

3. The encrypted data is sent over an open network to the external data center or corporate storage site and is stored. The data is stored encrypted and protected from unauthorized access.

4. The network security device is located between the firewalls and the transport network equipment . Thus the firewalls and other equipment process the data in the clear.

The following features relate to receiving data from the external data center or corporate storage site 

1. The company site or mobile device requests its data from the external data center or corporate storage site.

In one embodiment network security device encrypts data that is sent to site using a first set of keys. Transport network equipment sends the encrypted first data over the network . At site transport network equipment receives the data. Network security device decrypts the received data with the same first set of keys. The decrypted data is provided to networks firewalls and other equipment .

Key manager loads the first set of keys into network security device prior to receipt of the data. In some cases key managers and are the same external key manager and are under control of the user.

In one embodiment the company sites send and receive encrypted data over an open network. The network encryptor or other security device encrypts data when sending data over the open network and decrypts when receiving encrypted data. This general approach can be applied to any desired number of company sites that are sharing data. No VPN is required and no special service provider set up is required. The key manager for all company sites is established by any secure means to send or insert the keys to each site.

In one embodiment the storage security device encrypts all data being stored on the storage network within company site . When sharing data between company sites and the data is read from the encrypted stored data storage and by passes the network security device not shown . The encrypted data is sent by transport network equipment over the open network to the requesting company site .

The requesting company site then stores the encrypted data in its data storage network . When the requesting company site access the data storage security device decrypts the data using the key s e.g. previously established by key manager and then accesses the data such as with application server .

In one embodiment a similar process to the above is used when site requests data that is read from site . This data is decrypted by storage security device when application server needs access to the data. Key manager is used to load the key s into storage security device prior to requesting this data.

First data obtained from a data storage is decrypted by storage security device using the first set of keys. Network security device encrypts the first data using the second set of keys. The encrypted first data is then sent over network by transport network equipment .

The encrypted first data may be sent to mobile device or or to an external site such as data center . Each of the mobile devices and the external site has a security device configured to decrypt the first data using the second set of keys. The second set of keys may have been pre loaded for this purpose using mobile key manager . In one embodiment a key address is sent with the first data over the network . This key address is used by the mobile device or external site in selecting the second set of keys when decrypting the first data.

In one embodiment an authentication code is sent with the first data over the network and the authentication code is used to authenticate the mobile device or external site and verify that a proper key address is used when selecting the second set of keys. In some embodiments both the key address and the authentication code are sent with the first data.

Application server receives the decrypted first data from the storage security device and provides the first data to the network security device for encryption prior to the sending of the encrypted first data over the network by the transport network equipment . In some cases the first data is accessed by an application on application server prior to sending the first data.

In one embodiment the storage security device is a storage encryptor used to encrypt data prior to storing the data e.g. in drive arrays of data storage . The storage encryptor has dedicated key manager . When writing from the application servers of application server to the storage array the storage encryptor will encrypt the data payload only and leave its headers in the clear. The encryption keys can be a set of keys having one key or multiple keys and are determined by the key manager .

When reading the storage array the storage encryptor decrypts the outgoing data with the correct key s . The decrypted data is sent to the application server . If the data is being read requested by a mobile or external device the data is sent from the application server to network security device e.g. a network encryptor . The network encryptor encrypts the data with the same key as used for the targeted mobile or external device.

The encrypted data is then sent over an open network e.g. network to the mobile or external device with an authentication code and key address in the header e.g. header of a data packet . The mobile or external device site then decrypts the data by using the key address in the header. No VPN technology or protocols are required to transfer the encrypted data to the mobile or external device.

In one embodiment when the mobile or external device site sends data to be stored in the external storage system the mobile or external device site encrypts the data using a key with a specific key address in the header of for example a data packet and sends the encrypted data to the other end of the system i.e. the data center to store the data. The encrypted data is received by the end system data center and decrypted by the network encryptor using the key address embedded in the header.

In one embodiment the network encryptor sends the clear data to the application server for two actions 

In one embodiment the key management can be set up during the configuration of the mobile or external device site by the administrator or set up using another key management protocol. The keys are loaded into specific key addresses in the end user s device or at the external site with authenticated means to verify the keys are authenticated to each end of the secure communication channel.

Additional variations details and examples for various non limiting embodiments of the secure communication architecture system are now discussed below. In a first variation the communication system above may be used for secure communication between customers end users and data centers or company storage access facilities. For example a company located off site can encrypt data send it over the Internet and store it into any storage area such as a data center or other forms of storage. When the company is reading the data it is in an encrypted form and the data comes back to the same key manager at the company site for decryption and then local use on the company internal network.

Similarly to the company site a mobile device can interact with a storage area as discussed above. The mobile device may be for example a tablet or a portable computer. Stationary devices such as a desktop computer may also use the security communication system.

Regarding in another variation there are two different sets of keys. The key manager has the primary set of keys. The company gives the mobile device a secondary set of keys such as expendable keys having a limited life. When the mobile device reads data from the data center the data center only gives the mobile device that data which it is permitted to read. The mobile device may read the data and the secondary set of keys may be discarded in some cases after use.

Regarding in one variation this shows two company sites. The company is sending a large amount of data between the sites using the same system and is encrypting the data at both ends. So a VPN network is no longer needed. The key managers are controlled at both sites by the same company. Since the company controls the key managers used at its sites the company can do secure communication between the sites.

Regarding in one variation the security device is behind the firewall e.g. the firewall may be provided by security network equipment as contrasted to in which the security device is outside of the firewall .

Regarding in one variation there are two encryptors. There is an encryptor dedicated for storage. In front of the application server there is another encryptor dedicated to sending data outside of the network. In an alternative approach a single box or hardware unit can be used to provide the functions of both the network encryptor and the storage encryptor.

At least some aspects disclosed can be embodied at least in part in software. That is the techniques may be carried out in a computer system or other data processing system in response to its processor such as a microprocessor executing sequences of instructions contained in a memory such as ROM volatile RAM non volatile memory cache or a remote storage device.

In various embodiments hardwired circuitry may be used in combination with software instructions to implement the techniques. Thus the techniques are neither limited to any specific combination of hardware circuitry and software nor to any particular source for the instructions executed by the data processing system.

Although some of the drawings may illustrate a number of operations in a particular order operations which are not order dependent may be reordered and other operations may be combined or broken out. While some reordering or other groupings are specifically mentioned others will be apparent to those of ordinary skill in the art and so do not present an exhaustive list of alternatives. Moreover it should be recognized that various stages or components could be implemented in hardware firmware software or any combination thereof.

In the foregoing specification the disclosure has been described with reference to specific exemplary embodiments thereof. It will be evident that various modifications may be made thereto without departing from the broader spirit and scope as set forth in the following claims. The specification and drawings are accordingly to be regarded in an illustrative sense rather than a restrictive sense.

