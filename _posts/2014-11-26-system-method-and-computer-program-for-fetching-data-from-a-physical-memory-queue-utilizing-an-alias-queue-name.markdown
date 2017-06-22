---

title: System, method, and computer program for fetching data from a physical memory queue utilizing an alias queue name
abstract: A system, method, and computer program product are provided for fetching data from a physical memory queue utilizing an alias queue name. In use, a physical queue associated with at least a portion of memory is identified. Additionally, a first alias queue name is mapped to the physical queue. Further, data is fetched utilizing the first alias queue name in response to a request to fetch the data from the physical queue.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09501228&OS=09501228&RS=09501228
owner: Amdocs Development Limited
number: 09501228
owner_city: Limassol
owner_country: CY
publication_date: 20141126
---
There is generally an outage or interruption in service when switching between applications listening getting and servicing requests from a particular memory queue. The activation deactivation process of an application set usually takes a few minutes thus creating an outage. The activation deactivation process of an application set is also error prone since it is handled at the client level.

A system method and computer program product are provided for fetching data from a physical memory queue utilizing an alias queue name. In use a physical queue associated with at least a portion of memory is identified. Additionally a first alias queue name is mapped to the physical queue. Further data is fetched utilizing the first alias queue name in response to a request to fetch the data from the physical queue.

As shown a physical queue associated with at least a portion of memory is identified. See operation . The physical queue may include any portion or portions of the memory. Moreover the memory may include any type of memory. In one embodiment identifying the physical queue may include allocating a portion or portions of the memory to the physical queue.

Additionally a first alias queue name is mapped to the physical queue. See operation . The first alias queue name may include any logical name and may include any number of characters symbols and or numbers etc.

Further data is fetched utilizing the first alias queue name in response to a request to fetch the data from the physical queue. See operation . The data may include any data stored in the physical queue. The data may be fetched utilizing a GET operation e.g. MQGET etc. .

The first alias queue may be associated with various applications and or application programming interfaces APIs . For example the first alias queue name may be associated with a primary application programming interface.

In one embodiment the method may further include receiving an indication to utilize a maintenance application programming interface instead of the primary application programming interface. In this case the maintenance application programming interface may have the same functionality as the primary application programming interface.

Additionally a second alias queue name may be mapped to the physical queue. The second alias queue name may be associated with the maintenance application programming interface. Moreover the second alias queue may be different than the first alias queue name.

When it is desired to use the maintenance application programming interface as opposed to the primary application programming interface e.g. in response to performing maintenance on the primary API etc. the maintenance application programming interface may be utilized without any down time. For example the first alias queue name may be mapped to a dummy queue and additional data may be fetched utilizing the second alias queue name in response to a request to fetch the additional data from the physical queue. The additional data may be fetched utilizing the second alias queue name without any disruption of service to application usage associated with the APIs.

As another example of a use case such techniques may be used in the context of usage scaling. For example the first alias queue name may be associated with a first set of applications.

Further a plurality of different alias queue names may be mapped to the physical queue. In this case each of the different alias queue names may associated with a different set of applications e.g. application set A application set B etc. .

Thus if it is determined to scale up usage associated with the first set of applications e.g. during a peak usage time etc. it may be determined to scale up usage associated with the first set of applications by utilizing the different set of applications. Accordingly data may be fetched from the physical queue utilizing the plurality of different alias queue names such that the different set of applications are capable of being utilized without interruption to use of first set of applications e.g. without any outage etc. .

Client applications that connect to a message queue may use different alias queues to connect. These may be activated by targeting the alias queue to the real queue or may be deactivated by targeting the alias queue to a dummy queue as and when required. The connections shift when custom message queue channels are refreshed and it takes fraction of a second for the connections to shift.

Thus the method may be implemented such that application clients fetch messages not from the real physical queue but from an alias name mapped to the real queue. Additionally the method may be utilized to implement a production application maintenance strategy to achieve high availability for applications servicing messages from a queue. This strategy works by switching application sets listening to a particular queue and servicing requests to a different set of applications with minimal or no outage.

There is generally an outage if a system switches between applications listening getting and servicing requests from a particular queue. The activation deactivation process of an application set usually takes a few minutes thus creating an outage. This process is also error prone since it is handled at the client level. Utilizing the method dependencies at a client level are completely removed and it is a single channel bounce that triggers the switch. This process ensures that switching between two sets of applications is seamless.

The method may function to implement an effective strategy where aliases which are logical names are mapped to actual queues.

More illustrative information will now be set forth regarding various optional architectures and uses in which the foregoing method may or may not be implemented per the desires of the user. It should be strongly noted that the following information is set forth for illustrative purposes and should not be construed as limiting in any manner. Any of the following features may be optionally incorporated with or without the exclusion of other features described.

As shown in scenario A a primary application programming interface API is UP with MDB message driven bean . The primary API is listening to primary alias queues . The primary alias queues are aliases pointing to real queues.

In this example a maintenance API is brought up with MDB listening to a maintenance alias queue which is pointing to dummy queues .

As shown in scenario B the aliases are switched verified and a SVRCONN channel is restarted to refresh connections at QMGR where nothing changes at the WL. Additionally the maintenance API is activated.

The primary API and the maintenance API are identical application sets and each set connects to a different alias queue to get messages. The aliases are swapped from a dummy queue to a real queue as a target to fetch GET messages. The switch is seamless using the techniques described.

Fast on demand switching of application sets servicing a particular kind of request may be performed based on the incoming request volume. Scaling and de scaling of an application can be done in a fraction of a second bringing in virtues of flexibility optimized usage of resources and reduced cost of operation.

With reference to and as an example implementation there may be APIs that are listening to actual physical queues servicing Add and Multiply API service calls.

As shown in example A APP 1 is currently servicing an Add API Operation Queue requests through logical queue APP1 Alias Q . APP 2 is also servicing Add API Operation Queue requests through logical queue APP2 Alias Q . Further APP 3 is servicing Multiply API Queue requests through logical queue APP3 Alias Q .

During the peak hours Multiply Operation API Queue may be getting more requests and Add Operation API Queue may not be getting many requests. Thus it may be decided to adjust to the requirement with the same resources with the options that the techniques described herein provide.

Thus as shown in example B the alias logical name may be switched from where the APP 1 is fetching messages and mapped to Multiply Operation Queue . This takes effect by refreshing connection channels within a fraction of a second.

Accordingly lesser application resources may be flexibly managed to adjust to fluctuating demand or even schedule requests in batches to optimize hardware software usage.

Coupled to the network is a plurality of devices. For example a server computer and an end user computer may be coupled to the network for communication purposes. Such end user computer may include a desktop computer tap top computer and or any other type of logic. Still yet various other devices may be coupled to the network including a personal digital assistant PDA device a mobile phone device a television etc.

As shown a system is provided including at least one central processor which is connected to a communication bus . The system also includes main memory e.g. random access memory RAM etc. . The system also includes a graphics processor and a display .

The system may also include a secondary storage . The secondary storage includes for example a hard disk drive and or a removable storage drive representing a floppy disk drive a magnetic tape drive a compact disk drive etc. The removable storage drive reads from and or writes to a removable storage unit in a well known manner.

Computer programs or computer control logic algorithms may be stored in the main memory the secondary storage and or any other memory for that matter. Such computer programs when executed enable the system to perform various functions as set forth above for example . Memory storage and or any other storage are possible examples of tangible computer readable media.

While various embodiments have been described above it should be understood that they have been presented by way of example only and not limitation. Titus the breadth and scope of a preferred embodiment should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

