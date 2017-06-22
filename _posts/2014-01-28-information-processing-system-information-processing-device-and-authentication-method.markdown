---

title: Information processing system, information processing device, and authentication method
abstract: An information processing system includes a receiving unit that receives user identification information and organization identification information from an external device, and an authentication unit that performs authentication of the user identification information and the organization identification information received by the receiving unit using a first storage unit storing one or more sets of user identification information in association with organization identification information. When the authentication unit receives a federated authentication request to access an external service from the external device that is authenticated, the authentication unit sends a federated authentication response to the external device if the organization identification information received from the external device and the external service designated in the federated authentication request are associated with each other in a second storage unit storing the organization identification information in association with information on one or more external services that have established a trust relationship for authentication.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09210159&OS=09210159&RS=09210159
owner: RICOH COMPANY, LTD.
number: 09210159
owner_city: Tokyo
owner_country: JP
publication_date: 20140128
---
The present invention relates to an information processing system an information processing device and an authentication method.

In recent years attention has been directed to cloud computing technology which is a form of providing services from a server to a client. In cloud computing many computing resources are used for executing data processing and processing a request from a client. There are many vendors that provide various services by implementing a web service in a cloud computing environment for realizing cloud computing as described above see e.g. Japanese Laid Open Patent Publication No. 2012 226700 .

The user may need to perform multiple authentication operations in order to use various services provided by cloud computing. Note that Single Sign On SSO is known as a technology for reducing the load on the user when performing authentication. By using Single Sign On once the user completes a sign on login operation i.e. once the user is authenticated the user does not have to execute another sign on operation with respect to another service see e.g. Japanese Laid Open Patent Publication No. 2006 31714 .

The Single Sign On is an authentication method that involves utilizing a common authentication base for a plurality of services such that once authentication is performed with respect to one service authentication may be omitted with respect to other services. To implement Single Sign On a trust relationship must be established beforehand between an IdP Identity Provider that provides authentication authorization information and a SP Service Provider that provides services to a client according to authentication authorization information issued by the IdP. Such a trust relationship between an IdP and a SP is referred to as trust circle . A user that is authenticated at the IdP is able to forgo authentication at an SP that has established a trust relationship with the IdP beforehand i.e. SP that belongs to the same trust circle .

Services of an IdP that are provided by cloud computing may be used by a plurality of organizations. An SP belonging to a trust circle may vary depending on each organization. However a conventional IdP lacks the means to accommodate such a variation.

Accordingly there is a demand for a technique for enhancing flexibility in establishing a trust relationship for authentication.

According to an aspect of the present invention an information processing system including one or more information processing devices is provided. The information processing system includes a receiving unit configured to receive user identification information and organization identification information from an external device and an authentication unit configured to perform authentication with respect to the user identification information and the organization identification information received from the external device by the receiving unit using a first storage unit that stores one or more sets of user identification information in association with organization identification information. When the authentication unit receives a federated authentication request to access an external service from the external device that is authenticated the authentication unit sends a federated authentication response to the external device if the organization identification information received from the external device and the external service designated in the federated authentication request are stored in association with each other in a second storage unit that stores the organization identification information in association with information on one or more external services that have established a trust relationship for authentication.

According to an aspect of the present invention flexibility may be enhanced in establishing a trust relationship for authentication.

In the following embodiments of the present invention are described with reference to the accompanying drawings.

The network N1 is a private network behind a firewall FW. The firewall FW is installed at the contact point between the network N1 and the network N3 and detects and blocks unauthorized access. A client terminal a mobile terminal and an image forming apparatus such as a multifunction peripheral are connected to the network N1.

The client terminal is an example of a terminal device. The client terminal is realized by an information processing device having a typical OS installed therein. The client terminal includes a unit for performing radio communication or a unit for performing cable communication. The client terminal is a terminal that can be operated by a user such as a tablet PC and a notebook PC.

The mobile terminal is an example of a terminal device. The mobile terminal includes a unit for performing radio communication or a unit for performing cable communication. The mobile terminal is a terminal that may be carried by a user such as a smartphone a mobile phone a tablet PC and a notebook PC.

The image forming apparatus is a device having an image forming function such as a multifunction peripheral. The image forming apparatus includes a unit for performing radio communication or a unit for performing cable communication. The image forming apparatus is a device for performing processes relevant to image formation such as a multifunction peripheral a copier a scanner a printer a laser printer a projector and an electronic blackboard. illustrates an example including one of each of the client terminal the mobile terminal and the image forming apparatus however there may be a plurality of each of these devices.

The network N2 is connected to the network N3 by an access control device . The security of the network N2 is protected by the access control device . A print service providing device a scan service providing device and another service providing device are connected to the network N2.

In the information processing system of the access control device the print service providing device the scan service providing device and the other service providing device realize a service providing system. The print service providing device the scan service providing device and the other service providing device provide a print service a scan service and other services.

The access control device controls the operation of logging into a print service provided by the print service providing device or a scan service provided by the scan service providing device for example.

The access control device the print service providing device the scan service providing device and the other service providing device are realized by one or more information processing devices.

The access control device the print service providing device the scan service providing device and the other service providing device may be realized by being integrated in a single information processing device or may be realized by being distributed across a plurality of information processing devices.

Part of the services on the network N2 side may be outside the network N2. The mobile terminal may be outside the network N1 namely outside the office network for example. In the information processing system illustrated in one mobile terminal is connected to the network N1 and another mobile terminal is connected to the network N3.

An external service that is connected to the network N3 may be a device that provides an online storage service for example. Note that the external service is an exemplary embodiment of a SP that provides a service to a client according to authentication authorization information issued by an IdP. The service providing system is an exemplary embodiment of an IdP and a SP.

The configuration of the service providing system illustrated in is merely one example that is the service providing system may alternatively have a configuration as illustrated in for example. is a configuration diagram of another example of the service providing system. In the service providing system of the network N2 is connected to the network N3 by a firewall FW.

In the network N2 service providing devices of a SaaS Software as a Service system service providing devices of a common service Network Service Platform system and storage devices of a storage system are connected. The service providing device of a common service system provides a service that can be commonly used by the service providing devices of the SaaS system.

The service providing devices of the SaaS system include service providing devices according to the service to be provided such as a portal service providing device a print service providing device and a scan service providing device . Furthermore the service providing devices of the common service system include service providing devices according to a common service to be provided such as an authentication service providing device a data process service providing device and a temporary data saving service providing device . The storage devices of the storage system include storage devices according to the information data to be stored such as an authentication information storage device a job information storage device and a temporary data storage device .

In the service providing system of security is protected by authentication services provided by for example the firewall FW and the authentication service providing device . Note that the configuration of the service providing system of is also one example and the service providing system may have other configurations.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device are realized by for example a computer system having a hardware configuration as illustrated in .

The service providing devices of the SaaS system the service providing devices of the common service system and the storage devices of the storage system illustrated in may also be realized by for example a computer system having a hardware configuration as illustrated in .

The input device includes a keyboard a mouse and a touch panel which are used by the user for inputting operation signals. The display device includes a display etc. and displays processing results obtained by the computer system .

The communication I F is an interface for connecting the computer system to the networks N1 through N3. Accordingly the computer system can perform data communication via the communication I F .

The HDD is a nonvolatile storage device storing programs and data. Examples of the stored programs and data are an OS Operating System which is the basic software for controlling the entire computer system and application software for providing various functions in the OS.

The HDD manages the stored programs and data by a predetermined file system and or a DB database . The external I F is an interface between the computer system and an external device. An example of the external device is a recording medium . Accordingly the computer system can read data from and or write data in the recording medium via the external I F . Examples of the recording medium are a flexible disk a CD Compact Disk a DVD Digital Versatile Disk an SD memory card and a USB memory Universal Serial Bus memory .

The ROM is a nonvolatile semiconductor memory storage device that can hold programs and data even after the power is turned off. The ROM stores programs and data such as BIOS Basic Input Output System that is executed when the computer system is activated OS settings and network settings. The RAM is a volatile semiconductor memory storage device for temporarily storing programs and data

The CPU is a processor that controls and executes overall operations and functions of the computer system by loading programs and data from storage devices such as the ROM and the HDD into the RAM and executing relevant processes for example.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device can realize various processes as described below by the hardware configuration of the computer system . Furthermore the service providing device of the SaaS system the service providing device of the common service system and the storage device of the storage system can also realize various processes as described below by the hardware configuration of the computer system . Note that descriptions of hardware configurations of the image forming apparatus and the firewall FW illustrated in are omitted.

The service providing system according to the first embodiment is realized by for example process blocks as illustrated in . is a process block diagram of an example of a service providing system according to the first embodiment.

A service providing system realizes applications common services a database DB and a platform API Application Programming Interface by executing programs.

The applications include for example a portal service application a scan service application and a print service application .

The portal service application is an application for providing a portal service. A portal service provides a service acting as an entrance for using the service providing system . The scan service application is an application for providing a scan service. The print service application is an application for providing a print application. The applications may include other service applications.

The platform API is an interface for using the common services by the applications by the portal service application the scan service application and the print service application . The platform API is an interface that is defined in advance which is provided for the common services to receive requests from the applications . The platform API may include functions and classes for example.

The platform API may be realized by for example a Web API that can be used via the network in a case where the service providing system includes a plurality of information processing devices.

The common services include an authentication authorization unit an organization managing unit a user management unit a license management unit a device management unit a temporary image saving unit an image processing workflow control unit and a log collection unit .

Furthermore the image processing workflow control unit includes a message queue and at least one worker . The worker realizes functions such as image conversion and image transmission.

The authentication authorization unit executes authentication authorization based on a login request from office devices such as the client terminal and the image forming apparatus . The term office device is used below as a generic term for devices used at the office such as the client terminal the mobile terminal and the image forming apparatus .

The authentication authorization unit authenticates authorizes a user by accessing for example a user information storage unit and a license information storage unit which are described below. Furthermore the authentication authorization unit authenticates for example the image forming apparatus by accessing for example the organization information storage unit the license information storage unit and the device information storage unit described below.

The organization managing unit manages organization information stored in an organization information storage unit described below. The user management unit manages user information stored in the user information storage unit described below.

The license management unit manages license information stored in the license information storage unit described below. The device management unit manages device information stored in a device information storage unit described below. The temporary image saving unit saves temporary images in a temporary image storage unit described below and acquires temporary images from the temporary image storage unit .

The image processing workflow control unit controls a workflow relevant to image processing based on a request from the applications . The message queue includes a queue corresponding to the type of process. The image processing workflow control unit submits the message of the request relevant to the process job in the queue corresponding to the type of the job.

The worker monitors the corresponding queue. When a message is submitted in the queue the worker performs a process such as image conversion and image transmission according to the type of the corresponding job. Note that the submitted message may be subjectively read pulled by the worker or may be provided pushed from the queue to the worker .

The database includes a log information storage unit an organization information storage unit a user information storage unit a license information storage unit a device information storage unit a temporary image storage unit a job information storage unit and an application specific setting information storage unit .

The log information storage unit stores log information. The organization information storage unit stores organization information described below. The user information storage unit stores user information described below. The license information storage unit stores license information described below. The device information storage unit stores device information described below.

The temporary image storage unit stores a temporary image. A temporary image is for example a file or data of a scan image to be processed by the worker . The job information storage unit stores information job information of a request relevant to a process job . The application specific setting information storage unit stores setting information unique to the application .

The service providing system functions as an integrated base for providing a common service such as a workflow relevant to authentication authorization and image processing and a group of services providing application services by using the function of the integrated base such as a scan service a print service and a portal service. The integrated base is constituted by for example the common services the database and the platform API . The group of services is constituted by for example the applications .

The service providing system illustrated in can easily develop the applications using the platform API according to the configuration in which the group of services and the integrated base are separated.

Note that the classification form of the process blocks of the service providing system illustrated in is one example that is the applications the common services and the database do not necessarily have to be classified into a hierarchy as illustrated in . As long as the process of the service providing system according to the first embodiment can be performed the hierarchical relationship illustrated in is not limited to a particular relationship.

The organization ID is information for identifying a group such as a company and a department. The organization ID is not limited to information specifically identifying the organization itself but may be in other forms such as information identifying a subscription for example. Note that the organization ID is unique.

The organization name display language indicates the language used for expressing the name of a group such as a company and a department. The time zone indicates the standard time used by a group such as a company and a department. A state indicates the state or status of a group such as a company and a department. A country indicates the country of a group such as a company and a department.

As described below single sign on setting information is configured to have the data structure of the organization information as illustrated in . By configuring the organization information as illustrated in the service providing system may set up a trust circle associated with an organization and implement SAML based single sign on that can accommodate a plurality of organizations.

Further as the user name information for identifying an electronic medium e.g. IC card owned by the user may be used. Examples of an electronic medium owned by the user include an IC card a mobile phone a tablet terminal and an electronic book terminal for example. As the information for identifying the electronic medium a card ID a serial ID a telephone number of a mobile phone profile information of a terminal or a combination of the above may be used for example.

In the case of implementing single sign on between the service providing system and a service provider such as the external service an administrator has to establish a trust relationship between the service providing system and the service provider beforehand. For example to implement single sign on the administrator may perform a single sign on setting operation on the service providing system and perform a single sign on setting operation on the external service .

First to perform the single sign on setting operation on the service providing system an ID of the service provider such as the external service has to be entered. is an image of an exemplary screen for entering an ID of a service provider. For example the administrator may enter a domain name registered with the external service into the screen illustrated in as the ID e.g. domain name URL of the service provider that is to use single sign on. The domain name of the external service entered into the screen of assumes a function similar to that of the organization ID of the service providing system at the external service side.

The portal service application displays a screen as illustrated in for example to indicate information to be set up at the service provider. is an image of an exemplary screen displaying information to be set up at the service provider. Information to be set up at the service provider may include a login URL sign in page URL a logout URL sign out page URL a password change URL and a public key certificate for signature validation verification certificate for example.

Note that the login URL sign in page URL in corresponds to a redirect URL for deploying SAML federation as described below. The administrator displays an administrator page of the external service and performs a single sign on setting operation on the external service . The administrator refers to the information to be set up at the service provider displayed in the screen of and enters the information in the administrator page of the external service to set up the external service for single sign on.

By performing single sign on setup of the external service at the administrator page of the external service as described above the administrator may establish a trust relationship between the service providing system and the external service .

By performing single sign on setting operations on the service providing system and the external service as described above the portal service application may add the external service to the trust circle as a service provider belonging to the trust circle.

When the URL of the external service is entered or a bookmark for the external service is selected at a browser installed in one of the office devices illustrated in the browser may access the external service through a screen transition as illustrated in for example. Note that illustrates a case where the browser is accessing the service provider that has already been set up for single sign on.

By successfully logging in via the login screen of the portal service application the browser of the office device of may be redirected to a page of the external service .

In another example when the URL of the portal service application is entered or a bookmark for the portal service application is selected at the browser installed in the office device of the browser may access the external service via a screen transition as illustrated in . Note that illustrates a case where the browser is accessing the service provider that has already been set up for single sign on.

By successfully logging in via the login screen of the portal service application the browser of the office device of may display an app launcher screen . In turn a user may click an icon for the external service displayed at the app launcher screen for example.

Because the user has already successfully logged in via the login screen the browser installed in the office device of is not redirected to the login screen and is redirected to a page of the external service .

As can be appreciated from the above a screen transition upon accessing the external service may vary depending on whether the user has already logged into the portal service application . In the following process steps of the information processing system for prompting the screen transitions as illustrated in are described.

In step S when a user enters the URL of the external service or selects a bookmark for the external service as an access destination at the browser installed in the office device of the browser accesses the external service .

In steps S and S the browser is redirected to the URL that is set up as the login URL sign in page URL by the single sign on setting. Upon being redirected to the login URL the browser sends a SAML federation request to the authentication authorization unit . The SAML federation request includes a SAML request and a RelayState. RelayState is a component of the SAML standard specification and refers to state information of the external service corresponding to the destination of a SAML response. After executing the process of step S the authentication authorization unit may execute process steps as illustrated in for example.

Note that the URL of the login screen of the portal service application to which the browser is redirected in step S may be stored at the authentication authorization unit for example. In the following an exemplary case where the browser is redirected to the login screen of the portal service application is described.

In steps S and S of the browser is redirected to the login screen of the portal service application and in turn the browser sends a request for the login screen to the portal service application . Note that the login screen request includes an organization ID a SAML request and a RelayState.

In step S the portal service application sends a login screen having the SAML request and the RelayState embedded as hidden type input tags in an HTML form. In this way the browser may display the login screen as illustrated in for example.

The user may then enter an organization ID a user name and a password into the login screen and press a login button . Note that in a case where the organization ID included in the login screen request is to be used the user may not have to enter the organization ID into the login screen . When the login button is pressed the browser proceeds to step S where it sends a login request to the portal service application . Note that the login request includes an organization ID a user name a password a SAML request and a RelayState.

In step S the portal service application sends a login request including the organization ID the user name and the password included in the login request from the browser to the authentication authorization unit . The authentication authorization unit determines whether the combination of the organization ID the user name and the password included in the login request from the portal service application is stored as user information in the user information storage unit as illustrated in .

If the combination of the organization ID the user name and the password is included in the user information storage unit in step S the authentication authorization unit returns an authentication ticket to the portal service application . After receiving the authentication ticket in step S the portal service application may execute process steps as illustrated in for example.

In the following an exemplary case where the browser is redirected to the sign in page URL SAML federation URL is described. In steps S and S of the browser is redirected to the SAML federation URL and in turn the browser sends a SAML federation request to the authentication authorization unit . Note that the SAML federation request of step S includes a SAML request a RelayState and an authentication ticket.

After the process of step S is executed the authentication authorization unit executes the process steps illustrated in as described above. Because an authentication ticket is included in the SAML federation request of step S the authentication authorization unit generates an SAML response in step S. Note that in step S the authentication authorization unit generates a SAML response to a SAML request from the external service that belongs to the same trust circle associated with the same organization.

In the following an exemplary case in which an SAML response is generated at the authentication authorization unit is described. In step S of the authentication authorization unit generates the SAML response. In steps S and S the authentication authorization unit designates a POST destination of the external service to which the SAML response is to be posted and prompts the browser to automatically POST the SAML response. In step S the external service checks the SAML response and prompts the browser to display a service screen for the corresponding user.

By implementing the process steps as illustrated in a SAML response may be generated with respect to a SAML request from the external service belonging to the same trust circle associated with the same organization. That is in the information processing system according to the first embodiment a trust circle may be set up with respect to each organization and in this way SAML based single sign on accommodating a plurality of organizations may be implemented. As a result flexibility may be enhanced in establishing a trust relationship for authentication in the information processing system according to the first embodiment.

Also by implementing the process steps as illustrated in when login via the login screen of the portal service application has not yet been performed the browser may be prompted to display the login screen in response to a SAML federation request.

Also by implementing the process steps as illustrated in a determination may be made as to whether a login request from the browser corresponds to a SAML request or a normal login request and a SAML response may be returned in the case where the login request corresponds to a SAML request.

In step S when a user enters the URL of the portal service application or selects a bookmark for the portal service application as the access destination at the browser installed in the office device of the browser accesses the portal service application .

In step S the portal service application sends a login screen to the browser . In turn the browser displays the login screen as illustrated in . Note that the URL of the login screen illustrated in is different from the URL of the login screen illustrated in .

The user enters an organization ID a user name and a password into the login screen and presses a login button . Note that in a case where a pre designated organization ID is to be used the user may not have to enter the organization ID in the login screen . When the login button is pressed the browser proceeds to step S and sends a login request to the portal service application . The login request sent in step S includes an organization ID a user name and a password.

In step S the portal service application sends a login request including the organization ID the user name and the password included in the login request from the browser to the authentication authorization unit . The authentication authorization unit determines whether the combination of the organization ID the user name and the password included in the login request from the portal service application is stored as user information in the user information storage unit as illustrated in .

If the combination of the organization ID the user name and the password included in the login request from the portal service application is stored in the user information storage unit the process proceeds to step S where the authentication authorization unit returns an authentication ticket to the portal service application .

After the process of step S the portal service application may execute the process steps as illustrated in for example. Because a SAML request is not included in the login request received in step S of the portal service application generates a portal screen in step S of .

In step S of the portal service application sends the portal screen to the browser . In turn the browser displays the portal screen including the app launcher as illustrated in .

The user may for example click the icon for the external service from the app launcher of the portal screen. In step S the browser accesses the external service .

In steps S and S the browser is redirected to the URL set up as the login URL sign in page URL by the single sign on setting and in turn the browser sends a SAML federation request to the authentication authorization unit . Note that the SAML federation request sent in step S includes a SAML request a RelayState and an authentication ticket.

After the process of step S the authentication authorization unit may execute the process steps as illustrated in for example. Because an authentication ticket is included in the SAML federation request received in step S the authentication authorization unit generates a SAML response in step S. Note that the authentication authorization unit generates a SAML response to a SAML request from the external service that belongs to the same trust circle associated with the same organization.

In steps S and S the authentication authorization unit designates a POST destination of the external service to which the SAML response generated in step S is to be posted and prompts the browser to automatically POST the SAML response. In step S the external service checks the SAML response and prompts the browser to display a service screen for the corresponding user.

By implementing the process steps as illustrated in when login via the login screen of the portal service application has already been performed a SAML response may be returned to the browser in response to a SAML federation request without having the browser display a login screen.

Also by implementing the process steps as illustrated in a determination may be made as to whether a login request from the browser corresponds to a SAML request or a normal login request and in the case where the login request corresponds to a normal login request a portal screen may be returned.

In step S the browser is redirected to the SAML federation URL and in turn the browser sends a SAML federation request to the authentication authorization unit . Note that the SAML federation request sent in step S includes a SAML request a RelayState and an authentication ticket.

In step S it is assumed that an error occurs when the authentication authorization unit generates a SAML response. For example an error may occur when a SAML request that cannot be processed is received.

In steps S and S the browser is redirected to an error screen of the portal service application and in turn the browser sends an error screen request to the portal service application . The error screen request includes error information.

In step S the portal service application sends an error screen to the browser . In turn the browser displays the error screen. The error screen may be a dedicated screen for displaying the error information or a login screen including the error information as illustrated in for example.

The external service set up for single sign on may be configured to separately provide a URL for accessing the external service through normal login operations non single sign on and a URL for accessing the external service through single sign on where the URL varies with respect to each organization ID . The app launcher screen of the external service that is configured to provide a URL for accessing the external service through non single sign on and a URL for accessing the external service through single sign on may be generated in the following manner for example.

In the app launcher screen illustrated in a link for accessing the external service is represented by the icon . When generating the app launcher screen including such a link for accessing the external service the portal service application checks whether the external service is set up for single sign on and switches the URL of the link accordingly for example.

Then referring to the organization information as illustrated in the portal service application checks whether there is a trust circle including the external service as a link. If such a trust circle exists the portal service application uses the service provider URL included in the service provider information of the organization information as illustrated in . If such a trust circle does not exist the portal service application uses a URL fixed URL for accessing the external service without using single sign on.

As described above when the service providing system is set up for single sign on the portal service application may switch a link included in the app launcher screen of the portal screen to a link to the URL of the external service that belongs to the same trust circle.

When generating the app launcher screen as illustrated in a substantial amount of time may be required to search through the complicated data structure of the organization information stored in the organization information storage unit and acquire the service provider URL. In this respect the service providing system of the first embodiment may reduce the amount of time required for displaying a page URL page by caching the service provider URL of the external service in a high speed storage device. Examples of a high speed storage device include Key Value store and Memcached.

In step S the organization managing unit acquires service provider information from the organization information database stored in the organization information storage unit . In step S the organization managing unit updates service provider information cached in the high speed storage device.

In step S the organization managing unit determines whether a service provider ID entered by an administrator user is equal to a service provider ID currently set up for single sign on. If the service provider IDs are equal the organization managing unit ends the process of . On the other hand when the service provider IDs are not equal the organization managing unit deletes the trust circle associated with the organization in step S. Then in step S the organization managing unit determines whether an input value is empty.

If the input value is empty the organization managing unit ends the process of . If the input value is not empty the organization managing unit generates trust circle information of the organization information illustrated in in step S. Then in step S the organization managing unit updates the service provider information cached in the high speed storage device.

By implementing the process steps as illustrated in service provider information may be cached in a high speed storage device and the amount of time required for displaying a page URL page may be reduced. Also in the case where the service provider information is already set up for single sign on the setting process may be omitted.

In some cases the external service may provide an API that may be used based on authentication by SAML federation. In such a case when executing a job a SAML request SAML response may be generated and the SAML response may be posted to the ACS URL of the service provider included in the organization information of . In this way login access to the external service may be obtained and the result may be used to execute the API.

In step S the image forming apparatus logs into the authentication authorization unit of the service providing system . The image forming apparatus logs in using an organization ID a user ID and a password. If login is successful the authentication authorization unit returns an authentication ticket to the image forming apparatus in step S.

In step S when the user requests the image forming apparatus to execute a job of registering a scanned image file in the external service the image forming apparatus scans an image. In step S the image forming apparatus attaches the authentication ticket to the scanned image file and uploads the scanned image file to the scan service application .

In step S the scan service application attaches the authentication ticket to a login request for accessing the external service and sends the login request to the authentication authorization unit . Note that the service provider name of the external service may be used to designate the external service as the login destination in the login request.

In step S the authentication authorization unit returns a SP authentication ticket of the external service to the scan service application . Then in step S the scan service application attaches the SP authentication ticket of the external service to the file and registers the file in the external service . In step S the external service returns a file registration result to the scan service application . In step S the image forming apparatus receives the file registration result from the scan service application .

In the service providing system according to the first embodiment a trust circle may be set up with respect to each organization and in this way SAML based single sign on accommodating a plurality of organizations may be implemented. Accordingly flexibility may be enhanced in setting a trust relationship for authentication in the information processing system according to the first embodiment.

Further the present invention is not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention.

Note that the portal service application described above corresponds to an exemplary embodiment of a receiving unit. The authentication authorization unit corresponds to an exemplary embodiment of an authentication unit. The office device having the browser installed therein corresponds to an exemplary embodiment of an external device. The user information storage unit corresponds to an exemplary embodiment of a first storage unit. The organization information storage unit corresponds to an exemplary embodiment of a second storage unit.

Further the SAML request and the SAML response described above correspond to exemplary embodiments of a federated authentication request and a federated authentication response. The authentication ticket corresponds to an exemplary embodiment of authentication information indicating that authentication has been completed. The portal screen corresponds to an exemplary embodiment of a screen including information on the external service that can be accessed. The user name corresponds to an exemplary embodiment of user identification information. The organization ID corresponds to an exemplary embodiment of organization identification information. The application corresponds to an exemplary embodiment of an internal service.

The present application is based on and claims the benefit of priority of Japanese Patent Application No. 2013 021264 filed on Feb. 6 2013 the entire contents of which are hereby incorporated herein by reference.

