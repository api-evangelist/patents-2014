---

title: Job performing control system, job performing system and job performing control method
abstract: A job performing control system that includes at least an apparatus and controls a job performing apparatus that performs a job, includes a job storing unit that stores a job input in the job performing control system with attribute data of the job, the attribute data being set based on an inputting method of the job; a rule storing unit that stores a predetermined rule that determines a method of performing the job in the job performing apparatus; a determining unit that determines whether the attribute data of the job satisfies the predetermined rule; and a performing control unit that controls the job performing apparatus to perform the job determined to satisfy the predetermined rule by the determining unit by the method of performing the job determined from the predetermined rule.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09176682&OS=09176682&RS=09176682
owner: RICOH COMPANY, LTD.
number: 09176682
owner_city: Tokyo
owner_country: JP
publication_date: 20140218
---
The present invention relates to a job performing control system a job performing system and a job performing control method.

In recent times attention has been given to usage environments typified by cloud services in which web application functions or external server side application functions are provided as a service. For example for a print service using a cloud by sending and storing a print job to a server on the cloud the print job can be performed by any image forming apparatuses at any place that is capable of accessing the server. With this a user can perform a print job with an outside image forming apparatus by sending data to be printed by an e mail or uploading the data by a web site to the server for example.

On the other hand as one method of printing using image forming apparatuses device designated printing is known. In the device designated printing a job print job is input with designating an image forming apparatus to print the job in a print driver. The designated image forming apparatus instantly prints the job when the job is input. Thus this method is convenient for a user who is in a hurry.

Further as another one of the methods of printing using the image forming apparatuses on demand printing is known. In the on demand printing a user can obtain a job list of jobs stored in a print server by logging in an image forming apparatus and then the job selected from the job list is printed by the image forming apparatus. As the image forming apparatus prints the job after the user logs in the image forming apparatus in the on demand printing the on demand printing has a security higher than that of the device designated printing because the user can be prevented from leaving the printed document that causes leakage of the content to a third person.

However the on demand printing is inferior to the device designated printing with respect to simply and immediately performing the job because the user has to select a job to be performed after logging in the image forming apparatus in the on demand printing. As such there are different advantages for the methods of printing. As both methods have different advantages users wish to use an appropriate one based on the situation the place or the like to perform a job.

However conventionally in the on demand printing there is a problem in that only a place or a device previously designated by a management tool or the like can be designated as a place or a device to print when a job is input using an e mail. Further although cases of using devices other than the devices normally used by users such as the print service using the cloud as described above are increasing in such cases the device designated printing may not be used.

Here Patent Document 1 discloses a data output system by which a user can easily request printing of an attached file of an e mail received by a mobile phone for example.

However according to the technique disclosed in Patent Document 1 methods such as the device designated printing or the like cannot be selected so that the above problems cannot be solved.

The present invention is made in light of the above problems and provides a technique capable of easily controlling a method of performing the job based on a method of inputting the job.

According to an embodiment there is provided a job performing control system that includes at least an apparatus and controls a job performing apparatus that performs a job including a job storing unit that stores a job input in the job performing control system with attribute data of the job the attribute data being set based on an inputting method of the job a rule storing unit that stores a predetermined rule that determines a method of performing the job in the job performing apparatus a determining unit that determines whether the attribute data of the job satisfies the predetermined rule and a performing control unit that controls the job performing apparatus to perform the job determined to satisfy the predetermined rule by the determining unit by the method of performing the job determined from the predetermined rule.

According to another embodiment there is provided a job performing system including a job performing apparatus that performs a job and a job performing control system that includes at least an apparatus and controls the job performing apparatus. The job performing control system includes a job storing unit that stores a job input in the job performing control system with attribute data of the job the attribute data being set based on an inputting method of the job a rule storing unit that stores a predetermined rule that determines a method of performing the job in the job performing apparatus a determining unit that determines whether the attribute data of the job satisfies the predetermined rule and a performing control unit that controls the job performing apparatus to perform the job determined to satisfy the predetermined rule by the determining unit by the method of performing the job determined from the predetermined rule. The job performing apparatus includes a job performing unit that performs the job based on the method of performing.

According to another embodiment there is provided a job performing control method performed by a job performing control system that includes at least an apparatus and controls a job performing apparatus that performs a job including a job storing step of storing a job input in the job performing control system with attribute data of the job the attribute data being set based on an inputting method of the job a rule storing step of storing a predetermined rule that determines a method of performing the job in the job performing apparatus a determining step of determining whether the attribute data of the job satisfies the predetermined rule and a performing control step of controlling the job performing apparatus to perform the job determined to satisfy the predetermined rule in the determining step by the method of performing the job determined from the predetermined rule.

Note that also arbitrary combinations of the above described elements and any changes of expressions in the present invention made among methods devices systems recording media computer programs and so forth are valid as embodiments of the present invention.

The invention will be described herein with reference to illustrative embodiments. Those skilled in the art will recognize that many alternative embodiments can be accomplished using the teachings of the present invention and that the invention is not limited to the embodiments illustrated for explanatory purposes.

It is to be noted that in the explanation of the drawings the same components are given the same reference numerals and explanations are not repeated.

The network N and the network N are connected via a firewall FW of the network N. The firewall FW is provided at a connecting point of the network N and the network N and relays an access from the network N to the network N. The network N and the network N are connected via an access control apparatus of the network N. The security of the network N is protected by the access control apparatus . The network N is a private network that is provided inside the firewall FW. The client terminal and the image forming apparatus are connected to the network N.

The client terminal is an example of a terminal apparatus and is a Personal Computer PC a mobile terminal or the like for example. The client terminal may be a general data processing apparatus a computer system on which OS or the like is mounted. The client terminal has a wireless or wired communication function. The mobile terminal is a terminal capable of being carried by a user such as a smartphone a mobile phone a tablet PC or the like for example.

The image forming apparatus is an example of a job performing apparatus that performs a job. The image forming apparatus is an apparatus that has an image forming function to perform a print job such as a printer a Multifunction Peripheral MFP or the like for example. The image forming apparatus has a wireless or wired communication function. The image forming apparatus is not limited to the printer the MFP or the like and may be a copying machine a scanner a projector or the like.

The job performing system illustrated in may include a plurality of the client terminals and the image forming apparatuses .

The mail server is connected to the network N. The mail server is a computer that transfers e mails. For example an e mail with a predetermined address sent by the client terminal is stored in the mail server and is obtained by the job performing control system .

The network N is connected to the network N such as INTERNET or the like by the access control apparatus . The job performing control system includes a print service providing apparatus a scan service providing apparatus another service providing unit and the like in addition to the access control apparatus . The access control apparatus the print service providing apparatus the scan service providing apparatus and the other service providing unit are connected to the network N. For the job performing system as illustrated in the access control apparatus the print service providing apparatus the scan service providing apparatus and the other service providing unit actualize a job performing control system.

The access control apparatus controls a log in to services such as a print service provided by the print service providing apparatus a scan service provided by the scan service providing apparatus or the like. The access control apparatus the print service providing apparatus the scan service providing apparatus and the other service providing unit are actualized by one or more data processing apparatuses computer systems .

The print service providing apparatus the scan service providing apparatus and the other service providing unit of the job performing system illustrated in may be actualized by a single computer or may be actualized by a plurality of distributed computers.

 1 An administrator of the job performing system previously sets a job performing rule that defines a method of performing outputting printing or the like a job to the job performing control system .

In this embodiment the job performing rule is a condition to perform a job by a direct print. Here in this embodiment a method of printing by which the job is performed printed without selecting a job to be performed from a job list after a user inputs the job in the job performing control system and logs in the image forming apparatus is referred to as a direct print .

When a user logs in the image forming apparatus to perform a job and the job is determined to satisfy the job performing rule the job is directly performed output printed or the like without displaying a job list screen for on demand printing that includes various instruction data such as a job name or the like to the user. The job performing rule is for example conditions such as job is printed using an image forming apparatus previously designated by a user job is sent by an e mail attached to an e mail or the like.

 2 When a user operates the client terminal and sends an e mail attached with a job A to be performed to a predetermined address it means that the job A is input in the performing control system . Here alternatively the job A may be input by another method such as uploading using a web page web upload or the like.

 4 When the user logs in the image forming apparatus for performing the job A the image forming apparatus sends a log in request to the job performing control system .

 5 The job performing control system determines whether the job A satisfies the job performing rule based on the previously set job performing rule.

 6a When the job A is determined to satisfy the job performing rule the job performing control system sends the job A to the image forming apparatus .

Here in the above processes 4 to 7a if another job other than the job A exists that is determined to satisfy the job performing rule the other job is also directly performed by the image forming apparatus.

 6b When the job A and other jobs input in the performing control system by the user are determined not to satisfy the job performing rule in 5 a normal on demand printing is performed. At this time the job performing control system sends a job list of the jobs input in the performing control system by the user to the image forming apparatus .

 7b The image forming apparatus displays a selection screen including the job list for selecting a job for the on demand printing. The selection screen includes a user name of the user the job list a print button a delete button and the like. Then when the user selects a job based on the screen the image forming apparatus sends a request of obtaining the selected job to the job performing control system . Thereafter the selected job is sent to the image forming apparatus from the job performing control system and the image forming apparatus performs outputs prints the selected job.

As such according to the job performing system of the embodiment if a job satisfies the job performing rule a procedure for a user to select a job to be printed from a job list can be omitted so that the processes necessary to obtain a printed document can be simplified. According to the embodiment the job performing rule can be set based on the method of inputting the job such as job is sent by an e mail attached to an e mail or the like. Thus for example when the job is input by the e mail as it is assumed that the user is in a hurry when the job is input the job is directly performed printed right after the user logs in the image forming apparatus.

The computer system includes an input device a display device an external I F a Random Access Memory RAM a Read Only Memory ROM a Central Processing Unit CPU a communication I F a Hard Disk Drive HDD and the like that are connected with each other via a bus B.

The input device includes a keyboard a mouse a touch panel or the like and is used by a user to input operation signals. The display device includes a display or the like and displays processed results by the computer system .

The communication I F is an interface that connects the computer system to the network N or N. The computer system may perform a data communication via the communication I F .

The HDD is a non volatile storage device that stores programs or data. The programs or data stored in the HDD include an Operating System OS that is basic software to control the entirety of the computer system application software that provide various functions on the OS or the like. The HDD manages the program or data stored therein by a predetermined file system and or a database DB .

The external I F is an interface between an external device. The external device may be a recording medium or the like. The computer system is capable of reading and writing data from and on the recording medium via the external I F . The recording medium may be a flexible disk a Compact Disk CD a Digital Versatile Disk DVD an SD Memory card a Universal Serial Bus memory or the like.

The ROM is a non volatile semiconductor memory storage device capable of storing programs or data even when a power supply is off. The ROM stores programs or data such as a Basic Input Output System BIOS that is executed when the computer system is activated a setting of the OS a setting of networks or the like. The RAM is a volatile semiconductor memory storage device that temporarily stores programs or data.

The CPU is an arithmetic device that controls and actualizes functions of the entirety of the computer system by reading out the programs or data from storage devices such as the ROM the HDD or the like on the RAM and executing processes.

The client terminal the access control apparatus the print service providing apparatus the scan service providing apparatus the other service providing unit and the mail server of the embodiment illustrated in may actualize various processes which will be explained later by the hardware structure of the computer system .

The controller includes a CPU a RAM a ROM an NVRAM a HDD and the like. The ROM stores various programs or data. The RAM temporarily stores programs or data. The NVRAM stores setting data or the like for example. The HDD stores various programs or data.

The CPU is a calculation device that controls and actualizes functions of the entirety of the image forming apparatus by reading out the programs the data the setting data or the like from the ROM the NVRAM the HDD or the like on the RAM and executing processes.

The operation panel includes an input unit that accepts an input from a user and a display unit that displays data. The external I F is an interface between an external device. The external device may be a recording medium or the like. The image forming apparatus is capable of reading and writing data from and on the recording medium via the external I F . The recording medium may be an IC card a flexible disk a CD a DVD an SD Memory card a Universal Serial Bus memory or the like.

The communication I F is an interface that connects the image forming apparatus to the network N1. The image forming apparatus is capable of having a data communication via the communication I F .

The printer is a printing device that prints print data on a paper. The scanner is a reading device that obtains image data from a document.

The image forming apparatus of the embodiment may actualize various processes which will be explained later by the above described hardware structure.

The client terminal of the embodiment is actualized by a functional structure as illustrated in for example. is a view illustrating an example of a functional structure of the client terminal of the embodiment. Each function may be actualized by the CPU that executes programs in cooperation with the hardware structure.

The client terminal includes a log in requesting unit a job inputting unit an input accepting unit and the like. The log in requesting unit and the job inputting unit are functions included in a print service using application .

The log in requesting unit requests a log in to the job performing control system by sending authentication data. The authentication data of the embodiment may include user identification data user ID that uniquely identifies a user a password and group identification data hereinafter referred to as a company code that identifies a group such as a company an organization or the like to which the user belongs.

The job inputting unit inputs sends a job in to the job performing control system . When the print service is used the job means a print job. The job is input by the job inputting unit by sending an e mail attached with the job to be performed web uploading or the like. When the job is sent by the e mail address data corresponding to the place office or the image forming apparatus that performs the job is set for an e mail destination address. The e mail sent from the job inputting unit is stored in the mail server .

The input accepting unit accepts an input by a user operation such as a touch panel contacting operation a keyboard input operation or the like.

The image forming apparatus of the embodiment is actualized by a functional structure illustrated in for example. is a view illustrating an example of a functional structure of the image forming apparatus of the embodiment. Each function may be actualized by the CPU that executes programs in cooperation with the hardware structure.

The image forming apparatus of the embodiment includes a log in requesting unit a job obtaining unit a display control unit an input accepting unit a job performing unit and the like. The log in requesting unit and the job obtaining unit are functions included in print service using application .

The log in requesting unit sends a log in request for obtaining a job or a job list to the job performing control system . The log in request by the log in requesting unit includes a user ID a password and a company code of a user who requests to log in and device ID that uniquely identifies the image forming apparatus to which the log in is requested. The password and the company code may be optionally required for the log in request by the log in requesting unit .

Then the log in succeeds the job obtaining unit obtains a job or a job list from the job performing control system as a response to the log in request.

The display control unit displays a job selection screen for performing a normal on demand printing based on the job list obtained by the job obtaining unit .

The input accepting unit accepts an input by a user operation such as a touch panel touching operation a keyboard input operation or the like. The input accepting unit accepts an input of authentication data such as a user ID a password or the like from a user for example.

The job performing control system of the embodiment is actualized by a functional structure as illustrated in for example. is a view illustrating an example of a functional structure of the job performing control system of the embodiment. The job performing control system includes service application a platform a management data storing unit and a platform Application Programming Interface API . These are structured by a program stored in the job performing control system and to be executed by the CPU.

The service application includes print service application scan service application and one or more other service application as an example.

The print service application is an application program that provides a print service and has functions illustrated in . is a view illustrating an example of a functional structure of the print service application of the embodiment. As illustrated in the print service application includes a job accepting unit a job analyzing unit a job attribute data management unit a job job list sending unit a determining unit a job performing rule management unit a job attribute data storing unit a job performing rule storing unit and the like.

The job accepting unit accepts a job input from the client terminal . When the job is input by an e mail the job accepting unit receives data included in the job a body of the e mail and an attached file from the mail obtaining unit . Further when the job is input by a web upload the job accepting unit receives the job sent from the client terminal via the session management unit . Then the job accepting unit transfers the received job to the job analyzing unit .

The job analyzing unit analyzes the job transferred from the job accepting unit . Specifically the job analyzing unit specifies user management data the user ID the company code or the like of the user of the client terminal who inputs the job or extracts the print property included in the job. Then the job analyzing unit instructs the job attribute data management unit to store data hereinafter referred to as job attribute data regarding the job specified by the analysis in the job attribute data storing unit . Further the job analyzing unit determines a data conversion content of the input job adds a job ID that identifies the job to the job and stores the job in the data storage .

The job attribute data management unit stores or reads out job attribute data corresponding to the input job in and from the job attribute data storing unit based on a request from the job analyzing unit .

The job attribute data storing unit stores job attribute data as illustrated in . is a view illustrating an example of data stored in the job attribute data storing unit . As illustrated in the job attribute data storing unit stores items such as job ID company code user ID job name print setting job inputting method e mail destination device office data direct print designating flag and the like. Although not illustrated in the drawings the job attribute data storing unit may further store an item such as conversion status or the like.

The job ID is identification data that uniquely identifies the job in the job performing control system . The company code is a company code of an organization company to which the user who inputs the job belongs. The user ID is identification data that identifies the user who inputs the job. Here when the job is input by an e mail the company code and the user ID of the user who inputs the job are set based on the sender address of the e mail. On the other hand when the job is input by web upload the company code and the user ID of the user who inputs the job are set based on a user ID that is input when the logs in the client terminal . The job name is a name of the job and arbitrarily set by the user.

The print setting is a so called print property that is applied when performing printing the job and includes conditions such as color monochrome single side both sides with without intensive 2 in 1 or the like or the like. Further the print setting may further include data such as with or without staple with or without punches the printing number paper size or the like.

The job inputting method is data indicating a method of inputting the job that is whether the job is input by an e mail or web upload. The e mail destination device office data is data indicating a device device ID of the image forming apparatus or an office name corresponding to the destination address of the e mail that is set when the job is input by the e mail. The direct print designating flag is data indicating whether a direct print is designated by the user that is set when the job is input by the web upload.

Referring back to upon accepting a log in request from the image forming apparatus the job job list sending unit requests the determining unit to determine whether to perform a direct print based on the job performing rule of the job. Here the log in request includes user ID of a user who performs a log in operation inputting ID password having a card reader of the image forming apparatus read an IC card or the like to the image forming apparatus and device ID of the image forming apparatus . Then the job job list sending unit sends the job or the job list to the image forming apparatus based on the determined result by the determining unit . Specifically when it is determined that the job performing rule is satisfied in other words when it is determined that a condition to perform the direct print is satisfied the job job list sending unit sends the job. On the other hand when it is determined that the job performing rule is not satisfied the job job list sending unit sends the job list.

The determining unit determines whether the job attribute data of the job corresponding to the user ID included in the log in request satisfies the job performing rule stored in the job performing rule data storing unit based on the instruction from the job job list sending unit . Then the determining unit outputs the determined result to the job job list sending unit .

The job performing rule management unit stores the job performing rule in the job performing rule data storing unit or reads out the job performing rule stored in the job performing rule data storing unit . The job performing rule management unit accepts a job performing rule input by an administrator or the like and stores it in the job performing rule data storing unit .

Referring back to the scan service application is an application that provides a scan service. The other service application is an application that provides an arbitral service.

Referring back to the platform API is an interface for the service application such as the print service application the scan service application the other service application or the like to use the platform . The platform API is an interface that is previously defined so that the platform is capable of receiving a request from the service application and is structured by a function a class or the like for example. Here when the job performing control system is structured by a plurality of data processing apparatuses web API that is capable of being used via a network for example may be used as the platform API .

The platform includes an authentication processing unit a device communication unit a session management unit a data processing unit a mail obtaining unit and the like.

The authentication processing unit performs an authentication based on a log in request from the client terminal the image forming apparatus or the like. The authentication processing unit accesses a user management data storing unit which will be explained later to authenticate the user. Further the authentication processing unit accesses an organization management data storing unit and a device management data storing unit to authenticate the image forming apparatus or the like.

The device communication unit performs a communication between the client terminal and the image forming apparatus .

The session management unit manages a session with the client terminal and the image forming apparatus .

The data processing unit processes data sent from the client terminal and the image forming apparatus and data stored in the data storage . The data processing unit converts a data format of the application data to be printed in a Page Description Language PDL format deletes the data stored in the data storage or the like for example.

The mail obtaining unit periodically performs a polling to the mail server and obtains e mail having a predetermined address domain . Then the mail obtaining unit extracts an attached file from the obtained e mail and outputs the obtained mail body and the attached file to the print service application .

The management data storing unit includes the organization management data storing unit the user management data storing unit the device management data storing unit a data management data storing unit and a data storage .

The organization management data storing unit stores organization management data as illustrated in . is a view illustrating an example of the data stored in the organization management data storing unit . As illustrated in the organization management data includes items such as company code company name country language or the like. The company code is identification data that identifies the company organization . The company name is a name of the company organization . The country is a country name to which the company organization belongs. The language is the language used in the company organization .

The user management data storing unit stores user management data as illustrated in . is a view illustrating an example of the data stored in the user management data storing unit . As illustrated in the user management data includes items such as company code user ID password role user address data main work location designated device ID and the like.

The company code is the same as the above described company code and is a company code of the organization company to which the user belongs. The user ID is identification data that identifies the user. It is necessary for the user ID to be unique among users of the same company code and as long as this condition is satisfied the user ID may be a user name. Further for the user ID data that identifies an electronic medium an IC card for example possessed by the user may be used. For the electronic medium possessed by the user an IC card a mobile phone a tablet terminal an electronic book terminal or the like may be used. For data that identifies the electronic medium a card ID a serial ID telephone number of the mobile phone profile data of the terminal or the like may be used. The data that identifies the electronic medium may be the combination of the above examples.

The password is authentication data that is referred to when a log in request from the client terminal or the image forming apparatus is accepted. Here the password is optionally provided. The role is data indicating whether the user is an administrator or a normal user.

The user address data is an e mail address of the user for example. The user address data is a sender address when the job is input by the e mail from the client terminal . The main work location is data indicating a place where the user ordinary work at not a business trip destination and is an office name for example. The designated device ID is a device ID that uniquely identifies the image forming apparatus . For the designated device ID a device ID of the image forming apparatus that is often used by the user or a default value may be set.

The device management data storing unit an example of a job performing place data storing unit stores device management data that is data regarding the image forming apparatus as illustrated in . is a view illustrating an example of data stored in the device management data storing unit . As illustrated in the device management data includes items such as device ID company code provided office device office address data and the like.

The device ID is identification data that uniquely identifies the image forming apparatus and may be a device ID of the image forming apparatus . Alternatively the device ID may be a MAC address or the like of the image forming apparatus for example.

The company code is the same as the above described company code and may be the company code of the organization company that manages the image forming apparatus . The provided office is a name of the office where the image forming apparatus is provided.

The device office address data is address data such as an e mail address or the like provided for each of the image forming apparatuses or each office for example. For the example illustrated in address data corresponding to the device ID DEV111 is DEV111.A xxx.com and address data corresponding to office A whose device ID is not set is A xxx.com . When the user inputs a job the user can change whether to perform a direct print for the job based on the job performing rule by setting address data corresponding to a device to perform the job or a place office to perform the job.

The data management data storing unit stores a place URI or the like of data such as an electronic file or the like included in the job that is stored in the data storage . is a view illustrating an example of data stored in the data management data storing unit . As illustrated in the data management data includes items such as job ID job stored URL and the like. The job ID is the same as the above described job ID and is identification data that identifies the input job or the like. The job stored URL is data indicating a place where the data of the input job is stored.

The structure of units illustrated in is just an example and the units illustrated in may not be structured or layered as such.

The operation of the job performing system mainly includes 1. Process of inputting sending job and 2. Process of performing job . First the process of inputting sending job is explained.

In step S the input accepting unit of the client terminal accepts a request of sending an e mail whose destination address is address data of the print service application and indicating to input a job from a user the person who instructs to input the job . The address data of the print service application is an e mail address corresponding to the image forming apparatus that performs the job or the place office where the job is to be performed. The user may previously know the address data or the address data may be put on the target image forming apparatus or the like so that the user can recognize the address data.

In step S the input accepting unit transfers the request of sending the e mail accepted from the user to the job inputting unit . In step S the job inputting unit sends the e mail requested by the user to the mail server .

In steps S to S the mail obtaining unit of the job performing control system receives the e mail from the mail server by polling for example. The mail obtaining unit may receive the e mail when a request of obtaining the e mail is requested by the print service application .

In step S when the mail obtaining unit receives the e mail if an attached file is attached to the e mail the mail obtaining unit extracts the attached file from the e mail. The attached file is not essential. In step S the mail obtaining unit sends a mail body and the attached file if it is attached as mail data to the print service application .

In step S the job accepting unit of the print service application causes the job analyzing unit to analyze the content of the received mail data. Specifically the job analyzing unit of the print service application obtains an URL a destination address and a sender address that is a mail address of the user that are described in the mail body.

In step S the job analyzing unit of the print service application sends a request of obtaining user management data to the authentication processing unit by designating the sender address and the destination address in the received mail data.

In step S the authentication processing unit refers to the user management data storing unit and obtains the user management data corresponding to the sender address and the destination address. In step S the authentication processing unit sends the user management data corresponding to the sender address and the destination address to the print service application .

In step S the job analyzing unit of the print service application stores job attribute data in which a job ID that specifies the job input by the e mail the company code of the user the user ID of the user are in correspondence with each other in the job attribute data storing unit .

In step S the job analyzing unit of the print service application requests the data processing unit to store the input job in the data storage .

Then in step S the data processing unit stores the job in the data storage and stores the job ID and a place where the job is stored in the data management data storing unit .

The user the person who instructs to input the job requests a log in to the job performing control system by inputting the company ID the user ID and the password and presses a log in button in a log in screen displayed on the client terminal illustrated in . The company ID is an example of the company code.

Referring back to in step S the input accepting unit of the client terminal accepts the company ID the user ID and the password from the user as log in data. In step S the input accepting unit sends a log in request accepted from the user to the log in requesting unit . In step S the log in requesting unit requests the authentication processing unit of the job performing control system to log in based on the log in data accepted from the user.

In step S the authentication processing unit authenticates the log in data. The authentication processing unit determines whether to allow or not to allow the log in by the user. Here it is assumed that the log in by the user is allowed.

In step S the authentication processing unit sends a log in response indicating that the log in allowed to the log in requesting unit of the client terminal . Upon receiving the log in response indicating that the log in allowed the client terminal displays a service selection screen as illustrated in for example to have the user select a service.

When the user presses a print service button in the service selection screen the print service is selected. In step S it is assumed that the input accepting unit of the client terminal accepts a request of using the print service from the user. In step S the input accepting unit outputs the request of using the print service to the job inputting unit .

In step S the job inputting unit sends the request of using the print service accepted from the user to the job performing control system . After confirming the session in step S the session management unit obtains screen data of a print service screen as illustrated in as an example of a service using screen from the print service application in steps S to S. The print service screen includes designation forms for the job to input upload a check box to designate a direct print. The check box to designate the direct print is checked when the user wishes to have the input job to be performed by the direct print. The print service screen further includes an upload button and a cancel button. The print service screen may further include a setting format for setting the print property color monochrome single side both sides or the like .

Referring back to in step S the session management unit sends the screen data of the print service screen to the job inputting unit . The client terminal displays the print service screen as illustrated in and accepts a designation of the job to input from the user. The user sets the data to be printed by designating a file an URL or the like sets data such as checking the check box to designate the direct print or the like and presses the upload button in the print service screen .

In step S the input accepting unit of the client terminal accepts settings of the data to be printed from the user. In step S the input accepting unit outputs a request of inputting the job based on the settings of the data accepted from the user to the job inputting unit . In step S the job inputting unit sends the request of inputting the job to the job performing control system .

After confirming the session in step S in step S the session management unit outputs the request of inputting the job to the print service application . Processes of the print service application after receiving the request of inputting the job are the same as those of the case when the job is input by the e mail except that the job attribute data is extracted based on the e mail received from the user or the job attribute data is extracted based on the settings of the data accepted from the user. Thus the explanation is omitted.

First upon receiving the job from the mail obtaining unit or the session management unit the job accepting unit of the print service application requests the job analyzing unit to analyze the received job S .

The job analyzing unit determines the method of inputting the job that is whether the job is input by the e mail or the web upload S . Specifically the job analyzing unit determines that the job is input by the e mail when the job includes e mail data and determines that the job is input by the web upload when the job includes the company code the user ID and the device ID.

When it is determined that the job is input by the e mail in step S the device or the office place corresponding to the destination address included in the job is specified S . Specifically the job analyzing unit obtains the device ID or the provided office corresponding to the destination address included in the job from the device management data storing unit S . Here with reference to when it is assumed that the destination address is DEV111.A xxx.com for example the device ID DEV111 corresponding to the device office address data DEV111.A xxx.com is obtained. If there is no device ID corresponding to the device office address data the office name set in the provided office is obtained.

Then the job analyzing unit obtains the company ID and the user ID of the user the person who inputs the job from the user management data storing unit based on the sender address included in the job S . Here for example when it is assumed that the sender address is userA xxx.com the company code XXX and the user ID UserA corresponding to the user address data userA xxx.com in the user management data storing unit as illustrated in are obtained.

Then the job analyzing unit stores the specified company code the user ID the job inputting method and the device office address data and the job name and the print setting included in the job in the job attribute data storing unit via the job attribute data management unit S .

Then the job analyzing unit requests the data processing unit to store the sent job in the data storage and the data processing unit stores registers the job in the data storage S .

On the other hand when it is determined that the job is sent by the web upload in step S the job analyzing unit obtains data indicating whether the direct print is designated included in the request of inputting the job S .

Next the job analyzing unit obtains the company code and the user ID included in the log in request S . Thereafter the above described processes after step S are performed. Here when the job is sent by the web upload in step S the job inputting method included in the job attribute data is set to be web upload and when the direct print is designated the direct print designating flag is set to be ON . Further in this case values are not set in the e mail destination device office data N A or the like is set .

As described above the job performing system of the embodiment is capable of storing the job input from the client terminal and the job attribute data of the job including the job inputting method in the job performing control system .

Then a process of having the image forming apparatus perform the input job in accordance with an instruction by the user is explained. is a sequence diagram illustrating an example of a process of performing a job of the embodiment.

First upon receiving an input of the authentication data log in data such as the company code the user ID the password or the like from the user S the input accepting unit of the image forming apparatus requests the log in to the log in requesting unit S . Here the authentication data may be input using the IC card or the like on which the user ID or the like of the user is written.

The log in requesting unit sends the log in request including the company code the user ID and the password to the job performing control system S .

The authentication processing unit of the job performing control system refers to the user management data storing unit and performs an authentication process based on the company code the user ID and the password included in the log in request S . Then the authentication processing unit sends the authentication result as a log in response to the image forming apparatus S . Here when the authentication result indicates success log in is allowed the authentication processing unit also sends a token cookie to the image forming apparatus . The job performing control system stores the token and the user name and the company code of the authenticated user in correspondence with each other.

Processes after step S are examples when the authentication result is success log in OK . The log in requesting unit outputs the authentication result log in OK including the received token to the job obtaining unit S . The job obtaining unit generates a request of obtaining a job including the token and the device ID of the image forming apparatus for obtaining a job corresponding to the logged in user user ID from the job performing control system and sends it to the job performing control system S .

Upon receiving the request of obtaining the job the session management unit of the job performing control system determines whether the same token as the token included in the request of obtaining the job exists in previously stored tokens. When the same token as the token included in the request of obtaining the job exists in the previously stored tokens the session management unit adds the user ID and the company code that are corresponded with the token to the request of obtaining the job and outputs the request of obtaining the job to the print service application S .

Upon receiving the request of obtaining the job the job job list sending unit of the print service application outputs the company code and the user ID included in the request of obtaining the job to the determining unit . The determining unit obtains a list of the job attribute data of the job stored in the job attribute data storing unit that match the user ID and the company code included in the request of obtaining the job via the job attribute data management unit S . Then the determining unit determines whether each of the jobs satisfies the job performing rule based on the read out job attribute data and the job performing rule stored in the job performing rule data storing unit S . The jobs determined to satisfy the job performing rule by the determining unit are target jobs for the direct print. On the other hand the jobs determined not to satisfy the job performing rule by the determining unit are target jobs for the normal on demand printing. The determining unit outputs a determined result to the job job list sending unit .

Here when the job is determined to satisfy the job performing rule by the determining unit in step S the job job list sending unit sends a request of obtaining a target job for the direct print to the data processing unit . Upon receiving the target job from the data storage S the data processing unit sends a response including the obtained job to the job job list sending unit S . The job job list sending unit sends the obtained job to the image forming apparatus via the session management unit S S .

The job obtaining unit of the image forming apparatus requests the job performing unit to perform the obtained job S . The job performing unit performs prints the job S .

On the other hand when it is determined that the job does not satisfy the job performing rule by the determining unit in step S the job job list sending unit sends the job list of the job s that does not satisfy the job performing rule to the image forming apparatus S via the session management unit S .

The job obtaining unit of the image forming apparatus requests the display control unit to display the obtained job list S . The display control unit displays the job list on the operation panel an external display that is connected to the display control unit or the like S .

Here when the jobs in the job list corresponding to the user include both of a job that satisfies the job performing rule and a job s that does not satisfy the job performing rule the job and the job list may be sent from the job performing control system to the image forming apparatus .

First the job job list sending unit of the print service application of the job performing control system receives the request of obtaining the job sent from the image forming apparatus S . Then the job job list sending unit extracts the user ID and the company code included in the request of obtaining the job S . The job job list sending unit outputs the extracted user ID and the company code to the determining unit .

The determining unit obtains a list of job attribute data corresponding to the user ID from the job attribute data storing unit via the job attribute data management unit S .

Next the determining unit obtains the job performing rule corresponding to the company code from the job performing rule data storing unit via the job performing rule management unit S .

Processes of steps S to S are performed for each of the jobs included in the list of the job attribute data.

The determining unit determines whether the job attribute data of the job included in the list of the job attribute data satisfies the job performing rule in other words the condition to allow the direct print S . The process of determining is explained in detail later with reference to .

When the target job is determined to satisfy the job performing rule YES in step S the job job list sending unit obtains the target job from the data storage via the data processing unit and sends it to the image forming apparatus S .

On the other hand when the target job is determined not to satisfy the job performing rule NO in step S the determining unit sets the target job in the job list S . Then after the determining process is performed for the number of the jobs included in the job attribute data list the job job list sending unit sends the job list to the image forming apparatus S .

Here the job that satisfies the job performing rule in step S may be sent every time the process of determining is performed or may be sent at the same time with other jobs that satisfy the job performing rule after the process of determining for all of the jobs included in the list of the job attribute data are performed. Further the process of step S in which the job is sent and the process of step S in which the job list is sent may be performed at the same time.

Here in for example it is assumed that the user ID of the user is UserA the company code is XXX and the device ID of the image forming apparatus to which the user logs in to have a printed document is DEV222 . Further it is assumed that data as illustrated in and are stored in the user management data storing unit the job attribute data storing unit and the job performing rule data storing unit respectively.

The determining unit reads out the job attribute data of the job IDs 1 3 and 4 corresponding to the user ID UserA and the company code XXX from the job attribute data storing unit see . First the determining unit designates the job corresponding to the job ID 1 among the job IDs 1 3 and 4 as a target job.

Further the determining unit reads out the job performing rule based on the user ID UserA and the company code XXX from the job performing rule data storing unit see .

Then the determining unit determines whether one of the job performing rules illustrated in for example designated device by user and device to print are same is satisfied S . Here as the designated device ID of the user ID UserA is DEV111 according to the user management data storing unit see it is determined that the designated device by the user and the device to print DEV222 are different NO in step S .

Next the determining unit determines whether another one of the job performing rules illustrated in office corresponding to e mail destination address and office to print are same is satisfied S . Here as the e mail destination device office data included in the job attribute data corresponding to the job ID 1 is DEV222 as illustrated in address data corresponding to an office is not set as the e mail destination address. Thus it is determined that the office corresponding to e mail destination address and office to print are same is not satisfied NO in step S .

Next the determining unit determines whether another one of the job performing rules illustrated in device corresponding to e mail destination address and device to print are same is satisfied S . Here as the e mail destination device office data included in the job attribute data corresponding to the job ID 1 is DEV222 as illustrated in and the device to print is also DEV222 it is determined that the device corresponding to e mail destination address and device to print are same is satisfied YES in step S .

In this case YES in step S the job job ID 1 is determined to satisfy the condition for the direct print job performing rule S . Similarly when the job is determined to satisfy any one of the job performing rules YES in step S or S the job is determined to satisfy the condition for the direct print S .

On the other hand when the job is determined not to satisfy all of the job performing rules corresponding to the company code XXX NO in step S the job is determined not to satisfy the condition for the direct print job performing rule S .

The process of determining illustrated in is performed for all of the jobs job ID 1 3 and 4 corresponding to the user ID UserA and the company code XXX .

Here the process of determining based on the job performing rule may not be performed by the job performing control system print service application . Alternatively the process of determining may be performed by the image forming apparatus not by the job performing control system for example. In this case for example the image forming apparatus may include a unit that has the same function as the determining unit and the data stored in the job attribute data storing unit and the job performing rule data storing unit may be included in a response to the request of obtaining the job from the image forming apparatus . Then the image forming apparatus may perform the process of determining.

By the above processes according to the job performing system of the embodiment whether to perform the direct print is determined based on the predetermined job performing rule previously set by the administrator or the like and the job attribute data of the job set based on the method of inputting the job e mail web upload or the like or the like. Then in the job performing system of the embodiment when the input job is determined to satisfy the predetermined job performing rule and the input job is determined to be performed by the direct print by the job performing control system the job is obtained from the job performing control system to be printed when a user logs in from the image forming apparatus without having the user select a job from a job list.

With this the administrator or the user is capable of flexibly changing the method of performing the job based on the method of inputting the job the device image forming apparatus to use or the like so that the procedure for printing can be simplified.

Further as the direct print is performed after the user logs in the image forming apparatus that performs the job the user can be prevented from leaving the printed document that causes leakage of the content to a third person. Thus security can be improved compared with the device designated printing by which the job is immediately printed right after the job is input.

According to the embodiment a technique capable of easily controlling a method of performing the job based on a method of inputting the job is provided.

Although a preferred embodiment of the job performing control system the job performing system and the job performing control method has been specifically illustrated and described it is to be understood that minor modifications may be made therein without departing from the spirit and scope of the invention as defined by the claims.

For example the image forming apparatus is exemplified as an example of the job performing apparatus the job performing apparatus is not limited to the image forming apparatus and may be any apparatuses that perform a job such as a projection apparatus like a projector or the like a display apparatus that displays image data or the like. Further the structure of the job performing control system is not limited to that illustrated in and may be an apparatus that controls a job performing apparatus to perform the job or a system of a combination of a plurality of such apparatuses.

The individual constituents of the job performing system may be embodied by arbitrary combinations of hardware and software typified by a CPU of an arbitrary computer a memory a program loaded in the memory so as to embody the constituents illustrated in the drawings a storage unit for storing the program such as a hard disk and an interface for network connection. It may be understood by those skilled in the art that methods and devices for the embodiment allow various modifications.

The present invention can be implemented in any convenient form for example using dedicated hardware or a mixture of dedicated hardware and software. The present invention may be implemented as computer software implemented by one or more networked processing apparatuses. The network can comprise any conventional terrestrial or wireless communications network such as the Internet. The processing apparatuses can compromise any suitably programmed apparatuses such as a general purpose computer personal digital assistant mobile telephone such as a WAP or 3G compliant phone and so on. Since the present invention can be implemented as software each and every aspect of the present invention thus encompasses computer software implementable on a programmable device. The computer software can be provided to the programmable device using any storage medium for storing processor readable code such as a floppy disk hard disk CD ROM magnetic tape device or solid state memory device.

The present application is based on and claims the benefit of priority of Japanese Priority Application No. 2013 038764 filed on Feb. 28 2013 the entire contents of which are hereby incorporated by reference.

