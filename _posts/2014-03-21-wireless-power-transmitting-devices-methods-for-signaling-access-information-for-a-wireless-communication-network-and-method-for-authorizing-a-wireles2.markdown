---

title: Wireless power transmitting devices, methods for signaling access information for a wireless communication network and method for authorizing a wireless power receiving device
abstract: A wireless power transmitting device is described comprising a power transmitter to wirelessly transmit power to a wireless power receiving device, a controller configured to control the wireless power transfer to the wireless power receiving device via a wireless power transfer control channel of a first wireless communication network between the wireless power transmitting device and the wireless power receiving device and a signaling circuit configured to signal access information for a second wireless communication network via the wireless power transfer control channel.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09615254&OS=09615254&RS=09615254
owner: INTEL CORPORATION
number: 09615254
owner_city: Santa Clara
owner_country: US
publication_date: 20140321
---
Embodiments described herein generally relate to wireless power transmitting devices methods for signaling access information for a wireless communication network and method for authorizing a wireless power receiving device.

With the wide usage of electronic mobile devices and the need to regularly charge these devices convenient opportunities to charge mobile devices are searched for. Wireless charging may allow a user to charge a mobile device without the need to bring his recharger. It can be expected that wireless power transfer stations will be more widely deployed in the future and may for example be used by restaurants hotels etc. to offer customers the opportunity to charge and or power on their mobile devices. Accordingly mechanisms and features of wireless power transmitting devices that make them more effective and convenient for their users and their operators are desirable.

The following detailed description refers to the accompanying drawings that show by way of illustration specific details and aspects of this disclosure in which the invention may be practiced. Other aspects may be utilized and structural logical and electrical changes may be made without departing from the scope of the invention. The various aspects of this disclosure are not necessarily mutually exclusive as some aspects of this disclosure can be combined with one or more other aspects of this disclosure to form new aspects.

Commercial establishments such as coffee shops bookstores and airports typically offer WiFi hotspots as a convenience. In order to recoup network costs and prevent non customers from accessing or abusing the WiFi network such hotspots typically utilize network access control which requires the user to acquire certain access information such as shared credentials. The access information e.g. keying material is typically refreshed daily by the respective network operator and thus is a burden for the network operator to administer and manage. Therefore some establishments have abandoned sharing daily credentials e.g. a username and a password with their customers. However many hotels continue to employ a daily multi day credential access scheme i.e. an access control scheme which requires users to acquire credentials for network access which are changed daily or once every couple of days by the operator.

Furthermore wireless power transfer is becoming more ubiquitous. PC laptops smartphones even backpacks are or can be expected to soon be shipping with wireless power transfer facilities. The power transferred by a wireless power transfer system can be used for operating devices without the need for power cord or can be used for charging battery in battery operating devices. A system consisting of a power transmitter and a power receiver and or a control mechanism in which the wireless power is used for charging batteries is referred to as wireless charging system. Standardization in the field of wireless power transfer is for example performed by the Alliance for Wireless Power A4WP the Power Matters Alliance and the Wireless Power Consortium. For example smartphones already exist which include a wireless charging mechanism compatible with the wireless power specification by the Wireless Power Consortium and restaurant chains start providing wireless charging according to the specification by the Power Matters Alliance and the specification by the Wireless Power Consortium respectively.

According to the wireless power transfer specifications above a digital communication channel is established between the mobile device typically a mobile communication device such as a communication terminal to receive the power and the power transmitter i.e. the wireless power transmitter e.g. in the form of a table or mat that might be referred to as charging table or charging mat specifies and controls parameters before and during wireless power transfer via the communication channel. According to the Wireless Power Consortium a backscatter modulation scheme is used for the communication via the digital communication channel in which the receiver i.e. the mobile device that is charged amplitude modulates the power signal sent by the power transmitter to provide a communications channel. According to the A4WP Bluetooth Low Energy BLE is used for the communication channel between the power transmitter also referred to as power transmitting unit PTU and the mobile device generally referred to as power receiving unit PRU . The architecture according to A4WP is described in the following as an example for a wireless power transfer arrangement.

The wireless power transfer arrangement includes a power receiving unit PRU e.g. a mobile device such as a laptop or a mobile phone and a power transmitting unit PTU e.g. a charging mat or a charging table.

The PRU includes a reception resonator for receiving power which it provides via a regulator and a DC DC converter to a client device load e.g. a battery that is to be charged. A PRU microprocessor may control the regulator and the DC DC converter in accordance with a charging control algorithm.

The PTU includes a transmission resonator for sending power which it receives from a power supply via a power amplifier and a matching circuit . A PTU microprocessor controls the power supply and the power amplifier in accordance with the charging control algorithm.

The PRU microprocessor and the PTU microprocessor communicate via a communication channel . In this example the PRU and the PTU operate the communication channel according to BLE at 2.4 GHz. The power transmission from the transmission resonator to the reception resonator is for example performed at 6.78 MHz.

In the following examples the architecture as illustrated in is used as an exemplary architecture. However all examples may also be used with other architectures including the architectures according to the Power Matters Consortium and the Wireless Power Consortium as well as any other wireless charging architecture.

1. An automatic distribution of access credentials such as WLAN credentials e.g. including username and password via a wireless power transfer or transmitting station or a wireless charging station i.e. the power transmitter e.g. the PTU and

2. An automatic authorization for use by a wireless power transfer station or a wireless charging station or facility also referred to as wireless power transmitting device in the following by usage of a network protocol which includes the mobile device getting a token from a trusted resource. For example a mobile device needs to be authorized prior to enabling full wireless charging by the wireless charging station i.e. the power transmitter. Thus receiving wireless power and or charging or at least full charging may be restricted to authorized users e.g. paying customers . A use case is for example that the owner of a hotel or another establishment wishes to monetize the wireless charging facilities per user or on a metered basis.

The wireless power transmitting device includes a power transmitter to wirelessly transmit power to a wireless power receiving device e.g. for charging or power on of a mobile device and a controller configured to control the power transmitted to the wireless power receiving device via a wireless power transfer control channel may refer to as control channel or wireless power control channel of a first wireless communication network between the wireless power transmitting device and the wireless power receiving device.

The wireless power transmitting device further includes a signaling circuit configured to signal access information for a second wireless communication network via the wireless power transfer control channel.

In other words access information for a communication network other than the wireless network used for transmitting the wireless power or the control information is transmitted via the communication channel which is used for transmitting the wireless power control information. For example in the exemplary architecture of the PTU uses the communication channel for transmission of access information for a wireless communication network which may for example be a WLAN i.e. WiFi network but which also may be a wide area cellular communication network such as according to UMTS LTE etc.

In the wireless power transmitting device controls a wireless power transfer from the wireless power transmitting device to a wireless power receiving device via a wireless power transfer control channel of a first wireless communication network between the wireless power transmitting device and the wireless power receiving device.

In the wireless power transmitting device signals access information for a second wireless communication network via the wireless power transfer control channel.

The wireless power transmitting device includes a power transmitter to wirelessly transmit power to a wireless power receiving device e.g. for charging and or power on of a mobile device and a controller configured to instruct the wireless power receiving device to adapt a parameter of the power reception from the power transmitter via a communication channel between the wireless power transmitting device and the wireless power receiving device.

The wireless power transmitting device further includes a detector configured to detect whether the wireless power receiving device interrupts power reception for the predetermined time and an authentication circuit configured to verify that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel based on whether the wireless power receiving device adapts the parameter of the power reception.

In other words a wireless power transmitting device checks whether a wireless power receiving device e.g. a mobile device to be charged e.g. placed on a charging mat or on a charging table is the right device i.e. a device authorized for charging and or receiving wireless power namely the one connected to the wireless power transmitting device by a communication channel which the wireless power transmitting device for example uses for controlling the wireless power transfer e.g. charging by instructing the mobile device to adapt power reception e.g. to pause power reception via the communication channel and checking whether the device changes the power reception in accordance with the instruction.

In the wireless power transmitting device wirelessly transmits power from a wireless power transmitting device to a wireless power receiving device.

In the wireless power transmitting device instructs the wireless power receiving device to adapt a parameter of the power reception from the wireless power transmitting device via a communication channel between the wireless power transmitting device and the wireless power receiving device.

In the wireless power transmitting device detects whether the wireless power receiving device adapts the parameter of the power reception.

In the wireless power transmitting device verifies that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel based on whether the wireless power receiving device adapts the parameter of the power reception.

The wireless power transmitting device includes a power transmitter to wirelessly transmit power to a wireless power receiving device e.g. for charging a mobile device .

The wireless power transmitting device further includes a controller configured to request the wireless power receiving device to provide an electronic token indicating that the wireless power receiving device has the right to receive power from the power transmitter to verify based on the reception of a valid token from the wireless power receiving device whether the wireless power receiving device has the right to receive power from the power transmitter and to control the power transmitter to transmit power to the wireless power receiving device based on whether the wireless power receiving device has the right to receive power from the power transmitter.

In other words a wireless power transmitting device requires a e.g. mobile device to be charged or which wishes or requests to be charged or receive wireless power to provide a token proving that the device has the right to be charged or receive wireless power by the wireless power transmitting device. The device may for example acquire the token from a trusted entity e.g. via the Internet.

In the wireless power transmitting device requests a wireless power receiving device to provide an electronic token indicating that the wireless power receiving device has the right to receive power from a power transmitter.

In the wireless power transmitting device verifies based on the reception of a valid token from the wireless power receiving device whether the wireless power receiving device has the right to receive power from the power transmitter.

In the wireless power transmitting device controls the power transmitter to wirelessly transmit power to the wireless power receiving device based on whether the wireless power receiving device has the right to receive power from the power transmitter.

It should be noted that further devices according to the wireless power transmitting devices and methods described above may be provided.

For example according to the wireless power transmitting device a device is provided including a power receiver configured to wirelessly receive power from a wireless power transmitting device for charging the device and a first receiver configured to receive control information for the charging of the device via a control channel may also referred to as wireless power transfer control channel or charging control channel of a first wireless communication network between the wireless power transmitting device and the device.

The device further includes a second receiver configured to receive access information for a second wireless communication network via the charging control channel.

Further according to the wireless power transmitting device a device is provided including a power receiver configured to wirelessly receive power from a wireless power transmitting device e.g. for charging and or power on of the mobile device a receiver configured to receive an instruction to adapt a parameter of the power reception from the wireless power transmitting device via a communication channel between the wireless power transmitting device and the device and a controller configured to adapt the parameter of the power reception in response to the instruction.

Further according to the wireless power transmitting device a device is provided including a power receiver configured to wirelessly receive power from a wireless power transmitting device e.g. for charging the device a receiver configured to receive a request to provide an electronic token indicating that the device has the right to receive power from the wireless power transmitting device and a transmitter configured to provide an electronic token indicating that the device has the right to receive power from the wireless power transmitting device to the wireless power transmitting device.

In Example 2 the subject matter of Example 1 can optionally include the first wireless communication network being different from the second wireless communication network.

In Example 3 the subject matter of any one of Examples 1 2 can optionally include the first wireless communication network and the second wireless communication network using different radio access technologies.

In Example 4 the subject matter of any one of Examples 1 3 can optionally include the wireless power transmitting device comprising an authentication circuit configured to authenticate the wireless power receiving device and the signaling circuit being configured to signal the access information based on whether the authentication circuit has authenticated the wireless power receiving device.

In Example 5 the subject matter of any one of Examples 1 4 can optionally include the wireless power transmitting device comprising an authentication circuit configured to authenticate the wireless power receiving device and the power transmitter being configured to wirelessly transmit power to the wireless power receiving device based on whether the authentication circuit has authenticated the wireless power receiving device.

In Example 6 the subject matter of Example 5 can optionally include the authentication circuit being configured to authenticate the wireless power receiving device by verifying that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the wireless power transfer control channel.

In Example 7 the subject matter of any one of Examples 1 6 can optionally include the power transmitter being configured to wirelessly transmit power to the wireless power receiving device using a power signal and the wireless power transfer control channel being a channel based on a modulation of the power signal.

In Example 8 the subject matter of any one of Examples 1 7 can optionally include the wireless power transfer control channel operating in a different radio frequency band than the frequency band used by the power transmitter to transmit power.

In Example 9 the subject matter of any one of Examples 1 8 can optionally include the first wireless communication network being a Bluetooth communication network and the wireless power transfer control channel being a Bluetooth channel.

In Example 10 the subject matter of any one of Examples 1 9 can optionally include the second wireless communication network being a wireless local area network or a cellular mobile telephone communication network.

In Example 11 the subject matter of any one of Examples 1 10 can optionally include the access information including credentials for the wireless communication network.

In Example 12 the subject matter of any one of Examples 1 11 can optionally include the wireless power transmitting device comprising a receiver configured to receive the access information from a further communication device.

In Example 13 the subject matter of any one of Examples 1 12 can optionally include the further communication device being an Internet server.

In Example 15 the subject matter of Example 14 can optionally include the first wireless communication network being different from the second wireless communication network.

In Example 16 the subject matter of any one of Examples 14 15 can optionally include the first wireless communication network and the second wireless communication network using different radio access technologies.

In Example 17 the subject matter of any one of Examples 14 16 can optionally include authenticating the wireless power receiving device and signaling the access information based on a successful authentication of the wireless power receiving device.

In Example 18 the subject matter of any one of Examples 14 17 can optionally include authenticating the wireless power receiving device and wirelessly transmitting power to the wireless power receiving device based on a successful authentication of the wireless power receiving device.

In Example 19 the subject matter of Example 18 can optionally include authenticating the wireless power receiving device by verifying that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the wireless power transfer control channel.

In Example 20 the subject matter of any one of Examples 14 19 can optionally include wirelessly transmitting power to the wireless power receiving device using a power signal wherein the wireless power transfer control channel is a channel based on a modulation of the power signal.

In Example 21 the subject matter of any one of Examples 14 20 can optionally include the wireless power transfer control channel operating in a different radio frequency band than the frequency band used by the power transmitter to transmit power.

In Example 22 the subject matter of any one of Examples 14 21 can optionally include the first wireless communication network being a Bluetooth communication network and the wireless power transfer control channel being a Bluetooth channel.

In Example 23 the subject matter of any one of Examples 14 22 can optionally include the second wireless communication network being a wireless local area network or a cellular mobile telephone communication network.

In Example 24 the subject matter of any one of Examples 14 23 can optionally include the access information including credentials for the wireless communication network.

In Example 25 the subject matter of any one of Examples 14 24 can optionally include receiving the access information from a further communication device.

In Example 26 the subject matter of any one of Examples 14 25 can optionally include the further communication device being an Internet server.

Example 27 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for performing radio communication according to any one of Examples 14 to 26.

Example 28 is a wireless power transmitting device comprising a power transmitting means for wirelessly transmitting power to a wireless power receiving device a controlling means for controlling the wireless power transfer to the wireless power receiving device via a wireless power transfer control channel of a first wireless communication network between the wireless power transmitting device and the wireless power receiving device and a signaling means for signaling access information for a second wireless communication network via the wireless power transfer control channel.

In Example 29 the subject matter of Example 28 can optionally include the first wireless communication network being different from the second wireless communication network.

In Example 30 the subject matter of any one of Examples 28 29 can optionally include the first wireless communication network and the second wireless communication network using different radio access technologies.

In Example 31 the subject matter of any one of Examples 28 30 can optionally include the wireless power transmitting device comprising an authentication means for authenticating the wireless power receiving device and the signaling means being for signaling the access information based on whether the authentication circuit has authenticated the wireless power receiving device.

In Example 32 the subject matter of any one of Examples 28 31 can optionally include the wireless power transmitting device comprising an authentication means for authenticating the wireless power receiving device and the power transmitting means being for wirelessly transmitting power to the wireless power receiving device based on whether the authentication circuit has authenticated the wireless power receiving device.

In Example 33 the subject matter of Examples 32 can optionally include the authentication means being for authenticating the wireless power receiving device by verifying that the wireless power receiving device to which the power transmitting transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the wireless power transfer control channel.

In Example 34 the subject matter of any one of Examples 28 33 can optionally include the power transmitting means being for wirelessly transmitting power to the wireless power receiving device using a power signal and the wireless power transfer control channel being a channel based on a modulation of the power signal.

In Example 35 the subject matter of any one of Examples 28 34 can optionally include the wireless power transfer control channel operating in a different radio frequency band than the frequency band used by the power transmitter to transmit power.

In Example 36 the subject matter of any one of Examples 28 35 can optionally include the first wireless communication network being a Bluetooth communication network and the wireless power transfer control channel being a Bluetooth channel.

In Example 37 the subject matter of any one of Examples 28 36 can optionally include the second wireless communication network being a wireless local area network or a cellular mobile telephone communication network.

In Example 38 the subject matter of any one of Examples 28 37 can optionally include the access information including credentials for the wireless communication network.

In Example 39 the subject matter of any one of Examples 28 38 can optionally include the wireless power transmitting device comprising a receiving means for receiving the access information from a further communication device.

In Example 40 the subject matter of any one of Examples 28 39 can optionally include the further communication device being an Internet server.

In Example 42 the subject matter of Examples 41 can optionally include the controller being configured to instruct the wireless power receiving device to interrupt the power reception from the power transmitter.

In Example 43 the subject matter of any one of Examples 41 42 can optionally include the controller being configured to instruct the wireless power receiving device to adapt the parameter of the power reception for a predetermined time and the authentication circuit being configured to verify that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel based on whether the wireless power receiving device adapts the parameter of the power reception for the predetermined time.

In Example 44 the subject matter of Examples 43 can optionally include the controller being configured to randomly determine the predetermined time.

In Example 45 the subject matter of any one of Examples 41 44 can optionally further include a signaling circuit configured to signal access information for a wireless communication network to the wireless power receiving device based on whether the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel.

In Example 46 the subject matter of Example 45 can optionally include the wireless communication network being a wireless local area network or a cellular mobile telephone communication network.

In Example 47 the subject matter of any one of Examples 45 46 can optionally include the access information including credentials for the wireless communication network.

In Example 48 the subject matter of any one of Examples 45 47 can optionally include the wireless power transfer control channel being a channel of a further wireless communication network different from the wireless communication network.

In Example 50 the subject matter of Examples 49 can optionally include instructing the wireless power receiving device to interrupt the power reception from the power transmitter.

In Example 51 the subject matter of any one of Examples 49 50 can optionally include instructing the wireless power receiving device to adapt the parameter of the power reception for a predetermined time and verifying that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel based on whether the wireless power receiving device adapts the parameter of the power reception for the predetermined time.

In Example 52 the subject matter of Examples 51 can optionally include randomly determining the predetermined time.

In Example 53 the subject matter of any one of Examples 49 52 can optionally include signaling access information for a wireless communication network to the wireless power receiving device based on whether the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel.

In Example 54 the subject matter of any one of Examples 53 can optionally include the wireless communication network being a wireless local area network or a cellular mobile telephone communication network.

In Example 55 the subject matter of any one of Examples 53 54 can optionally include the access information including credentials for the wireless communication network.

In Example 56 the subject matter of any one of Examples 53 55 can optionally include the wireless power transfer control channel being a channel of a further wireless communication network different from the wireless communication network.

Example 57 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for performing radio communication according to any one of Examples 49 to 55.

Example 58 is a wireless power transmitting device comprising a power transmitting means for wirelessly transmitting power to a wireless power receiving device a controlling means for instructing the wireless power receiving device to adapt a parameter of the power reception from the power transmitting means via a communication channel between the wireless power transmitting device and the wireless power receiving device a detecting means for detecting whether the wireless power receiving device adapts the parameter of the power reception an authentication means for verifying that the wireless power receiving device to which the power transmitting transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel based on whether the wireless power receiving device adapts the parameter of the power reception.

In Example 59 the subject matter of Examples 58 can optionally include the controlling means being for instructing the wireless power receiving device to interrupt the power reception from the power transmitter.

In Example 60 the subject matter of any one of Examples 58 59 can optionally include the controlling means being for instructing the wireless power receiving device to adapt the parameter of the power reception for a predetermined time and the authentication means being for verifying that the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel based on whether the wireless power receiving device adapts the parameter of the power reception for the predetermined time.

In Example 61 the subject matter of one of Examples 60 can optionally include the controlling means being for randomly determining the predetermined time.

In Example 62 the subject matter of Example 61 can optionally further include a signaling means for signaling access information for a wireless communication network to the wireless power receiving device based on whether the wireless power receiving device to which the power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by the communication channel.

In Example 63 the subject matter of Example 62 can optionally include the wireless communication network being a wireless local area network or a cellular mobile telephone communication network.

In Example 64 the subject matter of any one of Examples 62 63 can optionally include the access information including credentials for the wireless communication network.

In Example 65 the subject matter of any one of Examples 62 64 can optionally include the wireless power transfer control channel being a channel of a further wireless communication network different from the wireless communication network.

In Example 67 the subject matter of Examples 66 can optionally include the controller being configured to determine whether a token received from the wireless power receiving device is valid.

In Example 68 the subject matter of Example 67 can optionally include the controller being configured to determine whether a token received from the wireless power receiving device is valid based on a signature of the electronic token.

In Example 69 the subject matter of any one of Examples 66 68 can optionally include the controller being configured to request the wireless power receiving device to provide an electronic token indicating that the wireless power receiving device has the right to be fully charged by the power transmitter to verify based on the reception of a valid token from the wireless power receiving device whether the wireless power receiving device has the right to be fully charged by the power transmitter and to control the power transmitter to fully charge the wireless power receiving device based on whether the wireless power receiving device has the right to be fully charged by the power transmitter.

In Example 70 the subject matter of any one of Examples 66 69 can optionally include the controller being configured to request the wireless power receiving device to provide the electronic token by transmitting a request message to the wireless power receiving device indicating that the wireless power receiving device is to provide the electronic token.

In Example 71 the subject matter of Example 70 can optionally include the message including at least one of the address of a communication device providing the electronic token a serial number of the wireless power transmitting device a URI of a web service providing the electronic token and a nonce.

In Example 72 the subject matter of Example 71 can optionally include the communication device being an Internet server.

In Example 73 the subject matter of Example 72 can optionally include the communication device being a web server.

In Example 74 the subject matter of any one of Examples 66 73 can optionally include the controller being configured to determine an amount of charge from the electronic token which the wireless power receiving device has the right to receive and to control the power transmitter to transmit the amount of charge to the wireless power receiving device.

Example 75 is a method for authorizing a wireless power receiving device as described with reference to .

In Example 76 the subject matter of Example 75 can optionally include determining whether a token received from the wireless power receiving device is valid.

In Example 77 the subject matter of Example 76 can optionally include determining whether a token received from the wireless power receiving device is valid based on a signature of the electronic token.

In Example 78 the subject matter of any one of Examples 75 77 can optionally include requesting the wireless power receiving device to provide an electronic token indicating that the wireless power receiving device has the right to be fully charged by the power transmitter verifying based on the reception of a valid token from the wireless power receiving device whether the wireless power receiving device has the right to be fully charged by the power transmitter and controlling the power transmitter to fully charge the wireless power receiving device based on whether the wireless power receiving device has the right to be fully charged by the power transmitter.

In Example 79 the subject matter of any one of Examples 75 78 can optionally include requesting the wireless power receiving device to provide the electronic token by transmitting a request message to the wireless power receiving device indicating that the wireless power receiving device is to provide the electronic token.

In Example 80 the subject matter of Example 80 can optionally include the message including at least one of the address of a communication device providing the electronic token a serial number of the wireless power transmitting device a URI of a web service providing the electronic token and a nonce.

In Example 81 the subject matter of Example 80 can optionally include the communication device being an Internet server.

In Example 82 the subject matter of Examples 81 can optionally include the communication device being a web server.

In Example 83 the subject matter of any one of Examples 75 82 can optionally include determining an amount of charge from the electronic token which the wireless power receiving device has the right to receive and controlling the power transmitter to transmit the amount of charge to the wireless power receiving device.

Example 84 is a computer readable medium having recorded instructions thereon which when executed by a processor make the processor perform a method for performing radio communication according to any one of Examples 75 83.

Example 85 is a wireless power transmitting device comprising a power transmitting means for wirelessly transmitting power to a wireless power receiving device a controlling means for requesting the wireless power receiving device to provide an electronic token indicating that the wireless power receiving device has the right to receive power from the power transmitter verifying based on the reception of a valid token from the wireless power receiving device whether the wireless power receiving device has the right to receive power from the power transmitting means and controlling the power transmitting means to transmit power to the wireless power receiving device based on whether the wireless power receiving device has the right to receive power from the power transmitting means.

In Example 86 the subject matter of Example 85 can optionally include the controlling means is for determining whether a token received from the wireless power receiving device is valid.

In Example 87 the subject matter of Example 86 can optionally include the controlling means is for determining whether a token received from the wireless power receiving device is valid based on a signature of the electronic token.

In Example 88 the subject matter of any one of Examples 85 87 can optionally include the controlling means being for requesting the wireless power receiving device to provide an electronic token indicating that the wireless power receiving device has the right to be fully charged by the power transmitting means for verifying based on the reception of a valid token from the wireless power receiving device whether the wireless power receiving device has the right to be fully charged by the power transmitting means and for controlling the power transmitter to fully charge the wireless power receiving device based on whether the wireless power receiving device has the right to be fully charged by the power transmitting means.

In Example 89 the subject matter of any one of Examples 85 88 can optionally include the controlling means is for requesting the wireless power receiving device to provide the electronic token by transmitting a request message to the wireless power receiving device indicating that the wireless power receiving device is to provide the electronic token.

In Example 90 the subject matter of Example 89 can optionally include the message including at least one of the address of a communication device providing the electronic token a serial number of the wireless power transmitting device a URI of a web service providing the electronic token and a nonce.

In Example 91 the subject matter of Example 90 can optionally include the communication device being an Internet server.

In Example 92 the subject matter of Example 91 can optionally include the communication device being a web server.

In Example 93 the subject matter of any one of Examples 85 92 can optionally include the controlling means being for determining an amount of charge from the electronic token which the wireless power receiving device has the right to receive and control the power transmitting means to transmit the amount of charge to the wireless power receiving device.

It should be noted that one or more of the features of any of the examples above may be combined with any one of the other examples.

In the following examples are described in more detail. As mentioned above in the following examples the architecture illustrated in is used as a basis but any other wireless charging architecture may be used alternatively.

In the following examples a wireless power transmitting device uses a communication between the wireless power transmitter i.e. the wireless power transmitting device and the wireless power receiver e.g. a mobile device to be charged to provision credentials to the mobile receiver device for a Wi Fi access.

For example the wireless power transmitting device i.e. the PTU initially transfers a small amount of power i.e. a power beacon to the PRU to power up the PRU setup the communication channel and identify and establish operating parameters before power is transferred to complete a full charge of the battery of the PRU . During this process the PTU may use the communication channel to securely deliver WiFi credentials. This may for example eliminate the need to manually distribute WLAN credentials to legitimate customers. Namely instead charging stations push the credentials e.g. charging tables and charging mats to the customers mobile devices. Mobile devices that are known to be physically present in a location e.g. a store or restaurant since they have been charged or receiving wireless power in the location can now e.g. automatically connect to a WiFi network provided in the location. The wireless power transmitting devices may or may not be directly connected to the local WLAN network. However they are in any case provided with a mechanism to store and update the WLAN credentials.

Further in the following examples a wireless power transmitting device e.g. a wireless charging transmitter uses a network protocol to authenticate a wireless power receiver device before allowing full rate power transfer or before completing a full or partial charge of the receiver e.g. the receiver s battery.

For example if the owner of a commercial establishment e.g. a restaurant airport or hotel wants to be paid for use of wireless power transfer stations and the consumed electricity or wants to simply restrict access to paying customers then he she may require the wireless power transmitting devices e.g. charging mats to authorize mobile devices before charging them or transferring wireless power to them. For example a wireless power transmitting device uses a mechanism to authenticate and authorize devices via a cloud based protocol and cloud service as described below. The need to securely deliver WLAN credentials to the wireless power transmitting device may be a prerequisite to access the cloud service for authentication authorization for payment of a charging session.

An exemplary use case is the access to a hotel s WLAN and payment for wireless power transfer services that are provided in the hotel. This is illustrated in .

For example a hotel customer arrives with a mobile device that supports wireless power transfer checks in and picks up his room key or key fob. The customer walks into his room and lays his mobile device e.g. a laptop with wireless power reception capability or a mobile phone e.g. corresponding to PRU on a charging desk e.g. corresponding to PTU . The desk and the mobile device exchange power transfer information and exchange Wi Fi credentials via a communication channel e.g. corresponding to communication channel . The mobile device can now access the hotel s WiFi network provided by access points without the customer having to manually enter the credentials.

In this use case the credentials traverse from the hotel s WiFi network through the wireless power transfer station over the wireless power transfer communication channel and to the mobile device . The mobile device then uses it to gain access to the wireless WiFi network.

Owners of commercial establishments may prefer to be financially compensated i.e. to charge customers for using wireless power transfer facilities. In the example of to achieve this the hotel s wireless power transfer station may check for authorization from a trusted network service before it starts charging and or receiving wireless power. The customer user may for example be required to go to a third party web site and enter a credit card number or proof of purchase in exchange for a certain amount of charge and or wireless power the amount can be measured by the amount of energy amount of power or the duration of receiving wireless power .

Alternatively the customer may be required to browse to the hotel s web site and acknowledge that wireless power transfer fees will be added to his room charges. Once the user has accepted the agreement the wireless power transmitting device commences wireless power transfer or continues full charging and or full rate power transfer of the mobile device .

As explained above with reference to according to A4WP a communication channel based on Bluetooth Low Energy BLE is used as communications channel between the Power Receiving Unit and the Power Transmitting Unit . The BLE architecture classifies devices into Clients and Servers where Servers expose Services and Attributes and Clients use those Attributes. Attributes are simply logical state variables on the Server with permissions and security requirements that can be read and or potentially written by the Client. Servers can notify Clients when the logical value changes. Attributes have UUIDs universally unique identifiers that are either standardized by the Bluetooth SIG special interest group or created by the device manufacturer to customize and extend functionality. According to A4WP the PTU is the Client and the PRU is the Server.

The wireless power transfer arrangement includes a power receiving unit corresponding to PRU and a power transmitting unit corresponding to PTU .

The PRU only advertises itself in over BLE i.e. via the communication channel after detecting the power pulse over its Rx Resonator from the PTU .

In after receiving the PRU s advertisement the PTU connects to the PRU and in the PTU requests to read the PRU s static and dynamic attributes. In PRU issues notifications to the PTU such as about overcurrent overvoltage or overtemperature.

The PRU for example has the ability to provide a list of all primary services such as GAP Generic Access Profile Service GATT Generic Attribute Profile Service and the A4WP charging service .

In this example the PRU and the PTU further support the ability to push WiFi credentials from the PTU to the PRU . For this in this example two additional BLE device services a storage service on the PTU to manage and store WLAN pass phrases in other words WiFi credentials and a WLAN pass phrase service on the PRU to receive the WLAN pass phrases from a WLAN pass phrase push client of the PTU after it connects during a power charging session.

The PTU acts as a BLE Client Credential Push in that when it discovers the WLAN pass phrase service in the PRU the PTU in writes the current WLAN credentials to the appropriate attribute and thus pushes the WLAN credentials to the PRU .

The PRU can then in turn push the WLAN credentials to its the device s WLAN stack i.e. provided by its operating system s native WiFi software and connect to the for example hotel s WLAN according to IEEE 802.11.

While this is described in context of A4WP a similar approach may be used in the context of other wireless power standards.

A mechanism may be provided to avoid man in the middle attacks between the PTU and the PRU when exchanging WLAN credentials. For example Wireless Power Transfer may support authentication and or encryption of the communication channel for controlling the power transfer e.g. communication channel .

According to A4PW the PTU accepts PRU BLE connections without authentication and without encryption. However if bonding has occurred in the past authentication and encryption then the PTU and the PRU reconnect securely. In the case of an unsecure connection the WLAN credentials are transferred in the open over the communication channel . If this poses a security issue the PTU may be configured to not send the WLAN credentials until the user e.g. customer pairs the PRU and the PTU via a PIN or password. However even on an authenticated and or encrypted link the PTU may need to ensure that the mobile device which is going to be charged e.g. which is placed on the wireless power transmitting device e.g. charging mat for charging is the same as the mobile device connected to the PTU via the communication channel rather than a rogue device.

Therefore in this example before the PTU pushes the WLAN credentials to the PRU the PTU requests the PRU to suspend charging for a random number of milliseconds e.g. 100 to 2000 . If the PRU complies this can be detected by the PTU and provides confirmation to the PTU that the device getting the WLAN credential is the device that is actually connected to the PTU for charging.

The PTU may have the ability to store the WLAN credentials locally i.e. in a memory of the wireless power transmitting device and or receive and forward them from another communication device e.g. a proxy to provide the storage service e.g. a WLAN Proxy Storage Service BLE service .

For example an employee of the hotel uses a mobile phone containing the daily credentials and walks to wireless power transfer station also referred to as charging station of the hotel pairs the mobile phone and the wireless power transfer station and stores the credentials in the charging station . In this case for example the PTU corresponding to the charging station acts as a BLE Server it advertises the storage service connects to the mobile phone which is acting as a BLE Client and allows the mobile phone to update the Attributes containing the credentials. BLE Security can be employed here to only allow pre paired or authenticated devices such as the mobile phone to update the Attributes of the Storage Service.

The communication arrangement includes the Internet a Bluetooth Gateway i.e. a Bluetooth enable gateway and a power transmitting unit for example corresponding to the PTU .

The PTU provides a credential storage service corresponding to storage service that is connected to the Internet e.g. to a cloud service. For example the PTU can connect by means of a Bluetooth connection to the Bluetooth gateway and onto the Internet e.g. over IPv6. The PTU may additionally be configured with an HTTP RESTful stack and use one or more cloud services to populate the WLAN credentials.

The PTU may retrieve or receive WLAN credentials either over the Internet e.g. by pulling them from the Internet. Alternatively as described above the PTU may receive the WLAN credentials via a local provisioning step e.g. from another communication device e.g. a mobile phone as in the example above which pushes the credentials onto the PTU locally e.g. using Bluetooth.

The wireless power transfer arrangement may further provide the ability to control access to the charging unit i.e. to PTU in other words to control whether a mobile device is charged. For example it supports metering access to the PTU i.e. to the charging service and thus addresses the business need of authenticating a user s PRU e.g. the mobile device of customer and billing that user for the wireless charging service.

For this the PTU for example only enables wireless power transfer and or charging after it has received an electronic digital token from a trusted third party for instance a trusted cloud based service.

The communication arrangement includes a power receiving unit for example corresponding to PRU a power transmitting unit for example corresponding to PTU and a web service provided by a web server located in the Internet .

The PTU contains a Universal Resource Identifier URI pointing to the web service its unique serial number GUID and a certificate chain to validate responses from the web service i.e. from the web server providing the web service . The PRU for example contains an application or background process to connect with a web browser e.g. via browser plug in installed on the PRU . The browser may display web pages for interaction with the user of the PRU and communicate with the web service. The web server contains user accounts PTU information and implements the payment system.

For the following example it is assumed that the PTU and the PRU have established a communication channel e.g. corresponding to communication channel and have set up and or negotiated power parameters i.e. parameters for the wireless power transfer and or charging such as charging power charging frequency etc. The PRU for example estimates the amount of charging time or electrical charge needed to complete a full charge. The PRU is also assumed to have Internet access e.g. based on a WLAN and the WLAN credentials received from the PTU as described in the above examples.

In the following an example for a process flow for charging authentication by means of a token is given.

In the PTU transmits a token request in the form of a RequestChargingAuthorization message with the URI GUID and a randomly generated Nonce to the PRU .

In the PRU application either launches the PRU s web browser or connects directly to Web Service per the URI .

In the PRU application or the web browser as the case may be sends the RequestChargingAuthorization with GUID Nonce and estimated time and energy to fully charge the PRU s battery to the Web Service .

In the PRU requests the user for an authentication via the web browser or via the application . The user logs into an existing user account e.g. using web browser provide a payment e.g. via a credit card provide a PIN e.g. a code given to him during the hotel check in for example or accept other billing terms e.g. accept that the cost will be billed to his room . The user may also have the opportunity to select the amount of charging he wishes to pay for e.g. as a percentage of total battery charge .

In if the user authentication is validated the Web Server generates a token denoted as ChargingResponseToken in this example including information for the PTU signs it for integrity protection and returns it to the PRU . The information in the token includes a token identifier the PTU serial number the amount of charge authorized the nonce generated in the token request the signature and a certificate chain allowing signature verification.

In if the application has contacted the web service via the web browser the web browser sends the token to the application .

In the PTU checks whether the signature of the token is valid and signed by a designated signature chain and that the nonce matches the one sent in the token request.

In if the signature is valid the PTU commences wireless power transfer and or charging or continues for the amount time or energy specified in the token.

The PTU may for example validate the signature of the token using a local certificate chain and thus does not need to have a network connection. However if a network connection is available the PRU may use it for validating certificate authenticity or detecting certification revocation.

If the PTU was not able to validate the PRU since the PRU has not provided a valid token the PTU can for example reject PRU by one or a combination of

1. Not enabling the PRU to charge by means of PRU control characteristics such as setting a bit in an Enable PRU Output field to zero 

2 Not enabling the PRU to charge through PRU control characteristics by setting a bit in an Enable PRU Charge Indicator bit field to zero 

3 Not permitting the PRU to charge by setting a bit in a Permission field to a value that is reserved for denying permission due to authentication causes or without any reason.

The PTU may also choose to only accept the charging response token via the communication channel if it has been validated that the communication channel is connected to the mobile device which is going to be charged e.g. which is placed on the wireless power transmitting device e.g. charging mat for charging. The PTU may do this by requesting the PRU suspend charging for a random amount of time as described previously.

As described above the power transmitting device may verify that a wireless power receiving device to which its power transmitter transmits power is the same as the wireless power receiving device connected to the wireless power transmitting device by a communication channel based on whether the wireless power receiving device adapts the parameter of the power reception e.g. based on whether it interrupts power reception according to an instruction.

In the wireless power receiving device wirelessly receives power from a wireless power transmitting device.

In the wireless power receiving device receives an instruction to adapt a parameter of the power reception from the wireless power transmitting device via a communication channel between the wireless power transmitting device and the device.

In the wireless power receiving device adapts the parameter of the power reception in response to the instruction.

While specific aspects have been described it should be understood by those skilled in the art that various changes in form and detail may be made therein without departing from the spirit and scope of the aspects of this disclosure as defined by the appended claims. The scope is thus indicated by the appended claims and all changes which come within the meaning and range of equivalency of the claims are therefore intended to be embraced.

