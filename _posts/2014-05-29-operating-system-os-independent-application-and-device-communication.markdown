---

title: Operating system (OS) independent application and device communication
abstract: An Inter-Process Communication (IPC) message transport mechanism is provided with an Application Programming Interface (API). Applications use the API to create and register clients, and device drivers for devices use the API to create and register services. The applications and device drivers use their own independent API to pass commands and responses to one another using the clients and services. An IPC message transport manager manages and routes the commands as messages without any restrictions on the format or content of the messages. The messages routed in an OS independent fashion.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09098362&OS=09098362&RS=09098362
owner: NCR Corporation
number: 09098362
owner_city: Duluth
owner_country: US
publication_date: 20140529
---
Enterprises often deploy a variety of devices and applications within their processing environments. Generally each business vertical has to support some form of an industry standard Application Programming Interface API at a business s application level e.g. financial solutions often support CEN XFS eXtensions for Financial Services and retail solutions support OPOS Object Linking and Embedding OLE for retail POS etc. . In order for applications to share device hardware with device driver implementations a custom and proprietary interface is required.

As a result when new device hardware is introduced updates to existing device hardware is made or existing device hardware is needed in a new OS platform businesses have to wait on support from their industry standard APIs or have to custom code individual applications to provide support. This creates time lags waiting on support and is not conducive to code reuse and portability.

Even though the third party APIs were meant to create better integration for applications since they are so tightly coupled to the underlying devices in which they support and the OSs on which they run the applications are still tightly coupled to their OS environments and environmental configurations. Moreover applications from different configurations or different business units that want to access devices used by other business units require substantial modification to achieve such access.

Moreover third party APIs are OS specific which means different OSs require different modifications for any third party API to work properly and some APIs may not even support a desired OS of an enterprise. Still further even when a third party API has versions of that API for multiple OSs each such version may have different commands or different features from the other versions. This means that trying to allow an application using a first OS having a first API supported by the first OS to access a device available from a second OS have a second API supported by the second OS is not seamless and requires a lot of programming rework and integration. So device sharing across OS environments is uncommon in the industry.

In various embodiments methods and a Self Service Terminal SST for Operating System OS independent application and device communication are presented.

According to an embodiment a method providing an OS independent application and device communication is presented. An Application Programming Interface API is provided to a client application and a device driver. Next objects are instantiated and registered through the API that permit the client application and the device driver to communicate with one another through messages in formats defined by the client application and the device driver wherein the messages are relayed and managed independent of a specific Operating System OS .

Before beginning the discussion of the ATM some terms are introduced and defined that may be used throughout this document.

A device driver is a driver that provides an interface to one or more peripheral devices. The device drivers discussed herein also expose the functionality of the underlying peripheral devices in a normalized interface communicated to applications which operate within an application layer of the OS. The device driver operates within a different processing context within the OS than the applications may also be referred to herein as client applications .

As used herein and below a peripheral device can be a physical device a virtual device being a logical representation of a peripheral device or a compound peripheral device a peripheral device that supports two or more discrete logical device functional operations that have been made independent because of design choice such as shared Input Output I O connection or shared transport mechanism .

A post office is the interface between the applications and the drivers. The post office acts as an Inter Process Communication IPC transport through an API to pass messages and events between post office clients and post office services. The post office also maintains address mappings between post office clients and post office services and registers post office clients and post office services. The post office is not dependent on any specific format of the messages used between the post office clients and the post office services. In this way the post office is API agnostic and OS agnostic because it serves as an IPC transport between different independent OS processing contexts between the post office clients and the post office services.

A post office client is created by client applications including third party APIs platforms and management systems through the post office API and registered with the post office for sending messages receiving replies from post office services and receiving events from the post office services.

A post office service is created by device drivers through the post office API and registered with the post office for receiving messages from post office clients sending replies to messages and sending events.

 Business layer software refers to the applications third party APIs platforms and or management systems processing context and application layer within the OS which sits above the OS layer software where the device driver is processed.

The ATM includes and is logically segmented into business layer software and OS layer software . The business layer software includes a variety of transaction applications A business or client applications relevant to transactions on the ATM a management system on box of off box A for management operations of the ATM third party APIs Platforms A such as XFS OPOS JAVAPOS and all the flavors or personalities associated with modifications customizations to these third party APIs Platforms A .

The OS layer software includes a post office that can also operate within the business layer software environment to communication with the business layer software acting as an IPC transport layer . Similarly the OS layer software includes one or more device drivers A and one or more post office services B.

During operation of the ATM the business layer software A A and A make requests for access to the peripheral devices card reader value media dispenser receipt printer etc. . The transaction applications A may be coded to communicate with the third party APIs Platforms A XFS OPOS JAVAPOS or personalities thereof to make such requests of the peripheral devices . The third party APIs Platforms A.

With the teachings herein modification of communication between the client applications A A and A are modified to achieve the described novel and new beneficial teachings to achieve OS independent application to device communications through the post office and its post office clients B and B and its post office services B.

As stated before the post office is a collection of software services that is accessed and interacted with through a post office API. The post office allows device drivers A to offer functionality known for the peripheral devices to the client applications A A and A while at the same time the post office remains conceptually and logically separated from the normalized interface or device driver and client application API used by the device drivers A and the client applications A A and A to communicate with one another. That is the post office is not dependent on and is agnostic to the format of the normalized interfaced used between the client applications A A and A and the device drivers A.

The device drivers A use the post office API to create and register post office services B. This allows the post office clients B and B to detect the presence of the device drivers A and provides a generic IPC cross OS processing contexts mechanism for communication with one another through the post office . Device drivers A register when they want to expose functionality of the peripheral devices that they support to the post office clients B and B . The post office services B provides the mechanism by which the device drivers A obtain post office client request messages and send appropriate response messages as obtained by the device drivers A interacting with their peripheral devices . The post office services B also provides the mechanism by which the device drivers A send asynchronous even messages to a specific post office client B or B and the mechanism by which the device drivers A broadcast asynchronous event messages to monitoring or subscribing post office clients B and B .

The post office provides an IPC transport mechanism for different OS processing contexts business layer software and OS layer software . So client users of the post office do not have to be in the same OS process in order for them to send messages to one another. Thus by using the post office device drivers A can reside in a different OS processing context from the client applications A A and A .

The post office is a transport layer achieved via the post office API for facilitating the passing of message data between the device drivers A and the client applications A A and A thus the post office does not impose or expect the messages that pass through to be in any particular format. So the post office is message format independent and device driver and client application API independent since it is the device driver and client application API that creates the message in the message format .

There are two types of post office interface modules the post office client B and B and the post office service B 

Logical software components other than a device driver A may also support a post office service B as logical services not shown in the .

Central to the post office is the identification of the post office clients B and B and the post office services B. The post office relies on a post office client B and B to register itself with the post office s client catalog and a post office service B to register itself with the post office s service catalog. Whenever a post office client B or B or post office service B registers with the appropriate post office catalog it will be identified by a numeric value called a system address. A system address is akin to a handle for files and other objects. The post office keeps records of associations between system addresses of post office clients B and B and post office services B. A post office client B or B uses the post office service Catalog to determine what post office services B are available for it to use.

The post office places no restrictions on the message format the size of message that can be sent to from its post office clients B and B and post office services B or the frequency rate or volume that messages are sent by post office clients B and B and post office services B. However it is expected that the size of a message is minimal in nature and consideration is given to the frequency at which messages are issued to and from post office services B. The size of the message can be a configured attribute based on the processing environment.

The messaging passing facilitated by the post office may or may not exist in a same thread or process. There are two types of messages used a two message sequence and a one message sequence.

In a two message sequence a post office client B or B originated from client application A A and A sends a request message to a post office service B and the post office service B responds by sending a response message to the post office client B or B . The format of both a request message and response message is pre defined by the writer of the service not the post office . The post office client B or B can participate in many two message sequences at a time and two message sequences can be interleaved in two ways 

1. The post office client B and B can send a request message to a particular post office service B before collecting the response message associated with a previous request message from that service. Note that the outstanding response message may or may not have been already sent by the post office service B.

2. Before collecting the response message associated with a request message it sent to a post office service B the post office client B or B can send a request message to another post office service B.

A one message sequence can occur between a post office service B and a post office client B or B . In an embodiment the post office supports two types of one message sequence 

1. Event Message. This message occurs between a post office service B and a post office client B or B when the post office service B sends an event message to the post office client B or B .

2. Broadcast Message. This message occurs between a post office service B and post office client B or B monitors when the service sends a broadcast message.

By default messages are received by post office client B and B in the chronological order that they have been sent. However if a post office client B or B chooses to it can request to receive a particular post office service B response message. In this case other messages received before the post office client B or B specified message will be queued within the post office for the post office client B or B to receive later.

As discussed when a message is sent by a post office client B or B or a post office service B it is queued within the post office . The number of messages that can be queued by the post office at any point in time is configurable but due to resource requirements there is a maximum limit. A message will be kept on a queue within the post office for a configurable period of time. If no post office client B or B or post office service B picks up the message during this period then the message will be deleted from the queue.

The post office does not define or impose the format of the messages passed between post office clients B and B and post office services B. The post office does not impose a maximum size of message. However the post office does have a finite amount of space to store messages that are being passed through it at any point in time messages that are to be routed to the appropriate post office clients B and B and post office services B. When a post office client B or B or post office service B sends a message and there is no space available within the post office to handle the message the post office will scan the current message queue. If the post office finds any message on the queue that has not been picked up within a configurable period of time then the message will be removed from the queue. After purging any time lapsed messages if there is still no space available for passing the message to be sent then the post office client B or B or post office service B will be informed of this with an out of memory condition.

During operation of the ATM the client applications A A and A detect the presence of peripherals through the device drivers A through the IPC transport message passing of the post office utilizing the post office services B and the post office clients B and B . The format of the messages and the API used between the client applications A A and A and the device driver A are irrelevant to and no restrictions are enforced on these items by the post office . The post office API used by the client applications A A and A and the device drivers A permits the creation or and registration of the post office clients B and B and the post office services B. This IPC message passing mechanism between applications and device drivers permits OS independent and application to device API independence meaning the applications and devices are free to use existing APIs to communicate as they normally would with one another.

In an embodiment the messaging transport configurer presents and processes the post office API discussed above with reference to the .

In an embodiment the messaging transport configurer produces at least one instance of a post office client B and or B and at least one instance of a post office service B on a host machine that is the ATM .

In an embodiment the messaging transport configurer produces at least one instance of a post office client B and or B and at least one instance of a post office service B on a host machine that is a Self Service Terminal SST .

In an embodiment the messaging transport configurer produces at least one instance of a post office client B and or B and at least one instance of a post office service B on a host machine that is a kiosk.

At the messaging transport configurer receives objects instantiated through the API that permit the client application and the device driver to communicate with one another through messages in formats defined by the client application and the device driver. The messages relayed and managed in an OS independent manner.

According to an embodiment at the messaging transport configurer registers a client object instantiated by the client application.

In an embodiment the client object is an instance of the post office client B and or B of the created by the client application using the post office API.

In an embodiment of and at the messaging transport configurer registers a service object instantiated by the device driver.

In an embodiment the service object is an instance of the post office service B of the created by the device driver A using the post office API.

In an embodiment of and at the messaging transport configurer publishes the service object as being available to the client object this is done through message passing as discussed above with reference to the .

In an embodiment of and at the messaging transport configurer receives an indication from the client object to communicate with the service object.

In another embodiment of and at the messaging transport configurer receives an indication from the client object to register for events published by the service object.

In an embodiment of and at the messaging transport configurer receives another indication from the client object to register for broadcast events broadcasted by the service object.

In an embodiment at the messaging transport configurer manages messages between the object by mapping each message to an address to which that message is being sent. The address is outside an OS processing context from where the message originated.

In an embodiment at the messaging transport configurer queues a number of the messages for the object to pick up. The messages are maintained in a memory buffer until picked up.

In an embodiment the IPC transport manager is partially configured for operation by the message transport configurer of the .

In an embodiment the IPC transport manager is the post office and any created instances of the post office clients B and B and the post office services B of the .

At the IPC transport manager receives on a host device that executes the IPC transport manager a service message exposing functionality of a peripheral device from a service object that is registered by a device driver.

At the IPC transport manager resolves an address a client object registered by a client application based on the service message received from the service object.

At the IPC transport manager relays the service message to the client object for delivery to the client application.

According to an embodiment at the IPC transport manager receives a second message from the client object which was initiated by the client application the second message requests a service function associated with the exposed functionality.

In an embodiment of and at the IPC transport manager resolves a second address for the service object based on the client object and the second message.

In an embodiment of and at the IPC transport manager relays the second message the service object for delivery to the device driver and processing on the peripheral device.

In an embodiment of and at the IPC transport manager receives a third message from the service object for a response made to the second message by the device driver.

In an embodiment of and at the IPC transport manager resolve the address a second time for the client object.

In an embodiment of and at the IPC transport manager relays the third message to the client object for delivery to the client application.

It is noted that one client application and device driver having one client object and one service object has been illustrated for purposes of comprehension but that there can be multiple different ones of these all operating simultaneously and handled by the IPC transport manager within a single processing environment.

The IPC message transport manager is configured and adapted to execute on the processor within its own independent processing context within an OS for the SST and relay messages between client applications and device drivers for peripherals of the SST . The message relaying is achieved without imposing any restrictions on the format of the messages and passing the messages in an OS independent manner.

According to an embodiment the IPC message transport manager is further configured and adapted to register client objects for the client application and service objects for the device drivers.

In an embodiment the IPC message transport manager is further adapted and configured to maintain address mappings between the registered client objects and service objects.

In an embodiment the IPC message transport manager is further and adapted to provide an API to the client applications and the device drivers to create and register client objects and service objects that perform the relays of the messages on behalf of the client applications and the device drivers.

One now fully appreciates how an IPC message transport between applications and devices can be configured and created to provide OS independent and API independence. This permits for improved reuse of devices by applications independent of third party APIs and OSs.

It should be appreciated that where software is described in a particular form such as a component or module this is merely to aid understanding and is not intended to limit how software that implements those functions may be architected or structured. For example modules are illustrated as separate modules but may be implemented as homogenous code as individual components some but not all of these modules may be combined or the functions may be implemented in software structured in any other convenient manner.

Furthermore although the software modules are illustrated as executing on one piece of hardware the software may be distributed over multiple processors or in any other convenient manner.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

