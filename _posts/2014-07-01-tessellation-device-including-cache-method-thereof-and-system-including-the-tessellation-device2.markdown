---

title: Tessellation device including cache, method thereof, and system including the tessellation device
abstract: A tessellation method includes determining whether a previous tag the same as a current tag of a current patch is stored in a cache, and transmitting a previous tessellation pattern corresponding to the previous tag stored in the cache to a domain shader when a cache hit occurs. The method may further include, when a cache miss occurs, generating a current tessellation pattern corresponding to the current patch using a tessellator and transmitting the generated current tessellation pattern to the domain shader, and storing the generated current tessellation pattern in the cache.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09582935&OS=09582935&RS=09582935
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09582935
owner_city: Suwon-si, Gyeonggi-Do
owner_country: KR
publication_date: 20140701
---
This application claims priority under 35 U.S.C. 119 a to Korean Patent Application No. 10 2013 0083521 filed on Jul. 16 2013 the disclosure of which is incorporated by reference in its entirety herein.

Embodiments of the present inventive concept relate to tessellation using a cache and more particularly to a tessellation device including a cache an operation method thereof and a system including the tessellation device.

Tessellation is the tiling of a plane using one or more geometric shapes called tiles with no overlaps and no gaps.

In computer graphics the term tessellation is used to describe the organization of information needed to give the appearance of realistic three dimensional objects.

A group of control points that define a part of a surface is referred to as a patch. Tessellation factors determine how much to subdivide each patch. For example the tessellation factors may determine how many tiles the patch will be subdivided into during tessellation. The tessellation converts a low detail part of a surface into higher detail primitives in a graphic process. However since this graphic process is computationally intensive there is a need to make the process more efficient.

According to an exemplary embodiment of the present inventive concept a tessellation method includes determining whether a previous tag the same as a current tag of a current patch is stored in a cache and transmitting a previous tessellation pattern corresponding to the previous tag stored in the cache to a domain shader when a cache hit occurs.

According to an exemplary embodiment of the present inventive concept a tessellation device includes a Hull shader a domain shader and a cache processing circuit. The Hull shader generates current tag generation data for a current patch. The cache processing circuit generates a current tag based on the current tag generation data determines whether a previous tag the same as the current tag is stored in a cache reads a previous tessellation pattern corresponding to the previous tag from the cache when a cache hit occurs and transmits the read previous tessellation pattern to the domain shader.

According to an exemplary embodiment of the present inventive concept a method of managing an operation of a graphics processor unit GPU includes determining whether a tag based on an output of a hull shading can be retrieved within a threshold time performing a tessellation to generate a current tessellation pattern CTP and performing a domain shading on the CTP when it is determined that the tag cannot be retrieved in time and performing the domain shading on a previous tessellation pattern PTP when it is determined that the tag cannot be retrieved in time.

The present inventive concept now will be described more fully hereinafter with reference to the accompanying drawings in which exemplary embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the exemplary embodiments set forth herein. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like numbers refer to like elements throughout.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present.

As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise.

Tessellation or a tessellation stage in a graphic pipeline to be described in the present inventive concepts may be embodied in hardware or software.

A current patch is a patch which is a current processing object and a previous patch is a patch which is processed before the current patch.

A current tag is a tag related to tag generation data of the current patch a previous tag is a tag related to tag generation data of the previous patch and the tag generation data include tessellation factors and a patch equation.

The portable electronic device may be embodied in a laptop computer a smart phone a tablet PC a personal digital assistant PDA a portable multimedia player PMP a handheld game console or a mobile internet device MID .

The processing device may be embodied in a printed circuit board PCB a system on chip SoC or an application processor.

The processing device includes a central processing unit CPU a graphics processing unit GPU a graphics memory a non volatile memory a volatile memory a memory interface and a display interface .

In an embodiment the CPU controls the GPU the graphics memory the non volatile memory the volatile memory the memory interface and or the display interface through a bus .

In an exemplary embodiment the CPU executes an application e.g. a 3D application or a 3D game application .

As the 3D application or the 3D game application is performed or executed the 3D application or the 3D game application outputs 3D application programming interface API commands. A 3D API e.g. OpenGL or Direct3D used in applications may be performed or executed to render 3D computer graphics based on the 3D API commands.

The GPU may be used to process data streams related to computer graphics based on a control of the CPU .

In an exemplary embodiment the GPU is a graphics processor including a graphic pipeline with one or more processing stages. The GPU may include a cache as illustrated in and selectively operate a tessellator based on whether a previous tag the same as a current tag of a current patch is stored in the cache .

The non volatile memory and the volatile memory may be used as a system memory. The non volatile memory may be embodied in a read only memory ROM and store a basic input output system BIOS . The volatile memory may be embodied in a random access memory RAM and temporally store data and or a program or program module needed in the GPU .

For example the volatile memory may store an operating system OS application programs other program modules and program data.

The external memory may be embodied in a volatile memory or a non volatile memory. The volatile memory may be embodied in a dynamic random access memory DRAM a static random access memory SRAM a thyristor RAM T RAM a zero capacitor RAM Z RAM or a Twin Transistor RAM TTRAM .

The non volatile memory may be embodied in an Electrically Erasable Programmable Read Only Memory EEPROM a flash memory a Magnetic RAM MRAM a Spin Transfer Torque MRAM a Conductive bridging RAM CBRAM a Ferroelectric RAM FeRAM a Phase change RAM PRAM a Resistive RAM RRAM a Nanotube RRAM a Polymer RAM PoRAM a Nano Floating Gate Memory NFGM a holographic memory a Molecular electronics Memory Device or an Insulator Resistance Change Memory.

The external memory may store an operating system OS application programs other program modules and or program data. According to a control of the CPU the OS the application programs the other program modules and or the program data stored in the external memory may be loaded to the volatile memory .

The 3D application the 3D game application or an API which may perform a tessellation method to be described in at least one embodiment of the present inventive concept stored in the external memory may be loaded to the volatile memory .

According to an exemplary embodiment the external memory is embodied in a hard disk drive HDD or a solid state drive SSD .

According to an exemplary embodiment the external memory is embodied in a removable storage media or a non removable storage media. For example the external memory may be embodied in a universal flash storage UFS an embedded multimedia card eMMC or a USB flash drive.

The display interface may transmit a computer graphics processed by the CPU or the GPU e.g. 2D data or 3D data to the display . In an exemplary embodiment the display is embodied in a flat display which displays the computer graphics.

In for convenience of description of technical concepts according to an exemplary embodiment of the present inventive concept only a tessellation device A B or C which is related to the tessellation is illustrated among graphic pipelines included in the GPU . Accordingly the tessellation device A B or C may be applied or used in various graphic pipelines.

The tessellation device A includes a Hull shader a cache processing circuit A a tessellator and a domain shader .

A Direct3D 11 graphics pipeline adds three graphics pipelines such as the Hull shader the tessellator and the domain shader to a Direct3D 10 graphics pipeline. Accordingly each operation of the Hull shader the tessellator and the domain shader except for the cache processing circuit A is substantially the same as each operation of the Hull shader the tessellator and the domain shader included in the Direct3D 11 graphics pipeline.

The Hull shader may receive input points ICP calculate the tessellation factor TF by or per face edge or point using the received input points ICP and assign the calculated tessellation factor TF by or per the face the edge or the point.

The tessellation factor TF may denote a level of detail LOD . The tessellation factor TF may be an integer or a decimal fraction.

In an exemplary embodiment the Hull shader transforms a set of the input points ICP into a set of output points OCP. According to an exemplary embodiment the number of the input points ICP and the number of the output points OCP may be designed to be equal to each other or different from each other.

The patch equation PE may be a curve equation or a surface equation. For example the curve equation may be a Hermite curve equation a Bezier curve equation a Non uniform rational B spline NURBS curve equation or B spline curve equation.

The Hull shader generates tag generation data related to input points ICP or output points OCP according to programmed criteria. For example the tag generation data includes a patch equation PE and a tessellation factors TF which are related to the input points ICP or the output points OCP.

The tessellation factors TF may include internal tessellation factors and outer tessellation factors which are independent from each other.

The input points ICP included in a patch may denote input vertices or input control points. The patch may denote a quad patch a tri patch or an isoline.

Each of a series or sequence of input patches is located close to each other so that each of the input patches may use the same patch equation and the same tessellation factors. That is the series of input patches may have the same tessellation patterns. The patch equation may denote a curve equation or a surface equation.

The cache processing circuit A determines whether a previous tag the same as a current tag of a current patch to be currently processed is stored in a cache and when a cache hit occurs according to a result of the determination outputs a previous tessellation pattern PTP corresponding to the previous patch stored in the cache to the domain shader . For example the cache hit means that the previous tag the same as the current tag is stored in the cache. If the previous tag the same as the current tag is not stored in the cache then a cache miss has occurred.

Here the previous tessellation pattern PTP includes UV coordinates or UVW coordinates of tessellated points for a previous patch and topology information of the tessellated points. The tessellated points may be referred to as domain points. The letters U and V may denote the axes of a 2D texture when UV mapping is used to project a texture map onto a 3D object. UVW coordinates are used in UVW mapping which allows texture maps to wrap in complex ways onto irregular surfaces. Each point in a UVW corresponds to a point on a surface.

According to an exemplary embodiment the previous tessellation pattern PTP further includes output points for the previous patch.

The topology information includes connectivity information of each of the tessellated points. For example the topology information may indicate which points are connected to one another.

However when a cache miss occurs according to a result of the determination the tessellator performs a tessellation operation by using output points OCP for a current patch and tessellation factors TF for the current patch and generates a current tessellation pattern CTP corresponding to the current patch.

The current tessellation pattern CTP includes UV coordinates or UVW coordinates of tessellated points for the current patch and topology information on the tessellated points.

The tessellator outputs the current tessellation pattern CTP to the domain shader through the cache processing circuit A. The current tessellation pattern CTP may be stored in a cache of the cache processing circuit A.

According to an exemplary embodiment the current tessellation pattern CTP further includes output points OCP for a current patch.

The tessellation device A according to an exemplary embodiment of the present inventive concept skips an operation of the tessellator based on repetitiveness of the current tag of the current patch. For example if a previous tag is the same as the current tag it is likely that similar output points OCP and tessellation factors TF were already previously processed by the tessellator and thus there would be no need to have tessellator process the current output points and tessellation factors TF. Accordingly the tessellation workload of the tessellator may be reduced.

The domain shader generates and outputs attributes VA of vertices or locations VA of vertices using outputs OCP and patch constant data PCD of the Hull shader and an output PTP or CTP of a cache processing circuit A.

For example the domain shader may calculate surface geometry or tessellated vertices using output points OCP patch constant data PCD and an output PTP or CTP of the cache processing circuit A.

The patch constant data PCD may include tessellation factors TF coefficients related to the patch equation PE and or user defined values.

Referring to a tessellation device B according to an exemplary embodiment of the tessellation device A illustrated in includes the Hull shader the cache processing circuit B the tessellator and the domain shader .

The cache processing circuit B includes a tag comparator a cache a cache access control circuit a selector and a cache interface .

Referring to the hull shader outputs tessellation factors TF e.g. TF and the patch equation PE e.g. PE for a first patch e.g. a current patch to the tag comparator . Tag generation data TGD for the first patch includes the tessellation factors TF e.g. TF and the patch equation PE e.g. PE .

The tag comparator generates an address ADD using the tag generation data TGD. For example the address ADD may include an index INDEX a first tag TAG and a first offset OFFSET. That is the first tag TAG may be defined or generated based on the tag generation data TGD. The tag comparator determines whether a tag corresponding to the first tag TAG is stored in a tag cache of the cache .

According to a result of the determination when the tag corresponding to the first tag TAG is not stored in the tag cache of the cache the tag comparator transmits an indication signal indicating a cache miss MISS to the cache access control circuit and the tessellator and transmits the address ADD to the cache access control circuit .

The tessellator performs a tessellation operation using output points OCP for the first patch and tessellation factors TF for the first patch generates a current tessellation pattern CTP corresponding to the first patch based on a result of the tessellation operation and transmits the current tessellation pattern CTP to the cache access control circuit .

The cache access control circuit transmits the current tessellation pattern CTP to the cache based on the address ADD. Accordingly the first tag TAG is stored in the tag cache and the current tessellation pattern CTP is stored in a data cache .

Referring to the Hull shader outputs tessellation factors TF e.g. TF and a patch equation PE e.g. PE for a second patch e.g. a current patch to the tag comparator .

Tag generation data TGD for the second patch includes the tessellation factors TF e.g. TF and the patch equation PE e.g. PE . When the first patch and the second patch are adjacent to each other the tag generation data TGD for each of the first patch and the second patch may be the same as each other.

The tag comparator generates the address ADD using the tag generation data TGD. For example the address ADD may include an index INDEX the first tag TAG and a first offset OFFSET. That is the first tag TAG may be defined or generated based on the tag generation data TGD. The tag comparator determines whether a tag corresponding to the first tag TAG is stored in the tag cache of the cache .

According to a result of the determination when the tag TAG corresponding to the first tag TAG is stored in the tag cache of the cache the tag comparator transmits an indication signal indicating a cache hit HIT to the cache access control circuit and the tessellator and transmits the address ADD to the cache access control circuit .

The cache access control circuit based on the first tag TAG included in the address ADD and the indication signal reads a previous tessellation pattern CTP corresponding to the first patch e.g. a previous patch from the data cache and outputs the read previous tessellation pattern CTP to the selector .

Here the tessellator does not perform a tessellation operation on the second patch based on the indication signal indicating a cache hit HIT.

Referring to the Hull shader generates current tag generation data TGD of a current patch including input points ICP S . As described above the current tag generation data TGD includes the patch equation PE and tessellation factors TF.

The tag comparator compares tags and determines whether a previous tag the same as a current tag of the current patch is stored in the cache and the memory or S .

The tag comparator receives the patch equation PE related to a current patch and the tessellation factors TF related to a current patch generates a current tag using the patch equation PE and the tessellation factors TF compares the current tag with each of previous tags and generates an indication signal indicating a cache hit HIT or a cache miss MISS based on a result of the comparison.

Here each of the previous tags is generated based on tag generation data related to each of previous patches i.e. a patch equation and tessellation factors.

A tag cache of the cache stores each of the previous tags. In addition the data cache of the cache stores a previous tessellation pattern corresponding to each of the previous tags.

The cache may store a previous tessellation pattern corresponding to each of the previous tags transmitted from the memory or through a cache interface .

The tag comparator outputs an address ADD to the cache access control circuit . The address ADD is an address needed to access a previous tessellation pattern stored in the cache . For example the address ADD may be an address including a current tag of a current patch.

The tag comparator outputs an indication signal indicating a cache hit HIT or a cache miss MISS to the cache access control circuit the selector and the tessellator .

When a result of the comparison in step S is a cache hit HIT an operation of the cache processing circuit B is as follows.

The cache access control circuit is enabled in response to an indication signal indicating a cache hit HIT the enabled cache access control circuit using an address ADD including a current tag reads a previous tessellation pattern PTP corresponding to the current tag from the data cache of the cache S and transmits the read previous tessellation pattern PTP to a second input port IP of the selector .

The tessellator may be disabled in response to an indication signal indicating a cache hit HIT. The selector outputs the previous tessellation pattern PTP input to the second input port IP of the selector to the domain shader S .

The domain shader may calculate a location of each vertex in response to the previous tessellation pattern PTP output from the cache access control circuit and outputs OCP and PCD from the Hull shader S .

When the result of the comparison in step S is a cache miss MISS an operation of the cache processing circuit B is as follows.

It is assumed that a previous tag the same as a current tag of a current patch is not present in both the cache and the memory or .

The tessellator receives output points OCP for a current patch and tessellation factors TF for the current patch performs a tessellation operation using the output points OCP and the tessellation factors TF generates a current tessellation pattern CTP corresponding to the current patch based on a result of the tessellation operation S and transmits the current tessellation pattern CTP to a first input port IP of the selector .

The tessellator transmits the current tessellation pattern CTP to the cache access control circuit and the cache access control circuit stores the tessellation pattern CTP in the cache .

For example the cache access control circuit may store the current tessellation pattern CTP in the cache using an address ADD including a current tag generated based on the patch equation PE and the tessellation factors TF of the current patch.

The selector outputs the current tessellation pattern CTP input to the first input port IP to the domain shader in response to an indication signal indicating a cache miss MISS S .

The domain shader calculates a location of each vertex using the outputs OCP and PCD output from the Hull shader and the current tessellation pattern CTP S .

A tessellation pattern for each patch may be generated by a tessellation device A B or C in real time or on the fly and stored in the cache .

As illustrated in tessellation patterns for each patch may be generated in advance and loaded from the memory or to the cache through the cache interface at an appropriate timing S . For example the tessellation pattern for each patch may be generated by a user e.g. a manufacturer or programmer and stored in the memory or .

The appropriate timing may be determined according to a design specification of the tessellation device A B or C. For example when a compulsory miss or a cold miss occurs a tessellation pattern for each patch may be loaded to the cache . The tessellation pattern for each patch may be stored in the external memory .

Referring to the tessellation device C according to an exemplary embodiment of the tessellation device A of includes the Hull shader the cache processing circuit C tessellator and the domain shader .

The cache processing circuit C includes a tag comparator a cache a cache access control circuit a compressor a de compressor a selector and a cache interface .

Referring to the Hull shader generates current tag generation data of a current patch including input points ICP S .

The tag comparator compares tags and determines whether the previous tag the same as the current tag of the current patch is stored in the cache according to a result of the comparison S . As described above the current tag may be defined by tag generation data of the current patch and the previous tag may be defined by tag generation data of a previous patch.

The tag comparator receives the patch equation PE related to the current patch and the tessellation factors TF related to the current patch generates a current tag using the patch equation PE and the tessellation factors TF compares the current tag with each of previous tags and generates an indication signal indicating a cache hit HIT or a cache miss MISS based on a result of the comparison.

When a result of the comparison in step S is cache hit HIT an operation of the cache processing circuit C is as follows.

The cache access control circuit is enabled in response to an indication signal indicating a cache hit HIT and the enabled cache access control circuit in response to an address ADD including a current tag reads a compressed previous tessellation pattern CPTP which corresponds to the current tag from the cache and transmits the compressed previous tessellation pattern CPTP to the de compressor S .

The de compressor de compresses the compressed previous tessellation pattern CPTP and transmits the de compressed previous tessellation pattern PTP to a second input port IP of the selector S . The tessellator may be disabled in response to an indication signal indicating a cache hit HIT.

The selector outputs the de compressed previous tessellation pattern PTP input to the second input port IP to the domain shader in response to an indication signal indicating a cache hit HIT S . The domain shader calculates a location of each vertex using the de compressed previous tessellation pattern PTP and outputs OCP and PCD of the Hull shader S .

When a result of the comparison in step S is a cache miss MISS an operation of the cache processing circuit C is as follows.

The tessellator receives output points OCP for a current patch and tessellation factors TF for the current patch performs a tessellation operation using the output points OCP and the tessellation factors TF generates a current tessellation pattern CTP corresponding to the current patch based on a result of the tessellation operation and transmits the current tessellation patch CTP to a first input port IP of the selector S .

Here the tessellator transmits the current tessellation pattern CTP to a compressor the compressor compresses the current tessellation pattern CTP and transmits the compressed current tessellation pattern CCTP to the cache access control circuit S .

The cache access control circuit stores the compressed current tessellation pattern CCTP in the cache using the address ADD S . Here the cache access control circuit may store the compressed current tessellation pattern CCTP in the cache using the address ADD including a current tag generated based on the patch equation PE related to a current patch and the tessellation factor TF related to the current patch S .

The selector outputs the current tessellation pattern CTP input to the first input port IP to the domain shader in response to an indication signal indicating a cache miss MISS S . The domain shader calculates a location of each vertex using the outputs OCP and PCD of the Hull shader and the current tessellation pattern CTP output from the tessellator S .

When a previous tag the same as a current tag of a current patch is not stored in the cache but stored only in the memory or a cache miss MISS may occur. When the cache miss occurs one of the tag comparator the cache and the cache access control circuit compares a load time with a computing time S .

According to an exemplary embodiment a comparison algorithm in which the load time is compared with the computing time is embodied in the tag comparator the cache or the cache access control circuit .

The load time is an amount of time consumed in loading a previous tessellation pattern corresponding to a previous patch from the memory or to the cache and the computing time is an amount of time consumed in generating a current tessellation pattern corresponding to a current patch or a current tag.

When the load time is shorter than the computing time according to a control of the comparison algorithm the cache interface loads a previous tessellation pattern corresponding to a previous patch from the memory or to the cache S .

When a cache hit HIT occurs the cache access control circuit in response to the address ADD including a current tag reads the previous tessellation pattern PTP loaded in the cache S and transmits the previous tessellation pattern PTP to the domain shader through the selector S .

However when the load time is longer than the computing time the tessellator performs a tessellation operation using output points OCP for a current patch and tessellation factors TF for the current patch generates a current tessellation pattern CTP corresponding to the current patch according to a result of the tessellation operation S and transmits the current tessellation pattern CTP to the domain shader through the selector S .

When a previous tag the same as a current tag of a current patch is not stored in the cache but stored only in the memory or a cache miss MISS may occur.

Referring to when the load time is longer than the computing time S a tessellation operation of generating a current tessellation pattern CTP corresponding to a current patch is performed by the tessellator S a compression operation of the current tessellation pattern CTP using the compressor is performed S and the compressed current tessellation pattern CCTP is stored in the cache by the cache access control circuit S .

A tessellation device including a cache according to an exemplary embodiment of the present inventive concept may reduce a tessellation workload by selectively skipping an operation of a tessellator. Accordingly power consumption of the tessellation device may be reduced.

According to an exemplary embodiment a method of managing an operation of a GPU e.g. includes determining whether a tag based on an output of a hull shading can be retrieved within a threshold time. For example the output of the hull shading may be generated by a hull shader and include tessellation factors TF and a patch equation PE. In an exemplary embodiment it can be determined that the tag can be retrieved within the threshold time when a cache e.g. of the GPU stores the tag. In an exemplary embodiment it can be determined that the tag can be retrieved within the threshold time when the tag is present within a memory external to the cache e.g. external memory or graphics memory the tag is not present within the cache and an estimated time to load the tag from the memory to the cache is within the threshold time. In an exemplary embodiment it is determined that the tag cannot be retrieved within the time when the tag is not present in the cache or the estimated time to load the tag from the memory to the cache exceeds the threshold time.

At least one embodiment of the inventive concept can be embodied as computer readable codes having computer executable instructions on a non transitory computer readable medium. For example the operations of may be embodied as computer executable instructions. The computer readable recording medium is any data storage device that can store data as a program which can be thereafter read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks and optical data storage devices.

While the present inventive concepts have been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in forms and details may be made therein without departing from the spirit and scope of the present inventive concepts.

