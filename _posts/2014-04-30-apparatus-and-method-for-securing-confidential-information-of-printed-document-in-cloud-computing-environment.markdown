---

title: Apparatus and method for securing confidential information of printed document in cloud computing environment
abstract: The present invention provides a client terminal for receiving a cloud computing service from a cloud server that provides the cloud computing service. The client terminal includes a character string information extractor configured to extract character string information from document data requested to print in a printer that is connected to the client terminal, a confidential information detector configured to detect confidential information from the extracted character string information and a controller configured to prohibit printing of the document data including the character string of the detected confidential information or to mask at least one or more characters of the character string of the detected confidential information, with predetermined specific characters.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09036180&OS=09036180&RS=09036180
owner: KINGS INFORMATION & NETWORK CO., LTD.
number: 09036180
owner_city: Gyeonggi-do
owner_country: KR
publication_date: 20140430
---
This application claims the benefit of Korean Patent Application No. 10 2013 0048335 filed on Apr. 30 2013 which is hereby incorporated by reference as if fully set forth herein.

The present invention relates to an apparatus for securing confidential information of printed documents in a cloud computing environment and the method thereof. More specifically the present invention relates to an apparatus and method for securing confidential information of printed documents in a cloud computing environment capable of effectively securing confidential information of documents printed in a printer directly indirectly connected to a client terminal in a cloud computing environment in which the client terminal is connected a cloud server over a wired wireless communication network.

With the development of an information oriented society generally the economic value of information is highly estimated and it is becoming normal to collect and use personal information throughout our society.

Recently cases that personal information is leaked out and violated increase steadily and cases that confidential information and personal information of customers are leaked out increase in companies. Further there are illegal use of other s name and phone scam causing mental and financial damages to individuals.

In order to prevent the above problems companies construct integrated security solutions such as DRM Digital Right Management DLP Data Loss Prevention ECM Enterprise Contents Management etc. Security on printed documents also continues to be performed and method for the security includes a printed document control text log original log and so on.

A method for the printed document control generally includes a control method using a print processor and a control method using a virtual print.

First in the control method using a print processor a printout is controlled by sensing a print task during the procedure in which the print task spooled in a print spooler is transferred to a printer apparatus from a hard disk HD.

Second in the control method using a virtual printer a printout is controlled by sensing a print task of all applications upon performing a printing installed in a computer using print control modules built in each user s computer.

In such two control methods it is possible to know the printout information provided. However functions to detect and protect the personal information included in printed documents are not being studied yet.

Meanwhile in the text log method for a printed document information on a printed document is extracted using the aforementioned printed document control method and the log is generated. The overall printout situation can be managed through printout information by transmitting the log to a central management server to be managed. Although it is possible to identify the name date output PC and so on of the printed document using the log information it is not possible to identify whether personal information is included in the document.

Further in the original log method for a printed document a user generates a copy image for a printed document through the print control method when the print task is performed and transmits it to a central management server so as to be managed. The original image is used as an image to identify whether what print task has been performed on the printed document by the user. However the original image is prepared in a pictorial file format so that it is not possible to detect personal information.

As such the security method in the art does not identify the personal information so as to control the personal information. In the method for generating text log or original log it does not identify personal information when printing and can determine whether there is personal information through a log after printing.

That is in the above mentioned security methods in the art there is a high possibility that personal information is leaked out when printed documents including personal information is exposed out in public. Especially when personal history certificate license and diploma issued based on personal information and company s confidential documents were leaked out it is necessary to prepare the measures to protect them.

Meanwhile a recent computing environment is evolving toward a cloud computing architecture in which services are provided utilizing overall computing resources on a network when required by each terminal. A cloud computing service may be defined as on demand outsourcing service of computing resource over an information communication network such as the Internet.

In the cloud computing environment a service provider combines several data centers dispersed using a virtualization technology and provides services needed by users. A service user uses necessary computing resources such as application storage operation system and security by not installing them in each user s own terminal. Rather the service user selectively uses services on a virtual space generated by the virtualization technology at the user s desired time and as much as the user likes. The user pays for based on the amount of use of computing resources instead of purchasing each computing resource.

According to the cloud computing service there are advantages that users have access to a cloud network using a terminal capable of performing network access and basic arithmetic functions and then perform tasks requiring mass storage and high performance computing resource and are also provided with enhanced services.

However in case of downloading contents using the cloud computing service and outputting them problems may come up when the output is secret or confidential documents of a company not general documents.

For example when an inside authorizer has access to cloud computing service of the company and outputs confidential documents with malicious intent it is not possible to control the above problems in the existing system.

In view of the above the present invention provides a client terminal for effectively securing confidential informant printed in a printer directly indirectly connected to the client terminal in a cloud computing environment in which the client terminal has access to a cloud server over wired wireless communication network and a method thereof.

In accordance with an aspect of embodiments of the present invention there is provided a client terminal for receiving a cloud computing service from a cloud server that provides the cloud computing service and the client terminal includes a character string information extractor configured to extract character string information from document data requested to print in a printer that is connected to the client terminal a confidential information detector configured to detect confidential information from the extracted character string information and a controller configured to prohibit printing of the document data including the character string of the detected confidential information or to mask at least one or more characters of the character string of the detected confidential information with predetermined specific characters.

Further the character string information extractor is configured to extract character string information from the document data before the document data requested to print in the printer that is connected to the client terminal is transformed into a pictorial format.

Further the character string information extractor is configured to extract the character string information from the document data based on printing start end information for the document data.

Further the printing start end information is obtained using an AIP Application Programming Interface hooking.

Further the confidential information detector is configured to compare the character string information extracted with at least one preset confidential information pattern data thereby detecting confidential information.

Further in case that the number of the detected confidential information is more than a predetermined reference value the controller is configured to mask at least one or more characters of a character string of the detected confidential information with a predetermined specific character.

Further the controller is configured to prohibit printing of the document data in case that the number of the detected confidential information is more than a predetermined reference value.

Further the character string information extractor is configured to process the document data in a unit of page after extracting the character string information and the confidential information detector is configured to compare the processed document data with the at least one preset confidential information pattern data thereby detecting the confidential information.

Further the character string information extractor is configured to generate first hash information for a file downloaded through the cloud computing service of the cloud server and the confidential information detector is configured to generate second hash information for the document data and in case that there is hash information identical to the second hash information in the generated first hash information compare the processed document data with the at least one preset confidential information pattern data thereby detecting confidential information.

Further the confidential information detector is configured to detect confidential information from the processed document data by the character string information extractor and then perform a checksum thereby minimizing data errors.

In accordance with another aspect of embodiments of the present invention there is provided a method for securing confidential information of documents printed using a printer connected to a client terminal in a cloud computing environment in which the client terminal having a character string information extractor a confidential information detector and a controller is connected to a cloud server over a wired wireless communication network and the method includes extracting character string information from document data requested to print in the printer connected to the client terminal detecting confidential information from the extracted character string information and controlling to prohibit printing of the document data including the character string of the confidential information detected or to mask at least one or more characters of the character string of the detected confidential information with a predetermined specific character.

Further the extracting character string information includes extracting character string information from the document data before the document data requested to print in the printer connected to the client terminal is transformed into a pictorial format.

Further the extracting character string information includes extracting the character string information from the document data based on printing start end information for the document data.

Further the printing start end information is obtained using an AIP Application Programming Interface hooking.

Further the detecting confidential information includes comparing the extracted character string information with at least one preset confidential information pattern data thereby detecting confidential information.

Further in case that the number of the confidential information detected is more than a predetermined reference value the controlling includes masking at least one or more characters of the character string of the detected confidential information with a predetermined specific character.

Further the controlling includes blocking printing of the document data in case that the number of the detected confidential information is more than a predetermined reference value.

Further the extracting character string information includes processing the document data in a unit of page after extracting the character string information and the detecting confidential information includes comparing the processed document data with the at least one preset confidential information pattern data thereby detecting the confidential information.

Further the extracting character string information includes generating first hash information for a file downloaded through the cloud computing services of the cloud server and the detecting confidential information includes generating second hash information for the document data and in case that there is hash information identical to the second hash information in the first hash information generated comparing the document data processed with the at least one preset confidential information pattern data thereby detecting confidential information.

Further the detecting confidential information includes detecting confidential information from the document data produced by processing the character string information extractor and then performing a checksum thereby minimizing data errors.

According to the present invention it is possible to secure confidential information of documents printed in a printer connected directly indirectly to a client terminal in a cloud computing environment in which the client terminal is connected to a cloud server over a wired wireless communication network.

The advantages and features of exemplary embodiments of the present invention and methods of accomplishing them will be clearly understood from the following description of the embodiments taken in conjunction with the accompanying drawings. However the present invention is not limited to those embodiments and may be implemented in various forms. It should be noted that the embodiments are provided to make a full disclosure and also to allow those skilled in the art to know the full scope of the present invention. Therefore the present invention will be defined only by the scope of the appended claims. Similar reference numerals refer to the same or similar elements throughout the drawings. The term and or used herein includes all combinations of each of the items and one or more of them described herein.

Although the terms a first a second and the like are used herein to describe a variety of elements components and or sections it is understood that these elements components and or sections are not limited by these terms. The use of the terms is intended to distinguish the elements components or sections from other elements components or sections. Thus it is understood that a first element a first component or a first section mentioned below may be a second element a second component or a second section within the spirit of the present invention as well.

It should be noted that the terminologies used herein is merely intended to describe the embodiments and do not limit the scope of the present invention. In the present application the representation of the singular unless it clearly indicates in the phrase otherwise includes multiple representations. In the present application it should be understood that the terms includes or comprises and or including or comprising and variants thereof are used to specify the presence of other components steps operations and or elements mentioned herein but are not intended to exclude the possibility of the presence or supplement of one or more other components steps operations and or elements.

Unless there is another definition all terms including technical and scientific terminologies as used herein may be used as meaning that may be commonly understood by those having ordinary skill in the art. Further unless specifically defined clearly terms that are defined in advance commonly used are not to be construed ideally or excessively.

Further in the following description well known functions or constitutions will not be described in detail if they would obscure the subject matter of the present disclosure in unnecessary detail. Further the terminologies to be described below are defined in consideration of functions in the present disclosure and may vary depending on the intentions or practices of a user or an operator. Accordingly the definition may be made on the basis of the content throughout the specification.

First a technology called cloud computing means an Internet based cloud computing technology. The cloud computing has a hidden complex infrastructure as if the Internet is expressed as a cloud in a computer network topology and has a computing style by which IT related functions are provided as a service style. A user can make use of the services provided from the cloud computing by using the Internet.

In addition the cloud computing is a technology which employs the combination of the concept of various computing such as virtualized computing utility computing on demand computing and the like and a communication technology implements one virtual computer or service by integrating multiple data centers typically made up of a large number of computers using a virtualization technology and provides a variety of software security solutions and computing power to a user accessing thereto through on demand service.

In other words the cloud computing calls an on demand outsourcing service of IT resources over the Internet that enables a user to perform his her desired task in the way of storing programs or documents that were otherwise stored individually in a personal computer or a server of a company in an Internet based virtual server or storage and running a cloud application such as a web browser or the like using various terminals inclusive of a personal computer.

In this case the users may selectively pick and use the computing resources such as a cloud application storage OS security and the like at a user s desired time and as much as the users want and pay for based on the amount of use of computing resources. Although a full fledged cloud computing has not yet made researches on a cloud computing service service platform and virtual technology are actively ongoing under the leadership of the large companies such as including Google Microsoft and IBM.

And the term secreting information as used throughout the embodiments of the present invention may include personal related information for example a social security number telephone number mobile phone number e mail address driver s license number personal card number of information about individuals personal account number etc. as well as company related information for example corporation number business registration number corporate card number corporation account number etc. which may generally mean any information to be protected from individuals and companies.

On the other hand the typical printing process between a terminal such as a computer and a printer directly or indirectly connected to the computer will be described as follows.

First the process by the client terminal will be explained as follows. Upon receiving a printing instruction from the exterior the client terminal creates document information including the name of a document to be printed start and end of the document and start and end of pages records the created document information on the header of packet data and transmit it to the printer.

In response thereto the client terminal extracts the document information including a document name start and end of the document and start and end of pages creates new document information such as the name of a document to be printed total page page number being printed based on the extracted document information transforms the document information to a language recognizable by the printer and outputs the transformed document information to the print through a spooling process.

The process of creating the document information such as the name of a document to be printed total page and page number being printed will be described in terms of a printing architecture in detail as follows.

In an application program of a document processor installed in the client terminal in case where the document name is transferred as a parameter when StartDoc function is called from GDI Graphics Device Interface function for example GDI32.DLL the GDI transfers the document name to a printer driver while calling a function e.g. a DrvStartDoc function in case of Windows NT .

The printer driver transforms the document s name into the format that is recognizable by a PDL Printer Description Language translation program and stores it in a spooler.

Whenever each page starts in the application program a StartPage function is called from the GDI function. In this case the GDI calls a function corresponding to the StartPage function for example a DrvStartPage in case of Windows NT of the printer driver. Whenever the aforementioned function is called the printer driver counts the page number transforms the counted page number into the format that is recognizable by the PDL translation program and stores it in the spooler.

When the application program calls EndDoc function from the GDI function the printer driver calculates a total page of the document through the number of the counted pages until now transforms the total page into the format that is recognizable by the PDL translation program and stores it in the spooler.

Meanwhile the process by the printer will be described as follows. The printer receives the new document information from the client terminal and displays the name of the document currently being printed total page number page number being printed name of the document in a queue to be printed and total page number on an LCD panel.

In other words the printer extracts data corresponding to the document s name total page number page number being printed from PDL data received from the client terminal and transforms the extracted data into an image to be printed through the use of the PDL translation program. A print controller then sends the transformed image to a print engine so as to print the document.

As described above in the typical printing process between the client terminal and the printer the document processor records the data in a DC Device Context in the form of a picture using GDI32.DLL when printing it. At this time a character string is changed to a pictorial file format.

Based on the foregoing description the embodiment of the present invention is mainly characterized by extracting character string information of the document data that is requested to print based on printing start end information using an API Application Programming Interface hooking technique before the character string of the document data that is requested to print is changed to the pictorial file format.

Referring to a security system of confidential information of printed documents in a cloud computing environment in accordance with an embodiment of the present invention serves as a system for securing the confidential information of documents printed using a printer directly indirectly connected to a client terminal in a cloud computing environment. The security system largely includes a cloud server and a client terminal and a printer that are connected to the cloud server over wired wireless communication network .

Here the cloud server performs a function to provide a cloud computing service in response to a request from the client terminal .

In other words the cloud server is responsible for providing the cloud computing service to the client terminal and providing computing resources requested from the client terminal over the wired wireless network with the client terminal. The cloud server also provides a computing service that allows the client terminal to use any of devices requested by the client terminal.

The cloud server thus includes a plurality of storages that stores file received from a business operator a content provider which provides a large amount of data for example such as an application program file game program file text data file document file picture file music file video file bar code file etc.

Meanwhile the wired wireless network may be a wired wireless network or the Internet. The Internet may refer to a global open computer network architecture that provides TCP IP protocol and several services on the upper layer i.e. HTTP Hyper Text Transfer Protocol Telnet FPT File Transfer Protocol DNS Domain Name System SMTP Simple Mail Transfer Protocol SNMP Simple Network Management Protocol NFS Network File Service NIS Network Information Service and the like and provides environments that enable the client terminal to access the cloud server and or the printer . The Internet may be the wired or wireless Internet or a core network integrated with a wired public network wireless mobile communication network or the mobile Internet.

The client terminal may be typically a personal computer PC for example a desktop PC notebook PC or the like but is not limited thereto and may be any type of wired wireless communication device capable of accessing the cloud server and or the printer over the wired wireless network to receive the cloud computing service and printing various document data.

For example the client terminal may mean any wired wireless terminal having a user interface for accessing to the cloud server and or the printer and Windows OS installed therein such as a Palm PC Personal Computer personal digital assistant PDA smart phone WAP phone wireless application protocol phone mobile gaming machine e.g. mobile play station that can communicate with the cloud server and or the printer over the wired wireless network .

The client terminal includes a character string information extractor a confidential information detector a controller and a hash information DB which are the main components to secure confidential information of printed documents in a cloud computing environment.

The character string information extractor performs functions to generate hash information for a file downloaded through a cloud computing service of the cloud server to make them as a table and to store them in the hash information DB .

Further the character string information extractor performs functions of monitoring document data requested to print using a document processor of the client terminal through an API Application Programming Interface generating hash information for document data requested to print extracting character string information based on printing start end information and processing the document data in a unit of the page.

In other words the character string information extractor calls a printout related GDI32.DLL file of the document processor included in the client terminal using the API hooking monitors a StartDoc and EndDoc functions indicating printing start end in real time and extracts character string information using at least one character string related function of character string related functions for example DrawTextA DrawTextW DrawTextExA DrawTextExW ExtTextOutA ExtTextOutW TextOutA TextOutW PolyTextOut TabbedTextOut and so on thereby extracting character string information of the document data requested to print.

Further it is preferred that the character string information extractor stores the processed document data as a file and transfers it to the confidential information detector .

In case that there is hash information identical to the hash information for the document data requested to print in the hash information DB the confidential information detector performs a function to compare the document data processed by the character string information extractor with at least one preset confidential information pattern data thereby detecting confidential information.

The controller performs a function to control the document processor of the client terminal so as to analyze the type and number of the detected confidential information and to block or secure the document data requested to print according to a predetermined security policy.

The confidential information detector also detects the confidential information from the document data processed by the character string information extractor and perform a checksum thereby minimizing data errors.

Preferably the controller may control the document processor of the client terminal to block printing of the document data requested to print according to the predetermined security policy in case that the number of the confidential information detected is more than a predetermined reference value and to mask some characters for example and so on of the character string of the confidential information with predetermined specific characters in case that the number of the confidential information detected is less than the predetermined reference value thereby securing the confidential information.

Meanwhile it is preferred that the confidential information includes at least one of an identification number telephone number card number corporate registration number business registration number account number e mail address passport number mobile phone number or driver s license number.

The hash information DB performs functions to store and manage the hash information for files generated by the character string information extractor by making it as a table. The hash information DB is preferably included in the client terminal but it is not limited thereto. The hash information DB may be substituted with a memory included in the terminal or may be embodied by a separate database DB server or storage medium.

Hereinafter a detailed description will be given to a method for securing confidential information of documents printed using a printer directly indirectly connected to a client terminal in a cloud computing environment in accordance with an embodiment of the present invention.

Referring to first in case that there is a file downloaded from the cloud server through a character string information extractor included in a client terminal hash information for the file is generated and then made as a table thereby being stored in a hash information DB at Block S.

Next when a printing request is received from a document processor included in the client terminal the character string information extractor applied in an embodiment of the present invention is switched to a monitoring mode in order to detect a character string.

In other words the character string information extractor monitors the character data requested to print in the document processor of the client terminal in real time using an API Application Programming Interface hooking at Block S.

Subsequently the character string information extractor generates hash information for the document data requested to print extracts character string information based on printing start end information and then processes the document data in a unit of page at Block S.

Specifically in order to extract character string information of the document data requested to print the character string information extractor calls a printout related GDI32.DLL file of a document processor included in a client terminal using an API hooking and monitors a StartDoc and EndDoc functions indicating printing start end in real time. Then the character string information extractor extracts character string information using at least one character string related function of character string related functions indicating timing points to extract the character string for example DrawTextA DrawTextW DrawTextExA DrawTextExW ExtTextOutA ExtTextOutW TextOutA TextOutW PolyTextOut TabbedTextOut etc. stores the document data processed in a unit of page as a file for example DocName.txt and then transfers the file to a confidential information detector . Simultaneously the character string information extractor switches to a normal mode.

Next the confidential information detector included in the client terminal compares hash information for the document data requested to print with hash information previously stored in the hash information DB in advance to make a determination thereof at Block S.

Thereafter in case that there is hash information identical to the hash information for the document data requested to print in the hash information DB as a result of the comparison at Block S the confidential information detector compares the document data processed at Block S with at least one preset confidential information pattern data thereby detecting confidential information at Block S.

The confidential information detector compares a file including the document data processed with the predetermined confidential information pattern data thereby detecting confidential information matched to the confidential information pattern. As such when the confidential information matched to the confidential information pattern is detected it may be possible to minimize error check ratio and excessive check ratio by checking the checksum. It is preferred to store the detection result in an int file format.

In addition a key value of jumin6 has spaces which are used for extracting irregular character string. Since each document has a different identification number type it is preferred to provide a variety of patterns. Likewise other personal information may also be configured in patterns matched to their types.

After that the controller in the client terminal controls a document processor of the client terminal to analyze the kind and number of the confidential information detected at Block S and prohibits or secure the document data requested to print according to a security policy predetermined at Block S.

Specifically in case that the number of the confidential information detected at Block S is more than a reference value predetermined it is prohibited to print the document data requested to print in accordance with the predetermined security policy.

For example in case that a security policy is set to prohibit the printing only when ten 10 or more identification numbers are included it is controlled to prohibit the printing when the number of the identification number of a detection result log file is equal to or more than ten and it is controlled to permit the printing when the number of the identification number is less than ten.

In this regard in order to accomplish the control the security policy does not return a success Return Success but returns an output failure code negative number to the document processor Return Fail by calling EndDoc function in the EndDoc function normally.

Meanwhile in order to secure confidential information after permitting the printing in accordance with the security policy the confidential information character string is masked with specific characters for example and so on as illustrated in .

That is in case where the number of confidential information detected at Block S is less than a predetermined reference value the controller controls a document processor of a client terminal to mask some characters of the confidential information character string with a predetermined specific character and secure the confidential information.

The procedure to mask will be described in more detail as follows. When functions related to the first character string for example DrawTextA DrawTextW DrawTextExA DrawTextExW ExtTextOutA ExtTextOutW TextOutA TextOutW PolyTextOut TabbedTextOut and so on are called it is confirmed whether there is confidential information for a document string. If the document string includes the confidential information the document string is masked and then stored in the previous character string.

From the second or later call it is determined whether there is confidential information by combining the previous character string value and the current character string value. It is because the confidential information may not identify when the confidential information is called separately in a printing call procedure. When the masking is completed the character string is returned.

Meanwhile it is preferred that the confidential information comprises at least one of identification number telephone number card number corporation number business registration number account number e mail address passport number mobile phone number or driver s license number for example.

Additionally after Block S the character string information extractor in the client terminal may further perform additional procedures of storing the document data processed as a file and transferring the file to the confidential information detector .

Furthermore after Block S the confidential information detector in the client terminal may further perform procedures of detecting confidential information from document data processed in the character string information extractor and then performing a checksum thereby minimizing data errors.

Meanwhile the method for protecting confidential information on the printed document in a cloud computing environment in accordance with an embodiment of the present invention may also be implemented as a computer readable code in a computer readable recording medium. The computer readable recording medium includes any type of recording devices in which data readable by a computer system is stored.

For example the computer readable recording medium includes a ROM RAM CD ROM magnetic tape hard disk floppy disk mobile storage device non volatile memory flash memory optical data storage device and the like.

Also the computer readable recording medium may be stored and performed in the form of codes that are distributed to computer systems connected via a computer communication network and can be read in a distribution method may be stored and executed in the computer readable recording medium.

While embodiments of the system and method for securing confidential information of printed documents in a cloud computing environment in accordance with the present invention have been described the present invention is not limited thereto. Various modifications can be made to the above described exemplary embodiments of the present invention without departing from the spirit or scope of the invention and are intended to be embraced by the scope of the present invention.

