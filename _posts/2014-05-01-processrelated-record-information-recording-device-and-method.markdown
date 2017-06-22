---

title: Process-related record information recording device and method
abstract: An image forming device is capable of executing an application. In the image forming device, a determining unit is configured to determine, in response to a request of execution of a communication process from the application, whether the communication process is an encrypted communication based on contents of a call stack which stores the request. A log recording unit is configured to record log information of the communication process in a storage device when the communication process is determined as being an encrypted communication.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09047031&OS=09047031&RS=09047031
owner: RICOH COMPANY, LTD.
number: 09047031
owner_city: Tokyo
owner_country: JP
publication_date: 20140501
---
The present application is a continuation of U.S. patent application Ser. No. 12 437 598 filed on May 8 2009 which is based upon and claims the benefit of priority of Japanese Patent Application No. 2008 139759 filed on May 28 2008. The disclosures of the prior applications are hereby incorporated herein in their entirety by reference.

This invention relates to an image forming device a log recording method and a computer readable recording medium which are adapted to record log information concerning the processing performed by an application.

In recent years some image forming devices called multi function peripherals are provided with the environment for developing and deploying applications and it is possible to develop and deploy new applications on the image forming devices even after the shipment by using the API application programming interface supplied by the environment. For example see Japanese Laid Open Patent Application No. 2005 269619.

The image forming device as disclosed in Japanese Laid Open Patent Application No. 2005 269619 is able to implement not only the applications developed by the vendor of the image forming device but also the applications developed by the third vendor. Hence it is possible to remarkably improve the ability to expand the functions of the image forming device.

However an unspecified application may be implemented in the image forming device and the security of the image forming device in such a case may be degraded. It is difficult to determine prior to the implementation whether operation of each of the individual applications is inappropriate for protection of confidential information in the image forming device.

In recent years many image forming devices are provided with mass storage and such image forming devices are capable of managing various kinds of confidential information personal information of the users image data of the scanned confidential documents etc. stored in the mass storage. Thus it is desired to prevent an unspecified application from illegally accessing the confidential information in the image forming device.

Recording of log information is an effective mechanism for detecting existence of an unsuitable application which illegally accesses confidential information in the image forming device. However according to the related art it is necessary to implement a certain function e.g. calling of a function of recording logs into the application appropriately in order to perform recording of log information.

In the case of the mechanism according to the related art if the function is implemented in the application inappropriately failure of recording of log information may occur. As a result it is impossible to detect an unsuitable application which may illegally access the confidential information in the image forming device.

In one aspect of the invention the present disclosure provides an improved image forming device in which the above described problems are eliminated.

In one aspect of the invention the present disclosure provides an image forming device a log recording method and a computer readable recording medium which are able to record appropriately log information with respect to a process performed by an application in the image forming device.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides an image forming device which is capable of executing an application the image forming device comprising a determining unit to determine in response to a request of execution of a communication process from the application whether the communication process is an encrypted communication based on contents of a call stack which stores the request and a log recording unit to record log information of the communication process in a storage device when the communication process is determined as being an encrypted communication.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides a log recording method which is performed by an image forming device capable of executing an application the log recording method comprising determining in response to a request of execution of a communication process from the application whether the communication process is an encrypted communication based on contents of a call stack which stores the request and recording log information of the communication process in a storage device when the communication process is determined as being an encrypted communication.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides a computer readable recording medium storing a program which when executed by a processing unit of an image forming device capable of executing an application causes the processing unit to perform a log recording method the log recording method comprising determining in response to a request of execution of a communication process from the application whether the communication process is an encrypted communication based on contents of a call stack which stores the request and recording log information of the communication process in a storage device when the communication process is determined as being an encrypted communication.

Other objects features and advantages of the present invention will become more apparent from the following detailed description when read in conjunction with the accompanying drawings.

A description will be given of embodiments of the invention with reference to the accompanying drawings.

Hereinafter when the image forming devices etc. are referred to collectively each device will be simply called the image forming device . For example each of the image forming devices may be a multi function peripheral MFP in which multiple image forming functions including functions of a copier a facsimile a printer and a scanner are integrated in a single housing.

The log collecting server is a computer which collects various kinds of log information generated in the image forming devices and manages them collectively. Alternatively two or more log collecting servers may be arranged in the system of .

The controller includes a CPU a RAM a ROM and a HDD . The ROM is arranged to store various kinds of programs and data used by the programs. Moreover the ROM may be arranged to store a program which when executed by the CPU causes the CPU to perform a log recording method of an embodiment of the invention which will be described later.

The RAM is used as a program storage area to which programs are loaded and used as a work area which is used by the loaded programs etc. The CPU carries out the functions of the image forming device which will be described later by performing the procedure in accordance with the program loaded to the RAM .

The HDD is arranged to store various kinds of data for example image data of scanned documents . Moreover the HDD may be arranged to store a program which when executed by the CPU causes the CPU to perform a log recording method of an embodiment of the invention which will be described later.

In the image forming device of the embodiment shown in at least one of the ROM and the HDD constitutes a computer readable recording medium of an embodiment of the invention.

The scanner is arranged to optically read image data from an original document. The printer is arranged to print image data on a print sheet. The modem is arranged to connect the image forming device to a public telephone line and the modem is used to perform the transmission and reception of image data in accordance with the FAX communication protocol. The network interface is arranged to connect the image forming device to the network . The operation panel is provided with a display unit such as a liquid crystal panel and operational buttons which are arranged to receive data input from the user and output notices of operational information to the user.

The program which causes a computer or the CPU of the image forming device to perform the log recording method according to the invention may be installed in the image forming device in various manners. For example a removable recording medium such as an SD secure digital card which stores the above mentioned program in advance is inserted to the image forming device and the program is read from the recording medium and installed in the image forming device such that the program is executable by the CPU . The SD card in such a case may be a computer readable recording medium of an embodiment of the invention. Alternatively the above mentioned program may be downloaded to the image forming device via the network and installed such that the program is executable by the CPU .

As shown in the software items of the image forming device of this embodiment include an SDK software development kit application an SDK platform a log service and a socket library . These software items are loaded to the RAM and the corresponding function is performed by causing the CPU to perform the processing of the corresponding software item.

The log service is configured to record the logs of the communications especially encrypted communications performed by the SDK application in a log recording area . The SDK application will be described later. Also the log service is configured to control the transmission of the logs recorded in the log recording area to the log collecting server .

The log storage area is a storage area in the RAM or the HDD for recording the logs therein. The socket library is a socket library arranged to provide the API used in TCP IP communications for the upper layer modules.

The SDK platform is a software platform arranged to provide the environment for executing the SDK application . In the composition of a SDK common process module a JVM Java registered trademark virtual machine a JSSE Java secure socket extension a communication service and a communication log service are contained in the SDK platform .

The JVM converts the Java bytecodes into the native codes that can be run on the OS and executes the native codes. The software components of the SDK platform illustrated above the block of the JVM in are installed in the Java bytecodes. The JSSE is a package of the security component of the Java standard edition platform. The JSSE provides both an application programming interface API framework for the Java standard encrypted communication e.g. SSL communication and implementation of the API.

The communication service and the communication log service are bundles running on the OSGi Open Service Gateway initiative framework. The OSGi framework is the standardized technology by the OSGi alliance which is a software platform to provide the execution environment for executing the software components developed based on the open software component technology using the Java language. The software components written in the Java language are implemented in the form of the bundles on the OSGi framework. A bundle is constituted by a JAR Java archive file and such bundles can be dynamically installed independently of each other without requiring the rebooting of the device.

The communication service is configured to control the communication process according to the communication protocol of the application layer such as HTTP hypertext transfer protocol FTP file transfer protocol SNMP simple network management protocol or LDAP lightweight directory access protocol and configured to provide the interface of the communication process to the SDK application . When a request of encrypted communication is received from the SDK application the communication service performs encrypted communication by using the JSSE . The communication log service is configured to control the process of recording the log communication log when a communication request is received from the SDK application .

In addition the class library concerning the Java standard classes and the extended classes for the image forming device is also included in the SDK platform . For example the security manager is illustrated in as a part of the JVM . The security manager is implemented by the extended class of the Java standard security manager class. Hence the security manager restricts the accessing by the SDK application to the resources such as files network sockets and the printer in accordance with the access control information which is defined in advance in the policy file.

Specifically the SDK platform is arranged so that each time the accessing to the resources takes place a call is sent to the security manager . The security manager determines the permission of accessing to the resources in response to the call received. In this embodiment by using this mechanism the security manager detects execution of the encrypted communication by the SDK application .

The SDK application is an application which is developed by using the SDK software development kit dedicated for use in the SDK platform . It is possible to install two or more SDK applications in the SDK platform .

A description will be given of the procedure of the image forming device of the first embodiment. is a flowchart for explaining the outline process performed by the image forming device of the first embodiment.

In the image forming device the SDK application which is about to start communication sends a request for performing the communication process to the SDK platform S .

Next the image forming device determines whether the communication requested by the SDK application is an encrypted communication S .

When it is determined in step S that the requested communication is an encrypted communication the image forming device performs the preparation for the recording of log information S . Specifically the image forming device detects the values of information items to be recorded as log information. For example the image forming device detects a communication protocol and an encryption protocol which are used for the requested communication.

Next the image forming device opens the communication socket S and records the log information S . Next the image forming device performs the communication process in accordance with the protocol specified by the SDK application S .

On the other hand when it is determined in S that the requested communication is not an encrypted communication the image forming device determines whether the requested communication is an in device communication S . The in device communication means an internal communication between the software components or the programs within the image forming device for example an inter process communication .

When it is determined in step S that the requested communication is not an in device communication the image forming the image forming device detects the communication protocol used for the requested communication in order to perform the preparation for the recording of log information S . In this case the requested communication is not an encrypted communication and the value of the encryption protocol is set to null. After the step S is performed the steps S S are performed.

When it is determined in step S that the requested communication is an in device communication the image forming device opens the communication socket S and performs the communication process in accordance with the protocol specified by the SDK application S . In the case of the in device communication the recording of log information is not performed. This is because the level of significance of the in device communication from the viewpoint of security is considered relatively low. In other words the level of significance of the communication between the image forming device and an external device via the network is considered relatively high.

If the log information for all the in device communication is recorded the log recording area will be full of the logs in a short time. When it is desired to further restrict the consumption of the log recording area the image forming device may be arranged so that the log information only for the encrypted communication is recorded. It is considered that in the case of the encrypted communication the content of the communication itself is important. Therefore in such a case the log information only for the encrypted communication is recorded and it is possible to record the log information concerning the important communication and restrict the consumption of the log recording area to a certain degree.

Next a description will be given of the procedure of the image forming device of the first embodiment. is a sequence diagram for explaining the procedure of the image forming device of the first embodiment.

If the SDK application sends a request for performing an encrypted communication according to a desired one of the communication protocols HTTP FTP SNMP LDAP etc. to the communication service the communication service sends a request for performing the encrypted communication to the JSSE S . For the sake of convenience the illustration of the communication service in is omitted. For example transmission of the request from the SDK application to the communication service is carried out by calling the method of a class according to a requested communication protocol. Namely a class exists for each of the communication protocols contained in the communication service .

Similarly transmission of the request from the communication service to the JSSE is carried out by calling the method of the class according to the communication requested by the SDK application among the classes contained in the JSSE . The called class the class in the JSSE in this case may vary depending on the communication protocol specified by the SDK application or on whether the communication as a client is requested or the communication as a server is requested.

The called class in the JSSE notifies the security manager that the class in the JSSE has been called which means occurrence of a communication request S .

Next the security manager detects a communication protocol and an encryption protocol which are to be used for the requested communication S . The detection of the protocols is performed by the stack tracing. Generally the calling relations between the classes or the hierarchical conditions of the calls are recorded in a stack call stack which is provided within the RAM . In step S the security manager refers to the call stack in the RAM traces the path of the call from the JSSE and detects the called class class name in the JSSE and the called class class name in the communication service .

Specifically the communication protocol to be used is detected by the class name of the called class in the communication service and by the class name of the called class in the JSSE the reception of a request of encrypted communication and the encryption protocol to be used for the encrypted communication are detected.

When the requested communication is not an encrypted communication the calling of the method of the class in the JSSE is not performed. Therefore when a class concerning encrypted communication the class in the JSSE is not contained in the call stack the security manager determines that the requested communication is not an encrypted communication.

When the requested communication is an encrypted communication the security manager notifies to the communication log service identifiers for example protocol names of the detected communication protocol and the detected encryption protocol as log information S . The communication log service transmits the log information and a request of recording of the log information to the log service via the SDK common process module S S .

Next the log service checks the available capacity of the log recording area and determines whether the recording of the log information is permitted S .

When the available capacity of the log recording area is sufficient the log service records the log information in the log recording area S . At this time the log service records the identifiers of the communication protocol and the encryption protocol a time information a log identifier etc. The log identifier is an ID specific to each of one or more communication logs one for each log recording .

Next the log service notifies the SDK common process module that the recording of the log information has been done successfully S . After the recording of the log information has been done successfully the SDK common process module notifies the security manager that performance of the communication process is enabled S .

In response to the notice from the SDK common process module the security manager transmits to the JSSE a response to the communication request in the step S indicating that performance of the communication process is enabled S . In response to the permission from the security manager the JSSE starts performing the communication process e.g. communication start transmission or reception of data communication end requested by the SDK application using the socket library S .

The JSSE receives the information indicating a result of the communication process success or failure of the communication process from the socket library S . Next the JSSE transmits the corresponding information to the SDK application S .

On the other hand when it is determined in step S that the log recording area is full or nearly full of logs or the available capacity of the log recording area is below a predetermined value and the recording of the log information is impossible the log service notifies the SDK common process module of the failure of the recording of the log information S .

After the notice of failure of the recording of the log information is received the SDK common process module notifies the security manager that performance of the communication process is disabled S . In response to the notice from the SDK common process module the security manager transmits to the JSSE a response indicating that performance of the communication process by the communication request in step S is disabled S .

In response to the response from the security manager about the disabled communication process the JSSE notifies the SDK application that performance of the communication process requested by the SDK application is disabled S .

Alternatively the procedure of may be arranged so that when the log recording area is full or nearly full of logs the log service transmits the log information of the logs recorded in the log recording area to the log collecting server . In this case if the log information after it is transmitted to the log collecting server is deleted from the log recording area it is possible to perform the communication process while holding the available capacity of the log recording area at a sufficient level. However when the storage of the log collecting server at this time is full or nearly full of logs the procedure of the steps S S is performed.

Transmission of the log information to the log collecting server may be performed periodically. Alternatively transmission of the log information to the log collecting server may be performed each time the log information is recorded. The timing at which the log information should be transmitted to the log collecting server may be set up in accordance with a setting parameter input by a system administrator using the operation panel . In this case the content of the setting parameter the information indicating the timing of the transmission is stored into the HDD . The log service refers to the content of the setting parameter stored in the HDD and determines the timing of the transmission of the log information to the log collecting server .

As described above according to the image forming device of the first embodiment the recording of the log information of encrypted communication can be compulsorily performed even if an explicit request for recording the log information is not received from the SDK application . It is possible to prevent the failure of recording the log information and it is possible to increase the possibility of detection of an unsuitable SDK application .

Moreover according to the image forming device of the first embodiment the log information of encrypted communication which is important for security can be recorded and a rapid increase of the amount of the accumulated log information can be avoided. When the recording of the log information is impossible performance of the communication process is not permitted. It is possible to avoid the occurrence of the situation in which a communication process unsuitable for the image forming device is performed by a request from an unspecified application but no trace of the unsuitable process is left in the image forming device.

Next a description will be given of an image forming device of a second embodiment of the invention. The second embodiment relates to recording of job logs job records .

In the following only the elements of the second embodiment which are different from the first embodiment will be explained. Unless otherwise specified the elements in the second embodiment are essentially the same as corresponding elements in the first embodiment described above.

In the composition of a job service an application manager a job control module an authentication manager and a job log manager are contained in the SDK platform .

The job service controls the hardware resources of the image forming device with respect to a job among the jobs print scan copy fax transmission etc. the execution of which is requested.

The application manager manages the information concerning the SDK application which information is called application information . For example at a time of installation of the SDK application the correspondence information to associate a product ID of the SDK application and an identifier or application name of the SDK application is registered in the application manager . The application manager records the correspondence information in the HDD and manages the application information. The product ID is a unique ID assigned for each of individual products of the SDK application .

The job control module the authentication manager and the job log manager are bundles running on the OSGi framework. The job control module receives a request of execution of a job from the SDK application .

The authentication manager performs authentication of a user when the user logs in the image forming device . User information including a user name and a password is stored in the HDD of the image forming device . The authentication manager authenticates the user based on the comparison of the stored user information with input user information including a user name and a password input to the login screen displayed on the operation panel . The user name and user ID of the authenticated user are retained in the RAM . The authenticated user is allowed as a login user to cause the image forming device to perform a job using the SDK application of the image forming device .

The job log manager controls the recording process of a log job log in response to the request of execution of a job received from the SDK application .

A description will be given of the procedure of the image forming device of the second embodiment. is a flowchart for explaining the outline process performed by the image forming device of the second embodiment.

In the image forming device the SDK application outputs a request of execution of a job print scan copy or FAX transmission which request is input by the user through the operation panel to the SDK platform S .

In response to the request of execution of the job the job service generates job information to be output as a job log S . For example the job information contains the information parameters on the execution conditions of the job. For example the parameters on the execution conditions of the job are input by the user concurrently with the inputting of the job execution request. When the job information is generated successfully in step S the job service notifies the job log manager of the generated job information S .

Moreover in response to the request of execution of the job the authentication manager acquires from the RAM the user information user name and password of the login user at the time of inputting the job execution request S . When the user information is acquired successfully in step S the authentication manager notifies the job log manager of the acquired user information S .

Moreover in response to the request of execution of the job the application manager acquires the application information product ID of the SDK application which is the source of the job execution request S . When the product ID is acquired successfully in step S the application manager notifies the job log manager of the acquired product ID S .

After the job information the user information and the product ID are received the job log manager generates log information including the received information items S .

Next the log service checks the available capacity of the log recording area and determines whether the recording of the log information is permitted S .

When it is determined in step S that the recording of the log information is permitted the job service controls execution of the requested job S . The log service records the log information in the log recording area S . At this time the job information the user information and the product ID are contained in the log information. Therefore the log information which indicates who has requested the job the user information which application has been used the product ID and which job has been performed the job information is recorded as a job log.

As shown in the flowchart of in the respective cases in which the job information is not generated successfully in the step S the user information is not acquired successfully in the step S the product ID is not acquired successfully in the step S and the recording of the log information is impossible in the step S the execution of the job is stopped and the recording of the log information is not performed.

A description will be given of the procedure of the image forming device of the second embodiment. is a sequence diagram for explaining the procedure of the image forming device of the second embodiment.

As shown in the SDK application outputs a request of execution of a job print scan copy FAX transmission etc. which request is input by the user through the operation panel to the job control module S . The parameters of the job executing conditions job conditions are contained in the execution request.

Next the job control module sends the parameters of the job conditions to the job service and requests execution of the job to the job service S .

Next the job service sends a notice of job execution indicating that the execution of the job is started to both the authentication manager and the application manager S S . The job service generates the job information including the job conditions and notifies the job log manager of the generated job information S .

In response to the notice of job execution received in step S the authentication manager acquires the user information user name and password of the current login user from the RAM and notifies the job log manager of the acquired user information S .

In response to the notice of job execution received in step S the application manager acquires the product ID of the SDK application which is the source of the job execution request based on the attribution information of the thread concerning the notice of job execution S .

In this embodiment a thread group is used as the attribution information of the thread. The thread group is the Java standard mechanism which is constituted by a set of threads and thread groups. One or more threads can be associated with one thread group. A name thread group name may be attached to a thread group. In each thread a thread group to which the thread belongs can be detected.

In this embodiment a thread and a thread group are generated for each of the SDK applications in the image forming device . Namely one thread group is assigned to one SDK application and the identifier application name of the SDK application is set to the thread group name of the thread group.

In this embodiment the job control module the job service and the application manager are not the programs which operate as the processes or threads independently of each other but constitute a program module a set of functions or classes which operates on the thread which is the same as that of the SDK application . Hence the application manager acquires the application name of the SDK application which is the source of the job execution request based on the thread group name of the thread group to which the thread of the application manager belongs.

The application manager acquires the product ID of the SDK application which is the source of the job execution request based on the acquired application name and the correspondence information to associate the application name generated at the time of installation of the SDK application with the product ID. Then the application manager notifies the job log manager of the acquired product ID as identification information of the SDK application which is the source of the job execution request S .

After the job information the user information and the product ID are received the job log manager generates log information including the received information items S .

Next the job log manager requests recording of the generated log information to the log service through the SDK common process module S S .

Next the log service checks the available capacity of the log recording area and determines whether the recording of the log information is permitted S .

When the available capacity of the log recording area is sufficient the log service records the log information in the log recording area S . At this time the log service records a time information a log ID etc. in addition to the job information the user information and the product ID.

Next the log service notifies the SDK common process module that the recording of the log information has been done successfully S . After the recording of the log information has been done successfully the SDK common process module notifies the job service that execution of the job is enabled S .

In response to the notice the job service controls execution of the job requested by the SDK application S . Next the job service transmits the information indicating the running state of the job or a result of the job execution to the SDK application through the job control module S S .

Alternatively the procedure of may be arranged so that when the log service determines in step S that the recording of the log information is impossible or inappropriate the log service transmits the log information currently recorded in the log recording area to the log collecting server via the network and delete the log information from the log recording area after the transmission is done. This procedure is similar to that in the previously described first embodiment. In addition the timing of transmission of the log information to the log collecting server may be selected in a manner similar to the first embodiment.

As described above according to the image forming device of the second embodiment the recording of the log information with respect to the execution of a job can be compulsorily performed even if an explicit request for recording the log information is not received from the SDK application . It is possible to prevent the failure of recording the log information and it is possible to increase the possibility of detection of an unsuitable SDK application .

Moreover according to the image forming device of the second embodiment when the recording of the log information is impossible execution of the job is not permitted. It is possible to avoid the occurrence of the situation in which a job unsuitable for protection of the confidential information in the image forming device is performed by a request from an unspecified application but no trace of execution of the unsuitable job is left in the image forming device.

Moreover the image forming device of the first embodiment may be arranged so that the user information of a login user used at the time of an encrypted communication process and the identifier of the SDK application which is the source requesting execution of an encrypted communication process are included in the log information and the log information is recorded in a manner similar to the second embodiment.

According to the present invention it is possible to provide an image forming device a log recording method and a computer readable recording medium which are able to record appropriately log information with respect to a process performed by an application in the image forming device.

The present invention is not limited to the specifically disclosed embodiments and variations and modifications may be made without departing from the scope of the present invention.

