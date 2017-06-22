---

title: Storage control apparatus, storage control method, and computer-readable recording medium having stored storage control program
abstract: A storage apparatus includes a processing unit that functions a SAN OS which performs SAN control and a NAS OS which performs NAS control to be operated on a virtualized OS, an inter-OS communication unit that transmits and receives data between the NAS OS and the SAN OS, a transmission controller that transmits a NAS input/output request received in the NAS OS to the SAN OS through the inter-OS communication unit, and a NAS request processing unit that processes the NAS input/output request received from the transmission controller in the SAN OS. With this configuration, the NAS and the SAN can be efficiently integrated in a storage apparatus.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09483211&OS=09483211&RS=09483211
owner: FUJITSU LIMITED
number: 09483211
owner_city: Kawasaki
owner_country: JP
publication_date: 20140829
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent application No. 2013 202311 filed on Sep. 27 2013 the entire contents of which are incorporated herein by reference.

The embodiments discussed herein are directed to a storage control apparatus a storage control method and a storage control program.

The NAS which is connected to the existing Internet registered trademark network is simple in management compared to the SAN but degraded in performance and causes capacity insufficiency in many cases. On the other hand the SAN generally operates at high speed compared to the NAS and can store a large amount of data but it is expensive in price.

In order to improve the efficiency in data storage and the reduction in cost by combining advantages of the NAS and the SAN a method of integrating the SAN and the NAS is known and specifically the SAN and the NAS are integrated by employing a NAS gateway.

However the storage system in the related art is provided with a server machine for implementing a NAS gateway function in order to integrate the SAN and the NAS. Therefore there is a problem in that a cost for configuring the system increases.

Further the network storage system in which the NAS gateway is used to integrate the SAN and the NAS as described above it is necessary to perform the setting of the SAN and the setting of the NAS separately. Therefore there is also a problem in that a workload of operations by a manager increases.

According to an aspect of the embodiments a storage control apparatus includes a processing unit that functions a SAN operating system which performs SAN control and a NAS operating system OS which performs NAS control to be operated on a virtualized operating system an inter OS communication unit that transmits and receives data between the NAS operating system and the SAN operating system a transmission controller that transmits a NAS input output request received in the NAS operating system to the SAN operating system through the inter OS communication unit and a NAS request processing unit that processes the NAS input output request received from the transmission controller in the SAN operating system.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention.

Hereinafter embodiments of a storage control apparatus a storage control method and a storage control program will be described with reference to the drawings. However the following embodiments are given as merely exemplary embodiments and it is not intended to exclude various modifications and various technical applications which are not specified in the embodiments. In other words the embodiments can be implemented in various forms within a scope not departing from the spirit thereof. Further there is no purpose of exclusively including only the components in the drawings but other functions can be included.

The storage apparatus virtualizes storage devices which are stored in a drive enclosure DE to set up a virtual storage environment. Then the storage apparatus provides a virtual volume to a host apparatus not illustrated which is an upper level device.

The storage apparatus is communicably connected to one or more host apparatuses. The host apparatus and the storage apparatus are connected through communication adapters CAs and which will be described below.

The host apparatus for example is an information processing apparatus which has a server function and transmits receives commands on a NAS and a SAN with respect to the storage apparatus . The host apparatus for example transmits a disk access command such as read write in the NAS with respect to the storage apparatus in order to read write data from to the volume provided by the storage apparatus .

Then the storage apparatus performs a process such as reading writing of data on an actual storage corresponding to the volume according to an input output request for example a read command and a write command which is issued from the host apparatus to the volume. In addition the input output request from the host apparatus may be referred to as an I O command or an I O request.

As illustrated in the storage apparatus includes a plurality two in the embodiment of controller modules CM and and one or more one in the example illustrated in drive enclosures .

The drive enclosure is mountable with one or more four in the example illustrated in storage devices physical disks and provides the storage areas actual volume actual storage of these storage devices to the storage apparatus .

For example the drive enclosure includes a plural stages of slots not illustrated and the capacity of the actual volume can be changed at any time by inserting the storage devices such as a hard disk drive HDD and a solid state drive SSD into these slots. Further redundant arrays of inexpensive disks RAID may be formed using the plurality of storage devices .

The drive enclosure is connected to device adapters DAs and of the CM and DAs and of the CM . Therefore any of the CMs and can access the drive enclosure to perform the writing reading of data. In other words the respective CMs and are connected to the storage devices of the drive enclosure so that the access paths to the storage devices are redundantly formed.

The CMs and are controllers storage control apparatuses which control the operations in the storage apparatus and perform various types of control such as access control to the storage device of the drive enclosure according to the I O command transmitted from the host apparatus. Further the CMs and have substantially the same configuration. Hereinafter as a symbol for indicating the CM when there is a need to specify one of a plurality of CMs the symbols and will be used and when any CM is indicated the symbol will be used. Further the CM may be represented by CM 1 and the CM by CM 2.

Further in the drawings the same symbols as those described above indicate the identical or similar portions and thus the descriptions thereof will not be repeated.

The CMs and are configured in pair and the CM performs various types of control under normal conditions as a primary CM. However when the primary CM fails in its operation the secondary CM takes over the operation from the primary CM

The CMs and each are connected to the host apparatus through the CAs and . Then the CMs and receive commands such as read write which are transmitted from the host apparatus and performs control on the storage device through the DA or the like. Further the CMs and are connected to each other through an interface not illustrated such as PCI Express.

As illustrated in the CM includes the CAs and and a plurality two in the example illustrated in of the DAs and and further includes a central processing unit CPU a memory an SSD and an IOC .

The CAs and receive data transmitted from the host apparatus and the like or transmits data out of the CM to the host apparatus and the like. In other words the CAs and controls data input output I O with respect to an external apparatus such as the host apparatus.

The CA is a network adapter which is communicably connected to the host apparatus through the NAS for example there is a local area network LAN interface and the like.

The CM is connected to the host apparatus and the like by the NAS through a communication line not illustrated connected to the CA and performs an I O command reception and a data transmission reception. In the example illustrated in each of the CMs and includes two CAs and .

The CA is a network adaptor which is communicably connected to the host apparatus through the SAN for example there is an iSCSI interface and a fibre channel FC interface.

The CMs are connected to the host apparatus and the like by the SAN through the communication line not illustrated connected to the CA and perform the I O command reception and the data transmission reception. In the example illustrated in each of the CMs and includes one CA .

The DA is an interface which is communicably connected to the drive enclosure the storage device and the like. The DA is connected to the storage devices of the drive enclosure and each CM performs the access control to the storage devices based on the I O command received from the host apparatus.

The CM performs data write read on the storage device through the DA . Further in the example illustrated in each of the CMs and includes two DAs and . Then in each of the CMs and each DA is connected to the drive enclosure .

With this configuration any one of the CMs and can perform data write read on the storage device of the drive enclosure .

The memory is a storage device which temporarily stores various types of data and a program and includes a memory area and a cache area which are not illustrated. The cache area temporarily stores data received from the host apparatus and data to be transmitted to the host apparatus. The memory area is used to temporarily store and develop the data and the program when the CPU executes the program.

The input output controller IOC is a control device which controls data transmission in the CM and for example realizes DMA Direct Memory Access transfer in which the data stored in the memory is transferred without passing through the CPU .

The CPU is a processing device which performs various types of control and calculations and for example there is a multi core processor multi CPU . The CPU executes the OS and the program stored in the SSD and the like thereby realizing various functions.

The CPU executes a hypervisor which is a virtualization OS and executes a plurality of virtual machines VMs on the hypervisor thereby causing a plurality of OSs to be executed. Hereinafter an OS executed on the hypervisor may be referred to as a guest OS or a GOS.

In addition a plurality of CPUs may be provided and the hypervisor may be performed on the plurality of CPUs .

The SAN OS is an OS for performing SAN control and includes a kernel and a function firmware . Various types of existing OSs can be used as the SAN OS but VxWorks registered trademark made by Wind River will be exemplified in the embodiment.

The NAS OS is an OS for performing NAS control and includes a kernel and a function firmware . Various types of existing OSs can be used as the NAS OS but Linux registered trademark will be exemplified in the embodiment.

Then the CPU functions as the hypervisor the SAN OS and the NAS OS by executing a storage control program.

In addition a program storage control program for realizing the functions as the hypervisor the SAN OS and the NAS OS for example is provided in types of being recorded in a computer readable recording medium such as a flexible disk a CD such as a CD ROM a CD R and a CD RW a DVD such as a DVD ROM a DVD RAM a DVD R a DVD R a DVD RW a DVD RW and an HD DVD a Blu ray disk a magnetic disk an optical disk a magneto optical disk and the like. In this case the computer reads the program from the recording medium and transfers and stores the program into an inner storage unit or an external storage unit for use. While being stored in a storage apparatus recording medium such as the magnetic disk the optical disk and the magneto optical disk the program may be provided to a processor from the storage apparatus through a communication path. Further the program may be recorded in a storage device recording medium for example a magnet disk an optical disk a magneto optical disk and the like and provided to the computer from the storage device through a communication path.

When the functions as the hypervisor the SAN OS and the NAS OS are realized the program stored in an internal storage device the memory and the SSD in the embodiment is executed by a microprocessor the CPU in the embodiment of the computer. At this time the program stored in the recording medium may be read by the computer for execution.

As illustrated in the NAS OS includes Samba NFS server software a file system an OS system controller and an SCSI driver group .

On the other hand the SAN OS includes an intelligent CA agent . Further an inter GOS communication unit is provided to connect the NAS OS and the SAN OS .

The Samba NFS server software is a file system based application which uses Samba or NFS to receive the I O request of the NAS received from the host apparatus and transfers the request to the file system .

The file system for example is a virtual file system VFS or a file system such as ext3 which converts the I O request received from the Samba NFS server software into an API of every relative local file system and transfers the API to the SCSI driver group .

The OS system controller performs various types of normal control as the NAS OS and for example issues an event request such as additional request of the device to the SCSI driver group an LLD .

As illustrated in the SCSI driver group has a layered architecture which is configured of 3 layers such as an upper level driver ULD upper level layer a middle level driver MLD middle level layer and a lower level driver LLD lower level layer .

In the ULD four types of drivers such as an SD an SR an ST and an SG are prepared and these drivers are differently used depending on the types of SCSI devices. Herein the SD is used at the time of access to a HDD and has a block type. The SR is used at the time of access to a CD ROM and has a block type. The ST is used at the time of access to a tape device and has a block type. The SG is a pseudo host adapter which is used without a host bus adapter hardware and has a character type.

The MLD provides an SCSI driver API Application Programming Interface library for the ULD and the LLD . The SCSI driver reads the MLD to perform control.

The LLD includes an actual driver corresponding to a physical interface which is applicable to the SCSI and corresponds to the host bus adapter. The LLD is a driver layer which controls a hardware interface and the driver to be used is unique for every device. For example as illustrated in the LLD includes an iSCSI driver and an FC driver . Furthermore in the storage apparatus the LLD includes an intelligent SCSI driver . In addition an existing Linux driver may be used for the ULD and the MLD .

As illustrated in in the NAS OS the I O request from the host apparatus reaches the intelligent SCSI driver of the LLD through the Samba NFS server software the file system the ULD and the MLD .

The intelligent SCSI driver receives the I O request from the file system and transmits the I O request to the intelligent CA agent in the SAN OS through the inter GOS communication unit to be described below. In addition the I O request receives the request in a format of an SCSI command in the intelligent SCSI driver .

Further the intelligent SCSI driver receives a response result to the transmitted SCSI command from the intelligent CA agent and informs the ULD of the SCSI driver layer about the received result.

When receiving the I O request of the NAS from the host apparatus and the like the intelligent SCSI driver suppresses a direct access to a SAN dedicated volume see and transmits the I O request of the NAS to the SAN OS by inter guest communication through the inter GOS communication unit to be described.

Furthermore the intelligent SCSI driver processes the event request for the device which is received from the OS system controller of the NAS OS . For example in a case where the event request is a request for adding a device the intelligent SCSI driver receives the addition request and adds defines a device file in the folder dev .

The inter GOS communication unit transmits or receives data between the guest OSs. In the storage apparatus the data is transmitted or received between the NAS OS and the SAN OS . Specifically the I O request SCSI command received in the NAS OS is transferred from the intelligent SCSI driver to the intelligent CA agent of the SAN OS .

Further the inter GOS communication driver transfers a response result to the I O request from the intelligent CA agent of the SAN OS to the intelligent SCSI driver of the NAS OS .

The inter GOS communication unit controls communication between the guest OSs through the inter GOS communication driver which is provided in each of the SAN OS and the NAS OS .

Further the inter guest OS communication uses a shared memory see shared between the NAS OS and the SAN OS and an interrupt of an inter processor interrupt IPI scheme. The IPI controls an interrupt between the guest OSs through the hypervisor .

In other words the inter GOS communication driver of the guest OS on the data transmission side writes information data indicating a request to transmit data to a predetermined area for example a control area for transferring a request of the shared memory . Then an interrupt is informed to the inter GOS communication driver of the guest OS at the transmission destination using the IPI function through the hypervisor . The inter GOS communication driver which receives the interrupt reads the area in the shared memory to make preparation for the reception of transmission data. Therefore the data transmission reception communication between the guest OSs is completed.

Further in actual data transmission data transmission between the cache area and each guest OS area in the shared memory is realized by the DMA transfer function of the IOC described above. REQUEST RESPONSE as exchange of control information for transmitting and receiving the data are realized using the shared memory and the interrupt of the IPI scheme.

In the example illustrated in a thick broken line represents an IPI notification from the NAS OS to the SAN OS and a thick solid line represents the IPI notification from the SAN OS to the NAS OS .

In the example illustrated in in the NAS OS the OS system controller and the intelligent SCSI driver instruct the inter GOS communication driver to transmit data and receive a response from the inter GOS communication driver . On the other hand in the SAN OS an intelligent CA agent and a system controller instruct the inter GOS communication driver to transmit data and receive a response from the inter GOS communication driver .

Further when the data is transmitted from the SAN OS to the NAS OS the hypervisor handles an interrupt by the IPI and informs the NAS OS . However when the data is transmitted from the NAS OS to the SAN OS a direct interruption scheme is used to directly inform the SAN OS without passing through the hypervisor as denoted by arrows A and A in . The direct interrupt is an interrupt notification between the guest OSs without passing through the hypervisor .

With this configuration it is possible to speed up the data transmission inter guest communication from the NAS OS to the SAN OS .

As illustrated in the NAS OS includes the SCSI driver layer the file system the Samba NFS server software a SCSI application and a network layer .

The network layer controls communication in a network layer for example receives the I O request of the NAS from the host apparatus.

The SCSI driver layer is a driver group for controlling the SCSI devices and corresponds to the SCSI driver group illustrated in .

In the SCSI driver layer an SCSI disk driver corresponds to the ULD illustrated in and a common service corresponds to the MLD .

Further the SCSI driver layer includes the iSCSI driver and the FC driver which correspond to the above mentioned LLD . The functions of the respective components as the NAS OS are well known in Linux and the like for example and thus the detailed descriptions thereof will not be made.

Then in the storage apparatus the LLD of the SCSI driver layer includes the above mentioned intelligent SCSI driver .

As illustrated in the SAN OS includes an intelligent CA driver a target driver a CA thread a basic control a backend control an FC CA driver an iSCSI CA driver and a SAS CA driver .

In addition among these components the functions as the target driver the CA thread the basic control the backend control the FC CA driver the iSCSI CA driver and the SAS CA driver are well known in the SAN OS such as VxWorks and thus the descriptions thereof will not be made.

The intelligent CA driver is a virtual driver layer of the NAS which is added to a channel adapter driver layer of the SAN control in the SAN OS . The intelligent CA driver performs the I O request and a response transmission reception of the NAS with respect to the NAS OS . The intelligent CA driver includes an SCSI command queue and an SCSI status queue .

For example the I O command received from the NAS OS is stored in the SCSI command queue and status information and the like as a response to the NAS OS is stored in the SCSI status queue .

The target driver includes the intelligent CA agent . The intelligent CA agent is a NAS dedicated function which is added to the target driver and is a block which controls the I O request received from the NAS OS through the inter guest OSs communication. The intelligent CA agent may be called a NAS control block . The function of the intelligent CA agent the NAS control block will be described below.

The CA thread includes an optimized NAS I O layer . The optimized NAS I O layer is used for processing the I O request from the NAS OS and obtained by customizing the CA thread including the CA driver of the SAN. The optimized NAS I O layer may be called the CA control block . The function of the optimized NAS I O layer the CA control block will be described below.

Furthermore one or more SAN dedicated volumes and NAS dedicated volumes are provided on the hypervisor . The SAN dedicated volumes are storage areas in which the I O request by the SAN is performed and the NAS dedicated volumes are storage areas in which the I O request by the NAS is performed. In other words the SAN dedicated volumes and the NAS dedicated volumes are guest OS dedicated volumes.

The SAN dedicated volumes and the NAS dedicated volumes for example are set and managed by a management apparatus not illustrated and a management screen and the like thereof are displayed on a display of the management apparatus.

In the storage apparatus various types of management screens are displayed on the display of the management apparatus. For example the volume creation screen as illustrated in is displayed when a volume is created. A manager operates an input device such as a mouse and a keyboard not illustrated to input various types of information in the volume creation screen so that the SAN dedicated volume and the NAS dedicated volume are created.

The management screen displayed on the display of the management apparatus for example may be created and displayed by the management apparatus or the CPU and the like of the primary CM may perform these processes.

In the example illustrated in the volume creation screen includes input areas to . For example an arbitrary volume name of a volume to be created can be input in the input area . An arbitrary RAID type of the volume to be created can be input in the input area . In the example illustrated in any one of RAID 1 to RAID 6 can be selected in a pull down menu.

An arbitrary size of the volume to be created can be input in the input area . Further an arbitrary attribute of the volume to be created can be input in the input area . For example in the example illustrated in any one of a SAN volume and a NAS volume can be selected as an attribute and any one of Normal Thin provisioning and Copy can be further selected as the SAN volume.

For example in a case where any one of SAN Normal SAN Thin provisioning SAN Copy is selected as the volume attribute the SAN volume can be created and when NAS is selected the NAS volume can be created.

When a create button is selected after the input areas to are input with each piece of information the I O request instructing to create the volume is transmitted to the SAN OS for example.

Further the storage apparatus can selectively create the SAN volume and the NAS volume in one volume creation screen . In other words the SAN volume and the NAS volume can be managed and operated through one management screen and the convenience increases.

The NAS agent processes a NAS input output request which is received from the intelligent SCSI driver .

The NAS agent includes the NAS control block which controls the I O request from the NAS OS and the CA control block which processes the I O request.

The intelligent CA agent illustrated in functions as the NAS control block or the optimized NAS I O layer illustrated in functions as the CA control block . In other words the intelligent CA agent and the optimized NAS I O layer function as the NAS agent .

The NAS control block controls the I O request which is received from the NAS OS through the inter GOS communication unit .

For example the NAS control block has a function of logging in to a virtual host dummy host so as to process the request from the NAS OS in the SAN OS and informs the CA control block

Further the NAS control block analyzes and checks the SCSI command from the NAS OS and informs the CA control block

As the SCSI command which is supportable in the NAS control block the following commands are exemplified.

READ6 10 WRITE6 10 READ CAPACITY 16 SYNCHRONIZE CACHE TEST UNIT READY INQUIRY Standard Page 00 80 83 86 8F B0 B2 F0 F1 F2 and MODE SENSE page 00 01 02 03 04 07 08 0A 1C .

In addition for example the number written in the parenthesis in these commands shows various types of parameters such as a bit number and a page number and various modifications can be made.

Further the NAS control block sends a request to the IOC for the data transmission and data integrity field DIF control between the cache area and the NAS OS area in the shared memory through a serial attached SCSI SAS driver for example according to a transmission request content from the CA control block as described below.

The CA control block processes the I O request which is received from the NAS OS through the inter GOS communication unit . The CA control block has the following functions.

In other words an NIC Network Interface Card mounting port area in a port management area is released to the NAS control block and a command management such as queue management and block control is performed.

Further the CA control block informs the basic control see of a command and an event which are created by the NAS control block . Furthermore when the data transmission is requested from the basic control the NAS control block is called to perform a process according to the processing result. In other words an abnormal sense creation a transmission request and the like are performed.

In addition a resource cache in corresponds to the basic control in . Further a maintenance unit is a maintenance controller which performs control of a maintenance system in the storage apparatus .

An exemplary process in the storage apparatus according to the embodiment as configured above will be described according to a flowchart illustrated in . In addition in a read command of the NAS is exemplified.

When the read request of the NAS is performed the intelligent SCSI driver in the NAS OS prepares a read data storage area in the NAS area of the shared memory in Step A.

In Step A the read command is informed from the intelligent SCSI driver of the NAS OS to the intelligent CA driver of the SAN OS through the inter GOS communication unit inter GOS communication . In addition since the inter GOS communication is performed in a direct interrupt scheme without passing through the hypervisor it is possible to reduce time necessary for the communication.

In Step A the intelligent CA driver receives the read command. In this way the inter GOS communication is performed between the NAS OS and the SAN OS .

In Step A the intelligent CA driver analyzes the received command and determines that the command is the read command. The read command is passed through the CA thread Step A and in Step A a cache area is acquired by the resource cache .

In Step A the resource cache arranges read data in the acquired cache area and the cache area comes to be a state where the read data is ended in arrangement Step A . The fact that the read data is arranged in the cache area is informed through the CA thread Step A to the intelligent CA driver .

In Step A the intelligent CA driver makes a request to the IOC for the data transmission a block check character BCC check and the added BCC removal. When the IOC performs these processes the read data in the cache area is stored in the read data storage area secured by the intelligent SCSI driver in Step A Step A .

Further the IOC informs the intelligent CA driver of the completion Step A and the intelligent CA driver informs the intelligent SCSI driver of the completion through the inter GOS communication unit inter GOS communication in Step A. At this time the inter GOS communication is performed between the SAN OS and the NAS OS .

Next a creating process of the NAS dedicated volume see in the storage apparatus according to the embodiment will be described according to a flowchart illustrated in Steps B to B .

The creating process of the NAS dedicated volume is performed by selecting the create button in a state where NAS is selected as an attribute in the input area in the volume creation screen illustrated in .

In Step B various types of information input to the volume creation screen are analyzed in the SAN OS and the creating process of the SAN volume is performed based on the information in Step B. In Step B the created SAN volume is formatted.

Thereafter in Step B a process of changing the attribute of the created SAN volume to the NAS volume is performed the information for example attribute information size and the like of the created volume is stored in a database of configuration information in the SSD .

In Step B inter GOS communication interface conversion control is performed a volume number of the volume created in Step B is informed to the NAS OS along with an instruction to create the NAS volume through the shared memory by the inter GOS communication.

In the NAS OS first a device is created based on the volume number according to the instruction to create the NAS volume informed by the inter GOS communication in Step B and the device is registered dev . Therefore the volume created in the SAN is recognized as hardware usable for the NAS OS .

Further a partition is created for the created volume in Step B a mount point is created in Step B and the file system is formatted in Step B.

Thereafter the completion is informed to the SAN OS completion return of the screen is performed in the SAN OS Step B and the process is ended.

In addition the example illustrated in illustrates a case where a process request input in the volume creation screen is processed in the SAN OS and transferred to the NAS OS through the inter GOS communication unit to be processed in the NAS OS but the invention is not limited thereto.

In other words the process request input in the input screen through which the process request of the NAS and the process request of the SAN can be input may be processed in the NAS OS and then transferred to the SAN OS through the inter GOS communication unit to be processed in the SAN OS and may be processed in various modified manners.

As described above with the storage apparatus according to the embodiment the hypervisor which is the virtualized OS is executed on the CPU which is the multi core processor and the NAS OS and the SAN OS are executed on the hypervisor . Therefore the file system control implemented in a dedicated server apparatus in the related art can be mounted in the storage apparatus as the guest OS. Accordingly it is possible to reduce a cost for introducing the server apparatus.

In the NAS OS when receiving the I O request of the NAS from the host apparatus and the like the intelligent SCSI driver suppresses the direct access to the SAN dedicated volume and transmits the I O request of the NAS to the SAN OS by the inter guest OS communication through the inter GOS communication unit .

At this time since the inter guest OS communication is performed by the direct interrupt scheme without passing through the hypervisor it is possible to reduce time necessary for the communication.

In the SAN OS the intelligent CA driver performs the I O request of the NAS and transmission reception of a response with respect to the NAS OS . Thereafter in the NAS agent of the SAN OS the NAS control block controls the received I O request and the CA control block processes the I O request. In this way the I O request of the NAS can be processed in the SAN OS and the NAS and the SAN can be integrally handled.

A response such as the processing result of the I O request is transmitted from the intelligent CA driver to the intelligent SCSI driver of the NAS OS through the inter GOS communication unit . The NAS OS transmits the response to the host apparatus.

In other words the I O requests of the NAS and the SAN are performed for the storage apparatus without a special change in the functional configuration of the host apparatus and the processing result can be received.

The NAS OS and the SAN OS are configured to be executed on the hypervisor and the operation of the NAS and the operation of the SAN are configured to be input using the same menu screen. Further at this time the data transmission reception between the SAN OS and the NAS OS is performed by the inter GOS communication unit . With this configuration the NAS OS and the SAN OS can be operated by an integrated user interface so that the convenience increases and a workload of a system operation manager is reduced. In other words both the SAN and the NAS can be integrally designed managed maintained using a common user interface screen so that the convenience increases.

In addition the disclosed technology is not limited to the above embodiment and various modifications can be made in a scope not departing from the spirit of the embodiment. The respective configurations and processes of the embodiment can be optionally selected as needed or can be appropriately combined to each other.

For example the above mentioned embodiment illustrates an example in which VxWorks is used as the SAN OS and Linux is used as the NAS OS but the invention is not limited thereto and various modifications such as using other OSs can be made.

According to the embodiment the NAS and the SAN can be efficiently integrated in the storage apparatus.

All examples and conditional language recited herein are intended for the pedagogical purposes of aiding the reader in understanding the invention and the concepts contributed by the inventor to further the art and are not to be construed limitations to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although one or more embodiments of the present inventions have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

