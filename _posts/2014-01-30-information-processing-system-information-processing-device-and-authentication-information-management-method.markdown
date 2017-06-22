---

title: Information processing system, information processing device, and authentication information management method
abstract: An information processing system includes a receiving unit configured to receive from an external device a use initiation request designating user specific information and organization identification information, and an authentication unit configured to issue authentication information indicating that authentication has been completed in a case where the user specific information and the organization identification information designated in the use initiation request are stored in association with each other in a first storage unit that stores one or more sets of user specific information in association with the organization identification information. The authentication unit receives a new authentication information issuance request designating the authentication information and issues new authentication information that can be used even after a user termination request designating the authentication information is made.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09514291&OS=09514291&RS=09514291
owner: Ricoh Company, Ltd.
number: 09514291
owner_city: Tokyo
owner_country: JP
publication_date: 20140130
---
The present invention relates to an information processing system an information processing device and an authentication information management method.

In recent years network systems web systems such as a LAN local area network and an intranet are set up to enable a client terminal connected to a network to use various web services that are provided by a web server using a web browser.

In such a web system a user typically inputs a login name account and a password upon requesting authentication by an authentication service from a web browser. The web system passes the login name and password input by the user to the authentication service and provides an authentication ticket to a web service so that the user may be allowed to use a function of the web service see e.g. Japanese Laid Open Patent Publication No. 2007 53580 .

A client making a request to a server for a service such as data conversion or data processing provides the server with a valid authentication ticket issued in response to a user login operation and uses a function of the server under the authority of the logged in user. Note that some processes such as data conversion or data processing that are executed by the server may require a long process time.

However the client using a function of the server under the authority of the logged in user may be unable to continue using the function of the server once the user logs out.

Accordingly a technique is desired for enabling continuation of a process executed under the authority of a user even after the user logs out.

According to an aspect of the present invention an information processing system including one or more information processing devices is provided. The information processing system includes a receiving unit configured to receive from an external device a use initiation request designating user specific information and organization identification information and an authentication unit configured to issue authentication information indicating that authentication has been completed in a case where the user specific information and the organization identification information designated in the use initiation request are stored in association with each other in a first storage unit that stores one or more sets of user specific information in association with the organization identification information. The authentication unit receives a new authentication information issuance request designating the authentication information and issues new authentication information that can be used even after a user termination request designating the authentication information is made.

According to an aspect of the present invention a process executed under the authority of a user may be continued even after the user makes a use termination request.

In the following embodiments of the present invention are described with reference to the accompanying drawings.

The network N is a private network behind a firewall FW. The firewall FW is installed at the contact point between the network N and the network N and detects and blocks unauthorized access. A client terminal a mobile terminal and an image forming apparatus such as a multifunction peripheral are connected to the network N.

The client terminal is an example of a terminal device. The client terminal is realized by an information processing device having a typical OS installed therein. The client terminal includes a unit for performing radio communication or a unit for performing cable communication. The client terminal is a terminal that can be operated by a user such as a tablet PC and a notebook PC.

The mobile terminal is an example of a terminal device. The mobile terminal includes a unit for performing radio communication or a unit for performing cable communication. The mobile terminal is a terminal that may be carried by a user such as a smartphone a mobile phone a tablet PC and a notebook PC.

The image forming apparatus is a device having an image forming function such as a multifunction peripheral. The image forming apparatus includes a unit for performing radio communication or a unit for performing cable communication. The image forming apparatus is a device for performing processes relevant to image formation such as a multifunction peripheral a copier a scanner a printer a laser printer a projector and an electronic blackboard. illustrates an example including one of each of the client terminal the mobile terminal and the image forming apparatus however there may be a plurality of each of these devices.

The network N is connected to the network N by an access control device . The security of the network N is protected by the access control device . A print service providing device a scan service providing device and another service providing device are connected to the network N.

In the information processing system of the access control device the print service providing device the scan service providing device and the other service providing device realize a service providing system. The print service providing device the scan service providing device and the other service providing device provide a print service a scan service and other services.

The access control device controls the operation of logging into a print service provided by the print service providing device or a scan service provided by the scan service providing device for example.

The access control device the print service providing device the scan service providing device and the other service providing device are realized by one or more information processing devices.

The access control device the print service providing device the scan service providing device and the other service providing device may be realized by being integrated in a single information processing device or may be realized by being distributed across a plurality of information processing devices.

Part of the services on the network N side may be outside the network N. The mobile terminal may be outside the network N namely outside the office network for example. In the information processing system illustrated in one mobile terminal is connected to the network N and another mobile terminal is connected to the network N.

The configuration of the service providing system illustrated in is merely one example that is the service providing system may alternatively have a configuration as illustrated in for example. is a configuration diagram of another example of the service providing system. In the service providing system of the network N is connected to the network N by a firewall FW.

In the network N service providing devices of a SaaS Software as a Service system service providing devices of a common service Network Service Platform system and storage devices of a storage system are connected. The service providing device of a common service system provides a service that can be commonly used by the service providing devices of the SaaS system.

The service providing devices of the SaaS system include service providing devices according to the service to be provided such as a portal service providing device a print service providing device and a scan service providing device . Furthermore the service providing devices of the common service system include service providing devices according to a common service to be provided such as an authentication service providing device a data process service providing device and a temporary data saving service providing device . The storage devices of the storage system include storage devices according to the information data to be stored such as an authentication information storage device a job information storage device and a temporary data storage device .

In the service providing system of security is protected by authentication services provided by for example the firewall FW and the authentication service providing device . Note that the configuration of the service providing system of is also one example and the service providing system may have other configurations.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device are realized by for example a computer system having a hardware configuration as illustrated in .

The service providing devices of the SaaS system the service providing devices of the common service system and the storage devices of the storage system illustrated in may also be realized by for example a computer system having a hardware configuration as illustrated in .

The input device includes a keyboard a mouse and a touch panel which are used by the user for inputting operation signals. The display device includes a display etc. and displays processing results obtained by the computer system .

The communication I F is an interface for connecting the computer system to the networks N through N. Accordingly the computer system can perform data communication via the communication I F .

The HDD is a nonvolatile storage device storing programs and data. Examples of the stored programs and data are an OS Operating System which is the basic software for controlling the entire computer system and application software for providing various functions in the OS.

The HDD manages the stored programs and data by a predetermined file system and or a DB database . The external I F is an interface between the computer system and an external device. An example of the external device is a recording medium . Accordingly the computer system can read data from and or write data in the recording medium via the external I F . Examples of the recording medium are a flexible disk a CD Compact Disk a DVD Digital Versatile Disk an SD memory card and a USB memory Universal Serial Bus memory .

The ROM is a nonvolatile semiconductor memory storage device that can hold programs and data even after the power is turned off. The ROM stores programs and data such as BIOS Basic Input Output System that is executed when the computer system is activated OS settings and network settings. The RAM is a volatile semiconductor memory storage device for temporarily storing programs and data.

The CPU is a processor that controls and executes overall operations and functions of the computer system by loading programs and data from storage devices such as the ROM and the HDD into the RAM and executing relevant processes for example.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device can realize various processes as described below by the hardware configuration of the computer system . Furthermore the service providing device of the SaaS system the service providing device of the common service system and the storage device of the storage system can also realize various processes as described below by the hardware configuration of the computer system . Note that descriptions of hardware configurations of the image forming apparatus and the firewall FW illustrated in are omitted.

The service providing system according to the first embodiment is realized by for example process blocks as illustrated in . is a process block diagram of an example of a service providing system according to the first embodiment.

A service providing system realizes applications common services a database DB and a platform API Application Programming Interface by executing programs.

The applications include for example a portal service application a scan service application and a print service application .

The portal service application is an application for providing a portal service. A portal service provides a service acting as an entrance for using the service providing system . The scan service application is an application for providing a scan service. The print service application is an application for providing a print application. The applications may include other service applications.

The platform API is an interface for using the common services by the applications by the portal service application the scan service application and the print service application . The platform API is an interface that is defined in advance which is provided for the common services to receive requests from the applications . The platform API may include functions and classes for example.

The platform API may be realized by for example a Web API that can be used via the network in a case where the service providing system includes a plurality of information processing devices.

The common services include an authentication authorization unit an organization management unit a user management unit a license management unit a device management unit a temporary image saving unit an image processing workflow control unit and a log collection unit .

Furthermore the image processing workflow control unit includes a message queue and at least one worker . The worker realizes functions such as image conversion and image transmission.

The authentication authorization unit executes authentication authorization based on a login request from office devices such as the client terminal and the image forming apparatus . The term office device is used below as a generic term for devices used at the office such as the client terminal the mobile terminal and the image forming apparatus .

The authentication authorization unit authenticates authorizes a user by accessing for example a user information storage unit and a license information storage unit which are described below. Also the authentication authorization unit authenticates for example the image forming apparatus by accessing for example an organization information storage unit the license information storage unit and a device information storage unit described below. The authentication authorization unit authenticates authorizes a login request and returns an authentication ticket.

The organization management unit manages organization information stored in the organization information storage unit described below. The user management unit manages user information stored in the user information storage unit described below.

The license management unit manages license information stored in the license information storage unit described below. The device management unit manages device information stored in a device information storage unit described below. The temporary image saving unit saves temporary images in a temporary image storage unit described below and acquires temporary images from the temporary image storage unit .

The image processing workflow control unit controls a workflow relevant to image processing based on a request from the applications . The message queue includes a queue corresponding to the type of process. The image processing workflow control unit submits the message of the request relevant to the process job in the queue corresponding to the type of the job.

The worker monitors the corresponding queue. When a message is submitted in the queue the worker performs a process such as image conversion and image transmission according to the type of the corresponding job. Note that the submitted message may be subjectively read pulled by the worker or may be provided pushed from the queue to the worker .

The database includes a log information storage unit an organization information storage unit a user information storage unit a license information storage unit a device information storage unit a temporary image storage unit a job information storage unit and an application specific setting information storage unit .

The log information storage unit stores log information. The organization information storage unit stores organization information described below. The user information storage unit stores user information described below. The license information storage unit stores license information described below. The device information storage unit stores device information described below.

The temporary image storage unit stores a temporary image. A temporary image is for example a file or data of a scan image to be processed by the worker . The job information storage unit stores information job information of a request relevant to a process job . The application specific setting information storage unit stores setting information unique to the applications .

The service providing system functions as an integrated base for providing a common service such as a workflow relevant to authentication authorization and image processing and a group of services providing application services by using the function of the integrated base such as a scan service a print service and a portal service. The integrated base is constituted by for example the common services the database and the platform API . The group of services is constituted by for example the applications .

Note that the classification form of the process blocks of the service providing system illustrated in is one example that is the applications the common services and the database do not necessarily have to be classified into a hierarchy as illustrated in . As long as the process of the service providing system according to the first embodiment can be performed the hierarchical relationship illustrated in is not limited to a particular relationship.

The organization name is the name of a group such as a company and department. The country indicates the country where a group such as a company and a department is located. The language indicates the language used by a group such as a company and a department. The address information indicates an email address of a group such as a company and a department.

Further as the user name information for identifying an electronic medium e.g. IC card owned by the user may be used. Examples of an electronic medium owned by the user include an IC card a mobile phone a tablet terminal and an electronic book terminal for example. As the information for identifying the electronic medium a card ID a serial ID a telephone number of a mobile phone profile information of a terminal or a combination of the above may be used for example.

In step S the client terminal makes a login request to the application of the service providing system designating the user specific information input by the user in the login request. In step S the application makes a login request to the authentication authorization unit designating the user specific information. Note that the login request of step S may be made using an authentication API included in the platform API for example.

The authentication authorization unit includes an authentication unit and a ticket management unit as sub modules. The authentication unit of the authentication authorization unit handles the login request from the application . In step S the authentication unit checks whether the user specific information designated in the login request matches user specific information stored in the user information storage unit for example.

If it is confirmed that the user specific information designated in the login request matches the stored user specific information the authentication unit makes a ticket issuance request to the ticket management unit designating the organization ID and the user ID included in the user specific information designated in the login request. In turn the ticket management unit issues authentication ticket and registers the organization ID the user ID and the authentication ticket in association with each other in a table see e.g. described below .

In step S the ticket management unit returns the issued authentication ticket to the authentication unit . In step S the authentication unit returns the authentication ticket to the application corresponding to the sender of the login request. Note that in returning the authentication ticket in step S the authentication ticket may be set up in a cookie for example.

Then in step S the application returns the authentication ticket to the client terminal corresponding to the sender of the login request. In this way the client terminal may acquire the authentication ticket issued in response to the login operation by the user.

The user may use the authentication ticket acquired by the login process of to make a process request to the service providing system as illustrated in for example. is a sequence chart illustrating an exemplary process that may be executed when the user makes a process request to the service providing system . Note that in the example illustrated in the applications include an application A that executes a synchronous process and an application B that executes an asynchronous process.

In step S the client terminal makes a process request to the application A of the service providing system using the acquired authentication ticket i.e. valid authentication ticket . The application A determines whether the process requested by the process request from the client terminal is an asynchronous process.

If the requested process is an asynchronous process in step S the application A makes a new ticket issuance request to the authentication authorization unit designating the authentication ticket . The new ticket issuance request of step S may be made using the authentication API included in the platform API for example.

In step S the authentication unit makes a request to the ticket management unit to check the authentication ticket designated in the new ticket issuance request. The ticket management unit refers to the table see e.g. described below to check whether the authentication ticket is registered. If the authentication ticket is registered in the table the ticket management unit may determine that the authentication ticket is a valid ticket. Upon confirming that the authentication ticket is registered in step S the ticket management unit refers to the table and returns an organization ID and a user ID that are stored in association with the authentication ticket to the authentication unit .

In step S the authentication unit makes a ticket issuance request to the ticket management unit designating the organization ID and the user ID associated with the authentication ticket . In turn the ticket management unit issues authentication ticket and registers the authentication ticket in association with the organization ID and the user ID in the table as illustrated in for example.

As described above in the table managed by the ticket management unit the authentication ticket designated in the new ticket issuance request is not discarded but is instead registered together with the authentication ticket issued in response to the new ticket issuance request.

In step S the ticket management unit returns the issued authentication ticket to the authentication unit . Then in step S authentication unit returns the authentication ticket to the application A corresponding to the sender of the new ticket issuance request. Note that the authentication ticket may be returned in step S by setting up the authentication ticket in a cookie for example.

In step S the application A makes a process execution request designating the authentication ticket to the application B for prompting the application B to execute the requested asynchronous process using the authentication request . Upon receiving the process execution request designating the authentication ticket the application B starts the requested asynchronous process under the authority of user A logged in user .

In step S the application A returns a response to the process request received in step S. After step S the user operates the client terminal to issue a logout request. Note that the logout request is an example of a use termination request.

In step S the client terminal makes a logout request to the application A for prompting the application A to perform a logout operation using the authentication ticket . In step S the application A makes a logout request designating the authentication ticket to the authentication authorization unit . Note that the logout request of step S may be made using the authentication API included in the platform API for example.

In step S the authentication unit sends a ticket deletion request designating the authentication request to the ticket management unit for prompting the ticket management unit to discard delete the authentication ticket . In turn the ticket authentication unit deletes the authentication ticket from the table as illustrated in . In step S the ticket management unit returns a response to the ticket deletion request received in step S to the authentication unit . In step S the authentication unit returns a response to the logout request received in step S to the application A.

Then the application A returns a login screen as a response to the logout request received in step S to the client terminal . In turn the client terminal displays the login screen and in this way the user may be notified of the completion of the logout operation.

According to the process illustrated in FIG. when a process request is made by user A with a valid authentication ticket an authentication ticket is generated that is not discarded even after the user A logs out. Accordingly even when the authentication ticket is discarded after the user A logs out the authentication ticket associated with the user A remains registered in the table. In this way the application B may continue execution of the asynchronous process under the authority of the user A even after the user A logs out.

Note that although not illustrated in when the application B completes the asynchronous process the application B may issue a logout request designating the authentication ticket and in this way the authentication ticket may be deleted from the table illustrated in . Note that the authentication ticket cannot be discarded deleted by the user. Also the new ticket issuance request of step S can be used even when a corresponding account is locked.

As can be appreciated from the above descriptions in the service providing system according to the first embodiment when a process that requires a long time is executed asynchronously under the authority of a user execution of the asynchronous process under the authority of the user may be continued even after the user logs out.

In the following exemplary uses of the authentication ticket new authentication ticket that is not discarded even after the user logs out are described.

For example the portal service application illustrated in may include a user management function. The user management function of the portal service application may include importing exporting and deleting user information for example. In some cases processes for importing exporting or deleting user information may take a long time. Accordingly the authentication ticket new authentication ticket that is not discarded even after the user logs out may be used to continue such processes even after the user logs out.

In step S the portal service application makes a login request to the authentication authorization unit designating the user specific information input by the user. If authentication using the designated user specific information is successful the authentication authorization unit issues an authentication ticket and registers the issued authentication ticket the organization ID and the user ID in association with each other in the table illustrated in .

In step S the authentication authorization unit returns the issued authentication ticket to the portal service application corresponding to the sender of the login request. In step S the portal service application sets up the authentication ticket in a cookie for example. In step S the portal service application makes a user list information acquisition request to the authentication authorization unit designating the authentication ticket. In step S the portal service application acquires the user list information from the authentication authorization unit .

Then in step S the portal service application generates a user list screen. The portal service application prompts the client terminal to display the generated user list screen.

A process of inputting additional user information from a UI user interface after prompting the client terminal to display the user list screen is one example of a synchronous process executed by the portal service application .

In step S the portal service application receives a response to the user addition request from the authentication authorization unit . In step S if the user addition process is properly completed the portal service application generates a user list screen with the additional user information added thereto. The portal service application prompts the client terminal to display the user list screen with the added user information.

In the following referring to a process of adding user information in a batch from a file is described as an example of an asynchronous process.

The user may operate the client terminal for example to input necessary information for executing a process of adding user information in a batch from a file user information import process from a UI as illustrated in for example. is an exemplary image of the UI for enabling the import process.

The UI illustrated in is for prompting a user to set up information related to import conditions for importing user information and select the file in which the user information is recorded. The import conditions may include a character code and whether to send a notification to a newly registered user for example. After setting up the import conditions and selecting the relevant file the user presses the OK button. In turn client terminal makes a request to the portal service application to execute the process of importing the user information from the selected file.

In step S because the process of importing the user information from a file requested by the client terminal corresponds to an asynchronous process the portal service application sends a new ticket issuance request to the authentication authorization unit designating the authentication ticket acquired by the login process.

Note that the process steps of the authentication authorization unit executed in response to the new ticket issuance request made in step S may be identical to steps S S illustrated in so that their descriptions are omitted. Then in step S the authentication authorization unit returns the newly issued authentication ticket to the portal service application corresponding to the sender of the new ticket issuance request. In step S the portal service application sets up the new authentication ticket in a cookie.

In step S the portal service application makes a user batch addition request to a batch process job thread designating the new authentication ticket and a list of user addition request information. Note that the batch process job thread is an example of a process agent that handles the user addition request on behalf of the portal service application .

The batch process job thread loops process steps S S for the number of users included in the list of user addition request information. In step S the batch process job thread makes a user addition request to the authentication authorization unit designating the new authentication ticket. In step S the batch process job thread receives a response to the user addition request from the authentication authorization unit .

After looping steps S for the number of users included in the list of user addition request information the batch process job thread makes a logout request to the authentication authorization unit designating the new authentication request.

In step S the portal service application makes a user list information acquisition request to the authentication authorization unit asynchronously with respect to the process executed by the batch process job thread . In step S the portal service application acquires user list information from the authentication authorization unit . The user list information acquired by the portal service application reflects the user information addition implemented by the batch process job thread . For example if the user information addition by the batch process job thread is partially completed the user list information acquired by the portal service application reflects the partially completed addition of user information.

Then in step S the portal service application generates a user list screen. The portal service application prompts the client terminal to display the generated user list screen.

In the process illustrated in a new ticket that is not discarded even after the user logs out is generated upon importing user information and in this way the user information import process executed by the batch process job thread may be continued even after the user logs out. Note that use of the new authentication ticket is not limited to the case of importing user information. For example the new authentication ticket may similarly be used in exporting user information or deleting user information.

For example the scan service application illustrated in may include a function for registering and executing a job. In some cases such a job process may take a long time. Accordingly the authentication ticket new authentication ticket that is not discarded even after the user logs out as described above may be used to enable the scan service application to continue the job process even after the user logs out.

In step S the portal service application makes a login request to the authentication authorization unit designating the user specific information input by the user. If the authentication based on the user specific information designated in the login request is successful the authentication authorization unit generates an authentication ticket and registers the generated authentication ticket the organization ID and the user ID in association with each other in the table illustrated in . In step S the authentication authorization unit returns the authentication ticket to the portal service application corresponding to the sender of the login request.

The portal service application sets up the authentication ticket in a cookie. In step S the portal service application makes an information acquisition setting request to the scan service application designating the authentication request. In step S the scan service application acquires the authentication ticket from the cookie.

In steps S and S the scan service application makes an information acquisition request to the authentication authorization unit based on the information acquisition setting request from the portal service application and acquires the requested information.

In step S the scan service application makes an information acquisition setting request to the common services to set up the information acquired from the authentication authorization unit based on the information acquisition setting request from the portal service application . The information is set up by the common services as requested and in step S a result of the setting operation is returned from the common services to the scan service application . In step S the scan service application returns a response to the information acquisition setting request from the portal service application .

Note that the information acquisition setting process illustrated in is an example of a synchronous process. In the following referring to a job registration process is described as an example of an asynchronous process. is a sequence chart illustrating an exemplary job registration process.

In step S the portal service application makes a login request to the authentication authorization unit designating the user specific information input by the user. If authentication based on the user specific information designated in the login request is successful the authentication authorization unit issues an authentication ticket and registers the issued authentication ticket the organization ID and the user ID in association with each other in the table illustrated in . In step S the authentication authorization unit returns the authentication ticket to the portal service application corresponding to the sender of the login request.

The portal service application sets up the authentication ticket in a cookie for example. In step S the portal service application makes a job registration request to the scan service application designating the authentication ticket. The scan service application acquires the authentication ticket from the cookie.

In steps S and S the scan service application makes an information acquisition request to the authentication authorization unit based on the job registration request from the portal service application and acquires the requested information from the authentication authorization unit .

Also in step S because the job registration process corresponds to an asynchronous process the scan service application makes a new ticket issuance request to the authentication authorization unit designating the authentication ticket obtained from the login operation.

Note that the process steps executed by the authentication authorization unit in response to the new ticket issuance request of step S may be identical to steps S S of so that their descriptions are omitted. Then in step S the authentication authorization unit returns the new authentication ticket to the scan service application corresponding to the sender of the new ticket issuance request. In step S the scan service application sets up the new authentication ticket in a cookie.

In step S the scan service application makes a job registration request to the image processing workflow control unit designating the new authentication ticket. In step S the image processing workflow control unit returns a job registration result to the scan service application . Then in step S the scan service application returns a response to the job registration request from the portal service application .

Note that the image processing workflow control unit may include a callback function for calling back a designated application after a job is completed. Job information of the job registered in the image processing workflow control unit by the scan service application in step S may have a data configuration as illustrated in for example.

The user ID is information indicating the user requesting execution of the job. The organization ID is information indicating the organization requesting execution of the job. The application ID is information indicating the application requesting execution of the job. The callback URL is information indicating the URL that is to be called back after completion of the job. The cookie information required for callback is information to be used upon calling back the application .

Note that in the example illustrated in the URL of the scan service application may be set up as the callback URL and the new authentication ticket may be set up in the cookie information required for callback.

In step S the image processing workflow control unit notifies the scan service application of the job completion i.e. calls back the scan service application . Note that in step S the image processing workflow control unit may use the cookie information required for callback included in the portion related to the definition of the job of the job information illustrated in to attach the new authentication ticket used for executing the job to the callback.

In step S the scan service application acquires the new authentication ticket from the callback. In step S the scan service application makes a request for services such as updating information to the common services . In step S the scan service application receives a response to the request for services such as updating information from the common services .

In step S the scan service application makes a logout request to the authentication authorization unit designating the new authentication ticket. In turn the authentication authorization unit deletes the new authentication ticket designated in the logout request from the table.

In step S the authentication authorization unit returns a response to the logout request received in step S. Then in step S the scan service application returns a response to the callback of step S to the image processing workflow control unit .

As can be appreciated in the job registration process as illustrated in a new authentication ticket that is not discarded even after the user logs out is issued so that the image processing workflow control unit may continue execution of processes related to the job even after the user logs out.

Also in the job registration process as illustrated in a callback URL to be called upon job completion and cookie information required for callback may be set up in the job information of the job that is registered so that authentication may be omitted upon callback. Further in the process illustrated in the new authentication ticket used for executing the job is attached to the callback and conveyed from the image processing workflow control unit to the scan service application . In this way the scan service application may be able to logout using the new authentication ticket.

In the service providing system according to the first embodiment when a process that takes a long time is executed asynchronously under the authority of a user even after the user logs out the process may continue to be executed under the authority of the logged out user.

The present invention is not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention.

Note that the portal service application described above corresponds to an exemplary embodiment of a receiving unit. The authentication authorization unit corresponds to an exemplary embodiment of an authentication unit. The application B for executing an asynchronous process the batch process job thread and the image processing workflow control unit correspond to exemplary embodiments of an execution unit.

Also the office device such as the client terminal corresponds to an exemplary embodiment of an external device. The user information storage unit corresponds to an exemplary embodiment of a first storage unit. The table as illustrated in corresponds to an exemplary embodiment of a second storage unit. The cookie information required for callback corresponds to an exemplary embodiment of information required for notifying a notification destination of a completion of the requested process execution. The organization ID corresponds to an exemplary embodiment of organization identification information. The authentication ticket corresponds to an exemplary embodiment of authentication information indicating that authentication has been completed. The new authentication ticket corresponds to exemplary new authentication information.

The present application is based on and claims the benefit of priority of Japanese Patent Application No. 2013 021265 filed on Feb. 6 2013 the entire contents of which are hereby incorporated herein by reference.

