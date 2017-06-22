---

title: System coordinated WLAN scanning
abstract: The invention proposes a scan control device, wherein in the scan operation a network detection is performed, the device comprising a request receiving means for receiving at least one request for providing scan information, and a scan control means for performing a scan operation independently from receiving the scan information requests. The invention also proposes a corresponding method and a computer program product.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09554327&OS=09554327&RS=09554327
owner: NOKIA TECHNOLOGIES OY
number: 09554327
owner_city: Espoo
owner_country: FI
publication_date: 20140702
---
This application is a Continuation of U.S. application Ser. No. 11 377 454 filed Mar. 17 2006 which claims priority from European Patent Application Number 05014203.3 filed Jun. 30 2005 the contents of which applications are herein incorporated by reference.

The invention relates to a method and a device for wireless communication by which a scan for access networks can be performed.

This invention is related to a network in which a device for wireless communication may establish a connection to one or more access networks. Examples for such access networks are Wireless Local Area Networks WLAN wherein each network is identified by a Service Set IDentifier SSID .

There are several reasons why a device might connect to a plurality of access networks. Namely certain applications have needs for different kind of networks. For example access networks may include a company network hotspot provider ISP Internet Service Provider operator networks and home WLAN networks. Different networks can provide different set of destination networks. Here a couple of examples 

From a company network it is possible to reach intranet and Internet but it might not be possible to send mails via your person ISP account. From a WLAN home network you might not be possible to use intranet services. Also in technologies like UMA Unlicensed Mobile Access it might not be possible to carry data over UMA in all operators so that also in this case it might be necessary to change an access network or to use additionally an alternative access network.

Furthermore scanning for new access networks might be advantageous in order to get cheaper connection better performing connection or to find a current network for a particular service as described above. Also technologies like location information using WLAN may use extensively scanning.

When connecting to WLAN networks it is necessary to scan for surrounding WLAN networks to which a WLAN station STA may connect. The scanning procedure may be a passive scan in which the WLAN station listens to beacons delivered from surrounding Access Points AP or an active scan in which the WLAN station sends probe requests and waits for an answer.

Currently most operating systems provide a basic WLAN API Application Programming Interface that allows applications do the scanning of the surrounding WLAN networks. Normally the scanning is done so that an application triggers a scan request via the API to a corresponding subsystem which then performs the scan operation. By having all the applications to perform separate scan logic this can create a situation where the whole system is scanning just about all the times due to one to one mapping of all the scan requests.

For example it is assumed that a WLAN station e.g. a mobile device has six applications that each have decided to scan the surrounding networks every two minutes. This situation can result in that the system initiates a scan every 20 seconds which is very unnecessary in most cases. This has a very large effect on power consumption. Namely the situation that the device has to scan every 20 seconds will cause the average power consumption to go up by 60 mW which is almost ten times more than a normal basic phone idle power consumption.

As clearly derivable from the stand by time drastically reduces when the number of scans per hour is increased.

Heretofore some implementations prohibit a system to do scanning too often and they are implementing this feature so that the system returns the old scan result if a certain threshold time has not been passed since the previous scan. For example the Nokia Communicator 9500 does it this way. However this makes application programming tricky as they do not know if the scan results are actually current or not. Also this type of behaviour forces all the applications to have separate timers and they wake up separately the application engine processor thus increasing power consumptions. Hence this approach does not solve the problem sufficiently.

Furthermore while a scan operation is performed sending and receiving of data MPDUs MAC Medium Access Control Protocol Data Unit is not possible due to implementation limitation or it is very slow so that the long time needed for the scan results affect applications in particular applications that have real time requirements like voice. Thus an increased number of scan operations may be annoying for the user of the WLAN station.

Hence it is an object of the present invention to solve the problem mentioned above and to minimize the number of scans.

This object is solved by a scan control device wherein in the scan operation a network detection is performed the device comprising

a request receiving means request receiver for receiving at least one request for providing scan information and

a scan operation control means scan operation controller for performing a scan operation independently from receiving the scan information requests.

Alternatively the above object is solved by a method for controlling a scan operation wherein in the scan operation a network detection is performed the method comprising the steps of

controlling performing of a scan operation independently from receiving the scan information requests.

Hence according to the invention the scan operation is performed independently from the requests for providing scan information.

Therefore a scan operation does not have to be performed each time such a request is received but a scan operation can be carried out independently. In this way only one scan operation is necessary during a particular time period whereas according to the prior art for example scan operations in the number of the applications were necessary during the same time period.

Hence according to the invention an application transparent way of doing scanning is provided so that as many applications as possible could use the same scan results so that not every application would be doing this scanning on their own.

For example the scan operation control means may send scan information which is obtained based on the scan operation. Moreover the request for providing scan information may be stored in a memory and the scan information may be sent by referring to the request stored in the memory. That is a scan request does not have to be processed immediately but can be stored and is pending. When the result is to be sent to the application issued the request the scan information is sent using information from this request.

Alternatively the request may be a registration for a scan event. That is an application can register to the scan event.

Furthermore a maximum latency value may be received which indicates a maximum delay time by which a scan operation may be delayed. That is an application requesting the scan operation can indicate which maximum delay time it allows for the scanning operation.

In detail the request for providing scan information may contain a parameter indicating the maximum latency value.

Furthermore an interval for performing the scan operation may be set based on the maximum latency value.

In case there are a plurality of requests for providing scan information and a plurality of maximum latency values the interval may be set based on the minimum value of the maximum latency values.

The network detection may be performed with respect to at least one Wireless Local Area Network WLAN . That is the networks in question may be WLAN networks.

Moreover a plurality of application devices may be provided and the scan control device may be configured to forward scan information to all application devices simultaneously.

The method according to the invention may be realized as a computer program product for a processing device comprising software code portions for performing the steps of the method according to the invention when the program is run on the processing device. The computer program product may comprise a computer readable readable for the processing device medium on which the software code portions are stored.

In this case the request to provide scan information may be generated by at least one application module for executing an application.

Furthermore in case a plurality of application modules are present the scan control module may forward scan information to all application devices simultaneously. The scan control module may be implemented in an Application Programming Interface API .

In particular the processing device may be part of a WLAN apparatus in more detail a part of a WLAN host device so that the computer program may be stored in a memory of the WLAN apparatus.

In the following a preferred embodiment of the present invention is described by referring to the attached drawings.

In particular according to the preferred embodiment an API as an example for a scan control device is provided which controls the scan operation such that the actual scan is performed independently from scan requests. That is the actual scan is carried out at an own independent timing.

The WLAN station or WLAN apparatus comprise the WLAN device and a host device wherein in the host device the application modules to and the API are accommodated.

It is noted that the WLAN device can be a WLAN card to be inserted in a laptop computer in a PDA personal digital assistant a mobile phone a WLAN enabled device connected to the host by some other wireless technology e.g. bluetooth a USB Universal Serial Bus stick inserted in a USB port of a laptop computer or a fixed personal computer or the like. In these cases the laptop computer and the fixed personal computers are examples for host devices. Furthermore the WLAN apparatus can be a laptop computer having an on board WLAN functionality a WLAN enabled phone or the like. In these cases the WLAN device and the host device are arranged within one entity and may only be logically separated.

In three main parts of the API are illustrated a connection module as an example for a request receiving means establishes a connection to the application modules to in order to receive scan requests and to send scan results a scan control module for performing the actual control of the scan operation a memory for storing scan requests or scan registrations and also for storing programs data etc and a timer for setting scan intervals.

According to the preferred embodiment the connection module receives a scan request from at least one of the application modules. This request is forwarded to the scan control module which controls the scan operation independently from the reception of the scan request.

That is according to the present embodiment the SW Software subsystem of the WLAN station provides an API that allows various applications to register for a delayed scan event when ever the system scans. When system would do the scanning all the applications would be let to know about the scan results as a scan event instead of having then to poll the system themselves.

Hence according to the present embodiment a centralized way of controlling when the actual WLAN scan happens is provided by separating the interface and implementation from the applications.

It is noted that the scan request can be a direct scan request which is basically the same as the scan known in the prior art or alternatively a registration for a scan event. The registration for a scan event means that the application informs the API that it would like to have scan results when the WLAN device actually performs a scan operation.

In the following the operation according to the preferred embodiment is described by referring to . In the timings of scan requests of the applications and the actual start of the scan operation are illustrated.

In this example it is assumed that the application which wants to initiate a WLAN connection when it sees a network a decides to register itself for scan events. Application decides then to also set that it would like the system to scan after every 2 minutes. This registration or request is issued at the beginning of the illustrated sequence i.e. at 0 seconds.

Then the application is started 30 seconds later and it also wants to initiate a WLAN connection when it sees a network b . Thus it decides to register itself for scan events. It also sets its scan period to be 2 minutes.

Then application is started further 30 seconds later and it also wants to initiate a WLAN connection when it sees a network b decides to register itself for scan events. It sets its scan period to be 3 minutes. This registration or request is issued at 60 seconds.

After 30 seconds the system i.e. the WLAN device under control of the API and in more detail of the scan control module scans and the scan results are delivered to all the applications simultaneously. As the maximum interval for the scan is two minutes the interval of 3 minutes requested by the application would be to long for the applications and the system waits for another two minutes after providing another scan results. That is the scan control module sets the timer to two minutes so that a scan operation is performed every 2 minutes.

In contrast thereto according to the prior art the scan operation would have been carried out immediately upon issuing the corresponding scan requests and then at each individual interval. That is in average every 40 seconds the scan operation would have been carried out.

It is noted that the actual scan operation can be started at an arbitrary timing independent from the timings of issuing the scan requests. For example a first scan operation can already be carried out immediately e.g. 5 seconds after receiving the first scan request from application . The applications and which issued their scan requests or registered to the scan event later will be provided with the scan results upon the next scan operation i.e. at 2 minutes and 5 seconds after the start.

Thus according to the preferred embodiment the amount of power needed by the WLAN chipset WLAN device as well as the host processors including API and applications is reduced.

Hence in order to implement this type of service the API is adapted to allow applications to register for scan events or issue a scan request that will be pending on the WLAN subsystem until the subsystem actually performs scan and then the call is returned i.e. the scan results are delivered to the applications. Furthermore the API allows some way of setting the maximum scan latency by the applications. This can be done either during the pending scan requests as a parameter or by setting a separate application specific MIB Management Information Base .

The parameter during the scan request is referred to as a maximum pending timeout parameter with a pending scan request asynchronous scan request . Many operating systems provide an asynchronous service that allows client send a message to service and still carry on executing its code path until it receives an indication about the completion of the request.

In the following an implementation example for such a type of request from client side for this type is described wherein a start with forced scan and then a move into a periodic mode is illustrated. It is noted that the following examples are written in a pseudo code based on the computer language C.

Hence according to the present embodiment it is possible to provide parameters with an asynchronous request which is also referred to as a pending request.

It is noted that it is basically possible to force the subsystem to do the scanning right away by specifying the MaximumScanLatency to zero. However this is only sensible for initial scan requests or an emergency scan request after losing connection or the like since this would imply that also during normal operation i.e. after the starting procedure scanning has to be performed all the time.

In the above example this maximum scan latency is 2 minutes for applications and and minutes for application . That is the scan interval is set according to the minimum of maximum scan latencies of the applications which is 2 minutes in the above example.

The system may perform a basic scanning right away when the first request is being issued but after that all the framework initiated scans are synchronized together so that the maximum latency would always be respected.

Furthermore if some other system events trigger scan immediate scan request call etc. then the framework will make use of the new scan requests by providing the scan information for application as well and basically resetting the timer again.

That is in case an immediate scan operation is required the scan control module immediately performs the scan operation and resets the timer so that the next scan operation is performed after the interval previously set with the timer .

Moreover in case a new request is issued or another application registers to the scan event the interval can be adapted. That is in case an application in the above example needs to have a scan operation every 1 minute than the interval is to 1 minute so that also the value of the timer would be rewritten to 1 minute. A similar operation is carried out when an earlier request or registration is modified namely when for example it is for some reason necessary for application to have a scan operation every 1 minute.

To applications the type of scanning according to the present embodiment would look like a delayed scan request but most of the applications would not care about this as usually scanning is anyway a periodic operation.

That is in a practical implementation it is not necessarily required to adapt the applications to the scan procedure according to the present embodiment. They can simply issue scan requests as in the prior art but will receive the results delayed.

That is the scan requests may be simply stored in the memory and when the scan result is sent to the application modules to the scan control module refers to the stored scan request in order to address the corresponding application module for example.

Hence according to the present embodiment the power consumption due to scanning operations can be significantly reduced. That is the stand by time of a WLAN station such as a mobile phone a laptop computer or the like with WLAN functionality can be considerably prolonged.

The more applications there are the more benefits from power consumption point of view can be achieved. Having system initiated scanning can also help applications to react for certain events. For example when connection gets bad the system will start performing an automatic scan operation immediately in order to roam. Then all the scan results are being delivered to the applications which gives them more time to adapt to the low signal conditions.

Namely if by using the conventional technique all applications would start doing separate scanning and one scan would take 0.5 seconds then in a case of five applications the last application would get its result after 2.5 seconds. In contrast thereto all applications receive the scan results after the first scan i.e. after 0.5 seconds.

Hence according to the present embodiment an application transparent way of doing scanning is provided so that as many applications as possible could use the same scan results so that no every application would be doing this scanning on their own.

Further possibility to benefit from this invention in WLAN station power consumption sense is that the WLAN station can be set to operate in a low power mode. In such case there would be a limit for the scanning frequency. Such a limit could be e.g. one scan per 30 s. Since scanning would not be made more often the applications registered for scan events might have to settle for the same scan result several times. Nevertheless there would be the advantage of performing scans for all the registered applications instead performing scans for all the applications separately and simultaneously save power.

The invention is not limited to the embodiment described above and various modifications are possible.

For example the invention is not limited to WLAN but can also be applied to other radio networks in which it is necessary to perform a scan operation in order to detect access networks.

The invention can also be realized by a computer program product. The computer program product i.e. the computer code may be stored on a medium e.g. a memory card a RAM Random access memory or a ROM read only memory a hard drive a CD ROM or a DVD ROM.

In this case the different applications described above are application program modules and the API is realized as an API program module.

