---

title: Mobile communication station having selectable position latency for position estimation in a wireless network
abstract: Mobile communication stations (STA) and a method for position estimation in a wireless network having access points (APs) are disclosed. The STA is configured to perform position estimation operations, with respect to the APs, based on a position latency parameter, a rate parameter, a power parameter, and an accuracy parameter. An upper layer of the STA may send the parameters to a position provider that generates the position estimation measurements and transmits the results back to the upper layer wherein the results include the position of the STA prior to the present time and the length of time from the present time to the time that the STA was at that particular position.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09374676&OS=09374676&RS=09374676
owner: Intel Corporation
number: 09374676
owner_city: Santa Clara
owner_country: US
publication_date: 20141219
---
Embodiments pertain to wireless network communications. Some embodiments relate to the IEEE 802.11 standards. Some embodiments relate to wireless networks. Some embodiments relate to indoor positioning and indoor location. Some embodiments relate to geo fencing and geo logging. Some embodiments relate to time of flight ToF position estimation.

Outdoor navigation is widely deployed through the use of various global navigation satellite systems GNSS such as the U.S. Global Positioning System GPS the Russian Global Navigation Satellite System GLONASS and the European GALILEO. These systems may operate effectively outdoors but due to satellite reception problems may not be very effective indoors.

Relatively recently there has been a focus on solving indoor navigation problems. One solution may be based on Time of Flight ToF positioning methods. Time of Fight may be defined as the overall time a signal propagates from a mobile communication station STA e.g. user to an access point AP and back to the user. This value may then be converted into distance by dividing the time by two and multiplying the result by the speed of light. The position estimation may be performed periodically multiple times per second in order to provide an accurate position estimation. This method may be robust and scalable but may consume more power than is desirable depending on the application.

Subsequently described embodiments refer to WiFi communication systems and Institute of Electrical and Electronics Engineers IEEE 802.11 i.e. a set of physical layer standards for implementing wireless local area network WLAN computer communication . However the present embodiments are not restricted to only a WiFi communication system or any particular communication standard. The present embodiments may be used in any communication system in which location and navigation capabilities may be desired.

ToF positioning methods may provide a way to determine a STA location in an environment where GNSS may not be available e.g. indoors . APs typically have fixed antennas whose positions are known. Thus a STA using ToF trilateration between multiple APs may generate a relatively accurate estimate of the STA s position. The ToF calculations may be used with any wireless technology including WiFi Bluetooth and or cellular.

The present disclosure is not limited to ToF calculations. Other embodiments may use other ways to estimate the STA position. For example the STA position may be estimated by inertial sensors in the STA a GPS receiver in the STA magnetometers barometers and or map data including street maps indoor maps or combinations of any of these and other ways to estimate or determine a position. A position estimation determination module e.g. circuit may include any one or more of these ways to estimate determine the STA position. The module may be hardware software or a combination of hardware and software.

The position estimation may be performed between the STA and the APs one or more times per second. This results in the STA using its limited battery power to continuously update its position even when such a frequent update may not be necessary for the user and or an applications being executed on the STA. The subsequently described embodiments include a position latency parameter in addition to the power and accuracy parameters when estimating the STA s position. Using the position latency parameter the present embodiments provide a STA with higher accuracy of position estimation for the same power or the same accuracy of position estimation using less power.

As used herein position latency may be defined as a time period between a time that a STA arrives at a position and a time when it performs a calculation to estimate its position.

The STA may be a communication device that is non stationary. Such a communication device may include mobile radiotelephones e.g. cellular telephones tablet computers lap top computers or other communication devices that may communicate with the access points over one or more wireless channels using a communication technique e.g. IEEE 802.11 .

The access points have fixed locations. The access points may be part of a stationary network that may be coupled to a larger network e.g. local area network LAN wide area network WAN . For example the access points may be part of a wired network that is coupled to the Internet. The STA may then access the larger network by communicating over the wireless channels with the access points .

It may be desirable for the STA to know its location with relation to the access points . Since the geographical locations of the access points are fixed and known the geographical location of the STA may be determined by trilateration and tracked thereafter. The trilateration may be accomplished by using ToF calculations as described previously.

The communication apparatus may include at least one controller e.g. a central processing unit CPU a graphics processing unit GPU or both processor cores compute nodes etc. a main memory and a static memory that communicate with each other via a link e.g. bus . The memory may be used for storing map data used herein. The communication apparatus may further include a display device e.g. video LED LCD and an alphanumeric input device e.g. a keypad keyboard . In one embodiment the display device and the input device may be incorporated as one unit as a touch screen display. The communication apparatus may additionally include a mass storage device e.g. a drive unit a signal generation device e.g. a speaker a network interface device and one or more sensors e.g. GPS receiver magnetometer barometer inertial sensor . The network interface device may include one or more radios e.g. transmitters and receivers coupled to one or more antennas in order to communicate over a wireless network channel as illustrated in . The one or more radios may be configured to operate using one or more of the IEEE 802.11 standards.

The storage device includes a computer readable medium on which is stored one or more sets of data structures and instructions e.g. software embodying or utilized by any one or more of the methodologies or functions described herein. The instructions may also reside completely or at least partially within the main memory static memory and or within the controller during execution thereof by the communication apparatus with the main memory static memory and the processor also constituting computer readable media.

While the computer readable medium is illustrated in an example embodiment to be a single medium the term computer readable medium may include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more instructions .

Embodiments may be implemented in one or a combination of hardware firmware and software. Embodiments may also be implemented as instructions stored on a computer readable storage device which may be read and executed by at least one processor to perform the operations described herein. A computer readable storage device may include any non transitory mechanism for storing information in a form readable by a machine e.g. a computer . For example a computer readable storage device may include read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices and other storage devices and media. In some embodiments a system may include one or more processors and may be configured with instructions stored on a computer readable storage device.

For purposes of clarity and illustration subsequent discussions refer to the upper layer as being the operating system OS . However the present embodiments are not limited to any one upper layer process.

The functional block diagram illustrates an application programming interface API i.e. a set of protocols between applications between the OS and the position engine PE i.e. position algorithm . The OS is configured to control the STA as well as provide an interface for a user to interact with the STA. The PE is configured to interact with the OS in order to estimate a position of the STA. The interaction between the OS and the PE may include the API as well as the results e.g. estimated position of the operation.

In the illustrated embodiment the API between the OS and the PE includes a rate parameter a power parameter an accuracy parameter and a selected position latency parameter. The OS sends the position rate parameter to the PE to instruct the PE as to the time between two position reports from the PE to the OS . The rate of reporting may affect the resolution of the trajectory. The OS sends the power parameter to the PE to instruct the PE to obtain a position estimate based on the power parameter. For example the OS may send one of the following parameters high low none. The high parameter may instruct the PE to obtain the best position estimate in any way it can e.g. GPS only GPS and WiFi which would use a higher power. The low parameter would instruct the PE to minimize it power usage in obtaining the position estimate e.g. WiFi only . The none parameter would instruct the PE to respond with the already obtained position estimate without additional measurements and without additional power usage.

The OS sends the accuracy parameter to the position engine to instruct the PE as to what level of accuracy is desired. This parameter may be an indication of the accuracy as represented by a particular error distance e.g. meters or a high accuracy or a low accuracy indication. The PE may use this parameter in combination with the power parameter in determining when to use a WiFi trilateration method only a GPS only method or a combination of both GPS and WiFi.

Not all applications executed by the STA need the same accuracy or position update frequency for STA position. For example a navigation application for a vehicle may need updated more often than an application to log a jogging route. Another application may need only a single position estimation. In the illustrated embodiment the OS sends the selected position latency parameter to the PE so that the PE knows what the restrictions are with respect to the timing of when to perform a position estimation after arriving at a location.

It should be noted that the position latency parameter is different from the rate parameter. The rate parameter indicates how often the PE is to report the STA position e.g. frequency of reporting the position to the OS . The position latency parameter indicates a time period for estimating the STA position in relation to a time at a previous position. Thus various combinations of these parameters may be used including high rate high position latency high rate lo position latency low rate high position latency and low rate low position latency.

The API interface between the OS and the PE may include at least the four parameters i.e. rate power accuracy position latency such that the PE may now have multiple operational modes that combine all of these parameters. For example these modes may include 

Selection of one or more of the modes by the upper layer e.g. OS may provide benefits over other modes. Typical conventional reporting for navigation or position indication on a map use minimal latency in order to report the STA position with minimal delay. Using minimal latency the PE estimates and reports to the OS only the present location. However with the higher selected latency e.g. modes 5 6 the PE has a longer time period over which to collect additional previous measurements up to the present time and then report the result to the OS at the designated time or every designated time period. The result may include the position of the STA prior to the present time and the length of time from the present time to the time that the STA was at that particular position.

If lower power operation by the STA is desired or necessary to conserve a reduced battery storage mode 7 may provide lower power consumption as compared to for example mode 2. Since the position latency of mode 7 is longer than mode 2 fewer measurements may occur during the selected time period and thus the power consumption for performing the estimations is reduced.

Mode 8 may provide improved power consumption as compared to for example mode 3. Like mode 7 mode 8 also uses a higher latency and thus fewer measurements.

If greater accuracy with improved power consumption is desired mode 9 may provide better accuracy as compared to for example mode 3. As in previous examples the higher latency may make more measurements available including measurements based on future position.

At block the position provider receives parameters from a higher layer e.g. OS . As discussed previously these parameters may include rate power accuracy and position latency.

At block the position provider performs a position estimation operation based on the received parameters. As discussed previously the position estimation operation may be performed according to one or more of the above described modes as selected by the combination of the parameters. Depending on the mode the position estimation may be obtained using any of the above disclosed position estimation methods.

In block the position estimation is reported to the requesting layer e.g. OS based on the received parameters. For example the position latency parameter may indicate that the position estimation should be performed at a particular time after arriving at a particular position.

This embodiment may use a network of WiFi APs or some other wireless technology to provide the ToF operations with a STA in order to estimate a position of the STA. In another embodiment inertial sensors and map matching algorithms may be combined with the ToF operations to increase the accuracy of the estimations.

The STA is shown starting at a start position . The STA then move through the office area over a path to a final position . It can be seen that the low latency results in an erratic path through various areas that may not be important to note to the requester of the information.

In another example of operation of the method of a user may be walking with a STA through an urban canyon where satellite reception is unlikely to allow adequate position reporting. In such an embodiment the STA may use a trilateration operation to estimate its position based on ToF operations with wireless system APs. In such an embodiment a geo fencing may be used to define a virtual fence around the user s favorite coffee shop such that an alarm is generated when the STA is within that virtually fenced area. While walking a few blocks from the coffee shop the user may receive a false alarm due to an inaccurate estimation. By increasing the position latency such an outlier position may be filtered from being reported. Moreover by instructing the position provider to use the increased latency such outlier positions may not even be calculated.

In yet another example of operation of the method of a secured access embodiment such as Enterprise Right Management ERM may be improved by increased position latency. In such an embodiment it is important to verify a STA position at the secured location prior to giving the requested rights to the user. Position latency may be applied to increase the confidence in the position. Such an embodiment may use the highest accuracy high latency mode discussed previously.

In yet another example of operation of the method of a position analytics embodiment may be improved by collecting information that is not sensitive to latency. A large amount of position data may be gathered by monitoring the position of the STA through a particular time period. By smoothing the position data with a high latency position accuracy may be increased at the expense of latency. For example a store may gather location information from all of its customers in order to determine the time spent in particular parts of the store. The store may then adjust its layout or try different sales tactics.

In yet another example of operation of the method of the unsmoothed position data may be stored when performing one of the above described smoothing operations as a result of the high position latency. There is no need to store two different states for the position provider so when calculating a high latency position the low latency position data is also generated with no additional work. For example if a position with five seconds latency is calculated the positions with 4 3 2 1 and 0 seconds latency are also generated.

Example 1 is a mobile communication station STA for operation in a wireless network having access points APs the STA having hardware processing circuitry including logic configured to perform position estimation operations with respect to the APs based on a position latency parameter the circuitry including a position estimation module to estimate a prior STA position at a time delay indicated by the latency parameter wherein the time delay is a time period from a present time to a previous time that the STA was at that particular position.

In Example 2 the subject matter of Example 1 can optionally include an upper layer and a position provider wherein the upper layer is configured to provide a rate parameter a power parameter an accuracy parameter and the position latency parameter to the position provider.

In Example 3 the subject matter of Examples 1 2 can optionally include wherein the upper layer is an operating system and the position provider is a position engine.

In Example 4 the subject matter of Examples 1 3 can optionally include wherein the position engine is further configured to report position estimation results to the operating system in response to the position latency parameter such that the position estimation results comprise the prior position of the STA prior to a present time and the time delay from the present time to a time that the STA was at that particular position.

In Example 5 the subject matter of Examples 1 4 can optionally include memory configured to store map data including street maps and indoor maps.

In Example 6 the subject matter of Examples 1 5 can optionally include wherein the position estimation module is configured to estimate the STA position at a rate determined by a rate parameter from an operating system.

In Example 7 the subject matter of Examples 1 6 can optionally include wherein the position estimation module is configured to estimate the STA position based on the position latency parameter that is configured to represent a time period between a first time that the STA arrives at a prior position and a second time when the STA performs a calculation to estimate its position.

In Example 9 the subject matter of Examples 1 8 can optionally include at least one antenna coupled to the at least one radio.

In Example 10 the subject matter of Examples 1 9 can optionally include wherein the at least one radio is configured to operate over one or more wireless channels using an IEEE 802.11 standard.

In Example 11 the subject matter of Examples 1 10 can optionally include wherein the position estimation module is further configured to estimate the position of the STA using time of flight ToF calculations.

In Example 12 the subject matter of Examples 1 11 can optionally include a position engine configured to use the at least one radio a GPS receiver a magnetometer an inertial sensor a barometer and or map data to estimate the prior STA position based on a rate parameter a power parameter an accuracy parameter and the position latency parameter.

Example 13 is a method for position estimation of a mobile communication station STA with respect to access points APs the method comprising receiving a position latency parameter and performing a position estimation operation with respect to the APs based on the position latency parameter.

In Example 14 the subject matter of Example 13 can optionally include wherein receiving the position latency parameter comprises a position provider receiving the position latency parameter and further comprising the position provider reporting the position estimation to an upper layer of the STA.

In Example 15 the subject matter of Examples 13 14 can optionally include receiving a power parameter and an accuracy parameter and performing the position estimation operation in response to the power parameter the accuracy parameter and the position latency parameter.

In Example 16 the subject matter of Examples 13 15 can optionally include performing the position estimation operation comprises performing a WiFi trilateration and or performing a global positioning system GPS position estimation.

Example 17 is a non transitory computer readable storage medium that stores instructions for execution by processing circuitry of a mobile communication station STA to perform operations to estimate a location with respect to access points APs the operations to configure an initiating station to perform a position estimation operation with respect to the APs based on a position latency parameter.

In Example 18 the subject matter of Example 17 can optionally include wherein the operations further perform the position estimation operation based on the position latency parameter a power parameter and an accuracy parameter.

In Example 19 the subject matter of Examples 17 18 can optionally include wherein the operations further perform one of a plurality of modes based on the position estimation power and accuracy parameters the plurality of modes comprising high accuracy low latency low power low latency balanced power and accuracy low latency no power high accuracy high latency low power high latency balanced power and accuracy high latency for power or balanced power and accuracy high latency for accuracy.

In Example 20 the subject matter of Examples 17 19 can optionally include wherein the operations further perform the position estimation operation based on a predetermined time to perform the position estimation operation or a predetermined frequency for performing the position estimation operation as indicated by the position latency parameter.

The Abstract will allow the reader to ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to limit or interpret the scope or meaning of the claims. The following claims are hereby incorporated into the detailed description with each claim standing on its own as a separate embodiment.

