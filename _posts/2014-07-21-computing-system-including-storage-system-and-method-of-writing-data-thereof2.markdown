---

title: Computing system including storage system and method of writing data thereof
abstract: Provided is a method of writing data of a storage system. The method includes causing a host to issue a first writing command; causing the host, when a queue depth of the first writing command is a first value, to store the first writing command in an entry which is assigned in advance and is included in a cache; causing the host to generate a writing completion signal for the first writing command; and causing the host to issue a second writing command.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09557935&OS=09557935&RS=09557935
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09557935
owner_city: 
owner_country: KR
publication_date: 20140721
---
This application claims the benefit of Korean Patent Application No. 10 2013 0116891 filed on Sep. 30 2013 in the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

The inventive concept relates to a computing system including a storage system and a method of writing data thereof and more particularly to a computing system capable of improving a writing speed and a method of writing data thereof.

Native command queuing NCQ is a technique that stores a request for inputting and outputting I O in a queue and then rearranges and executes the request for I O in order to improve performance of a serial advanced technology attachment SATA device in a specific situation.

However if a case where a host computer has to receive a response immediately synchronous I O that is a case where a queue depth is 1 frequently occurs it may be difficult to utilize a NCQ technique.

Not only SATA NCQ but with any device which can process multiple commands in parallel. For example all modern SSDs have multiple channels and they can process multiple commands at the same time.

The inventive concept provides a computing system that increases a writing speed using a storage system.

According to an aspect of the inventive concept there is provided a method of writing data of a storage system by host the method comprising issuing a first writing command storing the first writing command in an entry which is assigned in advance and is comprised in a cache when a queue depth of the first writing command is a first value generating a writing completion signal in response to the first writing command and issuing a second writing command.

When the number of writing commands stored in the cache is equal to or greater than a first reference value the method may further include reordering the writing commands in accordance with address values corresponding to the writing commands.

The reordering of the writing commands may include rearranging the writing commands so that the order of the writing commands conforms to the order of the address values corresponding to the writing commands.

When the total share of the writing commands stored in the cache is equal to or greater than a second reference value the method may further include starting to flush the writing commands from the cache to the storage system.

When the total share of the writing commands stored in the cache is equal to or less than a third reference value the method may further include stopping the flushing.

When the total size of pieces of target data of the second writing command is equal to or greater than a third reference value and target address values of the second writing command are sequential values the method may further include flushing the second writing command from the host to the storage without transmitting the second writing command from the host to the cache.

When the first writing command is stored in the cache the total share of writing commands stored in the cache is equal to or greater than a fourth reference value and target address values of the second writing command are sequential values the method may further include flushing the second writing command from the host to the storage.

When a target address of the second writing command conforms to a target address of a writing command which is stored in the cache in advance the writing command stored in the cache in advance may not be flushed to the storage and only the second writing command may be flushed to the storage.

According to another aspect of the inventive concept there is provided a computing system comprising a host and a storage system. When a queue depth of a first writing command is 1 the host stores the first writing command in an entry which is assigned in advance and is comprised in a cache generates a writing completion signal for the first writing command and issues a second writing command.

When the number of writing commands stored in the cache is equal to or greater than a first reference value the writing commands may be reordered in accordance with address values corresponding to the writing commands.

The writing commands may be rearranged so that the order of the writing commands conforms to the order of the address values corresponding to the writing commands.

When the total share of the writing commands stored in the cache is equal to or greater than a second reference value the writing commands may start to be flushed from the cache to the storage system.

When the total size of pieces of target data of the second writing command is equal to or greater than a third reference value and target address values of the second writing command are sequential values the second writing command may be flushed from the host to the storage without being transmitted from the host to the cache.

When the first writing command is stored in the cache the total share of writing commands stored in the cache is equal to or greater than a fifth reference value and target address values of the second writing command are sequential values the second writing command is flushed from the host to the storage.

The inventive concept will now be described more fully with reference to the accompanying drawings in which exemplary embodiments of the inventive concept are shown. The inventive concept may however be embodied in many different forms by one of ordinary skill in the art without departing from the technical teaching of the inventive concept. In other words particular structural and functional description of the inventive concept are provided in descriptive sense only various changes in form and details may be made therein and thus should not be construed as being limited to the embodiments set forth herein. As the inventive concept is not limited to the embodiments described in the present description and thus it should not be understood that the inventive concept includes every kind of variation examples or alternative equivalents included in the spirit and scope of the inventive concept. Also throughout the specification like reference numerals in the drawings denote like elements. In the drawings lengths and sizes of layers and regions may be exaggerated for clarity.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of example embodiments. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising when used in this specification specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this inventive concept belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein. As used herein the term and or includes any and all combinations of one or more of the associated listed items. Expressions such as at least one of when preceding a list of elements modify the entire list of elements and do not modify the individual elements of the list.

Referring to the method of writing data of a storage system according to the current embodiment includes causing a host to issue a first writing command operation S causing the host to store the first writing command in an entry which is assigned in advance and is included in a cache when a queue depth if the first writing command is 1 operation S and operation S causing the host to generate a first writing completion signal operation S and causing the host to issue a second writing command operation S .

The host mentioned in this specification means a host computer PC . In addition the host means a device that performs a writing operation on a storage system for example an electronic device such as a multimedia device a digital camera a digital TV a computer a tablet a phone or a server.

The queue depth mentioned in this specification means a physical limitation of a storage port capable of performing inputting and outputting I O at a time. For example when the queue depth is 1 an I O command may be transmitted using one storage port. In addition when the queue depth is 32 an I O command may be transmitted using 32 storage ports. When the queue depth increases the storage port may not be used in another application and when the storage port decreases the speed of the host computer felt by a user may be remarkably decreased.

In a general computing system when a queue depth issued by an operating system is 1 a host waits to receive a response of a writing command from a storage. After the host receives the response the host performs another writing command. On the other hand when the queue depth is 32 the host transmits 32 writing commands to the storage and receives responses of the commands from the storage and then performs another writing command. Accordingly when the queue depth is 1 the transmission speed of a writing command is lower than that in a case where the queue depth is 32.

In this specification a cache may mean a memory which is included in the host computer and is capable of a high speed operation faster than the main storage to which I O is directed. For example the cache may mean a volatile memory DRAM SRAM which is included in the host computer.

In the method of writing data of the storage system when the queue depth is 1 writing commands are stored in a portion of the cache which is assigned in advance and the writing completion signal is generated in the host itself. Accordingly the host may perform processing in the same manner that the writing commands were transmitted to the storage system to issue the writing commands later more rapidly. Thus a user may feel an operation of the host computer more rapidly.

The storage may include a controller Ctrl a buffer and a memory array MEM ARRAY. However the scope of the inventive concept is not limited thereto.

The memory array MEM ARRAY may be constituted by for example a DRAM an SRAM a PRAM an MRAM a ReRAM an FRAM a NOR flash memory a NAND flash memory or a fusion flash memory for example a memory in which an SRAM buffer a NAND flash memory and a NOR interface logic are combined .

The controller Ctrl may control an operation of the memory array MEM ARRAY. For example the controller Ctrl may receive a plurality of writing commands WRT WRT and write corresponding data in a region corresponding to an address included in each of commands.

In addition the controller Ctrl may write data in the memory array MEM ARRAY in response to a writing command with reference to a logic block address LBA stored in the buffer and a look up table indicating a correspondence relation of a physical block address PBA.

Referring to the computer system according to the current embodiment may include the host and the storage system . The host may include an application interface APP I F a processor PROS a random access memory RAM and a file management device FMD.

The processor PROS may issue an I O command for inputting and outputting data to and from the storage system . In addition the processor PROS may store data transmitted from the storage system in the random access memory RAM. In addition the processor PROS may receive the data stored in the random access memory RAM to perform processing arithmetic operation and or handling of the data.

The application interface APP I F may receive a request of a user or an application to transmit data or a data I O command to the processor PROS.

The processor PROS may control the file management device FMD to store information stored in a storage system STORAGE in the random access memory RAM in response to a request of the host. Here the random access memory RAM may be a dynamic random access memory DRAM a static random access memory SRAM a different type of volatile memory or a combination thereof. In other parts of this specification the random access memory RAM may be referred to as a buffer or a cache.

The file management device FMD may use at least one file system and or virtual file system. For example the file management device FMD may use a first file system FS and a second file system FS. A virtual file system VFS allows a client application program to have access to the plurality of file systems FS and FS by using the same method. The virtual file system VFS may define an interface between a kernel of a computer operating system and the file systems FS and FS.

For example the file systems FS and FS of the file management device FMD may be a Unix based file system a file system of LINUX a file system of MacOS or a file system of Microsoft Windows.

For example the file systems FS and FS may be an advanced disc filing system AdvFS a be file system BFS Btrfs CrossDOS a disc filing system DFS Episode EFS exFAT ext FAT Files 11 hierarchical file system HFS HFS plus a high performance file system IBM GPFS JFS a Macintosh file system MINIX a NetWare file system NILFS a Nobel storage service NTFS QFS QNX4FS a ReiserFS Reiser4 SpadFS UBIFS a Unix file system a veritas file system VxFS VFAT a write anywhere file layout WAFL XFS Xsan or ZFS.

When the computing system CSYS according to the current embodiment is a mobile device a battery for supplying an operation voltage of the computing system and a modem such as a baseband chipset may be additionally provided. In addition the computing system CSYS according to the current embodiment may further include an application chipset a camera image processor CIS a mobile DRAM and the like.

Referring back to the host may include the processor PROS and the random access memory RAM of and a host interface HOST I F. Hereinafter an operation of the operating system of the host will be described.

The host may receive data which is input through a user application . In addition the host may output output data through the user application . The data which is input through the user application may be processed through a file system of the operating system and may be stored in the storage .

The data which is input through the user application is transmitted to the file system via a window application programming interface and an IO sub system. The file system processes the input data so that the input data includes information regarding where the data is logically stored in the storage . That is the input data is processed to include volume information through a volume manager partition information through a partition manager and disc information through a disk class driver. The processed input data is stored in the storage through a port.

The file system may further include an upper filter driver or a lower filter driver. The upper filter driver may process the input data in units of files. The lower filter driver may process the input data in units of logical block addressing LBA . For example the host may generate a writing completion signal may check the size of data stored in the cache to perform reordering and may check a writing command to perform an operation such as direct bypassing to the storage through the upper filter driver and the lower filter driver.

Referring to the host may receive the data which is input through the user application . An operating system OS may issue a writing command WRT Addr1 AddrK Dta1 DtaK so as to write the received data in the storage. Pieces of data Dta1 to DtaK may be input to addresses Addr1 to AddrK of the storage respectively in response to the writing command WRT Addr1 AddrK Dta1 DtaK .

When a queue depth of the writing command issued from the operating system is the host according to the current embodiment may assign entries ETR to ETR to a cache may store the writing command processed by the operating system in each entry and then may generate a writing completion signal for the writing command. Accordingly the host may generate the writing completion signal without receiving the writing completion signal from the storage and may issue the next writing command. Thus a user may feel that the writing command is rapidly transmitted.

The cache may store the writing command WRT Addr1 AddrK Dta1 DtaK issued from the operating system in the entry ETR ETR. The host may assign a region for storing the writing command to a part of the cache in advance. When a predetermined number of writing commands are filled in the entry ETR ETR the host may transmit a flush command Flush WRT WRT including the writing commands to the storage .

A host according to another embodiment of the inventive concept may flush writing commands stored in a cache from the cache to a storage in units of a predetermined number of entries.

For example the host may transmit a first writing command WRT to a 32 nd writing command WRT to the storage at a time using a plurality of ports while performing flushing as in a case where a queue depth is 32. Accordingly the host may increase transmission efficiency even when the queue depth is 1.

In another embodiment of the inventive concept when the number of stored writing commands is increased more than a predetermined number flushing may be performed from a cache to a storage in units of a predetermined number of entries.

Referring to the method of writing data of the storage system may further include reordering writing commands in accordance with address values corresponding to the writing commands operations S and operation S when the number of writing commands stored in a cash is equal to or greater than a first reference value as compared with the method of writing data of the storage system which is described in . Here the reordering may mean rearrangement performed so that the order of writing commands conform to the order of address values corresponding to the writing commands which will be described later with reference to .

Referring to the method of writing data of the storage system according to another embodiment of the inventive concept may further include starting to flush writing commands from a cache to the storage system when the total share of writing commands stored in the cache is increased to a value equal to or greater than a second reference value as compared with the method of writing data of the storage system which is described with reference to . Here the flushing may be performed in units of a predetermined number of entries.

In addition the method of writing data of the storage system according to another embodiment of the inventive concept may further include stopping flushing when the total share of writing commands stored in the cache is decreased to a value equal to or less than a third reference value. Here the flushing may be performed in units of a predetermined number of entries which will be described in detail later with reference to .

Referring to the computing system may include a host and a storage . The storage may be configured in a similar manner to the storage of .

The host may receive data which is input through a user application . An operating system OS may issue a writing command WRT Addr1 AddrK Dta1 DtaK so as to write the received data in the storage . Pieces of data Dta1 to DtaK may be input to addresses Addr1 to AddrK of the storage respectively in response to the writing command WRT Addr1 AddrK Dta1 DtaK .

A cache may store the writing command WRT Addr1 AddrK Dta1 DtaK which is issued from the operating system in an entry ETR ETR. When a predetermined number of writing commands are filled in the entry ETR ETR the host may transmit a flush command Flush WRT WRT including the writing commands to the storage .

The host according to the current embodiment may further include a reordering engine . When the number of writing commands stored in a cache is equal to or greater than a first reference value the reordering engine may perform reordering of the writing commands in response to address values corresponding to the writing commands.

For example it is assumed that the number of writing commands having a queue depth of 1 stored in the cache is 32 and that each of the writing commands is stored in the entry ETR ETR. The reordering engine may perform reordering ROD WRT WRT of the writing commands for example WRT to WRT in accordance with the order of addresses of the storage .

The writing commands on which the reordering is performed may be stored in the cache again and then may be flushed Flush WRT WRT to the storage . Although not shown in the writing commands on which the reordering is performed may be flushed Flush WRT WRT to the storage without being stored in the cache again. Accordingly the writing commands on which the reordering is performed have a sequential characteristic and thus pieces of input data may be rapidly written in the storage .

When the total share of writing commands stored in the cache is increased to a value equal to or greater than a second reference value the host according to the current embodiment may start to flush the writing commands from the cache to a storage system.

In addition in the method of writing data of the storage system when the total share of writing commands stored in the cache is decreased to a value equal to or less than a third reference value the host may stop the flushing.

For example it is assumed that the total size of writing commands is 60 MB when the capacity of the cache is 1 GB. In this case the total share of the writing commands is 6 . If the second reference value is 5 the writing commands may be continuously flushed by for example 128 KB. In this case the flushing may be continuously performed by 2 MB and the total size of the writing commands occupied in the cache may be decreased to equal to or less than 50 MB. If the total size of the writing commands occupied in the cache is decreased to equal to or less than 50 MB the host may stop the flushing.

Accordingly the computing system according to the current embodiment may perform reordering of writing commands having a constant size so that the writing commands may have a sequential characteristic thereby allowing pieces of input data to be rapidly written in the storage .

Referring to the method of writing data of the storage system according to another embodiment of the inventive concept may include causing a host to issue a third writing command operation S and bypassing the third writing command issued by the host without storing the third writing command in a cache when the total size of continuous writing commands is equal to or greater than a fourth reference value and is not the same as an address value of the previous writing command operation S operation S and operation S which will be described later in detail with reference to .

Referring to the computing system may include a host and a storage . The storage may be configured in a similar manner to the storage of .

The host according to the current embodiment may include a first bypass engine Bypass Engine  . The first bypass engine checks whether a writing command WRT  Addr1 AddrM Dta1 DtaM issued from an operating system may be bypassed. That is the first bypass engine checks whether the total size of pieces of target data of a third writing command is equal to or greater than a fourth reference value and whether target address values of the third writing command are sequential values.

Specifically the operating system transmits a bypass check command Bypass CHK WRT  with respect to the issued third writing command to the first bypass engine . The first bypass engine may determine whether the target address values Addr1 AddrM of the third writing command are sequential values and whether the total size of pieces of target data Dta1 to DtaM of the third writing command is equal to or greater than the fourth reference value.

When the target address values Addr1 AddrM of the third writing command are sequential values and the total size of the pieces of target data Dta1 to DtaM of the third writing command is for example equal to or greater than 4 MB the operating system may directly bypass Bypass WRT  the writing command to the storage . Accordingly when the pieces of target data of the writing command targeted at the sequential address values have a size equal to or greater than a constant size the writing command may be directly transmitted to the storage without being stored in a cache and thus a writing speed may be increased.

Referring to the computing system may include a host and a storage . The storage may be configured in a similar manner to the storage of .

The host according to the current embodiment may include a second bypass engine Bypass Engine  . A writing command WRT  Addr1 AddrN Dta1 DtaN which is issued from an operating system is stored in a cache. When the total share of writing commands stored in the cache is equal to or greater than a fifth reference value and target address values of a second writing command generated thereafter are sequential values the second bypass engine may flush the second writing command to the storage .

Specifically when the writing command WRT  Addr1 AddrN Dta1 DtaN is stored in the cache and the total share of writing commands stored in the cache is equal to or greater than the fifth reference value the second bypass engine may determine whether the target addresses of the second writing command generated thereafter are sequential addresses. When the target addresses of the second writing command generated thereafter are sequential addresses the operating system may generate a bypass command Bypass WRT  for directly transmitting the second writing command WRT  to the storage .

Accordingly when writing commands targeted at sequential address values are issued and the total share of writing commands stored in the cache is equal to or greater than the fifth reference value the writing commands may be directly transmitted to the storage without being stored in the cache and thus a writing speed may be increased.

Referring to the network system NSYS according to the current embodiment may include a computing system CSYS and a plurality of terminals TEM to TEMn connected to each other through a network. The computing system CSYS according to the current embodiment may include a server that processes a request received from the plurality of terminals TEM to TEMn and an SSD that stores data corresponding to the request received from the terminals TEM to TEMn.

A host of may be the host of . In addition the computing system CSYS of may be the computing system CSYS of . Furthermore even when the host of issues a writing command of data to the plurality of terminals TEM to TEMn included in the network the method of may be applied.

While the inventive concept has been particularly shown and described with reference to exemplary embodiments thereof it will be understood that various changes in form and details may be made therein without departing from the spirit and scope of the following claims.

