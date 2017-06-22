---

title: Image forming system, method of controlling image forming apparatus by using messenger application of mobile device, and the mobile device for performing the method
abstract: An image forming system to control an image forming apparatus by using a messenger application, a mobile device, and a method are provided. The image forming system includes a mobile device to activate a chat user interface to interface with an account of the image forming apparatus on the messenger application, and sending user messages to control a printing function of the image forming apparatus, a cloud server to receive the user messages from a messenger server, providing response messages of the account of the image forming apparatus in response to the user messages, and communicating with the mobile device in a conversational manner, thus controlling the printing of the image forming apparatus, and an image forming apparatus whose printing is controlled by the cloud server based on the user messages or providing monitoring information of a current status.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432527&OS=09432527&RS=09432527
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09432527
owner_city: Suwon-Si
owner_country: KR
publication_date: 20141204
---
This application is related to and claims the priority benefit of Korean Patent Application No. 10 2013 0156641 filed on Dec. 16 2013 in the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

One or more embodiments relate to a method of controlling an image forming apparatus by using a message application of a mobile device and a mobile device to perform the method.

Users communicate by using for example a home page an e mail etc. as various information transfer media. However users may not communicate with a target user in real time using such forms of communication. An instant messenger i.e. a messenger may be useful for transferring information in real time via the Internet. The instant messenger attempts to transfer a simple message between users in real time. When the messenger is used two users may chat in real time through texts transferred as if they personally converse with each other. As the messenger instantly transfers input content of a message the real time feature of the message is regarded as being important. A messenger application may provide a function of transmitting emoticons flashcons giftcons etc. to a conversation participant through a conversation window or a chat window or a function of transmitting a file using the conversation window as well as transferring a message.

One or more embodiments include a method of controlling an image forming apparatus by using a message application of a mobile device and the mobile device to perform the method.

One or more embodiments include a computer readable recording medium having recorded thereon a program for executing the method.

Additional aspects will be set forth in part in the description which follows and in part will be apparent from the description or may be learned by practice of the presented embodiments.

According to one or more embodiments a mobile device to control an image forming apparatus by using a messenger application includes a user interface unit to activate a chat user interface to interface with an account of the image forming apparatus corresponding to the image forming apparatus on the messenger application a network interface unit to send user messages to control a printing function of the image forming apparatus which are input through the activated chat user interface and a control unit to control the printing function of the image forming apparatus by communicating with the image forming apparatus in a conversational manner according to response messages of the account of the image forming apparatus in response to the input user messages.

According to one or more embodiments a method of controlling an image forming apparatus by using a messenger application of a mobile device includes activating a chat user interface to interface with an account of the image forming apparatus corresponding to the image forming apparatus on the messenger application sending user messages to control a printing function of the image forming apparatus which are input through the activated chat user interface and controlling the printing function of the image forming apparatus by communicating with the image forming apparatus in a conversational manner according to response messages of the account of the image forming apparatus in response to the input user messages.

According to one or more embodiments a non transitory computer readable recording medium having embodied thereon a program for executing the method described above is included.

According to one or more embodiments a image forming system to control an image forming apparatus by using a messenger application includes a mobile device to activate a chat user interface to interface with an account of the image forming apparatus on the messenger application and sending user messages to control a printing function of the image forming apparatus a cloud server to receive the user messages from a messenger server providing response messages of the account of the image forming apparatus in response to the user messages and communicating with the mobile device in a conversational manner thus controlling the printing function of the image forming apparatus and an image forming apparatus whose printing function is controlled by the cloud server based on the user messages or providing monitoring information of a current status.

Reference will now be made in detail to embodiments examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to like elements throughout. The present embodiments may have different forms and should not be construed as being limited to the descriptions set forth herein. Accordingly the embodiments are merely described below by referring to the figures to explain aspects of the present description. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

Although the mobile device the message server the cloud server and the image forming apparatus are provided to the image forming system of for convenience of description the present embodiment is not limited thereto. One or more various types of mobile devices message servers cloud servers and image forming apparatuses may be provided.

In other words exemplary hardware components are illustrated in order not to obscure the characteristics of the embodiment in . However it will be understood by one of ordinary skill in the art that general use hardware components for example an access point AP a network hub etc. other than the hardware components shown in may also be provided.

The image forming apparatus may be an individual device such as a printer a scanner a copier or a facsimile or the like or may correspond to a multifunction product MFP that incorporates various functions of the above different devices into one device.

The mobile device may correspond to a device such as a smart phone a tablet device a personal digital assistant PDA a notebook a personal computer PC or the like.

The mobile device may correspond to a device in which commercial messenger applications such as Kakao Talk WhatsApp Facebook Messenger and the like may be installed.

The messenger server may correspond to a server that is run by a provider to provide types of commercial messenger applications.

The cloud server which is a server that manages the image forming apparatus mediates messages transmitted and received between the image forming apparatus and the mobile device via the messenger server .

Each of the mobile devices the message servers the cloud servers and the image forming apparatuses that are provided to the image forming system may have wired and or wireless communication functions. Thus each of the mobile devices the message servers the cloud servers and the image forming apparatuses may utilize the wired and or wireless communication functions that are supported by a device itself to form a wired and or wireless network that is connected to each other. That is as long as the image forming system connected over the wired and or wireless network is established it will be understood by one of ordinary skill in the art that various y wired or wireless networks may be used 

When the mobile device executes the messenger application in the image forming system the mobile device may control the image forming apparatus by using a chatting method of conversing by transmitting receiving messages between a user s account and an account of the image forming apparatus corresponding to the image forming apparatus through the executed messenger application. The image forming apparatus pushes and provides information regarding a current status of the image forming apparatus to the messenger application of the mobile device in a message form and thus a user of the mobile device may more easily manage the current status of the image forming apparatus .

The bot server communicates with the messenger server that provides a service relating to a messenger application to transmit and receive messages.

The image forming apparatus may not actively compose a message like a user because the image forming apparatus itself is a machine. Thus the bot server parses user messages transmitted from the mobile device by using an account of the image forming apparatus corresponding to the image forming apparatus and generate response messages of the account of the image forming apparatus corresponding to the user messages. That is the bot server automatically feeds back the response messages to the user messages in place of the image forming apparatus by using a messenger application of the mobile device .

A bot server registration configuration of the messenger server registers and manages the bot server to be identified with the messenger server .

A relay interface configuration and a request received message configuration are divided according to which communication method is to be applied to the bot server .

The messenger server includes the relay interface configuration so that the messenger server may send e.g. automatically send a user message transmitted from a messenger application of the mobile device to an implement relay interface configuration of the bot server .

The messenger server which is an open application programming interface API may respond to a message according to a request of a receive message fetcher configuration . The bot server leadingly operates as a fetcher that fetches the user message received by the messenger server .

When the user message is sent from the messenger server to the bot server as described above the bot server parses the user message and internally generates a response message in response to the user message. A message sender configuration of the bot server calls the open API of the messenger server to send the response message to a send message configuration of the messenger server so that the messenger server is requested to send the response message to the messenger application of the mobile device .

The bot server separates texts included in the user message sent from the messenger server according to words. The words separated from the texts correspond to tokens. The tokens may be mapped to actions defined in the action map.

For example when a token or printer is included in the texts included in the user message the bot server parses the token to be mapped to an action PRINTER . When a token is included in the texts included in the user message the bot server parses the token to be mapped to an action SEARCH .

In other words the bot server construes meaning of the texts included in the user message and a user converts the meaning into a control command for the image forming apparatus .

Referring to the print service server controls and manages the image forming apparatus provided to the image forming system . Although only one image forming apparatus is provided in the present embodiment for convenience of description various image forming apparatuses may be provided to the image forming system other than the image forming apparatus . That is the print service server may control and manage all image forming apparatuses provided to the image forming system .

The print service server registers identification information of the image forming apparatus provided to the image forming system to control an operation of the image forming apparatus . The print service server maps and registers user identification information with respect to information regarding the image forming apparatus .

Referring to the user may access a web page provided by an embedded web server of the image forming apparatus to register the identification information of the image forming apparatus and the user.

The user may input their e mail address and information regarding the image forming apparatus that are to be registered by using the web page . That is for example the user may input their e mail address jaeyoung.soh samsung.com and designate Printer A R4 19F as the image forming apparatus that is to be mapped to the e mail address jaeyoung.soh samsung.com .

When the user clicks a registration button on the web page the user maps and registers information regarding the e mail address jaeyoung.soh samsung.com and the image forming apparatus Printer A R4 19F to the print service server as user management information and printer management information respectively.

The user may register user identification information by using a user interface UI panel of the image forming apparatus .

The user may input information regarding their e mail address in the image forming apparatus Printer A R4 19F . That is for example when the user inputs their e mail address jaeyoung.soh samsung.com and clicks the registration button the information regarding the e mail address jaeyoung.soh samsung.com and the image forming apparatus Printer A R4 19F may be mapped and registered to the print service server as the user management information and the printer management information respectively.

Referring to the print service server may control the image forming apparatus or manage a status of the image forming apparatus according to actions that are indicated by user messages parsed by the bot server .

For example when the actions that are indicated by the user messages parsed by the bot server correspond to the actions PRINTER and SEARCH the print service server may return a list of image forming apparatuses that are currently connected to a network of the image forming system back to the bot server .

Alternatively when the actions that are indicated by the user messages parsed by the bot server correspond to an action PRINT the print service server may control the image forming apparatus to perform a printing function.

When the actions that are indicated by the user messages parsed by the bot server correspond to the action PRINT the print service server may perform rendering for generating printing data as a cloud printing function and send the rendered printing data to the image forming apparatus 

Alternatively when the actions that are indicated by the user messages parsed by the bot server correspond to actions RESOURCE and CHECK the print service server may return information regarding an amount of toner currently remaining in the image forming apparatus back to the bot server .

That is the messenger server the cloud server and the image forming apparatus process the user messages transmitted from the mobile device and send response messages in response to the user messages to the mobile device again in order to allow a user account and an account of the image forming apparatus to automatically converse with each other on the messenger application.

Referring to the mobile device includes a user interface unit a control unit and a network interface unit according to an embodiment. However it will be understood by one of ordinary skill in the art that general use hardware components other than the hardware components shown in may also be provided.

The user interface unit which is a hardware component including an input apparatus or a display apparatus displays information to a user of the mobile device or receives information from the user. The user interface unit may include some or all individual apparatuses that interface with the user such as a display screen a speaker a key pad a keyboard a mouse and the like and may also include a touch screen etc.

The user may execute a messenger application via the user interface unit . The user interface unit displays information displayed by the executed messenger application to the user. The user may input messages to the messenger application via the user interface unit to chat with other users or an account of the image forming apparatus .

The control unit is a hardware component that controls a general operation and function of the mobile device . The control unit controls an execution of the message application installed in the mobile device .

The control unit may be implemented as at least one processor such as a central processing unit CPU an application processor AP etc.

The network interface unit that may support wired communication 2G mobile communication 3G mobile communication 4G mobile communication etc. is a hardware component that supports a wired or wireless communication function. The network interface unit may support wireless communication such as Wi Fi Wi Fi Direct near field communication NFC Bluetooth etc. and wired communication 2G mobile communication 3G mobile communication 4G mobile communication etc. via Ethernet.

When the user requests that a chat window with an account of the image forming apparatus corresponding to the image forming apparatus be opened on the messenger application the user interface unit activates a chat UI to interface with the account of the image forming apparatus on the messenger application.

The activated chat UI may correspond to a chat window for chatting with the account of the image forming apparatus one to one. Alternatively the activated chat UI may correspond to a chat window for chatting with the cloud server that manages the account of the image forming apparatus and accounts of other image forming apparatuses. Alternatively the activated chat UI may correspond to a group chat window for chatting with each of the accounts of other image forming apparatuses one to N where N is a natural number equal to or greater than 2 .

The network interface unit sends user messages to control a printing function of the image forming apparatus that are input via the activated chat UI. The messenger application may correspond to an application provided by the messenger server as described above and thus the user messages may be preferentially sent to the messenger server .

For example when a message including an image that is to be printed is input via the activated chat UI the network interface unit sends the image that is to be printed to the image forming apparatus . The image that is to be printed may be sent to the image forming apparatus via the messenger server and the cloud server .

The control unit communicates with the image forming apparatus for example in a conversational manner according to response messages of the account of the image forming apparatus in response to the input user messages thereby controlling the printing function of the image forming apparatus .

The account of the image forming apparatus may be managed by the bot server . The response messages may be generated by the bot server and sent to the mobile device .

That is the user messages and the response messages may be transmitted and received via mediation of the cloud server that manages the image forming apparatus .

Referring to Printer A and a chat window are activated in the mobile device that is currently executing a messenger application.

A user may input a user message printer search via the user interface to send the user message printer search to an account of Printer A.

The input user message printer search may be sent to the messenger server via the network interface unit . The messenger server as described with reference to above sends the user message printer search to the bot server .

The bot server parses and converts the user message printer search into actions corresponding to the user message printer search by using the action map for example of .

The print service server collects information regarding Printer A and Printer B that are currently connected to the print service server for example based on the actions PRINTER and SEARCH corresponding to the user message printer search .

The print service server transmits the information regarding the Printer A and Printer B to the bot server . The bot server returns a response message such as Select a printer. 1. Printer A 19F 2. Printer B 35F based on the information regarding the Printer A and Printer B back to the mobile device via the messenger sever .

When the response message regarding a list of image forming apparatuses is returned the user may select a desired object from the list of image forming apparatuses. For example the user may input a user message 1 via the user interface unit to select Printer A.

Thereafter the messenger server the bot server and the print service server send a message of an image that was sent from the user and is to be printed to the image forming apparatus Printer A to allow the image forming apparatus to perform a printing function with respect to the image.

The messenger server the bot server and the print service server may additionally send response messages that guide a printing process to the mobile device during the printing process. The user interface unit may display the response messages on the messenger application.

Referring to A and B a user of the mobile device uses an e mail address sadman samsung.com and a user of a mobile device uses an e mail address kasey samsung.com .

Printer A the image forming apparatus for example may be already registered to the print service server . Printer B not shown for example may be already registered to the print service server .

In operation the mobile device receives a user message printer search from the user. The user message printer search is sent to the messenger server via the network interface unit . The messenger server sends the user message printer search to the bot server .

In operation the bot server parses and converts the user message printer search into actions corresponding to the user message printer search by using the action map of .

The bot server converts a response message that inquires about whose user account is used to log in to the messenger server before transferring the actions PRINTER and SEARCH corresponding to the user message printer search to the print service server . The messenger server sends a response message let us know an account to be used to the mobile device .

In operation the mobile device receives a user message of a user account kasey samsung.com from the user. The user message of the user account kasey samsung.com is sent to the messenger server via the network interface unit . The messenger server sends the user message of the user account kasey samsung.com to the bot server .

In operation the bot server requests the print service server to transfer a list of image forming apparatuses that are to be mapped to the user account kasey samsung.com . The print service server returns information regarding the list of Printer A the image forming apparatus and Printer B not shown that are currently connected to the print service server and are mapped to kasey samsung.com back to the bot server .

In operation the bot server returns a response message such as Select a printer. 1. Printer A 19F 2. Printer B 35F based on the information regarding the list of the Printer A and Printer B back to the messenger sever . The messenger server sends the response message such as Select a printer. 1. Printer A 19F 2. Printer B 35F to the mobile device .

In operation the mobile device receives a user message 1 for selecting Printer A the image forming apparatus from the user. The user message 1 is sent to the messenger server via the network interface unit . The messenger server sends the user message 1 to the bot server .

In operation the bot server parses and converts the user message 1 into actions corresponding to the user message 1 by using the action map of .

The bot server returns a response message indicating that an action SELECTION corresponding to the user message 1 is determined to the messenger server . The messenger server sends a response message Printer A is selected. Send contents to be printed to the mobile device .

In operation the mobile device receives a user message regarding an image that is to be printed from the user. The user message including the image is sent to the messenger server via the network interface unit . The messenger server sends the user message including the image to the bot server .

In operation the print service server returns information regarding the user account kasey samsung.com back to the bot server . This is because the user account sadman samsung.com of the mobile device may be different from the user account kasey samsung.com mapped to the Printer A. Thus authentication of the mobile device having the user account kasey samsung.com may be required.

In operation the bot server returns a response message Waiting for use authentication of Printer A informing that authentication of the mobile device is required back to the messenger server . The messenger server sends the response message Waiting for use authentication of Printer A to the mobile device .

In operation the bot server returns a response message Sadman requested for printing of Printer A. Will you accept 1. Yes 2. No informing that authentication of the mobile device is required back to the messenger server . The messenger server sends the response message Sadman requested for printing of Printer A. Will you accept 1. Yes 2. No to the mobile device having the user account kasey samsung.com .

In operation the mobile device receives the user message 1 for authenticating use of Printer A the image forming apparatus from another user. The user message 1 is sent to the messenger server via the network interface unit . The messenger server sends the user message 1 to the bot server .

In operation Printer A is completely authorized by the user of the mobile device and thus the bot server transmits the image that is to be printed to the print service server .

The print service server renders the image that is to be printed to generate and transmit printing data to Printer A the image forming apparatus .

Printer A the image forming apparatus performs the printing function thereof based on the printing data thereby printing the image.

In operation the image is completely printed by Printer A the image forming apparatus and thus the bot server returns a response message Authenticated. Printing is complete. back to the messenger server . The messenger server sends the response message Authenticated. Printing is complete. to the mobile device .

Through operations through above the mobile device may control the printing function of Printer A the image forming apparatus for printing the image by using the messenger application.

Printer A the image forming apparatus is already registered to the print service server . Printer B not shown is already registered to the print service server .

In operation the mobile device receives a user message printer search from the user. The user message printer search is sent to the messenger server via the network interface unit . The messenger server sends the user message printer search to the bot server .

In operation the bot server parses and converts the user message printer search into actions corresponding to the user message printer search by using the action map of .

The bot server converts a response message that inquires about whose user account is used to log in to the messenger server before transferring the actions PRINTER and SEARCH corresponding to the user message printer search to the print service server . The messenger server sends a response message let us know an account to be used to the mobile device .

In operation the mobile device receives a user message of a user account kasey samsung.com from the user. The user message of the user account kasey samsung.com is sent to the messenger server via the network interface unit . The messenger server sends the user message of the user account kasey samsung.com to the bot server .

In operation the bot server requests the print service server to transfer a list of image forming apparatuses that are to be mapped to the user account kasey samsung.com . The print service server returns information regarding the list of Printer A the image forming apparatus and Printer B not shown that are currently connected to the print service server and are mapped to kasey samsung.com back to the bot server .

In operation the bot server returns a response message such as Select a printer. 1. Printer A 19F 2. Printer B 35F based on the information regarding the list of the Printer A the image forming apparatus and Printer B back to the messenger sever . The messenger server sends the response message such as Select a printer. 1. Printer A 19F 2. Printer B 35F to the mobile device .

In operation the mobile device receives a user message 1 for selecting Printer A the image forming apparatus from the user. The user message 1 is sent to the messenger server via the network interface unit . The messenger server sends the user message 1 to the bot server .

In operation the bot server parses and converts the user message 1 into actions corresponding to the user message 1 by using the action map of .

The bot server returns a response message indicating that an action SELECTION corresponding to the user message 1 is determined to the messenger server . The messenger server sends a response message Printer A is selected. to the mobile device .

In operation the bot server requests the print service server for information regarding a status of Printer A the image forming apparatus . The print service server returns information indicating that Printer A the image forming apparatus is currently a paper shortage and a paper jam. has occurred back to the bot server .

In operation the bot server returns a response message there is no paper to the messenger server . The messenger server sends the response message there is no paper to the mobile device .

Accordingly the user supplies more paper to Printer A the image forming apparatus thereby managing the status of Printer A the image forming apparatus .

In operation the bot server returns a response message jam has occurred back to the messenger server . The messenger server sends the response message jam has occurred to the mobile device .

Accordingly the user removes a jammed paper from Printer A the image forming apparatus thereby managing the status of Printer A the image forming apparatus .

In operation the mobile device receives a user message Check toner status from the user. The user message Check toner status is sent to the messenger server via the network interface unit . The messenger server sends the user message Check toner status to the bot server .

The bot server parses and converts the user message Check toner status into the actions RESOURCE and CHECK corresponding to the user message Check toner status by using the action map of .

In operation the bot server requests the print service server for information regarding a toner status of Printer A the image forming apparatus . The print service server returns information indicating that 90 of black toner currently remains in Printer A the image forming apparatus back to the bot server .

In operation the bot server returns a response message 90 of black is remaining to the messenger server . The messenger server sends the response message 90 of black is remaining to the mobile device .

Accordingly the user determines the toner status of Printer A the image forming apparatus thereby managing the status of Printer A the image forming apparatus .

In operation the mobile device receives a user message Check fax status from the user. The user message Check fax status is sent to the messenger server via the network interface unit . The messenger server sends the user message Check fax status to the bot server .

The bot server parses and converts the user message Check fax status into the actions FAX and CHECK corresponding to the user message Check fax status by using the action map of .

In operation the bot server requests the print service server for information regarding a fax status of Printer A the image forming apparatus . The print service server returns information indicating that a fax function of Printer A the image forming apparatus is currently deactivated back to the bot server .

In operation the bot server returns a response message fax function is off to the messenger server . The messenger server sends the response message fax function is off to the mobile device .

Accordingly the user determines the fax status of Printer A the image forming apparatus thereby managing the status of Printer A the image forming apparatus .

Through operations through stated above the mobile device may manage the status of Printer A the image forming apparatus by using the messenger application.

Referring to Printer A the image forming apparatus may push a message indicating monitoring information to the messenger application of the mobile device . For example when Printer A the image forming apparatus is short of black toner Printer A the image forming apparatus may send a push message 4 of black toner currently remains in Printer A to the mobile device . That is the monitoring information of a status of Printer A the image forming apparatus may be pushed to the mobile device by using the messenger application like a message sent from an outside individual.

In other words the print service server may transfer the monitoring information of the status of Printer A the image forming apparatus to the bot server regularly or when an event occurs in Printer A the image forming apparatus . Accordingly the bot server may send the message including the monitoring information to the mobile device via the messenger server .

In operation the user interface unit of the mobile device activates a chat UI to interface with an account of the image forming apparatus corresponding to the image forming apparatus on the messenger application.

In operation the network interface unit of the mobile device sends user messages to control a printing function of the image forming apparatus that are input through the activated chat UI.

In operation the control unit of the mobile device communicates with the image forming apparatus in a conversational manner according to response messages of the account of the image forming apparatus in response to the input user messages thereby controlling the printing function of the image forming apparatus .

In operation the messenger server automatically sends the user message to the bot server as illustrated for example by path of .

Alternatively in operation the bot server inquires whether the messenger server currently receives a message from the mobile device as illustrated for example by path of . If the messenger server currently receives the message from the mobile device operation is performed.

Both operations and or one of them may be performed according to types of interfaces of the messenger server and the bot server .

In operation the bot server parses the user message. The bot server may parse texts included in the user message as tokens.

In operation the bot server designates actions corresponding to the user message by using an action map. The bot server may map the tokens parsed from the user message to the actions by using the action map.

In operation the bot server determines whether the user message is a printing command. If the user message is the printing command operation is performed. However if the user message does not mean the printing command operation A of is performed.

In operation the bot server determines whether the user message includes an image that is to be printed. If the user message includes the image operation is performed. However if the user message does not include the image operation is performed again in order to input a user message including the image.

In operation the print service server renders the image included in the user message to generate printing data. That is the print service server performs cloud rendering.

In operation the bot server determines whether a user message is a message that requests monitoring information. If the user message is the message that requests the monitoring information operation is performed. If not operation is performed.

In operation the print service server monitors the status of the image forming apparatus to collect the monitoring information.

In operation the bot server generates a response message including current monitoring information based on the collected monitoring information.

In operation the bot server generates a response message that guides or explains actions mapped by using an action map as a result of parsing the user message.

In operation the bot server sends the response message to the messenger server and the messenger server sends the response message to the mobile device .

According to the one or more embodiments various types of commercial messenger applications that are installed in a mobile device may be used to control a printing function of an image forming apparatus or monitor information regarding a status of the image forming apparatus by using a method of chatting with the image forming apparatus thereby more conveniently and intuitively utilizing a function of the image forming apparatus or managing the image forming apparatus.

In addition an exemplary embodiment may be implemented through computer readable code instructions in on a medium e.g. a computer readable medium to control at least one processing element to implement any above described embodiment. The medium can correspond to another medium media permitting the storage and or transmission of the computer readable code. The computer readable code can be recorded transferred on a medium in a variety of ways with examples of the medium including recording media such as magnetic storage media e.g. ROM floppy disks hard disks etc. and optical recording media e.g. CD ROMs or DVDs and transmission media such as Internet transmission media.

It should be understood that the exemplary embodiments described herein should be considered in a descriptive sense only and not for purposes of limitation. Descriptions of features or aspects within each embodiment should typically be considered as available for other similar features or aspects in other embodiments.

While one or more embodiments have been described with reference to the figures it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope as defined by the following claims.

