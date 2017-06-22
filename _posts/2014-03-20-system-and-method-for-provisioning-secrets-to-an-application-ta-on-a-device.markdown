---

title: System and method for provisioning secrets to an application (TA) on a device
abstract: A system and method can support device management. An authorization entity can pass one or more secrets that are wrapped with a first key to a communication entity. Furthermore, the communication entity can use a second key to establish a secure channel with an application on a device, and pass the one or more secrets that are wrapped with the first key to the application on the device using the secure channel. Then, the device can use the first key to unwrap the received wrapped secret.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09331988&OS=09331988&RS=09331988
owner: ORACLE INTERNATIONAL CORPORATION
number: 09331988
owner_city: Redwood Shores
owner_country: US
publication_date: 20140320
---
This application is related to the following patent application s each of which is hereby incorporated by reference in its entirety 

U.S. Patent Application titled SYSTEM AND METHOD FOR SUPPORTING DERIVING SECRETS FROM A MASTER KEY BOUND TO AN APPLICATION ON A DEVICE application Ser. No. 14 220 988 filed Mar. 20 2014 and

U.S. Patent Application titled SYSTEM AND METHOD FOR UPDATING TRUSTED APPLICATION TA ON A DEVICE application Ser. No. 14 221 004 filed Mar. 20 2014.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention is generally related to computer systems and is particularly related to device management and security.

In the post personal computer PC era businesses often permit employees to bring various mobile devices such as smart phones tablets and laptops to their workplace. The employees can use those personally owned devices to access privileged company information and applications. The information technology industry has been evolving to promote the secure and interoperable deployment and management of software applications using secure chip technology e.g. based on the GlobalPlatform. This is the general area that embodiments of the invention are intended to address.

Described herein are systems and methods that can support device management. An authorization entity can pass one or more secrets that are wrapped with a first key to a communication entity. Furthermore the communication entity can use a second key to establish a secure channel with an application on a device and pass the one or more secrets that are wrapped with the first key to the application on the device using the secure channel. Then the device can use the first key to unwrap the received wrapped secret.

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

Furthermore the keys which are generated on the device can be passed to an authorization entity as the K KEK and the K SC via a hardware security module HSM . Thus the device can share the keys with the authorization entity in a secure manner at the manufacturing time.

Furthermore the device can have access to different device keys e.g. the K KEK and the K SC which are intrinsic to the device and or application . Additionally during the manufacturing time the device can share the device keys K KEK and K SC with an authorization entity in a secure manner as the K KEK and the K SC .

As shown in the authorization entity can wrap one or more secrets using a shared device key e.g. the K KEK before passing the wrapped secret to the communication entity . Additionally the authorization entity can pass another device key e.g. the K SC to the communication entity as the K SC .

Then the communication entity such as a trusted server manager TSM can use the received K SC i.e. same as the K SC on the device to establish a secure channel with the trusted application on the device .

Furthermore the communication entity can pass the wrapped secrets i.e. the secrets wrapped using K KEK to the trusted application on the device via the secure channel . Correspondingly the device can use the K KEK which is generated at the manufacturing time to unwrap the wrapped secrets in order to obtain the secrets .

In accordance with an embodiment of the invention the system can establish an inherent binding which may not rely on persistent data between the authorization entity server and the device for provisioning the secrets to the application on the device in the field. Additionally the authorization entity can use the communication entity which can be a third party entity to communicate secrets to the device without having to divulge the secrets that may need to be provisioned.

Thus the system permits the authorization entity to deal with the secrets without a need for dealing with the communication with the device . As a result using the system a business can achieve shorted time to market by not having to concern about communication features.

Many features of the present invention can be performed in using or with the assistance of hardware software firmware or combinations thereof. Consequently features of the present invention may be implemented using a processing system e.g. including one or more processors .

Features of the present invention can be implemented in using or with the assistance of a computer program product which is a storage medium media or computer readable medium media having instructions stored thereon in which can be used to program a processing system to perform any of the features presented herein. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

Stored on any one of the machine readable medium media features of the present invention can be incorporated in software and or firmware for controlling the hardware of a processing system and for enabling a processing system to interact with other mechanism utilizing the results of the present invention. Such software or firmware may include but is not limited to application code device drivers operating systems and execution environments containers.

Features of the invention may also be implemented in hardware using for example hardware components such as application specific integrated circuits ASICs . Implementation of the hardware state machine so as to perform the functions described herein will be apparent to persons skilled in the relevant art.

Additionally the present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail can be made therein without departing from the spirit and scope of the invention.

The present invention has been described above with the aid of functional building blocks illustrating the performance of specified functions and relationships thereof. The boundaries of these functional building blocks have often been arbitrarily defined herein for the convenience of the description. Alternate boundaries can be defined so long as the specified functions and relationships thereof are appropriately performed. Any such alternate boundaries are thus within the scope and spirit of the invention.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. The breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments. Many modifications and variations will be apparent to the practitioner skilled in the art. The modifications and variations include any relevant combination of the disclosed features. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

