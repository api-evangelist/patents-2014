---

title: Integrated circuit board with wireless circuitry
abstract: An IC Card comprises a first device, including a first processor and a first memory unit, to communicate with a handset, and a second device. The second device includes a second processor and a second memory unit, to communicate via a wireless communication with an electronic apparatus external to the handset, the second device providing predetermined services. Each predetermined service is programmed to receive a wireless message from a respective electronic apparatus, to execute a predetermined elaboration operation, and to return a result to the respective electronic apparatus. The second memory unit stores a plurality of additional programs for executing additional elaborations operations, each program being associated to one of the predetermined services. The second device has a run-time environment for executing the additional programs when the corresponding predetermined services receives the wireless message.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=RE045769&OS=RE045769&RS=RE045769
owner: STMICROELECTRONICS INTERNATIONAL N.V.
number: RE045769
owner_city: Geneva
owner_country: CH
publication_date: 20140324
---
The present invention is related to the field of IC Cards and more particularly to an IC Card for communicating with a wireless device.

An IC Card comprises a first device including a first processor and a first memory unit intended to communicate with a handset for example a mobile telephone. The IC Card is substantially enclosed inside the handset and electrically connected to it via contact pads.

A communication between the handset and the IC Card generally complies with an ISO 7816 protocol wherein the handset sends commands to the IC Card and the IC Card responds to such commands as a slave device. The IC Card may also comprise a second device including a second processor and a second memory unit intended to communicate with an electronic apparatus.

The IC Card of comprises a first device intended to communicate in conventional way with a handset and a second device intended to communicate with an electronic apparatus . The electronic apparatus is substantially external to the handset device and in wireless communication with the second device . More particularly the IC Card comprises an antenna connected to or included in the second device for receiving and transmitting wireless messages from to the electronic apparatus .

The second device emits conventional messages at predetermined intervals representing the profile of the second device . In other words the profile of the second device specifies the wireless messages that it is able to receive. The electronic apparatus in proximity of the handset device detects a conventional message emitted by the second device and responds to it with a wireless message.

When the antenna receives the wireless message from the electronic apparatus the wireless message is processed by the second device and a result is returned to the electronic apparatus . The profile of the second device may be programmed to receive wireless messages from different electronic apparatuses. In this case the second device may receive different wireless messages from different electronic apparatuses and process a specific result depending on the wireless messages received.

More particularly the second device provides one or more predetermined services a b c also indicated in as endpoint applications intended to receive wireless message from different and respective electronic apparatuses and to process the specific results.

When the electronic apparatus sends the wireless message to the antenna the corresponding predetermined service for example the predetermined service a executes a predetermined elaboration operation and returns a result to the electronic apparatus . The wireless communication may for example be based on the ZigBee protocol in this case the second device and the electronic apparatus are ZigBee nodes.

A drawback of such IC Card is that a long delay may occurs between the time in which the IC Card receives the wireless message and the time in which the IC Card may perform a consequential operation e.g. return the result to the corresponding electronic apparatus .

The external apparatus sends the wireless message indicated as remote request to the second device of the IC Card . In order to process the wireless message a software module indicated as ZigBee Engine is executed. As schematically represented in the ZigBee Engine is stored inside the first device and provides additional API for the execution of the predetermined services a b c and for managing a communication between the first device and the second device .

When the wireless message is received by the second device the first device may be not ready to execute the ZigBee Engine since it is a slave device with respect to the handset device and must wait for an APDU command from the handset device in order to execute the ZigBee Engine.

Such a drawback heavily penalizes the wireless communication between the second device and the electronic apparatus since the electronic apparatus cannot receive the result of the elaboration operation rapidly but it must wait for the execution of the ZigBee Engine. In other words the IC Card cannot be used with electronic apparatuses requiring a result in a few time. This is not helpful in case of protocols based on fast exchanges of small messages such as handshake procedures.

More particularly according to the ISO 7816 protocol the handset device executes a poll operation towards the first device of the IC Card in order to detect a status of the first device . The first device sends a poll message to the second device . Since the second device has received a wireless message it returns the wireless message to the first device .

The ZigBee Engine is executed to process the wireless message a reply message is forwarded to the second device and the result is delivered to the electronic apparatus via a wireless communication. The delay due to the operations described above is schematically shown in as effective response delay .

Moreover the ZigBee Engine is generally programmed to recall specific applets also indicated as ZigBee Applet a b c and stored inside the memory unit of the first device for executing the predetermined services a b c. Each ZigBee Applet a b c is generally provided to manage a corresponding predetermined service a b c. So the delay for returning the result to the electronic apparatus is also due to the execution of the ZigBee Applet a b c as schematically represented in .

Such IC Card suffers for another issue due to the fact that the predetermined services a b c provides predetermined elaborations operations depending on the hardware design of the second device . In order to modify the predetermined services a b c for example for processing an elaboration operation different from the predetermined one the hardware of the second device may helpfully be modified.

The present invention provides an IC Card able to communicate with a handset and additionally in wireless mode with one or more electronic apparatuses the IC Card being able to receive wireless messages from the electronic apparatuses to execute a predetermined elaboration operation as soon as the wireless message is received and to return a result to the electronic apparatus as soon as the result is processed without introducing delay due to the communication between the handset and the IC Card the IC Card being also easily configurable to modify the elaboration operation to be executed avoiding hardware modification of the second device.

The present disclosure provides an IC Card including a first device intended to communicate with a handset and a second device intended to execute predetermined elaborations operations for an electronic apparatus the second device further including a plurality of additional programs for providing additional elaborations operations such additional programs being executed without waiting a communication between the first device and the handset.

An IC Card comprises a first device including a first processor and a first memory unit intended to communicate with a handset and a second device including a second processor and a second memory unit intended to communicate via a wireless communication with at least an electronic apparatus external to the handset the second device providing predetermined services. Each predetermined service is programmed to receive a wireless message from a respective electronic apparatus to execute a predetermined elaboration operation and to return a result to the respective electronic apparatus. The second memory unit stores a plurality of additional programs for executing additional elaborations operations each program being associated to one of predetermined service. The second device comprises a run time environment for executing the additional programs when the corresponding predetermined services receives the wireless message.

Advantageously additional elaborations operations may be executed by the second device without modifying the hardware of the second device and without modifying the wireless communication between the second device and the electronic apparatuses since the execution of the additional programs is activated by the predetermined services.

Moreover the additional programs may be modified easily and post issuance in order to modify the additional elaboration operation and the corresponding results returned from the second device to the electronic apparatuses. Advantageously the run time environment of the second device provides that the execution of the additional elaboration operation and the corresponding result may be returned to the electronic apparatuses without introducing long latencies due to the communication between the handset and the first device.

These and other advantages will be apparent from the following description and from the annexed drawings given only for exemplificative purpose and without limiting the scope of protection of the appended claims.

With reference to the annexed drawings an IC Card is schematically represented and globally indicated with numeral reference . The IC Card comprises a first device including a first processor and a first memory unit M intended to communicate in conventional way with a handset according to the ISO 7816 protocol.

The IC Card also comprises a second device including a second processor and a second memory unit M intended to communicate with an electronic apparatus substantially external to the handset device in wireless communication with the second device .

The IC Card comprises an antenna for receiving and transmitting wireless messages from to the electronic apparatus . The wireless message is processed by the second device and a result is returned to the electronic apparatus .

More particularly as schematically represented in the second device provides one or more predetermined services a b c intended to receive wireless messages from different and respective electronic apparatuses and to process specific results.

When the electronic apparatus sends the wireless message to the antenna the corresponding predetermined service a b c executes a predetermined elaboration operation. The wireless communication is for example based on the ZigBee specification.

The second memory unit Mstores a plurality of additional programs a b c for executing additional elaborations operations. Each program a b c is associated to one of the predetermined services a b c so that the second device may return to the electronic apparatus a result not provided by the predetermined elaboration operation.

More particularly the second device comprises a run time environment for executing the additional programs a b c as soon as the corresponding predetermined services a b c receives the wireless message from the electronic apparatus. A plurality of applets stored in the first device and also indicated as ZigBee Applets have the capabilities provided by dedicated APIs of associating the additional programs a b c to the predetermined services a b c ZigBee Applet. The ZigBee Applets are executed when particular events occur e.g. at start up of the IC Card for associating the additional programs a b c to the corresponding predetermined services a b c.

When a predetermined service a b c receives a wireless message from an electronic device it executes immediately the corresponding additional program a b c through the run time environment the additional program a b c process the results that can be immediately returned to the electronic apparatuses .

According to the IC Card of the present invention when the additional programs a b c are associated to the predetermined programs a b c the additional programs a b c may process a result and result it to the electronic device without waiting for the execution of operations inside the first device .

More particularly the run time environment comprises but it is not limited to the following operations 

More particularly the second memory unit M comprises a storage area wherein data associated to an execution of the additional programs a b c are stored for example cryptographic keys text variables. The data stored in the storage area may be read or written by the predetermined services a b c as well as by the additional programs a b c during their execution.

For example the variables are stored in a portion of volatile memory or in a portion of non volatile memory of the second memory unit M. More particularly variables stored in different portions may be referred by the same name since each additional program a b c refers only to the portion associated to the respective predetermined service a b c.

The ZigBee Applet may be provided by specific commands to access the second memory unit M. For example this command may be based on additional API provided by the ZigBee Engine of the IC Card .

One aspect is directed to a method for downloading the additional programs a b c in the second device . More particularly the method provides the downloading of the additional programs a b c in different ways.

According to a first embodiment a specific service of the predetermined service a b c may be stored inside the second device for receiving the additional programs a b c from the electronic apparatus . In this case a specific electronic apparatus is provided for communicating with the second device and downloading the predetermined service a b c.

According to a second embodiment one or more ZigBee Applets stored in the first device provides the download of the additional programs a b c. For example the first device may receive a specific SMS including an additional program to be stored. When the specific SMS message is received the first device activates a specific ZigBee Applet. The ZigBee Applet accesses the second memory unit M of the second device and stores the program in the second memory unit M. The special SMS may be formatted and provided with security controls for example according to the standard ETSI TS 102 225.

According to a third embodiment each additional program a b c is downloaded by a corresponding ZigBee Applet. In this case for each predetermined service a b c a corresponding ZigBee Applet is provided. The ZigBee Applet controls the execution of the predetermined service a b c and may update the additional program a b c associated to the predetermined service a b c.

Hereinafter the main features of the IC Card are resumed. The IC Card comprises a first device including a first processor and a first memory unit M intended to communicate in conventional way with a handset and a second device including a second processor and a second memory unit M intended to communicate via a wireless communication with at least an electronic apparatus external to the handset .

The second device provides predetermined services a b c each predetermined service a b c being programmed to receive a wireless message from a respective electronic apparatus to execute a predetermined elaboration operation on the base of the wireless message received and to return a result to the respective electronic apparatus .

The second memory unit Mstores a plurality of additional programs a b c for executing additional elaborations operations each program a b c being associated to one of the predetermined services a b c. The second device comprises a run time environment for executing the additional programs a b c when the associated predetermined services a b c receive the wireless message.

The first device includes at least an applet also indicated as ZigBee Applet for associating the additional programs a b c to the corresponding predetermined services a b c . The second device is a ZigBee node and the wireless communication between the second device and the electronic apparatus comply with a ZigBee specification.

The first processor comprises additional APIs for supporting a communication between the ZigBee Applets and the second device .

Hereinafter the main features of the method for executing at least an additional program in an IC Card are resumed. The additional program a b c are by an IC Card comprising a first device intended to communicate in conventional way with a handset and a second device intended to communicate via a wireless communication with at least an electronic apparatus external to the handset . The second device provides predetermined services a b c associated to the additional programs a b c and programmed to receive a wireless message from a respective electronic apparatus .

The additional programs a b c are executed by a run time environment of the second device when the corresponding predetermined services a b c receives the wireless message. According to a first embodiment of the method the additional programs a b c are downloaded in a second memory unit M of the second device by an applet also indicated as ZigBee Applet of the first device .

According to a second embodiment of the method the additional programs a b c are downloaded in the second memory unit M of the second device by a specific predetermined service a b c programmed to receive the additional programs a b c from a corresponding specific electronic apparatus .

According to a third embodiment of the method the additional programs a b c are downloaded in the second memory unit M of the second device by an applet also indicated as ZigBee Applet programmed to receive a specific SMS that includes the additional programs a b c to be downloaded.

The additional programs a b c are associated to the predetermined services a b c by an applet or ZigBee Applet. Advantageously the IC Card allows the reduction of the response time required by the second device to return a result to the electronic apparatus and to perform any consequential operation.

As already stated without the additional programs a b c and the run time environment the response time of the second device towards the electronic device would depend on the applets or ZigBee Applets execution inside the first device . In fact according to the SIM Application Toolkit applets the ZigBee Applet are executed only from time to time when the handset activates the first device . However the activation of the IC Card may not occur continuously and long time may occur between the receipt of a wireless message from the second device and the activation of the first device . So the processing of the result to be sent from the second device towards to the electronic apparatus would be delayed.

Advantageously the present disclosure taking advantage of the fact that the second device is active and listening to incoming wireless messages from the electronic apparatus is able to process the wireless messages independently and autonomously with respect to the first device and handset . This reduces the delay for executing requests from the electronic apparatuses achieving a consistent benefit in real time applications.

The advantage is also greater when the second device communicates with a remote device via the electronic apparatus since data send to and received from the remote device are not delayed by the execution of a ZigBee Applet. A further advantage is based on the fact that a computational load may be balanced among the second device and the first device allowing more efficient executions.

Moreover the behavior of the second device in other words the elaboration operation provided by the second device on the receipt of a wireless message from an electronic device may be updated in simple way by modifying even remotely the additional program a b c and avoiding any hardware change.

The IC Card achieves great advantages also with respect to a handset provided with wireless communication for example Bluetooth and with programmable computation for example Symbian o J2ME.

In fact the Bluetooth Symbian J2ME handset is an expensive device while the IC Card provided with a second device and the corresponding wireless communication is a cheap device and it may be used with a handset .

Moreover since the IC Card is provided with secured means and with a user profile the additional elaborations operations may be associated to the identity of the used and or they may be protected by cryptographic operations providing a secure communications and results to the electronic apparatuses .

