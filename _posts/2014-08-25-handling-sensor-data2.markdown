---

title: Handling sensor data
abstract: An apparatus, a system and a method for securing sensor data by a security engine circuitry of a system on chip (SoC). For example, the security engine may receive from a processor circuitry of the SoC an inter processor communication (IPC) request to secure sensor data, and may send to an integrated sensor hub (ISH) of the SoC an IPC request to receive sensor data. The ISH may collect sensor data from one or more internal and/or external sensors, and may send the collected sensor data to the security engine. The security engine may receive the collected sensor data from the ISH, may secure the collected sensor data, and may send secured sensor data to the processor circuitry.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09654296&OS=09654296&RS=09654296
owner: Intel Corporation
number: 09654296
owner_city: Santa Clara
owner_country: US
publication_date: 20140825
---
Today handheld devices such as Smartphones and tablets rely on sensor data accelerometer gyro magnetometer pressure ambient light temperature etc. to enhance the user experience UX for a whole range of applications e.g. phone settings games and offer new features e.g. always on sensing motion based gestures user activity state pedometer etc. to enable new categories of applications. Besides motion sensors and other ambient sensors applications on mobile devices also use sensor data from other sensors such as audio e.g. for voice authentication camera e.g. for face recognition augmented reality always on location using GPS WiFi 3G LTE dead reckoning and the like.

The sensor data may include user sensitive personal and private information such as user health related information audio information camera pictures and video and or user location. This user information is not protected and or secured while provided to backend services and may be downloaded and viewed by unwanted entities and or persons. Thus there is a need to protect and secure the user information.

Reference will now be made to the exemplary embodiments illustrated and specific language will be used herein to describe the same. It will nevertheless be understood that no limitation of the scope of the disclosure is thereby intended.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of some embodiments. However it will be understood by persons of ordinary skill in the art that some embodiments may be practiced without these specific details. In other instances well known methods procedures components units and or circuits have not been described in detail so as not to obscure the discussion.

Discussions herein utilizing terms such as for example processing computing calculating determining establishing analyzing checking or the like may refer to operation s and or process es of a computer a computing platform a computing system or other electronic computing device that manipulate and or transform data represented as physical e.g. electronic quantities within the computer s registers and or memories into other data similarly represented as physical quantities within the computer s registers and or memories or other information storage medium that may store instructions to perform operations and or processes.

The terms plurality and a plurality as used herein include for example multiple or two or more . For example a plurality of items includes two or more items.

References to one embodiment an embodiment demonstrative embodiment various embodiments etc. indicate that the embodiment s so described may include a particular feature structure or characteristic but not every embodiment necessarily includes the particular feature structure or characteristic. Further repeated use of the phrase in one embodiment does not necessarily refer to the same embodiment although it may.

As used herein unless otherwise specified the use of the ordinal adjectives first second third etc. to describe a common object merely indicate that different instances of like objects are being referred to and are not intended to imply that the objects so described must be in a given sequence either temporally spatially in ranking or in any other manner.

Some embodiments may be used in conjunction with various devices and systems for example a Personal Computer PC a User Equipment UE a Mobile Device MD an Internet of Things IoT device a desktop computer a mobile computer a laptop computer a notebook computer a tablet computer an Ultrabook computer a Smartphone device a server computer a handheld computer a handheld device a Personal Digital Assistant PDA device a handheld PDA device an on board device an off board device a hybrid device a vehicular device a non vehicular device a mobile or portable device a consumer device a non mobile or non portable device a wireless communication station a wireless communication device a wireless Access Point AP a wired or wireless router a wired or wireless modem a video device an audio device an audio video A V device a wired or wireless network a cellular network a cellular node a handheld device e.g. a Smartphone a Wireless Application Protocol WAP device vending machines sell terminals and the like.

The phrases wireless device and or mobile device as used herein includes for example a device capable of wireless communication a communication device capable of wireless communication a communication station capable of wireless communication a portable or non portable device capable of wireless communication or the like. In some demonstrative embodiments a wireless device may be or may include a peripheral that is integrated with a computer or a peripheral that is attached to a computer. In some demonstrative embodiments the phrase wireless device and or mobile device may optionally include a wireless service.

The term communicating as used herein with respect to a wire and or wireless and or internal communication signal includes transmitting the communication signal and or receiving the communication signal. For example a communication unit which is capable of communicating a communication signal may include a transmitter to transmit the communication signal to at least one other communication unit and or a communication receiver to receive the communication signal from at least one other communication unit.

Reference is made to which schematically illustrates a system including a mobile device a World Wide Web WWW cloud and a server in accordance with some demonstrative embodiments. One or more external sensors may be operably coupled to mobile device if desired.

According to some exemplary embodiments system may include a wireless local area network WLAN a cellular network a local area network LAN a wide area network WAN a wireless WAN or the like.

According to some non limiting embodiments for example mobile device may include a wireless mobile device such as for example a cellphone a Smartphone a wearable device a tablet a laptop computer an Internet of things IoT device and the like.

According to a non limiting exemplary embodiment mobile device may include a system on chip SoC circuitry and or logic a Bluetooth BT circuitry a global positioning system GPS receiver a wireless local area network WLAN radio e.g. a Wireless Fidelity WiFi radio a memory a microphone MIC one or more speakers one or more sensors and one or more antennas e.g. a plurality of antennas .

According to some non limiting embodiments SoC circuitry may include a processor circuitry an integrated sensor hub ISH a security engine circuitry and or an audio circuitry if desired.

For example processor circuitry my include but not limited to a kernel layer which may include for example one or more drivers and an inter processor communication IPC logic a middleware MW layer which may include for example a security MW logic and a sensor MW logic an application framework layer and one or more applications e.g. operably coupled to application framework layer if desired.

In some demonstrative embodiments ISH may include a sensor data acquisition DAQ and sensor fusion. HIS may perform sensor processing e.g. all sensor processing required for an OS in processor circuitry and may also perform continuous sensing usages e.g. when a platform of device is in a low power state e.g. a lowest power state.

In some demonstrative embodiments sensors may be connected to ISH by a wired or a wireless I O bus. For example ISH may include a processor core which may for example operate at a speed of 100 Megahertz MHz or any other speed and ISH may handle more complex workloads in a responsive fashion if desired.

In another demonstrative embodiment ISH may include a paging architecture for code provider flexibility in handling larger code sizes if desired. For example ISH may include a direct IPC channel to processor circuitry security engine Audio DSP an image processor not shown and the like.

According to some demonstrative embodiments ISH may collect data and or communicate with one or more external sensors which for example may be connected with a low power radio protocol. According to another example external sensors may be connected to ISH via a wireless link. Thus exemplary embodiments of ISH may become the communication Hub for collecting data from external sensor pods.

ISH Firmware of ISH may be secure. For example the ISH firmware may be configured to perform sensor DAQ and processing may be integrity checked and loaded from a signed firmware image e.g. from external memory .

The above embodiments may apply to other IP blocks that are used to offload for example audio processing Audio DSP camera image processing Imaging Signal Processor location GNSS GPS WiFi 3G LTE and the like.

In some demonstrative embodiments a user of mobile device may use one or more applications operated on mobile device for example to transfer user data. The user data may be collected by one or more sensors and or one or more external sensors and provided e.g. through WWW cloud or via any other medium to server for example a backend server or any other server. For example the user data may include medical data such as for example blood pressure data sugar level data heartbeat data stress data and the like. Additionally or alternatively the user data may include user location data image data video data audio data private data such as for example contacts list data blog data password data bank account information and or any other private information sensitive information and or information and or data to be protected or secured.

According to some exemplary embodiments application may receive user data may validate a certificate and may locally logs the user data. According to another example the user data may be sent to WWW cloud where the certificate is verified and further heuristics may be performed to match data patterns with historical data from the same user. Thus preventing false information or outliers in the data getting logged. The user may change the privacy setting of the secure sensing e.g. ordering ISH not to forward data from some health sensors to the host. Security engine may encrypt data so that only the remote web service can open it if desired.

According to some demonstrative embodiments mobile device may include an enhanced privacy identifier EPID provisions and software not shown and server may include EPID software and an access to a corresponding public key for example from an issuer of the EPID keys.

According to some demonstrative embodiments mobile device may be configured to transfer the user data in a secure manner to server e.g. the backend server. For example application may create a verified device message and may send the verified device message to security engine . Security engine may sign the verified device message by using for example the EPID protocol and or digital signature standard DSS . The Signed message may be transferred from security engine to a host side application not shown . The host side application may send the signed message to the server .

In some demonstrative embodiments server side SW not shown may use an Issuer s public key to attest that the signature belongs to mobile device in good standing. Once the connection between mobile device and server is established the EPID Sigma protocol may be used to exchange session keys for example session key SK encrypt messages master keys MK integrity protects messages or the like. The SK may be transferred to the security engine if desired.

Acceding to some demonstrative embodiments the sensor data from sensors and or for example user health related data audio data camera data location data or other Personally Identifiable Information PII data may be transferred to server e.g. in a secure manner. For example application may request certified sensor data related to user health. ISH may gather the sensor data from sensors and or and may transfer the sensor data to security engine . Security engine may encrypt the sensor data e.g. with the SK and the MK for example to sign the sensor data and thus apply an integrity protection to the sensor data.

In some demonstrative embodiments security engine may pass the encrypted sensor data to application which operates on processor circuitry . The encrypted sensor data may be sent on a secure channel to server . Server e.g. the backend server may use a copy of the SK e.g. to decrypt the encrypted sensor data. Server may verify that the integrity of the sensor data has not been compromised.

In some demonstrative embodiments server may process the sensor data e.g. to complete checking the sensor data to consume the data and or to complete any necessary analysis and may optionally securely send an output of processing the sensor data back to application on mobile device .

Advantageously a device e.g. mobile device equipped with EPID may be recognized by a backend server e.g. server as a device associated with a certain level of trust security capabilities. For example the device may use a Sigma protocol to setup a session oriented secure channel from the device to the backend server. In alternative embodiments the device may implement a public key infrastructure PKI e.g. directly in security engine to generate a key pair and establish a secure channel between mobile device and server for user authentication and transfer of sensor data.

According to some demonstrative embodiments for example SoC may be configured to secure sensor data e.g. from sensors and or . Processor circuitry may be configured to collect and update sensor data to a service. ISH may be configured to collect and process the one or more sensors data.

In some demonstrative embodiments security engine may be configured to receive the sensor data from the ISH . Security engine may certify the sensor data and may send certified sensor data to middleware framework . Security engine may be configured to receive from IPC of processor circuitry an IPC request to provide the secure sensor data. Security engine may be configured to send to ISH the IPC request to add a certificate to the requested sensor data and to send the certified requested sensor data to processor circuitry .

According to some demonstrative embodiments security engine may be configured to generate at least one encryption key to encrypt the sensor data and to add a certificate to the sensor data. For example the certified requested sensor data may be delivered to middleware MW framework of the processor circuitry .

For example the certified requested sensor data may be configured to be used by a service in mobile device and or in cloud . The certified requested sensor data may be configured to be certified against user credentials and to be logged to a database in server .

Reference is made to which schematically illustrates a method of securing a sensor data at a system on chip SoC in accordance with some demonstrative embodiments. For example a secure and or hardware certified data may flow from processor circuitry to security engine from security engine to ISH and back to security engine and to application which may be running on an operating system OS of processor circuitry . For example the OS may be an Android OS an Apple iOS a Windows OS or the like.

According to some alternative embodiments ISH may include one or more IP blocks such as for example audio sensor imaging and the like. For example ISH may collect data from one or more sensors a microphone a camera and the like e.g. as described above although it should be understood that other alternative embodiments with different IP blocks may be used.

As indicated at block according to some demonstrative embodiments for example the method of may be initiated by an application e.g. application operated over the operating system OS of processor circuitry . Application may request certified data from for example one or more sensors e.g. sensors and or . At processor circuitry middleware MW and or an OS framework component may translate the request to a system call text box . MW and or the OS framework component may redirect the system call to a security engine device driver text box . The security engine device driver may send an IPC to security engine text box .

As indicated tat block security engine may check the validity of the request and that the ISH FW is in operation. Security engine may send IPC to ISH e.g. to request ISH to gather sensor data and return processed data text box . While ISH gathers the sensor data security engine may go to a lower power state mode and or may execute other tasks text box .

According to some exemplary embodiments ISH may receive IPC and may start an execution thread text box . ISH may collect sensor data text box may process the sensor data and may store the processed sensors data in a memory e.g. memory if desired text box . ISH may send the processed data to security engine text box .

According to some exemplary embodiments security engine may receive the processed data from ISH may use a session key to encrypt the processed data and may use one or more unique keys to add a certificate to the processed data text box . For example security engine may negotiate the session key with WWW cloud if desired. Security engine may send the processed certified data to processor circuitry text box .

As indicated at block a security engine device driver not shown of processor circuitry may receive the certified sensor data and may pass it to sensor MW . Application may receive the certified sensor data and may pass certified sensor data to a service in WWW cloud text box . The certified sensor data may be decrypted. The certificate may be verified against user credentials and logged to a database e.g. database at server if desired text box .

Reference is made to which schematically illustrates a mobile device in accordance with some demonstrative embodiments. The mobile device may include for example a user equipment UE a mobile station MS a mobile wireless device a cell phone a Smartphone a mobile communication device a tablet a handset or other type of mobile wireless device. The mobile device may include one or more antennas configured to communicate with a transmission station such as a base station BS an evolved Node B eNB a base band unit BBU a remote radio head RRH a remote radio equipment RRE a relay station RS a radio equipment RE or other type of wireless wide area network WWAN access point. The mobile device may be configured to communicate using at least one wireless communication standard including 3GPP LTE 3GPP UMTS GSM WiMAX High Speed Packet Access HSPA Bluetooth and WiFi. The mobile device may communicate using separate antennas for each wireless communication standard or shared antennas for multiple wireless communication standards. The mobile device may communicate in a WLAN a wireless personal area network WPAN and or a WWAN.

Various techniques or certain aspects or portions thereof may take the form of program code i.e. instructions embodied in tangible media such as for example CD ROMs hard drives Solid State Drives SSD non transitory computer readable storage medium or any other machine readable storage medium wherein when the program code is loaded into and executed by a machine such as a computer the machine becomes an apparatus for practicing the various techniques. In the case of program code execution on programmable computers the computing device may include a processor circuitry a storage medium readable by the processor circuitry including volatile and non volatile memory and or storage elements at least one input device and at least one output device. The volatile and non volatile memory and or storage elements may be a RAM EPROM flash drive optical drive magnetic hard drive or other medium for storing electronic data. One or more programs that may implement or utilize the various techniques described herein may use an application programming interface API reusable controls and the like. Such programs may be implemented in a high level procedural or object oriented programming language to communicate with a computer system. However the program s may be implemented in assembly or machine language if desired. In any case the language may be a compiled or interpreted language and combined with hardware implementations.

Reference is made to which schematically illustrates a product of manufacture in accordance with some demonstrative embodiments. Product may include a non transitory machine readable storage medium to store logic which may be used for example to perform at least part of the functionality of one or more elements of system one or more elements of SoC and or to perform one or more operations of the method of . The phrase non transitory machine readable medium is directed to include all computer readable media with the sole exception being a transitory propagating signal.

In some demonstrative embodiments product and or machine readable storage medium may include one or more types of computer readable storage media capable of storing data including volatile memory non volatile memory removable or non removable memory erasable or non erasable memory writeable or re writeable memory and the like. For example machine readable storage medium may include RAM DRAM Double Data Rate DRAM DDR DRAM SDRAM static RAM SRAM ROM programmable ROM PROM erasable programmable ROM EPROM electrically erasable programmable ROM EEPROM Compact Disk ROM CD ROM Compact Disk Recordable CD R Compact Disk Rewriteable CD RW flash memory e.g. NOR or NAND flash memory content addressable memory CAM polymer memory phase change memory ferroelectric memory silicon oxide nitride oxide silicon SONOS memory a disk a floppy disk a hard drive an optical disk a magnetic disk a card a magnetic card an optical card a tape a cassette and the like. The computer readable storage media may include any suitable media involved with downloading or transferring a computer program from a remote computer to a requesting computer carried by data signals embodied in a carrier wave or other propagation medium through a communication link e.g. a modem radio or network connection.

In some demonstrative embodiments logic may include instructions data and or code which if executed by a machine may cause the machine to perform a method process and or operations as described herein. The machine may include for example any suitable processing platform computing platform computing device processing device computing system processing system computer processor or the like and may be implemented using any suitable combination of hardware software firmware and the like.

Example 1 includes a method for securing sensor data by a security engine circuitry of a system on chip SoC the method comprising receiving from a processor circuitry of the SoC an inter processor communication IPC request to receive the sensor data sending to an integrated sensor hub ISH of the SoC an IPC request for receiving the sensor data receiving the sensor data from the ISH generating certified encrypted sensor data based on the sensor data and sending the certified encrypted sensor data to the processor circuitry.

Example 2 includes the subject matter of Example 1 and optionally wherein generating the certified encrypted sensor data comprises adding a certificate to the sensor data to provide certified sensor data and encrypting the certified sensor data with one or more keys.

Example 3 includes the subject matter of Example 1 or 2 and optionally comprising delivering the certified encrypted sensor data to a middleware MW framework of the processor circuitry.

Example 4 includes the subject matter of any one of Examples 1 3 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a device including the SoC.

Example 5 includes the subject matter of any one of Examples 1 4 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a cloud.

Example 6 includes the subject matter of any one of Examples 1 5 and optionally wherein the certified encrypted sensor data is configured to be certified against user credentials and logged to a database.

Example 7 includes a system on chip SoC configured to secure sensor data the SoC comprising processor circuitry an integrated sensor hub ISH configured to collect and process the sensor data and a security engine configured to receive the sensor data from the ISH certify and encrypt the sensor data and send certified encrypted sensor data to a middleware framework of the processor circuitry the processor circuitry being configured to provide the certified encrypted sensor data to a service.

Example 8 includes the subject matter of Example 7 and optionally wherein the security engine is configured to receive from the processor circuitry an inter processor communication IPC request to provide the secure sensor data.

Example 9 includes the subject matter of Example 7 or 8 and optionally wherein the security engine is configured to send to the ISH an IPC request to receive the sensor data to add a certificate to the sensor data and to send the certified sensor data to the processor circuitry.

Example 10 includes the subject matter of any one of Examples 7 9 and optionally wherein the security engine is configured to generate at least one encryption key to encrypt the sensor data and to add a certificate to the sensor data.

Example 11 includes the subject matter of any one of Examples 7 10 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a device including the SoC.

Example 12 includes the subject matter of any one of Examples 7 11 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a cloud.

Example 13 includes the subject matter of any one of Examples 7 12 and optionally wherein the certified encrypted sensor data is configured to be certified against user credentials and to be logged to a database.

Example 14 includes a computer program product comprising a non transitory computer readable storage medium having a computer readable program code embodied therein the computer readable program code adapted to be executed by a mobile device to implement a method for securing sensor data by security engine circuitry of a system on chip SoC the method comprising receiving from a processor circuitry of the SoC an inter processor communication IPC request to receive the sensor data sending to an integrated sensor hub ISH of the SoC an IPC request for receiving the sensor data receiving the sensor data from the ISH generating certified encrypted sensor data based on the sensor data and sending the certified encrypted sensor data to the processor circuitry.

Example 15 includes the subject matter of Example 14 and optionally wherein sending the certified requested sensor data comprises adding a certificate to the sensor data to provide certified sensor data and encrypting the certified sensor data with one or more keys.

Example 16 includes the subject matter of Example 14 or 15 and optionally wherein the method comprises delivering the certified encrypted sensor data to a middleware MW framework of the processor circuitry.

Example 17 includes the subject matter of any one of Examples 14 16 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a device including the SoC.

Example 18 includes the subject matter of any one of Examples 14 17 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a cloud.

Example 19 includes the subject matter of any one of Examples 14 18 and optionally wherein the certified encrypted sensor data is configured to be certified against a user credentials and logged to a database.

Example 20 includes a mobile device configured to secure sensor data the mobile device comprising a wireless local area radio operably coupled to a system on chip SoC wherein the SoC comprises processor circuitry an integrated sensor hub ISH configured to collect and process the sensor data and a security engine configured to receive the sensor data from the ISH certify and encrypt the sensor data and send certified encrypted sensor data to a middleware framework of the processor circuitry the processor circuitry being configured to provide the certified encrypted sensor data to a service.

Example 21 includes the subject matter of Example 20 and optionally wherein the security engine is configured to receive from the processor circuitry an inter processor communication IPC request to provide the secure sensor data.

Example 22 includes the subject matter of Example 20 or 21 and optionally wherein the security engine is configured to send to the ISH an IPC request to receive the sensor data to add a certificate to the sensor data and to send the certified sensor data to the processor circuitry.

Example 23 includes the subject matter of any one of Examples 20 22 and optionally wherein the security engine is configured to generate at least one encryption key to encrypt the sensor data and to add a certificate to the sensor data.

Example 24 includes the subject matter of any one of Examples 20 23 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a cloud.

Example 25 includes the subject matter of any one of Examples 20 24 and optionally wherein the certified encrypted sensor data is configured to be certified against user credentials and to be logged to a database.

Example 26 includes a mobile device configured to secure sensor data the mobile device comprising a system on chip SoC operably coupled to one or more sensors wherein the SoC comprises processor circuitry an integrated sensor hub ISH configured to collect and process the sensor data and a security engine configured to receive the sensor data from the ISH certify and encrypt the sensor data and send certified encrypted sensor data to a middleware framework of the processor circuitry the processor circuitry being configured to provide the certified encrypted sensor data to a service.

Example 27 includes the subject matter of Example 26 and optionally wherein the security engine is configured to receive from the processor circuitry an inter processor communication IPC request to provide the secure sensor data.

Example 28 includes the subject matter of Example 26 or 27 and optionally wherein the security engine is configured to send to the ISH an IPC request to receive the sensor data to add a certificate to the sensor data and to send the certified sensor data to the processor circuitry.

Example 29 includes the subject matter of any one of Examples 26 28 and optionally wherein the security engine is configured to generate at least one encryption key to encrypt the sensor data and to add a certificate to the sensor data.

Example 30 includes the subject matter of any one of Examples 26 29 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a cloud.

Example 31 includes the subject matter of any one of Examples 26 30 and optionally wherein the certified encrypted sensor data is configured to be certified against user credentials and to be logged to a database.

Example 32 includes the subject matter of any one of Examples 26 31 and optionally wherein the one or more sensors are external to the mobile device.

Example 33 includes a system on chip SoC configured to secure sensor data the SoC comprising means to perform the method of any one of Examples 1 6.

Example 34 includes a computer program product comprising a non transitory computer readable storage medium having a computer readable program code embodied therein the computer readable program code adapted to be executed by a mobile device to implement the method of any one of Examples 1 6.

Example 35 includes a mobile device configured to secure sensor data comprising a wireless local area radio operably coupled to a system on chip SoC wherein the SoC comprises means to perform the method of any one of Examples 1 6.

Example 36 includes a system on chip SoC configured to secure sensor data the SoC comprising processor circuitry an integrated sensor hub ISH means configured to collect and process the sensor data and a security engine means configured to receive the sensor data from the ISH certify and encrypt the sensor data and send certified encrypted sensor data to a middleware framework of the processor circuitry the processor circuitry being configured to provide the certified encrypted sensor data to a service.

Example 37 includes the subject matter of Example 36 and optionally wherein the security engine means is configured to receive from the processor circuitry SoC an inter processor communication IPC request to provide the secure sensor data.

Example 38 includes the subject matter of Example 36 or 37 and optionally wherein the security engine means is configured to send to the ISH means an IPC request to receive the sensor data to add a certificate to the sensor data and to send the certified sensor data to the processor circuitry.

Example 39 includes the subject matter of any one of Examples 36 38 and optionally wherein the security engine means is configured to generate at least one encryption key to encrypt the sensor data and to add a certificate to the sensor data.

Example 40 includes the subject matter of any one of Examples 36 39 and optionally wherein the certified encrypted sensor data is to be delivered to a middleware MW framework of the processor circuitry.

Example 41 includes the subject matter of any one of Examples 36 40 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a device including the SoC.

Example 42 includes the subject matter of any one of Examples 36 41 and optionally wherein the certified encrypted sensor data is configured to be used by a service in a cloud.

Example 43 includes the subject matter of any one of Examples 36 42 and optionally wherein the certified encrypted sensor data is configured to be certified against user credentials and to be logged to a database.

It should be understood that many of the functional units described in this specification have been labeled as modules in order to more particularly emphasize their implementation independence. For example a module may be implemented as a hardware circuit comprising custom VLSI circuits or gate arrays off the shelf semiconductors such as logic chips transistors or other discrete components. A module may also be implemented in programmable hardware devices such as field programmable gate arrays programmable array logic programmable logic devices or the like.

Modules may also be implemented in software for execution by various types of processors. An identified module of executable code may for instance comprise one or more physical or logical blocks of computer instructions which may for instance be organized as an object procedure or function. Nevertheless the executables of an identified module need not be physically located together but may comprise disparate instructions stored in different locations which when joined logically together comprise the module and achieve the stated purpose for the module.

Indeed a module of executable code may be a single instruction or many instructions and may even be distributed over several different code segments among different programs and across several memory devices. Similarly operational data may be identified and illustrated herein within modules and may be embodied in any suitable form and organized within any suitable type of data structure. The operational data may be collected as a single data set or may be distributed over different locations including over different storage devices and may exist at least partially merely as electronic signals on a system or network. The modules may be passive or active including agents operable to perform desired functions.

As used herein a plurality of items structural elements compositional elements and or materials may be presented in a common list for convenience. However these lists should be construed as though each member of the list is individually identified as a separate and unique member. Thus no individual member of such list should be construed as a de facto equivalent of any other member of the same list solely based on their presentation in a common group without indications to the contrary. In addition various embodiments and example ay be referred to herein along with alternatives for the various components thereof. It is understood that such embodiments examples and alternatives are not to be construed as defacto equivalents of one another but are to be considered as separate and autonomous representations.

Furthermore the described features structures or characteristics may be combined in any suitable manner in one or more embodiments.

In the foregoing description numerous specific details are provided such as examples of layouts distances network examples etc. to provide a thorough understanding of some demonstrative embodiments. One skilled in the relevant art will recognize however that some embodiments can be practiced without one or more of the specific details or with other methods components layouts etc. In other instances well known structures materials or operations are not shown or described in detail to avoid obscuring aspects of the disclosure.

While the forgoing examples are illustrative of the principles of some embodiments in one or more particular applications it will be apparent to those of ordinary skill in the art that numerous modifications in form usage and details of implementation can be made without the exercise of inventive faculty and without departing from the principles and concepts of the disclosure. Accordingly it is not intended that the disclosure be limited except as by the claims set forth below.

