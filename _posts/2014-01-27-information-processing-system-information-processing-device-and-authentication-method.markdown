---

title: Information processing system, information processing device, and authentication method
abstract: An information processing system includes a common service providing unit configured to manage a user with organization identification information, user identification information, and unique identification information, and to provide a common service; and an application service providing unit configured to manage a user with user identification information, and to provide an application service by using the common service. The application service providing unit includes a receiving unit configured to request the common service providing unit to perform authentication on user identification information and organization identification information received from an external device, and receive, from the common service providing unit, the unique identification information associated with the user identification information and the organization identification information received from the external device, and a requesting unit configured to identify a user with the unique identification information and request the common service providing unit to provide the common service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09282091&OS=09282091&RS=09282091
owner: RICOH COMPANY, LTD.
number: 09282091
owner_city: Tokyo
owner_country: JP
publication_date: 20140127
---
The present invention relates to an information processing system an information processing device and an authentication method.

In recent years cloud computing has been garnering attention which is a form of providing services from a server to a client. In cloud computing many computing resources are used for executing data processing and processing a request from a client. There are many vendors that provide various services by implementing a web service in a cloud computing environment for realizing cloud computing as described above see for example Patent Document 1 .

The user may need to perform multiple authentication operations in order to use various services provided by cloud computing. Note that Single Sign On SSO is known as a technology for reducing the load inflicted on the user when performing authentication. By Single Sign On after the user completes a sign on operation i.e. after the user is authenticated the user does not need to execute another authentication operation see for example Patent Document 2 .

In information processing systems and information processing devices for providing services there are cases where the contents of user information used for user management are different. However in the conventional method of cooperatively executing the processes by combining the information processing systems and information processing devices inconveniences may arise in user management unless the contents of user information used for user management are redesigned so as to match each other.

The present invention provides an information processing system an information processing device and an authentication method in which one or more of the above described disadvantages are eliminated.

According to an aspect of the present invention there is provided an information processing system including one or more information processing devices the information processing system including a common service providing unit configured to manage a user with organization identification information user identification information and unique identification information and to provide a common service and an application service providing unit configured to manage a user with user identification information and to provide an application service by using the common service provided by the common service providing unit wherein the application service providing unit includes a receiving unit configured to request the common service providing unit to perform authentication on user identification information and organization identification information received from an external device and receive from the common service providing unit the unique identification information associated with the user identification information and the organization identification information received from the external device and a requesting unit configured to identify a user with the unique identification information and request the common service providing unit to provide the common service.

According to an aspect of the present invention there is provided an information processing device including a common service providing unit configured to manage a user with organization identification information user identification information and unique identification information and to provide a common service and an application service providing unit configured to manage a user with user identification information and to provide an application service by using the common service provided by the common service providing unit wherein the application service providing unit includes a receiving unit configured to request the common service providing unit to perform authentication on user identification information and organization identification information received from an external device and receive from the common service providing unit the unique identification information associated with the user identification information and the organization identification information received from the external device and a requesting unit configured to identify a user with the unique identification information and request the common service providing unit to provide the common service.

According to an aspect of the present invention there is provided an authentication method executed by an information processing system including one or more information processing devices wherein the information processing system includes a common service providing unit configured to manage a user with organization identification information user identification information and unique identification information and to provide a common service and an application service providing unit configured to manage a user with user identification information and to provide an application service by using the common service provided by the common service providing unit the authentication method including requesting by the application service providing unit the common service providing unit to perform authentication on user identification information and organization identification information received from an external device receiving by the application service providing unit from the common service providing unit the unique identification information associated with the user identification information and the organization identification information received from the external device and requesting by the application service providing unit the common service providing unit to provide the common service by identifying a user with the unique identification information.

A description is given with reference to the accompanying drawings of embodiments of the present invention.

The network N is a private network behind a firewall FW. The firewall FW is installed at the contact point between the network N and the network N and detects and blocks unauthorized accesses. To the network N a client terminal a mobile terminal and an image forming apparatus such as a multifunction peripheral are connected.

The client terminal is an example of a terminal device. The client terminal is realized by an information processing device in which a typical OS is installed. The client terminal includes a unit for performing radio communication or a unit for performing cable communication. The client terminal is a terminal that can be operated by a user such as a tablet PC and a notebook PC.

The mobile terminal is an example of a terminal device. The mobile terminal includes a unit for performing radio communication or a unit for performing cable communication. The mobile terminal is a terminal that is portable for a user such as a smartphone a mobile phone a tablet PC and a notebook PC.

The image forming apparatus is a device having an image forming function such as a multifunction peripheral. The image forming apparatus includes a unit for performing radio communication or a unit for performing cable communication. The image forming apparatus is a device for performing processes relevant to image formation such as a multifunction peripheral a copier a scanner a printer a laser printer a projector and an electronic blackboard. illustrates an example including one of each of the client terminal the mobile terminal and the image forming apparatus however there may be a plurality of each of these devices.

The network N is connected to the network N by an access control device . The security of the network N is protected by the access control device . To the network N a print service providing device a scan service providing device and another service providing device are connected.

In the information processing system of the access control device the print service providing device the scan service providing device and the other service providing device realize the service providing system. The print service providing device the scan service providing device and the other service providing device provide a print service a scan service and other services.

The access control device controls the operation of logging into a print service provided by the print service providing device and a scan service provided by the scan service providing device .

The access control device the print service providing device the scan service providing device and the other service providing device are realized by one or more information processing devices.

The access control device the print service providing device the scan service providing device and the other service providing device may be realized by being integrated in a single information processing device or may be realized by being distributed across a plurality of information processing devices.

Part of the services on the network N side may be outside the network N. The mobile terminal may be outside the network N that is a network inside the office. In the example of the information processing system of the mobile terminal is in the network N and in the network N.

The configuration of the service providing system of is one example the service providing system may be realized by the configuration illustrated in . is a configuration diagram of another example of the service providing system. In the service providing system of the network N is connected to the network N by a firewall FW.

In the network N service providing devices of a SaaS Software as a Service system service providing devices of a common service Network Service Platform system and storage devices of the storage system are connected. The service providing device of a common service system provides a service that can be commonly used by the service providing devices of the SaaS system.

The service providing devices of the SaaS system include service providing devices according to the service to be provided such as a portal service providing device a print service providing device and a scan service providing device . Furthermore the service providing devices of the common service system include service providing devices according to a common service to be provided such as an authentication service providing device a data process service providing device and a temporary data saving service providing device . The storage devices of the storage system include storage devices according to the information data to be stored such as an authentication information storage device a job information storage device and a temporary data storage device .

In the service providing system of security is protected by authentication services provided by for example the firewall FW and the authentication service providing device . Note that the configuration of the service providing system of is also one example and the service providing system may have other configurations.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device are realized by for example computer system having a hardware configuration as illustrated in .

The service providing devices of the SaaS system the service providing devices of the common service system and the storage devices of the storage system illustrated in may also be realized by for example a computer system having a hardware configuration as illustrated in .

The input device includes a keyboard a mouse and a touch panel which are used by the user for inputting operation signals. The display device includes a display etc. and displays processing results obtained by the computer system .

The communication I F is an interface for connecting the computer system to the networks N through N. Accordingly the computer system can perform data communication via the communication I F .

The HDD is a nonvolatile storage device storing programs and data. Examples of the stored programs and data are an OS Operating System which is the basic software for controlling the entire computer system and application software for providing various functions in the OS.

The HDD manages the stored programs and data by a predetermined file system and or a DB database . The external I F is an interface between the computer system and an external device. An example of the external device is a recording medium . Accordingly the computer system can read data from and or write data in the recording medium via the external I F . Examples of the recording medium are a flexible disk a CD Compact Disk a DVD Digital Versatile Disk an SD memory card and a USB memory Universal Serial Bus memory .

The ROM is a nonvolatile semiconductor memory storage device that can hold programs and data even after the power is turned off. The ROM stores programs and data such as BIOS Basic Input Output System that is executed when the computer system is activated OS settings and network settings. The RAM is a volatile semiconductor memory storage device for temporarily storing programs and data

The CPU is a processor for loading the programs and data from storage devices such as the ROM and the HDD into the RAM and executing processes control the entire computer system and realize functions.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device can realize various processes as described below by the hardware configuration of the computer system . Furthermore the service providing device of the SaaS system the service providing device of the common service system and the storage device of the storage system can also can realize various processes as described below by the hardware configuration of the computer system . Note that descriptions of hardware configurations of the image forming apparatus and the firewall FW illustrated in are omitted.

The service providing system according to the first embodiment is realized by for example process blocks as illustrated in . is a process block diagram of an example of a service providing system according to the first embodiment.

A service providing system realizes applications common services a database DB and a platform API Application Programming Interface by executing programs.

The applications include for example a portal service application a scan service application and a print service application .

The portal service application is an application for providing a portal service. A portal service provides a service acting as an entrance for using the service providing system . The scan service application is an application for providing a scan service. The print service application is an application for providing a print application. The applications may include other service applications.

The platform API is an interface for using the common services by the applications by the portal service application the scan service application and the print service application . The platform API is an interface that is defined in advance which is provided for the common services to receive requests from the applications . The platform API is constituted by for example functions and classes.

The platform API is realized by for example a Web API that can be used via the network when the service providing system is constituted by a plurality of information processing devices.

The common services include an authentication authorization unit an organization managing unit a user management unit a license management unit a device management unit a temporary image saving unit an image processing workflow control unit and a log collecting unit .

Furthermore the image processing workflow control unit includes a message queue and at least one worker . The worker realizes functions such as image conversion and image transmission.

The authentication authorization unit executes authentication authorization based on a log in request from office devices such as the client terminal and the image forming apparatus . The office device is a collective term of the client terminal the mobile terminal and the image forming apparatus .

The authentication authorization unit authenticates authorizes a user by accessing for example a user information storage unit a license information storage unit and an authority information storage unit described below. Furthermore the authentication authorization unit authenticates for example the image forming apparatus by accessing for example the organization information storage unit the license information storage unit and the device information storage unit described below.

The organization managing unit manages organization information stored in an organization information storage unit described below. The user management unit manages user information stored in the user information storage unit described below. Furthermore the user management unit manages authority information stored in the authority information storage unit described below.

The license management unit manages license information stored in the license information storage unit described below. The device management unit manages device information stored in a device information storage unit described below. The temporary image saving unit saves temporary images in a temporary image storage unit described below and acquires temporary images from the temporary image storage unit .

The image processing workflow control unit controls a workflow relevant to image processing based on a request from the applications . The message queue includes a queue corresponding to the type of process. The image processing workflow control unit submits the message of the request relevant to the process job in the queue corresponding to the type of the job.

The worker monitors the corresponding queue. When a message is submitted in the queue the worker performs a process such as image conversion and image transmission according to the type of the corresponding job. Note that the submitted message may be subjectively read pulled by the worker or may be provided pushed from the queue to the worker .

The database includes a log information storage unit an organization information storage unit a user information storage unit a license information storage unit a device information storage unit a temporary image storage unit an authority information storage unit a job information storage unit and a setting information storage unit unique to an application.

The log information storage unit stores log information. The organization information storage unit stores organization information described below. The user information storage unit stores user information described below. The license information storage unit stores license information described below. The device information storage unit stores device information described below.

The temporary image storage unit stores a temporary image. A temporary image is for example a file or data of a scan image to be processed by the worker . The authority information storage unit stores authority information described below. The job information storage unit stores information job information of a request relevant to a process job . The setting information storage unit unique to an application stores setting information unique to the application .

The service providing system functions as an integrated base for providing a common service such as a workflow relevant to authentication authorization and image processing and a group of services providing application services by using the function of the integrated base such as a scan service a print service and a portal service. The integrated base is constituted by for example the common services the database and the platform API . The group of services is constituted by for example the applications .

The service providing system illustrated in can easily develop the applications using the platform API according to the configuration in which the group of services and the integrated base are separated.

Note that the classification form of the process blocks of the service providing system illustrated in is one example it is not essential that the applications the common services and the database are classified into a hierarchy as illustrated in . As long as the process of the service providing system according to the first embodiment can be performed the hierarchical relationship illustrated in is not limited to a particular relationship.

The organization name expresses the name of a group such as a company and a department. The display language expresses the language used for expressing the name of a group such as a company and a department. The time zone expresses the standard time used by a group such as a company and a department. A state expresses the state of a group such as a company and a department. A country expresses a name of a country to which a group such as a company and a department belongs.

The user ID and the password are information for identifying a user user identification information . The user ID may be a user name. Furthermore a password is not essential. Note that the user ID and password managed by the same organization ID are unique but may be overlapping with another user ID and password if the organization ID is different.

Furthermore as the user ID information for identifying an electronic medium for example an IC card held by the user may be used. As the electronic medium held by the user an IC card a mobile phone a tablet terminal and an electronic book terminal may be used. As the information for identifying an electronic medium a card ID a serial ID a telephone number of a mobile phone and profile information of a terminal may be used. The information for identifying an electronic medium may be used in combination.

The user name expresses the name of the user. The display language expresses the language used for displaying the user name. The time zone is the standard time used by the user. The state expresses the state of the user. The country expresses the name of the country to which the user belongs.

The UUID Universally Unique Identifier is a unique identifier. For example the UUID is a unique identifier across the world however in the present embodiment the UUID does not necessarily need to be unique across the world as long as the UUID is a unique identifier in the information processing system according to the first embodiment.

Note that the process blocks of the service providing system illustrated in may be for example process blocks as illustrated in . is a process block diagram of another example of the service providing system according to the first embodiment. Note that the service providing system illustrated in is the same as the service providing system illustrated in except for some elements and therefore descriptions of the same elements are omitted.

The service providing system illustrated in realizes a domain unique API and a domain unique service in addition to the applications the common services the database DB and the platform API Application Programming Interface by executing programs.

The service providing system illustrated in is different from the service providing system illustrated in in terms of the applications the domain unique API and the domain unique service . The applications illustrated in include for example the portal service application a UI unit of a scan service application and a UI unit of a print service application . Furthermore the domain unique services include for example a logic unit of a scan application and a logic unit of a print service application

The logic unit of a scan application and the logic unit of a print service application which are logics unique to the domain receive accesses from clients other than the web browser of the mobile terminal and the image forming apparatus . In clients other than the web browser UI units such as the UI unit of a scan service application are disposed on the client side and therefore the server side only needs to provide the domain unique API .

As described above in the service providing system illustrated in the UI units such as the UI unit of a scan service application receive accesses from the web browser. Furthermore the logic units such as the logic unit of a scan application receive accesses from clients other than the web browser. Because the frequency of accesses from the web browser is different from the frequency of accesses from clients other than the web browser the scan service application and the scan application are provided as separate servers so as to efficiently perform the scaling out accompanying an increase in the frequency. Furthermore in the service providing system illustrated in multiple applications can be constructed by using domain unique APIs in combination.

In the portal service application illustrated in the portal framework is activated on the application server and the HTTP server . The portal framework includes the mapping module having functions as described below.

The portal framework collectively provides multi purpose functions to the at least one portlet and the log in UI and functions as a base of the at least one portlet and the log in UI . The at least one portlet is a removable UI component that is managed and displayed by the portal. The log in UI performs processes relevant to log in from a user operating the office device.

When a system for performing user management of a plurality of organizations and a system without the concept of organizations are used in combination and user management is performed with a user ID there may be cases where the same user ID is present across different organizations which may cause inconveniences in the user management.

For example in the case of the service providing system illustrated in when a portal service application without the concept of organizations is used the same inconvenience arises. In the service providing system illustrated in when user management is performed with a user ID there may be cases where the same user ID is present across different organizations in the common services and the database corresponding to user management of a plurality of organizations.

Therefore in the service providing system according to the first embodiment a UUID is applied to the user identification information such as a user ID. The portal service application without the concept of organizations uses the UUID when requesting a process to the common services and the database by specifying a user. The portal service application only needs to use the UUID instead of the user ID and therefore significant changes are unnecessary as described below.

The web browser displays a log in screen. The user enters in the log in screen an organization ID a user ID and a password and presses a log in button. When the log in button is pressed the web browser proceeds to step S and requests log in to the log in UI . Note that in the request for log in an organization ID a user ID and a password are included.

In step S the log in UI requests log in to the authentication authorization unit according to the organization ID the user ID and the password included in the request to log in from the web browser. The authentication authorization unit confirms whether the combination of the organization ID the user ID and the password included in the request to log in from the log in UI is stored in the user information storage unit as user information as illustrated in step S .

When the combination of the organization ID the user ID and the password included in the request to log in is stored in the user information storage unit in step S the authentication authorization unit returns the authentication ticket to the log in UI . Furthermore in step S the authentication authorization unit returns to the log in UI the UUID associated with the combination of the organization ID the user ID and the password included in the request to log in.

In step S the log in UI specifies the UUID and requests log in to the portal framework . In step S the portal framework specifies the UUID and requests log in to the mapping module . In step S the mapping module confirms whether the UUID included in the request to log in from the portal framework is stored in the user information storage unit as user information as illustrated in .

When the UUID included in the request to log in is stored in the user information storage unit in step S the mapping module returns authentication OK to the portal framework . The mapping module functions as a module for connecting the portal framework and the database .

In step S the portal framework generates a session ID and also saves the session ID and the UUID in association with each other as illustrated in . is a configuration diagram of an example of a table for associating the UUID and a session ID.

In step S the portal framework returns to the log in UI a response to the log in request of step S. When the authentication result is OK in step S the log in UI specifies a session ID and redirects the web browser to the portal framework . Note that the session ID can be set in the cookie.

The process of step S and onward is illustrated in . is a sequence diagram part 2 of 2 of an example of processing procedures for logging in. The portal framework acquires the session ID set in the cookie and reads a UUID associated with the session ID from the table illustrated in . Based on the UUID the portal framework repeatedly requests the mapping module to provide information until the information necessary for creating a portal screen can be acquired.

For example in step S the portal framework specifies a UUID and requests the mapping module to provide user table information. In step S the mapping module requests the database to provide user table information specified by the UUID. In step S the mapping module acquires the user table information from the database .

The mapping module converts the user table information acquired from the database into a data structure that can be handled at the portal framework . Then in step S the mapping module provides the user information having the data structure that can be handled at the portal framework to the portal framework .

Similar to steps S through S for example in step S the portal framework specifies the UUID and requests the mapping module to provide authority table information. In step S the mapping module requests the database to provide the authority table information specified by the UUID. In step S the mapping module acquires the authority table information from the database .

The mapping module converts the authority table information acquired from the database into a data structure that can be handled at the portal framework . Then in step S the mapping module provides the authority information having the data structure that can be handled at the portal framework to the portal framework .

Note that the user table information illustrated in is one example of the user information necessary for creating the portal screen. Furthermore the authority table information is an example of authority information necessary for creating a portal screen. The contents of the information acquired by the mapping module from the database and the procedures for acquiring the information illustrated in are one example the contents and procedures may be as described below.

For example in the case of information having configurations as illustrated in the mapping module may specify the UUID and acquire information illustrated in and specify the organization ID of the acquired user information and acquire the organization information of the license information of and the device information of . Furthermore the mapping module may specify the user ID of the acquired user information and acquire the authority information illustrated in .

When the information necessary for creating a portal screen is acquired as illustrated in the portal framework caches the information in association with the UUID. is a configuration diagram of an example of the cache data. The cache data illustrated in is for storing the information acquired from the database in association with the UUID. The cache data is cached in a storage area that can be accessed at high speed from the portal framework . Note that information for which a change needs to be immediately applied such as authority information may not be cached.

For example the setting as to whether the information is to be cached or not to be cached may be collectively set for all information items or may be set for each information item. In step S the portal framework specifies a UUID user information authority information etc. and requests a portal table to provide screen information for a portal screen.

The portal table is a table including screen information. is a configuration diagram of an example of a portal table . As illustrated in the portal screen includes a common screen provided to all portal users and a service exclusive use screen provided to a user having the usage authority to use each service.

In the portal table illustrated in for each role of the user a mark is indicated for the tab to be displayed among the tables included in the common screen and a mark is indicated for the tab to be displayed among the tabs included in the service exclusive use screen.

In step S the portal framework acquires from the portal table the screen information of the portal screen based on the role of the user and the service for which the user has a usage authority. In step S the portal framework generates a portal screen based on the screen information of the acquired portal screen and displays the portal screen on the web browser.

For example in the case of the portal table as illustrated in in a portal screen of a user who has a role user and a usage authority for the services scan service and print service the tabs of application list account information and job registration screen are displayed.

Furthermore in the case of the portal table as illustrated in in a portal screen of a user who has a role poweruser and a usage authority for the services scan service and print service all of the tabs are displayed.

Note that when the UUID acquired from the cookie is cached in the cache data illustrated in the portal framework may use the cached information without requesting the mapping module to provide information. By using the cache data the portal framework can reduce the frequency of accessing the database and can reduce the time until the portal screen is displayed.

By the service providing system according to the first embodiment even when the portal framework does not use an organization ID the user can be identified with a UUID. Thus it is easy to cooperate with the common services and the database that use an organization ID.

Therefore by using the UUID the information processing system according to the first embodiment can cancel out the difference in the user information for user management and therefore the degree of freedom in the user information for user management can be increased.

According to one embodiment of the present invention an information processing system an information processing device and an authentication method are provided which are capable of increasing the degree of freedom in user information for user management.

The image processing system the image processing device and the authentication method are not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention. For example in the present embodiment a description is given of the portal service application as one example however an embodiment of the present invention is also applicable to the scan service application and the print service application .

Note that the common service corresponds to a common service providing unit. The application corresponds to an application service providing unit. The log in UI corresponds to a receiving unit. The portal framework corresponds to a requesting unit. The UUID corresponds to unique identification information. The office device in which the web browser is installed corresponds to an external device. The mapping module corresponds to a connection unit. The user ID corresponds to user identification information. The organization ID corresponds to organization identification information.

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2013 021266 filed on Feb. 6 2013 the entire contents of which are hereby incorporated herein by reference.

