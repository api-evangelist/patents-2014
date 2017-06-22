---

title: Method and technical equipment for short range data transmission
abstract: The invention relates to a method and a technical equipment for short range data transmission, e.g. Bluetooth low energy. The method comprises receiving, as a response to a transmitted advertisement packet, a scan request from a scanning device; reporting the scan request from a link layer to an application layer; determining a following action according to the scan request and performing the determined action.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09332376&OS=09332376&RS=09332376
owner: Silicon Laboratories Finland Oy
number: 09332376
owner_city: 
owner_country: FI
publication_date: 20140415
---
This application claims priority under 35 USC 119 to Finnish Patent Application No. 20135446 filed on Apr. 30 2013 which application is hereby incorporated by reference in its entirety.

The present application relates to Bluetooth modules. In particular the present application relates to Bluetooth low energy.

Bluetooth Low Energy BLE relates to Bluetooth wireless radio technology. It has been designed for low power and low latency applications for wireless devices within short range. Today typical BLE applications can be found from healthcare fitness security smart energy industrial automation and home entertainment. However BLE is not limited only those but increasingly more new applications utilizing BLE technology are designed.

The difference between BLE and classic Bluetooth is that the BLE devices consume remarkably less power for communication than classic Bluetooth devices. In addition the BLE is able to start the data transmission much quicker than the classic Bluetooth. This makes it possible to have BLE devices constantly on and to communicate intermittently with other devices.

The present application discloses a method and technical equipment implementing the method to improve the state of art by reducing over the air traffic between devices.

According to a first aspect a method comprises receiving as a response to a transmitted advertisement packet a scan request from a scanning device reporting the scan request from a link layer to an application layer and determining a following action according to the scan request and performing the determined action.

According to a second aspect an apparatus comprises a processor and a non transitory memory including computer program code wherein the memory and the computer program code are configured to perform with the processor cause the apparatus at least to receive as a response to a transmitted advertisement packet a scan request from a scanning device to report the scan request from a link layer to an application layer and to determine a following action according to the scan request and to perform the determined action.

According to a third aspect a system comprises at least one advertising device and at least one scanning device wherein said at least one advertising device is configured to receive as a response to a transmitted advertisement packet a scan request from said at least one scanning device to report the scan request from a link layer to an application layer and to determine a following action according to the scan request and to perform the determined action.

According to a fourth aspect a computer program product embodied on a computer readable medium comprises computer program code configured to when executed on at least one processor cause an apparatus or a system to receive as a response to a transmitted advertisement packet a scan request from a scanning device to report the scan request from a link layer to an application layer and to determine a following action according to the scan request and to perform the determined action.

According to an embodiment the following action is to modify a scan response packet to be sent to the scanning device.

According to an embodiment the following action is to modify an advertisement packet to be transmitted.

According to an embodiment the following action is to select a certain scan response to be transmitted from a group of different scan response packets which selection is based on the scan request.

According to an embodiment the scan response packet contains data on the address of a target device for the scan request packet and information on the services the target device for the scan request packet is able to provide.

According to an embodiment the apparatus performing the method is a Bluetooth low energy enabled device.

The link layer provides ultra low power idle mode operation and device discovery i.e. connection mode and advertising mode handling . The link layer also is in charge for packet transmission and responding.

In BLE technology one or more slave devices can be connected to a master device. The master is able to communicate with one or more slave devices also simultaneously. To let the master know about the slave devices the slave devices or at that point advertisers periodically at pseudo random intervals pass advertisements packets which a scanner device i.e. scanner is scanning.

When an advertising device receives SCAN REQ from a scanning device the advertising device may give more information to the scanning device by SCAN RSP packet. SCAN RSP packet may contain information on the name of the advertising device and on the services the advertising device is able to provide. However SCAN RSP packet is not limited to carry only this information but may contain other data as well or instead.

CONNECT REQ packet contains data on transmit window size defining timing window for first data packet transmit window offset that is off when the transmit window starts connection interval is the time between connection events slave latency defines number of times the slave can ignore connection events from the master connection timeout is maximum time between two correctly received packets in the connection before link is considered to be lost hop sequence is a random number appointing the starting point for a hop channel map CRC initialization value.

When the scanner is connected to an advertiser the advertiser is called a slave and the scanner is called a master . The state for passing advertisements packets is called advertising state and the state for connection is called connected state . In both states data transfer occurs. Slave device may be a sensor or an actuator such as a temperature sensor heart rate sensor light bulb proximity sensor etc. Master device can be any electronic device capable of collecting data e.g. mobile phone smart phone personal digital assistant personal computer laptop computer tablet computer etc.

Packets sent from a slave device in advertising mode contains approximately 27 bytes of data and a slave address. Packets from master device in advertisement channel contains only a master address.

When an advertisement packet is successfully received by the master device the master device can send a SCAN REQ packet to the slave device. This SCAN REQ packet indicates that the master device has received the advertisement data successfully. The SCAN REQ packet is transmitted from the master device to the slave device in order to request more data.

Connection between the master device and the slave device can be formed by the master device sending CONNECT REQ packet after the slave advertisement packet. When the connection is opened the slave device becomes aware with which device the connection is formed.

However before the connection is formed there is no indication to the slave device that the master device has received any advertisement packets. This means that SCAN REQ packet is not reported outside the BLE chip of the device whereby the slave device does not know if the advertisement packet was received and by who.

The present embodiments improve the previous by enabling the application of the slave device to know that a master device has received an advertisement packet. For that a device in advertising mode reports SCAN REQ messages to the application layer so that the application can reliable detect that data in the advertisement packet was received by a certain device.

This is illustrated in . resembles but differentiates in that the SCAN REQ being received from link layer LLA of host A is further transmitted from link layer LLB of host B. Now it is not only the link layer LLB or BLE module that is aware of that host A received an advertisement packet but also the application layer knows it.

SCAN REQ contains scanner s and advertiser s address meaning that there is no payload. Scanner address as such is useful but there are some metadata e.g. channel and receiving time for the packet. The metadata may also be sent to upper layer i.e. application layer. The application logic may be divided in to layers but also link layer may process the SCAN REQ packet in addition to just sending SCAN RSP.

The present embodiments propose using information such as master address being obtained from SCAN REQ packet to control application layer logic. Therefore the application is able to determine what kind of data should be put to the advertisement packet or whether to advertise at all. The SCAN RSP packet may be modified before transmission to the scanner. However because the SCAN RSP should be send within 150 s from receiving the SCAN REQ the processing time for SCAN RSP packet is very small. As an alternative the link layer may contain different kinds of SCAN RSP packets for different SCAN REQ i.e. transmitted from different addresses packets.

When an apparatus such as an apparatus in knows that data has been received by another device the apparatus changes its operation. How the operation is changed depends on the type of the Bluetooth low energy enabled device i.e. an apparatus comprising the Bluetooth low energy module.

In an example a thermometer is configured to slow down the advertising and go to power save mode. After for example an hour the thermometer can wake up and start advertising again. This can be implemented as follows The thermometer has an application running. The application receives the measurement in every hour reports it to GAP and asks GAP to enter to advertising mode. GAP generates an advertisement packet containing the temperature and transmits the packet to link layer with a command to start advertising in every 100 ms. At some point a mobile terminal or another scanning device being interested in this temperature scans the packet and sends an SCAN REQ packet to the thermometer. Link layer of thermometer receives the SCAN REQ packet and informs either GAP or the application layer directly on it. The application layer notices that a certain scanner has received an information on the temperature after which it turns down the advertising mode to save power.

The above description is an example on the procedure and the device. However it is appreciated that the principle of the invention may be utilized by any other device as well. What is important is that the device determines the following action to be performed based on the SCAN REQ packet being received and then performs the action. The action may be either changing the operation mode from an advertising mode to a power save mode or vice versa or the action may be to modify or select a certain SCAN RSP packet to be transmitted as a response.

It is also realized that just receiving SCAN REQ packet is information which indicates that somebody has received the data. According to an embodiment for notifying the slave application that the master device has received the transmitted advertisement packet a metadata from advertisement channel may be used.

The various embodiments may provide advantages. For example over the air traffic can be reduced because only two packets is needed for indicating that an advertisement packet has been received. Also by the present embodiments power can be saved because the advertising device can stop advertising and go to the sleep mode after having received an indication that someone has received its advertisement packet.

The various embodiments of the invention can be implemented with the help of computer program code that resides in a memory and causes the relevant apparatuses to carry out the invention.

It is obvious that the present invention is not limited solely to the above presented embodiments but it can be modified within the scope of the appended claims.

While there have been shown and described and pointed out fundamental novel features of the invention as applied to preferred embodiments thereof it will be understood that various omissions and substitutions and changes in the form and details of the devices and methods described may be made by those skilled in the art without departing from the spirit of the invention. For example it is expressly intended that all combinations of those elements and or method steps which perform substantially the same function in substantially the same way to achieve the same results are within the scope of the invention. Moreover it should be recognized that structures and or elements and or method steps shown and or described in connection with any disclosed form or embodiment of the invention may be incorporated in any other disclosed or described or suggested form or embodiment as a general matter of design choice. It is the intention therefore to be limited only as indicated by the scope of the claims appended hereto. Furthermore in the claims means plus function clauses are intended to cover the structures described herein as performing the recited function and not only structural equivalents but also equivalent structures. Thus although a nail and a screw may not be structural equivalents in that a nail employs a cylindrical surface to secure wooden parts together whereas a screw employs a helical surface in the environment of fastening wooden parts a nail and a screw may be equivalent structures.

