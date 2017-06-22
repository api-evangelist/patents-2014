---

title: Self-service terminal (SST) device driver
abstract: Methods for extensible device drivers and an extensible device driver Self-Service Terminal (SST) are provided. A SST includes an operating system (OS) having a communication port and an application having low-level commands that are specific to a hardware device, which is coupled to the SST; the low-level commands directly capable of being executed by the device. The communication port is operable to relay information and commands (including the low-level commands) between the device and the application. The application directly controls the device, with the low-level commands, and the low-level commands unrecognized by the OS.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09483420&OS=09483420&RS=09483420
owner: NCR Corporation
number: 09483420
owner_city: Duluth
owner_country: US
publication_date: 20140228
---
Traditionally hardware drivers are packaged as separate binary components that extend the Operating System OS the hardware drivers also provide Application Programming Interfaces APIs to applications for controlling devices associated with the drivers. This separation between the OS components and the application components API adds complexity to updates requiring either 

The issues associated with hardware device installation are particularly noticeable with Self Service Terminals SSTs such as Automated Teller Machines ATMs . An ATM is a highly secure type of SST where administrative access to the underlying OS hardware devices and software is restricted to select engineers. Remote network access is generally forbidden even to the servicing engineers. As a result when a new hardware device is swapped out of the ATM for a defective device or when a new device with newer features is installed on the ATM the bank staff has to wait for an available engineer and the update process can take some time. Moreover the OS itself may not even permit the newer device or may require an update to the OS which can also add significant time and complexity to the installation and testing of a new device on the ATM platform.

In various embodiments an extensible Self Service Terminal SST device driver and techniques for installing and using the SST device driver are presented.

According to an embodiment a SST is provided that includes an Operating System OS and an application. The OS includes a communication port and the application includes low level commands specific to a hardware device which is coupled to the SST through the communication port and the low level commands directly executable by the hardware device. The communication port operable to relay information and commands between the hardware device and the application and the application directly controls the hardware device the low level commands unrecognized by the OS.

The ATM methods and SST presented herein and below for extensible SST device driver operation can be implemented in whole or in part in one all or some combination of the components shown with the ATM . The techniques and methods are programmed as executable instructions in memory and or non transitory computer readable storage media and processed on one or more processors associated with the various components. Moreover the ATM is shown in greatly simplified form illustrating primarily but not exclusively just the components that are enhanced or that are necessary for comprehending the teachings presented herein.

The discussion that follows represents one embodiment of the invention for an application within an ATM . It is noted that any SST such as a kiosk or any device can benefit from the teachings presented herein some of which are discussed with reference to the . Thus the description that follows below is but one embodiment of the invention and it not intended to limit the invention to only financial transactions at financial facilities.

The ATM includes an operating system OS an OS communication port API an application having physical device commands a communication port and a coupled hardware device .

The OS provides a processing environment platform for executing commands operations and applications and for accessing devices and peripherals coupled or interfaced to the OS .

In an embodiment the OS is selected from one of Tizen Unix or Linux based open source OS and other open source OSs.

In an embodiment the OS is selected from one of Windows Apple iOS Blackberry and other non open source or proprietary OSs .

The OS communication port API is an interface provided by the OS to applications such as application for access to a communication port of the ATM . Primarily this port API allows an application to connect direct to the port and pass commands from the application to the hardware device coupled to the ATM though the port .

The application is configured with the physical device commands necessary to access and communicate with the coupled hardware device . The physical device commands can be in any low level format expected and recognized by the coupled hardware device such as but not limited to binary instructions and memory or storage locations and offsets for activating commands and storage locations. In some cases the physical device commands can be at a higher level such that recognized API calls can be made. But regardless of the level of abstraction associated with the physical device commands the OS lacks and does not recognize that format the OS just connects the application to the port and provides the port API for the application to communicated with the hardware device .

The OS also terminates the connection between the application and the port . This can occur when the application specifically issues an OS recognized command to terminate the connection the command may also be part of the port API . This can also occur when the application is terminated normally or abnormally from execution within the ATM or can occur when the hardware device is decoupled removed from port .

Additionally the application is the device driver for the hardware device . That is the OS lacks a device driver to service the hardware device . The device driver is referred to as a soft driver because access to device specific low level commands is controlled by a user application such as application and not by the OS which is typically the case. Thus access to the hardware device cannot be achieved outside the scope of execution for the application . This provides additional security to the ATM which is critical in ATM environments because any access occurring originates from the application .

Typically when a new device is installed on a device the OS restricts access to that device until the OS can locate and install a device driver for interfacing with the device through a communication port to deliver device specific commands and to receive device specific responses.

However as will be illustrated more completely herein and below the OS requires no device driver to install and permit communication with a newly coupled hardware device . Rather the application provides the device driver to the coupled hardware device by requesting the OS to connect the application to the port and by using the OS provided port API from which the application can deliver physical device commands to the hardware device and receive responses from the hardware device .

The application may also have an application interface providing user interaction capabilities and or application API commands for other application layer applications to interact with the application .

During operation of the application within the ATM the hardware device is detected as being connected coupled or interfaced to the ATM s communication port . This causes the OS to receive notice of the connection over the port . The notice is communicated by the OS to the application . This can occur via a notification command of the port API or via other OS provided commands configured in the application .

Once the application receives the notice from the OS the application requests a connection to the port . This can occur via a command in the port API or via a standard port connection command configured in the application and recognized by the OS .

After the connection to the port the application uses commands selected from the port API to issue the physical device commands over the port and directly to the hardware device . The hardware device recognizes the commands and takes the appropriate actions and perhaps delivers responses or other data back through the port which may also be in a device specific format. The application being connected to the port receives the responses or other data and processes that according to the application s configured logic.

In an embodiment each device command is encrypted or includes a key that is only capable of decryption or validation between the hardware device and the application . In this manner security can be further enhanced because the hardware device is preconfigured to valid each command and provided encrypted data back as a response. So assuming the application were replaced or modified by an unauthorized application within the OS of the ATM and that application somehow knew the device commands communications between that application and the hardware device would fail because the encrypted communications or validations would fail on the hardware device .

Security is of particular concern to ATMs since financial transactions of consumers are occurring and since ATMs are equipped with large amounts of currency.

Maintenance support and management are also issues for staff that services the ATMs with respect to coupled hardware devices. The techniques of providing soft device driver support on an ATM though an application of the OS improve maintenance support and management of the ATM beyond what has heretofore been available in the industry.

For example an update to the application is also an update or provides an opportunity for updating the commands which effectively updates device driver support for the hardware device . It is noted this occurs without requiring any update to the OS .

Furthermore since the device commands are controlled by the application perhaps via a file reference and indexing mechanism the device commands can be updated soft driver update by replacing a file accessible to the application . This provides great flexibility with respect to managing the application and the device driver for the hardware device because the commands are not hardcoded in the application and replacing a file having the commands effectively updates the device driver without updating the application and without updates to the OS .

It is also noted that the application can have different sets and types of device commands for device driver support of different devices coupled to the ATM . So one application can server as multiple soft device drivers for multiple hardware devices. Different port APIs can also be used for different communication ports accessible on the ATM and as provided to applications.

Moreover it is to be noted that although ATM depicts a single application there can actually be multiple independent applications for application each having its own physical device commands some may be directed to the same hardware device or directed to a different coupled hardware device . As stated before the ATM is provided in greatly simplified form and the single application and single hardware device are presented for purposes of illustration only and such depiction is not intended to limit the scope of ATM to just a configuration having single instances of the application and the hardware device .

In an embodiment the hardware device is a dispenser that dispenses valuable media at the AMT such as currency rewards virtual currency via interfaced non transitory computer readable media devices coupons and the like.

In an embodiment the communication port is selected from one of a Video Graphics Array VGA port a High Definition Multimedia Interface HDMI and an Apple Thunderbolt port.

One now appreciates how device driver support for coupled hardware device of an ATM can be achieved via an application within an application layer of an OS . This improves security and removes the dependency of device drivers from the OS when the OS is updated or when the device driver is updated. This also improves maintenance support and management of the hardware device more efficiently than what has heretofore been available in the industry.

So initially at a processor s of the host device executes the soft device driver referred to as application in the on that host device within an OS that provides the processing environment or platform for the soft device driver.

At the soft device driver connects to a hardware device that is coupled to the host device. This may be after the OS notifies the soft device driver that the hardware device is present or connected to a communication port of the host device.

According to an embodiment at the soft device driver selects a connect command from available commands provided by the OS in a USB port API for communication by the application with the communication port that the hardware device is coupled to.

At the soft device driver a low level command device specific command for communication with the hardware device. That is the soft device driver selects a particular command from the commands recognized by the hardware device physical device commands or device commands recognized by the hardware device .

In an embodiment at the soft device driver determines the low level device command based on a processing condition evaluated by the soft device driver that necessitated a communication or access between the soft device driver and the hardware device. This can be any logic evaluated in the soft device driver.

At the soft device driver issues the low level device command to the hardware device coupled to the host device using an OS communication port API provided by the OS. The OS does not recognize the low level device command.

According to an embodiment at the soft device driver provides the low level device command as a physical device command that is specific and proprietary to the hardware device. Again this physical device command is unrecognized by the OS. This means the OS does not know how to handle or recognize the format of the physical device command.

In an embodiment at the soft device driver receives from the hardware device a response to the initially issued low level device command. The response is received through the OS communication port API.

In an embodiment at the software is processed by the processor of the host device and the processing associated with as a soft device driver for the hardware device. In other words the soft device driver is a device driver for the hardware device and the OS lacks a device driver for independently interacting with the hardware device. The soft device driver is the device driver for the hardware device.

According to an embodiment of and at the soft device driver updates the soft device driver by updating the low level device command and or updating other low level device commands within the soft device driver. This can be done when the low level device commands are available within files accessible to the soft device driver such that the soft device driver selects a new file or selects a file that was modified to effectively update the soft device driver.

In another case at the processor of the host device that executes the soft device driver updates the soft driver by updating the soft device driver.

At the SST soft driver OS detects a presence of a newly coupled device to the SST. This is achieved through a communication port interface for a communication port that the SST soft driver OS is managing for the SST.

According to an embodiment at the SST soft driver OS detects the presence on a USB communication port interface that is monitored by the SST soft driver OS.

At the SST device driver manager notifies an application of the presence detected on the communication port interface of the SST.

The notification can occur via a communication port interface API provided to the application by the SST soft driver OS alternatively the notification can occur via standard device notification messages of the OS to the application.

According to an embodiment of and and at the SST soft driver OS provides the notification as a USB attached device notification recognized by the processing logic of the application as the coupled device to the SST via the communication port.

At the SST soft driver OS establishes a connection between the application and the coupled device. This is done in response to a connection request issued by the application to the SST soft driver OS. Again the connection request can be issued by the application using a communication port interface API provided by the OS to the application or the application issues an SST soft driver OS command recognized by the SST soft driver OS which is not included in the communication port API standard device connection request .

According to an embodiment at the SST soft driver OS provides the connection between the application and the coupled device as a tunnel between the application and the communication port of the SST to which the coupled device is attached.

In an embodiment at the SST soft driver OS terminates the connection when coupled device is decoupled from the communication port of the SST. For example someone has physically removed the coupled device from the communication port e.g. disconnected a USB device from a USB port .

In an embodiment at the SST soft driver OS terminates the connection when the SST soft driver OS receives a connection termination command from the application or when the application ceases to execute on the SST such as when the application terminates normally or abnormally .

At the SST soft driver OS provides an OS communication port API to the application for the application to communicate with the communication port of the SST that the coupled device is attached to. The application uses the connection and the communication port API to communicate with the coupled device directly. The application issues device specific commands during the connection that are recognized and processed by the coupled device. The connection OS communication port API and the application having the device specific commands permit the application to act as a soft device driver for the coupled device. The device specific commands are unrecognized by the SST soft driver OS and the SST soft driver OS lacks a device driver for the coupled device. So the application is the device driver for communication with the coupled device.

According to an embodiment at the SST soft driver OS ignores the presence of the coupled device attached to the communication port of the SST when the application is not actively executing on the SST.

In an embodiment at the SST soft driver OS updates the application and the update results in an update to the device specific commands. Essentially an update to the application is an update to the device driver because the application is a soft device driver for the coupled device via the device specific commands .

The SST includes an application software module or set of modules that execute as executable instructions on one or more processes of the SST . The executable instructions reside in memory and or a non transitory computer readable storage medium accessible to the SST .

The application operable to execute within an OS on the SST and connect to a communication port of the SST to which a hardware device is coupled. The extensible SST is also operable to issue device specific commands to the hardware device during the connection through a communication port API provided by the OS to direct the device specific commands from the application to the communication port. The device specific commands are unrecognized by and inaccessible to the OS and the device specific commands are recognized by and processed on the hardware device.

According to an embodiment the application is further operable to process as a soft device driver for the hardware device though the device specific commands and process as an interface to managing controlling and accessing the hardware device through a user API accessible from the user application layer of the OS.

In an embodiment the OS is an enhanced OS or enhanced feature to an OS represented by the method of the .

In an embodiment the hardware device is inaccessible outside an execution space associated with the application within the OS.

According to an embodiment the SST is an ATM and the hardware device is media dispenser coupled to the ATM via a USB communication port.

It should be appreciated that where software is described in a particular form such as a component or module this is merely to aid understanding and is not intended to limit how software that implements those functions may be architected or structured. For example modules may be illustrated as separate modules but may be implemented as homogenous code as individual components some but not all of these modules may be combined or the functions may be implemented in software structured in any other convenient manner.

Furthermore although the software modules are illustrated as executing on one piece of hardware the software may be distributed over multiple processors of a single device or in any other convenient manner.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

