---

title: Service providing system and service providing method for providing a service to a service usage device connected via a network
abstract: A service providing system includes an information processing device and provides a service to a service usage device connected via a network. The service providing system includes a storage unit for storing management information, in which service identification information, user identification information, and service usage device identification information are associated; an authentication unit for performing authentication, by using authentication information of the user or the device acquired from the service usage device; a service specification unit for specifying the service associated with the authentication information, based on the authenticated authentication information and the management information; and an execution unit configured to execute a process according to a usage request to use the service, when the usage request specified by the service specification unit is acquired, and to execute control of output, based on contents of an output request from the service usage device instructed by the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09189187&OS=09189187&RS=09189187
owner: RICOH COMPANY, LTD.
number: 09189187
owner_city: Tokyo
owner_country: JP
publication_date: 20140723
---
As a technology for analyzing print contents and performing print control in accordance with analysis results there is known a method for reducing the load when sorting document data that has been printed. Specifically the print output of each page is controlled by detecting a keyword set in advance from character strings expressed by print control data generated as data for printing the document data see for example Patent Document 1 .

Furthermore for example there is known a method of detecting overlapping print jobs for the purpose of preventing needless print jobs from being printed as a result of a transmission error of a print job by the user in which the user erroneously sends an execution instruction for the same print job see for example Patent Document 2 .

The present invention provides a service providing system and a service providing method in which one or more of the above described disadvantages are eliminated.

According to an aspect of the present invention there is provided a service providing system for providing a service to a service usage device connected via a network the service providing system being constituted by at least one information processing device the service providing system including a management information storage unit configured to store management information in which service identification information of the service user identification information of a user using the service and device identification information of the service usage device are associated with each other an authentication unit configured to execute an authentication process by using as authentication information user authentication information used for user authentication or device authentication information used for device authentication acquired from the service usage device a service specification unit configured to specify the service associated with the authentication information based on the authentication information authenticated by the authentication unit and the management information and an execution unit configured to execute a process according to a usage request to use the service when the usage request to use the service specified by the service specification unit is acquired from the service usage device wherein the execution unit executes control of output based on contents of an output request from the service usage device instructed by the user.

According to an aspect of the present invention there is provided a service providing method performed in a service providing system for providing a service to a service usage device connected via a network the service providing system being constituted by at least one information processing device the service providing method including storing management information in which service identification information of the service user identification information of a user using the service and device identification information of the service usage device are associated with each other executing an authentication process by using as authentication information user authentication information used for user authentication or device authentication information used for device authentication acquired from the service usage device specifying the service associated with the authentication information based on the authenticated authentication information and the management information and executing a process according to a usage request to use the service when the usage request to use the specified service is acquired from the service usage device wherein the executing of the authentication process includes executing control of output based on contents of an output request from the service usage device instructed by the user.

According to an aspect of the present invention there is provided a non transitory computer readable recording medium storing a program that causes a computer to execute a process performed in a service providing system for providing a service to a service usage device connected via a network the service providing system being constituted by at least one information processing device the process including storing management information in which service identification information of the service user identification information of a user using the service and device identification information of the service usage device are associated with each other executing an authentication process by using as authentication information user authentication information used for user authentication or device authentication information used for device authentication acquired from the service usage device specifying the service associated with the authentication information based on the authenticated authentication information and the management information and executing a process according to a usage request to use the service when the usage request to use the specified service is acquired from the service usage device wherein the executing of the authentication process includes executing control of output based on contents of an output request from the service usage device instructed by the user.

A description is given with reference to the accompanying drawings of embodiments of the present invention.

In the network N in an office a firewall FW is installed. The firewall FW restricts accesses from unauthorized access sources. In the network N of the service providing system an access control device is installed. The access control device restricts accesses made via the network N.

The network N in an office is a private network that is inside the firewall FW. To the network N a terminal device an image forming device an authentication device and another device are connected.

The terminal device is realized by an information processing device computer system in which a typical OS Operating System is installed. The terminal device is a device operable by the user such as a PC Personal Computer a tablet PC a notebook PC a smartphone and a mobile phone.

The image forming device is a device having an image forming function such as a multifunction peripheral a copier a scanner and a laser printer. The authentication device is realized by an information processing device in which a typical OS is installed. The authentication device provides a user authentication function. The other device is a device such as a projector and an electronic blackboard device.

Note that the terminal device the image forming device the authentication device and the other device include a wireless communication unit or a wired communication unit. illustrates an example where there is one of each of the terminal device the image forming device the authentication device and the other device however there may be a plurality of each of these devices.

The service providing system is a system constructed by a provider providing a cloud service via the network N. Note that in the present embodiment the cloud service is described as an example however the present embodiment is also applicable to other services provided via the network N such as services provided by ASP Application Service Provider and web services.

The network N of the service providing system is connected to the network N by the access control device . To the network N the access control device a print service providing device a distribution service providing device a portal service providing device an authentication device a data process control device a data process execution control device and a data process device are connected.

Details of the print service providing device the distribution service providing device the portal service providing device the authentication device the data process control device the data process execution control device and the data process device are described below.

The devices in the service providing system such as the access control device and the print service providing device may be realized by one or more information processing devices. That is to say the devices in the service providing system may be realized by one information processing device or may be distributed across a plurality of information processing devices.

Note that the devices in the service providing system may be realized by being combined in a single computer. That is to say the number of information processing devices constituting the devices in the service providing system does not limit the application scope of the present invention.

Furthermore part of or all of the devices in the service providing system may be realized in a private network such as the network N in an office. The information processing system according to the present embodiment indicates a preferred example. For example the application scope of the present invention is not limited according to whether there is a firewall FW between the service providing system and the devices of the network N in the office accessed for using the service providing system .

The service providing system may be broadly divided into devices for realizing service providing functions for providing various services and devices for realizing platform functions that are commonly usable when providing the various services.

Note that the print service providing device the distribution service providing device and the portal service providing device are examples of devices for realizing the service providing functions for providing various services. The authentication device the data process control device the data process execution control device and the data process device are examples of devices for realizing platform functions that are commonly usable when providing the various services.

The way of broadly dividing the service providing system as described above is a conceptual perception for describing the present invention to be easily understandable the service providing system need not be constituted based on such a perception.

Furthermore to the network N such as the Internet the terminal device a mail server and an online storage are connected. As illustrated in the terminal device may be connected to a network outside the network N in the office. In the example of the information processing system illustrated in the terminal device is connected to the network N in the office and the network N such as the Internet.

The mail server performs processes relevant to e mails such as sending and receiving e mails of users. The online storage performs processes relevant to a service of lending storage areas of the storage. The mail server and the online storage are realized by one or more information processing devices.

The terminal device and the authentication device of may be realized by a computer system having a hardware configuration as illustrated in for example . Similarly the devices in the service providing system such as the access control device and the print service providing device illustrated in may be realized by a computer system having a hardware configuration as illustrated in for example .

The mail server and the online storage illustrated in are also realized by a computer system having a hardware configuration as illustrated in . illustrates a hardware configuration of an example of a computer system according to the present embodiment.

A computer system illustrated in includes an input device a display device a RAM a ROM a HDD Hard Disk Drive a CPU Central Processing Unit a communication I F and an external I F which are interconnected by a bus B.

The input device includes a keyboard a mouse and a touch panel and is used by the user for inputting various operation signals. The display device includes a display and displays processing results by the computer system .

The RAM is a volatile semiconductor memory storage device for temporarily saving programs and data. The ROM is a nonvolatile semiconductor memory storage device that can save programs and data even after the power is turned off. The ROM stores programs and data such as BIOS Basic Input Output System that is executed when the computer system is activated OS settings and network settings.

The HDD is a nonvolatile storage device storing programs and data. The stored programs and data include for example an OS that is the basic software for controlling the entire computer system and application software for providing various functions on the OS.

The CPU is a processor for controlling the entire computer system and realizing functions of the computer system by loading programs and data from storage devices such as the ROM and the HDD into the RAM and executing processes.

The communication I F is an interface for connecting the computer system to the networks N through N. Accordingly the computer system performs data communication via the communication I F .

The external I F is an interface between the computer system and an external device. An example of the external I F is a recording medium A. Accordingly the computer system can read and or write data with respect to the recording medium A via the external I F .

Examples of the recording medium A are a flexible disk a CD Compact Disk a DVD Digital Versatile Disk a SD memory card and a USB memory Universal Serial Bus memory .

The service applications of include a portal service application a print service application and a distribution service application for example. The service application is an application having a function for providing various services.

For example the portal service application is implemented in the portal service providing device of . The print service application is implemented in the print service providing device . The distribution service application is implemented in the distribution service providing device .

The portal service application is an application that provides a portal site for the user to use various services such as a print service and a distribution service. The portal service application performs processes for the user to use various services as described below such as a tenant registration process a service registration process and a registration process of various kinds of management information in cooperation with the platform .

The print service application is an application for providing a print service realizing printing by for example the image forming device by storing print data and sending the print data to the image forming device .

The distribution service application is an application for providing a distribution service of performing data processing with respect to image data sent from various devices such as the image forming device and distributing the processed data to the online storage illustrated in .

Note that the service applications are not limited to the examples of the service applications may include an application for providing a service of sending the stored image data projection data to another device such as a projector. Furthermore the service applications may include an application for providing a service of sending the stored image data projection data to another device such as an electronic blackboard device. As described above the service applications include applications for providing some kind of service to the devices such as the image forming device used by the user.

The platform API is an interface for the service application to use the platform . The platform API is an interface that is defined in advance and provided for the platform to receive requests from the service application for example the platform API is constituted by functions and classes.

Note that when the service providing system is constituted by being distributed across a plurality of information processing devices for example a Web API that can be used via the network may be used as the platform API .

The platform includes a communication unit an access control unit a mail transmission unit a setting registration unit a permission setting processing unit a license authentication unit a user authentication unit a user device authentication unit an in house cooperation authentication unit an external cooperation authentication unit a data processing control unit one or more processing queues one or more data process request units and one or more data processing units .

The communication unit is a functional unit for executing communication with devices such as the image forming device and is implemented in the access control device of for example. The access control unit is a functional unit for executing access control according to various accesses requested to the service providing system from devices such as the image forming device and is implemented in the access control device for example.

The mail transmission unit is a functional unit for transmitting e mails and is implemented in the authentication device of for example. The setting registration unit is a functional unit for setting and registering various management data items to be stored in the management data storage unit and is implemented in the authentication device for example. The permission setting processing unit is a functional unit for executing processes for setting permission with respect to an external service such as the online storage and is implemented in the authentication device for example.

The license authentication unit is a functional unit for executing authentication relevant to a license based on license information and tenant information stored in the management data storage unit as described below and is implemented in the authentication device for example. The user authentication unit is a functional unit for executing user authentication based on a login request from a device that does not require device authentication such as the terminal device and is implemented in the authentication device for example.

The user device authentication unit is a functional unit for executing user authentication based on a login request from a device requiring device authentication such as the image forming device and is implemented in the authentication device for example.

The in house cooperation authentication unit is a functional unit for performing user authentication when the user is authenticated by the authentication device illustrated in at a device such as the image forming device and uses a user ID acquired from the authentication device to log in and the in house cooperation authentication unit is implemented in the authentication device for example. The external cooperation authentication unit is a functional unit for executing an authentication process for logging into the online storage of and is implemented in the authentication device for example.

The data processing control unit is a functional unit for controlling data processing executed based on a request from the service application and is implemented in the data process control device for example. The one or more processing queues are message queues corresponding to the type of data processing and a message of a request relevant to data processing from the data processing control unit is registered in the processing queue . The processing queues are implemented in the data process control device for example.

The one or more data process request units monitors the processing queue assigned to itself and receives a message of a request relevant to data processing from the processing queue . The data process request unit is a functional unit for requesting the data processing unit to execute data processing corresponding to the received message and is implemented in the data process execution control device for example.

The one or more data processing units are functional units for executing data processing in response to a request from the data process request unit and are implemented in the data process device for example. Note that examples of data processing executed by the data processing unit include a dividing process of dividing the request from the service application a data format conversion process of converting the data format and an OCR process of executing OCR. Furthermore an example of data processing executed by the data processing unit includes an upload process of uploading data in the online storage .

Note that depending on the type of data processing the data process request unit and the data processing unit may be implemented in the data process execution control device for example.

The management data storage unit includes for example a management information storage unit a data processing information storage unit and a data storage unit .

The management information storage unit stores management information such as license information tenant information user information and device information. The management information storage unit is implemented in for example the authentication device . The data processing information storage unit stores information relevant to the requested data processing. The data processing information storage unit is implemented in the data process control device for example. The data storage unit stores other data such as application data and print data. The data storage unit is implemented in the data process control device for example.

Examples of the management data stored in the management data storage unit of are as follows. is a configuration diagram of an example of license information. The license information includes the license type an ID a registration code and a registration state as data items. The license type is information expressing the type of license.

The license types include a tenant a print service and a distribution service. The ID is an ID of each license and is information used for license authentication. The registration code is information used when registering a tenant. The registration state is information indicating whether the registration state is a state where registration registration of ID of a license by the user has been completed or not registered or not registered .

The name is the name that the user sets when performing tenant registration and a company name or an organization name is set for example. The service ID is an ID of a service when the license type is print service and distribution service in the license information and is information that is registered as the user performs service registration after tenant registration is performed.

The service type is information expressing the license type type of service corresponding to the service ID. The validity term is the validity term of the service ID. The validity term of a service ID registered in a particular device is managed from the time point of registration.

The external service is information expressing an external service that is used in cooperation with the service providing system . An example of the external service is the online storage illustrated in for example. The address information is a mail address of the administrator registered when performing tenant registration.

The usage district information is information relevant to the country area in which the service is used. Note that the online storage is an example of the external service. Information items such as an account a password a permission token and a scope described below are examples of information items used when using an external service.

Note that permission is to set a usage range authority relevant to the usage of a service as to which service is to be used and which resource is allowed to be accessed when the user uses a service. Permission may be set by using a standard technology such as AIP permission called OAuth. From the viewpoint of using an external service such as the online storage from the service providing system the external service serves as a service provider of OAuth and the service providing system serves as the consumer of OAuth.

The user information is for managing information of each user in units of tenant IDs. The user ID and the password used for login are authentication information used for user authentication when logging into the service providing system . The user. ID for login may be the user name or any information as long as the user can be identified when logging into the service providing system .

The user ID for in house authentication is user specification information for specifying a user in the authentication device of the network N in the office. Furthermore the user ID for in house authentication is authentication information used for user authentication when the user specification information acquired from the authentication device is used for login. The user ID for in house authentication may be any user specification information by which a user can be specified in the authentication device of the network N in the office and may be a card ID of an IC card carried by the user or a terminal ID of a mobile terminal.

The account and password for online storage are authentication information used for logging into the online storage . The permission token is information for using the online storage within a range of a particular authority. The scope is information for specifying the usage range set by the permission.

Note that an account may be a user ID a user name or an address for online storage the account may be any authentication information used for authentication when the user logs into the target online storage . The address information is the mail address of the user.

The device ID is information for identifying a device and is information used for device authentication. An example of the device ID is the equipment number of the device. The service ID and the service type are the same information as the service ID and the service type in the tenant information and are registered as the user registers a service ID with respect to a particular device.

The usage start date is information of the date when the service ID is registered. The usage end date is information of the date when the validity term of the registered service ID has ended. The device registered in the device information can use the service of the registered service ID from the usage start date to the usage end date of the service ID.

Note that depending on the type of service and the type of license there may be service IDs that have unlimited validity terms virtually no expiration . Furthermore even if the device does not have its device information registered it is assumed that part of the functions provided by the service providing system can be used excluding services functions that cannot be used unless device authentication is performed.

Note that in the present embodiment the terminal device is indicated as an example of a device that does require registration of device information. Furthermore in the present embodiment the image forming device is indicated as an example of a device that requires registration of device information.

Examples of a function that can be used in the terminal device include setting registering management data and inputting and deleting print data. Furthermore examples of functions that can be used in the image forming device include acquiring print data and sending distribution data.

Note that the provider providing the service is to determine which functions require device authentication to be used and which functions do not require device authentication to be used and there may be services that do not require device authentication.

The service name is the name of an external service. The client ID is information for specifying the service providing system that is issued by an external service. The client secret is secret information for ensuring the personal identification of the client ID and is information serving as a password.

The product name is information specifying the service application . The scope is information specifying the usage range of the external service. The permission destination URL is URL for example a URL of a permission server included in the external service of a permission system included in the external service. The redirect destination URL is a URL of the service providing system that is redirected from the external service for example a URL of a function serving as a permission client of the permission setting processing unit .

As described above the tenant ID is associated with the service provided by the service providing system the user using the service and a device using the service the tenant ID is information for managing the user the device and the service in the service providing system . Furthermore the tenant ID is information usage target specification information for specifying the usage target such as specifying which service is to be provided to which user and furthermore to which device among the services that can be provided by the service providing system .

In the following a detailed description is given of the process of the information processing system according to the present embodiment.

Note that examples of the method of acquiring a tenant ID and a registration code are a method of directly acquiring a tenant ID and a registration code from the service provider and a method of acquiring a tenant ID and a registration code by accessing an exclusive use site operated by the service provider from the terminal device .

In step S the user operates the input device of the terminal device so that the terminal device accesses the portal site of the service providing system . The terminal device accesses the portal site of the service providing system based on the operation of the user.

Because the access is made to the portal site the access control unit of the service providing system allows the access from the terminal device and lets the terminal device access the portal service application .

The portal service application causes the display device of the terminal device to display the top screen. The user can operate the input device of the terminal device to select from the top screen whether to request login or whether to request new tenant registration. Here a description is given assuming that a request for new tenant registration is requested.

Note that if the user is registered in the user information of the management information storage unit administrator or other user the user can select to request login by inputting a tenant ID a user ID and a password.

When new tenant registration is requested in step S the portal service application of the service providing system causes the display device of the terminal device to display an input screen for performing tentative registration of the tenant ID. The user operates the input device of the terminal device inputs information for performing tentative registration of the tenant ID and then requests tentative registration. Based on the operations of the user the terminal device makes a request for tentative registration to the portal site of the service providing system .

Note that examples of the information input for performing tentative registration of the tenant ID are information relevant to the country area where the service is used usage district information and information indicating to agree with the terms of use displayed according to the country area where the service is used binding terms and conditions . The information input for performing tentative registration of the tenant ID may include information such as a tenant ID a registration code a mail address and the used language.

Thus the service providing system holds the terms of use binding terms and conditions information according to the country area where the service is used. The portal service application of the service providing system performs display control of causing the display device of the terminal device to display the terms of use according to the usage district information input by the user to perform tentative registration of the tenant ID and prompts the user to select whether the user agrees with the terms of use.

When tentative registration is requested from the user s terminal device the portal service application requests the license authentication unit to perform a process of confirming the validity of the tenant ID and the registration code included in the information input for performing tentative registration of the tenant ID. The license authentication unit that has received the request executes a license authentication process and determines match whether a tenant ID and a registration code for which a process of confirming the validity has been requested is stored the license information of stored by the management information storage unit .

When the tenant ID and registration code for which a process of confirming the validity has been requested is stored the license authentication unit determines whether the registration state associated with the tenant ID and registration code is not registered .

When the registration state is not registered the license authentication unit determines that the tenant ID and registration code for which a process of confirming the validity has been requested is valid information and authenticates the tenant ID license . The license authentication unit reports the authentication result of the license to the portal service application .

When the tenant ID and registration code are valid information the portal service application requests the setting registration unit to register the tenant ID the mail address and the usage district information included in the information input for performing tentative registration of the tenant ID. The setting registration unit registers the tenant ID the mail address and the usage district information in the tenant information in the management information storage unit according to the request from the portal service application .

When registration by the setting registration unit is performed in step S the portal service application generates a URL for the real registration that is the access destination for displaying the screen for the real registration and creates a mail describing the URL for the real registration. The portal service application requests the mail transmission unit to send the created mail.

The mail transmission unit sends the mail addressed to the mail address included in the information that has been input for performing the tentative registration of the tenant ID. When the mail is sent by the mail transmission unit the portal service application causes the display device of the terminal device to display a report screen reporting that the mail has been sent.

Note that the URL for the real registration is managed by a validity term for example one hour from when the URL is generated. Furthermore in the mail sent from the mail transmission unit from the viewpoint of enhancing security it is assumed that at least one of the information items of the tenant ID and the registration code is not described.

Next the user operates the input device of the terminal device to access the URL for the real registration described in the received mail. The terminal device accesses the URL for the real registration based on the operation by the user.

Note that the terminal device accessing the URL for the real registration may not be the same as the terminal device that has made the request for tentative registration. The access control unit causes the terminal device to access the portal service application .

The portal service application confirms whether the access to the URL for the real registration is valid whether the access is made to the generated URL for the real registration and that the access is within the validity term . When the access is valid the portal service application causes the display device of the terminal device to display the screen for the real registration.

The user operates the input device of the terminal device and inputs information for performing the real registration of the tenant ID in the real registration screen and then requests the real registration. In the information input to the real registration screen is tenant information including the tenant ID the name and the registration code and user information including the user ID and the password for login and address information.

Note that either the tenant ID or the registration code already input by the user at the time of tentative registration of the tenant ID may be displayed in an input state in advance. From the viewpoint of enhancing security it is assumed that at least one of the information items of the tenant ID and the registration code to be input by the user is not described in the mail describing the URL for the real registration as described above.

When the real registration is requested from the terminal device of the user the portal service application requests the license authentication unit to perform a validation process real registration process of a license based on the tenant ID and the registration code input in the real registration screen.

The license authentication unit that has received the request executes the license authentication process and determines whether the tenant ID and the registration code input in the real registration screen are stored in the license information stored by the management information storage unit . When the input tenant ID and registration code are stored in the license information and the registration state associated with the stored tenant ID and the registration code is not registered the license authentication unit determines that the input tenant ID and registration code are valid information.

When the input tenant ID and registration code are determined to be valid information the license authentication unit requests the setting registration unit to change the state of the license information. The setting registration unit changes the value of the registration state associated with the valid tenant ID and registration code to registered in the license information stored by the management information storage unit .

When the validation process of the license is completed the portal service application requests the setting registration unit to register the tenant information and the user information input to the real registration screen in the terminal device by the user. The setting registration unit registers in the tenant information stored by the management information storage unit the name that is input as part of the tenant information in the real registration screen. Furthermore the setting registration unit registers in the user information stored by the management information storage unit a tenant ID a user ID and a password for login and address information.

When the registration of settings of various information items is completed by the setting registration unit the portal service application causes the display device of the terminal device to display a tenant registration completion screen. Furthermore the portal service application creates a mail describing a tenant registration completion report and requests the mail transmission unit to send the mail. The mail transmission unit sends a mail describing the tenant registration completion report to the mail address address information registered in the tenant information input for performing the tentative registration of the tenant ID in the terminal device by the user.

For example the user confirms the tenant registration completion screen displayed on the display device of the terminal device . By completing the registration of the tenant ID the user ID and the password from next time the user can request to login from the top screen of the portal site. By logging in from the top screen of the portal site the user can perform the process of registering the tenant information the user information and the device information associated with the tenant ID.

In step S the user such as an administrator operates the input device of the terminal device and inputs the tenant ID the user ID and the password from the top screen of the portal site and then requests to log in.

The portal service application that has received the request to log in requests the user authentication unit to perform user authentication. The user authentication unit determines match whether a combination of the tenant ID and a user ID and a password for login received from the terminal device is stored in the user information stored by the management information storage unit .

When the combination of the tenant ID and a user ID and a password for login received from the terminal device is stored the user authentication unit authenticates the user who has requested the login. When the user is authenticated by the user authentication unit the portal service application allows the login.

The user who has logged into the portal service application can register the service ID of the service that the user desires to use. The portal service application causes the display device of the terminal device to display a service registration screen for registering the service ID. The user operates the input device of the terminal device and inputs the service ID from the service registration screen displayed on the display device of the terminal device and then requests service registration. The terminal device requests the portal service application to perform service registration based on the operation by the user.

When service registration is requested from the terminal device the portal service application refers to the license information stored by the management information storage unit and the user selects an ID that matches the service ID input to the service registration screen. The portal service application acquires the license type service type associated with the selected ID.

Furthermore the portal service application refers to the tenant information stored by the management information storage unit and acquires usage district information associated with the tenant ID of the user who has logged in. The portal service application causes the display device of the terminal device to display the terms of use according to the acquired type of license and the usage district information and prompts the user to select whether to agree with the terms of use.

The service providing system saves terms of use binding terms and conditions according to the country area of using each service type license type . The portal service application performs display control of displaying the terms of use according to the usage district information input by the user for performing tentative registration of the tenant ID and the service type for which service registration is requested and can prompt the user to select whether to agree with the terms of use.

When the user operates the input device of the terminal device and makes a selection of agreeing with the terms of use the portal service application requests the license authentication unit to perform a service registration process based on the tenant ID of the user who has logged in and the service ID input to the service registration screen.

The license authentication unit confirms match whether the service ID input to the service registration screen is stored as an ID in the license information stored by the management information storage unit . When the service ID input to the service registration screen is stored as an ID the license authentication unit determines that the service ID is a valid ID authenticates the service ID .

When the service ID is determined to be a valid service ID the license authentication unit requests the setting registration unit to register a service ID. The setting registration unit registers the service ID and the service type in association with the tenant ID of the user who has logged in in the tenant information stored by the management information storage unit .

In step S the user such as an administrator performs device registration of the service ID. The user operates the input device of the terminal device and causes the display device of the terminal device to display a device registration screen. The user operates the input device of the terminal device and inputs in the device registration screen the service ID and the device ID of the device in which the usage of the service becomes possible by the service ID and requests device registration of the service ID.

When device registration of the service ID is requested from the terminal device the portal service application requests the license authentication unit to perform a device registration process of the service ID based on the tenant ID of the user who has logged in and the service ID and the device ID input to the device registration screen.

The license authentication unit determines match whether the combination of the tenant ID of the user who has logged in and the service ID input to the device registration screen is stored in the tenant information stored by the management information storage unit .

When the combination of the tenant ID of the user who has logged in and the service ID input to the device registration screen is stored the license authentication unit refers to the license information stored by the management information storage unit . The license authentication unit determines whether the registration state associated with the service ID input to the device registration screen is not registered .

When the registration state is not registered the license authentication unit requests the setting registration unit to perform device registration of the service ID. Note that a service ID whose registration state is not registered is a service ID for which device registration of a service ID has not been performed. The setting registration unit registers in the device information stored by the management information storage unit the tenant ID of the user who has logged in and the service ID and the device ID input to the device registration screen.

Furthermore the setting registration unit refers to the tenant information saved by the management information storage unit and acquires the service type and validity term specified from the tenant ID and the service ID. The setting registration unit registers in the device information stored by the management information storage unit the service type the usage start date and the usage end date based on the acquired service type and validity term.

As the usage start date the date when the device registration of the service ID has been performed is stored. As the usage end date the last date calculated based on the validity term acquired from the tenant information for example one year and the usage start date is stored.

For example the usage start date may be specified in the request for service registration of step S. When it is made possible to specify the usage start date the usage start date specified in the request for service registration is stored as the usage start date of the device information. When the device registration of the service ID has been completed the setting registration unit changes the value of the registration state associated with the service ID for which device registration has been performed to registered in the license information stored by the management information storage unit .

As described above by the process from tenant registration to service registration the user such as an administrator is able to perform tenant registration service ID registration and device registration of the service ID by accessing the service providing system from the terminal device . In this manner the user is able to easily complete the formalities needed for receiving the service to be provided.

As illustrated in in user authentication from the terminal device the user inputs from the top screen of the portal site a tenant ID a user ID and a password as login information. In step S the terminal device receives the login information input from the user.

In step S the terminal device makes a login request to the service providing system by using the login information input by the user. The access control unit of the service providing system requests the user authentication unit to perform user authentication.

In step S the user authentication unit confirms whether there is login information received from the terminal device in the user information stored by the management information storage unit . When there is login information received from the terminal device in the user information stored by the management information storage unit the user authentication unit determines that user authentication is successful. When there is no login information received from the terminal device the user authentication unit determines that user authentication is unsuccessful.

When the user authentication is successful the access control unit allows the login from the terminal device to the service providing system login for using service . In step S the access control unit sends to the terminal device the login response based on the result of the user authentication by the user authentication unit .

In and in the user authentication for logging into the service providing system the image forming device saves a setting of using the user ID and the password for login or using the user ID for in house authentication. Note that the setting of using the user ID and the password for login or using the user ID for in house authentication may be changed according to need. Furthermore it is assumed that the image forming device has the tenant ID and the device ID saved in the storage area in itself.

In the case of a setting to use the user ID and the password for login in order to log into the service providing system the image forming device performs user device authentication as illustrated in B .

In step S the image forming device displays an input screen for the user to input the user ID and the password for login. The user inputs the user ID and the password for login from the input screen displayed on the image forming device . The image forming device receives the user ID and the password for login input by the user.

In step S the image forming device sends to the service providing system as login information the user ID and the password for login input by the user and the tenant ID and the device ID saved in the storage area of itself and makes a login request. The access control unit of the service providing system requests the user device authentication unit to perform user device authentication.

In step S the user device authentication unit confirms whether there is a combination of a tenant ID and a device ID included in the login information received from the image forming device in the device information saved by the management information storage unit . When there is a combination of the tenant ID and the device ID the user device authentication unit determines that the device authentication is successful. When there is no combination of the tenant ID and the device ID the user device authentication unit determines that the device authentication is unsuccessful.

Furthermore the user device authentication unit confirms whether there is a combination of a tenant ID and a user ID and a password for login included in the login information received from the image forming device in the user information stored by the management information storage unit .

When there is a combination of the tenant ID and the user ID and the password for login included in the login information received from the image forming device in the user information stored by the management information storage unit the user device authentication unit determines that the user authentication is successful. When there is no combination of the tenant ID and the user ID and the password for login included in the login information received from the image forming device the user device authentication unit determines that the user authentication is unsuccessful.

When the device authentication and the user authentication are successful the access control unit allows the login from the image forming device to the service providing system login for using service . In step S the access control unit sends to the terminal device a login response based on the results of device authentication and user authentication by the user device authentication unit .

In the case of the setting to use a user ID for in house authentication in order to log into the service providing system the image forming device performs the in house cooperation authentication illustrated in C . First the user executes user authentication in the image forming device . The user authentication executed in the image forming device is user authentication that is executed for using the image forming device or a particular function of the image forming device . In this case a description is given of an example where the authentication device performs user authentication by using a card ID saved in an ID card carried by the user.

In step S the user performs user authentication by causing a card reader not illustrated connected to the image forming device to read a card ID. In step S the image forming device sends the card ID read by the card reader to the authentication device and makes an authentication request.

In step S the authentication device performs authentication determination by using the card ID received from the image forming device . The authentication device stores in the storage area user authentication information in which card IDs and user IDs are associated with each other. The authentication device refers to the user authentication information in which card IDs and user IDs are associated with each other and confirms whether it is possible to specify a user ID associated with the card ID received from the image forming device .

When a user ID associated with the card ID is specified the authentication device determines that user authentication is successful. In step S the authentication device sends to the image forming device the authentication result indicating that authentication is successful together with the specified user ID.

Next for example the user can request to log into the service providing system by selecting to log into the service providing system from the display screen of the image forming device . In step S the user requests to log into the service providing system from the image forming device .

When login to the service providing system is requested from the user the image forming device sends to the service providing system as login information the specified user ID and the tenant ID and device ID saved in the storage area of itself and makes a login request. The access control unit of the service providing system requests the in house cooperation authentication unit to perform in house cooperation authentication.

In step S the in house cooperation authentication unit confirms whether there is a combination of the tenant ID and device ID included in the login information received from the image forming device in the device information stored by the management information storage unit .

When there is a combination of the tenant ID and the device ID the in house cooperation authentication unit determines that the device authentication is successful. When there is no combination of the tenant ID and the device ID the in house cooperation authentication unit determines that the device authentication is unsuccessful.

Furthermore the in house cooperation authentication unit confirms whether there is a combination of the tenant ID and the user ID for in house authentication included in the login information received from the image forming device in the user information stored by the management information storage unit . When there is a combination of the tenant ID and the user ID for in house authentication included in the login information received from the image forming device in the user information stored by the management information storage unit the in house cooperation authentication unit determines that user authentication is successful.

When there is no combination of the tenant ID and the user ID for in house authentication included in the login information received from the image forming device the in house cooperation authentication unit determines that user authentication is unsuccessful.

The access control unit allows the login to the service providing system from the image forming device login for using service when the device authentication and the user authentication are successful. In step S the access control unit sends to the terminal device a login response based on the results of device authentication and user authentication by the in house cooperation authentication unit .

Note that when the device authentication is successful but the user authentication is unsuccessful by the in house cooperation authentication unit the service providing system may cause the image forming device to display an input screen for the user to input a user ID and a password for login.

In this case the user can request login again by inputting the user ID and the password for login in the input screen. The image forming device sends to the user device authentication unit of the service providing system the user ID and the password for login input by the user and the tenant ID saved in the storage area of itself and makes a login request.

The user device authentication unit confirms whether there is a combination of the tenant ID and the user ID and the password for login received from the image forming device in the user information stored by the management information storage unit .

When there is a combination of the tenant ID and the user ID and the password for login received from the image forming device in the user information stored by the management information storage unit the user device authentication unit determines that user authentication is successful. The access control unit allows the login to the service providing system .

Furthermore the setting registration unit registers in the user information stored by the management information storage unit the user ID for in house authentication received from the image forming device in association with the tenant ID and the user ID and the password for login received from the image forming device . As described above by registering in the user information the user ID for in house authentication received from the image forming device in association with the tenant ID and the user ID and the password for login the user is able to log in by using the user ID for in house authentication from next time.

In the service providing system various data processes requested from a process request unit of the service application are executed as follows by the data processing control unit the processing queue the data process request unit and the data processing unit of the platform .

Furthermore the process request unit sends a data processing request hereinafter request to the data processing control unit of the platform . The request to be sent includes processing contents of the data process and information of the recording destination of the process target data for example a URL .

The data processing control unit analyzes the received request and registers a message in the processing queue message queue according to the process contents of the data process. Note that the processing queue is provided for each process content of the data process.

Furthermore the data processing control unit registers the information of the request in the data processing information storage unit of the management data storage unit . The information of the request is for example the recording destination of the processing target data the process contents of the data process and the state of the request.

The state of the request is for example received executing and completed . Note that the state of the request expresses the status indicating the process situation of the data process. The state of the request becomes received at the stage when the data processing control unit has registered the information of the request.

Each data process request unit monitors one or more processing queue assigned to itself. That is to say each data process request unit monitors the request of the process contents of one or more data processes. Each data process request unit acquires a message registered in the processing queue that it is monitoring.

For example in the first data process request unit monitors the first processing queue and the second processing queue which have different process contents of data. Furthermore second data process request unit monitors the first processing queue through the third processing queue which have different process contents of data. In the example of the first data process request unit and the second data process request unit monitor overlapping queues i.e. the first processing queue and the second processing queue .

Note that the assignment of processing queues monitored by the data process request unit may be set and changed according to need. For example the assignment of processing queues monitored by each data process request unit may be set and changed according to the request frequency and the processing time of each process content of the data process.

The data process request unit acquires information of the request from the data processing information storage unit based on a message acquired from the processing queue that it is monitoring. The data process request unit causes the data processing unit to execute a data process of the request based on the record destination of the process target data and the process contents of the data process included in the acquired information of the request.

Next the data process request unit updates the information of the request from the execution result of the data process executed by the data processing unit and registers the updated information of the request in the data processing information storage unit . The updating of the information of the request includes a process of deleting the process contents of the data process executed from the request a process of changing the state of the request when there is a change etc. Furthermore when the information of the request includes process contents of a data process to be performed next the data process request unit registers a message in the processing queue corresponding to the process contents of the data process.

Note that when the process target data before and after the data process becomes different data by causing the data processing unit to execute the data process of the request the data process request unit records the process target data after the process in the data storage unit . Furthermore the data process request unit updates the information of the request according to the information of the recording destination of the process target data after the process.

In step S the data processing control unit analyzes the request and registers a message in the processing queue according to the process contents of the data process. Furthermore the data processing control unit registers information of the request in the data processing information storage unit of the management data storage unit .

In step S each data process request unit acquires the message registered in the processing queue that it is monitoring from the processing queue . In step S the data process request unit acquires information of the request from the data processing information storage unit based on the acquired message. Then the data process request unit causes the data processing unit to execute a data process of the request based on the acquired information of the request.

In step S the data process request unit updates the information of the request from the execution result of the data process executed by the data processing unit registers the updated information of the request in the data processing information storage unit and then ends the process of the flowchart of .

Note that when the information of the request includes process contents of a data process to be performed next the data process request unit registers a message in the processing queue corresponding to the process contents of the data process and then ends the process of the flowchart of .

In the following specific examples of the process contents of the data process are given however the process contents of the data process are not limited to these specific examples. As specific examples of the process contents of the data process first there is a data process of converting the data format of the process target data.

For example a data process of converting image data into PDF Portable Document Format data is an example of a data process of converting the data format of the process target data. In the data process of converting image data into PDF data the process contents of the data process are expressed as image2pdf .

Furthermore a data process of converting PDF data into PDL Page Description Language data is also an example of a data process of converting the data format of the process target data. In the data process of converting PDF data into PDL data the process contents of the data process are expressed as pdf2pdl .

Furthermore a data process of converting document data of Microsoft registered trademark Office registered trademark into PDL data is also an example of a data process of converting the data format of the process target data. In the data process of converting Office document data into PDL data the process contents of the data process are expressed as office2pdl .

As a second specific example of the process contents of a data process there is a data process of dividing the process contents of a single data process into process contents of a plurality of data processes and converting the process contents into requests of the respective data processing units according to the process contents of the data processes obtained as a result of the division.

For example the data process of converting image data into PDL data may be realized by dividing the data process into a data process of converting image data into PDF data and a data process of converting PDF data into PDL data. Note that in the data process of converting image data into PDL data the process contents of the data process are expressed as image2pdl .

For example the data processing unit executes a data process of dividing the request of a data process of image2pdl into requests of data processes of image2pdf and pdf2pdl . As described above the data processing units include units for performing a data process of dividing a request of a single data process into requests of a plurality of data processes.

As described above for example when there is no data processing unit capable of executing a data process of image2pdl data processes of image2pdf and pdf2pdl are performed in cooperation with each other to execute the desired data process of image2pdl .

In this case expresses that the desired data process of image2pdl can be executed by performing data processes of image2pdf and pdf2pdl in cooperation with each other.

In the service providing system according to the present embodiment it is possible to perform a data process of dividing the process contents of a single data process into process contents of a plurality of data processes and therefore it is possible to flexibly handle increases in the types of process contents of data processes.

Furthermore as a third specific example of the process contents of a data process there is a data process of cooperating with an external storage. One example of a data process of cooperating with an external storage is a data process of requesting the external cooperation authentication unit to log into the online storage by using an account and a password for the online storage corresponding to the user who has logged in.

Other examples of a data process of cooperating with an external storage are a data process of saving data in the online storage to which the user has logged in and a data process of acquiring data from the online storage to which the user has logged in.

In step S in the registration screen of an external service the user selects the online storage external service that he desires to use from a list of external services stored in the external service information of the management information storage unit and requests to register the selected online storage .

The portal service application which has received the request for registration requests the setting registration unit to register the online storage selected by the user. The setting registration unit associates the tenant ID of the user who has logged in with the tenant information in the management information storage unit and registers the online storage selected by the user.

In step S the user selects in the permission setting screen of the portal site the user ID of the user for which the permission setting is to be applied the external service ID performing the permission setting or the service name of the external service and the scope to be set for the user and requests the registration of the permission setting. The portal service application receives the request of the permission setting.

In step S the portal service application that has received the request for the permission setting requests the permission setting processing unit to perform permission setting. The permission setting processing unit acquires parameters needed for the permission setting from external service information of the management information storage unit . Note that parameters needed for the permission setting include an external service ID and a scope and also a client ID associated with the selected external service ID a redirect destination URL and an arbitrary session key for maintaining the session.

In step S the permission setting processing unit that has acquired the parameters needed for permission setting acquires from the external service information of the management information storage unit a permission destination URL associated with the selected external service ID. The permission setting processing unit causes the request including the parameters needed for permission setting request in which the parameters needed for permission setting are set as the query of the GET request to be redirected from the terminal device to the permission destination URL.

By redirecting the request from the terminal device to the permission destination URL permission setting is performed between the terminal device and the online storage . Note that after the permission setting as the request is redirected from the online storage to the permission setting processing unit the session in the HTTP level is interrupted. Thus in order to maintain the same session a session key is used.

The redirected online storage causes the display device of the terminal device to display a login screen. The user operates the input device of the terminal device inputs the account and the password from the login screen and then requests to log in. The online storage to which a login request is made receives the login request.

When the login is successful the online storage causes the display device of the terminal device to display a permission screen. The user confirms the permission screen. When permission is to be given the user operates the input device of the terminal device and requests the permission by pressing a permission button displayed on the permission screen for example. The online storage that has received the request for permission registers the permission.

In step S the online storage causes a permission code indicating that permission is given and a session key to be redirected from the terminal device to the redirect destination URL.

In step S the permission setting processing unit of the service providing system receives a permission code. Note that if the user has already logged in when redirecting to the online storage the display of the login screen is omitted.

The permission setting processing unit that has received the permission code in step S acquires from the external service information of the management information storage unit the parameters needed for acquiring a permission token. The parameters needed for acquiring a permission token includes the received permission code and also the client ID and a client secret associated with the external service ID of the online storage that has sent the permission code.

In step S the permission setting processing unit sends to the online storage the acquired client ID and client secret and the received permission code and requests to acquire the permission token. The online storage validates the received permission code and sends the permission token to the permission setting processing unit of the service providing system .

In step S the permission setting processing unit that has received the permission token requests the setting registration unit to register the permission token. The setting registration unit registers in the user information of the management information storage unit the user to which the permission setting selected in the permission setting screen is to be applied the received permission token and the scope in association with each other.

When the registration of the permission token is completed the permission setting processing unit reports the completion of the registration to the portal service application . The portal service application causes the display device of the terminal device to display a screen indicating the setting results of the permission setting.

Note that when the online storage sends the permission token to the service providing system the online storage may also send together the validity term of the permission token and a refresh token used for reissuing a permission token when the validity term expires.

When a request for a process to cooperate with the online storage is received in step S the external cooperation authentication unit of the service providing system performs the process of logging into the online storage .

The external cooperation authentication unit receives a request to log into the online storage from the data processing unit for example. The external cooperation authentication unit acquires from the user information of the management information storage unit information needed for the login process associated with the user that has logged into the service providing system and the online storage for which the login process is to be performed.

Specifically the external cooperation authentication unit acquires information needed for the login process to the online storage associated with the tenant ID and the user ID and the password for login of the user who has logged into the service providing system .

For example in the case of the user information of when a request to log into the online storage A is received the external cooperation authentication unit acquires an account and a password as information needed for the login process to the online storage A .

Furthermore in the case of the user information of when a request to log into the online storage B is received the external cooperation authentication unit acquires an account and a permission token as information needed for the login process to the online storage B .

When the online storage to be cooperated with is an external service that does not have a permission setting like online storage A and a login process is to be performed the external cooperation authentication unit requests login to the online storage A by using an account and a password. The account and the password are an example of authentication information with respect to an external service.

The online storage A that has received the request for login executes authentication with respect to the received account and password. When the authentication is successful the online storage A sends a response indicating to allow the login to the external cooperation authentication unit . When the authentication is unsuccessful the online storage A sends a response indicating not to allow the login to the external cooperation authentication unit .

The external cooperation authentication unit receives a response indicating to allow the login from the online storage A . Accordingly the service providing system is able to perform the uploading saving of data in the online storage A and to perform the downloading acquiring of the data from the online storage A .

As described above as the external cooperation authentication unit receives a response indicating to allow the login from the online storage in step S the service providing system is able to execute a process of cooperating with the online storage .

When the online storage to be cooperated with is an external service that has a permission setting like online storage B the external cooperation authentication unit requests login to the online storage B by using an account and a permission token.

The account and the permission token are an example of authentication information with respect to an external service. The online storage B that has received the request for login confirms the validity of the received account and permission token. When the validity is confirmed the online storage B sends a response indicating to allow the login to the external cooperation authentication unit . When the authentication is unsuccessful the online storage B sends a response indicating not to allow the login to the external cooperation authentication unit .

The external cooperation authentication unit receives a response indicating to allow the login from the online storage B . Accordingly in step S the service providing system is able to realize a process of cooperating with the online storage within a usage range set by the scope.

Next a description is given of an example of data output control of a job in the information processing system according to the present embodiment described above. Note that in the following a description is given of an example of controlling based on rule information set in advance a method of outputting data of a job input by the terminal device in the office of the information processing system . Here for example rule information is for setting the output method by setting the contents of the data to be printed as a condition.

When the rule registration unit receives a request to register rule information from the terminal device the rule registration unit registers the received rule information in association with the tenant information of the user stored by the management information storage unit described above.

When the output method control unit receives a request to input a job from the terminal device in order to analyze the document data of the job the output method control unit requests the intermediate data conversion request unit to convert the document data of the job into intermediate data. For example the output method control unit acquires the rule information stored in the management information storage unit based on a user name that has logged in and requests the keyword detection unit to detect a keyword based on the rule information from the converted intermediate data.

The output method control unit determines the data output method of the job based on the keyword and rule information obtained from the keyword detection unit . Here for example the output method control unit requests a data process with respect to the intermediate data according to the determined result and requests the print data conversion request unit to convert the intermediate data on which a data process has been executed into print data.

The intermediate data conversion request unit makes a process request to the data processing control unit to cause the data processing unit to convert the document data of the job into intermediate data according to a request from the output method control unit . Note that for example the intermediate data is data that is converted from original data document data for extracting a predetermined keyword the intermediate data may be edited while maintaining the format and the layout of the original data such as XPS and PDF and the intermediate data is data before being converted into print data.

For example the keyword detection unit detects a predetermined keyword from the character string of the intermediate data obtained by the conversion by the intermediate data conversion request unit according to a request from the output method control unit . Here for example the keyword detection unit may detect predetermined information condition included in the intermediate data.

The data process request unit makes a process request to the data processing control unit to cause the data processing unit to execute a predetermined data process on the intermediate data according to a request from the output method control unit . For example the data process request unit requests as a predetermined data process on the intermediate data a combining process of overpainting an area where the predetermined keyword has been detected with a predetermined color and a process of printing a barcode in a predetermined area when a predetermined area is detected.

The print data conversion request unit converts the intermediate data on which a predetermined process has been executed by the data process request unit into print data according to a request from the output method control unit . The print data conversion request unit makes a process request to the data processing control unit to cause the data processing unit to execute a process of converting the intermediate data into data that is appropriate for the image forming device i.e. into printer language Page Description Language data.

Note that for example the intermediate data may be converted into output data according to the terminal device the image forming device and a device for displaying data such as a projector and the print data conversion request unit has a function that is an example of an output data conversion unit.

In the example of an output method is indicated in which the company A of tenant ID 10000 performs a data process of setting A when keyword A is detected from the data of the input job in print service of service ID 20000 .

Here the page in which keyword A is detected may have a setting to stop output do not print and the area where keyword A is detected may have a setting of executing a combining process of overpainting with predetermined color or an editing process of deleting keyword A . Furthermore the data in which the keyword A is detected in a predetermined area may have a setting of executing a print process such as print a barcode in a predetermined area.

As described above for example the output method control unit can refer to the rule information associated with the user who input the job determine the output method set with respect to the contents of the data of the job and control the output of the data.

Next a specific description is given of a data output control process of a job executed by the above described process blocks after a user such as an administrator registers rule information. is a sequence diagram of a data output control process of a job. Note that illustrates a sequence example of a data output control process performed in the terminal device and the print service application .

In the example of in order to register rule information when printing by using the print service application of the service providing system the terminal device accesses the portal site of the service providing system according to a user s operation.

Here the access control unit of the service providing system causes the terminal device to access the portal service application . The portal service application displays for example a login screen on the operation panel of the terminal device .

According to an operation in the login screen by the user the terminal device logs into the portal service application and accesses the print service application . For example the print service application displays a rule information registration screen on the operation panel of the terminal device . In the rule information registration screen for example a tenant ID a user name and a rule can be input.

In step S when the terminal device receives the rule information input by the user in the rule information registration screen in step S the terminal device requests the rule registration unit of the print service application to register rule information.

In step S the rule registration unit registers the rule information received from the terminal device in association with a tenant ID and then in step S the rule registration unit reports to the terminal device that the rule information has been registered.

Here a description is given of a case where the terminal device receives the document data to be printed at an upload screen and the terminal device uploads the document data in the print service application of the service providing system .

In step S when the terminal device receives document data of a job via an upload screen from the user in step S the terminal device requests the print service application to input a job.

In step S when the output method control unit of the print service application receives a request to input a job from the terminal device in order to analyze the document data of the job the output method control unit requests the intermediate data conversion request unit to convert the document data into intermediate data.

In step S the intermediate data conversion request unit converts the document data into intermediate data and then in step S the intermediate data conversion request unit reports to the output method control unit that the document data has been converted into intermediate data.

In step S the output method control unit acquires rule information stored in the management information storage unit based on the user name that has logged in. In step S the output method control unit requests the keyword detection unit to detect a predetermined keyword from the character string of the intermediate data based on the acquired rule information.

In step S when the keyword detection unit detects a predetermined keyword in step S the keyword detection unit reports to the output method control unit that a predetermined keyword has been detected.

In step S the output method control unit determines the data output method of the job by referring to the setting applied from the rule information illustrated in based on the keyword detected by the keyword detection unit . In step S the output method control unit requests the data process request unit to perform a predetermined data process on the intermediate data according to the determination result.

In step S the data process request unit executes a predetermined data process on the intermediate data and then in step S the data process request unit reports to the output method control unit that the predetermined data process has been executed.

In step S the output method control unit requests the print data conversion request unit to convert the intermediate data on which the predetermined data process has been executed into print data. In step S the print data conversion request unit converts the intermediate data into print data and then in step S the print data conversion request unit reports to the output method control unit that the intermediate data has been converted into print data. Accordingly it is possible to control the output method of the data of the job input by the terminal device based on rule information set in advance.

Note that in step S when a report is received that a predetermined keyword is not detected the output method control unit determines the method to be a normal data output method to which the rule information is not applied and proceeds to step S to make a request of converting the intermediate data into print data.

Furthermore in the above process the predetermined process is executed by extracting a predetermined keyword from the intermediate data however a page index may be created based on keywords extracted in units of pages from the intermediate data and the data process may be executed based on the page index.

Next a description is given of an example of printing out from the image forming device the data that has been converted into print data by the data output control process illustrated in . illustrates a sequence of a process of outputting data from the image forming device . Note that the process of is executed by the image forming device and the user device authentication unit and the print service application of the service providing system .

In the example of in order to output the print data by using the print service application of the service providing system the image forming device displays a login screen on the operation panel via an exclusive use application installed in advance.

In step S the image forming device receives login information according to an operation to the login screen by the user and then in step S the image forming device makes a login request to the user device authentication unit . In step S the user device authentication unit performs user device authentication.

In step S the user device authentication unit makes a login response based on the result of the user device authentication. For example when the image forming device receives a login response indicating login OK in step S the image forming device requests the print service application to provide a data list indicating jobs of a particular user.

In step S the image forming device acquires the data list from the print service application and then displays the acquired data list on the screen and prompts the user to select the data he desires to output. In step S the image forming device receives the data that the user wants to output from the data list according to the user s operation and then in step S the image forming device makes a data output request to the print service application .

Here in step S the print service application acquires data corresponding to the data output request for example the print data whose output is controlled by the data output control process illustrated in and then in step S the print service application sends the data to the image forming device . In step S the image forming device outputs the data that has been acquired from the print service application .

As described above it is possible to control the data output of a job based on rule information set in advance. Note that in the above example the data input from the terminal device is subjected to output control by the print service application and is output as print data from the image forming device however the present embodiment is not so limited.

For example the embodiment may be applied to a case where the image data acquired from the image forming device is subjected to output control by the distribution service application and data is distributed to the online storage . Furthermore the embodiment may be applied to a usage purpose where a data process such as black painting is performed on form data acquired from the terminal device and then the data is electronically saved.

According to the embodiment described above it is possible to control the output based on contents of the data upon managing the service and the service providing destination.

Next a description is given of an example of data output control of a job in the information processing system according to the embodiment described above. The following describes an example of data output control in a case where overlap detection is set in the job output request output from the image forming device in the office of the information processing system .

The input reception unit receives various input operations such as a login instruction from the user. The output unit outputs for example prints the received data.

The print service usage application includes a login request unit and a service usage request unit and provides a function of executing jobs. The login request unit provides a function of logging into the service providing system from the image forming device . The login request unit receives a job list of the user that has logged in from the service providing system .

The service usage request unit receives a selection of a job for which print output is desired via the input reception unit from the job list displayed on the operation panel of the image forming device for example and then requests the service providing system to acquire data corresponding to the received job. The setting information saving unit saves various kinds of setting information.

When the job output control unit receives a request to acquire data corresponding to a job the job output control unit determines whether overlap detection is set in the job. When the job output control unit determines that overlap detection is set in the job the job output control unit refers to a target range of overlap detection and overlap detection conditions stored in the overlap setting storage unit as conditions set in advance by the user and requests overlap detection of a job to the overlap detection unit .

The job output control unit controls output of the job according to the result of overlap detection of the job acquired from the overlap detection unit . When overlap of the job is detected the job output control unit reports to the user to stop the output of the job or deletes the job for example.

The overlap detection unit performs an overlap detection of detecting whether a job for which overlap detection has been requested overlaps with a job that has already been received based on a target range of overlap detection and overlap detection conditions acquired from the job output control unit . The overlap detection unit refers to for example information of the process target data stored in the data processing information storage unit and history information that has already been output and performs overlap detection of the job. Note that the overlap detection unit may detect the overlap of the job based on only the overlap detection condition without setting a target range of overlap detection.

The overlap setting storage unit stores a target range of overlap detection and overlap detection conditions set for each user. The target range of overlap detection is for setting the length of the past time period including jobs to be comparison targets for example jobs included in the time period extending from the present time point to the past hour based on the reception time and the output time of the job. Furthermore the target range of overlap detection may not only be for setting jobs of a particular user as comparison targets but may also set jobs of the group to which the user belongs as comparison targets.

The overlap detection conditions are for setting information of the job such as the user name the file name and the file size as information used for comparing jobs.

As illustrated in the print service application includes a job output control unit an overlap detection unit an overlap setting storage unit and a comparison target range determination unit . That is to say in the configuration of the comparison target range determination unit is included in addition to the elements of .

The comparison target range determination unit receives a request from the job output control unit and determines the comparison target range of the job for which overlap is to be detected by the overlap detection unit . The comparison target range determination unit acquires from the data processing information storage unit the process target data and history information that has already been output and determines the comparison target range of the job based on the target range of overlap detection of the overlap setting storage unit to which the job output control unit has referred. The comparison target range determination unit determines the comparison target range of the job and reports the range to the job output control unit .

Next a specific description is given of an output control process of data in a case where overlap detection is set for a job which is executed by the process blocks of the image forming device illustrated in and the print service application illustrated in . is a sequence diagram of an example of an output control process of a job.

In the example of first it is assumed that a job which has been uploaded to the service providing system from the terminal device by the user is spooled in the data storage unit by the print service application .

The image forming device accesses the print service application according to the user s operation to the login screen displayed on the operation panel in order to print out the data uploaded to the service providing system by using the print service application .

The print service application displays a job list screen of the user on the operation panel of the image forming device . When a job is selected from the job list screen the print service application displays on the operation panel of the image forming device an overlap detection setting screen for setting overlap detection for the selected job.

Note that in the overlap detection setting screen it is possible to set the target range of overlap detection and overlap detection conditions described above for each job and this information may be set for each user in advance and stored in the overlap setting storage unit . Furthermore in the job list screen displayed on the operation panel of the image forming device it may be possible to select a job together with an overlap detection setting.

As illustrated in in step S the service usage request unit receives a selection of a job made by the user in the job list screen. In step S the service usage request unit receives a report that overlap detection has been set for the selected job in the overlap detection setting screen and then in step S the service usage request unit requests the print service application to acquire the data of the job.

In step S the job output control unit of the print service application determines whether the job received from the image forming device has a setting of overlap detection. When the job output control unit determines that the job has a setting of overlap detection in step S the job output control unit refers to the target range of overlap detection and overlap detection conditions stored in the overlap setting storage unit .

In step S the job output control unit requests the overlap detection unit to perform overlap detection of the job. In step S the overlap detection unit performs overlap detection by referring to information of process target data in the data processing information storage unit and history information that has been already output based on the target range of overlap detection and overlap detection conditions acquired from the job output control unit .

Note that in step S the job output control unit may refer to the target range of overlap detection in the overlap setting storage unit and then acquire the process target data and history information that has been already output from the data processing information storage unit and determine the comparison target range of the job. Here the job output control unit excludes from the comparison targets jobs other than those determined as the comparison target range among the jobs in the process target data and the history information already output.

Accordingly in step S the overlap detection unit acquires the jobs determined as the comparison target range from the job output control unit and in step S it is possible to execute the overlap detection with respect to jobs determined as the comparison target range.

In step S the job output control unit receives an overlap detection report from the overlap detection unit and then in step S the job output control unit controls the output of the job based on the result of the overlap detection report.

Here descriptions are divided into a case where overlap is detected as a result of the overlap detection report and a case where overlap is not detected. When overlap is detected in step S the job output control unit executes a process of reporting to stop the output of the job output stop of job to the user operating the image forming device and in step S the job output control unit deletes the job for which output has been stopped.

Conversely when overlap is not detected in step S the job output control unit outputs the print data of the job to the image forming device . In step S the image forming device prints out the print data.

By the output control process of data described above even when acquisition requests are executed for the same job by detecting an overlap of jobs it is possible to prevent a job from being needlessly output.

Next a specific description is given of an output control process of data in a case where overlap detection is set for a job which is executed by the terminal device and the process blocks of the print service application illustrated in . is a sequence diagram of another example of an output control process of a job.

In the example of the terminal device accesses the portal site of the service providing system according to the user s operation in order to upload the data of the job to be printed by using the print service application of the service providing system .

Here the access control unit of the service providing system causes the terminal device to access the portal service application . The portal service application displays a login screen on the operation panel of the terminal device .

The terminal device logs into the portal service application according to a user s operation in the login screen and then accesses the print service application via the intermediate data conversion request unit . The print service application displays an upload screen on the operation panel of the terminal device .

In step S the terminal device receives data of the job from the upload screen and in step S the terminal device receives a report that the user has set overlap detection in the job to be uploaded in the upload screen.

In step S the terminal device requests the job output control unit of the print service application to input a job and then the job output control unit determines whether the job input from the terminal device has a setting of overlap detection.

When the job output control unit determines that the job has a setting of overlap detection in step S the job output control unit refers to the target range of overlap detection and overlap detection conditions stored in the overlap setting storage unit .

In step S the job output control unit requests the comparison target range determination unit to determine the comparison target range of the job based on the target range of overlap detection referred to in step S.

In step S the comparison target range determination unit acquires from the data processing information storage unit the process target data and history information that has already been output and determines the comparison target range of the job. Here the comparison target range determination unit excludes from the comparison targets jobs other than those determined as the comparison target range among the jobs in the process target data and the history information already output.

In step S the comparison target range determination unit reports the comparison target range for example from ID to ID of the job to the job output control unit .

In step S the job output control unit requests the overlap detection unit to perform overlap detection of the job. In step S the overlap detection unit performs overlap detection based on the comparison target range of the job and overlap detection conditions acquired from the job output control unit .

In step S the job output control unit receives an overlap detection report from the overlap detection unit and then in step S the job output control unit controls the output of the job based on the result of the overlap detection report. For example when overlap is detected the job output control unit implements control so that the job is not spooled in the data storage unit and when overlap is not detected the job output control unit implements control to spool the job in the data storage unit .

By the output control process of data described above even when the same job is input by detecting an overlap of jobs it is possible to prevent spooling caused by a needlessly input job. Note that even when overlap is detected the job may be spooled and the job may be deleted in the output control process of .

As described above overlap of jobs is detected at a timing when a request to acquire a job is received at the service providing system from the image forming device or at a timing when a job is input to the service providing system from the terminal device . Accordingly it is possible to detect an overlapping needless job.

According to the embodiment described above it is possible to detect an overlap of output requests upon managing the service and the service providing destination.

The service providing system and the service providing method are not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention. Note that the terminal device and the image forming device correspond to a service usage device. The user authentication unit and the user device authentication unit correspond to an authentication unit. The portal service application corresponds to a service specification unit. The print service application the data processing control unit the processing queue the data process request unit and the data processing unit correspond to an execution unit.

According to one embodiment of the present invention a service providing system and a service providing method are provided which are capable of controlling output based on contents of the data.

The present invention can be implemented in any convenient form for example using dedicated hardware or a mixture of dedicated hardware and software. The present invention may be implemented as computer software implemented by one or more networked processing apparatuses. The network can comprise any conventional terrestrial or wireless communications network such as the Internet. The processing apparatuses can compromise any suitably programmed apparatuses such as a general purpose computer personal digital assistant mobile telephone such as a WAP or 3G compliant phone and so on. Since the present invention can be implemented as software each and every aspect of the present invention thus encompasses computer software implementable on a programmable device. The computer software can be provided to the programmable device using any storage medium for storing processor readable code such as a floppy disk hard disk CD ROM magnetic tape device or solid state memory device.

The hardware platform includes any desired kind of hardware resources including for example a central processing unit CPU a random access memory RAM and a hard disk drive HDD . The CPU may be implemented by any desired kind of any desired number of processor. The RAM may be implemented by any desired kind of volatile or non volatile memory. The HDD may be implemented by any desired kind of non volatile memory capable of storing a large amount of data. The hardware resources may additionally include an input device an output device or a network device depending on the type of the apparatus. Alternatively the HDD may be provided outside of the apparatus as long as the HDD is accessible. In this example the CPU such as a cache memory of the CPU and the RAM may function as a physical memory or a primary memory of the apparatus while the HDD may function as a secondary memory of the apparatus.

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2013 157795 filed on Jul. 30 2013 Japanese Priority Patent Application No. 2013 158465 filed on Jul. 31 2013 the entire contents of which are hereby incorporated herein by reference.

