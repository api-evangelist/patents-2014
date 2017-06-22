---

title: Information processing system, information processing apparatus, method of administrating license, and program
abstract: An information processing system that includes a service providing unit providing a service to an apparatus associated with a license; and a license administration unit administrating a provisionally registered license or a registered license, wherein the service providing unit includes a second memory storing a copy of license information, and an activation unit that receives a request to activate the license from the apparatus, activates the provisionally registered license or associates the registered license with the identification information of the apparatus, and requests a change of the license information stored in the second memory unit to be reflected on the license information stored in the first memory unit, wherein the activation unit adjusts a quantity of the identification information of the apparatus associated with the registered license based on the quantity of the apparatus by which a service included in the license information is made usable.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09659154&OS=09659154&RS=09659154
owner: Ricoh Company, Ltd.
number: 09659154
owner_city: Tokyo
owner_country: JP
publication_date: 20141210
---
The present invention generally relates to an information processing system an information processing apparatus a method of administrating license and a program.

For example there is known a license administration system featured to respond to a use request for using a software program with a license as a method of controlling the license in for example an information processing apparatus. This license administration system has a function of administrating an application and information of a device performing the application. This license administration system performs a license administration activating an application in a device to which an execution is permitted see for example Patent Document 1 .

In recent years there is increasing a new mode of providing a service where only a necessary function can be used when a user needs it. In a case where the service can be used by the above new mode of providing the service the user purchases for example a license from a sales company a distributor of the service.

A service distributor administrates the license issued to the user by for example a business system. The service providing system judges whether the service is provided based on the license issued by the business system. However in a case where multiple business systems are provided such that individual business systems are provided for each distributor it is not easy to administrate the license issued by each business system.

It is an object of at least one embodiment of the present invention to provide an information processing system an information processing apparatus a method of administrating a license and a program that substantially obviates one or more problems caused by the limitations and disadvantages of the related art.

One aspect of the embodiments of the present invention may be to provide an information processing system including at least one information processing apparatus the information processing system including at least one service providing unit that provides a service to at least one apparatus associated with a license and a license administration unit that administrates a provisionally registered license or a registered license wherein each of the at least one service providing unit includes a second memory unit that stores a copy of the license information of the license stored by a first memory unit and administered by the license administration unit and an activation unit that receives a request to activate the license from the apparatus activates the provisionally registered license in association with identification information of the apparatus or associates the registered license with the identification information of the apparatus by adding the identification information of the apparatus to the registered license and requests a change of the license information of the license stored in the second memory unit to be reflected on the license information of the license stored in the first memory unit wherein the activation unit adjust a quantity of the identification information of the at least one apparatus associated with the registered license based on the quantity of the at least one apparatus by which a service included in the license information is made usable.

Additional objects and advantages of the embodiments will be set forth in part in the description which follows and in part will be clear from the description or may be learned by practice of the invention. Objects and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the appended claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory only and are not restrictive of the invention as claimed.

A description is given below with reference to the through of embodiments of the present invention. Where the same reference symbols are attached to the same parts repeated description of the parts is omitted.

The network N is a private network located inside a firewall FW. The firewall FW is installed at a node between the network N and the network N. The firewall FW detects and blocks an unauthorized access. A client terminal a mobile terminal and an image forming apparatus such as a multifunction peripheral are connected to the network N.

The client terminal is an example of a terminal apparatus. The client terminal can be substantialized by an information processing apparatus in which an ordinary OS or the like is installed. The client terminal includes a wired or wireless communication means. The client terminal is a terminal which can be operated by a user such as a tablet PC or a notebook PC.

The mobile terminal is an example of the terminal apparatus. The mobile terminal includes a wired or wireless communication means. The mobile terminal such as a smartphone a portable phone a tablet PC a notebook PC or the like can be carried by the user.

The image forming apparatus is an apparatus having an image forming function such as a multifunction peripheral. The image forming apparatus includes a wireless or wired communication means. The image forming apparatus is an apparatus of performing processes related to image formation such as a multifunction peripheral a copier a scanner a printer a laser printer a projector and an electronic blackboard.

Referring to the number of the client terminal the number of the mobile terminal and the number of the image forming apparatus are one for example. However the numbers of the client terminal the mobile terminal and the image forming apparatus may be plural.

The network N is connected to the network N by an access control apparatus . Security of the network N is protected by the access control apparatus . A print service providing apparatus a scan service providing apparatus another service providing apparatus a license administration apparatus and so on are connected to the network N.

The information processing system is substantialized by the access control apparatus the print service providing apparatus the scan service providing apparatus the other service providing apparatus the license administration apparatus and so on. The print service providing apparatus the scan service providing apparatus and the other service providing apparatus provide a print service a scan service and another service. The license administration apparatus performs a process related to license administration.

The access control apparatus controls a login to the print service provided by the print service providing apparatus the scan service provided by the scan service providing apparatus or the like.

The access control apparatus the print service providing apparatus the scan service providing apparatus the other service providing apparatus and the license administration apparatus are substantialized by at least one information processing apparatus.

The access control apparatus the print service providing apparatus the scan service providing apparatus the other service providing apparatus and the license administration apparatus may be substantialized by incorporating into one information processing apparatus or by distributing to multiple information processing apparatuses.

A part of the service on the side of the network N may exist outside the network N. The mobile terminal may exist outside the network N such as the inter office network. In the information processing system illustrated in the mobile terminal exists in the network N and the network N.

The structure of the service providing system illustrated in is an example. The service providing system may be substantialized by a structure illustrated in . illustrates a structure on another exemplary service providing system. In the service providing system illustrated in the network is connected to the network N by the firewall FW.

A service providing system of a Software as a Service SaaS system a service providing system of a common service Network Service Platform system a memory apparatus of a storage Storage system and an administration apparatus of a business system are connected to the network N. Here the service providing apparatus of the common service system provides a service used by the service providing apparatus of the SaaS system in common.

The service providing apparatus of the SaaS system includes a service providing apparatus corresponding to provided services such as a portal service providing apparatus a print service providing apparatus or a scan service providing apparatus . The service providing apparatus of the common service system includes a service providing apparatus corresponding to provided common services such as an authentication service providing apparatus a data process service providing apparatus or a temporary data storage service providing apparatus .

The memory apparatus of the storage system includes a memory apparatus corresponding to stored information data such as an authentication information service memory unit a job information memory device or a temporary data memory apparatus . The administration apparatus of the business system includes an administration apparatus corresponding to administered information such as a license administration apparatus or a client information administration apparatus .

In the service providing system illustrated in security is protected by an authentication service provided by for example the firewall FW or an authentication service providing apparatus . The structure of the service providing system illustrated in is an example. The service providing system may have another structure. Various apparatuses various terminals and the networks forming the service providing system illustrated in may be structured in a virtual environment.

The client terminal and the mobile terminal are substantialized by a computer system having for example a hardware structure illustrated in . The access control apparatus the print service providing apparatus the scan service providing apparatus the other service providing apparatus and the license administration apparatus are substantialized by the computer system having for example the hardware structure illustrated in .

The service providing apparatus of the SaaS system the service providing apparatus of the common service system the memory apparatus of the storage system and the administration apparatus of the business system which are illustrated in may be substantialized by a computer system having for example the hardware structure illustrated in .

The input device includes a keyboard a mouse a touch panel and or the like by which the user inputs various operation signals. The display device includes a display or the like to display a processing result obtained by the computer system .

The communication I F is an interface provided to connect the computer system to the networks N to N. Thus the computer system can perform data communications with another apparatus and or another terminal through the communication I F .

The HDD is a non volatile memory device storing programs and or data. The program and or data to be stored is for example an operating system OS which is basic software controlling the entire computer system application software providing various functions in the OS and so on.

Further the HDD administrates the stored program and the stored data using a predetermined file system and or a predetermined data base DB . The external I F is an interface with the external apparatus. The external apparatus is a recording medium or the like. With this the computer system can read information from the recording medium and or write information to the recording medium through the external I F .

The recording medium includes for example a flexible disk a compact disk CD and a digital versatile disk DVD . The recording medium may be an SD memory card a universal serial bus USB memory or the like.

The read only memory ROM is a non volatile semiconductor memory a memory device which can hold a program and or data even when a power source is powered off. The ROM stores programs and data used for a basic input output system BIOS OS setup network setup or the like which are executed at a time of booting up the computer system .

The random access memory RAM is a volatile semiconductor memory a memory device temporarily storing a program and or data. The central processing unit CPU reads the program and or data out to the RAM from the memory device such as the ROM the HDD or the like. The read program or data perform the process to thereby entirely substantialize controls or functions of the computer system .

With such a hardware structure of the computer system the client terminal and the mobile terminal can substantialize various processes described later. The access control apparatus the print service providing apparatus the scan service providing apparatus the other service providing apparatus and the license administration apparatus can perform various processes described later by the hardware structure of the computer system . The service providing apparatus of the SaaS system the service providing apparatus of the common service system the memory apparatus of the storage system and the administration apparatus of the business system which are illustrated in can perform various processes described later by the hardware structure of the computer system . A description of the hardware structures of the image forming apparatus and the firewall FW which are illustrated in is omitted.

The service providing system of the first embodiment is substantialized by for example a processing block illustrated in . is a processing block chart of an exemplary service providing system of the first embodiment. The service providing system substantializes the processing block illustrated in by executing the program.

The service providing system illustrated in substantializes an application a common service a database DB a platform API and a business service .

The application includes for example a portal service application a scan service application and a print service application .

The portal service application is an application providing a portal service. The portal service provides a service as an entrance for using the service providing system . The scan service application is an application for providing the scan service. The print service application is an application providing the print service. The application may include another service application.

The platform Application Programming Interface API platform is an interface used by the application such as the portal service application when the application uses the common service . The platform API is an interface previously defined so that the common service receives a request from the application . The platform API is structured by for example a function a class or the like.

The platform API can be substantialized by for example Web API which can be used through the network when the service providing system is structured by multiple information processing apparatuses.

The common service includes an authentication and permission unit an organization administration unit a user administration unit a license administration unit for providing service an apparatus administration unit a temporary image storing unit an image processing workflow controlling unit and a log collection unit .

The image processing workflow controlling unit includes a message queue and at least one worker Worker . The worker substantializes a function such as an image conversion or an image transmission.

The authentication and permission unit performs authentication and or permission based on a login request received from office equipment such as the client terminal the image forming apparatus or the like. The office equipment is a general term of the client terminal the mobile terminal the image forming apparatus and so on.

The authentication and permission unit accesses for example a user information memory unit a license information memory unit or the like which are described below and authenticates and or permits the user. Further the authentication and permission unit accesses for example an organization information memory unit the license information memory unit the apparatus information memory unit or the like which are described below to authenticate the image forming apparatus .

The organization administration unit administrates organization information stored in the organization information memory unit . The user administration unit administers the user information stored in a user information memory unit described below.

The license administration unit for providing service administrates the license information stored in the license information memory unit described below. The apparatus administration unit administers apparatus information stored in the apparatus information memory unit described later. The temporary image storing unit stores a temporary image in a temporary image memory unit described later and acquires the temporary image from the temporary image memory unit .

The image processing workflow controlling unit controls a workflow related to image processing based on a request from the application . The message queue includes queues corresponding to types of the processes. The image processing workflow controlling unit inputs a message of a request related to a process a job into the queue corresponding to the type of the job.

The worker monitors the corresponding queue. When the message is input in the queue the worker performs a process such as an image conversion or an image transmission corresponding to the type of the job. The message input in the queue may be mainly read out Pull by the worker or may be provided Push from the queue to the worker .

The database includes a log information memory unit an organization information memory unit a user information memory unit a license information memory unit an apparatus information memory unit a temporary image memory unit a job information memory apparatus and a setup information memory unit inherent in the application .

The log information memory unit stores log information. The organization information memory unit stores organization information described below. The user information memory unit stores user information described below. The license information memory unit stores license information described below. The apparatus information memory unit stores apparatus information described below.

The temporary image memory unit stores the temporary image. The temporary image is a file or data such as a scanned image processed by for example the worker . The job information memory apparatus stores information job information of a request related to the process the job . The setup information memory unit inherent in the application stores setup information inherent in the application .

The business service includes the customer information administration unit the contract administration unit the sales administration unit and the business license administration unit . The customer information administration unit administers client information. The contract administration unit administers contract information. The sales administration unit administers sales information. The business license administration unit administers the license information. The business license administration unit includes a license DB storing the license information.

The service providing system functions as an integrated platform for providing a common service such as authentication and permission or a workflow related to image processing and a service group for providing an application service such as the scan service the print service or a portal service.

The integrated platform includes for example the common service the database the platform API and the business service . Further the service group is formed by for example the application . As described in the service providing system illustrated in the application and the business service are separated.

In the service providing system by adopting the structure where the service group and the integrated platform are separated it is possible to easily develop the application using the platform API .

A mode of classifying the processing blocks of the service providing system illustrated in is an example. It is unnecessary that the application the common service the database and the business service are classified in a hierarchy illustrated in . As long as the processes of the service providing system of the first embodiment are processed a relationship of the hierarchy illustrated in or the like is not specifically limited.

Meanwhile the processing blocks of the service providing system illustrated in may be processing blocks illustrated in . is a processing block chart of another exemplary service providing system of the first embodiment. Because the service providing system illustrated in is similar to the service providing system illustrated in except for a part explanation is appropriately omitted for the same parts.

The service providing system substantializes a domain inherent service and a domain inherent API in addition to the processing blocks illustrated in by performing the program. The service providing system illustrated in differs from the service providing system at the application the domain inherent service and the domain inherent API . The application illustrated in includes the portal service application an UI unit of the scan service application and an UI unit of the print service application as an example. The domain inherent service includes a logic unit of the scan service application and a logic unit of the print service application as an example.

The logic unit of the scan service application and the logic unit of the print service application are logics inherent in the domain and are accessed by the client such as the mobile terminal or the image forming apparatus other than the Web browser. For the client other than the Web browser the UI unit such as the UI unit of the scan service application is arranged on the client side. Therefore it is sufficient for the server side to be able to provide the domain inherent API .

As such in the service providing system illustrated in the access from the web browser is received by a UI unit such as the UI unit of the scan service application. Further the access from the client other than the web browser is received by a logic unit such as the logic unit of the scan service application. Because the frequency of accessing from the web browser is different from the frequency of accessing from the client other than the web browser the client and the web browser are arranged as separate servers to effectively perform a scale out along with an increment of the frequencies. In the service providing system illustrated in it is possible to construct a composite application by additionally using the domain inherent API .

As described the service providing systems illustrated in include the license information stored in the license information memory unit and the license information stored in the license DB of the business license administration unit .

Referring to the business license administration unit corresponds to a license administration server . Further the application the common service the database DB and the platform API are represented by the service providing apparatus . The license administration server is located in for example a data center close to a center of operating the business e.g. a head office so as to be uniformly managed.

Further the service providing apparatus and the license DB are located in a data center close to the user in order to improve a response performance. The data center in which the service providing apparatus and the license DB are located may be located in multiple locations. The data center is connected to the data center by for example a private line or a VPN to thereby limit the server using a firewall.

The business terminal corresponds to the client terminal or the like operated by a business controller. The user terminal is a client terminal or the like operated by a user such as the administrator. A multifunction peripheral MFP is an example of the image forming apparatus .

In a case where the locations of the data centers are multiple the business system and the common service system are structured as illustrated in . explains the license information in the license administration apparatus of the business system and the service providing apparatus of the common service system. Referring to the data centers and are located at two locations.

For example the data centers and are located in association with regions sales regions where the sales are done. Borders of the sales regions are variously determined in consideration of business modes such as North America Europe or Japan.

The license administration server issues the license information and reports the issuance of the license information while distributing the license information and the reports into the data centers and corresponding to the designated sales regions when it is received to issue the license information in which the sales region is designated. The license information issued by the license administration server is uniquely selected regardless of the sales regions.

The business application is an application used by the business controller. The business API is provided to perform for example an issuance of the license a cancellation of the license a change of the license or the like which can be used from the business application . The license administration server includes the business API . The service providing application is an application used by the user such as the administrator. The platform API is provided to perform for example a reference of the license a search of the license a change of the license or the like which can be used from the service providing application . The service providing apparatus includes the platform API .

In a case where the locations of the data centers are multiple the business system and the service providing system are structured as illustrated in . explains an API used by the license administration apparatus of the business system and the service providing apparatus of the common service system. Referring to the data centers and are located at two locations.

The organization name represents the name of the group such as the company or the department. The display language represents a language used for displaying the group name such as the company and the department. Further the display language represents a display for an access from the browser and a language used for a body text of a mail. The time zone represents a standard time used by the group such as the company the department or the like. The state represents a state of the group such as the company or the department. The country represents a name of a country to which the company the department or the like belong.

The user ID and the password are information user specifying information for specifying the user. The user ID may be the user name or the like. The password is not indispensable. Although the user ID administered by the same organization ID is uniquely determined the same user ID may be used in different organization IDs.

Further identification information of an electronic medium for example an IC card owned by the user may be used as the user ID. The electronic medium owned by the user is an IC card a portable phone a tablet terminal an electronic book reader or the like. Information identifying the electronic medium is a card ID a serial ID a telephone number of the portable phone profile information of a terminal or the like. It is possible to combine the information identifying the electronic medium in using the information identifying the electronic medium.

The user name represents the name of the user. The display language represents a language for displaying the user name. Further the display language represents the display for the access from the browser and the language used for the body text of the mail. The time zone represents a standard time used by the user. The state represents the state of the user.

The service type is information for specifying the type of the service such as the portal service the scan service the print service or the like. The license ID is identification information for identifying the license. The license ID becomes the organization ID in a case where the license is the organization license and the service ID in a case where the license is the service license. The sales region is information indicative of a region where the license is sold or the like. The country represents the name of the country where the license is used. The time zone represents the standard time of the country where the license is used. The commodity code is identification information for identifying a commodity corresponding to the license. The quantity the number of apparatuses is information indicative of the quantity of the apparatuses where the service can be used by the license.

The use start date is information indicative of a date when the license becomes active. The billing start date is information indicative of a date when billing is started and the same date as the use start date or later for example the first day of the next month . The use end date is information indicative of a license deadline on display. The use end date is for example one year after the billing start date. The scheduled cancellation date is information indicative of a date when the license is inactivated. The state is information indicative of a state of the license. The state of the license includes for example a provisional registration indicating that the license before use a registration indicating that the license is now being used and a cancellation indicating that the license is after use.

In a case of the service license the organization is set to the parent service type. In a case of the service license the organization ID is set to the parent license ID. In a case of the organization license the registration code is set. The registration code is input at a time of opening the organization.

The machine type and machine number is set in a case of the service license. The machine type and machine number is information specifying the apparatus as an object of the license. In case of a volume license where the multiple apparatuses to be licensed exist the machine type and machine number of the apparatus activated the earliest is set.

The next license type is set in a case of the renewed service license. The next license type has the same value as the service type. The next license ID is set in a case of the renewed service license. The next license ID is the service ID of the renewed service license.

The license type is information for specifying the type of the service license such as the apparatus license or the user license. The license type is information for setting the apparatus the user or the like which are an object of limiting the use by the service license. The license mode is information indicative of whether the use is permitted with the own service license in combination with the service license of another type or the use is permitted with only the own service license.

For example the information such as only the apparatus license or apparatus license user license is set to the license mode. In a case where the license mode is only the apparatus license the use of the service is permitted when the service license whose license type is the apparatus license is registered. In a case where the license mode is the apparatus license the user license the use of the service is permitted when the service license whose license type is the apparatus license and the service license whose license type is the user license are registered.

The quantity the number of users is information indicative of the number of the users who can use the service by the license. The number of apparatuses in use is information indicative of the number of the apparatuses where the service can be used by the license. The number of users in use is information indicative of the number of the users who can use the service by the license. In the license information illustrated in the quantity the number of apparatuses and the quantity the number of users are separately provided as the data items. However the quantity the number of apparatuses and the quantity the number of users may be treated as the same data item.

Referring to the license information of the organization license and the service license are in a relationship between parent and child. In the license information illustrated in the organization license corresponds to the parent license and the service license corresponds to the child license not illustrated . The organization license as the parent license is set to the parent license ID. In the license information illustrated in although the parent in the relationship between parent and child is illustrated for the organization license and the service license there may be a relationship among three hierarchies or more such as parent child and grandchild.

The organization license is necessary to use the service providing system . Without the organization license the organization cannot be opened in the service providing system . By handling the organization license in the same data format as that of the service license it becomes possible to bill the organization itself or provide a difference in a service level a speed or a capacity depending on the amount of the bill.

The service providing system provides a service to multiple organizations and provides a user administration independent for each organization. The service providing system performs an access limitation by preventing the data from being referred between the organizations. Therefore it is necessary to open the organization before using all the services in the service providing system. Because the relationship between parent and child of the licenses has a very flexible data structure it is possible to express the grouping of the licenses in the volume license or the like.

In a case of the volume license the activated apparatus is administered by activated apparatus view information as illustrated in . is a structural view of exemplary activated apparatus view information.

Referring to the activated apparatus view information includes the service ID the device the organization ID or the machine type and machine number an activated date and so on as the data item. The service ID is identification information for identifying the service license.

The device the organization ID or the machine type and machine number is information of the machine type and machine number of the apparatus activated using the service ID and information of the organization ID. The device the organization ID or the machine type and machine number can hold multiple information of the machine type and machine number of the apparatus activated using the service ID and multiple information of the organization ID. The activated date is the earliest date among dates when the activated apparatus is activated.

The use start date Aug. 10 2012 is a date when the license becomes active. The billing start date is the first day Sep. 1 2012 of a next month of the use start date. The contract end date is one year Aug. 31 2013 after the billing start date. The scheduled cancellation date is the end day Sep. 30 2013 of the next month of the contract end date which is obtained by adding days as many as a month to the contract end date. The contract end date is the end date of the license presented to the user. The scheduled cancellation date is the end date of the license when the license actually becomes inactive.

After renewing the contract the scheduled cancellation date Sep. 30 2013 of the previous license is moved to the contract end date Aug. 31 2013 of the previous license. The use start date and the billing start date of the next license is the next day Sep. 1 2013 of the contract end date of the previous license. The contract end date of the next license is one year Aug. 31 2014 after the billing start date. The scheduled cancellation date of the next license is the end day Sep. 30 2014 of the next month of the contract end date which is obtained by adding days as many as a month to the contract end date.

Before renewing the contract the displayed period which is displayed on for example an UI and is between the use start date and the use end date is shorter than the license active period while the license is active. This is because the use end date corresponds to the contract end date illustrated in and the contract end date is earlier than the scheduled cancellation date by the margin equal to one month added to the scheduled cancellation date.

After renewing the contract the license active period of the previous license becomes equal to the displayed period which is displayed on for example the UI and is between the use start date and the use end date. This is because the scheduled cancellation date of the previous license is moved to the contract end date of the previous license.

The use start date and the billing start date of the next license is the next day Nov. 1 2013 of the contract end date of the previous license. In a manner similar to the previous license the displayed period which is displayed on for example the UI and is between the use start date and the use end date of the next license is shorter than the license active period while the license is active.

Referring to the scheduled cancellation date is set by adding the margin to the contract end date. With this it is possible to prevent the application from being unusable on or after the contract end date in the service providing system . Since the scheduled cancellation date is not presented to the user the scheduled cancellation date may be changed after renewing the contract. The use start date and the use end date which are displayed on the UI are displayed using a local date based on a time zone setup of the organization.

In a sequence chart described below an actor an icon in a human form represents a client application a browser operated in each terminal operated by a user such as a business controller.

The organization ID issuance screen illustrated in includes a column designating a sales region where the business controller sells the license. In the organization ID issuance screen illustrated in Asia is designated as the sales region.

The business controller operates a business terminal in step S designates the sales region for the business application and requests to issue the organization ID. The business application issues the organization ID and the registration code. The business application provisionally registers the sales region the organization ID and the registration code in the business license administration unit in step S. In step S the business license administration unit reports the registration code for the provisionally registered organization ID to the license administration unit for providing the service corresponding to the sales region. The license administration unit for providing the service corresponding to the sales region causes the reported organization ID and the reported registration code to be stored in the license information memory unit .

After the processes illustrated in the administrator purchases an organization license which is a license for using the service providing system from for example the distributer and obtains the organization ID and the registration code from the distributer.

In step S the administrator operates the user terminal and sets the country to the organization opening screen. The country which can be set to the organization opening screen may be limited to for example a country associated to the sales region. In step S the portal service application displays terms of use for the country set by the administrator as illustrated in . is an image chart of an exemplary terms of use screen. is an example where Japan is set as the country in the organization opening screen.

The administrator checks the terms of use and thereafter operates the user terminal to cause a URL issuance screen as illustrated in to be displayed. is an exemplary image chart of a URL issuance screen. The administrator operates the user terminal and sets the organization ID acquired from the distributor the registration code the mail address and a language of a return mail.

After the administrator sets the URL issuance screen the administrator operates the user terminal to cause an input content check screen to be displayed. After the administrator checks the input content in the URL issuance screen the administrator pushes a send button of the input content check screen. When the send button is pushed by the administrator the portal service application receives the input content input by the administrator in step S.

The portal service application requests to change the license information of the organization license to the license administration unit for providing the service in step S. The organization ID the registration code the country and the mail address are included in the request of step S.

In step S the license administration unit for providing the service checks whether the organization ID and registration code which are included in the request of step S is stored in the license information memory unit . In step S it is checked whether the registration code input by the administrator is correct.

When the organization ID and the registration code which are included in the request of step S are stored in the license information memory unit the license administration unit for providing the service reports the changed license information to the business license administration unit in step S. The country and the mail address are added to license information reported in step S. The business license administration unit changes the content of the license DB based on the license information reported in step S. The success or the failure in changing the license information is reported to the portal service application through the license administration unit for providing the service from the business license administration unit .

Meanwhile the portal service application causes a URL report screen to be displayed on the user terminal when the send button is pushed. In the URL report screen a message of sending a mail to a mail address set in the URL issuance screen illustrated in and a message of continuing the open of the organization by accessing the URL described in the mail are included.

In step S the portal service application sends the mail describing the URL for opening the organization to the mail address set in the URL issuance screen illustrated in . When the mail address is set in the URL issuance screen illustrated in the administrator cannot receive the mail. Therefore it is possible to prevent the mail address from being erroneously set.

In a case where the organization cannot be continuously opened the portal service application sends a mail including a message indicative of the failure in opening the organization to the mail address set in the URL issuance screen illustrated in . An error case in opening the organization occurs in a case where the organization ID and the registration code which are included in the request in step S are not stored in the license information memory unit or are already used to open the organization for example. The mail including the message indicative of the failure in opening the organization does not has a content enabling a malicious user to give a hint of distinguishing the error case. Therefore the mails have the same content.

In step S the administrator operates the user terminal and requests the portal service application to display a page of the URL for opening the organization described in the mail. The user terminal displays the organization information input screen illustrated in . is an exemplary image chart of the organization information input screen.

The administrator operates the user terminal and sets the registration code acquired from the distributor the organization information and the administrator information the user information . After the administrator sets the organization information input screen the administrator operates the user terminal to cause the input content check screen to be displayed. After the administrator checks the input content into the organization information input screen the administrator pushes a registration button of the input content check screen.

When the send button is pushed by the administrator the portal service application receives the input content input by the administrator in step S. The portal service application requests to perform a formal registration of the license information of the organization license to the license administration unit for providing the service in step S. The organization ID the time zone and so on are included in the request of step S.

The license administration unit for providing the service reports the changed license information to the business license administration unit is step S. The time zone and the use start date are included in the license information reported in step S. The business license administration unit changes the content of the license DB based on the license information reported in step S. The success or the failure in performing the formal registration of the license information is reported to the portal service application through the license administration unit for providing the service from the business license administration unit .

In step S the portal service application requests the organization administration unit to cause the organization information to be stored in the organization information memory unit and makes a portal site of the organization to thereby open the organization.

Further in step S the portal service application requests the user administration unit to cause the user information of the administrator to be stored in the user information memory unit . In step S the portal service application sends a mail describing that the open of the organization is completed to the mail address set in the URL issuance screen illustrated in .

Further the portal service application causes the user terminal to display a screen reporting the result of the open. The screen reporting the result of the open includes a message indicating that the mail reporting the result of the open to the mail address set in the URL issuance screen illustrated in .

In step S the business controller operates the business terminal selects the sales region and the commodity code and requests the business application to issue the service ID. The business application designates the sales region and the commodity code in step S and provisionally registers the license in the business license administration unit . In step S the business license administration unit selects the service ID. The business license administration unit causes the license DB to store the selected service ID . Further in step S the business license administration unit searches a commodity master using a commodity code and causes the license DB to store the service type the sales region the commodity code and the quantity. For example different commodity codes may be attached depending on combinations of the service type and the quantity. With this by using the commodity codes the business controller can request to issue the service ID designating the number of apparatuses enabled to use the service or the number of users enabled to use the service.

In step S the business license administration unit reports the license information including the selected service ID to the license administration unit for providing the service corresponding to the sales region. The license administration unit for providing the service corresponding to the sales region causes the reported service ID to be stored in the license information memory unit .

After the processes illustrated in the administrator purchases the service license being a license for using the service such as the scan service application or the like from for example the distributor and acquires the service ID from the distributor.

In step S the administrator inputs the service ID from the service registration screen. Hereinafter described is an example where the administrator performs the service registration.

The administrator operated the MFP to set the service ID acquired from the distributer in the service registration screen illustrated in . In step S the scan service application requests the license administration unit for providing the service corresponding to the sales region to perform the formal registration of the license information of the service license. For example the service ID the organization ID the machine type and machine number of the MFP and so on are included in the request in step S.

In step S the license administration unit for providing the service specifies the license information stored in the license information memory unit based on the service ID included in the request of step S. The license administration unit for providing the service sets the organization ID and the machine type and machine number of the MFP to the specified license information.

In step S the service ID to be registered the organization ID of the organization to which the administrator belongs and the machine type and machine number of the MFP are associated and stored. The license administration unit for providing the service sets the current date as the above use start date to the specified license information.

In step S the license administration unit for providing the service requests the business license administration unit to perform the formal registration of the license information of the service license in step S. In step S the business license administration unit calculates the scheduled cancellation date the billing start date and the use end date based on the use start date.

In step S the business license administration unit returns the scheduled cancellation date the billing start date and the use end date which were calculated to the license administration unit for providing the service. The license administration unit for providing the service stores the scheduled cancellation date the billing start date and the use end date to the license DB .

In step S the success and failure of the registration of the service ID are reported from the license administration unit for providing the service to the scan service application . In a case where the registration of the service ID fails the scan service application displays the failure of the registration of the service ID on the MFP . The error case where the registration of the service ID fails is that the service ID set in step S is not stored in the license information memory unit or already used for the registration of the service ID.

After registering the service ID in the first MFP in step S the administrator operates the MFP checks the terms of use displayed on the screen and causes the service registration screen to be displayed as illustrated in . In step S the administrator sets the service ID registered in the first MFP in the service registration screen and selects the service registration and pushes the next button.

When the next button is pushed by the administrator the process goes to step S. Then the scan service application requests the license administration unit for providing the service corresponding to the sales region to perform the formal registration of the license information of the service license. For example the service ID the organization ID the machine type and machine number of the MFP and so on are included in the request in step S.

If the service ID is registered in the MFP and the MFP is to register a service ID of the same service type the license administration unit for providing the service reports the error.

After the license administration unit for providing the service receives the request of step S the license administration unit for providing the service specifies the license information stored in the license information memory unit based on the service ID included in the request of step S. The license administration unit for providing the service checks whether the use start date is set to the specified license information.

Here because described is a case where the registered service ID is set to the first MFP the use start date is set to the specified license information. In a case where the use start date is set to the specified license information the license administration unit for providing the service determines that the specified license information is started to be used.

The license administration unit for providing the service checks the quantity the number of apparatuses of the specified license information and the number of apparatuses using the license and determines whether another apparatus can be registered. The number of the apparatuses using the license corresponding to the specified license information reaches the quantity the number of apparatuses of the specified license information the license administration unit for providing the service determines that the additional registration is not possible and reports it as the error. Said differently the license administration unit for providing the service adjusts the number of the apparatuses using the license so as not to exceed the quantity the number of apparatuses of the specified license information.

The number of apparatuses using the license corresponding to the specified license information does not reach the quantity the number of apparatuses of the specified license information the license administration unit for providing the service determines that the additional registration is possible. When the license administration unit for providing the service determines that the additional registration is possible the license administration unit for providing the service adds 1 to the number of apparatuses using the license. Further the license administration unit for providing the service adds the organization ID and the machine type and machine number which are included in the request of step S to the device the organization ID and the machine type and machine number of the activated apparatus view information illustrated in .

In step S the license administration unit for providing the service requests the business license administration unit to change the license information of the service license. The business license administration unit renews the license information and the activated apparatus view information based on the machine type and machine number included in the request of step S.

When the failure of the registration of the service ID is displayed in the MFP and the MFP a content enabling the error case to be distinguishable is not included to prevent a hint from being provided to the malicious user and has the same content as those of the other error cases.

Referring to the sequence chart illustrated in by inputting the service ID from the UIs of the scan service applications and operated in the MFP and the MFP it is possible to store the service ID and the machine type and machine number of the MFP while associating the service ID with the machine type and machine number of the MFP .

Further referring to the sequence chart illustrated in the same service ID can be registered in the multiple apparatuses using a volume license.

The volume license is provided so that one service ID can be registered to multiple apparatuses as described above. When the apparatus in which the service ID is registered or the use of the apparatus is completed there may be a case where the apparatus associated with the volume license is deleted.

The business controller operates the business terminal in step S and causes a service ID change screen illustrated in to be displayed. is an image chart of an exemplary service change screen. The license information specified by the service ID is displayed on the upper side of the service ID change screen illustrated in and a list view of the machine type and machine number of the apparatuses which can use the service by the activated service use with the service ID on the lower side of the service ID change screen illustrated in . The business controller sets the apparatus to be removed from the view of machine type and machine number displayed on the lower side of the service ID change screen illustrated in as a deletion target and requests the business application to delete the apparatus.

In step S the business application requests the business license administration unit to change the license information. At this time the business application reports the machine type and machine number of the deletion target to the business license administration unit .

The business license administration unit receives the request to change the license information and changes the license information and the apparatus view information activated in step S as described later. After changing the license information and the activate apparatus view information the business license administration unit reports the content of the change to the license administration unit for providing the service in step S. In step S the license administration unit for providing the service changes the license information and the activate apparatus view information which are held by the license administration unit for providing the service based on the content of change based on the reported content of the change.

The process of changing the license information and the activated apparatus view information is performed as illustrated in for example . is a flowchart of an exemplary process of changing the license information and the activated apparatus view information.

In step S the business license administration unit determines whether the activated apparatus view information specified by the service ID includes the machine type and machine number of the apparatus set as the deletion target.

If the activated apparatus view information specified by the service ID includes the machine type and machine number of the apparatus set as the deletion target the business license administration unit deletes the machine type and machine number of the apparatus set as the deletion target from the activate apparatus view information in step S. Then step S is performed.

In step S the business license administration unit determines whether a value set in the machine type and machine number of the license information is the machine type and machine number of the apparatus set as the deletion target or not. If the value set in the machine type and machine number of the license information is the machine type and machine number of the apparatus set as the deletion target the business license administration unit proceeds to step S and deletes the value set in the machine type and machine number of the license information.

In step S the business license administration unit searches the machine type and machine number of the apparatus which is activated immediately after the machine type and machine number of the apparatus set as the deletion target. In step S the business license administration unit sets the machine type and machine number searched in step S as a value of the machine type and machine number of the license information.

In step S the business license administration unit determines whether the value is set to the next license ID of the license information. If the value is set to the next license ID of the license information the business license administration unit goes to step S.

In step s the business license administration unit deletes the machine type and machine number of the apparatus set as the deletion target from the license information of the license ID set to the next license ID and the activated apparatus view information. The process of step S is similar to the process of steps S to S for for example the license information of the license ID set to the next license ID and the activated apparatus view information.

When the machine type and machine number of the apparatus set as the deletion target in step S does not exist if the value set in the machine type and machine number of the license information in step S is not the machine type and machine number set as the deletion target the flowchart illustrated in ends. In a case where the value is not set to the next license ID of the license information in step S the flowchart of ends.

Referring to the flowchart of the use of the service by all apparatuses associated with the volume license is not stopped but the use of the service of an arbitrary apparatus can be stopped. Further referring to the flowchart illustrated in the license information and the activated apparatus view information can be renewed in association with the machine type and machine number of the apparatus to be deleted.

The administrator operates the user terminal to access the portal service application . Then a service administration screen as illustrated in is received from the portal service application . is an image chart of an exemplary service administration screen after registering the service.

In the service administration screen illustrated in the service ID is registered from the MFP and one service license is displayed. Referring to the state of the service license displayed on the service administration screen is now being used not renewed .

The service license of the organization to which the administrator logging in the portal service application belongs is displayed on the service administration screen illustrated in . The service license of the organization to which the administrator belongs can be searched using a parent license ID of the license information.

Further the service license of the organization to which the administrator logging in the portal service application belongs can be searched using the machine type and machine number of the license information or the machine type and machine number of the apparatus view information associated with the license information and activated.

The machine type and machine number of the license information is displayed on the service administration screen illustrated in . Further all machine type and machine numbers of the apparatuses registered so as to have the license can be searched using the service administration screen illustrated in . Therefore it is possible to search the license associated with a specific machine type and machine number which cannot be checked using a view screen.

The state of the service license on the service administration screen illustrated in can be displayed by distinguishing now being used not renewed and now being used renewed from now being used depending on whether the next license ID is registered.

A detailed license screen illustrated in may be displayed when the administrator operates the user terminal to click or move a mouse over a service ID link on the service administration screen illustrated in . is an image chart of an exemplary detailed license screen. A machine type and machine number view of the apparatuses associated with the volume license is included in the detailed license screen illustrated in as the registered apparatus view.

The administrator operates the user terminal to click a link to license registration renewal on the service administration screen illustrated on . Thus a service registration screen as illustrated in is displayed. The administrator can start the renewal of the contracted service from the service registration screen as illustrated in .

In step S the administrator operates the user terminal to set the service ID a new service ID used to renew from the service registration screen. In step S the portal service application acquires the license information in which the license ID is set as a new service ID set in the service registration screen from the license administration unit for providing the service.

In step S the portal service application checks appropriateness of the new service ID set in step S using a result of acquiring the license information in step S. When the new service ID is not correctly input the portal service application displays a message indicating that the input is not correct. An error case where the input of the new service ID is not correct occurs when the new service ID is not stored in the license information memory unit or is already used for example. The message indicating that the input of the new service is not correct does not has a content enabling a malicious user to give a hint of distinguishing the error case. Therefore the messages have the same content.

When the new service ID set in step S is appropriate the portal service application displays a screen of the terms of use. After the administrator checks the terms of use the portal service application searches license information having the same parent ID and service type as those of the license information acquired in step S.

In step S the portal service application displays a renewable service out of the license information searched in step S. Said differently the state of the portal service application is now being used not renewed and displays a view of the service license having the number of apparatuses whose current license is now being used smaller than the number of apparatuses whose new license can be used as illustrated in . is an image chart of an exemplary service selection screen at a time of renewing the license. When the number of apparatuses which can use the current license is smaller than the number of apparatuses which can use the new license it is possible to reduce the number of apparatuses which can be used by the license by renewing the license. With this the cost for the license can be reduced.

In step S the operator operates the user terminal to select the service ID to be renewed from the service selection screen illustrated in and requests the portal service application to renew the service. The request of step S includes the service ID to be renewed the current service ID and the service ID used for the renewal the new service ID .

A check screen is displayed on the user terminal . The administrator checks the content of the check screen and pushes for example an OK button. When the OK button is pushed by the administrator the portal service application requests the license administration unit for providing the service to change the license information in step S. The request of step S includes the current service ID and the new service ID.

In step S the license administration unit for providing the service changes the scheduled cancellation date of the license information the current license whose license ID is the current service ID to be the same date as the use end date. Further the license administration unit for providing the service sets a next license ID next to the current license ID to be the new service ID.

In step S the license administration unit for providing the service sets the organization ID of the license information the new information in which the new service ID is set as the license ID the machine type and machine number and the current date as the use start date based on the current license. In step S the license administration unit for providing the service requests the business license administration unit to renew the license information of the service license in step S.

In step S the business license administration unit calculates the scheduled cancellation date the billing start date and the use end date based on the use start date. In step S the business license administration unit returns the scheduled cancellation date the billing start date and the use end date which were calculated to the license administration unit for providing the service. The license administration unit for providing the service stores the scheduled cancellation date the billing start date and the use end date to the license DB .

The end of the renewal of the contracted service can be reported from the license administration unit for providing the service to the portal service application . After the renewal of the contracted service ends the portal service application causes the user terminal to display a license renewal end screen.

After the renewal of the contracted service ends the service administration screen illustrated in is changed to the service administration screen illustrated as in . is an image chart of an exemplary service selection screen after renewing the license. On the service administration screen illustrated in the state of the current license is changed from now being used not renewed to now being used renewed . Further the service license of the new license whose state is before starting use is added to the service administration screen illustrated in .

In step S the business application requests to change the license information of the organization license. The request of step S includes the organization ID and the scheduled cancellation date. After the process of step S the business license administration unit requests the license administration unit for providing the service corresponding to the sales region of the organization ID to be canceled to change the license information in a manner similar to step S. On the scheduled cancellation date the business license administration unit starts a batch process in step S. In step S the business license administration unit changes the organization license associated with the organization ID and the state of the license information of the service license to the cancellation .

In step S the business license administration unit report the organization license to be canceled and the license information of the service license to the license administration unit for providing the service corresponding to the sales region of the organization ID. In step S the license administration unit for providing the service changes the reported organization license and the reported state of the license information of the service license to the cancellation .

In step S the license administration unit for providing the service performs a process of deleting all information associated with the organization ID such as the organization information the user information or the apparatus information. For example the license administration unit for providing the service reports the deletion of the service permission information to for example the authentication and permission unit to delete all the information associated with the organization ID in step S. The service permission information is described later.

In the sequence chart illustrated in the license administration unit for providing the service reports to the authentication and permission unit in order to delete authentication and permission information. However the license administration unit for providing the service reports to the organization administration unit the user administration unit the apparatus administration unit and so on depending on the information to be deleted.

In the process of the sequence chart illustrated in the license administration unit for providing the service can perform the cancellation of the license and the deletion of the information associated with the organization license in response to the report of the cancellation of the organization license from the business license administration unit . A portal site application setup information or the like for each organization or each user may be included in the information associated with the organization license. In the sequence chart illustrated in the state of the license information is changed to the cancellation without being deleted.

In step S the business application requests the business license administration unit to change the license information of the service license. The request of step S includes the service ID and the scheduled cancellation date. After the process of step S the business license administration unit requests the license administration unit for providing the service corresponding to the sales region of the service ID to be canceled to change the license information in a manner similar to step S. On the scheduled cancellation date the business license administration unit starts a batch process in step S. In step S the business license administration unit change the service license associated with the service ID and the state of the license information of the service license to the cancellation .

In step S the business license administration unit report the license information of the service license to be canceled to the license administration unit for providing the service corresponding to the sales region of the service ID. The license administration unit for providing the service changes the state of the reported license information of the service license to the cancellation .

On the scheduled cancellation date the business license administration unit starts a batch process in step S. In step S the business license administration unit changes the state of the license information of the service license associated with the service ID to the cancellation .

In step S the business license administration unit report the license information of the service license to be canceled to the license administration unit for providing the service corresponding to the sales region. In step S the license administration unit for providing the service changes the reported state of the license information associated with the service ID of the current license to the cancellation .

In step S the license administration unit for providing the service changes the state of the license information associated with the service ID of the new license to the formal registration . In step S the license administration unit for providing the service requests the business license administration unit to perform the formal registration of the license information of the service license in step S.

Referring to the sequence chart illustrated in the service license is switched from the current license to the new license. After the current license is switched to the new license the service administration screen is changed to a service administration screen as illustrated in .

When the user accesses the portal service application the portal service application can display a service selection screen as illustrated in on the user terminal . is an image chart of an exemplary service selection screen. The service selection screen illustrated in displays screen elements such as a tab or an icon for selecting the service corresponding to a service license when the service license whose license information is now being used indicating the activation exists in the organization to which the accessing user belongs.

In order to display the service selection screen illustrated in the service providing system stores service permission information as illustrated in . is a sequence chart of an exemplary process of storing the service permission information. Description of processes similar to the above described sequence chart is appropriately omitted.

In step S the scan service application requests the license administration unit for providing the service to perform the formal registration of the service license. In step S the scan service application reports the machine type and machine number of the apparatus to the license administration unit for providing the service in step S.

In step S the license administration unit for providing the service requests the business license administration unit to perform the formal registration of the service license in step S. In step S the business license administration unit reports the formal registration of the service license to the license administration unit for providing the service.

When the result of the formal registration indicates the success the license administration unit for providing the service stores the license information of the formal registered service license and the machine type and machine number in the license DB in step S.

In step S the license administration unit for providing the service reports the activation of the service to the authentication and permission unit . The report of the activation of the service is a report of a license activation for the first apparatus and a report of addition of apparatuses for the second and subsequent apparatuses. The report of step S includes the license information of the service license activated by the formal registration and an arrangement of the machine types and machine numbers of the apparatuses provided with the license activation.

Further in step S the authentication and permission unit renews the service permission information stored in the service permission table illustrated in based on the report of step S. The service permission information is a list of the service which can be used by the organization.

The authentication and permission unit adds or deletes a record having a machine type and machine number of and a record having a machine type and machine number of a target apparatus which are illustrated in at a timing of activating inactivating the license. The authentication and permission unit adds or deletes the record having a machine type and machine number of the target apparatus at a timing of adding deleting the apparatus.

In the service permission table illustrated in the record having the machine type and machine number of and the record having a machine type and machine number of at least one apparatus the machine type and machine number of an apparatus provided with the service activation .

In step S the authentication and permission unit returns a response to the report of step S. In step S the license administration unit for providing the service reports the result of the formal registration of the service license to the scan service application .

On the scheduled cancellation date the business license administration unit starts a batch process in step S. In step S the business license administration unit requests the license administration unit for providing the service requests to perform the cancellation of the service license.

In step S the license administration unit for providing the service causes the license information of the canceled service license to be changed reflected in the license DB . In step S the license administration unit for providing the service reports the inactivation of the license to the authentication and permission unit .

Here the report of the service inactivation includes a report of a license inactivation and a report of an apparatus deletion. In step S the license inactivation is reported. The report of step S includes the license information of the service license inactivated by the cancellation and an arrangement of the machine types and machine numbers of the apparatuses provided with the license inactivation.

Further in step S the authentication and permission unit renews the service permission information stored in the service permission table illustrated in based on the report of step S. In the process of step S the service permission information corresponding to the license ID provided with the license inactivation is deleted from the service permission table illustrated in .

When the deletion of the apparatus is reported in the process of step S the service permission information provided with the deletion of the apparatus and corresponding to the arrangement of the machine types and machine numbers is deleted from the service permission table illustrated in . The authentication and permission unit may hold a subset a cache of the license information. In step S the authentication and permission unit returns a response to the report of step S.

When the next license is registered the license administration unit for providing the service performs the process of step S. The license administration unit for providing the service causes the license information of the next license to be formally registered to be changed reflected in the license DB .

In step S the license administration unit for providing the service reports the activation of the license to the authentication and permission unit . The report of step S includes the license information of the next license activated by the formal registration and an arrangement of the machine types and machine numbers of the apparatuses provided with the license activation. In step S the authentication and permission unit renews the service permission information stored in the service permission table illustrated in based on the report of step S.

In the process of for example step S the record having a machine type and machine number of and a record having a machine type and machine number of the target apparatus which are illustrated in are added as the service permission information. In step S the authentication and permission unit returns a response to the report of step S.

In step S the license administration unit for providing the service requests the business license administration unit to perform the formal registration of the next license in step S. In step S the business license administration unit reports the result of the formal registration of the next license to the license administration unit for providing the service. In step S the license administration unit for providing the service reports the result of the cancellation of the current license to the business license administration unit .

In the process of the sequence chart of by making the service permission information it is possible to improve a response performance for generating the service selection screen and a response performance for determining whether the service can be performed or not.

The authentication and permission unit receiving the report of the license activation adds the service permission information to the service permission table illustrated in with a procedure illustrated in for example . is a flowchart of an exemplary process of renewing the service permission table.

In step S the authentication and permission unit refers to the license information the activation of which is reported and determines whether the license mode is only apparatus license or not.

If the license mode is only apparatus license the authentication and permission unit determines that the combination of the service licenses is unnecessary. In step S the authentication and permission unit adds the service permission information corresponding to the machine type and machine number which is provided with the license activation to the service permission table.

If the license mode is not only apparatus license the authentication and permission unit determines that the combination of the service licenses is necessary. Then the process goes to step S. The authentication and permission unit determines whether the license type of the license information provided with the report of the license activation is apparatus license or not.

If the license type is apparatus license the authentication and permission unit determines whether the license information whose license type is user license and which is provided with the license activation exists or not in step S.

If there exists the license information whose license type is user license and which is provided with the license activation the authentication and permission unit adds the service permission information to the service permission table in step S.

If there does not exist the license information whose license type is user license and which is provided with the license activation the authentication and permission unit does not add the service permission information to the service permission table.

If the license type is not apparatus license in step S the authentication and permission unit determines whether other license information whose license type is user license and which is provided with the license activation exists or not in step S.

If there exists the other license information whose license type is user license and which is provided with the license activation the authentication and permission unit does not add the service permission information to the service permission table.

If there does not exist the other license information whose license type is user license and which is provided with the license activation the authentication and permission unit searches the license information whose license type is apparatus license and which is provided with the license activation in step S.

In step S the authentication and permission unit adds the service permission information corresponding to the machine type and machine number of the apparatus which is provided with the license activation in the license information of the search result acquired in step S to the service permission table illustrated in .

The searches in steps S S and S are performed for license information which is provided with the license activation and has the same organization ID service type and license mode as those of the license information provided with the report of the license activation.

The authentication and permission unit receiving the report of the addition of the apparatus adds the service permission information to the service permission table illustrated in with a procedure illustrated in for example . is a flowchart of another exemplary process of renewing the service permission table.

In step S the authentication and permission unit refers to the license information provided with the report of the addition of the apparatus and determines whether the license mode is only apparatus license or not. If the license mode is only apparatus license the authentication and permission unit determines that the combination of the service licenses is unnecessary. In step S the authentication and permission unit adds the service permission information corresponding to the machine type and machine number which is provided with the addition of the apparatus to the service permission table.

If the license mode is not only apparatus license the authentication and permission unit determines that the combination of the service licenses is necessary. Then the process goes to step S. The authentication and permission unit determines whether the license information whose license type is user license and which is provided with the license activation exists or not in step S.

If there exists the license information whose license type is user license and which is provided with the license activation the authentication and permission unit adds the service permission information to the service permission table in step S.

If there does not exist the license information whose license type is user license and which is provided with the license activation the authentication and permission unit does not add the service permission information to the service permission table.

The search in step S is performed for license information which is provided with the license activation and has the same organization ID service type and license mode as those of the license information provided with the report of the addition of the apparatus.

The authentication and permission unit receiving the report of the deletion of the apparatus adds the service permission information to the service permission table illustrated in with a procedure illustrated in for example . is a flowchart of another exemplary process of renewing the service permission table.

In step S the authentication and permission unit refers to the license information provided with the report of the deletion of the apparatus and determines whether the license mode is only apparatus license or not. If the license mode is only apparatus license the authentication and permission unit determines that the combination of the service licenses is unnecessary. In step S the authentication and permission unit deletes the service permission information corresponding to the machine type and machine number which is provided with the deletion of the apparatus from the service permission table.

If the license mode is not only apparatus license the authentication and permission unit determines that the combination of the service licenses is necessary. Then the process goes to step S. The authentication and permission unit determines whether the license information whose license type is user license and which is provided with the license activation exists or not in step S.

If there exists the license information whose license type is user license and which is provided with the license activation the authentication and permission unit deletes the service permission information from the service permission table in step S.

If there does not exist the license information whose license type is user license and which is provided with the license activation the authentication and permission unit does not delete the service permission information from the service permission table. This is because if there does not exist the license information whose license type is user license and which is provided with the license activation the service permission table does not include the service permission information.

The search in step S is performed for license information which is provided with the license activation and has the same organization ID service type and license mode as those of the license information provided with the report of the deletion of the apparatus.

The authentication and permission unit receiving the report of the license inactivation deletes the service permission information from the service permission table illustrated in with a procedure illustrated in for example . is a flowchart of another exemplary process of renewing the service permission table.

In step S the authentication and permission unit refers to the license information the inactivation of which is reported and determines whether the license mode is only apparatus license or not.

If the license mode is only apparatus license the authentication and permission unit determines that the combination of the service licenses is unnecessary. In step S the authentication and permission unit deletes the service permission information corresponding to the machine type and machine number which is provided with the license inactivation from the service permission table.

If the license mode is not only apparatus license the authentication and permission unit determines that the combination of the service licenses is necessary. Then the process goes to step S. The authentication and permission unit determines whether the license type of the license information provided with the report of the license inactivation is apparatus license or not.

If the license type is apparatus license the authentication and permission unit determines whether the license information whose license type is user license and which is provided with the license activation exists or not in step S.

If there exists the license information whose license type is user license and which is provided with the license activation the authentication and permission unit deletes the service permission information from the service permission table in step S.

If there does not exist the license information whose license type is user license and which is provided with the license activation the authentication and permission unit performs nothing.

If the license type is not apparatus license in step S the authentication and permission unit determines whether other license information whose license type is user license and which is provided with the license activation exists or not in step S.

If there exists the other license information whose license type is user license and which is provided with the license activation the authentication and permission unit does not delete the service permission information from the service permission table.

If there does not exist the other license information whose license type is user license and which is provided with the license activation the authentication and permission unit searches the license information whose license type is apparatus license and which is provided with the license activation in step S.

In step S the authentication and permission unit deletes the service permission information corresponding to the machine type and machine number of the apparatus which is provided with the license activation in the license information of the search result acquired in step S from the service permission table illustrated in .

The searches in steps S S and S are performed for license information which is provided with the license activation and has the same organization ID service type and license mode as those of the license information provided with the report of the license inactivation.

The process of requesting to cancel the service license in step S may be requested by the business controller from the service ID change screen illustrated in . The service ID change screen illustrated in is displayed on for example the business terminal . The service ID change screen can display the organization ID and the machine type and machine number associated with the service ID. The process of requesting to cancel the service license in step S can be performed by inserting a check mark into a check box of deletion target of the displayed machine type and machine number on for example the service ID change screen illustrated in .

In order to generate the service selection screen illustrated in the service providing system performs the process as illustrated in . is a sequence chart of generating an exemplary service selection screen.

In step S the user operates the user terminal to log in the portal service application . In step S the portal service application presents an authentication ticket to the authentication and permission unit and requests the authentication and permission unit to acquire an available service view.

In step S the authentication and permission unit requests to acquire a service view by designating the country and the language. The license administration unit for providing the service holds a service master meta information . The data items of the service master are the service type an explanatory text various languages whether the license administration exists or not a URL a top terms of use and an icon .

In step S the license administration unit for providing the service sends a service meta information list to the authentication and permission unit based on the service master. In step S the authentication and permission unit searches the service permission information in the service permission table illustrated in and generates the available service view.

In step S even in a case where there is no record in which the machine type and machine number of the apparatus is set such as the records having the machine type and machine number of the available service view can be accurately generated.

Specifically when the service permission information having the organization ID of the organization in which the user logs and the service type is registered in the service permission table the authentication and permission unit adds this service permission information to the available service view. When the service permission information having the organization ID of the organization in which the user logs and the service type is registered in the service permission table the authentication and permission unit determines that the service corresponding to this service type can be used.

Further the authentication and permission unit unconditionally adds a service provided with no license administration to the available service view. The authentication and permission unit may be configured to hold a use availability setup of the service for each user. In this case the authentication and permission unit can display the service view for each user.

In step S the authentication and permission unit sends the available service view to the portal service application . In step S the portal service application generates the service selection screen as illustrated in by using the available service view. In step S the portal service application can cause the service selection screen illustrated in to be displayed in the user terminal .

The portal service application directly acquires the service meta list from the license administration unit for providing the service and generates the service selection screen by combining with the service permission information acquired from the authentication and permission unit as illustrated in .

Referring to the sequence chart of because the business license administration unit is not accessed a response performance for displaying the service selection screen illustrated in is improved. Referring to the sequence chart illustrated in it is possible to display the service selection screen including the screen elements such as the tab or the icon for selecting the service corresponding the service license when the activated service license exists.

In order to determine whether the service can be performed by the user the service providing system performs a process illustrated in FIG. . is a sequence chart of an exemplary process of determining whether the service can be performed or not.

In step S the user operates the MFP to log in the scan service application . In step S the user operates the MFP to instruct to perform scan. The MFP requests the scan service application to perform the scan.

In step S the scan service application designates the authentication ticket the service type and the machine type and machine number and inquires to the authentication and permission unit about whether the scan service of the MFP can be performed. In step S the authentication and permission unit requests to search the license information by designating the service type and the machine type and machine number.

In place of the process of step S when the service permission information having the organization ID the service type and the machine type and machine number is registered in the service permission table the authentication and permission unit may permit to perform the scan service. The organization ID included in for example the authentication ticket may be used.

The license administration unit for providing the service searches the license information by designating the service type and the machine type and machine number. In step S the license administration unit for providing the service sends the searched license information to the authentication and permission unit . The license administration unit for providing the service can determine whether the scan service of the MFP is performed by checking the state of the license information received from the license administration unit for providing the service.

The authentication and permission unit may hold a subset a cache of the license information. The authentication and permission unit may be configured to hold a use availability setup of the service for each user. In this case the authentication and permission unit determines whether the scan service of the MFP can be performed based on the use availability setup for each user.

The authentication and permission unit reports the determined result of whether the scan service of the MFP can be performed to the scan service application . In step S the scan service application reports the determined result of whether the scan service of the MFP can be performed to the MFP . When the scan cannot be performed the MFP displays for example an error. When the scan can be performed the MFP starts scanning.

The process of the sequence chart illustrated in enables the response performance for starting the scan to be improved because an access to the business license administration unit does not occur. Further when the activated service license exists a job of the service corresponding to the service license can be permitted by the process of the sequence chart illustrated in .

Within the service providing system of the first embodiment the license administration unit for providing the service and the business license administration unit are provided and a difference among the multiple business systems is absorbed compensated by the business license administration unit to facilitate the administration of the license.

Therefore the service providing system can easily constrain the use of the application by various licenses issued by the multiple business systems. Further because the service providing system of the first embodiment can activate the multiple apparatuses by one license the volume license the number of the licenses can be reduced and the administration of the license can be facilitated.

The service providing apparatus is an example of a service providing unit and is substantialized by a CPU or the like. The license administration server is an example of a license administration unit and is substantialized by a CPU or the like. The license DB is an example of a first memory unit and is substantialized by a memory a HDD or the like. The license DB is an example of a second memory unit and is substantialized by a memory a HDD or the like. The license administration unit is an example of an activation unit and is substantialized by a CPU or the like. The client terminal the mobile terminal and the image forming apparatus are an example of an apparatus.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the principles of the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority or inferiority of the invention. Although an information processing system has been described in detail it should be understood that various changes substitutions and alterations could be made thereto without departing from the spirit and scope of the invention.

This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2013 257094 filed on Dec. 12 2013 the entire contents of which are incorporated herein by reference.

