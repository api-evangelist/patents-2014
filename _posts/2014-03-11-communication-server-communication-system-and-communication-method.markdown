---

title: Communication server, communication system, and communication method
abstract: A communication server includes a checking unit that checks a terminal management table, a determination unit that determines whether group identification information of a first terminal of a plurality of terminals participating in a videoconference is a same as group identification of a second terminal of the plurality of terminals based on group identification data from the terminal management table, an updating unit that updates a shared location table including shared location information indicating a location of a shared memory area shared by the same group when the group identification information of each of the first and second terminals is determined as being the same, a memory access information creation unit that creates memory access information for accessing the shared memory area, and a notification unit that sends a notification of the shared location information and the memory access information to the same group.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09215415&OS=09215415&RS=09215415
owner: RICOH COMPANY, LTD.
number: 09215415
owner_city: Tokyo
owner_country: JP
publication_date: 20140311
---
The present invention relates to a communication server connected to two or more terminals participating in a videoconference to manage communications between the terminals and relates to a communication system including the communication server and a communication method performed by the communication server.

A videoconference system to conduct videoconferences between communication terminals at remote places via a network such as the Internet is becoming increasingly popular. In this videoconference system a videoconference is conducted by exchanging video and audio data between the communication terminals.

A communication terminal in a conference room in which one of the attendants of the videoconference is present collects information including an image of the conference room and voice of the attendants converts the collected information into digital image and voice data and transmits the resulting image and voice data to a communication terminal of the other party in the videoconference system. In the other party s terminal an image is displayed on a display of the other party s terminal and voice is output by a speaker of the other party s terminal. In the videoconference system according to the related art a videoconference in appropriate conditions closely resembling reality may be conducted between the terminals at the remote places.

Further in the related art a communication terminal which transmits display data of a screen displayed on a computer to the other party s terminal via a relay device for a videoconference system so that the screen is displayed on a display of the other party s terminal is also known.

For example Japanese Laid Open Patent Publication No. 2011 254453 discloses a communication terminal which transmits video data and display data of a screen shared with another communication terminal to the other communication terminal via a relay device. This communication terminal stores relay device information of the relay device to which the terminal transmits the display data receives the display data from an external input device connected to the communication terminal and transmits the received display data to the relay device indicated by the stored relay device information. Hence the relay device transmits the display data to the other communication terminal and the screen to be shared with the communication terminal is displayed on a display of the other communication terminal.

In one embodiment the present invention provides a communication server connected to a plurality of terminals participating in a videoconference to manage communications between the plurality of terminals the communication server including a checking unit configured to check a terminal management table which associates terminal identification data to identify each of the plurality of terminals with group identification data to identify each of groups to which the plurality of terminals belong respectively a determination unit configured to determine whether group identification information of a first terminal in the plurality of terminals and group identification information of a second terminal in the plurality of terminals are a same as each other based on the group identification data an updating unit configured to update a shared location table including shared location information indicating a location of a shared memory area shared by the same group when the group identification information of the first terminal and the group identification information of the second terminal are determined as being the same as each other a memory access information creation unit configured to create memory access information for accessing the shared memory area to associate the shared memory area and the memory access information and a notification unit configured to send a notification of the shared location information and the memory access information to the same group.

Other objects features and advantages of the present invention will become more apparent from the following detailed description when read in conjunction with the accompanying drawings.

A videoconference system according to a first embodiment is explained. is a diagram showing a composition of the videoconference system according to the first embodiment.

As shown in the videoconference system includes a videoconference server and two or more sets of terminals and PCs personal computers . The videoconference system according to this embodiment is a communication system.

The videoconference server in the videoconference system according to the embodiment is a communication server and each of the terminals is a communication terminal. In the following when distinguishing between each of the terminals and the PCs is needed any one of the terminals will be referred to as terminal . . . and any one of the PCs will be referred to as PC . . . . On the other hand when distinguishing between each of the terminals and the PCs is not needed any one of the terminals . . . will be referred to as the terminal and any one of the PCs . . . will be referred to as the PC .

In this embodiment the videoconference server includes a transmission management system management system a relay device and a temporary file storage device . The management system provides a service to manage communications between the terminals participating in a videoconference. For example the management system creates a session ID to identify a session when content data including image video data and voice audio data are transmitted and received between the terminals . By this session ID the terminals which share a file in the videoconference system are identified.

The relay device provides a service to relay transmission of image data and voice data in a relay path that is selected to allow the image data and the voice data to pass through an optimal path. In this embodiment the relay device monitors a delay time and optimizes a relay path a resolution etc. of the content data. The temporary file storage device provides a service to share a file between the terminals participating in the videoconference.

As shown in the management system the relay device and the temporary file storage device in the videoconference server are implemented by an information processing device and the information processing device is referred to as the videoconference server . However the present disclosure is not limited to this embodiment. The management system the relay device and the temporary file storage device may be implemented by two or more separate information processing devices.

Next operation of the videoconference system when the terminal and the terminal share a file in the PC is explained with reference to . is a diagram for explaining operation of the videoconference system according to the first embodiment.

In the videoconference system of this embodiment when a videoconference starts the management system causes the temporary file storage device to create a shared folder. The temporary file storage device creates a shared folder that is shared by the terminals participating in the videoconference and sends a notification of a shared folder URI uniform resource identifier and account information which will be described later to the terminals and step S .

Subsequently the terminals and mount the shared folder to the shared folder URI using the account information step S . In the following mounting a shared folder is to allow the terminals and to use the shared folder in the temporary file storage device like a folder in the terminals and .

In the videoconference system of this embodiment for example when the PC writes a file in the terminal the terminal detects the writing of the file by the PC and transmits the file to the temporary file storage device step S . At this time the file is not left in the terminal after it is transmitted to the temporary file storage device .

Subsequently the temporary file storage device stores the file in the shared folder step S . Then the temporary file storage device transmits a file name stored in the shared folder to the terminal having mounted the shared folder step S . In this embodiment the content of the file is not transmitted from the temporary file storage device to the terminal until an explicit file transmission request is received. A user of the PC views the file name and if the user finds it necessary to receive the file the user may request the temporary file storage device to transmit the file to the terminal .

In this embodiment if a request for file transmission is input by the user the PC may receive the content of the file from the shared folder via the terminal and display the file on a display of the PC .

As described above in the videoconference system of this embodiment if only the PC writes a file in the terminal the file may be shared by the terminal and the terminal .

In the videoconference system according to this embodiment services which are separate from the service of the relay device to transmit content data are configured to share a file the file may be shared by the terminals without affecting the transmission reception of the content data. Further the temporary file storage device manages the file by associating the file with the session ID. Hence the temporary file storage device may manage sharing of the file between the terminals as a service that is different from a service provided by the management system .

Next the terminal of this embodiment is explained with reference to . is a diagram showing a hardware configuration of a communication terminal in the videoconference system according to the first embodiment.

As shown in the terminal includes a central processing unit CPU configured to control overall operations of the terminal a read only memory ROM storing programs for the terminal a random access memory RAM utilized as a work area of the CPU a flash memory configured to store various data such as image data or audio data a solid state drive SSD configured to control retrieval and writing of the various data in the flash memory based on the control of the CPU a medium drive configured to control retrieval or writing storing of data into a recording medium such as a flash memory an operation button operated by a user when selecting an address of the terminal a power switch for switching ON OFF of the power of the terminal and a network interface IF for transmitting data utilizing a communication network.

The terminal further includes a built in camera configured to create an image of a subject based on the control of the CPU an image sensor interface IF configured to control driving of the camera a built in microphone configured to pick up audio such as voice sound or noise a built in speaker configured to output audio a voice input output I O interface IF configured to provide an interface for the inputting outputting of the audio from the microphone and to the speaker and a display interface IF configured to transmit image data to an external display based on the control of the CPU . The terminal further includes an external device IF configured to connect various external devices to the connecting ports an alarm lamp configured to inform the user of various functional problems of the terminal a display and a bus line B such as an address bus and a data bus for electrically connecting the elements and devices with one another shown in via the bus line B.

The display is a display unit formed of liquid crystal or an organic EL electroluminescence material and configured to display images of the subject or icons for operating the terminal . Further the display is connected to the display interface via a cable . The cable may be an analog RGB VGA cable signals a component video cable a high definition multimedia interface HDMI cable or a digital video interface DVI cable.

The camera includes lenses and a solid state image sensor configured to convert light into electric charges to produce digital images videos of the subject. Examples of the solid state image sensor include a complementary metal oxide semiconductor CMOS or a charge coupled device CCD .

The external device interface may be connected via a universal serial bus USB cable with external devices such as an external camera an external microphone and an external speaker. When connecting the external camera to the external device interface via the USB the external camera is driven in priority to the built in camera . Likewise when connecting the external microphone or the external speaker to the external device interface via the USB the external microphone or the external speaker is driven in priority to the built in microphone or the built in speaker .

Note that the recording medium is removable from the terminal . In addition if the recording medium is a non volatile memory configured to retrieve or write data based on the control of the CPU the recording medium is not limited to the flash memory and may be an electrically erasable and programmable ROM EEPROM .

Further the above described programs for the terminal may be recorded in an installable format or in an executable format on a computer readable recording medium such as the recording medium to distribute such a recording medium. Further the above described programs for the terminal may be recorded on the ROM instead of the flash memory .

Next the management system of this embodiment is explained with reference to . is a diagram showing a hardware configuration of a transmission management system in the videoconference system according to the first embodiment.

As shown in the management system includes a CPU configured to control overall operations of the management system a ROM storing programs for the management system a RAM utilized as a work area of the CPU a hard disk HD configured to store various data a hard disk drive HDD configured to control retrieval or writing of the various data to the HD based on the control of the CPU a medium drive configured to control retrieval or writing storing of data into a recording medium such as a flash memory a display configured to display various information such as a cursor menus windows characters and images a network IF for transmitting data utilizing a communication network a keyboard including plural keys for inputting the characters numerals and various instructions a mouse for selecting or executing various instructions selecting items to be processed and moving the cursor a CD ROM drive configured to control retrieval or writing of data in a compact disk read only memory CD ROM as an example of a removable recording medium and a bus line B such as an address bus and a data bus for electrically connecting the elements and devices with one another shown in via the bus line B.

Note that the above described programs for the management system may be recorded in an installable format or in an executable format on a computer readable recording medium such as the recording medium or the CD ROM to distribute such a recording medium.

Further the relay device of this embodiment includes a hardware configuration similar to that of the management system and a description of the hardware configuration of the relay device is therefore omitted. Note that the ROM stores programs for controlling the relay device . In this case the programs for the relay device may be recorded in an installable format or in an executable format on a computer readable recording medium such as the recording medium or the CD ROM to distribute such a recording medium.

In this embodiment in a case where the terminals are divided into plural groups the videoconference system is configured so that relevant files may be shared by the terminals belonging to a same group. Specifically in this embodiment a shared folder to be shared by the terminals same group is associated with the terminals same group.

Next association between the terminals same group and a shared folder is explained with reference to . is a diagram for explaining association between terminals and shared folders in the videoconference system according to the first embodiment.

In a case in which terminals participate in a videoconference of session ID conference ID 01 and terminals and participate in a videoconference of session ID 02 is illustrated.

In this case the management system in the videoconference server causes the temporary file storage device to create a shared folder 01 ALL which is shared by all the terminals participating in the videoconference of session ID 01. Further the management system in the videoconference server causes the temporary file storage device to create a shared folder 02 ALL which is shared by the terminals and participating in the videoconference of session ID 02.

In the example of two additional groups are formed for the terminals . Specifically the terminals and belong to group A1 and the terminals and belong to group A2.

The videoconference server of this embodiment is configured so that the management system causes the temporary file storage device to create a shared folder associated with each of the groups. Specifically the videoconference server of this embodiment creates a shared folder 01 A1 shared by only the terminals and belonging to group A1. Similarly the videoconference server of this embodiment creates a shared folder 01 A2 shared by only the terminals and belonging to group A2.

In this embodiment when the terminals participating in the same session conference are divided into plural groups a shared folder to be shared by only the terminals belonging to each of the groups is created. Thereby in the videoconference system according to the embodiment relevant files may be shared between the terminals participating in the same session while maintaining security and the management regarding sharing of the files may be performed appropriately.

In this embodiment grouping of the terminals may be performed based on an identifier of each terminal assigned beforehand to the terminal . Alternatively grouping of the terminals may be performed based on information of each terminal assigned beforehand to the terminal .

In this embodiment the shared folder which is created by the temporary file storage device is a storage region shared by the terminals same group. In this embodiment this storage region is referred to as a shared folder. However this storage region is not limited to a shared folder. For example the storage region shared by the terminals same group may be referred to as a directory. Further relevant files may be stored in the storage region.

Next creation and association of a shared folder for each group by the management system is explained. In the following the shared folder for each group is referred to as a group shared folder.

The management system of this embodiment includes a terminal management table which is used to manage the terminals and a shared folder table which is used to store information in the shared folder associated with the terminals .

As shown in in the terminal management table a terminal ID which identifies each of the terminals is associated with a name of a group which the terminal belongs to. For example the terminal management table of this embodiment may be stored in the ROM or the RAM as the storage region of the management system .

In the terminal management table the terminal ID is associated with the name of the group which the terminal belongs to. However the present disclosure is not limited to this embodiment. For example information associated with the terminal ID may be information that identifies the group which the terminal belongs to. Namely when the terminals are divided into groups group identification information which identifies a group which each terminal belongs to is assigned. The group name in the terminal management table may be the group identification information.

The session ID may be automatically assigned by the management system each time a videoconference is held for example. The terminal ID and the group name are assigned as described above with reference to . The shared folder URI is information which identifies a shared folder created by the temporary file storage device . In this embodiment the URL indicating a location of the shared folder is referred to as the shared folder URI.

The account name and the password is account information which the terminals are notified with the shared folder together with the shared folder URI. For example the account information may be predetermined at a time of creation of the shared folder. The shared folder URI and the account information are hidden from a user and they may be converted into illegible character strings such as hash values.

In the embodiment the terminal management table is stored beforehand in the management system . However the present disclosure is not limited to this embodiment. For example when the management system and the terminal are connected the management system may create the terminal management table by reading information from the terminal .

The management system of this embodiment is configured to perform association between the terminals and the group shared folder by using the terminal management table and the shared folder table .

Next operation of the videoconference system according to the first embodiment to exchange information between the videoconference server and the terminal is explained with reference to . is a sequence diagram for explaining the operation of the videoconference server according to the first embodiment.

When starting a videoconference in the videoconference system the management system of the videoconference server establishes a session with the terminal which participates in the videoconference step S . Subsequently the management system checks the terminal management table and determines a group shared folder to be created step S . A detailed process of step S will be described later.

After the group shared folder to be created is determined in step S the management system updates the shared folder table step S . Subsequently the management system creates account information of the group shared folder and the group shared folder in the temporary file storage device step S . In this embodiment in step S a shared folder which is shared by all the terminals participating in the same conference may be created in the temporary file storage device in addition to the group shared folder.

Subsequently the management system checks the shared folder table and the terminal is notified of the shared folder URI of the shared folder the shared folder URI of the group shared folder and the account information for accessing the shared folder step S . Subsequently the terminal mounts the shared folder and the group shared folder in the temporary file storage device step S . Mounting of the shared folder will be described later.

In the above embodiment the shared folder which is shared by all the terminals participating in the same videoconference is created in addition to the group shared folder. However the present disclosure is not limited to this embodiment. Only the group shared folder may be created without creating the shared folder.

In the above embodiment after the shared folder table is updated in step S the corresponding shared folder is created in step S. Alternatively a reverse process of step S and step S may be performed. Namely after the shared folder and the group shared folder are created by the temporary file storage device the shared folder table may be updated.

Next a detailed process of step S is explained with reference to . is a flowchart for explaining a process to determine a shared folder to be created in the videoconference system according to the first embodiment.

It is assumed that plural terminals are connected to the videoconference server upon a start of the videoconference. The management system checks the terminal management table and determines whether a terminal belonging to a group identical to a group of the terminal newly participating in the videoconference exists among the plural terminals step S .

When the terminal is determined as belonging to the group in step S the group shared folder to be created by the temporary file storage device is determined step S and the process of step S is completed. When the terminal is determined as not belonging to the group in step S the process of step S is completed without determining the group shared folder to be created.

Referring back to a concrete example is explained in order to facilitate the understanding of the process shown in . Suppose a case in which the terminal is newly connected to the videoconference server to participate in the videoconference of session ID 01. It is assumed that the session between the terminal and the videoconference server is already established at this time.

In this case the management system checks the terminal management table and receives a terminal ID 0002 of the terminal and a group name associated with the terminal ID of the terminal . In this example the group name of the terminal is A1 as shown in . Subsequently the management system determines whether a terminal belonging to group A1 identical to the group of the terminal newly participating in the videoconference exists among the terminals already participating in the videoconference of session ID 01. In this example the terminal is determined as belonging to group A1 and already participating in the videoconference.

Therefore in the above case the management system causes the temporary file storage device to create a group shared folder which is shared by the group A1 terminals . Then the management system sends a notification of the shared folder URI and the account information of the created group shared folder to the terminals and belonging to group A1.

Next mounting of a shared folder is explained with reference to . is a diagram for explaining mounting of a shared folder in the videoconference system according to the first embodiment.

Suppose that the shared folder URI of the temporary file storage device is represented by http kaigi.com share 01 A1 . The terminals and designate this shared folder URI and mount the group shared folder and the group shared folder is mounted on the terminals and . For example if the terminals and designate a D drive of each terminal as a mounting destination the group shared folder is mounted on each of the D drives of the terminals and .

For example when a file file.txt is stored in the group shared folder of the temporary file storage device a file name of file.txt on the corresponding D drive of the terminals and is displayed. In this case the substance of the file is stored in the group shared folder of the temporary file storage device .

Next a case in which the terminal participates midway through a videoconference in the videoconference system according to the first embodiment is explained. A process performed by the videoconference system when the terminal participates midway through the videoconference is essentially the same as that shown in except the process of step S. When creation of a group shared folder is not needed the management system performs only the updating of the shared folder table in step S.

The process performed by the videoconference system when the terminal participates midway through the videoconference is explained. is a flowchart for explaining a process to determine a shared folder to be created when the terminal participates midway through the videoconference in the videoconference system according to the first embodiment.

After a session between the terminal participating midway through the videoconference and the videoconference server is established in the videoconference system the management system determines whether a terminal whose group is the same as the group of the terminal of midway participation exists among the terminals already participating in the videoconference step S . Specifically the management system checks the terminal management table and the shared folder table and determines whether a terminal whose group is the same as the group of the terminal of midway participation exists among the terminals already participating in the videoconference.

When the terminal s same group is determined as not existing in step S the management system terminates the process of . When the terminal s same group is determined as existing in step S the management system determines whether a group shared folder associated with the group of the terminal of midway participation is not yet created by the temporary file storage device step S .

When the corresponding group shared folder is already created by the temporary file storage device in step S the management system terminates the process of . When no corresponding group shared folder is created by the temporary file storage device in step S the management system creates the corresponding group shared folder step S and terminates the process of .

Next updating of the shared folder table when a terminal participates midway through the videoconference is explained with reference to . are diagrams for explaining updating of the shared folder table.

In the example of it is assumed that the terminal participates midway through the videoconference of session ID 01 in which the terminals are participating. shows a state of the shared folder table A before updating and shows a state of the shared folder table B after updating.

In the shared folder table A shown in among the terminals participating in the videoconference of session ID 01 the terminal and the terminal belong to group A1. Therefore a shared folder shared by all the terminals participating in the videoconference of session ID 01 and a group shared folder associated with group A1 are created in the temporary file storage device .

When the terminal participates midway through the videoconference of session ID 01 the management system checks the terminal management table and detects the group which the terminal belongs to. As shown in the terminal belongs to group A2. Therefore the management system determines whether a terminal which belongs to group A2 exists among the terminals participating in the videoconference. In the shared folder table B shown in the terminal belongs to group A2. Therefore the management system creates a group shared folder associated with group A2 and updates the shared folder table A thereby resulting in the shared folder table B.

Accordingly even when the terminal participates midway through the videoconference the sharing of data between the terminals including the terminal of midway participation may be controlled appropriately.

In the above embodiment the shared folder and the group shared folder created by the temporary file storage device may be deleted after the videoconference is completed or may be left in the temporary file storage device without change.

It is assumed that when the videoconference of session ID 01 is completed group shared folders associated with group A1 and group A2 have been created by the temporary file storage device . In this case the management system checks the table deletes the group shared folder associated with group A1 and leaves the group shared folder associated with group A2 in the temporary file storage device in accordance with the content of the table . Deleting a shared folder is to return the shared folder state of the storage region in the temporary file storage device back to a normal storage region state.

Next a videoconference system A according to a second embodiment is explained. The videoconference system A is essentially the same as the videoconference system according to the first embodiment except that a group shared folder is created by a device other than videoconference server . In the following only the points of the second embodiment differing from the first embodiment will be described. The elements and devices of the videoconference system A which are essentially the same as corresponding elements and devices of the video conference system are designated by the same reference numerals and a description thereof will be omitted.

In the videoconference system A shown in the terminals and may utilize a video and audio router in the private network the intranet as a relay device to carry out a videoconference between the terminals and without transmitting video and audio data outside. Therefore in this case the temporary file storage device arranged in the in company LAN may improve the security at the time of file sharing.

In the videoconference system A a shared folder may be created in both the temporary file storage device connected to the intranet and the temporary file storage device connected to the Internet.

In the example of a group shared folder 01 A2 associated with group A2 to which the terminals and belong is created in the temporary file storage device of the in company server . For example in the terminal management table the terminal ID which identifies the terminal may be associated with the type of network to which the terminal is connected.

Next the terminal management table in the videoconference system A according to the second embodiment is explained with reference to . is a diagram showing an example of a terminal management table in the videoconference system A according to the second embodiment.

As shown in in the terminal management table a terminal ID which identifies the terminal is associated with the type of network to which the terminal is connected and a group name of a group which the terminal belongs to. Namely in this embodiment the network type and the group name constitute the group identification information assigned to the terminal .

Next a network management table in the videoconference system A according to the second embodiment is explained with reference to . is a diagram showing an example of a network management table in the videoconference system A according to the second embodiment.

As shown in in the network management table an intranet ID which identifies the intranet is associated with an intranet URI which is information which identifies a location of the intranet.

In this embodiment the management system is configured to create a group shared folder by checking the terminal management table and the intranet management table .

Next operation of the videoconference system A according to the second embodiment to exchange information between the videoconference server and the terminal is explained with reference to . is a sequence diagram for explaining the operation of the videoconference server according to the second embodiment.

When starting a videoconference in the videoconference system A the management system of the videoconference server establishes a session with the terminal which participates in the videoconference step S . Subsequently the management system determines a group shared folder to be created by checking the terminal management table step S . A detailed process of step S will be described later.

After the group shared folder to be created is determined in step S the management system updates the shared folder table step S . Subsequently the management system creates account information of the group shared folder and the group shared folder in the temporary file storage device step S . In this embodiment in step S a shared folder which is shared by all the terminals participating in the same videoconference may be created in the temporary file storage device in addition to the group shared folder.

Further when the location of the group shared folder to be created is the in company server the management system creates account information of the group shared folder and the group shared folder in the temporary file storage device of the in company server step S .

Subsequently the management system checks the shared folder table and the terminal is notified of the shared folder URI of the shared folder the shared folder URI of the group shared folder and the account information for accessing the shared folder step S . Subsequently the terminal mounts the shared folder and the group shared folder in the temporary file storage device step S . Further the terminal mounts the group shared folder in the temporary file storage device step S .

Next a detailed process of step S is explained with reference to . is a flowchart for explaining a process to determine a shared folder to be created in the videoconference system A according to the second embodiment.

As shown in the management system checks the terminal management table and determines whether a newly participating terminal belongs to a group identical to an existing group of a terminal in the terminals participating in the videoconference step S .

When the terminal is determined as belonging to the group in step S the management system checks the terminal management table and determines whether the type of network of the terminal s same group is the same as that of the newly participating terminal step S . When the terminal s same group is determined as not existing in step S the management system terminates the process of without determining the group shared folder to be created.

When the type of network of the terminal s same group is the same as that of the newly participating terminal the intranet in step S the management system determines the group shared folder is to be created on the intranet step S . When the type of network of the terminal s same group is not the same as that of the newly participating terminal the Internet in step S the management system determines the group shared folder is to be created on the Internet step S .

Referring back to and a concrete example is explained in order to facilitate the understanding of the process shown in . Suppose a case in which the terminal is newly connected to the videoconference server in order to participate in the videoconference of session ID 01. It is assumed that the session between the terminal and the videoconference server is already established at this time.

In this case the management system checks the terminal management table and receives a terminal ID 0002 of the terminal and a group name associated with the terminal ID of the terminal . In this example the group name of the terminal is A1 as shown in . Subsequently the management system determines whether a terminal belonging to group A1 identical to the group of the terminal newly participating in the videoconference exists among the terminals already participating in the videoconference of session ID 01. In this example the terminal is determined as belonging to group A1 and participating in the videoconference.

Subsequently the management system checks the terminal management table and determines whether the type of network of the terminal s same group is the same as that of the newly participating terminal . In this example the type of network of the terminal is the Internet the type of network of the terminal is also the Internet and the network types of the two terminals are in agreement. Therefore the management system determines the group shared folder to be created in the temporary file storage device and to be shared by the group A1 terminals and . Then the management system sends to the group A1 terminals and a notification of the shared folder URI and the account information of the created group shared folder.

Next a case in which the terminal participates midway through the videoconference in the videoconference system A according to the second embodiment is explained. A process performed by the videoconference system A when the terminal participates midway through the videoconference is essentially the same as that shown in except the process of step S in . When creation of a group shared folder is not needed the management system performs only the updating of the shared folder table in step S.

Next the process performed by the videoconference system A when the terminal participating midway through the videoconference is explained. is a flowchart for explaining a process to determine a shared folder to be created when a terminal participates midway through the videoconference in the videoconference system A according to the second embodiment.

After a session between the terminal participating midway through the videoconference and the videoconference server is established the management system determines whether a terminal whose group is the same as the group of the terminal of midway participation exists among the terminals already participating in the videoconference step S . Specifically the management system checks the terminal management table and the shared folder table and determines whether a terminal whose group is the same as the group of the terminal of midway participation exists among the terminals already participating in the videoconference.

When the terminal s same group is determined as not existing in step S the management system terminates the process of . When the terminal s same group is determined as existing in step S the management system determines whether a group shared folder associated with the group of the terminal of midway participation is not yet created by the temporary file storage device or the temporary file storage device step S .

When the corresponding group shared folder is already created in step S the management system terminates the process of . When no corresponding group shared folder is created in step S the management system checks the terminal management table and determines whether the type of network of the terminal s same group is the intranet step S .

When the type of network of the terminal s same group is the intranet in step S the management system determines the group shared folder is to be created on the intranet step S . When the type of network of the terminal s same group is not the intranet in step S the management system determines the group shared folder is to be created on the Internet step S .

As described above in this embodiment the location where the group shared folder shared by the terminals same group is created may be determined based on the kind of connection between the terminal and the temporary file storage device or . For example in this embodiment the group shared folder may be created by the in company server on the intranet.

In a case in which a videoconference is held between several different companies using the videoconference system A the terminals for each company may be made to belong to one group and a group shared folder associated with each group may be created by an in company server of a corresponding group. For example in this embodiment the terminals may be divided into a group hosting confidential data and a group hosting non confidential data and a group shared folder associated with the former group may be created on the intranet.

In the videoconference system according to the second embodiment the security regarding sharing of data may be increased.

Next a videoconference system B according to a third embodiment is explained. The videoconference system B is essentially the same as the videoconference systems and A according to the first and second embodiments except that a communication terminal A in which the terminal and the PC are integrated is utilized. In the following only the points of the videoconference system B differing from the videoconference system will be described. The elements and devices of the videoconference system B which are essentially the same as corresponding elements and devices of the video conference system are designated by the same reference numerals and a description thereof will be omitted.

For example the terminal A is a terminal in which a microphone a speaker a camera etc. are integrated on a general purpose computer. In this embodiment a general purpose computer is used as the terminal A including no dedicated terminal. Examples of the general purpose computer include a smart phone a mobile phone a tablet terminal etc.

In this embodiment grouping of the terminals A is performed based on attribute information indicating attributes of each terminal A. Namely in this embodiment the attribute information indicating the attributes of each terminal A constitutes the group identification information assigned to the terminal A.

In this embodiment a user ID assigned to the terminal A is used as the terminal ID an office name of a company office to which a corresponding user of the user ID belongs is used as the first attribute and a section name of a company section to which the corresponding user of the user ID belongs is used as the second attribute.

In this embodiment information of any other type that identifies the terminal A may be used instead as the terminal ID. Namely in the terminal management table the information of any other type that identifies the terminal A may be associated with the first attribute and the second attribute as a key.

For example the management system may be configured such that the user ID and the information which identifies the terminal A used by a corresponding user of the user ID are associated and stored and the terminal A may be designated using the user ID. The information which identifies the terminal A may be the terminal ID or may be the information IP address which indicates a location of the terminal A.

In this embodiment the management system determines the terminals A with the same office name and the same section name as belonging to one group. For example in the example of the terminal A of USER 1 user ID 1 and the terminal A of USER 2 user ID 2 are associated with the same office name and the same section name. Therefore the management system determines the two terminals A as belonging to one group and creates a corresponding group shared folder. Alternatively the management system may determine the terminals A associated with the same section name only as belonging to one group.

As described above in this embodiment the attribute information is used as the information for grouping of the terminals A and the videoconference system B according to this embodiment may create a group shared folder based on the attribute information.

Next a videoconference system C according to a fourth embodiment is explained. The videoconference system C is essentially the same as the videoconference system according to the first embodiment except that a shared folder name is created when a shared folder is created. In the following only the points of the videoconference system C differing from the videoconference system will be described. The elements and devices of the videoconference system C which are essentially the same as corresponding elements and devices of the video conference system are designated by the same reference numerals and a description thereof will be omitted.

The folder name creation unit is configured to create a name of a shared folder which is created by the management system A. The management system A is configured to notify to the terminal the shared folder URI the account information and the shared folder name created by the folder name creation unit .

Next creation of a shared folder name by the folder name creation unit is explained. For example the folder name creation unit may create a folder name for each of a shared folder and a group shared folder. Note that the shared folder is a folder shared by all the terminals participating in a videoconference of a certain session ID and the group shared folder is also a shared folder for each of the groups of the terminals participating in a videoconference of a certain session ID.

For example the folder name creation unit includes a table associating a setting method and a folder name of a shared folder and a table associating a setting method and a folder name of a group shared folder. The folder name creation unit checks these tables and creates a shared folder name.

For example when creating a shared folder name by checking the table the folder name creation unit may display on the terminal a list of folder name options included in the table and may prompt a user of the terminal to select a folder name from the list of folder name options displayed on the terminal so that the selected folder name is created. Subsequently the folder name creation unit may send to the terminal a notification of the selected folder name the account information and the URI of the shared folder. When the folder name is received at the terminal the folder name associated with the shared folder is displayed on the terminal .

The FOLDER NAME column of the table for the FIXED NAME setting method includes three options GROUP NAME ACCESS RESTRICTED FOLDER name and USER DEFINED name which is arbitrarily predetermined by the user .

The FOLDER NAME column of the table for the ACCESSIBLE TERMINAL ID setting method includes one or more terminal IDs. For example when the ACCESSIBLE TERMINAL ID setting method is designated the folder name creation unit creates the one or more terminal IDs received from the table as the group shared folder name. Note that a terminal ID of the user s terminal may also be included in the FOLDER NAME column of the table for the ACCESSIBLE TERMINAL ID setting method in addition to the one or more terminal IDs.

The FOLDER NAME column of the table for the ACCESSIBLE TERMINAL NAME setting method includes one or more terminal names. For example when the ACCESSIBLE TERMINAL NAME setting method is designated the folder name creation unit creates the one or more terminal names received from the table as the group shared folder name. Note that a terminal name of the user s terminal may also be included in the FOLDER NAME column of the table for the ACCESSIBLE TERMINAL NAME setting method in addition to the one or more terminal names.

For example the folder name creation unit may be configured to display on the terminal a list of the folder name setting methods from the table and prompt a user to select a folder name setting method from the list of the folder name setting methods displayed. The folder name creation unit may be configured to create a group shared folder according to the selected folder name setting method. Note that the folder name setting method may be selected beforehand prior to a start of a videoconference.

In the above embodiment the table in which the method of setting a shared folder name is stored and the table in which the method of setting a group shared folder name is stored are provided separately. The present disclosure is not limited to this method. For example the table and the table may be provided as a combined table.

Next operation of the videoconference server A according to the fourth embodiment is explained with reference to . is a sequence diagram for explaining operation of the videoconference server A. In the videoconference server A the management system A includes the folder name creation unit not illustrated .

The process of steps S and S in is the same as the process of steps S and S in and therefore a description thereof will be omitted.

As shown in after the group shared folder to be created is determined in step S the management system A causes the folder name creation unit to check the table and create a shared folder name based on the selected folder name setting method step S . Subsequently the management system A updates the shared folder table step S . A detailed process of updating the shared folder table in step S will be described later.

Subsequently the management system A creates account information of the group shared folder and the group shared folder in the temporary file storage device step S .

Subsequently the management system A checks the shared folder table and notifies to the terminal the shared folder URI of the shared folder the shared folder URI of the group shared folder the account information for accessing the shared folder and the created group shared folder name step S .

Subsequently the terminal mounts the group shared folder and its folder name in the temporary file storage device step S . At this time the group shared folder and its folder name are displayed on the terminal .

Next updating of the shared folder table is explained with reference to . are diagrams for explaining updating of the shared folder table in the videoconference server A according to the fourth embodiment. shows a state of the shared folder table C before updating and shows a state of the shared folder table D after updating.

In the example of it is assumed that the terminal participates midway through the videoconference of session ID 01 in which the terminals already participate.

In the shared folder table C shown in among the terminals participating in the videoconference of session ID 01 the terminals and belong to group A1. Therefore a shared folder shared by all the terminals participating in the videoconference of session ID 01 and a group shared folder associated with group A1 are created in the temporary file storage device .

Further in the shared folder table C an additional column FOLDER NAME is provided to indicate a shared folder name. In the example of the shared folder table C the folder name of the shared folder and the folder name of the group shared folder associated with group A1 both created by the folder name creation unit are included in the FOLDER NAME column.

Specifically in the example of ALL is indicated as the folder name of the shared folder and the terminal IDs 001 002 of the terminals which may access the group shared folder associated with group A1 are indicated as the folder name of the group shared folder associated with group A1.

If a terminal participates midway through the videoconference the management system A checks the terminal management table and obtains a group name of a group which the terminal belongs to. In the example the terminal belongs to group A2 and the management system A obtains A2 from the terminal management table .

Subsequently the management system A determines whether a terminal belonging to group A2 exists among the terminals already participating in the videoconference. In the example of the terminal belonging to group A2 exists among the terminals .

Hence the management system A creates a group shared folder associated with group A2 and a folder name of the group shared folder and updates the shared folder table C to create the shared folder table D.

In the shared folder table D of the folder name 003 004 of the terminals which may access the group shared folder associated with group A2 is indicated as a folder name of the group shared folder associated with group A2.

In this embodiment the terminal is notified of the folder name the shared folder URI and the account information and the group shared folder and its folder name are displayed on the terminal .

As described above in this embodiment the folder name is created and the terminal is notified and a user of the terminal may easily recognize folder names or IDs of shared folders on an accessible terminal that may be accessed by the user s terminal with a display indication thereof. Further the user of the terminal may easily designate by visual inspection the shared folders on the accessible terminal that may be accessed by the user s terminal.

In this embodiment the folder name or ID is information identifying a group shared folder shared memory area shared for each group. Hence the folder name creation unit creates the identification information of the shared memory area and functions to associate the identification information with the shared folder location information URI indicating the location of the shared memory area.

Further in this embodiment the information indicating whether a group shared folder exists on the Internet or on the intranet may be included in a folder name. For example a specific character string intra  may be placed in front of the folder name only when the group shared folder exists on the intranet. In this case for example when a group shared folder of attribute A1 exists on the intranet the information to be placed in front of the folder name of the group shared folder may be represented by intra A1 .

Further in this embodiment a numeral character indicating the number of terminals which may be accessed by the user s terminal may be placed in front of a folder name so that a user of the terminal may grasp the number of the accessible terminals on which a group shared folder is created. For example in the above example the group shared folder of attribute A1 may be accessed from two terminals terminal ID 003 and terminal ID 004. In such a case the folder name creation unit may create 2  A1 company as the group shared folder name which means that the group shared folder of attribute A1 may be accessed from the two terminals terminal ID 003 and terminal ID 004 .

Next a videoconference server A according to a fifth embodiment is explained. The videoconference server A according to this embodiment is essentially the same as the videoconference server A according to the fourth embodiment except that a shared folder name is created by the terminal . In the following only the points of the videoconference server A according to the fifth embodiment differing from the videoconference server A according to the fourth embodiment will be described. The elements and devices of the videoconference server A according to the fifth embodiment which are essentially the same as corresponding elements and devices of the videoconference server A according to the fourth embodiment are designated by the same reference numerals and a description thereof will be omitted.

The process of steps S S in is the same as the process of steps S S in and therefore a description thereof will be omitted.

As shown in following step S the management system A of this embodiment checks the shared folder table and notifies to the terminal the information associated with the terminal ID step S . Specifically the management system A sends to the terminal a notification of the group name the shared folder URI the account name and the password which are associated with the terminal ID.

Subsequently the terminal creates folder names of the shared folders based on the received information step S . Specifically the terminal creates a folder name of the shared folder and a folder name of the group shared folder.

In this embodiment the tables and see are stored in the terminal and when the notification is received from the management system A in step S the terminal checks the tables and and creates the folder names. Note that the setting method of the folder names may be selected beforehand in the terminal .

Subsequently the terminal mounts the shared folder and the group shared folder in the temporary file storage device step S .

The terminal may send a notification of the folder names to the management system after the folder names are created. After the folder names are received from the terminal the management system may update the shared folder table by adding the received folder names to the shared folder table .

As described in the foregoing in the communication server according to the present invention data may be safely shared between the terminals of the communication partners.

The communication server according to the present invention may be implemented in any convenient form for example using dedicated hardware or a mixture of dedicated hardware and software. The present invention may be implemented as computer software implemented by one or more networked processing apparatuses. The network may comprise any conventional terrestrial or wireless communications network such as the Internet. The processing apparatuses may comprise any suitably programmed apparatuses such as a general purpose computer personal digital assistant mobile telephone such as a WAP or 3G compliant phone and so on. Since the present invention may be implemented as software each and each aspect of the present invention thus encompasses computer software implementable on a programmable device.

The computer software may be provided to the programmable device using any storage medium for storing processor readable code such as a floppy disk a hard disk a CD ROM a magnetic tape device or a solid state memory device.

The hardware platform includes any desired kind of hardware resources including for example a central processing unit CPU a random access memory RAM and a hard disk drive HDD . The CPU may be implemented by any desired kind of any desired number of processors. The RAM may be implemented by any desired kind of volatile or non volatile memory. The HDD may be implemented by any desired kind of non volatile memory capable of storing a large amount of data. The hardware resources may additionally include an input device an output device and a network device depending on the type of the apparatus. Alternatively the HDD may be provided external to the apparatus as long as the HDD is accessible from the apparatus. In this example the CPU such as a cache memory of the CPU and the RAM may operate as a physical memory or a primary memory of the apparatus while the HDD may operate as a secondary memory of the apparatus.

The communication server according to the present invention is not limited to the above described embodiments and variations and modifications may be made without departing from the scope of the present invention.

The present application is based upon and claims the benefit of priority of Japanese Patent Application No. 2013 049213 filed on Mar. 12 2013 the contents of which are incorporated herein by reference in their entirety.

