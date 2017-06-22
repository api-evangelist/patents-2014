---

title: System and method for managing tokens authorizing on-device operations
abstract: A system and method can support on-device operation management. A token issuer on a backend server, and/or a tool, can generate an authorization token, which is bound to a user of one or more devices using a unique identifier (ID) that is assigned to the user. The unique ID can be known and/or shared between the an on-device authorizing entity and the token issuer. Then, the on-device authorizing entity can verify the authorization token before granting an execution of one or more protected on-device operations. Furthermore, the on-device authorizing entity may not grant the execution of the one or more protected on-device operations, when the unique ID is erased from the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09525705&OS=09525705&RS=09525705
owner: ORACLE INTERNATIONAL CORPORATION
number: 09525705
owner_city: Redwood Shores
owner_country: US
publication_date: 20140320
---
This application claims priority on U.S. Provisional Patent Application No. 61 905 008 entitled SYSTEM AND METHOD FOR MANAGING TOKENS AUTHORIZING ON DEVICE OPERATIONS filed Nov. 15 2013 which application is herein incorporated by reference.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention is generally related to computer systems and is particularly related to device management.

In the post personal computer PC era businesses often permit employees to bring various mobile devices such as smart phones tablets and laptops to their workplace. The employees can use those personally owned devices to access privileged company information and applications. The information technology industry has been evolving to promote the secure and interoperable deployment and management of software applications using secure chip technology e.g. based on the Global Platform Specifications. This is the general area that embodiments of the invention are intended to address.

Described herein are systems and methods that can support on device operation management. A token issuer on a backend server and or a tool can generate an authorization token which is bound to a user of one or more devices using a unique identifier ID that is assigned to the user. The unique ID can be known and or shared between the on device authorizing entity and the token issuer. Then the on device authorizing entity can verify the authorization token before granting an execution of one or more protected on device operations. Furthermore the on device authorizing entity may not grant the execution of the one or more protected on device operations when the unique ID is erased from the device.

The invention is illustrated by way of example and not by way of limitation in the figures of the accompanying drawings in which like references indicate similar elements. It should be noted that references to an or one or some embodiment s in this disclosure are not necessarily to the same embodiment and such references mean at least one.

In accordance with an embodiment the systems and methods described herein can be implemented as or used with a device such as a mobile device e.g. smart phone or other device

In accordance with various embodiments the device can be based on a system on chip SoC architecture. The description of embodiments of the invention provided herein generally uses the ARM SoC architecture as one example of a SoC architecture. It will be apparent to those skilled in the art that in accordance with various embodiments other types of SoC architecture can be used without limitation.

In accordance with an embodiment an SoC architecture which includes both hardware and software components can provide on chip integration of various types of functional hardware in order to perform different tasks such as power management computing audio video graphics global positioning system GPS and radio.

The hardware components in a SoC architecture can include various analog digital and storage components. For example in accordance with an embodiment the analog components can include analog to digital converter ADC and digitally controlled amplifier DCA components phase locked loop PLL components transmitting Tx receiving Rx components radio frequency RF components. The digital components can include various processors interfaces and accelerators. The storage components can include static random access memory SRAM dynamic random access memory DRAM non volatile storage components such as flash memory and read only memory ROM . Additionally the SoC can contain programmable hardware such as field programmable gate array FPGA mixed signal blocks and sensors.

In accordance with an embodiment a SoC architecture can include both on chip and off chip software components. For example the software components in a SoC architecture can include a real time operation system RTOS device drivers and software applications.

Additionally in accordance with an embodiment a SoC architecture can take advantage of various portable reusable components and or circuit designs embedded CPU embedded memory and real world interfaces such as universal serial bus USB peripheral component Interconnect PCI and Ethernet.

In accordance with an embodiment the processors in the SoC can include a single core or multiple core central processing unit CPU a cache component a graphics processing unit GPU a video codec and a liquid crystal display LCD video interface.

Also in accordance with an embodiment the SoC can include a bridge that connects the high performance on chip bus to a peripheral bus which can be run with a lower bandwidth using lower power latched address and control and simple interface. For example as shown in the peripheral bus can provide access to a universal asynchronous receiver transmitter UART a timer a keypad interface and programmed input output PIO interfaces .

In accordance with an embodiment the SoC for the device can establish mobile connectivity using different technologies such as Bluetooth Wi Fi cellular 3G 4G LTE LTE A modem and or GPS.

The exemplary SoC architecture shown in is provided for purposes of illustration. In accordance with various embodiments other types of SoC architecture can be used.

The REE can include the normal runtime environment based on a rich OS or the main OS such as Android or iOS while the TEE which is a secure area isolated from the REE can include the secure runtime environment based on a secure OS e.g. a trusted OS .

As shown in both the TEE and the REE can run on top of a hardware platform . For example an ARM SoC can provide a hardware mechanism based on the TrustZone technology and its related monitor code. Furthermore the hardware mechanism can enforce the isolation between the secure runtime environment in TEE i.e. the secure world and the normal runtime environment in REE i.e. the normal world . Also the hardware mechanism enables the communication between the two worlds.

Alternatively both the TEE and the REE can be run on top of a hypervisor instead of running directly on top of the hardware mechanism . For example the hypervisor can host two virtual machines VMs with one VM dedicated to host the REE and another VM dedicated to host the TEE . Here in order to support the isolated secure execution the VM that hosts the TEE can be assigned with higher privileges over the VM that hosts the REE .

Furthermore the SoC can provide a root of trust that is bound to a secure boot mechanism e.g. based on a boot ROM . The root of trust on a SoC guarantees that the code in a TEE is genuine and that only authorized code can be executed in the TEE .

As shown in the TEE environment allows one or more trusted application TAs to run on top of the trusted OS e.g. via a TEE internal application programming interface API . The trusted OS can leverage the security features present on the SoC and can execute the TAs in the TEE in a secure fashion.

The TAs may need to be signed by an authority such as an installation authority before being installed within the TEE . Depending on business models and business agreements the installation authority can be the owner of the device hosting the SoC the OEM or a third party.

Once the TAs are installed within the TEE the TAs can be stored in a secure file system SFS which is managed by the TEE . Furthermore the TA can be accessed from the SFS each time when the TA is required. Thus the TEE can provide secure storage for the TAs since the SFS guarantees confidentiality and integrity of the data stored in it.

Also as shown in the TEE can expose a set of interfaces such as the TEE client API and the TEE functional API in the REE in order to provide security services to various client applications in the REE . Additionally the TEE allows the client applications in the REE and the trusted applications to use a shared memory for communicating large amounts of data quickly and efficiently.

Since the authorization tokens are bound to a device instead of a user of the device the authorization tokens may remain valid even after the device has already been passed or sold to another user or after the device has been refurbished.

The authorized on device operations are preferable to be bound to a user. For example the authorized on device operations might have been paid and may not be transferable among the users. There may be security concerns if the authorization tokens remains valid after the device change hands since the authorization tokens can be intercepted and stored for a replay.

Furthermore various counter values can be used for addressing the security concerns that relate to using the authorization tokens . The system can compare a counter in an authorization token which is immutable to the counter in the on device authorizing entity . The system may consider authorization token is valid only if the counter in the authorization tokens is greater that the counter in the on device authorizing entity . Then the system can update the counter in the on device authorizing entity with the value from the counter in the authorization tokens to prevent the re use of this authorization token.

Additionally the authorization tokens may need to be used in the same order as they are generated. For example the reference counters maintained by the token issuer may become out of synchronization when a token is pre provisioned on a device to be used at a later time.

Also the above scheme does not allow for transferring the authorization tokens from one device to another device e.g. when the user changes devices.

Additionally the device can be based on a system on chip SoC architecture. The SoC architecture enables the device to execute code and to manipulate data in separate execution environments e.g. a trusted execution environment TEE .

In accordance with an embodiment of the invention the system can support binding the authorization tokens to the on device authorizing entity using a universally unique ID that is assigned to the user . One exemplary universally unique ID can be based on a random value RV . Also as shown in a unique ID can be shared between the token issuer and the authorizing on device entity i.e. as ID and ID respectively .

Furthermore the on device authorizing entity can verify the authorization token based on different criteria such as verifying a signature of the authorization tokens before granting the execution of one or more protected on device operations .

Additionally the verification of the authorization token can include the verification of the validity of the binding e.g. by comparing the unique ID contained in the authorization token with the unique ID assigned to the on device authorizing entity .

Thus the system can determine that the binding is valid when the unique ID contained in the authorization token matches the unique ID assigned to the on device authorizing entity . Otherwise the system may determine that the binding is invalid and the token issuer may be able to reissue a different authorization token that contains a different unique ID not shown which matches the unique ID assigned to the on device authorizing entity .

In accordance with an embodiment of the invention the system allows for the sharing of a unique ID i.e. ID and ID between the token issuer and an on device authorizing entity . For example the system can use a secure channel which is established between the token issuer and the on device authorizing entity for sharing different secrets including the unique ID and .

Additionally the token issuer can store the generated unique IDs which are assigned to different users in the backend server . Thus the system is able to easily transfer the authorization tokens from one device to another device. For example the token issuer can provision the unique ID which is assigned to the user to a new device after the user changes device or acquires an additional device.

In accordance with an embodiment of the invention the unique ID assigned to the on device authorizing entity may be erased after the device is refurbished. Also the binding between the authorization tokens and the on device authorizing entity may be broken as a result of the erasing of the unique ID . Thus the authorization tokens bound to the unique ID may no longer be valid on the device after the device is refurbished.

Furthermore upon a refurbishment of the device the on device authorizing entity may be recreated or re initialized. The system can generate a new unique ID and subsequently shares the new unique ID between the token issuer in the backend sever and the newly created authorizing on device entity on the device .

Additionally after a refurbishment of the device the system can avoid the replay of the authorization tokens that authorize the on device operations . Also the system allows for binding one or more authorization tokens to multiple devices of a single user and can overcome de synchronization issues related to the use of counters within the authorization tokens .

In accordance with an embodiment of the invention the system can enable and support various use cases which are base on the management of unique IDs.

For example the system supports the restoration of applications on a device after a reset by replaying the authorization tokens that is issued to the device in which case the unique ID is restored in the original device. Also the system supports the restoration transfer of applications from one device to a newly acquired device by replaying the authorization tokens issued to the former device in which case the unique ID is copied to the new device. Additionally the system can prevent the installation of applications by replaying the authorization tokens that are issued to a device after the device is refurbished in which case a different unique ID may have to be generated.

Furthermore the system allows for sharing applications among several devices that belong to the same user with the same universally unique ID. Also the system allows for sharing applications among a group of users e.g. an enterprise or a family . Here the different devices from the different users may be bound to the same ID that corresponds to the group in addition to each of their own IDs. Subsequently after a user leaves the group the system can remove the ID corresponding to the group from the device of the user who left the group. Thus the system can prevent any further unauthorized replay of the tokens that are issued to the group.

Additionally the system supports the restoration of applications which were previously installed on other devices on to a new device. Here the new device can be assigned with the unique IDs that were used in the former devices.

Many features of the present invention can be performed in using or with the assistance of hardware software firmware or combinations thereof. Consequently features of the present invention may be implemented using a processing system e.g. including one or more processors .

Features of the present invention can be implemented in using or with the assistance of a computer program product which is a storage medium media or computer readable medium media having instructions stored thereon in which can be used to program a processing system to perform any of the features presented herein. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

Stored on any one of the machine readable medium media features of the present invention can be incorporated in software and or firmware for controlling the hardware of a processing system and for enabling a processing system to interact with other mechanism utilizing the results of the present invention. Such software or firmware may include but is not limited to application code device drivers operating systems and execution environments containers.

Features of the invention may also be implemented in hardware using for example hardware components such as application specific integrated circuits ASICs . Implementation of the hardware state machine so as to perform the functions described herein will be apparent to persons skilled in the relevant art.

Additionally the present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail can be made therein without departing from the spirit and scope of the invention.

The present invention has been described above with the aid of functional building blocks illustrating the performance of specified functions and relationships thereof. The boundaries of these functional building blocks have often been arbitrarily defined herein for the convenience of the description. Alternate boundaries can be defined so long as the specified functions and relationships thereof are appropriately performed. Any such alternate boundaries are thus within the scope and spirit of the invention.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. The breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments. Many modifications and variations will be apparent to the practitioner skilled in the art. The modifications and variations include any relevant combination of the disclosed features. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

