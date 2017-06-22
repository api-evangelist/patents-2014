---

title: Method and system for audio channel setup
abstract: A method and system for audio channel setup for an electronic device connected with one or more external electronic devices is provided. The method includes configuring audio channel information for the electronic device and the one or more external electronic devices, determining whether a master device is changed between the electronic device and one or more external electronic devices, and sending, when the master device is changed, the configured audio channel information to a new master device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09467794&OS=09467794&RS=09467794
owner: Samsung Electronics Co., Ltd
number: 09467794
owner_city: 
owner_country: KR
publication_date: 20140902
---
This application claims priority under 35 U.S.C. 119 a to a Korean Patent Application Serial No. 10 2013 0104125 which was filed on Aug. 30 2013 in the Korean Intellectual Property Office the entire disclosure of which is incorporated herein by reference.

The present invention relates generally to a method and system for setting up an audio channel between wirelessly connected electronic devices.

Modern electronic devices such as a smartphone tablet personal computer Portable Multimedia Player PMP Personal Digital Assistant PDA and laptop personal computer and wearable devices such as a wrist watch and Head Mounted Display HMD support not only call handling functions but also other functions related to for example games Social Networking Services SNS Internet access multimedia still and moving images and music playback.

It is possible to wirelessly interconnect electronic devices establish an audio channel between the devices and reproduce sounds using the audio channel.

However after an audio channel is established between electronic devices using a conventional method it is difficult to change the settings of the audio channel when an electronic device is moved or is detached from the audio channel.

The present invention has been made to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present invention is to provide a method and system for audio channel setup for an electronic device connected with one or more external electronic devices.

In accordance with an aspect of the present invention an audio channel setup method is provided. The audio channel setup method includes configuring audio channel information for the electronic device and one or more external electronic devices determining whether a master device is changed between the electronic device and the one or more external electronic devices and sending when the master device is changed the configured audio channel information to a new master device.

In accordance with another aspect of the present invention a audio channel setup method is provided. The audio channel setup method includes configuring audio channel information for the electronic device and one or more external electronic devices checking whether a position of the electronic device is moved a master device is changed between the electronic device and external electronic devices at least one of the one or more external electronic devices is disconnected from the electronic device or at least one of the one ore more external electronic devices is newly connected to the electronic device and reconfiguring or sending the configured audio channel information when the position of the electronic device is moved the master device is changed between the electronic device and the one or more external electronic devices at least one of the one or more external electronic devices is disconnected from the electronic device or at least one of the one or more external electronic devices is newly connected to the electronic device.

In accordance with another aspect of the present invention a system for audio channel setup is provided. The audio channel setup system includes an electronic device and one or more external electronic devices wherein the electronic device is connected with the one or more external electronic devices is designated as a master device identifies positions of the one or more external electronic devices configures audio channel information and checks whether a master device designation is changed and where the one or more external electronic devices are designated as slave devices so that audio channel settings and volume settings thereof are controlled by the electronic device.

Hereinafter embodiments of the present invention are described in detail with reference to the accompanying drawings. Various specific details are included to assist in understanding but these are to be regarded as merely exemplary. Those skilled in the art will recognize that various changes and modifications of the embodiments described herein can be made without departing from the scope and spirit of the present invention. The same reference symbols are used throughout the drawings to refer to the same or like parts.

Referring to the electronic device is described as a representative one of multiple electronic devices and which have identical or similar configurations.

In various embodiments of the present invention the electronic devices include a smartphone a tablet computer a Portable Multimedia Player PMP a Personal Digital Assistant PDA a laptop computer and a wearable device such as a wrist watch and Head Mounted Display HMD .

The electronic device includes a display unit a user input unit a sensor unit a communication unit a storage unit an audio unit and a control unit .

The display unit is configured to display images or data for the user. The display unit includes a display panel. The display panel may be a Liquid Crystal Display LCD or an Active Matrix Organic Light Emitting Diode AMOLED display. The display unit further includes a controller to control the display panel. The display panel may be configured to be flexible transparent or wearable.

The display unit may be combined with a touch panel to form a touchscreen. For example such a touchscreen may include a display panel and a touch panel stacked together as an integrated module.

The user input unit is configured to receive various user commands. The user input unit includes one or more of a touch panel a pen sensor and keys .

The touch panel recognizes a user touch input using capacitive resistive infrared or ultrasonic technology. The touch panel includes a controller. When the touch panel is a capacitive type it recognizes not only direct touch input but also proximity input. The touch panel may further include a tactile layer to present a tactile response to the user. The pen sensor is realized using a pen recognition sheet and is manipulated in a manner similar to the touch panel . The keys include mechanical keys and touch keys. For example the mechanical keys include a power button formed at one side of the electronic device for turning on the display unit a volume button formed at another side thereof for volume adjustment and a home button formed at the center of the lower end of the display unit for restoring the home screen. The touch keys include a menu key formed at one portion of the lower end of the display unit for presenting menu items related to the currently displayed screen and a cancel key formed at another portion of the lower end of the display unit for returning to the previous screen.

The sensor unit includes a gyro sensor an acceleration sensor and the like. In one embodiment the sensor unit senses the position of the electronic device in three dimensional space and sends the sensed position information to the control unit which is then aware of the position of the electronic device in three dimensional space.

The communication unit includes one or more of a mobile communication module a wireless Internet module a short range communication module and a position information module .

The mobile communication module sends and receives radio signals to and from a base station an external terminal or a server on a mobile communication network. The radio signals include various types of data corresponding to a voice call a video call and a text or multimedia message.

The wireless Internet module is used for wirelessly accessing the Internet. Technologies such as Wi Fi Wireless Local Area Network WLAN Wireless Broadband WiBro Worldwide Interoperability for Microwave Access WiMAX and High Speed Downlink Packet Access HSDPA is utilized for wireless Internet access.

The short range communication module is used for short range communication. Technologies such as Bluetooth Radio Frequency Identification RFID Infrared Data Association IrDA Ultra Wideband UWB and ZigBee may be utilized for short range communication.

The position information module performs a function to acquire or identify the position of the electronic device . The position information module obtains position information using a Global Navigation Satellite System GNSS . The term GNSS refers to a system of satellites that revolve around the Earth and transmit reference signals enabling specific electronic receivers to determine their geo spatial positions. Systems such as the Global Positioning System GPS USA the Galileo system European Union the Global Orbiting Navigational Satellite System GLONASS Russia the COMPASS system China and the Quasi Zenith Satellite System QZSS Japan are regarded as a GNSS.

The communication unit may further include a network interface or modem e.g. LAN card to enable the electronic device to communicate with various networks such as the Internet a Local Area Network LAN a Wide Area Network WAN a telecommunication network a cellular network a satellite network and a Public Switched Telephone Network PSTN .

The communication unit may be aware of the position of the electronic device using position information generated by the position information module . The control unit identifies the position of the electronic device in three dimensional space on the basis of position information generated by the position information module .

The electronic device uses the communication unit to identify relative positions of other electronic devices and . For example relative positions between the electronic device and other electronic devices and are identified through measurement of Received Signal Strength Indication RSSI Time of Arrival ToA or Time Difference of Arrival TDOA .

The internal memory may be composed of a volatile memory such as a dynamic random access memory DRAM static RAM SRAM or synchronous dynamic RAM SDRAM a non volatile memory such as a programmable read only memory PROM one time programmable ROM OTPROM erasable programmable ROM EPROM electrically erasable programmable ROM EEPROM mask ROM or flash ROM a hard disk drive HDD and a solid state drive SSD . The control unit loads instructions or data received from a non volatile memory or another component onto a volatile memory for processing. The control unit also saves data received from or generated by another component in a non volatile memory for storage.

The external memory may be composed of a memory card such as Compact Flash CF Secure Digital SD Micro Secure Digital micro SD Mini Secure Digital mini SD or extreme Digital xD and a memory stick.

The storage unit stores an operating system OS for controlling the operation of the electronic device and the application programs for user functions. The operating system includes a kernel middleware APIs and the like. Examples of operating systems include Android iOS Windows Symbian Tizen and Bada. The storage unit stores audio channel settings configured by the control unit or stores weights or priorities needed for audio channel setup as a database.

The kernel of the operating system includes a resource manager for resource management and device drivers. The resource manager includes a process manager a memory manager a file system manager and the like and performs control allocation and release of system resources. The device drivers enable various components of the electronic device to be accessed and controlled through software. To this end each device driver is divided into an interface and a driver module provided by a hardware vendor. Examples of device drivers include a display driver camera driver Bluetooth driver shared memory driver USB driver keypad driver Wi Fi driver audio driver and inter process communication IPC driver.

The middleware is composed of multiple modules pre implemented to support functions commonly needed by various applications. The middleware provides commonly needed functions through APIs so that limited system resources of the electronic device may be efficiently utilized. Middleware includes at least one of an application manager window manager multimedia manager resource manager power manager database manager and package manager. The middleware may further include at least one of a connectivity manager notification manager location manager graphics manager and security manager according to embodiments of the present invention. The middleware may include a runtime library and other libraries. The runtime library is a library module that is used by a compiler to add new functions through a programming language at runtime. For example the runtime library may support functions related to input output memory management and arithmetic computation. The middleware is extended by adding a new middleware module that is created by combining existing middleware modules together according to a new functionality. The middleware is composed of distinct modules specialized according to the operating system.

An application programming interface API refers to a set of application programming functions. APIs have different configurations according to operating systems. For example in the case of Android or iOS one API set may be provided on a platform basis and in the case of Tizen two or more API sets may be provided.

An application performs one or more functions using a corresponding application program. Applications may be divided into preloaded applications and third party applications. Examples of applications include a home application supporting the home screen Short Message Service SMS application Multimedia Message Service MMS application Instant Message IM application browser application camera application alarm application contacts application voice dialing application email application calendar application media player application album application and clock application. The storage unit stores a variety of data generated by the communication unit the user input unit the audio unit and the control unit .

The audio unit converts an audio signal into an electrical signal and vice versa. For example the audio unit converts an audio signal from a microphone into an electrical signal for input or converts an electrical signal into an audio signal for output to a speaker receiver or earphone.

The control unit executes the operating system and application programs controls various hardware and software components processes various data including multimedia and performs various steps. The control unit may be realized as a System on Chip SoC and further includes a graphics processing unit GPU .

In one embodiment of the present invention when the electronic device is wirelessly connected with at least one of external electronic devices and the control unit identifies the position of the connected external electronic device relative to the position of the electronic device on the basis of position information obtained through the sensor unit and the communication unit . After connection establishment the control unit designates the electronic device as a master device and designates the connected external electronic device as a slave device. When the electronic device is designated as a master device it controls an audio channel setting operation and volume control operation of the external electronic device designated as a slave device. The control unit sets audio channel information of the electronic device and the external electronic devices and . The control unit sends sound information stored in the electronic device to one or more of the external electronic devices and according to the audio channel information. Here the electronic device sends sound information to one or more of the external electronic devices or through the communication unit . The control unit monitors movement in the position of the electronic devices or change in master designation of the electronic device and disconnection of the external electronic device or from the electronic device . When at least one of the electronic devices and is moved when master designation of the electronic device is changed or when at least one of the external electronic devices and is disconnected from the electronic device the control unit sends audio channel information to the external electronic devices and or reconfigures the audio channel information.

For example audio channel layout information as shown in Table 1 is stored as a database in the storage unit and the control unit configures the audio channel with reference to the database stored in the storage unit .

Referring to when the electronic devices and are wirelessly interconnected each device identifies its audio channel designation and produces sounds in a direction toward the user according to the audio channel designation. For example in the case of a 5.1 channel layout the audio channel is configured so that the electronic devices and placed in front of the user act respectively as a left speaker a center speaker and a right speaker and the electronic devices and placed behind the user act respectively as a rear left speaker a woofer and a rear right speaker. Here when the electronic device is designated as a master device and the other electronic devices and are designated as slave devices the electronic device designated as the master device configures and controls the audio channel of the electronic device and the other electronic devices and constituting the audio channel setup system.

When the electronic devices and are wirelessly interconnected each device identifies its audio channel designation according to relative positions and automatically plays back sound information in a direction toward the user according to the audio channel designation.

Referring to at step when external electronic devices and are connected with the electronic device the electronic device determines positions of the external electronic devices and relative to the position of the electronic device .

More specifically when external electronic devices and are wirelessly connected with the electronic device the electronic device designates itself as a master device and designates the external electronic devices and as slave devices.

The electronic device determines the position of the external electronic devices and relative to the position of the electronic device by use of the sensor unit and the communication unit .

At step the electronic device configures audio channel information of the electronic device and the external electronic devices and connected thereto. The electronic device configures audio channel information according to relative positions between the electronic devices and .

For example referring to in the case of a 5.1 channel layout the electronic device can identify relative positions of the other electronic devices and and configure audio channel information so that the electronic devices and placed in front of the user act respectively as a left speaker a center speaker and a right speaker and the electronic devices and placed behind the user act respectively as a rear left speaker a woofer and a rear right speaker.

At steps and the electronic device configures audio channel information according to user settings. For example in the case of a 5.1 channel layout the user can directly configure audio channel information so that the electronic devices and placed in front of the user act respectively as a left speaker a center speaker and a right speaker and the electronic devices and placed behind the user act respectively as a rear left speaker a woofer and a rear right speaker.

At step the electronic device sends sound information to the external electronic devices and according to the configured audio channel information. The electronic device sends sound information to the external electronic devices and through the communication unit . Here the sound information is a play list stored in the electronic devices and and the play list indicates a sound playback sequence. The electronic devices and plays back sound source materials according to the sound information.

At step the electronic device checks whether at least one of the electronic devices and is moved master designation of the electronic device is changed at least one of the external electronic devices and is disconnected from the electronic device or a new external electronic device is connected to the electronic device .

If at least one of the electronic devices and is moved if master designation of the electronic device is changed if at least one of the external electronic devices and is disconnected from the electronic device or if a new external electronic device is connected to the electronic device the electronic device proceeds to step at which the electronic device sends new audio channel information to the connected external electronic devices or reconfigures the audio channel information. The audio channel information indicates audio channel designation as used in for example 5.1 channel layout.

Otherwise the electronic device returns to step and the electronic device sends sound information to the external electronic devices and according to the configured audio channel information.

Referring to at step when external electronic devices and are wirelessly connected with the electronic device the electronic device configures audio channel information. The electronic device configures audio channel information of the electronic device and the external electronic devices and connected thereto according to identified positions.

For example referring to in the case of a 5.1 channel layout the electronic device can identify relative positions of the other electronic devices and and configure audio channel information so that the electronic devices and placed in front of the user act respectively as a left speaker a center speaker and a right speaker and the electronic devices and placed behind the user act respectively as a rear left speaker a woofer and a rear right speaker.

At step the electronic device configures and sends audio channel information according to user settings. For example in the case of a 5.1 channel layout the user can directly configure audio channel information so that the electronic devices and placed in front of the user act respectively as a left speaker a center speaker and a right speaker and the electronic devices and placed behind the user act respectively as a rear left speaker a woofer and a rear right speaker.

At step the electronic device sends sound information to the external electronic devices and according to the configured audio channel information. The electronic device sends sound information to the external electronic devices and through the communication unit . Here the sound information is a play list stored in the electronic devices and and the play list indicates a sound playback sequence.

At step the electronic device checks whether at least one of the electronic devices and is moved master designation of the electronic device is changed at least one of the external electronic devices and is disconnected from the electronic device or a new external electronic device is connected to the electronic device .

If at least one of the electronic devices and is moved if master designation of the electronic device is changed if at least one of the external electronic devices and is disconnected from the electronic device or if a new external electronic device is connected to the electronic device the electronic device proceeds to step at which the electronic device sends new audio channel information to the connected external electronic devices or reconfigures the audio channel information. The audio channel information indicates audio channel designation as used in for example 5.1 channel layout.

Otherwise the electronic device returns to step and the electronic device sends sound information to the external electronic devices and according to the configured audio channel information.

Referring to illustrates audio channel setup corresponding to the flowchart of . The audio channel setup method herein is described with reference to .

Referring to at step when external electronic devices and are wirelessly connected with the electronic device the electronic device determines positions of the external electronic devices and relative to the position of the electronic device .

More specifically when the external electronic devices and are wirelessly connected with the electronic device the electronic device acts as a master device and designate the external electronic devices and as slave devices.

At step the electronic device determines positions of the external electronic devices and relative to the position of the electronic device by use of the sensor unit and the communication unit . Here not only relative positions between the electronic device and the external electronic devices and but also relative positions between the external electronic devices and are determined.

After connection establishment at step the electronic device configures audio channel information of the electronic device and the external electronic devices and connected thereto. The electronic device configures audio channel information according to the identified relative positions between the electronic devices and .

At steps and the electronic device sends and configures audio channel information according to user settings. For example in the case of a 5.1 channel layout the user can directly configure audio channel information so that the electronic devices and placed in front of the user act respectively as a left speaker a center speaker and a right speaker and the electronic devices and placed behind the user act respectively as a rear left speaker a woofer and a rear right speaker.

As an example for step referring to in the case of a 5 channel layout the electronic device before master device change can identify relative positions between the electronic devices and and configure audio channel information so that the electronic devices and act as a first left speaker a second left speaker a first right speaker a second right speaker and a third right speaker respectively.

At step the electronic device sends sound information to the external electronic devices and according to the configured audio channel information. The electronic device sends sound information to the external electronic devices and through the communication unit .

At step the electronic device checks whether one of the external electronic devices and is newly designated as a master device.

If one of the external electronic devices and is newly designated as a master device the electronic device proceeds to step at which the electronic device sends the audio channel information to the external electronic device newly designated as a master device.

Otherwise the electronic device returns to step and the electronic device sends sound information to the external electronic devices and according to the configured audio channel information.

For example referring to when the external electronic device among the external electronic device and is newly designated as a master device the electronic device sends the audio channel information to the external electronic device .

Referring to at step when an external electronic device is wirelessly connected with the electronic device the electronic device is designated as a master device. Thereafter at step the external electronic device is designated as a slave device. The external electronic device designated as a slave device is controlled by the electronic device .

After wireless connection establishment at step the electronic device configures audio channel information. The electronic device configures audio channel information according to the identified relative positions between the electronic devices and . Here step is skipped when the user directly configures the audio channel information.

At step the electronic device produces sound information according to the configured audio channel information. At step the electronic device sends the sound information to the external electronic device . At step the external electronic device receives the sound information.

At step the electronic device checks whether master device designation is changed. Correspondingly at step the external electronic device checks whether the external electronic device is newly designated as a master device. If master device designation is changed the electronic device proceeds to step at which the electronic device sends the audio channel information to the external electronic device . If master device designation is not changed the electronic device returns to step and produces sound information according to the configured audio channel information.

If the external electronic device is newly designated as a master device the external electronic device proceeds to step at which it receives the audio channel information. The external electronic device newly designated as a master device controls the electronic device . If the external electronic device is not newly designated as a master device the external device returns to step and receives the sound information.

At step the external electronic device reconfigures the audio channel information relative to the position of the external electronic device . This is to change the audio channel designation with reference to the position of the master device. At step the external electronic device sends sound information to the electronic device according to the reconfigured audio channel information.

For example referring to when the external electronic device among the external electronic device and is newly designated as a master device the electronic device sends the audio channel information to the external electronic device newly designated as a master device. The external electronic device acting as a new master device reconfigures the audio channel information relative to the position of the master device. Although interactions between one master device and one slave device are shown in the above description may also be applied to interactions between one master device and multiple slave devices.

Referring to illustrates audio channel setup corresponding to the flowchart of . The audio channel setup method is described herein with reference to .

At step when external electronic devices and are wirelessly connected with the electronic device the electronic device determines positions of the external electronic devices and relative to the position of the electronic device .

More specifically when the external electronic devices and are wirelessly connected with the electronic device the electronic device designates itself as a master device and designates the external electronic devices and as slave devices.

At step the electronic device determines positions of the external electronic devices and relative to the position of the electronic device by use of the sensor unit and the communication unit . Here not only relative positions between the electronic device and the external electronic devices and but also relative positions between the external electronic devices and are determined.

After wireless connection establishment at step the electronic device configures audio channel information. Here the electronic device configures audio channel information according to the identified relative positions between the electronic devices and .

For example referring to in the case of a 5 channel layout the electronic device before master device change can identify relative positions between the electronic devices and and configure audio channel information so that the electronic devices and act as a first left speaker a second left speaker a first right speaker a second right speaker and a third right speaker respectively.

At step the electronic device sends sound information to the external electronic devices and according to the configured audio channel information. The electronic device sends sound information to the external electronic devices and through the communication unit .

At step the electronic device checks whether the position of the electronic device is changed. If the position of the electronic device is changed the electronic device proceeds to step at which the electronic device reconfigures the audio channel information relative to the new position thereof. If the position of the electronic device is not changed the electronic device returns to step and sends sound information to the external electronic devices and according to the configured audio channel information.

For example referring to when the electronic device is moved to the position of the external electronic device the electronic device reconfigures the audio channel information relative to the new position of the electronic device . The electronic device can identify relative positions between the electronic devices and and reconfigure the audio channel information so that the electronic devices and act as a first left speaker a second left speaker a first right speaker a second right speaker and a third right speaker respectively.

Referring to illustrates audio channel setup corresponding to the flowchart of . The audio channel setup method is described with reference to .

At step when external electronic devices and are wirelessly connected with the electronic device the electronic device determines positions of the external electronic devices and relative to the position of the electronic device .

More specifically when external electronic devices and are wirelessly connected with the electronic device the electronic device designates itself as a master device and designates the external electronic devices and as slave devices.

The electronic device determines the position of the external electronic devices and relative to the position of the electronic device by use of the sensor unit and the communication unit at step . Here not only relative positions between the electronic device and the external electronic devices and but also relative positions between the external electronic devices and are determined.

At step the electronic device configures audio channel information of the electronic device and the external electronic devices and connected thereto. The electronic device configures audio channel information according to the relative positions between the electronic devices and .

For example referring to in the case of a 5.1 channel layout the electronic device can identify relative positions of the electronic devices and and configure audio channel information so that the electronic devices and act as a center speaker a left speaker a rear left speaker a woofer a rear right speaker and a right speaker respectively. Here steps and may be skipped when the user directly configures the audio channel information.

At step the electronic device sends sound information to the external electronic devices and according to the configured audio channel information. The electronic device sends sound information to the external electronic devices and through the communication unit .

At step the electronic device checks whether at least one of the external electronic devices and is disconnected from the electronic device or at least one external electronic device is newly connected to the electronic device . If at least one of the external electronic devices and is disconnected or at least one external electronic device is newly connected the electronic device proceeds to step at which the electronic device reconfigures the audio channel information with respect to the position of the electronic device according to preset weights or priorities. Otherwise the electronic device returns to step and sends sound information to the external electronic devices and according to the configured audio channel information.

During reconfiguration of the audio channel information a channel with broad sound distribution may take a heavy weighting or high priority. For example speakers or channels may be listed in order of highest to lowest priority center speaker center channel left right speaker left right channel rear left right speaker rear left right channel and woofer speaker woofer channel . Hence when an external electronic device designated to act as the center speaker center channel or the left right speaker left right channel with broad sound distribution is disconnected the electronic device performs audio channel reconfiguration. On the contrary when an external electronic device designated to act as the center speaker center channel or the left right speaker left right channel with broad sound distribution is neither disconnected nor newly connected the electronic device does not perform audio channel reconfiguration. Alternatively weights or priorities may be determined according to the number of right channels and the number of left channels. For example when a given number or more of external electronic devices designated to act as a left channel or right channel are disconnected or newly connected the electronic device performs audio channel reconfiguration to achieve even sound distribution. Otherwise the electronic device does not perform audio channel reconfiguration.

As another example referring to when one or more external electronic devices are disconnected or newly connected for instance external electronic devices and designated to act respectively as the left channel and the rear left channel are disconnected the electronic device reconfigures the audio channel information with respect to the position of the electronic device according to preset weights or priorities. In this case the electronic device changes audio channel designation so that among the remaining external electronic devices and the external electronic device being designated to act as the woofer channel with low priority is newly designated to act as the left channel which has been deleted .

At step when external electronic devices and are wirelessly connected with the electronic device the electronic device determines positions of the external electronic devices and relative to the position of the electronic device .

More specifically when external electronic devices and are wirelessly connected with the electronic device the electronic device designates itself as a master device and designates the external electronic devices and as slave devices.

The electronic device determines the positions of the external electronic devices and relative to the position of the electronic device by use of the sensor unit and the communication unit at step . Here not only are relative positions between the electronic device and the external electronic devices and determined but also relative positions between the external electronic devices and .

At step the electronic device configures audio channel information and finds a central point between the electronic devices and . Here the central point is the center of gravity of the electronic devices and .

At step the electronic device adjusts sound volumes of the electronic devices and so that sounds are evenly spread from the electronic devices and toward the central point.

For example referring to distances between the central point and the electronic devices and are denoted respectively as A B C D E and F. When A B C D E and F are very different from each other if all the electronic devices and produce sounds at the same volume without regard to their distances to the central point sound quality at the central point may be poor or uneven. Hence when the electronic device determines the central point as described above and adjusts sound volumes of the electronic devices constituting the audio channel in proportion to their distances to the central point sound quality can be improved at the central point.

Various embodiments of the present invention have been shown and described for the purpose of illustration without limiting the subject matter of the present invention. It should be understood by those skilled in the art that many variations and modifications of the method and apparatus described herein will still fall within the spirit and scope of the present invention as defined in the appended claims and their equivalents.

