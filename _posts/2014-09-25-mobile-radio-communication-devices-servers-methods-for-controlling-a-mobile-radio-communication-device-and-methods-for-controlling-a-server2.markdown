---

title: Mobile radio communication devices, servers, methods for controlling a mobile radio communication device, and methods for controlling a server
abstract: A mobile radio communication device is described comprising: an instruction receiver configured to receive an instruction from a second mobile radio communication device to request subscriber identity module installation data for installation of a second subscriber identity module, wherein the second subscriber identity module is related to a first subscriber identity module that is installed in the second mobile radio communication device; a request transmitter configured to transmit a request for the subscriber identity module installation data to a first server; a subscription data receiver configured to receive the subscriber identity module installation data from a second server; and a controller configured to install the second subscriber identity module based on the received subscriber identity module installation data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09609458&OS=09609458&RS=09609458
owner: INTEL IP CORPORATION
number: 09609458
owner_city: Santa Clara
owner_country: US
publication_date: 20140925
---
The present disclosure generally relates to mobile radio communication devices servers methods for controlling a mobile radio communication device and methods for controlling a server.

Today s mobile devices mostly being smart devices smartphone tablet and computer Ultrabook are equipped with a range of connectivity options. Thus there may be a desire for efficiently handling these connectivity options.

The following detailed description refers to the accompanying drawings that show by way of illustration specific details and aspects of this disclosure in which various aspects of this disclosure may be practiced. Other aspects may be utilized and structural logical and electrical changes may be made without departing from the scope of the various aspects of this disclosure. The various aspects of this disclosure are not necessarily mutually exclusive as some aspects of this disclosure can be combined with one or more other aspects of this disclosure to form new aspects.

The terms coupling or connection are intended to include a direct coupling or direct connection as well as an indirect coupling or indirect connection respectively.

The word exemplary is used herein to mean serving as an example instance or illustration . Any aspect of this disclosure or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspect of this disclosure or designs.

The mobile radio communication device may include a memory which may for example be used in the processing carried out by the mobile radio communication device. The server may include a memory which may for example be used in the processing carried out by the server. A memory may be a volatile memory for example a DRAM Dynamic Random Access Memory or a non volatile memory for example a PROM Programmable Read Only Memory an EPROM Erasable PROM EEPROM Electrically Erasable PROM or a flash memory for example a floating gate memory a charge trapping memory an MRAM Magnetoresistive Random Access Memory or a PCRAM Phase Change Random Access Memory .

As used herein a circuit may be understood as any kind of a logic implementing entity which may be special purpose circuitry or a processor executing software stored in a memory firmware or any combination thereof. Furthermore a circuit may be a hard wired logic circuit or a programmable logic circuit such as a programmable processor for example a microprocessor for example a Complex Instruction Set Computer CISC processor or a Reduced Instruction Set Computer RISC processor . A circuit may also be a processor executing software for example any kind of computer program for example a computer program using a virtual machine code such as for example Java. Any other kind of implementation of the respective functions which will be described in more detail below may also be understood as a circuit . It may also be understood that any two or more of the described circuits may be combined into one circuit.

Description is provided for devices and description is provided for methods. It will be understood that basic properties of the devices also hold for the methods and vice versa. Therefore for sake of brevity duplicate description of such properties may be omitted.

It will be understood that any property described herein for a specific device may also hold for any device described herein. It will be understood that any property described herein for a specific method may also hold for any method described herein.

UICC Universal Integrated Circuit Card may be a specific type of smart card used in mobile terminals compliant to the 3GPP standard 2G second generation GSM Global System for Mobile Communications 3G third generation UMTS Universal Mobile Telecommunications System and 4G fourth generation LTE Long Term Evolution technologies . The UICC may securely store the SIM Subscriber Identification Module application or USIM UMTS Subscriber Identification Information application which allows the UE user equipment to connect to a mobile network. The SIM may store the International Mobile Subscriber Identity IMSI and the related secure keys which may be used to identify and authenticate the subscribers on the network with the Mobile Device e.g. a phone tablet or computer Ultrabook . The UICC may also contain several applications Java Card Applets making it possible for the same smart card to give access to both GSM and UMTS networks and also provide storage of phone book and other applications. The UICC ensures the integrity and security of personal data typically in a few hundred kilobytes.

Today s mobile devices mostly being smart devices smartphone tablet and computer Ultrabook are equipped with a range of connectivity options. With various radio communication devices on the smartphone such as NFC Near Field Communication Bluetooth WiFi etc. the smart devices are becoming a catalyst for Internet of Things IoT . To enable a seamless and high quality user experience it is crucial to identify the user s persona securely associating this sensitive data with a particular device.

Today we have the following limitations in the usage of the current UICC and the mobile subscription on smart devices 

1 Mobile Network Operator MNO Subscription parameters and security credentials are hosted on the UICC via SIM application and this application is specific to one particular MNO thus limiting the mobile subscriber to connect only to that MNO s network.

2 When the mobile subscriber user is roaming abroad either the user has to incur hefty roaming charges or go to a store to purchase a local SIM card thus having to manage multiple physical SIM cards and change accordingly.

3 Missing SIM card personalization. Current UICC for smart devices is limited in programming ability to remotely provision activate over the air newer subscriptions or transfer subscriptions between devices.

5 No user access and control for subscription management for a specific UICC. The mobile subscriber user is only able to switch between multiple physical SIM cards see 3. 

6 Missing network entity to manage multiple subscriptions services on devices. Currently MNO s are regarding the UICC as their property and are not interested in supporting the subscriber in his wish to be able to manage multiple subscriptions on a single SIM .

According to various aspects of this disclosure mobile subscription management for example using NFC Tap and Activate application may be provided.

In other words the mobile radio communication device may based on an instruction from another mobile radio communication device request receive and install data related to a subscriber identity mobile which is related to a subscriber identity module installed in the other mobile radio communication device.

It is to be noted that each mobile radio communication device may be getting its own subscription including an own International Mobile Subscriber Identity IMSI own security credentials secret key etc. . . . So the subscriber identity module which may also be referred to as subscription installed in the second mobile radio communication device may be different from the subscription already stored in the first mobile radio communication device. But the two subscriptions may be related to each other in so far as e.g. an Ultra Mobility Server knows that they are belonging to the same mobile data plan.

Besides the primary and secondary device a further device which may be referred to as Master device may be provided like will be described in the following.

The primary device may be a device owned by the user that is capable of having the first subscription. For example if the device itself does not have NFC capability it may become the primary device by inserting an NFC card. This NFC Card may have the form factor and functionality of a legacy UICC card which additionally has NFC capability. So the NFC card may be plugged into the normal SIM slot of a smartphone device that may become the primary device and may be used to Tap and Activate secondary devices.

Alternatively the primary device itself may already be equipped with an NFC chip and thus have NFC capability. In this case it may be sufficient to insert a UICC card without NFC capability in the SIM slot. By using the first subscription of the data plan stored on the UICC card and the NFC capability of the device the device may then act as a primary device.

The Master device may be a device owned by an operator or telecom shop owner that is capable to Tap and Activate a primary device. The Master device may include an NFC card with the form factor of a legacy UICC card. The UICC card may be storing a special subscription by which the Master device is enabled to turn e.g. a smartphone device into a primary device by tapping it and thus triggering the transfer of the first subscription of a data plan to the device.

I.e. the relationship between Master device and primary device may be similar to the relationship between primary device and secondary device however for example a primary device may only activate a small number of secondary devices as limited by the data plan whereas the Master device may activate a much bigger number of primary devices limited e.g. by a contract between the telecom shop owner and the operator and by the size of the pool of subscriptions that is reserved on the Subscription Management Server for the Ultra Mobility Server like described below .

The second mobile radio communication device may include a short range receiver. Correspondingly the first mobile radio communication device may include a short range transmitter so that it can signal a tap to the second device.

It is to be noted that the second mobile radio communication device can receive data Server Response from the Ultra Mobility Server UMS step in and later the actual subscription data step from the Subscription Management Server SubMan possibly via a different connection.

In other words the first server may receive a request for subscriber identity module installation data from a mobile radio communication device and may transmit the request to another server.

In other words the second server may receive a request for subscriber identity module installation data from a first server and may transmit the subscriber identity module installation data to a mobile radio communication device.

For example the server may deliver the subscription data to a certain IP Internet Protocol address Addr 2 which was assigned to the secondary device when it attached to the network. This attach may have happened via a cellular mobile network in which case the subscription data will be delivered via this mobile network via a gateway to this mobile network or it may have happened via a WLAN wireless local area network packet data network in which case the subscription data may be delivered via this packet data network via a gateway to this packet data network . In both cases the direct interface of the subscription data transmitter may be to a packet data network.

In other words the server may receive a request for subscriber identity module installation data from a mobile radio communication device and may transmit the subscriber identity module installation data to the mobile radio communication device.

Example 1 as described with reference to is a mobile radio communication device comprising an instruction receiver configured to receive an instruction from a second mobile radio communication device to request subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in the second mobile radio communication device a request transmitter configured to transmit a request for the subscriber identity module installation data to a first server a subscription data receiver configured to receive the subscriber identity module installation data from a second server and a controller configured to install the second subscriber identity module based on the received subscriber identity module installation data.

In Example 2 the subject matter of Example 1 can optionally include that the instruction receiver comprises a Near Field Communication receiver.

In Example 3 the subject matter of any one of Examples 1 2 can optionally include that the request transmitter comprises at least one of a cellular mobile radio communication transmitter a WLAN transmitter a transmitter of an ethernet card a transmitter of an interface card or a core network transmitter.

In Example 4 the subject matter of any one of Examples 1 3 can optionally include that the subscription data receiver comprises at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 5 the subject matter of any one of Examples 1 4 can optionally include a subscriber identity module circuit.

In Example 6 the subject matter of Example 5 can optionally include that the controller is configured to install the second subscriber identity module in the subscriber identity module circuit.

In Example 7 the subject matter of any one of Examples 1 6 can optionally include a short range receiver configured to receive event data from the second mobile radio communication device wherein the instruction receiver is configured to receive the instruction from the second mobile radio communication device based on the event data.

In Example 8 the subject matter of any one of Examples 1 7 can optionally include that the short range receiver comprises a Near Field Communication receiver.

In Example 9 the subject matter of any one of Examples 1 8 can optionally include that the second server comprises the first server.

In Example 10 the subject matter of any one of Examples 1 9 can optionally include a processor wherein the processor comprises the instruction receiver and the controller.

Example 11 as described with reference to is a first server comprising a request receiver configured to receive from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and a request transmitter configured to transmit to a second server a request to transmit the subscriber identity module installation data to the second mobile radio communication device.

In Example 12 the subject matter of Example 11 can optionally include that the request receiver comprises at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 13 the subject matter of any one of Examples 11 12 can optionally include that the request transmitter comprises a core network transmitter.

Example 14 as described with reference to is a second server comprising a request receiver configured to receive from a first server a request to transmit subscriber identity module installation data for installation of a first subscriber identity module to a first mobile radio communication device and a subscription data transmitter configured to transmit the subscriber identity module installation data to the first mobile radio communication device.

In Example 15 the subject matter of Example 14 can optionally include that the first subscriber identity module is related to a second subscriber identity module that is installed in a second mobile radio communication device.

In Example 16 the subject matter of any one of Examples 14 15 can optionally include that the request receiver comprises a core network receiver.

In Example 17 the subject matter of any one of Examples 14 16 can optionally include that the subscription data transmitter comprises a core network transmitter.

Example 18 as described with reference to is a server comprising a request receiver configured to receive from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and a subscription data transmitter configured to transmit the subscriber identity module installation data to the second mobile radio communication device.

In Example 19 the subject matter of Example 18 can optionally include that the request receiver comprises at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 20 the subject matter of any one of Examples 18 19 can optionally include that the subscription data transmitter comprises a core network transmitter.

Example 21 as described with reference to is a method for controlling a mobile radio communication device the method comprising receiving an instruction from a second mobile radio communication device to request subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in the second mobile radio communication device transmitting a request for the subscriber identity module installation data to a first server receiving the subscriber identity module installation data from a second server and installing the second subscriber identity module based on the received subscriber identity module installation data.

In Example 22 the subject matter of Example 21 can optionally include that receiving the instruction comprises receiving the instruction using a Near Field Communication receiver.

In Example 23 the subject matter of any one of Examples 21 22 can optionally include that transmitting the request comprises transmitting the request using at least one of a cellular mobile radio communication transmitter a WLAN transmitter a transmitter of an ethernet card a transmitter of an interface card or a core network transmitter.

In Example 24 the subject matter of any one of Examples 21 23 can optionally include that receiving the subscription data comprises receiving the subscription data using at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 25 the subject matter of any one of Examples 21 24 can optionally include controlling a subscriber identity module circuit.

In Example 26 the subject matter of Example 25 can optionally include that installing the second subscriber identity module comprises installing the second subscriber identity module in the subscriber identity module circuit.

In Example 27 the subject matter of any one of Examples 21 26 can optionally include receiving event data from the second mobile radio communication device wherein receiving the instruction comprises receiving the instruction from the second mobile radio communication device based on the event data.

In Example 28 the subject matter of Example 27 can optionally include that receiving the event data comprises receiving the event data using a Near Field Communication receiver.

In Example 29 the subject matter of any one of Examples 21 28 can optionally include that the second server comprises the first server.

In Example 30 the subject matter of any one of Examples 21 29 can optionally include controlling a processor wherein controlling the processor comprises receiving the receiver and installing the second subscriber identity module.

Example 31 as described with reference to is a method for controlling a first server the method comprising receiving from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and transmitting to a second server a request to transmit the subscriber identity module installation data to the second mobile radio communication device.

In Example 32 the subject matter of Example 31 can optionally include that receiving the request comprises receiving the request using at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 33 the subject matter of any one of Examples 31 32 can optionally include that transmitting the request comprises transmitting the request using a core network transmitter.

Example 34 as described with reference to is a method for controlling a second server the method comprising receiving from a first server a request to transmit subscriber identity module installation data for installation of a first subscriber identity module to a first mobile radio communication device and transmitting the subscriber identity module installation data to the first mobile radio communication device.

In Example 35 the subject matter of Example 34 can optionally include that the first subscriber identity module is related to a second subscriber identity module that is installed in a second mobile radio communication device.

In Example 36 the subject matter of any one of Examples 34 35 can optionally include that receiving the request comprises receiving the request using a core network receiver.

In Example 37 the subject matter of any one of Examples 34 36 can optionally include that transmitting the subscription data comprises transmitting the subscription data using a core network transmitter.

Example 38 as described with reference to is a method for controlling a server the method comprising receiving from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and transmitting the subscriber identity module installation data to the second mobile radio communication device.

In Example 39 the subject matter of Example 38 can optionally include that receiving the request comprises receiving the request using at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 40 the subject matter of any one of Examples 38 39 can optionally include that transmitting the subscription data comprises transmitting the subscription data using a core network transmitter.

In Example 41 is a mobile radio communication device comprising an instruction receiving means for receiving an instruction from a second mobile radio communication device to request subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in the second mobile radio communication device a request transmitting means for transmitting a request for the subscriber identity module installation data to a first server a subscription data receiving means for receiving the subscriber identity module installation data from a second server and a controlling means for installing the second subscriber identity module based on the received subscriber identity module installation data.

In Example 42 the subject matter of Example 41 can optionally include that the instruction receiving means comprises a Near Field Communication receiver.

In Example 43 the subject matter of any one of Examples 41 42 can optionally include that the request transmitting means comprises at least one of a cellular mobile radio communication transmitter a WLAN transmitter a transmitter of an ethernet card a transmitter of an interface card or a core network transmitter.

In Example 44 the subject matter of any one of Examples 41 43 can optionally include that the subscription data receiving means comprises at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 45 the subject matter of any one of Examples 41 44 can optionally include a subscriber identity module means.

In Example 46 the subject matter of Example 45 can optionally include that the controlling means is for installing the second subscriber identity module in the subscriber identity module circuit.

In Example 47 the subject matter of any one of Examples 41 46 can optionally include a short range receiving means for receiving event data from the second mobile radio communication device wherein the instruction receiving means is for receiving the instruction from the second mobile radio communication device based on the event data.

In Example 48 the subject matter of Example 47 can optionally include that the short range receiving means comprises a Near Field Communication receiver.

In Example 49 the subject matter of any one of Examples 41 48 can optionally include that the second server comprises the first server.

In Example 50 the subject matter of any one of Examples 41 49 can optionally include a processing means wherein the processing means comprises the instruction receiving means and the controlling means.

Example 51 is a first server comprising a request receiving means for receiving from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and a request transmitting means for transmitting to a second server a request to transmit the subscriber identity module installation data to the second mobile radio communication device.

In Example 52 the subject matter of Example 51 can optionally include that the request receiving means comprises at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 53 the subject matter of any one of Examples 51 52 can optionally include that the request transmitting means comprises a core network transmitter.

Example 54 is a second server comprising a request receiving means for receiving from a first server a request to transmit subscriber identity module installation data for installation of a first subscriber identity module to a first mobile radio communication device and a subscription data transmitting means for transmitting the subscriber identity module installation data to the first mobile radio communication device.

In Example 55 the subject matter of Example 54 can optionally include that the first subscriber identity module is related to a second subscriber identity module that is installed in a second mobile radio communication device.

In Example 56 the subject matter of any one of Examples 54 55 can optionally include that the request receiving means comprises a core network receiver.

In Example 57 the subject matter of any one of Examples 54 56 can optionally include that the subscription data transmitting means comprises a core network transmitter.

Example 58 is a server comprising a request receiving means for receiving from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and a subscription data transmitting means for transmitting the subscriber identity module installation data to the second mobile radio communication device.

In Example 59 the subject matter of Example 58 can optionally include that the request receiving means comprises at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 60 the subject matter of any one of Examples 58 59 can optionally include that the subscription data transmitting means comprises a core network transmitter.

Example 61 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for controlling a mobile radio communication device comprising receiving an instruction from a second mobile radio communication device to request subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in the second mobile radio communication device transmitting a request for the subscriber identity module installation data to a first server receiving the subscriber identity module installation data from a second server and installing the second subscriber identity module based on the received subscriber identity module installation data.

In Example 62 the subject matter of Example 61 can optionally include that receiving the instruction comprises receiving the instruction using a Near Field Communication receiver.

In Example 63 the subject matter of any one of Examples 61 62 can optionally include that transmitting the request comprises transmitting the request using at least one of a cellular mobile radio communication transmitter a WLAN transmitter a transmitter of an ethernet card a transmitter of an interface card or a core network transmitter.

In Example 64 the subject matter of any one of Examples 61 63 can optionally include that receiving the subscription data comprises receiving the subscription data using at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 65 the subject matter of any one of Examples 61 64 can optionally include recorded instructions thereon which when executed by a processor make the processor perform controlling a subscriber identity module circuit.

In Example 66 the subject matter of Example 65 can optionally include that installing the second subscriber identity module comprises installing the second subscriber identity module in the subscriber identity module circuit.

In Example 67 the subject matter of any one of Examples 61 66 can optionally include recorded instructions thereon which when executed by a processor make the processor perform receiving event data from the second mobile radio communication device wherein receiving the instruction comprises receiving the instruction from the second mobile radio communication device based on the event data.

In Example 68 the subject matter of Example 67 can optionally include that receiving the event data comprises receiving the event data using a Near Field Communication receiver.

In Example 69 the subject matter of any one of Examples 61 68 can optionally include that the second server comprises the first server.

In Example 70 the subject matter of any one of Examples 61 69 can optionally include recorded instructions thereon which when executed by a processor make the processor perform controlling a processor wherein controlling the processor comprises receiving the receiver and installing the second subscriber identity module.

Example 71 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for controlling a first server comprising receiving from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and transmitting to a second server a request to transmit the subscriber identity module installation data to the second mobile radio communication device.

In Example 72 the subject matter of Example 71 can optionally include that receiving the request comprises receiving the request using at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 73 the subject matter of any one of Examples 71 72 can optionally include that transmitting the request comprises transmitting the request using a core network transmitter.

Example 74 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for controlling a second server comprising receiving from a first server a request to transmit subscriber identity module installation data for installation of a second subscriber identity module to a second mobile radio communication device and transmitting the subscriber identity module installation data to the second mobile radio communication device.

In Example 75 the subject matter of Example 74 can optionally include that the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device.

In Example 76 the subject matter of any one of Examples 74 75 can optionally include that receiving the request comprises receiving the request using a core network receiver.

In Example 77 the subject matter of any one of Examples 74 76 can optionally include that transmitting the subscription data comprises transmitting the subscription data using a core network transmitter.

Example 78 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for controlling a server comprising receiving from a second mobile radio communication device a request for subscriber identity module installation data for installation of a second subscriber identity module wherein the second subscriber identity module is related to a first subscriber identity module that is installed in a first mobile radio communication device and transmitting the subscriber identity module installation data to the second mobile radio communication device.

In Example 79 the subject matter of Example 78 can optionally include that receiving the request comprises receiving the request using at least one of a cellular mobile radio communication receiver a WLAN receiver a receiver of an ethernet card a receiver of an interface card or a core network receiver.

In Example 80 the subject matter of any one of Examples 78 79 can optionally include that transmitting the subscription data comprises transmitting the subscription data using a core network transmitter.

Various aspects of this disclosure provide an architecture and solution of Virtual SIM vSIM for smart devices which aims to replace the current conventional UICC U SIM Card with a secure element. The secure element may be either embedded into the modem directly or in a dedicated secure engine such as an embedded UICC eUICC hosting the U SIM as part of the platform. The Virtual SIM may exhibit the same behavior and functionality as the current UICC just running the software version of the U SIM with minimal or no changes to the existing SIM modem interaction. It may provide interoperability between the U SIM and a cellular modem ME Mobile Equipment independently of the manufacturer card issuer or operator proving easy and fast acceptance and adoption of proposed system. It is to be noted that by hosting the SIM outside the UICC various aspects of this disclosure do not compromise the security aspects related to the SIM.

Various aspects of this disclosure provide a multiple persona management system via different mobile subscriptions to be hosted on the same secure element. This may allow downloading multiple subscriptions not only from the same MNO but also from different MNOs and also provides the management activation switching and deletion of the subscriptions on the Virtual SIM. Various aspects of this disclosure provide a solution of enabling secure isolated virtual containers to host multiple virtual SIMs on the same secure element hosted on the platform or the cellular modem.

Various aspects of this disclosure introduce a concept of combining the power of using other radio communication mechanisms like NFC services which may allow the smart devices to read and write a contactless card act like a contactless card and connect securely to other NFC enabled smart devices to exchange data along with the trusted secure element hosting the vSIM with a standardized generic interface e.g. Single Wire Protocol architecture. This allows the user to TAP and ACTIVATE or DOUBLE TAP and DEACTIVATE subscriptions on other smart devices equipped with the capability of embedded secure element hosting the Virtual SIM.

Various aspects of this disclosure provide an Ultra Mobility Server as new network element to manage the services and subscriptions related to a subscriber.

Various aspects of this disclosure may enhance user experience by providing a secure execution environment that stores the user s persona via his subscription information. Various aspects of this disclosure may provide ease of remote subscription management i.e. installation replacement and termination of subscriptions. Various aspects of this disclosure may provide once installed easy to use subscription management see example Tap and Activate .

This may allow the user to seamlessly choose connectivity to the world wide web and its digital data on the go anytime and anywhere.

Many smart devices today are equipped with Near Field Communication NFC technology. Also platforms are getting more secure with variants of Trusted Execution environment TEE being provisioned in them e.g. Trusted Platform Module ARM TrustZone etc. . Various aspects of this disclosure introduce the concept of combining the power of using NFC services which allows the smart devices to read and write a contactless card act like a contactless card and connect securely to other NFC enabled smart devices to exchange data along with the trusted secure element to provide a Single Wire Protocol SWP architecture hosted on the same Java Card.

In the following a use case scenario according to various aspects of this disclosure will be described.

A mobile network operator may provide the option for the subscriber to purchase a X GB mobile data plan with the option to connect up to Y connected devices. The key devices may be smartphones Ultrabooks and tablets. The user on purchase of a subscription from a store may use his smartphone with NFC capability or with an NFC card with integrated UICC functionality referenced as the primary device to first be loaded with a subscription from the plan and also be the identifier for the plan.

The smartphone or the NFC card may be equipped with the Trusted Execution Environment or Secure Chip that hosts the virtual SIM.

This primary device may also run the Tap App user application which may allow the user to get to know his plan details with a single click of the button. This primary device may be then used for activating subscriptions on other secondary devices described in the usage scenario below.

For example the primary device may be a smartphone for example with 3G LTE modem NFC card and TEE . For example the secondary device may be an Ultrabook for example with 3G LTE modem NFC card and TEE .

1. A user may receive a first subscription for his data plan on his smartphone by means of a single tap using a Master device with an NFC card at the telecom shop or he may already get the smartphone provisioned with the subscription at the store. If a Master device is used the sales person at the telecom shop may need to confirm the activation through the user interface of the Master device.

2. When the user wishes to activate a secondary device e.g. Ultrabook the User may tap the Ultrabook with the smartphone for NFC communication between the devices to activate a second subscription from his data plan.

3. The user may double tap the Ultrabook with the smartphone to remove a subscription. The user may need to confirm the removal through the user interface of the primary device.

4. Only the primary device or the Master device may be able to provide the confirmation for activating and removing subscriptions.

1. When the user taps the secondary device with the primary device the NFC applet of the primary device may signal a TAP event to the NFC applet of the secondary device.

3. The NFC applet of the secondary device may retrieve the ChipID of the UICC storing the SIM of the primary device the UserID of the primary device and a one time password OTP from the primary device. The user may need to confirm through the user interface of the primary device that it is allowed to provide an OTP. The UserID may be a unique identifier for the primary device. E.g. the UserID may be derived from the International Mobile Equipment Identity IMEI of the device.

4. The secondary device may authenticate itself towards the Ultra Mobility Server UMS by providing the UserID of the primary device and the OTP. Upon successful verification of the OTP provided for UserID the UMS may indicate to the secondary device that the authentication was successful.

5. The secondary device may send a request to the UMS to provide subscription data for installation of a subscriber identity module on the secondary device and to activate the subscription in the network. With the request the secondary device may send the UserID and the ChipID of the primary device and its own UserID and ChipID. UserID may be a unique identifier for the secondary device and ChipID may be the identity of the UICC of the secondary device on which the new SIM is to be installed.

The UMS may retrieve the subscriber data stored for UserID e.g. the maximum number of allowed subscriptions and the number of currently activated subscriptions and may check whether the user is allowed to perform the requested action in this case to download and activate another SIM.

6. If the number of subscriptions that are already active is smaller than the maximum number permitted by the user s data plan the UMS may send a request to the to the Subscription Management Server SubMan to provide subscription data for installation of a subscriber identity module on the secondary device and to activate the subscription in the network. The request may include the Pool ID the ChipID and the address Addr under which the SubMan can reach the secondary device for example an IP address. After successful completion of the requested actions the SubMan may send a confirmation to the UMS. The Pool ID may refer to a pool of subscriptions that have been reserved on the SubMan for the UMS and from which the requested subscription is selected. Dependent on the configuration the Pool ID may also be considered as a UMS identifier but generally a UMS may request subscriptions from more than one Pool ID on a SubMan and if more than one UMS is deployed several UMSs may request subscriptions from the same pool on the SubMan. The UMS may either extract the Addr in step 5 from the source address information of the HTTP request from the secondary device or alternatively the secondary device may send the Addr to the UMS as a separate parameter within the HTTP request.

7. The Subman may assign a new subscription for ChipID and Addr transmit the subscription data necessary to install the new subscription on the secondary device over the air OTA or over the internet to the secondary device and activate the subscription in the mobile network.

The user may tap the secondary device with the primary device and as a consequence the NFC applet of the primary device may signal a TAP event to the NFC applet of the secondary device.

The NFC applet of the primary device may retrieve in the ChipID from the eUICC of the primary device.

The NFC applet of the primary device may send in the ChipID and the UserID of the primary device to the NFC applet of the secondary device.

In the NFC applet of the secondary device may inform the TapApp an application running on the secondary device about the single tap event by sending a TAP NOTIFICATION message. The TapApp may determine from the type of event single tap that it needs to initiate a procedure to download a new subscription to the secondary device. Therefore in the TapApp may retrieve the UserID and ChipID from the NFC applet of the secondary device together with the UserID of the secondary device and the ChipID of the eUICC on which the new subscription is to be stored.

The TapApp may send a client request to the UMS . This client request may include an HTTP request to provide subscription data for installation of a subscriber identity module on the secondary device and to activate the subscription in the network. With the request the TapApp may send the UserID and the ChipID of the primary device and UserID and ChipID of the secondary device.

In the UMS may retrieve the subscriber data stored for UserID and check if the user is allowed to download and activate another SIM.

If the check is successful the UMS may send a request to the Subscription Management Server SubMan to provide subscription data for installation of a subscriber identity module on the secondary device and to activate the subscription in the network. The request may include the Pool ID of the pool from which the subscription is to be selected the ChipID and the address Addr under which the SubMan can reach the secondary device typically an IP address.

In the Subman may establish a secure connection over the air OTA or over the internet to the eUICC of the secondary device transmit the subscription data necessary to install the new subscription on the secondary device and activate the subscription in the mobile network.

In the UMS may record in the database entry for UserID that a subscription was downloaded and activated for UserID and ChipID.

The subscription management architecture may be provided as a SaaS Software as a Service solution hosted on a computing platform called Ultra Mobility Server . This architecture may provide connectivity interface via web services e.g. REST Representational State Transfer API Application Programming Interface for client webserver communication between Mobile Device and Ultra Mobility Server may provide mobile device management via generic methods API for subscription management and user account management may host smart brokering algorithms and intelligent billing operations and may provide REST APIs towards a Subscription Management Server for example operated by a UICC vendor on behalf of one or several operators for service activation and de activation.

The platform may also be equipped with a Near Field Communication NFC controller communicating with the trusted secure element via a standardized interface e.g. Single Wire Protocol .

A trusted secure element on the platform may provide the root of trust for hosting digital signatures security keys and subscription information. It may provide multiple secure containers hosting isolated SIM subscriptions thus enabling management of multiple SIM cards from different MNOs. It may run the security algorithms e.g. Milenage . It may also perform cryptographic operations providing security for accessing the data. Over the Air OTA may be used for provisioning personalization and activation of SIM cards in mobile devices.

According to various aspects of this disclosure NFC and a Tap App may be used. A smart user application may provide ease of management. The Tap App application which may be a host application for example Windows 8.1 Metro Application Android Application etc. may run on the clients for example on a smart device identified as secondary device . This host application may communicate securely with the Trusted Execution environment via the eSIM Host interface and with the NFC controller via the NFC Host App interface and may establish a secure connection with the Ultra Mobility Server using client server web APIs e.g. REST APIs .

According to various aspects of this disclosure application software hosted on smartphone operating systems embedded secure hardware hosting virtual SIM functionality along with the smart Java card applets and a middle man entity called Ultra Mobility Server may be provided.

The ease of subscription management like Tap and activate etc. may involve use of radio communication like NFC and a secure element hosting multiple SIMs. The devices and methods according to various aspects of this disclosure may allow only the primary device plan identifier to host multiple SIMs it s original one and a second one related to the X GB data plan.

The devices and methods according to various aspects of this disclosure may be used in or with 3GPP cellular modems.

The devices and methods according to various aspects of this disclosure may provide added revenue stream from MNO Mobile Network Operator commissions Content Providers ISVs independent software vendor Connectivity Service Providers Credit Card Providers etc.

The devices and methods according to various aspects of this disclosure may accelerate wireless WAN based platforms such as tablets smartphones and Ultrabooks to the market.

The devices and methods according to various aspects of this disclosure may provide a true Link Me Free Me user experience and Internet of things experience.

The devices and methods according to various aspects of this disclosure may reduce BOM bill of materials cost by leveraging trusted platform computing capabilities on smart devices e.g. by leveraging the Intel Manageability Engine Converged Security Engine capabilities to host SIM functionality .

While specific aspects have been described it should be understood by those skilled in the art that various changes in form and detail may be made therein without departing from the spirit and scope of the aspects of this disclosure as defined by the appended claims. The scope is thus indicated by the appended claims and all changes which come within the meaning and range of equivalency of the claims are therefore intended to be embraced.

