---

title: Controlling subscriber identity module (SIM) active state in a multiple SIMs radio
abstract: An apparatus, a system and a method of controlling a subscriber identity module (SIM) operation state in a multiple SIMs radio. For example, while operating a first packet switch (PS) service on a first SIM, a multi-SIM radio is configured to receive a PS paging signal indicating on arrival of a second PS service configured to operate on a second SIM. The radio may determine a priority of the first PS service, and a priority of the second PS service. The radio is configured to activate the second SIM, for example, if the priority of the second PS service is higher than the priority of the first PS service operating on the first SIM.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09461685&OS=09461685&RS=09461685
owner: INTEL IP CORPORATION
number: 09461685
owner_city: Santa Clara
owner_country: US
publication_date: 20141019
---
Some embodiments described herein generally relate to controlling subscriber identity module SIM operation state in a multiple SIMs radio.

In a multi SIM device e.g. a Smartphone with one transmitter circuitry only one SIM can use the transmitter circuitry at a time. When a service operated on one SIM is in use other services on the alternate SIM s are suspended. State of the art is to give preference of circuit switch CS based services versus packet switch PS based services. An incoming CS service on an alternate SIM may suspend any PS services running on the active SIM. CS preference is due to CS voice service which is rated as a high priority service.

In contrast PS based services on the alternate SIM do not interrupt PS based services of the active SIM.

Reference will now be made to the exemplary embodiments illustrated and specific language will be used herein to describe the same. It will nevertheless be understood that no limitation of the scope of the disclosure is thereby intended.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of some embodiments. However it will be understood by persons of ordinary skill in the art that some embodiments may be practiced without these specific details. In other instances well known methods procedures components units and or circuits have not been described in detail so as not to obscure the discussion.

Discussions herein utilizing terms such as for example processing computing calculating determining establishing analyzing checking or the like may refer to operation s and or process es of a computer a computing platform a computing system or other electronic computing device that manipulate and or transform data represented as physical e.g. electronic quantities within the computer s registers and or memories into other data similarly represented as physical quantities within the computer s registers and or memories or other information storage medium that may store instructions to perform operations and or processes.

The terms plurality and a plurality as used herein include for example multiple or two or more . For example a plurality of items includes two or more items.

References to one embodiment an embodiment demonstrative embodiment various embodiments etc. indicate that the embodiment s so described may include a particular feature structure or characteristic but not every embodiment necessarily includes the particular feature structure or characteristic. Further repeated use of the phrase in one embodiment does not necessarily refer to the same embodiment although it may.

As used herein unless otherwise specified the use of the ordinal adjectives first second third etc. to describe a common object merely indicate that different instances of like objects are being referred to and are not intended to imply that the objects so described must be in a given sequence either temporally spatially in ranking or in any other manner.

Some embodiments may be used in conjunction with various devices and systems for example a Personal Computer PC a User Equipment UE a Mobile Device MD an Internet of Things IoT device a desktop computer a mobile computer a laptop computer a notebook computer a tablet computer an Ultrabook computer a Smartphone device a server computer a handheld computer a handheld device a Personal Digital Assistant PDA device a handheld PDA device an on board device an off board device a hybrid device a vehicular device a non vehicular device a mobile or portable device a consumer device a non mobile or non portable device a wireless communication station a wireless communication device a wireless Access Point AP a wired or wireless router a wired or wireless modem a video device an audio device an audio video A V device a wired or wireless network a cellular network a cellular node a handheld device e.g. a Smartphone a Wireless Application Protocol WAP device vending machines sell terminals and the like.

The phrases wireless device and or mobile device as used herein includes for example a device capable of wireless communication a communication device capable of wireless communication a communication station capable of wireless communication a portable or non portable device capable of wireless communication or the like. In some demonstrative embodiments a wireless device may be or may include a peripheral that is integrated with a computer or a peripheral that is attached to a computer. In some demonstrative embodiments the phrase wireless device and or mobile device may optionally include a wireless service.

The term communicating as used herein with respect to a wire and or wireless and or internal communication signal includes transmitting the communication signal and or receiving the communication signal. For example a communication unit which is capable of communicating a communication signal may include a transmitter circuitry to transmit the communication signal to at least one other communication unit and or a communication receiver to receive the communication signal from at least one other communication unit. The verb communicating may be used to refer to the action of transmitting or the action of receiving. In one example the phrase communicating a signal may refer to the action of transmitting the signal by a first device and may not necessarily include the action of receiving the signal by a second device. In another example the phrase communicating a signal may refer to the action of receiving the signal by a first device and may not necessarily include the action of transmitting the signal by a second device.

Reference is made to which schematically illustrates a cellular system in accordance with some demonstrative embodiments.

For example cellular system may include third generation 3G fourth generation 4G fifth generation 5G sixth generation 6G a long term evolution LTE an advance LTE global system for mobile communications GSM cellular networks or the like.

According to some non limiting embodiments for example mobile device may include an antenna and or mobile device may include antenna . For example mobile devices and or may include a wireless mobile device such as for example a cellphone a Smartphone a wearable device a tablet a laptop computer a UE an Internet of things IoT device and the like.

Base station may establish a PS service with mobile device and or mobile device through wireless channel s . For example base station may include a node B NB an enhanced NB eNB a home eNB HeNB or the like.

According to a non limiting exemplary embodiment mobile device and or mobile device may include a multiple SIMs radio with a transmitter e.g. a single transmitter being shared by at least two SIMs. For example the multiple SIMs radio may include for example two SIMs. PS service may operate on a single SIM. Some demonstrative embodiments are described herein with respect to a multiple SIMs radio including two SIMs. However in other embodiments the multiple SIMs radio may include any other number of SIMs.

In some demonstrative embodiments multiple SIMs radio may be configured to switch between the multiple SIMs based on a priority of PS e.g. as described below.

In some demonstrative embodiments the multiple SIMs radio may switch between the SIMs for example when a higher priority PS service is received from base station through wireless channel for the second SIM e.g. while an ongoing PS service with a lower priority is operating on the first SIM e.g. as described below.

In some demonstrative embodiments a voice based PS may be given higher priority e.g. over PS services which are not voice based. In other embodiments the priority of the PS service may be defined according to any other additional or alternative criteria.

In one example with the introduction of IP Multimedia Subsystem IMS voice services over PS voice services running over PS may be given preference over other PS services.

In some demonstrative embodiments the multiple SIMs radio may be configured to identify PS services e.g. to determine if an oncoming PS service shall take precedence on other PS services.

Reference is made to which schematically illustrates a multiple SIMs radio in accordance with some demonstrative embodiments. For example multiple SIMs radio may perform the functionality of multiple SIMs radio .

In some demonstrative embodiments multiple SIMs radio may include a processor circuitry and or logic a SIM circuitry and or logic a SIM circuitry and or logic a modem circuitry and or logic a transmitter TX circuitry and or logic operably coupled to at least one antenna a receiver RX circuitry and or logic operably coupled to at least one antenna and a memory circuitry and or logic .

According to some embodiments processor circuitry and or logic may include a PS service policy manager logic and or circuitry an Internet Protocol IP protocol stack logic a Transmission Control Protocol User Datagram Protocol TCP UDP protocol stack logic and an application layer logic which may include an application .

According to some demonstrative embodiments modem circuitry and or logic may include a 3G and or 4G and or 5G and or 6G cellular modem such as for example an LTE and or LTE advance cellular modem. Antennas and or may include one or more antennas for example an antenna array a dipole antenna an internal antenna a phase array antenna or the like. Memory circuitry and or logic may include for example a FLASH memory a Read Only Memory ROM a Random Access Memory RAM a Dynamic RAM DRAM a static RAM SRAM a solid state memory and or any type of a volatile memory and or a non volatile memory.

For example PS service may operate on a first SIM the active SIM e.g. SIM which is operably coupled to transmitter circuitry and or logic while a second SIM the inactive SIM e.g. SIM may be disconnected to transmitter circuitry and or logic .

In some demonstrative embodiments multiple SIMs radio may detect a type of incoming PS services may also be referred to as mobile terminated PS services or outgoing PS services may also be referred to as mobile originated PS services which are to be set up on an alternate SIM e.g. SIM while another PS service is ongoing on an active SIM e.g. SIM .

In some demonstrative embodiments a configured policy may determine if an upcoming PS service on the alternate SIM e.g. SIM has higher priority than the ongoing PS service on the active SIM e.g. SIM .

In some demonstrative embodiments multiple SIMs radio may be configured to activate the alternate SIM e.g. SIM to connect the alternate SIM to transmitter circuitry or logic for PS service setup of the upcoming PS service and to disconnect SIM from transmitter circuitry and or logic .

In some demonstrative embodiments while a first PS service is operating on SIM receiver circuitry and or logic may receive a PS paging signal. The PS paging signal may indicate an arrival of a second PS service e.g. to be operated by SIM . PS service policy manger circuitry may determine a first PS service priority of the first PS service and a second PS service priority of the second PS service. If for example the priority of the second PS service is higher than the priority of the first PS service operating at SIM PS service policy manger circuitry may detach SIM from transmitter circuitry may connect SIM to transmitter circuitry may activate SIM and may suspend SIM if desired.

In some demonstrative embodiments PS service policy manger circuitry may use one or more detection methods to determine the priority of a PS service e.g. PS service . For example PS service policy manger circuitry may use one or more detection methods described below.

In one demonstrative embodiment PS service policy manger circuitry may inspect the content of the PS paging signal of a PS service e.g. the first or the second PS service described above and may detect the type of the PS service based on the content of the PS paging signal. For example the PS paging message may include a service description field and the content of the service description field may include a voice service indicator if desired.

In another demonstrative embodiment PS service policy manger circuitry may detect the type of a PS service e.g. the first or the second PS service described above based on data radio bearer DRB identification ID and or an evolved packed system EPS context ID and or packed data protocol PDP context ID. In one example PS service policy manger may set a radio resource control RRC connection with a base station e.g. base station to identify receiving of a user data and to determine a priority of an incoming PS service e.g. based on the content of the user data. After setup of the RRC connection IP protocol stack logic and or TCP UDP protocol stack logic may identify on which DRB EPS PDP context ID the user data is received. The priority of the incoming PS service may be determined for example based on the priority associated with the EPS PDP context ID.

For example the PS service priority may be determined based on at least one of a source IP address a source port a destination port a transport protocol e.g. UPD TCP a session protocol e.g. SIP or the like. The criteria on which parameter s to select to determine the priority may be configured for example by a user application and or by the user and or by a device manufacturer and or by the cellular network operator or the like.

In one example detecting the priority of a SP service may be based on criteria set by a user application . For example IP multimedia subsystem IMS signaling messages may come from an IMS Proxy Call Session Control Function PCSCF whose source IP address may be known. An incoming IP packet with the IP source address set to the one of the IMS PCSCF may be related to IMS. The incoming IMS service may be prioritized accordingly.

In another demonstrative embodiment PS service policy manger may detect the PS service e.g. PS service at a modem circuitry and or logic or at application layer logic e.g. without interrupting the ongoing PS service on the active SIM.

For example an ongoing PS service at modem may be detected based on the PDP EPS context used to send the data. For example an access point name APN of the EPS context used to transmit the data may be used to identify the PS service. For example for IMS service the PDP EPS context may be identified with the IMS APN. In another example detecting the ongoing PS service at the modem may be done by inspecting the received IP packet. The PS service detection may be based on source destination IP address source destination port protocol type etc. which may be present in the IP packet. For example when an IP packet for the alternate suspended SIM has to be transmitted the destination IP address set in the IP packet may be used to identify the corresponding PS service application if desired.

In another demonstrative embodiment the detection of the PS service may be performed at the application layer logic. For example the PS service detection may be based on the operating system specific application ID OSAppId or on a fully qualified domain name FQDN if desired.

For example PS service policy manager may include a list of PS service detection criteria and the PS service detection may be based on one or more of e.g. a combination of two or more of but not limited to the following parameters APN EPS PDP context ID Source destination IP address Source destination port OS specific application ID and the like.

Reference is made to which schematically illustrates a method of controlling a SIM operation state in a multiple SIMs radio in accordance with some demonstrative embodiments. In some demonstrative embodiments one or more of the operations of the method of may be performed by a multiple SIMs radio e.g. multiple SIMs radio .

As shown in a SIM is active text box a SIM is suspended text box and a PS service is ongoing text box between SIM and a network e.g. a cellular network. While operating a PS service on SIM SIM may receive a PS paging signal indicating on arrival of a new PS service configured to operate on SIM .

For example a PS service policy manager e.g. PS policy manager of multiple SIMs radio may temporary interrupt the service on SIM e.g. to enable SIM to set up an RRC connection and identify the new PS service text box . After RRC connection setup the PS service policy manger for example may identify the PS service type text box and may determine the new PS service priority and the ongoing PS service priority text box .

In some demonstrative embodiments if the priority of the new PS service is higher than the priority of the ongoing PS service the PS service policy manager may switch active SIM text box . For example the PS service policy manager may switch SIM to become the active SIM text box and SIM to be suspended text box . A new ongoing PS service may be setup between SIM and network text box .

Reference is made to which schematically illustrates a mobile device with a multiple SIMs radio e.g. multiple SIMs radio in accordance with some demonstrative embodiments The mobile device may include for example a user equipment UE a mobile station MS a mobile wireless device a cell phone a Smartphone a mobile communication device a tablet a handset or other type of mobile wireless device. The mobile device may include one or more antennas configured to communicate with a transmission station such as a base station BS an evolved Node B eNB a base band unit BBU a remote radio head RRH a remote radio equipment RRE a relay station RS a radio equipment RE or other type of wireless wide area network WWAN access point. The mobile device may be configured to communicate using at least one wireless communication standard including 3GPP LTE 3GPP UMTS GSM WiMAX High Speed Packet Access HSPA Bluetooth and WiFi. The mobile device may communicate using separate antennas for each wireless communication standard or shared antennas for multiple wireless communication standards. The mobile device may communicate in a WLAN a wireless personal area network WPAN and or a WWAN. In some demonstrative embodiments mobile device may perform the functionality of mobile device and or .

Various techniques or certain aspects or portions thereof may take the form of program code i.e. instructions embodied in tangible media such as for example CD ROMs hard drives Solid State Drives SSD non transitory computer readable storage medium or any other machine readable storage medium wherein when the program code is loaded into and executed by a machine such as a computer the machine becomes an apparatus for practicing the various techniques. In the case of program code execution on programmable computers the computing device may include a processor circuitry a storage medium readable by the processor circuitry including volatile and non volatile memory and or storage elements at least one input device and at least one output device. The volatile and non volatile memory and or storage elements may be a RAM EPROM flash drive optical drive magnetic hard drive or other medium for storing electronic data. One or more programs that may implement or utilize the various techniques described herein may use an application programming interface API reusable controls and the like. Such programs may be implemented in a high level procedural or object oriented programming language to communicate with a computer system. However the program s may be implemented in assembly or machine language if desired. In any case the language may be a compiled or interpreted language and combined with hardware implementations.

Reference is made to which schematically illustrates a product of manufacture in accordance with some demonstrative embodiments. Product may include a non transitory machine readable storage medium to store logic which may be used for example to perform at least part of the functionality of one or more elements of system one or more elements of multiple SIMs radio and or to perform one or more operations of the method of . The phrase non transitory machine readable medium is directed to include all computer readable media with the sole exception being a transitory propagating signal.

In some demonstrative embodiments product and or machine readable storage medium may include one or more types of computer readable storage media capable of storing data including volatile memory non volatile memory removable or non removable memory erasable or non erasable memory writeable or re writeable memory and the like. For example machine readable storage medium may include RAM DRAM Double Data Rate DRAM DDR DRAM SDRAM static RAM SRAM ROM programmable ROM PROM erasable programmable ROM EPROM electrically erasable programmable ROM EEPROM Compact Disk ROM CD ROM Compact Disk Recordable CD R Compact Disk Rewriteable CD RW flash memory e.g. NOR or NAND flash memory content addressable memory CAM polymer memory phase change memory ferroelectric memory silicon oxide nitride oxide silicon SONOS memory a disk a floppy disk a hard drive an optical disk a magnetic disk a card a magnetic card an optical card a tape a cassette and the like. The computer readable storage media may include any suitable media involved with downloading or transferring a computer program from a remote computer to a requesting computer carried by data signals embodied in a carrier wave or other propagation medium through a communication link e.g. a modem radio or network connection.

In some demonstrative embodiments logic may include instructions data and or code which if executed by a machine may cause the machine to perform a method process and or operations as described herein. The machine may include for example any suitable processing platform computing platform computing device processing device computing system processing system computer processor or the like and may be implemented using any suitable combination of hardware software firmware and the like.

Example 1 includes a method of controlling a subscriber identity module SIM operation state in a multiple SIMs radio the method comprising while operating a first packet switch PS service on a first SIM receiving a second PS service configured to operate on a second SIM determining a priority of the first PS service and a priority of the second PS service and activating the second SIM if the priority of the second PS service is higher than the priority of the first PS service.

Example 2 includes the subject matter of Example 1 and optionally wherein activating the second SIM comprises suspending the first PS service at the first SIM detaching the first SIM from a transmitter circuitry and connecting the second SIM to the transmitter circuitry.

Example 3 includes the subject matter of Example 1 comprising detecting a type of the first PS service and determining the priority of the first PS service based on the type of the first PS service and detecting a type of the second PS service and determining the priority of the second PS service based on the type of the second PS service.

Example 4 includes the subject matter of Example of any one of Examples 1 3 and optionally wherein the second PS service comprises an incoming PS service the method comprises receiving a PS paging signal indicating arrival of the second PS service detecting a type of the second PS service based on a content of the PS paging signal and determining the priority of the second PS service based on the type of the second PS service.

Example 5 includes the subject matter of Example 4 and optionally comprising detecting the type of the second PS service based on a data radio bearer DRB identification ID .

Example 6 includes the subject matter of Example 4 and optionally comprising setting a radio resource control connection RRC with a base station identifying reception of a user data and determining a priority of the incoming PS service based on content of the user data.

Example 7 includes the subject matter of Example 4 and optionally comprising detecting a type of the first PS service or the second PS service based on inspection of a first received data packet in the multiple SIMs radio and determining the priority of the first PS service or the priority of the second PS service based on the type of the first PS service or the second PS service.

Example 8 includes the subject matter of Example 4 and optionally comprising setting a radio resource control connection RRC with a base station receiving an Internet Protocol IP packet and inspecting the IP packet to determine the priority of the second PS service based on at least one parameter selected from a group consisting of a source IP address a source port a destination port a transport protocol and a session protocol.

Example 9 includes the subject matter of any one of Examples 1 3 and optionally wherein at least one PS service selected from the group consisting of the first PS service and the second PS service comprises an ongoing PS service the method comprising detecting a priority of the ongoing PS service based on a type of the ongoing PS service.

Example 10 includes the subject matter of Example 9 and optionally comprising detecting the priority of the ongoing PS service at a modem.

Example 11 includes the subject matter of Example 9 and optionally comprising detecting the priority of the ongoing PS service at an application layer logic by a processor circuitry.

Example 12 includes a multiple subscriber identity module SIM s radio configured to control a SIM operation state the multiple SIMs radio comprising transmitter circuitry configured to transmit communications of an active packet switch PS service receiver circuitry configured to receive communications of the active PS service and processor circuitry configured to determine a priority of a first PS service operating on a first SIM and a priority of a second PS service to operate on a second SIM and to activate the second PS service and suspend the first PS service if the priority of the second PS service is higher than the priority of the first PS service.

Example 13 includes the subject matter of Example 12 and optionally wherein the processor circuitry is configured to detach the first SIM from the transmitter circuitry and to connect the second SIM to the transmitter circuitry.

Example 14 includes the subject matter of Example 12 and optionally wherein the processor circuitry is configured to detect a type of the first PS service and to determine the priority of the first PS service based on the type of the first PS service and to detect a type of the second PS service and to determine the priority of the second PS service based on the type of the second PS service.

Example 15 includes the subject matter of any one of Examples 12 14 and optionally wherein the receiver circuitry is configured to receive a PS paging signal indicating arrival of the second PS service the processor circuitry being configured to detect a type of the second PS service based on the PS paging signal content and to determine the priority of the second PS service based on the type of the second PS service.

Example 16 includes the subject matter of Example 15 and optionally wherein the processor circuitry is configured to detect the type of the second PS service based on a data radio bearer DRB identification ID and to determine the priority of the second PS service based on the type of the second PS service.

Example 17 includes the subject matter of Example 15 and optionally wherein the processor circuitry is configured to set a radio resource control connection RRC with a base station to identify a reception of a user data and to determine a priority of an incoming PS service based on the content of the user data.

Example 18 includes the subject matter of Example 15 and optionally wherein the processor circuitry is configured to detect the type of the second PS service based on inspection of a first received data packet.

Example 19 includes the subject matter of Example 15 and optionally wherein the processor circuitry is configured to set a radio resource control connection RRC with a base station to receive an Internet Protocol IP packet to inspect the IP packet and to determine the priority of the second PS service based on at least one parameter selected from the group consisting of a source IP address a source port a destination port a transport protocol and a session protocol.

Example 20 includes the subject matter of Example 12 and optionally wherein the processor circuitry is configured to detect a priority of an ongoing PS service based on the type of the ongoing PS service.

Example 21 includes the subject matter of Example 20 and optionally wherein the processor is configured to detect the priority of the ongoing PS service at a modem.

Example 22 includes the subject matter of Example 20 and optionally wherein the processor circuitry is configured to detect the priority of the ongoing PS service at an application layer.

Example 23 includes a multiple subscriber identity module SIM s radio configured to control a SIM operation state the multiple SIMs radio comprising a transmitter circuitry to be operably coupled to a first SIM or to a second SIM the transmitter circuitry configured to transmit communications of an active packet switch PS service at least two dipole antennas operably coupled to the transmitter circuitry a receiver circuitry configured to receive communications of the active PS service and processor circuitry configured to determine a priority of a first PS service operating on the first SIM and a priority of a second PS service to operate on the second SIM and to activate the second PS service and suspend the first PS service if the priority of the second PS service is higher than the priority of the first PS service.

Example 24 includes the subject matter of Example 23 and optionally wherein the processor circuitry is configured to detach the first SIM from the transmitter circuitry and to connect the second SIM to the transmitter circuitry.

Example 25 includes the subject matter of Example 23 and optionally wherein the processor circuitry is configured to detect a type of the first PS service and to determine the priority of the first PS service based on the type of the first PS service and to detect a type of the second PS service and to determine the priority of the second PS service based on the type of the second PS service.

Example 26 includes the subject matter of any one of Examples 23 25 and optionally wherein the receiver circuitry is configured to receive a PS paging signal indicating arrival of the second PS service the processor circuitry being configured to detect the type of the first or the second PS service based on content of the PS paging signal and to determine the priority of the second PS service based on the type of the second PS service.

Example 27 includes the subject matter of any one of Examples 23 25 and optionally wherein the processor circuitry is configured to detect a type of the second PS service based on a data radio bearer DRB identification ID and to determine the priority of the second PS service based on the type of the second PS service.

Example 28 includes the subject matter of Example 26 and optionally wherein the processor circuitry is configured to set a radio resource control connection RRC with a base station to identify a reception of a user data and to determine a priority of an incoming PS service based on the content of the user data.

Example 29 includes the subject matter of Example 26 and optionally wherein the processor circuitry is configured to detect the type of the second PS service based on inspection of a first received data packet.

Example 30 includes the subject matter of any one of Examples 23 25 and optionally wherein the processor circuitry is configured to set a radio resource control connection RRC with a base station to receive an Internet Protocol IP packet to inspect the IP packet and to determine the priority of the second PS service based on at least one parameter selected from the group consisting of a source IP address a source port a destination port a transport protocol and a session protocol.

Example 31 includes the subject matter of any one of Examples 23 25 and optionally wherein the processor circuitry is configured to detect a priority of an ongoing PS based on the type of the ongoing PS service.

Example 32 includes the subject matter of Example 31 and optionally wherein the processor circuitry is configured to detect the priority of the ongoing PS service at a modem circuitry.

Example 33 includes the subject matter of Example 31 and optionally wherein the processor circuitry is configured to detect the priority of the ongoing PS service initiation at an application layer logic.

Example 34 includes a cellular system comprising a multiple subscriber identity module SIM s radio configured to control a SIM operation state the multiple SIMs radio comprises transmitter circuitry configured to transmit communications of an active packet switch PS service receiver circuitry configured to receive communications of the active PS service and processor circuitry configured to determine a priority of a first PS service operating on a first SIM and a priority of a second PS service to operate on a second SIM and to activate the second PS service and suspend the first PS service if the priority of the second PS service is higher than the priority of the first PS service.

Example 35 includes the subject matter of Example 34 and optionally wherein the processor circuitry is configured to detach the first SIM from the transmitter circuitry and to connect the second SIM to the transmitter circuitry.

Example 36 includes the subject matter of Example 34 and optionally wherein the processor circuitry is configured to detect a type of the first PS service and to determine the priority of the first PS service based on the type of the first PS service and to detect a type of the second PS service and to determine the priority of the second PS service based on the type of the second PS service.

Example 37 includes the subject matter of any one of Examples 34 36 and optionally wherein the receiver circuitry is configured to receive a PS paging signal indicating arrival of the second PS service the processor circuitry being configured to detect the type of the second PS based on content of the PS paging signal and to determine the priority of the second PS service based on the type of the second PS service.

Example 38 includes the subject matter of any one of Examples 34 36 and optionally wherein the processor circuitry is configured to detect a type of the first or the second PS service based on a data radio bearer DRB identification ID and to determine the priority of the second PS service based on the type of the second PS service.

Example 39 includes the subject matter of Example 37 and optionally wherein the processor circuitry is configured to set a radio resource control connection RRC with a base station to identify a reception of a user data and to determine a priority of an incoming PS service based on the content of the user data.

Example 40 includes the subject matter of Example 37 and optionally wherein the processor circuitry is configured to detect the type of the second PS service based on inspection of a first received data packet.

Example 41 includes the subject matter of any one of Examples 34 36 and optionally wherein the processor circuitry is configured to set a radio resource control connection RRC with a base station to receive an Internet Protocol IP packet to inspect the IP packet and to determine the priority of the second PS service based on at least one parameter selected from the group consisting of a source IP address a source port a destination port a transport protocol and a session protocol.

Example 42 includes the subject matter of Example 34 36 and optionally wherein the processor circuitry is configured to detect a priority of an ongoing PS service based on the type of the ongoing PS service.

Example 43 includes the subject matter of Example any one of Examples 42 and optionally wherein the processor circuitry is configured to detect the ongoing PS service at a modem.

Example 44 includes the subject matter of Example 42 and optionally wherein the processor circuitry is configured to detect the ongoing PS service at an application layer logic.

Example 45 includes a processor circuitry configured to control a subscriber identity module SIM operation state at a multiple SIMs radio the processor circuitry comprising an application layer logic to include a user application and a packet switch PS service policy manger logic configured to determine a priority of a first PS service operating on a first SIM and a priority of a second PS service to operate on a second SIM and to activate the second PS service and suspend the first PS service if the priority of the second PS service is higher than the priority of the first PS service.

Example 46 includes the subject matter of Example 45 and optionally wherein the PS service policy manger is configured to detach the first SIM from the transmitter circuitry and to connect the second SIM to the transmitter circuitry.

Example 47 includes the subject matter of Example 45 and optionally wherein the PS service policy manger is configured to detect a type of the first PS service and to determine the priority of the first PS service based on the type of the first PS service and to detect a type of the second PS service and to determine the priority of the second PS service based on the type of the second PS service.

Example 48 includes the subject matter of Example 45 and optionally wherein the second PS service includes an incoming PS service the PS service policy manger is configured to detect the type of the second PS based on a PS paging signal content.

Example 49 includes the subject matter of Example 48 and optionally comprising a Transmission Control Protocol User Datagram Protocol TCP UDP protocol stack logic configured to identify reception of the incoming PS service at an access point name APN of an evolved packet system EPS data radio bearer DRB identification ID after setting up a radio resource control connection RRC with a base station the PS service policy manger being configured detect a type of the second PS based on the DRB identification.

Example 50 includes the subject matter of Example 48 and optionally wherein the PS service policy manger is configured set a radio resource control connection RRC with a base station to identify a receiving of a user data and to determine a priority of the incoming PS service based on content of the user data.

Example 51 includes the subject matter of Example 48 and optionally wherein the PS service policy manger is configured detect the type of the incoming PS service based on inspecting a first received data packet.

Example 52 includes the subject matter of Example 45 and optionally comprising an Internet protocol stack logic configured to inspect a received Internet Protocol IP packet for a source IP address a source port a destination port a transport protocol and a session protocol wherein the PS service policy manger is configured to determine the PS service priority based on at least one parameter selected from the group consisting of the source IP address the source port the destination port the transport protocol and the session protocol.

Example 53 includes the subject matter of Example 45 and optionally wherein the first PS service includes an ongoing PS service the PS service policy manger being configured detect the priority of the first service based on a type of the first PS service.

Example 54 includes the subject matter of Example 53 and optionally wherein the PS service policy manger is configured detect the ongoing PS service at a modem.

Example 55 includes the subject matter of Example 53 and optionally wherein the PS service policy manger is configured detect the ongoing PS service at the application layer logic.

Example 56 includes a computer program product comprising one or more tangible computer readable non transitory storage media comprising computer executable instructions operable to when executed by at least one computer processor enable the at least one computer processor to implement a method in a multiple SIMs radio the method comprising while operating a first packet switch PS service on a first SIM receiving a second PS service configured to operate on a second SIM determining a priority of the first PS service and a priority of the second PS service and activating the second SIM if the priority of the second PS service is higher than the priority of the first PS service.

Example 57 includes the subject matter of Example 56 and optionally wherein activating the second SIM comprises suspending the first PS service at the first SIM detaching the first SIM from a transmitter circuitry and connecting the second SIM to the transmitter circuitry.

Example 58 includes the subject matter of Example 56 and optionally wherein the method comprises detecting a type of the first PS service and determining the priority of the first PS service based on the type of the first PS service and detecting a type of the second PS service and determining the priority of the second PS service based on the type of the second PS service.

Example 59 includes the subject matter of any one of Examples 56 58 and optionally wherein the second PS service comprises an incoming PS service the method comprising receiving a PS paging signal indicating arrival of the second PS service detecting a type of the second PS service based on a content of the PS paging signal and determining the priority of the second PS service based on the type of the second PS service.

Example 60 includes the subject matter of any one of Examples 56 58 and optionally wherein the method comprises detecting the type of the second PS is based on a data radio bearer DRB identification ID and determining the priority of the second PS service based on the type of the second PS service.

Example 61 includes the subject matter of Example 59 and optionally wherein the method comprises setting a radio resource control connection RRC with a base station identifying reception of a user data and determining a priority of the incoming PS service based on content of the user data.

Example 62 includes the subject matter of Example 59 and optionally wherein the method comprises detecting a type of the first PS service or the second PS service based on inspection of a first received data packet in the multiple SIMs radio and determining the priority of the first PS service or the priority of the second PS service based on the type of the first PS service or the second PS service.

Example 63 includes the subject matter of Example 59 and optionally wherein inspecting comprises setting a radio resource control connection RRC with a base station receiving an Internet Protocol IP packet and inspecting the IP packet to determine the priority of the second PS service based on at least one of parameter selected from the group consisting a source IP address a source port a destination port a transport protocol and a session protocol.

Example 64 includes the subject matter of any one of Examples 56 58 and optionally wherein at least one PS service selected from the group consisting of the first PS service and the second PS service comprises an ongoing PS service the method comprising detecting a priority of the ongoing PS service based on a type of the ongoing PS service.

Example 65 includes the subject matter of Example 64 and optionally wherein the detecting the priority of the ongoing PS service is done at a modem.

Example 66 includes the subject matter of Example 64 and optionally wherein the detecting the priority of the ongoing PS service is done at an application layer logic.

Example 67 includes a multiple subscriber identity module SIM s radio configured to control a SIM operation state the multiple SIMs radio comprising transmitter means configured to transmit communications of an active packet switch PS service receiver means configured to receive communications of the active PS service and processor means configured to determine a priority of a first PS service operating on a first SIM and a priority of a second PS service to operate on a second SIM and to activate the second PS service and suspend the first PS service if the priority of the second PS service is higher than the priority of the first PS service.

Example 68 includes the subject matter of Example 67 and optionally wherein the processor means is configured to detach the first SIM from the transmitter circuitry and to connect the second SIM to the transmitter circuitry.

Example 69 includes the subject matter of Example 67 and optionally wherein the processor means is configured to detect a type of the first PS service and to determine the priority of the first PS service based on the type of the first PS service and to detect a type of the second PS service and to determine the priority of the second PS service based on the type of the second PS service.

Example 70 includes the subject matter of any one of Examples 67 69 and optionally wherein the receiver means is configured to receive a PS paging signal indicating arrival of the second PS service the processor means being configured to detect a type of the second PS based on the PS paging signal content and to determine the priority of the second PS service based on the type of the second PS service.

Example 71 includes the subject matter of any one of Examples 67 69 and optionally wherein the processor means is configured to detect a type of the second PS service based on a data radio bearer DRB identification ID and to determine the priority of the second PS service based on the type of the second PS service.

Example 72 includes the subject matter of Example 70 and optionally wherein the processor means is configured to set a radio resource control connection RRC with a base station to identify a reception of a user data and to determine a priority of an incoming PS service based on content of the user data.

Example 73 includes the subject matter of Example 70 and optionally wherein the processor means is configured to detect the type of the second PS service based on inspection of a first received data packet.

Example 74 includes the subject matter of any one of Examples 67 69 and optionally wherein the processor means is configured to set a radio resource control connection RRC with a base station to receive an Internet Protocol IP packet to inspect the IP packet and to determine the priority of the second PS service based on at least one parameter selected from the group consisting of a source IP address a source port a destination port a transport protocol and a session protocol.

Example 75 includes the subject matter of any one of Examples 67 69 and optionally wherein the processor means is configured to detect a priority of an ongoing PS service based on a type of the ongoing PS service.

Example 76 includes the subject matter of Example 75 and optionally wherein the processor means is configured to detect the priority of the ongoing PS service at a modem.

Example 77 includes the subject matter of Example 75 and optionally wherein the processor means is configured to detect the priority of the ongoing PS service at an application layer.

Example 78 includes a processor circuitry configured to control a subscriber identity module SIM operation state at a multiple SIMs radio the processor circuitry comprising application layer means to include a user application and packet switch PS service policy manger means configured to determine a priority of a first PS service operating on a first SIM and a priority of a second PS service to operate on a second SIM and to activate the second PS service and suspend the first PS service if the priority of the second PS service is higher than the priority of the first PS service.

Example 79 includes the subject matter of Example 78 and optionally wherein the PS service policy manger means is configured to detect a type of the first PS service and to determine the priority of the first PS service based on the type of the first PS service and to detect a type of the second PS service and to determine the priority of the second PS service based on the type of the second PS service.

Example 80 includes the subject matter of Example 78 or 79 and optionally wherein the second PS service includes an incoming PS service the PS service policy manger means is configured to detect the type of the second PS based on a PS paging signal content.

Example 81 includes the subject matter of Example 80 and optionally comprising Transmission Control Protocol User Datagram Protocol TCP UDP protocol stack means configured to identify reception of the incoming PS service at an access point name APN of an evolved packet system EPS data radio bearer DRB identification ID after setting up a radio resource control connection RRC with a base station the PS service policy manger means being configured to detect a type of the incoming PS service based on the DRB identification.

Example 82 includes the subject matter of Example 80 and optionally comprising Internet protocol stack means configured to inspect a received Internet Protocol IP packet for a source IP address a source port a destination port a transport protocol and a session protocol and the PS service policy manger means is configured to determine the PS service priority based on at least one parameter selected from the group consisting of the source IP address the source port the destination port the transport protocol and the session protocol.

Example 83 includes the subject matter of Example 78 or 79 and optionally wherein the first PS service includes an ongoing PS service the PS service policy manger means being configured detect the priority of the first service based on a type of the first PS service.

Example 84 includes the subject matter of Example 83 and optionally wherein the PS service policy manger means is configured to detect the ongoing PS service at a modem.

Example 85 includes the subject matter of Example 83 and optionally wherein the PS service policy manger means is configured to detect the ongoing PS service at the application layer logic.

Example 86 includes a computer program product comprising one or more tangible computer readable non transitory storage media comprising computer executable instructions operable to when executed by at least one computer processor enable the at least one computer processor to implement a method in a multiple SIMs radio the method comprising while operating a first packet switch PS service on a first SIM receiving a second PS service configured to operate on a second SIM determining a priority of the first PS service and a priority of the second PS service and activating the second SIM if the priority of the second PS service is higher than the priority of the first PS service.

Example 87 includes the subject matter of Example 86 and optionally wherein activating the second SIM comprises suspending the first PS service at the first SIM detaching the first SIM from a transmitter circuitry and connecting the second SIM to the transmitter circuitry.

Example 88 includes the subject matter of Example 86 and optionally wherein the method comprises detecting a type of the first PS service and determining the priority of the first PS service based on the type of the first PS service and detecting a type of the second PS service and determining the priority of the second PS service based on the type of the second PS service.

Example 89 includes the subject matter of any one of Examples 86 88 and optionally wherein the second PS service comprises an incoming PS service the method comprising receiving a PS paging signal indicating arrival of the second PS service detecting a type of the second PS service based on a content of the PS paging signal and determining the priority of the second PS service based on the type of the second PS service.

Example 90 includes the subject matter of Example 89 and optionally comprising setting a radio resource control connection RRC with a base station receiving an Internet Protocol IP packet and inspecting the IP packet to determine the priority of the second PS service based on at least one parameter selected from the group consisting of a source IP address a source port a destination port a transport protocol and a session protocol.

Example 91 includes the subject matter of any one of Examples 86 88 and optionally wherein at least one PS service selected from the group consisting of the first PS service and the second PS service comprises an ongoing PS service the method comprising detecting at an element selected from the group consisting of a modem and an application layer logic a priority of the ongoing PS service based on a type of the ongoing PS service.

It should be understood that many of the functional units described in this specification have been labeled as modules in order to more particularly emphasize their implementation independence. For example a module may be implemented as a hardware circuit comprising custom VLSI circuits or gate arrays off the shelf semiconductors such as logic chips transistors or other discrete components. A module may also be implemented in programmable hardware devices such as field programmable gate arrays programmable array logic programmable logic devices or the like.

Modules may also be implemented in software for execution by various types of processors. An identified module of executable code may for instance comprise one or more physical or logical blocks of computer instructions which may for instance be organized as an object procedure or function. Nevertheless the executables of an identified module need not be physically located together but may comprise disparate instructions stored in different locations which when joined logically together comprise the module and achieve the stated purpose for the module.

Indeed a module of executable code may be a single instruction or many instructions and may even be distributed over several different code segments among different programs and across several memory devices. Similarly operational data may be identified and illustrated herein within modules and may be embodied in any suitable form and organized within any suitable type of data structure. The operational data may be collected as a single data set or may be distributed over different locations including over different storage devices and may exist at least partially merely as electronic signals on a system or network. The modules may be passive or active including agents operable to perform desired functions.

As used herein a plurality of items structural elements compositional elements and or materials may be presented in a common list for convenience. However these lists should be construed as though each member of the list is individually identified as a separate and unique member. Thus no individual member of such list should be construed as a de facto equivalent of any other member of the same list solely based on their presentation in a common group without indications to the contrary. In addition various embodiments and example ay be referred to herein along with alternatives for the various components thereof. It is understood that such embodiments examples and alternatives are not to be construed as defacto equivalents of one another but are to be considered as separate and autonomous representations.

Furthermore the described features structures or characteristics may be combined in any suitable manner in one or more embodiments.

In the foregoing description numerous specific details are provided such as examples of layouts distances network examples etc. to provide a thorough understanding of some demonstrative embodiments. One skilled in the relevant art will recognize however that some embodiments can be practiced without one or more of the specific details or with other methods components layouts etc. In other instances well known structures materials or operations are not shown or described in detail to avoid obscuring aspects of the disclosure.

While the forgoing examples are illustrative of the principles of some embodiments in one or more particular applications it will be apparent to those of ordinary skill in the art that numerous modifications in form usage and details of implementation can be made without the exercise of inventive faculty and without departing from the principles and concepts of the disclosure. Accordingly it is not intended that the disclosure be limited except as by the claims set forth below.

