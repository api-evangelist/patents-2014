---

title: Automatic generation of API classes
abstract: A compiler for compiling a server application is disclosed wherein the server is configured to automatically generate an API (Application Programming Interface) for use is a client device. The API allows communication between the client device and the compiled server application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09557973&OS=09557973&RS=09557973
owner: KING.COM LTD.
number: 09557973
owner_city: St. Julians
owner_country: MT
publication_date: 20140403
---
This application is based on and claims priority to Great Britain Application No. GB 1306036.3 filed Apr. 3 2013 the entire contents of which is fully incorporated herein by reference.

Some embodiments relate to a method and system for data cache handling in a server. The server may be used to handle data requests for the purposes of providing information to computer gaming software running on a client device.

In computer gaming it is commonplace to communicate over a network to provide additional functionality. This communication is often performed between a server and a client device. In order to assist in communication between a client device and a server an Application Programming Interface API is often used to provide an interface layer at the client.

According to a first embodiment there is provided a method comprising receiving programming code for a server application determining at least one programming code for a corresponding client interface dependent on at least one rule and compiling the received programming code into an executable server application.

The method may comprise determining from said abstract syntax tree if said received programming code comprises at least one unsupported variable type.

The method may comprise displaying an indication that said received programming contains an unsupported programming code dependent on said determining.

Said determining at least one programming code may be dependent on the contents of said abstract syntax tree.

The method may comprise determining a plurality of programming codes for different corresponding client interfaces dependent on at least one rule.

The at least one programming code may be automatically updated when the programming code for the server application is compiled.

According to a second aspect there is provided a compiler configured to receive programming code for a server application determine at least one programming code for a corresponding client interface dependent on at least one rule and compile the received programming code into an executable server application.

The compiler may be configured to construct an abstract syntax tree from said received programming code.

The compiler may be configured to determine from said abstract syntax tree if said received programming code comprises at least one unsupported variable type.

The compiler may be configured to display an indication that said received programming contains an unsupported programming code dependent on said determining.

Said determining at least one programming code may be dependent on the contents of said abstract syntax tree.

The compiler may be configured to determine a plurality of programming codes for different corresponding client interfaces dependent on at least one rule.

The compiler may be configured to automatically update the at least one programming code when the programming code for the server application is compiled.

A schematic view of a user device according to an embodiment is shown in . All of the blocks shown are implemented by suitable circuitry. The blocks may be implemented in hardware and or software. The user device may have a control part . The control part has one or more processors and one or more memories . The control part is also shown as having a graphics controller and a sound controller . It should be appreciated that one or other or both of the graphics controller and sound controller may be provided by the one or more processors .

The graphics controller is configured to provide a video output . The sound controller is configured to provide an audio output . The controller has an interface allowing the device to be able to communicate with a network such as the Internet or other communication infrastructure.

The video output is provided to a display . The audio output is provided to an audio device such as a speaker and or earphone s .

The device has an input device . The input device can take any suitable format and can be one or more of a keyboard mouse touch screen joystick or game controller. It should be appreciated that the display may in some embodiments also provide the input device by way of an integrated touch screen for example.

The blocks of the controller are configured to communicate with each other by an interconnect such as a bus or any other suitable interconnect and or by point to point communication.

It should be appreciated that in some embodiments the controller may be implemented by one or more integrated circuits at least in part.

The user device is shown by way of example only. In alternative embodiments one or more of the parts may be omitted. Alternatively or additionally some embodiments may comprise one or more other parts. Alternatively or additionally one or more parts may be combined.

The server may communicate via for instance the internet to one or more user devices shown in the figure by way of example as user devices and and may further provide connections to a social network .

The server or farm may be connected as shown to server and to database via link . Link may be wired wireless and or provided via or through networks such as the internet as known to those persons skilled in the art. The control module provides control and update of data in the database s .

Reference is made to which shows a client device connected to a server. Client device has a network interface controller which is configured to communicate over a network with a server . Network may be the internet. Client device has at least one processor and at least one memory . The at least one processor is configured to with at the least one memory to run an operating system . One or more applications are configured to run on client device . The one or more applications may comprise one or more game applications. The one or more applications may communicate with server .

Server is configured to run a back end server application . Back end server application may be configured to store and retrieve data in a database . The one or more applications of the client device may wish to access data stored in database or may wish to communicate with another client device via server . The one or more applications of client device must know how to communicate with back end server application . The rules required to communicate with back end server application are stored in client API Application Programming Interface .

Client API may be compiled into an application for example an application for a mobile device for example a device running iOS may execute pre compiled applications which comprise the client API . Alternatively the client API may be external to the applications. For example on a computer running a Windows operating system the client API may be stored in a DLL Dynamic Link Library which may be accessed by application running on the computer. The client API may therefore be provided with or separately to the applications. Alternatively the application may be a web browser running a web application embedded in a web page. The client API may be code written in a web language to allow the web application to communicate with the server. For example the client API may be written in Javascript or Flash.

It is commonplace for both applications and back end server applications to require updating. This may be for example to introduce new features or fix existing bugs with either application. It may be the case that an update to the back end server application will require an update to the client API in order to maintain compatibility. It is however preferable to maintain backwards compatibility with the client API to remove unnecessary updating so that even if the client API is not updated it will still be able to communicate successfully to the server but will not be able to benefit from the additional functionality.

Whenever changes are made to the back end server application that affects the communication with client devices the client API must also be changed. Traditionally these changes will require a programmer to redesign at least some part of the client API code.

According to an embodiment of the present application a method for compiling the server code is used to automatically generate an updated client API.

A compiler typically consists of three components the front end the middle end and the back end. The front end of the compiler verifies the syntax of the code and produces an abstract syntax tree AST . An AST is a data structure produced by syntax analysis and represents the structure of the source code. The middle end of the compiler provides optimisation whilst the back end generates the final assembly code.

According to one embodiment the AST may be analysed to produce a client API according to a set of rules. The compiler may be configured to produce multiple client APIs for use on different operating systems or in different programming languages.

Reference is made to which shows the method of traditional compiler. The compiler receives source code to be compiled. Source code is analysed by front end . The syntax is verified and an abstract syntax tree is generated. The processed source code is then passed to the middle end of the compiler. Middle end optimises the source code which is then passed to back end . Back end generates the assembly code for execution on a processor.

Reference is made to which shows a method according to an embodiment. The abstract syntax tree output from the front end is analysed and used to generate client API . The compiler is configured to produce a protocol specification from the abstract syntax tree. From this client API code in one or more languages may be produced to interface between a client application and the server using the determined protocol specification.

Different client devices may run different operating systems which may require being programmed in different languages. These different programming languages may support different variable types. Accordingly if a back end server application uses types unsupported by these programming languages some client devices may be unable to communicate with the server. To avoid this problem the compiler may verify that all types requires in the protocol are supported by all target programming languages on all target devices. In one embodiment the compiler may be configured to display an indication that an unsupported type has been used. For example an error message may be displayed. In another embodiment the compiler may be configured to exclude the use of these variables types. In yet another embodiment the compiler may be configured to substitute unsupported types with compatible alternatives.

Reference is made to claim which shows a method according to an embodiment. Method comprises receiving the programming code to be compiled at step . At step a client API for communication with the server application is determined. At step the server application is compiled.

