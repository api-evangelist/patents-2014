---

title: Nonvolatile memory system, system including the same, and method of adaptively adjusting user storage region in the same
abstract: A method is for adaptively adjusting a user storage region in an entire storage region of a nonvolatile memory system. The method includes a host transmitting a user region information request command to the nonvolatile memory system, the nonvolatile memory system transmitting user region information to the host, the host changing the user region information, the host transmitting a user region information setting command to the nonvolatile memory system, and the nonvolatile memory system controlling a size of the user storage region in response to the user region information setting command.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09460006&OS=09460006&RS=09460006
owner: Samsung Electronics Co., Ltd.
number: 09460006
owner_city: Suwon-si, Gyeonggi-do
owner_country: KR
publication_date: 20140313
---
A claim of priority under 35 U.S.C. 119 a is made to Korean Patent Application No. 10 2013 0028311 filed on Mar. 15 2013 the disclosure of which is hereby incorporated by reference in its entirety.

Embodiments of the inventive concept relate to nonvolatile memory systems and more particularly embodiments of the inventive concept relate to nonvolatile memory systems for controlling the size of a user storage region therein based on changed user region information and to methods of adaptively adjusting a user storage region in the nonvolatile memory system.

Flash memory is widely used in a variety of different nonvolatile memory applications. Some examples include universal serial bus USB drives digital cameras cellular phones smart phones tablet personal computers PCs memory cards and solid state drives SSDs .

Generally a flash memory device is configured to include a plurality of memory blocks and each of the blocks includes a plurality of pages. Each page includes a plurality of memory cells typically connected to a same word line. Each of the memory cells may be implemented as a single level cell SLC which stores a single bit per cell or a multi level cell MLC which stores two or more bits per cell. A program operation is performed on a page by page basis while an erase operation is performed on a block by block basis.

The blocks contained in a flash memory device may be designated in advance to define a user storage region of the device that is available to a user to store data and to read data there from and a nonuser storage region of the device that is unavailable to the user. The size of the user storage region and the size of the nonuser storage region are fixed during fabrication by the manufacturer of the flash memory device.

According to some embodiments of the inventive concept there is provided a method of adaptively adjusting a user storage region in an entire storage region of a nonvolatile memory system. The method includes a host transmitting a user region information request command to the nonvolatile memory system the nonvolatile memory system transmitting user region information to the host the host changing the user region information the host transmitting a user region information setting command to the nonvolatile memory system and the nonvolatile memory system controlling a size of the user storage region in response to the user region information setting command.

The user region information request command and the user region information setting command may be vendor specific commands.

The user region information may be indicative of at least one of a ratio of a capacity of a nonuser storage region to a capacity of the user storage region a ratio of the capacity of the user storage region to a total storage capacity of the nonvolatile memory system a ratio of the capacity of the nonuser storage region to the total storage capacity the capacity of the user storage region and the capacity of the nonuser storage region.

The method may further include the host updating logical addresses corresponding to a nonuser storage region according to the changed user region information.

The nonvolatile memory system may change an address mapping table according to the changed user region information.

The host changing the user region information may include the host displaying the user region information of the nonvolatile memory system at a user s request the host receiving a request to change the user region information of the nonvolatile memory system from the user and the host changing the user region information in response to the user s request.

Alternatively the host changing the user region information may include the host selecting an entry from a table which stores a plurality of entries for the user region information with respect to a predetermined management parameter as the changed user region information. Here the predetermined management parameter may include sequential read performance random read performance sequential write performance random write performance maximum latency lifespan or data write capacity.

As another alternative the host changing the user region information may include the host selecting one user region information item from a table which stores a plurality of predetermined user region information items as the changed user region information.

The one user region information item may be adaptively selected from the table according to at least one of an access frequency to the nonvolatile memory system data usage with respect to the nonvolatile memory system and a data write capacity with respect to the nonvolatile memory system.

The nonvolatile memory system may be a flash based storage device such as an embedded MMC eMMC a universal flash storage UFS or a solid state drive SSD including a flash memory controller.

According to other embodiments of the inventive concept there is provided a nonvolatile memory system including a nonvolatile memory device comprising a user storage region and a nonuser storage region and an address mapping module configured to transmit user region information to a host in response to a user region information request command received from the host and to control a size of the user storage region according to changed user region information received from the host.

The address mapping module may change an address mapping table according to the changed user region information.

The user region information may include at least one of a ratio of a capacity of a nonuser storage region to a capacity of the user storage region a ratio of the capacity of the user storage region to a total storage capacity of the nonvolatile memory system a ratio of the capacity of the nonuser storage region to the total storage capacity the capacity of the user storage region and the capacity of the nonuser storage region.

The nonvolatile memory system may be a flash based storage device such as an eMMC a UFS or an SSD including a flash memory controller.

According to further embodiments of the inventive concept there is provided a computing system including a host configured to monitor input output data of a file server and a nonvolatile memory system including an entire storage region and to configured to transmit user region information to the host the user region information indicative of a user storage region contained in the entire storage region. The host is further configured to change the user region information based on at least one of a monitoring result and the user region information and to transmit corresponding changed user region information to the nonvolatile memory system and the nonvolatile memory system is further configured to control a size of the user storage region contained in the entire storage region in response to the changed user region information.

The nonvolatile memory system may further include an address mapping module configured to transmit the user region information to a host and the address mapping module may change an address mapping table according to the changed user region information.

The user region information may indicative of at least one of a ratio of a capacity of a nonuser storage region to a capacity of the user storage region a ratio of the capacity of the user storage region to a total storage capacity of the nonvolatile memory system a ratio of the capacity of the nonuser storage region to the total storage capacity the capacity of the user storage region and the capacity of the nonuser storage region.

The nonvolatile memory system is a flash based storage device comprising a flash memory controller and the nonvolatile memory system is one selected from the group consisting of an embedded MMC eMMC a universal flash storage UFS and a solid state drive SSD .

The inventive concept now will be described more fully hereinafter with reference to the accompanying drawings in which embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like numbers refer to like elements throughout.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present. As used herein the term and or includes any and all combinations of one or more of the associated listed items and may be abbreviated as .

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are only used to distinguish one element from another. For example a first signal could be termed a second signal and similarly a second signal could be termed a first signal without departing from the teachings of the disclosure.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising or includes and or including when used in this specification specify the presence of stated features regions integers steps operations elements and or components but do not preclude the presence or addition of one or more other features regions integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and or the present application and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

Here the term module will be understood signify hardware computer program codes for executing particular function and operation or an electronic recording medium such as a processing circuit equipped with the computer program codes. In other words the module may indicate the functional and or structural combination between hardware for embodying the inventive concept and or software for driving the hardware.

In operation the host A may transmit a user region information request command CMD to the nonvolatile memory system . The nonvolatile memory system may transmit user region information URI to the host A in response to the user region information request command CMD.

The host A may change the user region information URI generate a user region information setting command CMD for setting changed user region information C URI in the nonvolatile memory system and transmit the changed user region information C URI and the user region information setting command CMD to the nonvolatile memory system . The operation of the host A or a host B in of generating the changed user region information C URI will be described later in detail with reference to . In other embodiments the host A may transmit the user region information setting command CMD containing the changed user region information C URI to the nonvolatile memory system .

The nonvolatile memory system may adjust the size of the user storage region allocated in the entire storage region in response to the user region information setting command CMD. In other words the nonvolatile memory system may change the size of the user storage region allocated in the entire storage region using the changed user region information C URI received from the host A.

The host A may also update a logic address space which corresponds to a nonuser storage region i.e. the entire storage region excluding the user storage region based on the changed user region information C URI.

The commands CMD and CMD may be generated during initialization of the electronic system A or may be generated in real time during operation of the electronic system A. The commands CMD and CMD may be vendor specific commands.

The physical addresses of the user storage region and the nonuser storage region forming the overall storage region of the nonvolatile memory system may be changed based on the changed user region information C URI. Therefore the host A is required to update the logical address sequence LSN corresponding to the physical addresses changed based on the changed user region information C URI. Referring to the host A may increase or decrease a logical address sequence LSN N corresponding to the nonuser storage region based on the changed user region information C URI.

Referring still to the host A may include a processor a memory and a host interface . The host A may as examples be an application processor or a mobile application processor.

The processor may control the operation of the memory and or the operation of the host interface through a bus . The processor may execute a program such as an operating system OS an application program or an application programming interface API which can perform an operation or function related to a method of adaptively controlling the user storage region in the entire storage region of the nonvolatile memory system according to one or more embodiments of the inventive concept.

The memory may be an operation memory that stores a program related to the method of adaptively controlling the user storage region in the overall storage region of the nonvolatile memory system . The memory may be implemented as a volatile memory device or a nonvolatile memory device. As examples in the case volatile memory the memory may be implemented using dynamic random access memory DRAM static RAM SRAM thyristor RAM T RAM zero capacitor RAM Z RAM or twin transistor RAM TTRAM . As other examples in the case of nonvolatile memory the memory may be implemented using electrically erasable programmable read only memory EEPROM flash memory magnetic RAM MRAM spin transfer torque MRAM STT MRAM conductive bridging RAM CBRAM ferroelectric RAM FeRAM phase change RAM PRAM resistive RAM RRAM nanotube RRAM polymer RAM PoRAM nano floating gate memory NFGM holographic memory molecular electronic memory device or insulator resistance change memory.

The host interface may exchange signals or data between the host A and the nonvolatile memory system . The host interface may be equipped with an interface protocol for this purpose. Examples of the interface protocol include a UHS UHS I or UHS II protocol a peripheral component interconnect express PCI E protocol an advanced technology attachment ATA protocol a serial ATA SATA protocol a parallel ATA PATA protocol or a serial attached SCSI SAS protocol. In other embodiments the interface protocol may be a protocol suitable for a universal serial bus USB a multi media card MMC enhanced small disk interface ESDI or integrated drive electronics IDE .

The nonvolatile memory system may include a memory controller and a nonvolatile memory device . As examples the nonvolatile memory system may be an embedded MMC eMMC a universal flash storage UFS a solid state drive SSD or a redundant array of independent disks or redundant array of inexpensive disks RAID . However the nonvolatile memory system is not restricted to these particular examples. For instance the nonvolatile memory system may be any flash based storage device including a flash memory controller.

The size of a user storage region in the overall storage region of the nonvolatile memory device may be adaptively controlled using the memory controller and more specifically an address mapping module according to the control of the host A. The nonvolatile memory device may be a flash memory device but is not restricted thereto. The nonvolatile memory device may as other examples be a PRAM device an MRAM device a ReRAM device or a FeRAM device. In the case where the nonvolatile memory device is the flash memory device the nonvolatile memory device may be a NAND flash memory device using floating gate technology or charge trap flash CTF technology. Memory cell transistors may be arranged in two or three dimensions in the nonvolatile memory device .

The entire storage region DSR may include a user storage region USR and a nonuser storage region NUSR. The user storage region USR may include a used storage region in which data has already been stored and a programmable free storage region.

Meta information used to manage the nonvolatile memory system and information about the features of the nonvolatile memory device or information about internal operations e.g. performance control merging wear leveling and garbage collection necessary for efficient management of the nonvolatile memory device may be stored in the nonuser storage region NUSR. In addition a signal e.g. a command or data output from the host A or a signal e.g. a command or data input to the host A may be temporarily stored in the nonuser storage region NUSR. Also the nonuser storage region NUSR may include a reserved region that is used to replace blocks having an error or a fault in the user storage region USR.

The size of the user storage region USR may be increased or decreased according to the changed user region information C URI. As the size of the user storage region USR is changed the size of the nonuser storage region NUSR may be decreased or increased.

The memory controller may control the overall operation of the nonvolatile memory system . For instance the memory controller may control exchange of signals e.g. commands or data between the host A and the nonvolatile memory system . The memory controller may include the address mapping module .

The address mapping module may transmit the user region information URI to the host A in response to the user region information request command CMD. The user region information URI may include at least one of a ratio of the capacity of the nonuser storage region NUSR to the capacity of the user storage region USR a ratio of the capacity of the user storage region USR to the capacity of the entire storage region DSR or the total capacity of the nonvolatile memory system and more specifically of the nonvolatile memory device a ratio of the capacity of the nonuser storage region NUSR to the capacity of the entire storage region DSR the capacity of the user storage region USR and the capacity of the nonuser storage region NUSR.

The address mapping module may control the size of the user storage region USR in the entire storage region DSR of the nonvolatile memory device based on the changed user region information C URI received from the host A in response to the user region information setting command CMD. As shown in the address mapping module may increase or decrease the user storage region USR according to the changed user region information C URI.

The address mapping module may map logical addresses and physical addresses of the nonvolatile memory device and more particularly of the memory cell array using an address mapping table . The address mapping module may change the address mapping table according to the changed user region information C URI. The operation of the address mapping module controlling the size of the user storage region USR and changing the address mapping table according to the changed user region information C URI will be described in detail with reference to .

Here as discussed previously the term module signifies hardware that can execute the function and the operation corresponding to a name herein described and or computer program codes for executing particular function and operation and or an electronic recording medium such as a processor equipped with the computer program codes. In other words the module may indicate the functional and or structural combination between hardware for embodying the inventive concept and or software for driving the hardware. The module may be referred to as a device.

The address mapping module may be implemented in a flash translation layer FTL . The FTL may be software or a software layer for managing the nonvolatile memory system .

The host B may transmit the user region information request command CMD to the nonvolatile memory system . The nonvolatile memory system may transmit the user region information URI to the host B in response to the user region information request command CMD.

The host B may display the user region information URI on the display at a user s request received through the input device . The host B may receive a request to change the user region information URI input by the user through the input device change the user region information URI in response to the user s request generate the user region information setting command CMD for setting the changed user region information C URI in the nonvolatile memory system and transmit the changed user region information C URI and the user region information setting command CMD to the nonvolatile memory system . The host B may transmit the user region information setting command CMD containing the changed user region information C URI to the nonvolatile memory system .

The nonvolatile memory system may control the size of the user storage region USR in its entire storage region DSR in response to the user region information setting command CMD. In other words the nonvolatile memory system may change the size of the user storage region USR in the entire storage region DSR using the changed user region information C URI received from the host B.

The host B may also update the logical address sequence LSN N corresponding to the nonuser storage region NUSR in the entire storage region DSR according to the changed user region information C URI.

The commands CMD and CMD may be generated curing the initialization of the electronic system B or may be generated in real time during the operation of the electronic system B.

The structure and operations of the elements and included in the host B illustrated in may be substantially the same as those of the elements and included in the host A illustrated in . Also the structure and operations of the nonvolatile memory system included in the electronic system B illustrated in may be substantially the same as those of the nonvolatile memory system included in the electronic system A illustrated in .

In detail the host may select as the changed user region information C URI an entry ENT ENT ENT ENT or ENT from a table URI T that stores a plurality of the entries ENT through ENT for user region information URI with respect to predetermined management parameters P and P. Data Value through Value in the user region information URI in the table URI T may be data or values corresponding to one of the ratios described above.

The management parameter P or P may include sequential read performance random read performance sequential write performance random write performance maximum latency lifespan or data write capacity. The data Value through Value in the user region information URI with respect to the management parameter P or P in the table URI T may be obtained through an experiment.

Consequently the host may control the nonvolatile memory system to change the size of the user storage region USR according to the changed user region information C URI thereby inhibiting a decrease in performance and durability of the nonvolatile memory system .

In detail the host may select as the changed user region information C URI a user region information item URI URI URI URI or URI from a table URI T that stores a plurality of the user region information items URI through URI. The user region information items URI through URI may include data or values corresponding to one of the ratios described above or may be data or values randomly set for one of the ratios.

The host may adaptively select one of the user region information items URI through URI in the table URI T as the changed user region information C URI according to at least one of an access frequency data usage and data write capacity with respect to the nonvolatile memory system . Consequently the host may control the nonvolatile memory system to change the size of the user storage region USR according to the changed user region information C URI thereby inhibiting a degradation in performance and durability of the nonvolatile memory system .

Referring to the address mapping module may decrease the user storage region USR in the entire storage region DSR according to the changed user region information C URI.

When there is no data stored in a region RR shifted from the user storage region USR to the nonuser storage region NUSR the address mapping module may map logical addresses based on physical addresses i.e. 4 5 10 11 16 17 22 and 23 of the region RR in CASE. At this time the address mapping table may be changed into TABLE shown in by the address mapping module .

When there is data stored in a partial region R of the region RR shifted from the user storage region USR to the nonuser storage region NUSR the address mapping module may allocate a new region R having no data stored therein to the region RR and change the address mapping table based on physical addresses i.e. 14 15 20 and 21 of the allocated region R in CASE. The address mapping table may be changed to TABLE shown in by the address mapping module .

The host A may change the user region information URI and transmit the user region information setting command CMD for setting the changed user region information C URI in the nonvolatile memory system to the nonvolatile memory system in operation S. The nonvolatile memory system may control the size of the user storage region USR in its entire storage region DSR in response to the user region information setting command CMD in operation S.

Referring to and the host B may transmit the user region information request command CMD to the nonvolatile memory system in operation S. The host B may receive the user region information URI from the nonvolatile memory system in operation S.

The host B may display the user region information URI on the display at a user s request input through the input device in operation S. The host B may receive a request to change the user region information URI from the user through the input device in operation S.

The host B may change the user region information URI at the user s request and transmit the user region information setting command CMD for setting the changed user region information C URI in the nonvolatile memory system to the nonvolatile memory system in operation S. The nonvolatile memory system may control the size of the user storage region USR in its entire storage region DSR in response to the user region information setting command CMD in operation S.

Referring to and the host A may transmit the user region information request command CMD to the nonvolatile memory system in operation S. The host A may receive the user region information URI from the nonvolatile memory system in operation S.

The host A may select one entry ENT ENT ENT ENT or ENT from the table URI T as the changed user region information C URI and transmit the user region information setting command CMD for setting the changed user region information C URI in the nonvolatile memory system to the nonvolatile memory system in operation S. The nonvolatile memory system may control the size of the user storage region USR in its entire storage region DSR in response to the user region information setting command CMD in operation S.

Referring to and the host A may transmit the user region information request command CMD to the nonvolatile memory system in operation S. The host A may receive the user region information URI from the nonvolatile memory system in operation S.

The host A may select one item URI URI URI URI or URI from the table URI T storing a plurality of the predetermined user region information items URI through URI as the changed user region information C URI and transmit the user region information setting command CMD for setting the changed user region information C URI in the nonvolatile memory system to the nonvolatile memory system in operation S. The nonvolatile memory system may control the size of the user storage region USR in its entire storage region DSR in response to the user region information setting command CMD in operation S.

The card interface may be a secure digital SD card interface or an MMC interface but the inventive concept is not restricted to the current embodiments. The card interface may interface the host and the memory controller for data exchange according to a protocol of the host .

Alternatively the card interface may support a USB protocol and an interchip IC USB protocol. Here the card interface may indicate a hardware supporting a protocol used by the host software installed in the hardware or a signal transmission mode.

The memory controller may be a NAND flash controller and the nonvolatile memory device may include a plurality of NAND flash memory elements through and through . Although the nonvolatile memory system having a 2 channel 4 bank hardware structure is illustrated in the inventive concept is not restricted thereto. The NAND flash memory elements through and through may each implemented as a NAND flash chip.

The memory controller is connected with the nonvolatile memory device through two channels CHANNEL and CHANNEL and each of the channels CHANNEL and CHANNEL may be connected to four flash memory elements. For instance the first channel CHANNEL may be connected to four NAND flash memory elements through and the second channel CHANNEL may be connected to four NAND flash memory elements through . The NAND flash memory elements through or through connected to the same channel may share an input output I O bus and a control signal. It will be apparent that the number of channels and the number of banks can be changed.

The memory controller may control the channels CHANNEL and CHANNEL completely independently from each other. In other words the memory controller may input a write command to two flash chips e.g. and at the same time. Accordingly a write operation is performed on two flash chips and at the same time so that the nonvolatile memory system increases the write performance.

Each of the NAND flash memory elements e.g. through connected to one channel may be selected using a different CE signal CE CE CE or CE. The input of a command and data transmission cannot be performed simultaneously with respect to the NAND flash memory elements through connected to one channel. In other words a command input time and a data transmission time for each of the NAND flash memory elements through connected to one channel cannot overlap those for the others of the NAND flash memory elements through but page program operations of the respective NAND flash memory elements through connected to one channel may overlap each other.

The nonvolatile memory system may include a plurality of memory devices the memory controller controlling the data processing operation of the memory devices a volatile memory device such as DRAM and a buffer manager controlling data transmitted between the memory controller and the host to be stored in the volatile memory device .

Each of the memory systems through may be the system illustrated in . The memory systems through may form a RAID array. The electronic system F may be implemented as a PC or an SSD.

During a program operation the RAID controller may transmit program data output from the host to at least one of the memory systems through according to a RAID level in response to a program command received from the host . During a read operation the RAID controller may transmit to the host data read from at least one of the memory systems through in response to a read command received from the host .

Except for a monitoring module the function and structure of the host C may be substantially the same as those of the host A illustrated in . The host C may also include the input device and the display illustrated in . At this time the structure and function of the host C may be substantially the same as those of the host B illustrated in . The structure and function of the nonvolatile memory system illustrated in may be substantially the same as those of the nonvolatile memory system illustrated in .

The file server and the clients through perform data communication through a wired or wireless network . The wired or wireless network may be an internet or a mobile communication network. The file server may function as a data source that provides the host C with data.

When the monitoring module transmits a monitoring result to the processor the processor may estimate the amount of data to be transmitted to the nonvolatile memory system based on the monitoring result in operation S. The processor may generate user region information based on an estimation result and transmit the user region information as changed user region information to the nonvolatile memory system in operation S.

Referring to the host C may generate the changed user region information C URI based on the estimation result and or the user region information URI. The host C may analyze at least one of a pattern of data to be transmitted to the nonvolatile memory system the amount of the data a start address of the data and the estimation result and may generate the changed user region information C URI based on an analysis result and the user region information URI. The nonvolatile memory system may control the size of the user storage region USR according to the changed user region information C URI in operation S.

As described above according to one or more embodiments of the inventive concept a host controls the size of a user storage region contained in an entire storage region of a nonvolatile memory system using user region information of the nonvolatile memory system. The nonvolatile memory system changes the size of the user storage region according to changed user region information received from the host thereby inhibiting deterioration of system performance and durability.

While the inventive concept has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in forms and details may be made therein without departing from the spirit and scope of the inventive concept as defined by the following claims.

