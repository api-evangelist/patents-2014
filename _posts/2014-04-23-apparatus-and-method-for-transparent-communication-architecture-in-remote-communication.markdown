---

title: Apparatus and method for transparent communication architecture in remote communication
abstract: A communication apparatus for remote communication may include a local communication proxy module configured to receive streams from a local communication application module. The streams may be in a form utilizing a first transmission protocol and destined to a remote destination. The local communication proxy module may be configured to facilitate sending, utilizing a second transmission protocol, the streams in real-time over a network to a remote communication proxy module. The local communication proxy module may be configured to conceal characteristics of the network from the local communication application module. The local communication proxy module may also be configured to be transparent to the local communication application module. A machine-readable medium and a method are also disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09325764&OS=09325764&RS=09325764
owner: Wyse Technology L.L.C.
number: 09325764
owner_city: San Jose
owner_country: US
publication_date: 20140423
---
The present application is a continuation application of U.S. patent application Ser. No. 12 484 126 filed Jun. 12 2009 now U.S. Pat. No. 8 775 658 which claims the benefit of priority under 35 U.S.C. 119 from U.S. Provisional Patent Application Ser. No. 61 164 376 entitled RELIABLE IN ORDER NETWORK PROTOCOL TO ACCELERATE REAL TIME APPLICATIONS THROUGH USE OF A TRANSPARENT PROXY ARCHITECTURE filed on Mar. 27 2009 which are hereby incorporated by reference in its entirety for all purposes.

The transmission control protocol TCP is the standard communications protocol for the internet and virtually all internet traffic is TCP based. In networks that have high latency and or packet loss TCP exhibits poor bandwidth utilization. When based on TCP real time applications therefore become progressively less usable as latency and or packet loss increases. For example the delay between a computer in the United Stated and another in India is approximately 250 milliseconds and at this latency real time applications are essentially unusable on TCP.

In one aspect of the disclosure a communication apparatus for remote communication may include a local transparent communication proxy module configured to intercept a first stream destined to a remote destination and configured to make a first determination whether to accelerate communication associated with the first stream. The communication apparatus may include a local communication proxy module configured to receive the first stream based on the first determination and configured to make a second determination whether a connection to a remote communication proxy module is established. If the connection is established then the local communication proxy module may receive one or more additional streams and may direct the one or more additional streams to the remote communication proxy module utilizing an accelerated mode. If the connection is not established then the local transparent communication proxy module may direct the first stream to the remote destination utilizing a non accelerated mode.

In another aspect of the disclosure a communication apparatus for remote communication may include a first local module configured to intercept a first stream. The first stream may utilize a first transmission protocol and may be destined to a remote destination over a network. The first local module may be configured to make a determination whether to direct the first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol. The determination may be based on one or more of the following factors a configuration or a network condition. The first local module may be also configured to direct the first stream to the first destination or the second destination based on the determination. The second transmission protocol is different from the first transmission protocol.

In another aspect of the disclosure a communication apparatus for remote communication may include a local communication proxy module configured to receive streams from a local communication application module. The streams may be in a form utilizing a first transmission protocol and destined to a remote destination. The local communication proxy module may be configured to facilitate sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module. The local communication proxy module may be also configured to adjust an amount of bandwidth used by the streams.

In another aspect of the disclosure a communication apparatus for remote communication may include a local communication proxy module configured to receive streams from a local communication application module. The streams may be in a form utilizing a first transmission protocol and destined to a remote destination. The local communication proxy module may be configured to facilitate sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module. The local communication proxy module may be configured to conceal characteristics of the network from the local communication application module. The local communication proxy module may also be configured to be transparent to the local communication application module.

In yet another aspect of the disclosure a communication apparatus for remote communication may include a local communication proxy module configured to receive streams from a local communication application module. The streams may be in a form utilizing a first transmission protocol and destined to a remote destination. The local communication proxy module may be configured to add first header information including one or more of the following a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier. The local communication proxy module may be configured to add second header information. The local communication proxy module may be also configured to form packets and to facilitate sending utilizing a second transmission protocol the packets in real time over a network to a remote communication proxy module.

It is understood that other configurations of the subject technology will become readily apparent to those skilled in the art from the following detailed description wherein various configurations of the subject technology are shown and described by way of illustration. As will be realized the subject technology is capable of other and different configurations and its several details are capable of modification in various other respects all without departing from the scope of the subject technology. Accordingly the drawings and detailed description are to be regarded as illustrative in nature and not as restrictive.

The detailed description set forth below is intended as a description of various configurations of the subject technology and is not intended to represent the only configurations in which the subject technology may be practiced. The appended drawings are incorporated herein and constitute a part of the detailed description. The detailed description includes specific details for the purpose of providing a thorough understanding of the subject technology. However it will be apparent to those skilled in the art that the subject technology may be practiced without these specific details. In some instances well known structures and components are shown in block diagram form in order to avoid obscuring the concepts of the subject technology. Like components are labeled with identical element numbers for ease of understanding.

In accordance with one aspect of the subject technology a novel communication protocol sometimes referred to as an accelerated protocol or UDP can overcome the problems inherent in the transmission control protocol TCP and exhibit maximum bandwidth utilization for networks utilizing TCP. As a result real time applications are usable even at delays exceeding 250 ms in the presence of packet loss.

Microsoft s Remote Desktop Protocol RDP uses TCP. If a user in the United States connects remotely to a server in India over Microsoft s RDP the user may find that the session is almost unusable. Irrespective of the amount of bandwidth available TCP may use only a small portion of it with the result that the session is extremely sluggish and simple mouse clicks can take several seconds to effect a response from the server. However in accordance with one aspect of the disclosure when using an accelerated protocol of the subject technology a session can use as much of the available bandwidth as possible or specified and the experience can be much closer to the experience the user would have if he she were using the application locally.

Various communication approaches are described below but these are inferior to the communication systems and methods of the subject technology.

In one aspect of the disclosure the subject technology does not have the constraints imposed by the other approaches described above.

In one aspect of the disclosure the subject technology is for example essentially software only and application agnostic. In one aspect any TCP stream can theoretically be accelerated by an accelerated protocol of the subject technology and is independent of layer 6 and above e.g. independent of layers 6 and 7 which are the presentation layer and application layer in the OSI model.

In one aspect of the disclosure the subject technology is able to achieve application transparency through the use of for example proxies. In one aspect the subject technology can achieve transfer of streams across Long Fat Networks for a real time application without invoking the transfer within the application.

A bandwidth delay product BDP may refer to the product of a data link s capacity in bits per second and its end to end delay in seconds . The result an amount of data measured in bits or bytes is equivalent to the maximum amount of data on the air at any given time i.e. data that has been transmitted but not yet received. Sometimes it is calculated as the data link s capacity times its round trip time RTT . A network with a large bandwidth delay product is commonly known as a Long Fat Network LFN . As described in RFC 1072 which is incorporated herein by reference a network may be considered an LFN if its bandwidth delay product is significantly larger than 105 bits about 12 kB .

According to another approach techniques such as packet coalescing compression caching and flow control optimization may be utilized in wide area network WAN accelerators to improve data transfer over WANs. Some of the shortcomings of these solutions are that they require hardware HW appliances be deployed between end points as opposed to the transparent peer to peer architecture of the subject technology according to one aspect of the disclosure they are optimized for bulk data transfers as opposed to being focused on real time applications they are not as highly optimized to deal with packet loss recovery. According to one aspect the subject technology provides a tight integration between the novel packet loss recovery error correction and congestion control techniques.

In accordance with various aspects of the disclosure examples of advantages and benefits of the subject technology are provided below.

In one aspect a communication apparatus of the subject technology can accelerate any stream e.g. any TCP stream to use maximum bandwidth for the current latency and packet loss conditions with particular emphasis on optimizing for real time applications.

In one aspect a communication apparatus of the subject technology can dynamically adjust itself to changing latency and packet loss conditions to maintain optimal usage of bandwidth and user experience.

According to one aspect the phrase dynamically adjust may refer to for example making a determination making an adjustment or the like when or as soon as one or more real time conditions are detected or altered or making a determination an adjustment or the like in response to one or more real time conditions. According to one aspect the term real time conditions may refer to for example conditions that exist or occur approximately in real time at the present time or at the current time.

In one aspect an architecture of the subject technology is transparent to applications. For example any application running on supported platforms can have its stream e.g. TCP stream or output sent over an accelerated protocol of the subject technology and this requires no changes to the application source code.

In one aspect a transparent architecture of the subject technology can be leveraged for peer to peer communications even in the presence of firewalls and network address translations NATs with or without.

In accordance with one aspect of the disclosure communication apparatus may include communication apparatus A and communication apparatus B . Communication apparatus A may include communication application module A transparent communication proxy module and communication proxy module A . In another configuration module may be placed outside communication apparatus A . Communication apparatus B may include communication application module B and communication proxy module B .

Communication application module A transparent communication proxy module communication proxy module A communication proxy module B and communication application module B are sometimes referred to as module module module module and module respectively or modules and .

In one configuration communication apparatus A includes two computers A and B e.g. clients where communication application module A and transparent communication proxy module are on computer A and communication proxy module A is on computer B. In another configuration communication apparatus A may include one or more computers and communication application module A transparent communication proxy module and communication proxy module A may be on the same one computer each of the modules can be on a separate computer or some of the modules can be on one computer while the other module s is are on another computer. In one aspect it is advantageous to have both communication application module A and transparent communication proxy module located on a first computer e.g. one client and to have communication proxy module A located on the same first computer or on another computer proximate to the first computer.

In one configuration communication apparatus B includes two computers A and B e.g. servers where communication application module B is on computer A and communication proxy module B is on computer B. In another configuration communication apparatus B may include one or more computers and communication application module B and communication proxy module B may be on the same one computer e.g. one server or each of the modules can be on a separate computer. In one aspect it is advantageous to have both communication application module B and communication proxy module B be located on the same one computer or to have communication application module B on a first computer and communication proxy module B on another computer proximate to the first computer.

In one aspect communication application module A may include one or more applications and communication application module B may include one or more applications. In one aspect the one or more applications on communication application module A may communicate with the one or more applications on communication application module B . An application in module or may be an application of any type. In one aspect each of transparent communication proxy module communication proxy module and communication proxy module may include one or more applications or instructions comprising software code.

In one aspect transparent communication proxy module may monitor outgoing streams from communication application module A . Transparent communication proxy module may intercept a stream e.g. a connection request or a TCP stream from communication application module A via a communication channel e.g. and forward it to communication proxy module A via a communication channel e.g. . Communication proxy module A may take the stream add headers so that it conforms to an accelerated protocol of the subject technology and send it to communication proxy module B over a communication channel utilizing the accelerated protocol of the subject technology. This communication channel may comprise for example communication channel network and communication channel . Communication proxy module B may then take the stream conforming to the accelerated protocol remove the headers and send the stream to communication application module B over a communication channel e.g. . Each of communication channels and may utilize a non accelerated protocol e.g. TCP . In one aspect a stream traveling on channels and may conform to a non accelerated protocol and a stream traveling on channels and and network may conform to an accelerated protocol.

In one aspect of the disclosure communications in an accelerated mode may occur concurrently with communications in a non accelerated mode. For example while one or more applications on module may communicate remotely with one or more applications on module or other module s in an accelerated mode e.g. via communication channels and one or more other applications on module may concurrently communicate with one or more other applications on module or other module s in a non accelerated mode e.g. via a communication channel . In one aspect streams from an application utilizing a non accelerated mode are not intercepted by module .

In one aspect of the disclosure the term stream may generally refer to any transmission incoming or outgoing or any signal s or packet s . In one aspect a stream may be from communication application module A or communication application module B . In another aspect a stream may be a connection request. In yet another aspect a stream may be a network request e.g. a connection request or another type of network request . In yet another aspect a stream may be a data stream e.g. data or packet s . In one aspect a data stream may include data control format information or data as well as control format information. In one aspect a stream may be a TCP stream.

In one aspect of the disclosure communication application modules A and B and e.g. client and server applications may be perceived as communicating as they normally would over a communication channel utilizing a non accelerated protocol e.g. TCP and are not aware of the stream being intercepted. In one aspect each of communication application modules A and B and is not aware of the existence of transparent communication proxy module communication proxy module A and communication proxy module B . In other words the operation and existence of modules and are transparent to modules and and communication can be accelerated without invoking the acceleration within module or . In one aspect this allows an accelerated protocol of the subject technology to be application agnostic. In one aspect this allows transparent communication proxy module communication proxy module A and communication proxy module B to be application agnostic.

In one aspect of the disclosure communication application module A transparent communication proxy module and communication proxy module A are local with respect to one another and remote with respect to each of communication application module B and communication proxy module B . Communication application module B and communication proxy module B are local with respect to each other and remote with respect to each of communication application module A transparent communication proxy module and communication proxy module A .

In one aspect a communication application module e.g. may be configured to connect to one or more other communication application modules e.g. one or more modules at any IP address or any port. In one aspect a transparent communication proxy module may be configured to connect to a communication proxy module at an IP address and a port of the communication proxy module. In one aspect communication proxy module A monitors or listens to streams from transparent communication proxy module at a port which can be a pre determined or pre assigned port or can be assigned to another port at a later time .

In one aspect a computer may be a laptop computer a desktop computer a thin client a client a server a personal data assistant PDA a portable computing device or a suitable device with one or more processors. According to one aspect of the disclosure when a computer is a thin client it may be a device having at least a processor and memory where the total amount of memory of the thin client is less than the total amount of memory in a server e.g. . A thin client may not have a hard disk. In certain configurations a computer may be a telephone a mobile telephone an audio player a game console a camera a camcorder an audio device a video device a multimedia device or a device capable of supporting a connection to another device. A computer can be stationary or mobile.

In one aspect of the disclosure a proxy module e.g. may be a module or a Windows system service and may be implemented as executable software code e.g. Proxy.exe . In another aspect a proxy module may be a module that performs a function or operation on behalf of another module such as module or or may be a module that performs a task in the background. In yet another aspect a proxy module may a module that performs other functions or operations.

In one aspect of the disclosure a delay between a local module and a remote module may exceed 0 ms e.g. 0.5 ms 1 ms 2 ms 5 ms 10 ms 15 ms 20 ms 25 ms 50 ms 100 ms 150 ms 200 ms 250 ms 300 ms 400 ms 500 ms 600 ms or another number larger than 0 ms . For example a delay between communication application module A and communication application module B may exceed 250 ms. A delay between local modules is less than a delay between a local module and a remote module.

In one aspect a communication between a local module and a remote module may experience a packet loss equal to or exceeding 0 e.g. 0.01 0.1 0.3 0.5 0.8 1 2 or another number larger than 0 . For example a communication between communication application module A and communication application module B may have greater than 1 packet loss. A packet loss between local modules is less than a packet loss between a local module and a remote module.

A communication channel formed by communication channel network and communication channel may experience a delay like the delay between a local module and a remote module and a packet loss like the packet loss between a local module and a remote module. Communication channel may experience a delay like the delay between a local module and a remote module and a packet loss like the packet loss between a local module and a remote module. Network may be the internet or another type of network. Network may be an external or internal network.

Each of the components shown in e.g. may be similar to those shown in e.g. except that in this example each of and may be on one or more client computers e.g. thin clients and each of and may be on one or more server computers. Client computers and server computers are sometimes referred to as clients and servers respectively. Client communication application module may include for example the Microsoft Remote Desktop Protocol RDP application and or the Citrix Independent Computing Architecture ICA application. Server communication application module may include for example the Microsoft Remote Desktop Protocol RDP application and or the Citrix Independent Computing Architecture ICA application.

In accordance with one aspect of the disclosure client transparent communication proxy module can intercept an outgoing TCP stream e.g. a connection request from client communication application module on one computer e.g. client computer or client and forward it to client communication proxy module . Client transparent communication proxy module may be located on the client computer itself and client communication proxy module may be located on the client computer or on another computer but preferably on the client computer or on a computer proximate to the client computer . Client communication proxy module may then take the TCP stream and send it to server communication proxy module over a communication channel e.g. communication channel network and communication channel using an accelerated protocol of the subject technology. Server communication proxy module can be running on a server computer itself or on another computer but preferably on the server computer or on a computer proximate to the server computer for optimal performance . Server communication proxy module may then take the TCP stream conforming to the accelerated protocol process it and send the TCP stream to the server communication application module on the server computer over a communication channel e.g. which may utilize TCP .

In one aspect modules and e.g. client and server applications communicate as they normally would over TCP and are not aware of modules and intercepting the data. According to one aspect of the disclosure this allows the protocol of the subject technology to be application agnostic.

In accordance with various aspects of the disclosure a communication apparatus may provide the following functions features 

In accordance with various aspects of the disclosure the features described above are discussed in further detail below while referring to 

In accordance with one aspect of the disclosure an example of an operation of a communication apparatus is described as follows while referring to .

In accordance with one aspect of the disclosure an example of an operation of a communication apparatus is described with reference to .

At block a stream is received. For example transparent communication proxy module intercepts a stream destined to a remote destination e.g. . In one aspect the stream is a connection request. In one aspect transparent communication proxy module may intercept i all streams that are connection requests ii all streams that are certain types of connection requests e.g. connection requests for one or more remote destinations or iii streams that are other network requests e.g. network requests that are not connection requests .

At block a determination or a selection is made as to whether to accelerate or not to accelerate communication associated with the stream. In one aspect the stream is a connection request and the communication associated with the stream may include communication of one or more streams or data streams that follow the connection request. In one aspect the stream is a connection request and the communication associated with the stream may include communication utilizing a connection that is made as a result of the connection request.

In one aspect transparent communication proxy module makes the determination. For example transparent communication proxy module determines whether to direct the stream to the remote destination e.g. through a local communication proxy module e.g. or to direct the stream to the remote destination without utilizing the local communication proxy module.

If a determination is made to accelerate the communication then at block the stream may be directed to a local communication proxy module e.g. . If a determination is made not to accelerate the communication then at block the stream may be directed towards the remote destination e.g. without utilizing the local communication proxy module.

Referring back to block in one aspect module may make a determination based on i a configuration e.g. a user configuration a user input a predetermined setting or a variable setting and or ii one or more network conditions e.g. an amount of packet loss or a round trip time . In one example if a configuration indicates an accelerated mode is selected e.g. module is enabled then module may select the accelerated mode and direct the stream to module and if not then module can select the non accelerated mode and direct the stream to the remote destination without using module . In one example if a network condition is acceptable e.g. the amount of packet loss is below a threshold level or the round trip time is below a threshold level then module may select the non accelerated mode. If not module may select the accelerated mode. In another example module may select the non accelerated mode if a bandwidth which may be another network condition used by streams is below a threshold value. If not module may select the accelerated mode. In one example module may receive the network conditions from module .

In one aspect module may also make a determination based on one or more of the following whether module is running or operational whether module is running or whether a connection between module and module is establishable. If module or module is not running or if the connection is not establishable module may select the non accelerated mode.

In one aspect prior to module making the determination described in the previous paragraph the local communication proxy module may make a determination as to whether a connection between the local communication proxy module e.g. and the remote communication proxy module e.g. is establishable e.g. whether a connection can be successfully established between and or a connection can be successfully established between and utilizing and .

In one example the local communication proxy module may attempt to establish a separate test connection with the remote communication proxy module to test and determine whether a connection between the local communication proxy module and the remote communication proxy module is establishable. Similarly in one example the remote communication proxy module may determine whether a connection between the remote communication proxy module e.g. and the remote destination e.g. is establishable e.g. using another test connection .

If a connection is establishable e.g. the test connection s are successfully established then the successful connection establishability result may be communicated. For example a local communication proxy module e.g. may send a reply message to a transparent communication proxy module e.g. for example in response to a request from the transparent communication proxy module that the connection is establishable so that the stream can be transmitted using the local communication proxy module.

If a connection cannot be successfully made e.g. the test connection s are not successfully established then the failed result may be communicated. For example a local communication proxy module e.g. may send a reply message to a transparent communication proxy module e.g. for example in response to a request from the transparent communication proxy module that the connection cannot be made. In this case the transparent communication proxy module may redirect the stream towards the remote destination without utilizing the local communication proxy module block .

At block the stream is provided to a remote communication proxy module e.g. . For example the local communication proxy module e.g. may facilitate sending the stream or may provide the stream to the remote communication proxy module. The remote communication proxy module may then send the stream to the remote destination.

In one example the stream provided to a remote communication proxy module may include one of the following i a portion of the stream received by the local communication proxy ii information extracted from the stream received by the local communication proxy e.g. the IP address and port of the remote destination or iii the entire stream received by the local communication proxy. Before providing the stream to the remote communication proxy module the local communication proxy module may add various header information described elsewhere in this disclosure.

In one example the local communication proxy module may receive the entire stream from the transparent communication proxy module and the local communication proxy module may then i take a portion of the stream received by the local communication proxy e.g. create a modified version of the stream received by the local communication proxy ii extract certain information from the stream received by the local communication proxy or iii take the entire stream received by the local communication proxy and add the appropriate header information before sending the stream to the remote communication proxy module. In another example the transparent communication proxy module may send to the local communication proxy module i a portion of the stream received by the transparent communication proxy module from a local communication application module e.g. ii information extracted from the stream received by the transparent communication proxy module from the local communication application module iii the entire stream received by the transparent communication proxy module from the local communication application module or iv a modified version of the stream received by the transparent communication proxy module from the local communication application module. In one example a transparent communication proxy module may send to a local communication proxy module the entire stream if the connection is successful with the destination IP address changed from the IP address of the remote application module to the IP address of the local communication proxy module.

At block one or more additional streams may be received. For example one or more subsequent data streams from communication application module A may be forwarded to the local communication proxy module e.g. via communication channel directly without utilizing transparent communication proxy module . In one aspect the port used by communication proxy module for communication channel is different from the port used by communication proxy module for communication channel .

At block the local communication proxy module e.g. may send the one or more additional streams to the remote communication proxy module e.g. . This may occur via a communication channel utilizing an accelerated protocol e.g. via and . At block the remote communication proxy module may send the one or more additional streams to the remote destination e.g. . This may occur via a communication channel utilizing a non accelerated protocol e.g. .

In one aspect once a connection is established transparent communication proxy module is not involved in transfer and or receipt of streams and communication application module A communicates e.g. sends and receives streams directly with communication proxy module A e.g. via communication channel . Streams from communication application module B may be sent to communication application module A through a communication channel which may include for example components and where the communication is accelerated through components and .

In one aspect after the stream e.g. a connection request is directed towards the remote destination without utilizing an accelerated communication channel block the data streams subsequent to the stream for the connection request are also directed towards the remote destination without utilizing an accelerated communication channel. For example subsequent data streams are sent from communication application module A to communication application module through communication channel . According to one example these subsequent data streams are not intercepted by transparent communication proxy module .

In one aspect an independent decision is made for each connection request as to whether to accelerate or not to accelerate communication associated with the connection request. For example after receiving a stream if module receives a subsequent stream which is a new connection request as opposed to a data stream then module determines whether to accelerate or not to accelerate communication associated with the subsequent stream.

If a connection fails or is interrupted during communication whether accelerated or not accelerated then communication application module A may reestablish the connection utilizing for example an RDP or ICA.

It should be noted that the order of operations provided in is an example. The order may be changed and some of the operations may be performed simultaneously in other examples.

A system may be for example a computer with module a computer with modules and a computer with modules and or or a computer with a module and or a module . The system includes a processing system . The processing system is capable of communication with a receiver and a transmitter through a bus or other structures or devices. It should be understood that communication means other than busses can be utilized with the disclosed configurations. The processing system can generate audio video multimedia and or other types of data to be provided to the transmitter for communication. In addition audio video multimedia and or other types of data can be received at the receiver and processed by the processing system .

The processing system may include a general purpose processor or a specific purpose processor for executing instructions and may further include a machine readable medium such as a volatile or non volatile memory for storing data and or instructions for software programs. The instructions which may be stored in a machine readable medium and or may be executed by the processing system to control and manage access to the various networks as well as provide other communication and processing functions. The instructions may also include instructions executed by the processing system for various user interface devices such as a display and a keypad . The processing system may include an input port and an output port . Each of the input port and the output port may include one or more ports. The input port and the output port may be the same port e.g. a bi directional port or may be different ports.

The processing system may be implemented using software hardware or a combination of both. By way of example the processing system may be implemented with one or more processors. A processor may be a general purpose microprocessor a microcontroller a Digital Signal Processor DSP an Application Specific Integrated Circuit ASIC a Field Programmable Gate Anay FPGA a Programmable Logic Device PLD a controller a state machine gated logic discrete hardware components or any other suitable device that can perform calculations or other manipulations of information.

A machine readable medium can be one or more machine readable media. Software shall be construed broadly to mean instructions data or any combination thereof whether referred to as software firmware middleware microcode hardware description language or otherwise. Instructions may include code e.g. in source code format binary code format executable code format or any other suitable format of code .

Machine readable media e.g. may include storage integrated into a processing system such as might be the case with an ASIC. Machine readable media e.g. may also include storage external to a processing system such as a Random Access Memory RAM a flash memory a Read Only Memory ROM a Programmable Read Only Memory PROM an Erasable PROM EPROM registers a hard disk a removable disk a CD ROM a DVD or any other suitable storage device. Those skilled in the art will recognize how best to implement the described functionality for the processing system . According to one aspect of the disclosure a machine readable medium is a computer readable medium encoded or stored with instructions and is a computing element which defines structural and functional interrelationships between the instructions and the rest of the system which permit the instructions functionality to be realized. Instructions may be executable for example by a computer or by a processing system of a computer. Instructions can be for example a computer program including code.

An interface may be any type of interface and may reside between any of the components shown in . An interface may also be for example an interface to the outside world e.g. an Internet network interface . A transceiver block may represent one or more transceivers and each transceiver may include a receiver and a transmitter . A functionality implemented in a processing system may be implemented in a portion of a receiver a portion of a transmitter a portion of a machine readable medium a portion of a display a portion of a keypad or a portion of an interface and vice versa.

According to one aspect of the disclosure communication proxy modules e.g. in can provide a consistent user experience on remote data communication sessions e.g. RDP ICA regardless of the round trip delay between its originating device and a remote destination device e.g. a client and a session server modules and in . In other words for a given bandwidth an accelerated session e.g. an accelerated RDPIICA session between a client and its remote destination device e.g. a server located at some arbitrary distance from the client feels like a local experience e.g. feels as if the remote destination device is local to the client .

Referring back to transparent communication proxy module communication proxy module A and communication proxy module B are described in further detail below.

When a connection request is made e.g. when an RDP connection request is initiated from communication application module A transparent communication proxy module which may be inserted at a layer below layer 6 in the OSI model e.g. in the networking stack layer 3 may intercept this outgoing connection establishment request and send the request to the address of communication proxy module A .

Communication proxy module A which is a software application in one example running as a service may monitor or listen on a port to accept incoming socket connections from communication application module A . This port may be a pre assigned port or may be configured to a different port at a later time. Once a connection request is received communication proxy module A may establish an accelerated connection e.g. and with communication proxy module B and then transfer streams e.g. data streams between communication application module A and communication proxy module B over the communication channel e.g. and utilizing an accelerated protocol.

Communication proxy module B which is a software application in one example running as a service may receive all incoming streams e.g. data streams conforming to an accelerated protocol from communication proxy module A and forward them to a destination e.g. communication application module B . Communication proxy module B may also receive streams from communication application module B and transfer them to communication proxy module A .

According to one aspect of the disclosure an example of an operation of a communication apparatus is illustrated below as a process flow while referring to .

In one configuration a graphical user interface GUI is not provided in another configuration a GUI is provided. In one aspect users administrators can configure the acceleration parameters in registry keys and can enable disable the acceleration by accelerator modules using for example the Windows Services menu e.g. services.msc .

In one aspect the accelerator modules may include communication proxy module A and communication proxy module B . In another aspect the accelerator modules may include transparent communication proxy module communication proxy module A and communication proxy module B .

In one example the following registry keys are available e.g. at HKEY LOCAL MACHINE Software WYSE Accelerator Product Settings 

In one example the following registry keys are available e.g. at HKEY LOCAL MACHINE Software Wyse Accelerator Product 

In the above two examples while the accelerator modules refer to accelerator modules and in an alternate configuration the accelerator modules may further include module . Accordingly in the above two example the phrase accelerator modules and may be replaced with the phrase accelerator modules and in an alternate configuration.

According to various aspects of the disclosure a number of different exemplary scenarios are presented in Table 1 below while still referring to .

In accordance with one aspect of the disclosure Event 2 described in Table 1 is described in further detail with reference to . In this example communication apparatus B includes multiple communication application modules and multiple communication proxy modules. In communication application modules B and are connected to communication proxy modules B and respectively via communication channels and respectively. Communication proxy modules B and may use separate communication channels and respectively to communicate with communication proxy module A . Thus each of communication proxy modules B and may utilize its respective port to communicate with communication proxy module A . While two communication application modules and two communication proxy modules are shown the subject technology is not limited to these and may include any number of communication application modules and any number of corresponding communication proxy modules.

In accordance with another aspect of the disclosure Event 2 described in Table 1 is described in further detail with reference to . In this example communication apparatus B includes multiple communication application modules and a single communication proxy module. In communication application modules B and are connected to communication proxy module B via communication channels and respectively. Communication proxy module B may use separate communication channels and respectively to communicate with communication proxy module A . Channel may be for streams from to module and channel may be for streams from to module . Thus communication proxy module B may utilize separate ports to communicate with modules and and separate ports to communicate with communication proxy module A . While two communication application modules and a single communication proxy module are shown the subject technology is not limited to these and may include any number of communication application modules and any number of communication proxy modules.

In accordance with one aspect of the disclosure Event 3 described in Table 1 is described in further detail with reference to . In this example communication apparatus A includes multiple communication application modules multiple transparent communication proxy modules and multiple communication proxy modules. In communication application modules A and are connected to communication proxy modules A and respectively via communication channels and respectively via transparent communication proxy modules and respectively via communication channels and respectively and also via communication channels and respectively. Communication proxy modules A and may use separate communication channels and respectively to communicate with communication proxy module B or and respectively in another configuration . Thus each of communication proxy modules A and may utilize its respective port to communicate with communication proxy module B or and . While two communication application modules two transparent communication proxy modules and two communication proxy modules are shown the subject technology is not limited to these and may include any number of communication application modules any number of corresponding transparent communication proxy modules and any number of corresponding communication proxy modules.

In accordance with one aspect of the disclosure Event 3 described in Table 1 is described in further detail with reference to . In this example communication apparatus A includes multiple communication application modules multiple transparent communication proxy modules and a single communication proxy module. In communication application modules A and are connected to communication proxy module A via communication channels and respectively via transparent communication proxy modules and respectively via communication channels and respectively and also via communication channels and respectively. Communication proxy module A may use separate communication channels and respectively to communicate with communication proxy module B or and respectively in another configuration . Thus communication proxy module A may utilize two separate ports to communicate with communication proxy module B or and . While two communication application modules two transparent communication proxy modules and one communication proxy module are shown the subject technology is not limited to these and may include any number of communication application modules any number of corresponding transparent communication proxy modules and any number of communication proxy modules.

Referring to in one aspect of the disclosure if there are many local clients receiving the same data from a remote location e.g. a single video from module that is being viewed by multiple modules and then i that data can be sent just once from the remote location to at least one of the communication proxy modules on the client side e.g. at least one of modules or in or module in ii if there are multiple communication proxy modules e.g. modules and as shown in the communication proxy modules can obtain the data from each other and iii the communication proxy module s can send that data to the communication application modules e.g. modules and . In another example instead of using at least one of the communication proxy modules an intermediary location that is not a communication proxy module can be used.

Similarly in one aspect of the disclosure if there are many local servers receiving the same data from a remote location e.g. data from module that is being viewed by multiple modules and then i that data can be sent just once from the remote location to at least one of the communication proxy modules on the server side e.g. at least one of modules or in or module in ii if there are multiple communication proxy modules e.g. modules and as shown in the communication proxy modules can obtain the data from each other and iii the communication proxy module s can send that data on to the communication application modules e.g. modules and . In another example instead of using at least one of the communication proxy modules an intermediary location that is not a communication proxy module can be used.

Referring back to exemplary operating systems that are compatible with a communication apparatus e.g. one or more computers in apparatus and or apparatus include but are not limited to various versions and flavors of Windows Vista Windows XP Windows 2000 Server Windows Server 2003 Windows NT Windows Me Windows 98 Windows CEO Windows XPe PocketPC Unix systems Wyse Thin Operating System OS and GNU Linux .

According to one aspect of the disclosure one or more computers in communication apparatus A may utilize for example any one of the following operating systems a version of Wyse Thin OS Linux Windows CEO including Windows CEO 5.0 and Windows CEO 6.0 Windows XP Windows XPe or any other operating system. One or more computers in communication apparatus A may use different classes of thin computing platforms such as platforms that differ in their levels of scalability flexibility and expense. In another aspect one or more computers in apparatus may utilize any one or more of the operating systems described in the previous paragraph.

According to one aspect of the disclosure one or more computers in communication apparatus B may utilize for example any one of the following operating systems a version of Windows XP including Windows XPe with SP2 and Windows XP Professional with SP2 Windows Server 2003 including Windows Server 2003 Standard Edition with SP1 or any other operating system. One or more computers in communication apparatus B may run any one or more of the following Microsoft Terminal Services Citrix Presentation server or Windows XP . In one example multiple sessions may not be supported natively in Windows XP .

According to one aspect of the disclosure a reliable UDP based protocol is provided with congestion control one that maximizes bandwidth usage over networks with high latencies which contains TCP like reliability and in order delivery.

In one aspect when a network becomes congested e.g. an increase in packet loss and or an increase in round trip time RTT a configuration of the subject technology may adjust the bandwidth usage by decreasing the transfer rate of the streams and or optimizing a window size of the packets.

In one aspect of the disclosure communication application module B e.g. a session server is housed proximate to communication proxy module B so that the network delay between them is low e.g. approximately 0 ms . Similarly communication proxy module A may be placed near communication application module A so that the delay between them is also low e.g. approximately 0 ms . In one aspect it is advantage to place transparent communication proxy module on the same computer as communication application module A . The delay between communication proxy modules and is large. In one example the delay between communication proxy modules and may be similar to the delay experienced by a Long Fat Network LFN i.e. a network with high bandwidth delay product BDP . According to one aspect of the disclosure modules and can perform well when the delay between modules and or the delay between modules and is approximately 250 ms and packet loss over the communication channel is about 0.5 .

According to one aspect of the disclosure an example of an operation of a communication apparatus is illustrated below as a process flow while referring to

In accordance with one aspect of the disclosure communication of streams e.g. data streams in communication apparatus of is described particularly in connection with a forward error correction FEC scheme.

In one aspect if communication proxy module B s send window is not full communication proxy module B may request for more data e.g. by calling a routine such as the Windows Sockets Application Programming Interface winsock call recv and receive one or more data streams e.g. RDP data from communication application module B e.g. a session server . This can take advantage of any inherent bandwidth adaptive features of module . The send window size may be dynamic changing to adapt to various parameters such as network speed and congestion. A scheme same as the scheme described above can be applied to communication proxy module A and communication application module A .

Due to high delay in sending data streams and consequently high round trip time RTT between modules and or between modules and some forward error correction FEC scheme is implemented. This reduces the amount of data streams that needs to be resent from module or . The FEC scheme employed can be an algorithm involving XOR operation on the data packets or may employ other FEC schemes known in the art.

According to one aspect of the disclosure an example of a communication operation utilizing an FEC scheme with XOR is presented below as a process flow while referring to 

After step 8 described above the sender e.g. module has the data streams received over a communication channel utilizing an accelerated protocol. In one aspect an accelerated protocol may have features such as reliability in order delivery and congestion control. An accelerated protocol may also make an efficient use of the network bandwidth.

According to one aspect of the disclosure an example of a communication operation utilizing a handshake is presented below as a process flow while referring to . In one aspect a connection between a sender e.g. module and a receiver e.g. module may be set up as follows 

In one aspect hole punching is a method for establishing bidirectional UDP connections between Internet hosts in networks using network address translation NAT . For example assume A and Bare the two hosts each in its own private network N1 and N2 are the two NAT devices and S is a public server with a well known globally reachable IP address. A and B each can begin a UDP conversation with S and the NAT devices N1 and N2 create UDP translation states and assign temporary external port numbers. Scan then relay these port numbers back to A and B. A and B can contact each others NAT devices directly on the translated ports and the NAT devices can use the previously created translation states and send the packets to A and B.

According to another aspect of the disclosure an example of a communication operation utilizing a handshake is presented below while referring to . In one aspect an example of an implementation of handshake may be described as follows.

According to one aspect of the disclosure the receiver and sender e.g. modules and can continue to send these hole punching packets until both ends receive these packets. In one aspect to check for this condition a reserved portion of a packet can be used as follow initially all the bits are set to zero and say 4th bit is the receiver s receive bit and 0bit is sender s receive bit. Whenever the sender e.g. module receives data from the receiver e.g. module the sender can make 0bit as 1 and send it to the receiver. When the receiver receives data the receiver can make its bit as 1. Once the receiver receives 0bit as 1 the receiver can connect to a destination module e.g. module a TCP server and when the sender receives 4th bit as 1 the sender can start sending data.

According to one aspect of the disclosure an approach for estimating the bandwidth Land RTT is described while referring to . The bandwidth L may be sometimes referred to as an available bandwidth or a link capacity.

To estimate RTT every RTT timeout seconds determined based on selection experimentation or other methods a data packet can be sent with packet type RTT. A receiver e.g. module upon receiving such a packet can respond immediately with an acknowledgement with packet type set as RTT response. This acknowledgement may contain the sequence number of the RTT packet in the data region in addition to the acknowledgement information contained in a standard acknowledgement. This RTT measurement can be stored in a running queue of length n determined based on selection experimentation or other methods and the current estimate of RTT is for example equal to the average of the values in this queue. In another aspect the current RTT estimate may be determined for example by a gradient descent method using a function such as RTT a RTT old 1 a RTT currentMeasured.

In one aspect a packet may have an arbitrary size rather than a fixed size. In another aspect all packets are of arbitrary non constant size. Referring to a packet utilizing an accelerated protocol of the subject technology may include some or all of the following portions according to one aspect of the disclosure 

In one aspect a header portion of a packet e.g. a packet sent or received between modules and in may include information located between bit through bit and any control information located between bit and the last bit. A packet structure described above shows illustrative examples and the subject technology is not limited to these examples. In one aspect a header portion of a packet may include any additional field s that contain more information which may be related to the packet type or other information. In one aspect the total size or the total number of bits for the header portion is not limited to the size shown above. In one example the total size of the header e.g. a header portion of a packet may be even smaller than the size shown above. This may be accomplished for example by eliminating or reducing the size of one or more fields in the header and using this reduced size header to achieve similar functionality. Such modifications would be apparent to those skilled in the art.

In one aspect of the disclosure a first communication proxy module e.g. module in may receive one or more streams e.g. data streams or connection requests from for example communication application module A or transparent communication proxy module generate one or more header portions and send the one or more streams including the one or more header portions to a second communication proxy module e.g. module . Each of the one or more header portions may include for example some or all of the following header information i a packet sequence identifier ii a packet size iii a packet type identifier iv control information and v any other information. The header information may be added to a stream. A stream may be encapsulated in a packet which has the header information. In one aspect module may generate header information for data streams as well as header information for connection requests. Header information for a data stream may be appended to the data stream and header information for a connection request may be appended to the connection request.

In another aspect of the disclosure a first communication proxy module e.g. module in may receive one or more streams e.g. data streams from for example communication application module B generate one or more header portions and send the one or more streams including the one or more header portions to a second communication proxy module e.g. module . Each of the one or more header portions may include for example some or all of the following header information i a packet sequence identifier ii a packet size iii a packet type identifier iv control information and v any other information. The header information may be added to a stream. A stream may be encapsulated in a packet which has the header information. In one aspect module may generate header information for data streams as well as header information for connection requests. Header information for a data stream may be appended to the data stream and header information for a connection request may be appended to the connection request.

Referring to in one aspect of the disclosure module may receive utilizing a first protocol a stream in a format utilizing the first protocol. Module may add first header information and then add second header information to form a packet in a format utilizing a second protocol and then facilitate sending the packet to module utilizing the second protocol.

In one aspect each of the first protocol and the second protocol is a first transmission protocol and a second transmission protocol respectively. In one aspect the first protocol is different from the second protocol. In one aspect the first header information may include one or more of the header information described above with reference to . In one example the first protocol is TCP and the second protocol is UDP. In one aspect module does not modify the stream itself e.g. a TCP stream in that it does not eliminate any portion of the stream but adds header information to the stream. In one aspect the first protocol may be a non accelerated protocol and the second protocol including the first and second header information may be an accelerated protocol.

In one example module may receive a TCP stream utilizing TCP e.g. via and or via add header information including one or more of the header information described above and add UDP header information to form a UDP packet or a packet that conforms to UDP and then facilitate sending the packet to module utilizing UDP e.g. via and . The UDP header information may for example include one or more of the following a source port a destination port and the length of a packet.

In one aspect the descriptions provided in the last three paragraphs with reference to modules and may apply mutatis mutandis to modules and respectively as if the following replacements were made with with and with .

According to one aspect of the disclosure an example of reliability control is described below while referring to .

In one aspect to ensure that all packets that are sent arrive at a receiver e.g. module or a timer based selective acknowledgement SACK scheme may be employed. This scheme may be enforced periodically.

In one aspect the format of a portion of an acknowledgement showing SEQ and data portions of a header may be 

Where SEQ is the sequence number of the data packet up to which all packets have been received including SEQ . The bits following the sequence number each contains a 0 or a 1 depending on whether the corresponding packet subsequent to SEQ has been received recovered or not by a receiver e.g. module or . In one aspect the last bit may be a 1 and represents the highest packet sequence number thus far received by the receiver. In another example the last bit is always a 1. Since data is sent by byte this last byte may contain some slack bits that are all 0 which may be interpreted correctly as this data has not been received. 

In one aspect an acknowledgement ACK includes a full header rather than just the SEQ and data portions described above . For example an ACK includes ACK as the packet type identifier and the reserved field may be empty.

In one aspect an acknowledgement ACK may be stored in the control information bits e.g. bit and thereafter in the header of the packet with the base sequence number stored in the sequence number portion of the header bits and the packet type field bits indicating that it is an acknowledgement packet. The ACKs may be sent periodically at some pre determined value for the period e.g. as a function of BDP so that the number of packets being acknowledged is approximately constant .

In one aspect packet loss statistics may be included in the header of a packet for example in the optional bits 

In addition in one aspect to ensure reliability all unacknowledged packets are buffered at the sender e.g. module or so that they may be resent if necessary.

According to one aspect of the disclosure an example of in order delivery is described below while referring to .

In one aspect all packets received at accelerator modules e.g. module or are put into order before they are forwarded to an application module e.g. module or respectively . Accordingly all out of order packets are buffered at the receiver e.g. module or until the packet sequence can be put into order when the required packet s arrive .

According to one aspect of the disclosure an example of memory management is described below while referring to .

In one aspect due to the reliability and in order delivery requirements an efficient memory management scheme is employed to handle the send and receive buffers in a sender and a receiver e.g. module or .

In one aspect a structure referred to as the send queue which may be sometimes referred to as a priority queue can be utilized. A send queue in a sender e.g. module or can be a linked list queue that contains pointers to the packets that have been sent in order of sending time along with the timestamp of the packet. The actual packets can be stored in a circular buffer of size W which is a window size . Every time the buffer becomes full which may happen when W is increased the buffer can be copied into a new buffer of size W new. In another example the buffer size may be 2 W or another size.

According to one aspect an example of an operation of memory management is described below as a process flow while referring to 

In one aspect a receiver e.g. module or may use two structures i a receive buffer into which packets can be received and ii a hash table to index these packets. In one example a buffer is a wrap around buffer of size 2W to provide some slack space . Since packets are not guaranteed to arrive in order buffer fragmentation becomes an issue. To optimize buffer usage it can be defragmented when it is nearing capacity. To make this process efficient a buffer in a receiver can make use of headers for each packet stored in the buffer. The header can indicate whether the slot is occupied or not and can also contain packet size of the contained packet. If the buffer reaches capacity e.g. when the amount of space left is about 1 MTU maximum transfer unit the largest possible size for a packet then it can be defragmented to free up space. If after defragmentation the buffer is still at capacity then its size can be doubled.

According to one aspect of the disclosure an example of an operation of memory management at a receiver e.g. module or is described in detail below while referring to .

According to one aspect of the disclosure an example of an operation of buffer defragmentation at a receiver e.g. module or is described in detail below while referring to .

In one aspect every packet in the receive buffer can be contained inside a receive buffer header which may have the format shown in . A receive buffer header may include bits for occupied bits for size and bits for a header including a packet. The bits for occupied may be used to indicate whether the block is occupied or not.

Referring to in one aspect an example of an operation of buffer defragmentation may be performed by a receiver e.g. module or as follows 

As illustrated in when packet number 0 arrives packet numbers 0 7 are cleared immediately. When more packets arrive and the amount of space at the end of the buffer is less than 1 MTU the allocated memory is defragmented as shown in .

According to one aspect of the disclosure an example of an operation of congestion control is described in detail below.

One approach for congestion control is to increase the window size I transmission rate until transmission reaches the available bandwidth L by using a function in which W is proportional to L exp t . L may be a link capacity measured by bits second. In one aspect congestion control may be carried out by determining a window size as a function of RTT and L.

Another approach for congestion control is an additive increase multiplicative decrease scheme. In this scheme the window size is increased by some fraction of the number of bytes that are acknowledged in each acknowledgement additive increase . When measured packet loss reaches a certain threshold value e.g. 1 the window size is reduced to a fraction of itself e.g. 75 multiplicative decrease . The measured packet loss may take into consideration not only the packets that are lost and retransmitted from a local communication proxy module but also the packets that are lost but recovered at a remote communication proxy module through FEC. In this way a true network packet loss can be measured and not just packets that are lost and not recovered.

According to one aspect of the disclosure an example of an operation of a transparent communication proxy module is described in further detail below while referring to .

In one aspect a transparent communication proxy module e.g. module may be implemented as a layered service provider Winsock interface. This interface can be loaded with any Winsock based application. Whenever a Winsock routine or function is called the routine is first dispatched to this interface and then this interface transfers it to other layers of Winsock.

As one example of an implementation transparent communication proxy module of may intercept connect calls of Winstock based applications from communication application module A and determine whether the port of this new outgoing connection needs to be accelerated or not. If the connection is to be accelerated then module may create a new socket and connect the socket to communication proxy module A . If a connection between communication proxy module A and communication proxy module B is successful then the IP address and the port number of an outgoing connection may be changed to communication proxy module A . Finally the connect call can be forwarded to other Winsock layers as usual in Winsock based applications to complete the connection process.

According to one aspect of the disclosure an example of an operation of a communication proxy module is described in further detail below while referring to .

As one example of an implementation communication proxy module A module may listen on a pre configured TCP port. When or whenever transparent communication proxy module finds any connection request for communication which needs to be accelerated module forwards that connection request to module on this port. On receiving the connect request module initiates a handshake with corresponding proxy module e.g. communication proxy module B and sets up a communication channel that utilizes an accelerated protocol and creates a new thread for data communication on this session.

According to one aspect of the disclosure if data can be parsed at a communication proxy module e.g. module or the communication proxy module may determine the type of data e.g. bitmap audio video and the communication proxy module may assign priorities e.g. transmission priorities specifying when to transmit the data to the data based on its type determined by the communication proxy module. In addition the communication proxy module may use different data processing techniques or sending schemes for different types of data e.g. less focus on error correction recovery for streaming data such as video different types of compression depending on the type of data .

Referring to in one aspect the terms local and remote are relative terms. For example any of the modules or components e.g. A B or in or items in in apparatus or e.g. on a client side may be considered as i local modules or local components or ii remote modules or remote components depending on whether the modules or components are described from the perspective of apparatus or e.g. a client side or from the perspective of apparatus or e.g. a server side respectively.

Similarly any of the modules or components e.g. A B or in or items in in apparatus or e.g. on a server side may be considered as i local modules or local components or ii remote modules or remote components depending on whether the modules or components are described from the perspective of apparatus or e.g. a server side or from the perspective of apparatus or e.g. a client side respectively.

Furthermore an application may be a local application or a remote application depending on whether the application is described from the perspective of apparatus or e.g. a client side or from the perspective of apparatus or e.g. a server side .

By way of illustration and not limitation a communication channel for remote communication e.g. between remote components or modules may include wired or wireless communication networks and may have any geographic reach e.g. a personal area network a local area network a wide area network the Internet or an intranet . A communication channel for remote communication may use the internet protocol IP packet format or any other format for data communication. A communication channel for remote communication may comprise one or more heterogeneous networks communicating on different physical media and may be managed by one or more network operators. In one example a communication channel for remote communication may be a wireless wide area network comprising a cellular telephony network.

Communication apparatus A may connect to communication apparatus B remotely over a communication channel e.g. for example via a modem connection a LAN connection including the Ethernet or a broadband WAN connection including DSL Cable T1 T3 Fiber Optics Wi Fi or other network connection. A communication channel for remote communication may include for example one or more routers for routing data between apparatus and . A remote device e.g. a component in apparatus from the perspective of apparatus or a component in apparatus from the perspective of apparatus on a network may be addressed for example by a corresponding network address such as but not limited to an Internal protocol IP address an Internet name a Windows Internet name service WINS name a domain name or other system name.

By way of illustration and not limitation a communication channel for local communication e.g. or from the perspective of apparatus from the perspective of apparatus between local components or modules may be a wired or wireless short range communication network or connection such as one of the family of Institute of Electrical and Electronics Engineers IEEE 802.x communication networks a Bluetooth network a universal serial bus USB connection a near field communication NFC network a FireWire connection or another type of short range connection or network including a direct connection . In one example a communication channel for local communication may be a connection or network within a distance of 1 foot 5 feet 10 feet 15 feet 20 feet 50 feet or 100 feet e.g. modules and are located within 1 foot 5 feet 10 feet 15 feet 20 feet 50 feet or 100 feet of each other .

In one aspect of the disclosure the term communication channel may sometimes be referred to as a connection a socket connection a connection channel a channel a network or vice versa. In one aspect a communication channel may include one or more communication channels in parallel or in series . In one aspect a communication channel may refer to a communication path. A communication path may include a wired path a wireless path or a combination of both. A communication path may include one or more components one or more devices and or one or more networks. For example in a communication channel between modules and may include an accelerated communication path that includes components and . In another example a communication channel between modules and may include a non accelerated communication path that includes channel .

In one aspect of the disclosure a stream transfer rate of an accelerated communication path may be higher than a stream transfer rate of a non accelerated communication path. In one example data streams utilizing an accelerated communication path e.g. components and are transferred between modules and at a rate higher than the rate the data streams would be transferred using a non accelerated communication path e.g. channel .

In one aspect the term stream may sometimes be referred to as data data stream data packet s packet s traffic a connection request a request or vice versa. In one aspect the term packet loss may sometimes be referred to as data loss or vice versa. In one aspect the terms packet sequence identifier and packet type identifier may be sometimes referred to as stream sequence identifier and stream type identifier respectively or vice versa. A term IP identifier may refer to an IP address. A term port or an identifier of a port may refer to a port number. In one aspect when a sender or a receiver is described as a module e.g. module or such sender or receiver may be i the module itself e.g. an application or ii a machine readable medium a device or a computer that contains the module.

In one aspect of the disclosure the term accelerate may refer to acceleration for a network s with high latency and or packet loss. In another aspect acceleration may provide the capability to increase bandwidth e.g. increase a window size of packets . In another aspect acceleration may provide the capability to maximize bandwidth for a network condition.

In one aspect when a signal flows from module U to module V to module X module Y and to module Z. A signal received by module Z can be viewed as originated by module U module V module X or module Y. Accordingly in one aspect an originator of a signal does not need to be the first originator of the signal. In another example an originator may be the first originator of the signal.

In one example a connection between two points is established when a handshake between the two points is made successfully. In another example a connection between two points is established when the two points are ready to send or receive a stream from each other. Methods of establishing a connection is not limited to these examples and a connection may be established using other methods.

In one aspect of the disclosure the one or more accelerator modules e.g. module module and or module in may be transparent to modules and . For example an accelerator module may be application agnostic. In one aspect an accelerator module may be a software only application. In one aspect an accelerator module may be at a layer below the presentation layer layer 6 in the OSI model e.g. in layer 3 so that an accelerator module may be independent of the presentation layer and any layer above it in the OSI model. In one aspect an accelerator module can be invoked outside modules and . In one aspect modules and can be pre existing applications and an accelerator module can be used with modules and without modifying module or specifically for the accelerator module.

In one aspect of the disclosure in an accelerated mode a module e.g. module or module in may transmit and receive streams via a communication channel utilizing an accelerated protocol e.g. non TCP . In one aspect in an accelerated mode a module may accelerate a stream to use the maximum bandwidth for the current latency and data loss conditions. In one aspect in an accelerated mode a module may dynamically adjust itself to changing latency and data loss conditions to maintain optimal usage of bandwidth and user experience.

In one aspect of the disclosure various network conditions e.g. latency data loss other network conditions and various measurements may be real time conditions and a module e.g. module or module in may respond to these conditions in real time. In one aspect the term a network condition may refer to one or more network conditions. In one aspect of the disclosure the term round trip time or RTT may refer to latency or vice versa.

The subject technology is illustrated for example according to various aspects described below. Numbered clauses are provided below for convenience. These are provided as examples and do not limit the subject technology.

a local transparent communication proxy module configured to intercept a first stream destined to a remote destination and configured to make a first determination whether to accelerate communication associated with the first stream and

a local communication proxy module configured to receive the first stream based on the first determination and configured to make a second determination whether a connection to a remote communication proxy module is established 

wherein if the connection is established then the local communication proxy module is configured to receive one or more additional streams and configured to direct the one or more additional streams to the remote communication proxy module utilizing an accelerated mode and if the connection is not established then the local transparent communication proxy module is configured to direct the first stream to the remote destination utilizing a non accelerated mode.

2. The communication apparatus of clause 1 wherein the first stream comprises a network request and the one or more additional streams comprise one or more data streams 

wherein the one or more computers comprises one or more displays one or more processing systems the local transparent communication proxy module and the local communication proxy module.

3. The communication apparatus of clause 1 wherein the first stream comprises real time information from a local communication application module comprising a real time application and the one or more additional streams comprise real time information and

wherein the first stream is in a form utilizing a first transmission protocol the non accelerated mode utilizes the first transmission protocol and the accelerated mode utilizes a second transmission protocol different from the first transmission protocol.

4. The communication apparatus of clause 1 wherein the local transparent communication proxy module is configured to receive the first stream via a first communication channel 

wherein the local communication proxy module is configured to receive the first stream via a second communication channel 

wherein if the connection is established then the local communication proxy module is configured to receive the one or more additional streams via a third communication channel 

wherein the third communication channel bypasses the local transparent communication proxy module wherein the local communication proxy module is configured to facilitate establishment of the connection via a fourth communication channel and

wherein a communication path for the accelerated mode is different from a communication path for the non accelerated mode.

5. The communication apparatus of clause 1 wherein a stream transfer rate utilizing the accelerated mode is higher than a stream transfer rate utilizing a transmission control protocol TCP or a stream transfer rate utilizing the non accelerated mode.

6. The communication apparatus of clause 1 wherein the local transparent communication proxy module is configured to intercept the first stream originated from a local communication application module and the local communication proxy module is configured to be transparent to the local communication application module.

7. The communication apparatus of clause 1 wherein the local transparent communication proxy module is configured to intercept the first stream from a local communication application module without modifying the local communication application module specifically for the local transparent communication proxy module and

wherein the local communication proxy module is configured to receive the first stream and the one or more additional streams originated from a local communication application module without modifying the local communication application module specifically for the local communication proxy module.

a priority queue configured to store and order streams according to times the streams have been sent and

9. The communication apparatus of clause 8 wherein the local communication proxy module further comprises 

a second local transparent communication proxy module configured to intercept a third stream destined to the remote destination and configured to make a third determination whether to accelerate communication associated with the third stream and

a second local communication proxy module configured to receive the third stream based on the third determination and configured to make a fourth determination whether a second connection to the remote communication proxy module is established 

wherein if the second connection is established then the second local communication proxy module is configured to receive one or more second additional streams and configured to direct the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode and the second connection and if the second connection is not established then the second local transparent communication proxy module is configured to direct the third stream to the remote destination utilizing a non accelerated mode.

a second local transparent communication proxy module configured to intercept a third stream destined to the remote destination and configured to make a third determination whether to accelerate communication associated with the third stream 

the local communication proxy module configured to receive the third stream based on the third determination and configured to make a fourth determination whether a second connection to the remote communication proxy module is established 

wherein if the second connection is established then the local communication proxy module is configured to receive one or more second additional streams and configured to direct the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode and if the second connection is not established then the second local transparent communication proxy module is configured to direct the third stream to the remote destination utilizing a non accelerated mode.

12. A machine readable medium encoded with instructions for remote communication the instructions comprising code for 

making a first determination whether to accelerate communication associated with the first stream e.g. B 

making a second determination whether a connection to a remote communication proxy module is established e.g. A 

if the connection is not established directing the first stream to the remote destination utilizing a non accelerated mode e.g. A and

if the connection is established directing one or more additional streams to the remote communication proxy module utilizing an accelerated mode e.g. A .

12A. The machine readable medium of clause 12 wherein the directing one or more additional streams comprises directing one or more additional streams to the remote communication proxy module through a local communication proxy module utilizing an accelerated mode.

13. The machine readable medium of clause 12 wherein the first stream comprises a network request and the one or more additional streams comprise one or more data streams.

14. The machine readable medium of clause 12 wherein the first stream comprises real time information from a local communication application module comprising a real time application and the one or more additional streams comprise real time information and

wherein the first stream is in a form utilizing a first transmission protocol the non accelerated mode comprises the first transmission protocol and the accelerated mode comprises a second transmission protocol different from the first transmission protocol.

15. The machine readable medium of clause 12 wherein the intercepting comprises receiving the first stream by a local transparent communication proxy module via a first communication channel wherein the making a first determination is performed by the local transparent communication proxy module wherein the making a second determination is performed by a local communication proxy module wherein the directing the first stream is performed by the local transparent communication proxy module wherein the directing one or more additional streams is performed by the local communication proxy module 

wherein the instructions further comprise code for receiving the first stream by the local communication proxy module based on the first determination via a second communication channel facilitating establishing the connection with the remote communication proxy module by the local communication proxy module based on the first determination if the connection between the local communication proxy module and the remote communication proxy module is established receiving by the local communication proxy module the one or more additional streams via a third communication channel 

wherein the third communication channel bypasses the local transparent communication proxy module wherein the local communication proxy module is configured to facilitate establishing the connection via a fourth communication channel and wherein a communication path for the accelerated mode is different from a communication path for the non accelerated mode.

16. The machine readable medium of clause 12 wherein a stream transfer rate utilizing the accelerated mode is higher than a stream transfer rate utilizing a transmission control protocol TCP or a stream transfer rate utilizing the non accelerated mode.

17. The machine readable medium of clause 12 wherein the intercepting a first stream comprises intercepting by a local transparent communication proxy module the first stream originated from a local communication application module and the local communication proxy module is configured to be transparent to the local communication application module.

18. The machine readable medium of clause 12 wherein the intercepting a first stream comprises intercepting by a local transparent communication proxy module the first stream from a local communication application module without modifying the local communication application module specifically for the local transparent communication proxy module and

wherein the instructions further comprise code for receiving based on the first determination by the local communication proxy module the first stream originated from the local communication application module without modifying the local communication application module specifically for the local communication proxy module and receiving based on the first determination by the local communication proxy module the one or more additional streams originated from the local communication application module without modifying the local communication application module specifically for the local communication proxy module.

19. The machine readable medium of clause 12 wherein the instructions further comprise code for facilitating storing and ordering streams according to times the streams have been sent and facilitating storing streams that have been received.

20. The machine readable medium of clause 19 wherein the instructions further comprise code for minimizing access time to the streams that have been sent and stored and minimizing access time to the streams that have been received and stored.

20A. The machine readable medium of clause 12 wherein the instructions further comprise code for error correction to reduce retransmission of streams.

a first local transparent communication proxy module comprising the code for intercepting a first stream destined to a remote destination making a first determination whether to accelerate communication associated with the first stream and if the connection is not established directing the first stream to the remote destination utilizing a non accelerated mode 

a first local communication proxy module comprising code for receiving the first stream based on the first determination wherein the first local communication proxy module further comprises the code for making a second determination whether a connection to a remote communication proxy module is established and if the connection is established directing one or more additional streams to the remote communication proxy module utilizing an accelerated mode 

a second local transparent communication proxy module comprising code for intercepting a third stream destined to the remote destination and making a third determination whether to accelerate communication associated with the third stream and

a second local communication proxy module comprising code for receiving the third stream based on the third determination making a fourth determination whether a second connection to the remote communication proxy module is established and if the second connection is established receiving one or more second additional streams and directing the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode 

wherein the second local transparent communication proxy module further comprises code for if the second connection is not established directing the third stream to the remote destination utilizing an non accelerated mode.

a first local transparent communication proxy module comprising the code for intercepting a first stream destined to a remote destination making a first determination whether to accelerate communication associated with the first stream and if the connection is not established directing the first stream to the remote destination utilizing a non accelerated mode 

a local communication proxy module comprising code for receiving the first stream based on the first determination wherein the first local communication proxy module further comprises the code for making a second determination whether a connection to a remote communication proxy module is established and if the connection is established directing one or more additional streams to the remote communication proxy module utilizing an accelerated mode and

a second local transparent communication proxy module comprising code for intercepting a third stream destined to the remote destination and making a third determination whether to accelerate communication associated with the third stream 

wherein the local communication proxy module further comprises code for receiving the third stream based on the third determination making a fourth determination whether a second connection to the remote communication proxy module is established and if the second connection is established receiving one or more second additional streams and directing the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode 

wherein the second local transparent communication proxy module further comprises code for if the second connection is not established directing the third stream to the remote destination utilizing a non accelerated mode.

making a second determination whether a connection to a remote communication proxy module is established 

if the connection is not established directing the first stream to the remote destination utilizing a non accelerated mode and

if the connection is established directing one or more additional streams to the remote communication proxy module utilizing an accelerated mode.

24. The method of clause 23 wherein the first stream comprises a network request and the one or more additional streams comprise one or more data streams.

25. The method of clause 23 wherein the first stream comprises real time information from a local communication application module comprising a real time application and the one or more additional streams comprise real time information and

wherein the first stream is in a form utilizing a first transmission protocol the non accelerated mode comprises the first transmission protocol and the accelerated mode comprises a second transmission protocol different from the first transmission protocol.

26. The method of clause 23 wherein the intercepting comprises receiving the first stream by a local transparent communication proxy module via a first communication channel wherein the making a first determination is performed by the local transparent communication proxy module wherein the making a second determination is performed by a local communication proxy module wherein the directing the first stream is performed by the local transparent communication proxy module wherein the directing one or more additional streams is performed by the local communication proxy module 

wherein the method further comprises receiving the first stream by the local communication proxy module based on the first determination via a second communication channel facilitating establishing the connection with the remote communication proxy module by the local communication proxy module based on the first determination if the connection between the local communication proxy module and the remote communication proxy module is established receiving by the local communication proxy module the one or more additional streams via a third communication channel 

wherein the third communication channel bypasses the local transparent communication proxy module wherein the local communication proxy module is configured to facilitate establishing the connection via a fourth communication channel and wherein a communication path for the accelerated mode is different from a communication path for the non accelerated mode.

27. The method of clause 23 wherein a stream transfer rate utilizing the accelerated mode is higher than a stream transfer rate utilizing a transmission control protocol TCP or a stream transfer rate utilizing the non accelerated mode.

28. The method of clause 23 wherein the intercepting a first stream comprises intercepting by a local transparent communication proxy module the first stream originated from a local communication application module and the local communication proxy module is configured to be transparent to the local communication application module.

29. The method of clause 23 wherein the intercepting a first stream comprises intercepting by a local transparent communication proxy module the first stream from a local communication application module without modifying the local communication application module specifically for the local transparent communication proxy module and

wherein the method further comprises receiving based on the first determination by the local communication proxy module the first stream originated from the local communication application module without modifying the local communication application module specifically for the local communication proxy module and receiving based on the first determination by the local communication proxy module the one or more additional streams originated from the local communication application module without modifying the local communication application module specifically for the local communication proxy module.

30. The method of clause 23 further comprising facilitating storing and ordering streams according to times the streams have been sent and facilitating storing streams that have been received.

31. The method of clause 30 further comprising minimizing access time to the streams that have been sent and stored and minimizing access time to the streams that have been received and stored.

32. The method of clause 23 wherein the intercepting is performed by a local transparent communication proxy module wherein the making a first determination is performed by the local transparent communication proxy module wherein the making a second determination is performed by a local communication proxy module wherein the directing the first stream is performed by the local transparent communication proxy module wherein the directing one or more additional streams is performed by the local communication proxy module 

wherein the method further comprises receiving by the local communication proxy module the first stream based on the first determination intercepting by a second local transparent communication proxy module a third stream destined to the remote destination making by the second local transparent communication proxy module a third determination whether to accelerate communication associated with the third stream receiving by a second local communication proxy module the third stream based on the third determination making by the second local communication proxy module a fourth determination whether a second connection to the remote communication proxy module is established if the second connection is established receiving by the second local communication proxy module one or more second additional streams and directing by the second local communication proxy module the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode and if the second connection is not established directing by the second local transparent communication proxy module the third stream to the remote destination utilizing a non accelerated mode.

33. The method of clause 23 wherein the intercepting is performed by a local transparent communication proxy module wherein the making a first determination is performed by the local transparent communication proxy module wherein the making a second determination is performed by a local communication proxy module wherein the directing the first stream is performed by the local transparent communication proxy module wherein the directing one or more additional streams is performed by the local communication proxy module 

wherein the method further comprises receiving by the local communication proxy module the first stream based on the first determination intercepting by a second local transparent communication proxy module a third stream destined to the remote destination making by the second local transparent communication proxy module a third determination whether to accelerate communication associated with the third stream receiving by the local communication proxy module the third stream based on the third determination making by the local communication proxy module a fourth determination whether a second connection to the remote communication proxy module is established and if the second connection is established receiving by the local communication proxy module one or more second additional streams and directing by the local communication proxy module the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode and if the second connection is not established directing by the second local transparent communication proxy module the third stream to the remote destination utilizing a non accelerated mode.

means for making a first determination whether to accelerate communication associated with the first stream e.g. B 

means for making a second determination whether a connection to a remote communication proxy module is established e.g. B 

means for if the connection is not established directing the first stream to the remote destination utilizing a non accelerated mode e.g. B and

means for if the connection is established directing one or more additional streams to the remote communication proxy module utilizing an accelerated mode e.g. B .

35. The communication apparatus of clause 34 wherein the first stream comprises a network request and the one or more additional streams comprise one or more data streams wherein the communication apparatus comprises one or more computers and wherein the one or more computers comprises means for displaying information means for processing information the means for intercepting the means for making a first determination the means for making a second determination the means for directing the first stream and the means for directing one or more additional streams.

36. The communication apparatus of clause 34 wherein the first stream comprises real time information from a local communication application module comprising a real time application and the one or more additional streams comprise real time information and

wherein the first stream is in a form utilizing a first transmission protocol the non accelerated mode comprises the first transmission protocol and the accelerated mode comprises a second transmission protocol different from the first transmission protocol.

37. The communication apparatus of clause 34 wherein the means for intercepting comprises means for receiving the first stream via a first communication channel 

wherein the communication apparatus further comprises means for receiving the first stream based on the first determination via a second communication channel means for facilitating establishing the connection with the remote communication proxy module based on the first determination via a fourth communication channel means for if the connection is established receiving the one or more additional streams via a third communication channel wherein the third communication channel bypasses the means for receiving the first stream via the first communication channel and

wherein a communication path for the accelerated mode is different from a communication path for the non accelerated mode.

38. The communication apparatus of clause 34 wherein a stream transfer rate utilizing the accelerated mode is higher than a stream transfer rate utilizing a transmission control protocol TCP or a stream transfer rate utilizing the non accelerated mode.

39. The communication apparatus of clause 34 wherein the means for intercepting a first stream comprises means for intercepting the first stream originated from a local communication application module and the means for making the second determination and the means for directing the one or more additional streams are transparent to the local communication application module.

40. The communication apparatus of clause 34 wherein the means for intercepting a first stream comprises means for intercepting by a local transparent communication proxy module the first stream from a local communication application module without modifying the local communication application module specifically for the local transparent communication proxy module and

wherein the communication apparatus comprises means for receiving based on the first determination by a local communication proxy module the first stream originated from the local communication application module without modifying the local communication application module specifically for the local communication proxy module and means for receiving based on the first determination by the local communication proxy module the one or more additional streams originated from the local communication application module without modifying the local communication application module specifically for the local communication proxy module.

41. The communication apparatus of clause 34 further comprising means for facilitating storing and ordering streams according to times the streams have been sent and means for facilitating storing streams that have been received.

42. The communication apparatus of clause 41 further comprising means for minimizing access time to the streams that have been sent and stored and means for minimizing access time to the streams that have been received and stored.

means for intercepting a third stream destined to the remote destination making a third determination whether to accelerate communication associated with the third stream and if a second connection is not established directing a third stream to the remote destination utilizing a non accelerated mode and

means for receiving the third stream based on the third determination making a fourth determination whether the second connection to the remote communication proxy module is established and if the second connection is established receiving one or more second additional streams and directing the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode.

means for receiving the first stream based on the first determination receiving a third stream based on a third determination making a fourth determination whether a second connection to the remote communication proxy module is established if the second connection is established receiving one or more second additional streams and directing the one or more second additional streams to the remote communication proxy module utilizing an accelerated mode and

means for intercepting the third stream destined to the remote destination and making the third determination whether to accelerate communication associated with the third stream and if the second connection is not established directing the third stream to the remote destination utilizing a non accelerated mode.

The subject technology is illustrated for example according to various aspects described below. Numbered clauses are provided below for convenience. These are provided as examples and do not limit the subject technology.

a first local module configured to intercept a first stream the first stream utilizing a first transmission protocol and destined to a remote destination over a network configured to make a determination whether to direct the first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol based on one or more of the following factors a configuration or a network condition and configured to direct the first stream to the first destination or the second destination based on the determination 

1A. The communication apparatus of clause 1 wherein the first connection comprises at least a portion or all of a communication channel wherein the communication channel may include for example a portion of connection a connection a port of the communication apparatus a channel and or a port at the remote destination wherein the communication channel may be between the communication apparatus and the remote destination e.g. A or between a local application module e.g. and a remote application module e.g. or a portion thereof and

wherein the first destination comprises one of the following a port e.g. of the communication apparatus an intermediary destination along the communication channel the remote destination or a port e.g. at the remote destination.

1B. The communication apparatus of clause 1 wherein the second connection comprises at least a portion or all of a second communication channel wherein the second communication channel may include for example a connection between the first local module and a local proxy module a port a communication channel e.g. and or ports and wherein the second communication channel may be between the communication apparatus and the remote destination between the first local module and a remote application module or a portion thereof and

wherein the second destination comprises one of the following a local proxy module e.g. a remote proxy module e.g. a port e.g. an intermediary destination along the second communication channel the remote destination or a port e.g. at the remote destination.

1C. The communication apparatus of clause 1 wherein the second transmission protocol comprises the first transmission protocol 

1D. The communication apparatus of clause 1 wherein if the first local module determines to direct the first stream to the first destination and the first stream is a connection request originated from a local application module then the first local module is configured to not intercept subsequent streams which comprise data from the local application module and is configured to allow the subsequent streams to be directed to the remote destination without the first local module s intervention and is configured to allow the local application module to receive streams from the remote destination without the first local module s intervention e.g. via a portion of .

2. The communication apparatus of clause 1 wherein the network condition comprises an amount of packet loss.

3. The communication apparatus of clause 1 wherein the network condition comprises a round trip time.

4. The communication apparatus of clause 1 wherein the network condition comprises available bandwidth.

5. The communication apparatus of clause 1 wherein the first local module is configured to direct the first stream to the first destination if an amount of packet loss over the network is below a threshold value and

wherein the first local module is configured to direct the first stream to the second destination if an amount of packet loss over the network is above a threshold value.

6. The communication apparatus of clause 1 wherein the first local module is configured to make a determination whether to direct a first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol further based on one or more of the following whether a second local module for receiving and accelerating a stream is running whether a first remote module for receiving a stream from the second local module is running and whether a connection between the second local module and the first remote module is establishable.

7. The communication apparatus of clause 1 wherein the communication apparatus comprises a computer wherein the computer comprises a display a processing system and the first local module wherein the first stream comprises a network request and wherein the first local module is configured to direct the first stream to the remote destination via the first destination or via the second destination.

8. A machine readable medium encoded with instructions for remote communication the instructions comprising code for 

intercepting a first stream the first stream utilizing a first transmission protocol and destined to a remote destination over a network e.g. A of 

making a determination whether to direct the first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol based on one or more of the following factors a configuration or a network condition e.g. A and

directing the first stream to the first destination or the second destination based on the determination e.g. A 

9. The machine readable medium of clause 8 wherein the network condition comprises an amount of packet loss.

10. The machine readable medium of clause 8 wherein the network condition comprises a round trip time.

11. The machine readable medium of clause 8 wherein the network condition comprises available bandwidth.

12. The machine readable medium of clause 8 wherein the directing comprises directing the first stream to the first destination if an amount of packet loss over the network is below a threshold value and directing the first stream to the second destination if an amount of packet loss over the network is above a threshold value.

making a determination by a first local module whether to direct a first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol further based on one or more of the following whether a second local module for receiving and accelerating a stream is running whether a first remote module for receiving a stream from the second local module is running and whether a connection between the second local module and the first remote module is establishable.

14. The machine readable medium of clause 8 wherein the first stream comprises a network request and wherein the directing comprises code for directing the first stream to the remote destination via the first destination or via the second destination.

intercepting a first stream the first stream utilizing a first transmission protocol and destined to a remote destination over a network 

making a determination whether to direct the first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol based on one or more of the following factors a configuration or a network condition and

directing the first stream to the first destination or the second destination based on the determination 

19. The method of clause 15 wherein the directing comprises directing the first stream to the first destination if an amount of packet loss over the network is below a threshold value and directing the first stream to the second destination if an amount of packet loss over the network is above a threshold value.

making a determination by a first local module whether to direct a first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol further based on one or more of the following whether a second local module for receiving and accelerating a stream is running whether a first remote module for receiving a stream from the second local module is running and whether a connection between the second local module and the first remote module is establishable.

21. The method of clause 15 wherein the first stream comprises a network request and wherein the directing comprises directing the first stream to the remote destination via the first destination or via the second destination.

means for intercepting a first stream the first stream utilizing a first transmission protocol and destined to a remote destination over a network e.g. B of 

means for making a determination whether to direct the first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol based on one or more of the following factors a configuration or a network condition e.g. B and

means for directing the first stream to the first destination or the second destination based on the determination e.g. B 

23. The communication apparatus of clause 22 wherein the network condition comprises an amount of packet loss.

24. The communication apparatus of clause 22 wherein the network condition comprises a round trip time.

25. The communication apparatus of clause 22 wherein the network condition comprises available bandwidth.

26. The communication apparatus of clause 22 wherein the means for directing comprises means for directing the first stream to the first destination if an amount of packet loss over the network is below a threshold value and means for directing the first stream to the second destination if an amount of packet loss over the network is above a threshold value.

means for making a determination by a first local module whether to direct a first stream over a first connection to a first destination utilizing the first transmission protocol or to direct the first stream over a second connection to a second destination utilizing a second transmission protocol further based on one or more of the following whether a second local module for receiving and accelerating a stream is running whether a first remote module for receiving a stream from the second local module is running and whether a connection between the second local module and the first remote module is establishable.

28. The communication apparatus of clause 22 wherein the communication apparatus comprises a computer and wherein the computer comprises means for displaying information means for processing information the means for intercepting the means for making a determination and the means for directing 

wherein the first stream comprises a network request and wherein the means for directing comprises means for directing the first stream to the remote destination via the first destination or via the second destination.

The subject technology is illustrated for example according to various aspects described below. Numbered clauses are provided below for convenience. These are provided as examples and do not limit the subject technology.

a local communication proxy module configured to receive streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination the local communication proxy module configured to facilitate sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module the local communication proxy module configured to adjust an amount of bandwidth used by the streams.

2. The communication apparatus of clause 1 wherein the local communication proxy module is configured to determine a window size for the streams to be sent to the remote communication proxy module and configured to adjust the window size based on one or more network conditions 

3. The communication apparatus of clause 1 wherein the local communication proxy module is configured to dynamically determine a window size for the streams to be sent to the remote communication proxy module and configured to dynamically adjust the window size based on one or more real time network conditions that are variable.

4. The communication apparatus of clause 1 wherein the local communication proxy module is configured to adjust a window size for the streams based on a round trip time RTT and a bandwidth of a connection between the local communication proxy module and the remote communication proxy module.

5. The communication apparatus of clause 1 wherein the local communication proxy module is configured to control congestion in a connection between the local communication proxy module and the remote communication proxy module based on recovery of lost data and based on lost data retransmitted.

6. The communication apparatus of clause 1 wherein the local communication proxy module is configured to adjust a window size for the streams based on the number or rate of lost data retransmitted by the local communication proxy module based on the number or rate of lost data recovered by the remote communication proxy module and based on data successfully transmitted and acknowledged.

7. The communication apparatus of clause 1 wherein the local communication proxy module is configured to determine periodically a round trip time RTT based on a signal sent to the remote communication proxy module and a signal received from the remote communication proxy module.

8. The communication apparatus of clause 1 wherein the local communication proxy module is configured to determine periodically a bandwidth of a connection between the local communication proxy module and the remote communication proxy module.

9. The communication apparatus of clause 1 wherein the local communication proxy module is configured to limit an amount of bandwidth used to send and receive streams between the local communication proxy module and the remote communication proxy module based on one or more of the following latency data loss and processing capabilities of a machine on which the local communication proxy module is located.

10. The communication apparatus of clause 1 wherein the local communication proxy module is configured to set constraints on the amount of bandwidth used by the streams.

11. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive the streams from the local communication application module based on a determination as to whether to accelerate the streams.

12. The communication apparatus of clause 1 wherein the local communication proxy module is configured to adjust the amount of bandwidth by cycling between two modes wherein in a first one of the two modes the local communication proxy module is configured to adjust bandwidth usage and in a second one of the two modes the local communication proxy module is configured to maintain bandwidth usage.

13. The communication apparatus of clause 1 wherein the communication apparatus comprises one or more computers 

wherein the one or more computers comprises one or more displays one or more processing systems and the local communication proxy module.

14. A machine readable medium encoded with instructions for remote communication the instructions comprising code for 

receiving streams from the local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination e.g. A of 

facilitating sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module e.g. A and adjusting an amount of bandwidth used by the streams e.g. A .

dynamically determining a window size for the streams to be sent to the remote communication proxy module and

dynamically adjusting the window size based on one or more real time network conditions that are variable.

adjusting a window size for the streams based on a round trip time RTT and a bandwidth of a connection between a local communication proxy module and the remote communication proxy module.

controlling congestion in a connection between a local communication proxy module and the remote communication proxy module based on recovery of lost data and based on lost data retransmitted.

adjusting a window size for the streams based on the number or rate of lost data retransmitted by a local communication proxy module based on the number or rate of lost data recovered by the remote communication proxy module and based on data successfully transmitted and acknowledged.

determining periodically a round trip time RTT based on a signal sent to the remote communication proxy module and a signal received from the remote communication proxy module.

determining periodically a bandwidth of a connection between a local communication proxy module and the remote communication proxy module.

limiting an amount of bandwidth used to send and receive streams between a local communication proxy module and the remote communication proxy module based on one or more of the following latency data loss and as processing capabilities of a machine on which the local communication proxy module is located.

23. The machine readable medium of clause 14 wherein the instructions comprise code for setting constraints on the amount of bandwidth used by the streams.

24. The machine readable medium of clause 14 wherein the instructions comprise code for receiving the streams from the local communication application module based on a determination as to whether to accelerate the streams.

25. The machine readable medium of clause 14 wherein the adjusting comprises cycling between two modes wherein a first one of the two modes comprises adjusting bandwidth usage and a second one of the two modes comprises maintaining bandwidth usage.

receiving streams from the local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination 

facilitating sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module and adjusting an amount of bandwidth used by the streams.

dynamically determining a window size for the streams to be sent to the remote communication proxy module and

dynamically adjusting the window size based on one or more real time network conditions that are variable.

adjusting a window size for the streams based on a round trip time RTT and a bandwidth of a connection between a local communication proxy module and the remote communication proxy module.

controlling congestion in a connection between a local communication proxy module and the remote communication proxy module based on recovery of lost data and based on lost data retransmitted.

adjusting a window size for the streams based on the number or rate of lost data retransmitted by a local communication proxy module based on the number or rate of lost data recovered by the remote communication proxy module and based on data successfully transmitted and acknowledged.

determining periodically a round trip time RTT based on a signal sent to the remote communication proxy module and a signal received from the remote communication proxy module.

determining periodically a bandwidth of a connection between a local communication proxy module and the remote communication proxy module.

limiting an amount of bandwidth used to send and receive streams between a local communication proxy module and the remote communication proxy module based on one or more of the following latency data loss and as processing capabilities of a machine on which the local communication proxy module is located.

35. The method of clause 26 comprising setting constraints on the amount of bandwidth used by the streams.

36. The method of clause 26 comprising receiving the streams from the local communication application module based on a determination as to whether to accelerate the streams.

37. The method of clause 26 wherein the adjusting comprises cycling between two modes wherein a first one of the two modes comprises adjusting bandwidth usage and a second one of the two modes comprises maintaining bandwidth usage.

means for receiving streams from the local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination e.g. B of 

means for facilitating sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module e.g. B and

means for determining a window size for the streams to be sent to the remote communication proxy module and

means for adjusting the window size based on one or more network conditions wherein the second transmission protocol is different from the first transmission protocol.

means for dynamically determining a window size for the streams to be sent to the remote communication proxy module and

means for dynamically adjusting the window size based on one or more real time network conditions that are variable.

means for adjusting a window size for the streams based on a round trip time RTT and a bandwidth of a connection between a local communication proxy module and the remote communication proxy module.

means for controlling congestion in a connection between a local communication proxy module and the remote communication proxy module based on recovery of lost data and based on lost data retransmitted.

means for adjusting a window size for the streams based on the number or rate of lost data retransmitted by a local communication proxy module based on the number or rate of lost data recovered by the remote communication proxy module and based on data successfully transmitted and acknowledged.

means for determining periodically a round trip time RTT based on a signal sent to the remote communication proxy module and a signal received from the remote communication proxy module.

means for determining periodically a bandwidth of a connection between a local communication proxy module and the remote communication proxy module.

means for limiting an amount of bandwidth used to send and receive streams between a local communication proxy module and the remote communication proxy module based on one or more of the following latency data loss and as processing capabilities of a machine on which the local communication proxy module is located.

means for receiving the streams from the local communication application module based on a determination as to whether to accelerate the streams.

49. The communication apparatus of clause 38 wherein the means for adjusting comprises means for cycling between two modes wherein a first one of the two modes comprises means for adjusting bandwidth usage and a second one of the two modes comprises means for maintaining bandwidth usage.

50. The communication apparatus of clause 38 comprising one or more computers wherein the one or more computers comprises means for displaying information means for processing information the means for receiving the means for facilitating and the means for adjusting.

The subject technology is illustrated for example according to various aspects described below. Numbered clauses are provided below for convenience. These are provided as examples and do not limit the subject technology.

a local communication proxy module e.g. or in configured to receive streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination the local communication proxy module configured to facilitate sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module the local communication proxy module configured to conceal characteristics of the network from the local communication application module the local communication proxy module configured to be transparent to the local communication application module.

2. The communication apparatus of clause 1 wherein a location of the local communication proxy module is independent of a location of the local communication application module configured to send the streams and the location of the local communication proxy module is independent of a location of the remote destination and wherein the second transmission protocol is different from the first transmission protocol.

3. The communication apparatus of clause 1 wherein the local communication proxy module is configured for a layer below a presentation layer in an Open Systems Interconnection Reference model OSI model and the remote communication proxy module is configured for a layer below a presentation layer in the OSI model.

4. The communication apparatus of clause 1 wherein the local communication proxy module is configured to cache streams received from the remote communication proxy module and configured to facilitate sending the cached streams to multiple local communication application modules.

5. The communication apparatus of clause 1 wherein the local communication proxy module is configured to determine a type of data select a compression type for the data based on the determination and compress streams to be sent to the remote communication proxy module utilizing the compression type selected and configured to decompress streams received from the remote communication proxy module.

6. The communication apparatus of clause 1 wherein the local communication proxy module is configured to encrypt streams to be sent to the remote communication proxy module and configured to decrypt streams received from the remote communication proxy module.

7. The communication apparatus of clause 1 wherein the local communication proxy module is configured to detect error in streams utilizing a cyclic redundancy check CRC or a checksum and

wherein the local communication proxy module is configured to recover corrupted data utilizing error correcting codes.

8. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive the streams from the local communication application module based on a determination as to whether to accelerate the streams.

a second local communication proxy module e.g. in or in configured to receive second streams from a second local communication application module e.g. in or in the second streams in a form utilizing the first transmission protocol and destined to the remote destination the second local communication proxy module configured to facilitate sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module the second local communication proxy module configured to conceal characteristics of the network used for the second streams from the second local communication application module the second local communication proxy module configured to be transparent to the second local communication application module.

10. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive second streams from a second local communication application module e.g. in or in the second streams in a form utilizing the first transmission protocol and destined to the remote destination wherein the local communication proxy module is configured to facilitate sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module wherein the local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and wherein the local communication proxy module is configured to be transparent to the second local communication application module.

11. The communication apparatus of clause 1 wherein the communication apparatus comprises one or more computers 

wherein the one or more computers comprises one or more displays one or more processing systems and the local communication proxy module.

12. A machine readable medium encoded with instructions for remote communication the instructions comprising code for 

receiving by a local communication proxy module streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination e.g. A of and

facilitating sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module e.g. A 

wherein the local communication proxy module is configured to conceal characteristics of the network from the local communication application module and

wherein the local communication proxy module is configured to be transparent to the local communication application module.

13. The machine readable medium of clause 12 wherein a location of the local communication proxy module is independent of a location of the local communication application module configured to send the streams and the location of the local communication proxy module is independent of a location of the remote destination and wherein the second transmission protocol is different from the first transmission protocol.

14. The machine readable medium of clause 12 wherein the local communication proxy module is configured for a layer below a presentation layer in an Open Systems Interconnection Reference model OSI model and the remote communication proxy module is configured for a layer below a presentation layer in the OSI model.

compressing streams to be sent to the remote communication proxy module utilizing the compression type selected and

19. The machine readable medium of clause 12 wherein the receiving comprises receiving the streams from the local communication application module based on a determination as to whether to accelerate the streams.

receiving second streams from a second local communication application module the second streams in a form utilizing the first transmission protocol and destined to the remote destination and

facilitating sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module wherein the second local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and

wherein the second local communication proxy module is configured to be transparent to the second local communication application module.

21. The machine readable medium of clause 12 wherein the local communication proxy module comprises code for 

receiving second streams from a second local communication application module the second streams in a form utilizing the first transmission protocol and destined to the remote destination and

facilitating sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module 

wherein the local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and

wherein the local communication proxy module is configured to be transparent to the second local communication application module.

receiving by a local communication proxy module streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination and

facilitating sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module 

wherein the local communication proxy module is configured to conceal characteristics of the network from the local communication application module and

wherein the local communication proxy module is configured to be transparent to the local communication application module.

23. The method of clause 22 wherein a location of the local communication proxy module is independent of a location of the local communication application module configured to send the streams and the location of the local communication proxy module is independent of a location of the remote destination and wherein the second transmission protocol is different from the first transmission protocol.

24. The method of clause 22 wherein the local communication proxy module is configured for a layer below a presentation layer in an Open Systems Interconnection Reference model OSI model and the remote communication proxy module is configured for a layer below a presentation layer in the OSI model.

caching streams received from the remote communication proxy module and facilitating sending the cached streams to multiple local communication application modules.

compressing streams to be sent to the remote communication proxy module utilizing the compression type selected and

encrypting streams to be sent to the remote communication proxy module and decrypting streams received from the remote communication proxy module.

29. The method of clause 22 wherein the receiving comprises receiving the streams from the local communication application module based on a determination as to whether to accelerate the streams.

receiving by a second local communication proxy module second streams from a second local communication application module the second streams in a form utilizing the first transmission protocol and destined to the remote destination and

facilitating sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module 

wherein the second local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and

wherein the second local communication proxy module is configured to be transparent to the second local communication application module.

receiving second streams from a second local communication application module the second streams in a form utilizing the first transmission protocol and destined to the remote destination and

facilitating sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module 

wherein the local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and

wherein the local communication proxy module is configured to be transparent to the second local communication application module.

means for receiving by a local communication proxy module streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination e.g. B of and

means for facilitating sending utilizing a second transmission protocol the streams in real time over a network to a remote communication proxy module e.g. B 

wherein the local communication proxy module is configured to conceal characteristics of the network from the local communication application module and

wherein the local communication proxy module is configured to be transparent to the local communication application module.

33. The communication apparatus of clause 32 wherein a location of the local communication proxy module is independent of a location of the local communication application module configured to send the streams and the location of the local communication proxy module is independent of a location of the remote destination and

34. The communication apparatus of clause 32 wherein the local communication proxy module is configured for a layer below a presentation layer in an Open Systems Interconnection Reference model OSI model and the remote communication proxy module is configured for a layer below a presentation layer in the OSI model.

means for facilitating sending the cached streams to multiple local communication application modules.

means for compressing streams to be sent to the remote communication proxy module utilizing the compression type selected and

39. The communication apparatus of clause 32 wherein the means for receiving comprises means for receiving the streams from the local communication application module based on a determination as to whether to accelerate the streams.

means for receiving by a second local communication proxy module second streams from a second local communication application module the second streams in a form utilizing the first transmission protocol and destined to the remote destination and

means for facilitating sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module 

wherein the second local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and

wherein the second local communication proxy module is configured to be transparent to the second local communication application module.

means for receiving second streams from a second local communication application module the second streams in a form utilizing the first transmission protocol and destined to the remote destination and

means for facilitating sending utilizing the second transmission protocol the second streams in real time over a network to the remote communication proxy module 

wherein the local communication proxy module is configured to conceal characteristics of the network used for the second streams from the second local communication application module and

wherein the local communication proxy module is configured to be transparent to the second local communication application module.

42. The communication apparatus of clause 32 comprising one or more computers wherein the one or more computers comprises means for displaying information means for processing information the means for receiving and the means for facilitating.

The subject technology is illustrated for example according to various aspects described below. Numbered clauses are provided below for convenience. These are provided as examples and do not limit the subject technology.

a local communication proxy module configured to receive streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination the local communication proxy module configured to add first header information comprising one or more of the following a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier the local communication proxy module configured to add second header information the local communication proxy module configured to form packets and to facilitate sending utilizing a second transmission protocol the packets in real time over a network to a remote communication proxy module.

2. The communication apparatus of clause 1 wherein the first transmission protocol comprises a transmission control protocol TCP and the second transmission protocol comprises a user datagram protocol UDP .

3. The communication apparatus of clause 1 wherein the first header information comprises a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier and

wherein a packet type identifier comprises one of the following a packet type for connection establishment a packet type for packet loss recovery and a packet type for round trip time RTT measurement.

3A. The communication apparatus of clause 1 wherein the first header information comprises a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier and

wherein packet type identifiers comprises one or more or all of the following a packet type for connection establishment a packet type for packet loss recovery a packet type for round trip time RTT measurement a packet type for data and a packet type for acknowledgement.

4. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive and sort packets from the remote communication proxy module based on packet sequence identifiers.

4A. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive a plurality of data through the remote communication proxy module from a remote communication application module at the remote destination configured to sort the plurality of data according to an order that is the same as an order in which the plurality of data have been sent by the remote communication application module and configured to facilitate delivering the plurality of data in the same order to the local communication application module.

5. The communication apparatus of clause 1 wherein the local communication proxy module is configured to facilitate sending hole punching packets to the remote communication proxy module.

6. The communication apparatus of clause 1 wherein the local communication proxy module is configured to facilitate sending hole punching packets to the remote communication proxy module to establish multiple concurrent connections with the remote destination.

7. The communication apparatus of clause 1 wherein the local communication proxy module is configured to recover lost packets utilizing a forward error correction method to minimize retransmission of packets.

7A. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive a plurality of data through the remote communication proxy module from a remote communication application module at the remote destination and configured to facilitate delivering all of the plurality of data from the remote communication application module without losing any of the plurality of data.

8. The communication apparatus of clause 1 wherein the local communication proxy module is configured to XOR n continuous packets and every mth packets until k where n m and k are determined based on packet loss and one or more round trip times RTTs and configured to facilitate sending an XOR value in a packet following the packet s corresponding packets.

8A. The communication apparatus of clause 1 wherein the local communication proxy module is configured to XOR n continuous packets and every mth packets until k where n m and k are determined based on a configuration and configured to facilitate sending an XOR value in a packet following the packet s corresponding packets wherein the configuration is predetermined.

9. The communication apparatus of clause 1 wherein the local communication proxy module is configured to set data prioritization.

10. The communication apparatus of clause 1 wherein the local communication proxy module is configured to determine a data type of a packet and assign a transmission priority to the packet based on the determination.

11. The communication apparatus of clause 1 wherein the local communication proxy module is configured to receive packets which include first and second header information from the remote communication proxy module utilizing the second transmission protocol configured to remove the first and second header information from the received packets and configured to facilitate sending packets without the removed first and second header information to the local communication application module utilizing the first transmission protocol.

12. The communication apparatus of clause 1 wherein the communication apparatus comprises one or more computers and

wherein the one or more computers comprises one or more displays one or more processing systems and the local communication proxy module.

13. A machine readable medium encoded with instructions for remote communication the instructions comprising code for 

receiving by a local communication proxy module streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination e.g. A of 

adding first header information comprising one or more of the following a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier e.g. A 

facilitating sending utilizing a second transmission protocol the packets in real time over a network to a remote communication proxy module e.g. A .

14. The machine readable medium of clause 13 wherein the first transmission protocol comprises a transmission control protocol TCP and the second transmission protocol comprises a user datagram protocol UDP .

15. The machine readable medium of clause 13 wherein the first header information comprises a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier and

wherein a packet type identifier comprises one of the following a packet type for connection establishment a packet type for packet loss recovery and a packet type for round trip time RTT measurement.

16. The machine readable medium of clause 13 wherein the instructions further comprise code for receiving and sorting packets from the remote communication proxy module based on packet sequence identifiers.

17. The machine readable medium of clause 13 wherein the instructions further comprise code for facilitating sending hole punching packets to the remote communication proxy module.

18. The machine readable medium of clause 13 wherein the instructions further comprise code for facilitating sending hole punching packets to the remote communication proxy module to establish multiple concurrent connections with the remote destination.

19. The machine readable medium of clause 13 wherein the instructions further comprise code for recovering lost packets utilizing a forward error correction method to minimize retransmission of packets.

20. The machine readable medium of clause 13 wherein the instructions further comprise code for XORing n continuous packets and every mth packets until k where n m and k are determined based on packet loss and one or more round trip times RTTs or based on a configuration and facilitating sending an XOR value in a packet following the packet s corresponding packets.

21. The machine readable medium of clause 13 wherein the instructions further comprise code for setting data prioritization.

22. The machine readable medium of clause 13 wherein the instructions further comprise code for determining a data type of a packet and assigning a transmission priority to the packet based on the determination.

23. The machine readable medium of clause 13 wherein the instructions further comprise code for receiving packets which include first and second header information by the local communication proxy module from the remote communication proxy module utilizing the second transmission protocol removing the first and second header information from the received packets and facilitating sending packets without the removed first and second header information to the local communication application module utilizing the first transmission protocol.

receiving by a local communication proxy module streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination 

adding first header information comprising one or more of the following a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier 

facilitating sending utilizing a second transmission protocol the packets in real time over a network to a remote communication proxy module.

25. The method of clause 24 wherein the first transmission protocol comprises a transmission control protocol TCP and the second transmission protocol comprises a user datagram protocol UDP .

26. The method of clause 24 wherein the first header information comprises a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier and

wherein a packet type identifier comprises one of the following a packet type for connection establishment a packet type for packet loss recovery and a packet type for round trip time RTT measurement.

27. The method of clause 24 further comprising receiving and sorting packets from the remote communication proxy module based on packet sequence identifiers.

28. The method of clause 24 further comprising facilitating sending hole punching packets to the remote communication proxy module.

29. The method of clause 24 further comprising facilitating sending hole punching packets to the remote communication proxy module to establish multiple concurrent connections with the remote destination.

30. The method of clause 24 further comprising recovering lost packets utilizing a forward error correction method to minimize retransmission of packets.

31. The method of clause 24 further comprising XORing n continuous packets and every mth packets until k where n m and k are determined based on packet loss and one or more round trip times RTTs or based on a configuration and facilitating sending an XOR value in a packet following the packet s corresponding packets.

33. The method of clause 24 further comprising determining a data type of a packet and assigning a transmission priority to the packet based on the determination.

34. The method of clause 24 further comprising receiving packets which include first and second header information by the local communication proxy module from the remote communication proxy module utilizing the second transmission protocol removing the first and second header information from the received packets and facilitating sending packets without the removed first and second header information to the local communication application module utilizing the first transmission protocol.

means for receiving by a local communication proxy module streams from a local communication application module the streams in a form utilizing a first transmission protocol and destined to a remote destination e.g. B of 

means for adding first header information comprising one or more of the following a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier e.g. B 

means for facilitating sending utilizing a second transmission protocol the packets in real time over a network to a remote communication proxy module e.g. B .

36. The communication apparatus of clause 35 wherein the first transmission protocol comprises a transmission control protocol TCP and the second transmission protocol comprises a user datagram protocol UDP .

37. The communication apparatus of clause 35 wherein the first header information comprises a packet sequence identifier a packet size a packet type identifier and additional information related to a packet type identifier and

wherein a packet type identifier comprises one of the following a packet type for connection establishment a packet type for packet loss recovery and a packet type for round trip time RTT measurement.

38. The communication apparatus of clause 35 further comprising means for receiving and sorting packets from the remote communication proxy module based on packet sequence identifiers.

39. The communication apparatus of clause 35 further comprising means for facilitating sending hole punching packets to the remote communication proxy module.

40. The communication apparatus of clause 35 further comprising means for facilitating sending hole punching packets to the remote communication proxy module to establish multiple concurrent connections with the remote destination.

41. The communication apparatus of clause 35 further comprising means for recovering lost packets utilizing a forward error correction method to minimize retransmission of packets.

42. The communication apparatus of clause 35 further comprising means for XORing n continuous packets and every mth packets until k where n m and k are determined based on packet loss and one or more round trip times RTTs or based on a configuration and means for facilitating sending an XOR value in a packet following the packet s corresponding packets.

43. The communication apparatus of clause 35 further comprising means for setting data prioritization.

44. The communication apparatus of clause 35 further comprising means for determining a data type of a packet and means for assigning a transmission priority to the packet based on the determination.

45. The communication apparatus of clause 35 further comprising means for receiving packets which include first and second header information by the local communication proxy module from the remote communication proxy module utilizing the second transmission protocol means for removing the first and second header information from the received packets and means for facilitating sending packets without the removed first and second header information to the local communication application module utilizing the first transmission protocol.

46. The communication apparatus of clause 35 comprising one or more computers wherein the one or more computers comprises means for displaying information means for processing information the means for receiving the means for adding first header information the means for adding second header information the means for forming packets and the means for facilitating sending.

In one aspect of the disclosure a communication apparatus a communication application module a transparent communication proxy module and a communication proxy module may refer to modules and as shown in or the modules shown in . The subject technology however is not limited to these exemplary modules shown in various figures of this disclosure. In other examples a communication apparatus a communication application module a transparent communication proxy module and communication proxy module may be represented by other types of modules structures blocks components devices or systems.

Those of skill in the art would appreciate that the various illustrative blocks modules elements components methods and algorithms described herein may be implemented as electronic hardware computer software or combinations of both. For example module and or in may be implemented as electronic hardware computer software or combinations of both. In one aspect a module e.g. module and or in may be an apparatus since the module s may include instructions encoded or stored on a machine readable medium on a computer readable medium on another device or on a portion thereof. In one aspect a module s may be software e.g. an application . In another aspect a module s may be hardware e.g. a FPGA or a PLD configured to perform the functions described a pre programmed general purpose computer or a special purpose electronic or optical device .

To illustrate this interchangeability of hardware and software various illustrative blocks modules elements components methods and algorithms have been described above generally in terms of their functionality. Whether such functionality is implemented as hardware or software depends upon the particular application and design constraints imposed on the overall system. Skilled artisans may implement the described functionality in varying ways for each particular application. Various components and blocks may be arranged differently e.g. arranged in a different order or partitioned in a different way all without departing from the scope of the subject technology.

It is understood that the specific order or hierarchy of steps in the processes disclosed is an illustration of exemplary approaches. Based upon design preferences it is understood that the specific order or hierarchy of steps in the processes may be rearranged. Some of the steps may be performed simultaneously. The accompanying method claims present elements of the various steps in a sample order and are not meant to be limited to the specific order or hierarchy presented.

In one aspect when a claim recites a first module configured to perform a first function and a second module configured to perform a second function the scope of such a claim may cover a module configured to perform both the first function and the second function.

The previous description is provided to enable any person skilled in the art to practice the various aspects described herein. The previous description provides various examples of the subject technology and the subject technology is not limited to these examples. Various modifications to these aspects will be readily apparent to those skilled in the art and the generic principles defined herein may be applied to other aspects. Thus the claims are not intended to be limited to the aspects shown herein but is to be accorded the full scope consistent with the language claims wherein reference to an element in the singular is not intended to mean one and only one unless specifically so stated but rather one or more. Unless specifically stated otherwise the term some refers to one or more. Pronouns in the masculine e.g. his include the feminine and neuter gender e.g. her and its and vice versa. Headings and subheadings if any are used for convenience only and do not limit the invention.

A phrase such as an aspect does not imply that such aspect is essential to the subject technology or that such aspect applies to all configurations of the subject technology. A disclosure relating to an aspect may apply to all configurations or one or more configurations. An aspect may provide one or more examples. A phrase such as an aspect may refer to one or more aspects and vice versa. A phrase such as an embodiment does not imply that such embodiment is essential to the subject technology or that such embodiment applies to all configurations of the subject technology. A disclosure relating to an embodiment may apply to all embodiments or one or more embodiments. An embodiment may provide one or more examples. A phrase such an embodiment may refer to one or more embodiments and vice versa. A phrase such as a configuration does not imply that such configuration is essential to the subject technology or that such configuration applies to all configurations of the subject technology. A disclosure relating to a configuration may apply to all configurations or one or more configurations. A configuration may provide one or more examples. A phrase such a configuration may refer to one or more configurations and vice versa.

The word exemplary is used herein to mean serving as an example or illustration. Any aspect or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspects or designs.

All structural and functional equivalents to the elements of the various aspects described throughout this disclosure that are known or later come to be known to those of ordinary skill in the art are expressly incorporated herein by reference and are intended to be encompassed by the claims. Moreover nothing disclosed herein is intended to be dedicated to the public regardless of whether such disclosure is explicitly recited in the claims. No claim element is to be construed under the provisions of 35 U.S.C. 112 sixth paragraph unless the element is expressly recited using the phrase means for or in the case of a method claim the element is recited using the phrase step for. Furthermore to the extent that the term include have or the like is used in the description or the claims such term is intended to be inclusive in a manner similar to the term comprise as comprise is interpreted when employed as a transitional word in a claim.

