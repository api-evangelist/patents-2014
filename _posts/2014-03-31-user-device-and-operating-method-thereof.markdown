---

title: User device and operating method thereof
abstract: A security method in an electronic device is provided. The method includes pairing the electronic device with an Access Point (AP), obtaining at least one item of information about the AP, and setting a security level of the electronic device according to the at least one item of information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09183409&OS=09183409&RS=09183409
owner: Samsung Electronics Co., Ltd.
number: 09183409
owner_city: Suwon-si
owner_country: KR
publication_date: 20140331
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed on Jun. 4 2013 in the Korean Intellectual Property Office and assigned Serial number 10 2013 0063946 the entire disclosure of which is hereby incorporated by reference.

The present disclosure relates to a user device having a security function and an operating method thereof.

At present owing to the growth of electronic communication industries user devices such as cellular phones electronic schedulers personal terminals laptop computers and the like are becoming necessities to modern society while being significant means for delivery of fast changing information. The user devices make users works convenient through a Graphical User Interface GUI environment using a touch screen and have come to provide various multimedia based on a web environment. Generally the user devices provide personalized services and are configured to operate with security. However users are not currently provided with a method or apparatus for setting a security level corresponding to a surrounding environment.

The above information is presented as background information only to assist with an understanding of the present disclosure. No determination has been made and no assertion is made as to whether any of the above might be applicable as prior art with regard to the present disclosure.

Aspects of the present disclosure are to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present disclosure is to provide a method for setting a security level of a user device according to a surrounding environment.

Another aspect of the present disclosure is to provide a method for setting a lock of a user device suitable to a security level.

Another aspect of the present disclosure is to provide a method for setting a security level of a user device according to at least one item of information about an Access Point AP .

In accordance with an aspect of the present disclosure a security method in an electronic device is provided. The method includes pairing the electronic device with an AP obtaining at least one item of information about the AP and setting a security level of the electronic device according to the at least one item of information.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes a pairing module an acquisition module and a security setting module. The pairing module is configured to pair with an AP. The acquisition module is configured to obtain at least one item of information about the AP. The security setting module is configured to set a security level of the electronic device according to the at least one item of information.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes one or more processors configured to execute computer programs a memory configured to store data and instructions and at least one program stored in the memory and configured to be executable by the one or more processors. The program pairs the electronic device with an AP and adjusts a lock level of the electronic device according to use restriction information set to the AP.

Other aspects advantages and salient features of the disclosure will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses various embodiments of the present disclosure.

Throughout the drawings it should be noted that like reference numbers are used to depict the same or similar elements features and structures.

The following description with reference to the accompanying drawings is provided to assist in a comprehensive understanding of various embodiments of the present disclosure as defined by the claims and their equivalents. It includes various specific details to assist in that understanding but these are to be regarded as merely exemplary. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the various embodiments described herein can be made without departing from the scope and spirit of the present disclosure. In addition descriptions of well known functions and constructions may be omitted for clarity and conciseness.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the present disclosure. Accordingly it should be apparent to those skilled in the art that the following description of various embodiments of the present disclosure is provided for illustration purpose only and not for the purpose of limiting the present disclosure as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

The user device may be one of an electronic device such as a mobile phone a mobile pad a media player a tablet computer a handheld computer a Personal Digital Assistant PDA and a digital camera. Also the user device may be any user device including a device combining two or more functions among these devices.

Referring to the user device can include a processor a memory a speaker a microphone a camera a display a touch panel a sensor a Power Manager Integrated Circuit PMIC a battery a cellular antenna a Front End Module FEM a Wireless Connectivity WC antenna WC and a Radio Frequency Integrated Circuit RFIC .

The processor controls the general operation of the user device . The processor performs a function of executing an Operating System OS and an application program of the user device and controlling other parts and devices. The processor can include an Application Processor AP for performing a key function of the entire system a Communication Processor CP for performing communication a Graphic Processing Unit GPU for processing 2 Dimensional 2D and 3 Dimensional 3D graphics an Image Signal Processor ISP for taking charge of image signal processing an Audio Signal Processor ASP for taking charge of voice signal processing a memory semiconductor a system interface and the like. The processor can be a System On Chip SOC in which various parts are integrated as one.

The AP plays a brain role of the user device and can support a function of computation processing a function of playing contents of various formats such as an audio an image a video and the like a graphic engine and the like. The AP can drive an operating system applied to the user device various functions and the like. The AP can perform a great number of functions of a core a memory a display system controller a multimedia encoding decoding CODEC a 2D 3D accelerator engine an Image Signal Processor ISP a camera an audio a modem various high and low speed serial parallel connectivity interfaces and the like. The AP can execute various software programs i.e. instruction sets stored in the memory to perform various functions of the user device and perform processing and control for voice communication image communication and data communication. The AP can execute software programs i.e. instruction sets stored in the memory to perform various functions corresponding to the programs. The AP can be an SOC integrating all of a GPU an ISP an ASP a memory semiconductor and a system interface.

The CP can perform voice communication and or data communication and can compress voice data and image data or decompress the compression thereof. The CP can be a baseband modem a Baseband Processor BP or the like. The CP can be designed to operate through one of a Global System for Mobile Communication GSM network an Enhanced Data GSM Environment EDGE network a Code Division Multiple Access CDMA network a Wireless Code Division Multiple Access W CDMA network a Long Term Evolution LTE network an Orthogonal Frequency Division Multiple Access OFDMA network a WiFi network a Wireless interoperability for Microwave Access WiMAX network and a BLUETOOTH network.

The GPU can process computation related to graphics and take charge of image information processing acceleration signal conversion picture output and the like. The GPU can solve a bottleneck phenomenon caused by a graphic work of the AP and can process 2D or 3D graphics faster than the AP.

The ISP can convert electrical signals i.e. image data from the camera into image signals. The ISP can change a color sense of the image data from the camera into a format such as a real image and can adjust brightness. The ISP can perform Automatic Exposure AE Automatic White Balance AWB automatically adjusting a white balance according to a change of a color temperature of an incident light source Automatic Focus AF automatically focusing a subject and the like. The ISP can analyze a frequency component of the image data obtained from the camera and recognize a definition of an image to adjust an F number of the iris of the camera and a shutter speed. The ISP can temporarily store the image data from the camera in the memory e.g. buffer memory .

The ASP can process computation related to an audio and can change an audio signal of a digital or analog form through an audio effect or effect unit.

The memory can store software related programs i.e. instruction sets executable by the aforementioned processors. The memory can include high speed random access memories and or non volatile memories such as one or more magnetic disk storage devices one or more optical storage devices and or flash memories for example Not AND NAND memories Not OR NOR memories . A total of storage time of video data obtained from an image sensor can be proportional to an available capacity of the memory .

Software can include an OS program a communication program a camera program a graphical program one or more application programs a user interface program a CODEC program a security program and the like. The term of program may be expressed as a set of instructions or an instruction set. The OS program can use various functions of the communication program the camera program the graphical program the one or more application programs the user interface program and the CODEC program through various Application Programming Interfaces APIs .

The OS program indicates an embedded operating system such as WINDOWS LINUX Darwin RTXC UNIX OS X or VxWorks and can include various software constituent elements controlling general system operation. Control of the general system operation can include memory control and management storage hardware device control and management power control and management and the like. Also the OS program can perform a function of smoothing communication between various hardware devices and software constituent elements programs . The communication program can enable communication with a computer a server a user device and the like through the WC the RFIC or an external port.

The camera program can include a camera related software constituent element enabling camera related processes and functions. Under support of an API such as Open Graphics Library OpenGL DirectX and the like the camera program can perform preprocessing applying various effects to an image from the image sensor of the camera and postprocessing applying various effects to a captured snap image. If video data from the camera reaches a transmission capacity e.g. an available capacity of the memory or a capacity of the buffer memory the camera program can convert the video data into a video file and transmit the converted video file to an external storage e.g. a server an external memory or the like .

The graphical program can include various software constituent elements for providing and displaying graphics on the display . The graphical program can create graphics based on an API such as OpenGL DirectX and the like and can provide various filters capable of applying various effects to an image. The term of graphics indicates a text a web page an icon a digital image a video an animation and the like. The graphical program can be an image viewer an image edit program and the like adapting usability to postprocessing an image and can be a camera related program a video call related program and the like optimized to preprocessing an image. The graphical program can perform postprocessing applying various effects to a rendering completed image or perform preprocessing applying various effects for an image. Filters for these effects can be collectively managed such that they can be used commonly to other programs as aforementioned.

The application program can include a browser an electronic mail e mail an instant message word processing keyboard emulation an address book a touch list a widget Digital Right Management DRM voice recognition voice replication a position determining function a location based service and the like. The user interface program can include various software constituent elements related to a user interface. The user interface program can include information about how a state of the user interface is changed whether the change of the state of the user interface is carried out in which condition and the like.

The CODEC program can include a software constituent element related to encoding and decoding of a video file.

The security program can pair with an AP obtain at least one item of information about the AP and set a security level according to the at least one item of information. The security program can set a lock of the user device according to the security level. The security program can release the lock of the user device according to the security level or maintain the lock of the user device or change the lock of the user device into other schemes. When a use restriction on the AP has been set the security program can set the security level high and when the use restriction on the AP has not been set the security program can set the security level low. When a use restriction level set to the AP is high the security program can set the security level high and when the use restriction level set to the AP is low the security program can set the security level low. When an encryption scheme e.g. a password for pairing with the AP has been set the security program can decrease the security level and when the encryption scheme for pairing with the AP has not been set the security program can increase the security level. According to the coincidence or non coincidence of a password for pairing with the AP with a password for releasing the lock of the user device the security program can adjust the security level. On the basis of an RF signal of the AP the security program can determine a Received Signal Strength Indication RSSI . When the RSSI exceeds a threshold value the security program can set the security level low and when the RSSI does not exceed the threshold value the security program can set the security level high. When a current location of the user device is included in an area set to the AP the security program may set the security level low and when the current location is not included in the area set to the AP the security program may set the security level high. When a current time belongs to a time zone set to the AP the security program may set the security level low and when the current time does not belong to the time zone set to the AP the security program may set the security level high.

Besides the aforementioned programs the memory can further include additional programs instructions . Also various functions of the user device can be executed by hardware and or software and or a combination thereof which may include one or more of stream processing and Application Specific Integrated Circuits ASICs .

The speaker can convert electrical signals into audible frequency band signals and output the audible frequency band signals. The microphone can convert sound waves forwarded from human or other sound sources into electrical signals.

The camera can convert light reflected from a camera target into electrical signals. The camera can include an image sensor such as a Charged Coupled Device CCD a Complementary Metal Oxide Semiconductor CMOS or the like. The image sensor can perform a camera function of photo and video clip recording and the like. According to a camera program executed by the AP of the processor the image sensor can change a hardware construction for example move a lens and adjust an F number of the iris and the like.

The display can output electrical signals as visual information e.g. a text a graphic a video and the like . The display may be one of an Electro Wetting Display EWD an Electronic paper E paper a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED and an Active Matrix OLED AMOLED .

The touch panel can receive a touch input. The touch panel may be one of a digitizer for stylus pen a capacitive overlay touch panel a resistance overlay touch panel a surface acoustic wave touch panel an infrared beam touch panel and the like.

The sensor can sense or distinguish and measure a physical quantity of heat light temperature pressure sound position or the like or a change thereof. The sensor can include a temperature sensor a pressure sensor a magnetic sensor an optical sensor an acoustic sensor a capacitance sensor a Global Positioning System GPS sensor and the like.

The PMIC can adjust power from the battery . For example the processor can transmit an interface signal dependent on a load to process to the PMIC . Adaptively to the processor the PMIC can adjust a core voltage supplied to the processor so the processor can be driven all the time at a minimum power. The PMIC can be constructed in relation to at least one of the WC the memory the speaker the microphone the camera the display the touch panel etc. as well as the processor . One integrated PMIC is constructed and the integrated PMIC may adjust a battery power related to at least one of the aforementioned constituent elements as well as the processor .

The FEM can be a transmitting receiving device capable of controlling an electric wave signal. The FEM can connect the cellular antenna and the RFIC and divide transmission reception signals. The FEM can play a role of filtering and amplification. The FEM may include a reception end FEM which embeds a filter filtering a reception signal and a transmission end FEM which embeds a Power Amplifier Module PAM amplifying a transmission signal.

The WC can perform various communication functions that the processor does not process for example WiFi BLUETOOTH Near Field Communication NFC Universal Serial Bus USB GPS and the like.

The RFIC e.g. RF transceiver can receive an electric wave from a base station and modulate a received high frequency into a low frequency i.e. baseband frequency such that the modem e.g. the CP can process the low frequency. The RFIC can modulate a low frequency processed in the modem into a high frequency for transmission to the base station.

Referring to the user device e.g. electronic device may include the processor including a search module an acquisition module a security setting module a lock module a pairing module and a display module .

The acquisition module can obtain at least one item of information about the network or AP searched by the search module . The at least one item of information about the AP may include use restriction information e.g. a use restriction or not or a use restriction level RSSI a location of the user device a current time previous pairing or non pairing with the AP a password for pairing with the AP and the like. The acquisition module may obtain the aforementioned information using the sensor .

According to the at least one item of information obtained by the acquisition module the security setting module can set a security level of the user device .

The lock module can set lock of the user device suitable to the security level set by the security setting module . The lock module can set a lock scheme suitable to the security level set by the security setting module . The lock scheme can be a lock using a password a touch pattern biometric recognition or the like. When the security level is low the lock module can release the lock of the user device and when the security level is high the lock module can execute the lock of the user device. When the security level is low the lock module can maintain an existing lock scheme e.g. a password and when the security level is high the lock module can change the lock scheme e.g. the password into other lock schemes of higher security e.g. biometric recognition .

The pairing module can pair with the AP searched by the search module . According to the at least one information obtained by the acquisition module the pairing module can set pairing with the AP. The at least one item of information may include one or more of the RSSI a previous pairing or non pairing with the AP the location of the user device the current time and the like.

The display module can display the result processed by the search module the acquisition module the security setting module and the pairing module .

In operation the processor e.g. the security setting module can set a security level of the user device according to a use restriction level set at the AP. The use restriction level set at the AP can be obtained by the acquisition module .

In operation the processor e.g. the lock module can set a lock of the user device according to the security level. The processor can set a lock scheme e.g. a password a touch pattern biometric recognition or the like suitable to the security level to the user device. When the security level is low the processor can release the lock of the user device and when the security level is high the processor can execute the lock of the user device. When the security level is low the processor can maintain an existing lock scheme e.g. a password and when the security level is high the processor can change the previously used lock scheme e.g. the password into a lock scheme of higher security e.g. biometric recognition .

Referring to in operation the processor e.g. the security setting module can determine whether a use restriction level set at an AP is high or low.

If the use restriction level set at the AP is high in operation the processor e.g. the security setting module can set the security level high.

If the use restriction level set at the AP is low in operation the processor e.g. the security setting module can set the security level low.

Referring to in operation the processor e.g. the security setting module can identify whether it is an AP set to a safety zone.

If it is the AP set to the safety zone in operation the processor e.g. the security setting module can set the security level low.

If it is the AP not set to the safety zone in operation the processor e.g. the security setting module can set the security level high.

Referring to in operation the processor e.g. the security setting module can identify whether it is an AP set to a secure area.

If it is the AP set to the secure area in operation the processor e.g. the security setting module can set the security level high.

If it is the AP not set to the secure area in operation the processor e.g. the security setting module can set the security level low.

In operation the processor e.g. the display module can display an icon corresponding to the searched at least one AP.

According to the selection of the icon in operation the processor e.g. the display module can display a menu for selecting a use restriction level of the AP.

According to the selection of the use restriction level of the AP in operation the processor e.g. the security setting module can set the use restriction level to the AP.

Referring to the user device can search at least one AP pairable with the user device and display icons corresponding to the searched at least one AP. If a user selects an icon among the icons the user device can provide a screen of or .

Referring to according to the selection of the icon the user device can display a menu for selecting a use restriction level of the AP. For example the menu can include an icon indicating a secure area and an icon indicating an insecure area. If the user selects one of the icon indicating the secure area and the icon indicating the insecure area the user device can set a use restriction level corresponding to the selected icon to the AP.

Referring to according to the selection of the icon the user device can display a menu for selecting a use restriction level of the AP. For example the menu can display icons e.g. low average and high divided by use restriction level.

Although not illustrated according to icon selection the user device may display a menu for enabling the user to set use information about the AP for example an area a time zone or the like.

Referring to the user device can display an icon for execution of lock screen option. If a user selects the icon the user device can provide a screen of .

Referring to according to the execution of the lock screen option the user device can display an icon indicating safety zone WiFi and an icon indicating secure area WiFi. If the user selects one of the icon indicating the safety zone WiFi and the icon indicating the secure area WiFi the user device can provide a screen of .

Referring to according to the selection of the icon or the user device can set a lock level of the user device on the basis of an AP to which a use restriction e.g. a safety zone or secure area is preset and can display status information in a status display bar .

In operation the processor e.g. the acquisition module can acquire at least one item of information about the searched AP. The at least one item of information about the AP can include an RSSI a location of the user device a current time a previous pairing or non pairing with the AP and the like.

In operation according to the acquired at least one item of information the processor e.g. the pairing module can set pairing or non pairing with the AP. If the RSSI exceeds a threshold value the processor can pair with the AP. If the location of the user device is included in an area set to the AP the processor can pair with the AP. If the current time is included in a time zone set to the AP the processor can pair with the AP. If the AP has ever been paired previously the processor can pair with the AP. If the acquired at least one item of information is equal to or greater than a reference with information set to the AP the processor can pair with the AP.

Referring to in operation the processor e.g. the pairing module can pair with an AP. By performing the aforementioned procedure of the processor can pair with the AP.

In operation the processor e.g. the acquisition module can acquire at least one item of information about the AP. The at least one item of information about the AP can include use restriction information e.g. a use restriction or not or a use restriction level an RSSI a location of the user device a current time a previous pairing or non pairing with the AP a password necessary for pairing with the AP and the like.

In operation according to the at least one item of information the processor e.g. the security setting module can set a security level. For example if a use restriction on the AP is set e.g. a secure area the processor can set the security level high and if the use restriction on the AP is not set e.g. a safety zone the processor can set the security level low. If a user restriction level of the AP is set high the processor can set the security level high and if the use restriction level of the AP is set low the processor can set the security level low.

In operation the processor e.g. the lock module can set a lock of the user device according to the security level. The processor can set a lock scheme e.g. a password a touch pattern biometric recognition or the like suitable to the security level to the user device. When the security level is low the processor can release the lock of the user device and when the security level is high the processor can execute the lock of the user device. When the security level is low the processor can maintain an existing lock scheme e.g. a password and when the security level is high the processor can change the previously used lock scheme e.g. the password into a lock scheme of higher security e.g. biometric recognition .

Referring to in operation the processor e.g. the security setting module can identify if a use restriction on an AP has been set.

If the use restriction on the AP has been set in operation the processor e.g. the security setting module can identify whether an RSSI exceeds a threshold value. The RSSI can be obtained by the acquisition module .

If the RSSI exceeds the threshold value in operation the processor e.g. the security setting module can set a security level low.

If the RSSI does not exceed the threshold value in operation the processor e.g. the security setting module can set the security level high.

Referring to in operation the processor e.g. the security setting module can identify if a use restriction on an AP has been set.

If the use restriction on the AP has been set in operation the processor e.g. the security setting module can identify if a location of a user device belongs to an area set to the AP. The acquisition module can obtain the location of the user device using the sensor .

If the location of the user device belongs to the area set to the AP in operation the processor e.g. the security setting module can set a security level low.

If the location of the user device does not belong to the area set to the AP in operation the processor e.g. the security setting module can set the security level high.

Referring to in operation the processor e.g. the security setting module can identify if a use restriction on an AP has been set.

If the use restriction on the AP has been set in operation the processor e.g. the security setting module can identify if a current time belongs to a time zone set to the AP.

If the current time belongs to the time zone set to the AP in operation the processor e.g. the security setting module can set a security level low.

If the current time does not belong to the time zone set to the AP in operation the processor e.g. the security setting module can set the security level high.

Referring to in operation the processor e.g. the search module can search an AP pairable with the user device.

In operation the processor e.g. the security setting module can identify if a use restriction on the AP has been set. This information can be obtained by the acquisition module .

If the use restriction on the AP has not been set in operation the processor e.g. the pairing module can pair with the AP.

If the use restriction on the AP has been set in operation the processor e.g. the security setting module can identify if there is previous pairing information with the AP. This information can be obtained by the acquisition module .

If there is the previous pairing information with the AP in operation the processor e.g. the pairing module can pair with the AP.

If there is not the previous pairing information with the AP in operation the processor e.g. the security setting module can identify whether an encryption scheme e.g. a password for pairing with the AP has been set. This information can be obtained by the acquisition module .

If the password for pairing with the AP has been set in operation the processor e.g. the security setting module can set the security level low.

If the password for pairing with the AP has not been set in operation the processor e.g. the security setting module can set the security level high.

Referring to in operation the processor e.g. the search module can search an AP pairable with the user device.

In operation the processor e.g. the security setting module can identify if a use restriction on the AP has been set. This information can be obtained by the acquisition module .

If the use restriction on the AP has not been set in operation the processor e.g. the pairing module can pair with the AP.

If the use restriction on the AP has been set in operation the processor e.g. the security setting module can identify if there is previous pairing information with the AP. This information can be obtained by the acquisition module .

If there is the previous pairing information with the AP in operation the processor e.g. the pairing module can pair with the AP.

In operation the processor e.g. the security setting module can identify if an RSSI exceeds a threshold value. The RSSI can be measured by the acquisition module .

If the RSSI exceeds the threshold value in operation the processor e.g. the securing setting module can set a security level low.

If the RSSI does not exceed the threshold value in operation the processor e.g. the securing setting module can set the security level high.

If there is not the previous pairing information with the AP in operation the processor e.g. the security setting module can identify whether a password for pairing with the AP has been set. The password necessary for pairing with the AP can be obtained by the acquisition module .

If the password for pairing with the AP has been set in operation the processor e.g. the security setting module can set the security level low.

If the password for pairing with the AP has not been set in operation the processor e.g. the security setting module can set the security level high.

In operation the processor e.g. the acquisition module can acquire at least one item of information about the network. The at least one item of information about the network can include use restriction information e.g. a use restriction or not or a use restriction level about the network an RSSI a location of the user device a current time a previous pairing or non pairing with the network a password necessary for pairing with the network and the like.

In operation according to the at least one item of information the processor e.g. the security setting module can set a security level. For example if a user restriction level of the network is set high the processor can set the security level high and if the use restriction level of the network is set low the processor can set the security level low.

In operation the processor e.g. the lock module can set a lock of the user device according to the security level. The processor can set a lock scheme e.g. a password a touch pattern biometric recognition or the like suitable to the security level to the user device. When the security level is low the processor can release the lock of the user device and when the security level is high the processor can execute the lock of the user device. When the security level is low the processor can maintain an existing lock scheme e.g. a password and when the security level is high the processor can change the previously used lock scheme e.g. the password into a lock scheme of higher security e.g. biometric recognition .

Referring to in operation the processor e.g. the security setting module can identify if a use restriction on a network has been set.

If the use restriction on the network has been set in operation the processor e.g. the security setting module can identify if a password set for lock of the user device coincides with a password necessary for pairing with the network.

If the password set for the lock of the user device does not coincide with the password necessary for pairing with the network in operation the processor e.g. the security setting module can set a security level low.

If the password set for the lock of the user device coincides with the password necessary for pairing with the network in operation the processor e.g. the security setting module can set the security level high.

Referring to the user device can provide a lock screen of a touch pattern scheme. If a user inputs a touch pattern joining predefined pointers together through touch and drag operations the user device can release the lock of the user device .

Referring to the user device can provide a lock screen of a password scheme. If the user inputs a correct password to the user device the user device can release the lock of the user device .

Referring to the user device can provide a lock screen of a Personal Identification Number PIN scheme. If the user inputs a correct PIN the user device can release lock of the user device .

Though not illustrated the user device may provide a lock screen using biometric recognition e.g. voice recognition fingerprint recognition iris recognition face recognition or the like .

As described above a user device can set a security level high or low according to at least one information e.g. use restriction information on an AP pairing with the user device. The user device provides a lock scheme e.g. password biometric recognition or the like suitable to the security level and adjusts the security level for use of wireless communication through the paired AP thereby being able to satisfy a user s convenience.

According to various embodiments of the present disclosure respective modules can be configured by software firmware hardware or a combination thereof Also some or all of the modules may be constructed in one entity and can identically perform a function of each module. According to various embodiments of the present disclosure respective operations can be executed sequentially repeatedly or in parallel. Also some of the operations can be omitted or other operations can be added and executed. For example the respective operations can be executed by corresponding modules described in the present disclosure.

Methods according to various embodiments disclosed in the claims and or specification of the present disclosure can be implemented in a form of hardware software or a combination of the hardware and the software for a general purpose or a specialized processor to be configured to execute an embodiment of the present disclosure.

In a case of implementing in the software form a computer readable storage medium storing one or more programs i.e. software modules may be provided. One or more programs stored in the computer readable storage medium are executable by one or more processors within an electronic device. The one or more programs may include instructions for enabling the electronic device to execute the methods according to the various embodiments disclosed in the claims and or specification of the present disclosure.

These programs i.e. software modules or software can be stored in a Random Access Memory RAM a nonvolatile memory including a flash memory a Read Only Memory ROM an Electrically Erasable Programmable ROM EEPROM a magnetic disk storage device a Compact Disk ROM CD ROM a Digital Versatile Disk DVD or an optical storage device of other form and a magnetic cassette. Or the programs can be stored in a memory configured by a combination of some or all of the foregoing. Also each configuration memory may be plural in number.

Also the programs can be stored in an attachable storage device accessible to the electronic device through a communication network such as the Internet an intranet a Local Area Network LAN a Wireless LAN WLAN and a Storage Area Network SAN or a communication network configured by a combination of the foregoing. This storage device can access the electronic device through an external port.

While the present disclosure has been shown and described with reference to various embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present disclosure as defined by the appended claims and their equivalents.

