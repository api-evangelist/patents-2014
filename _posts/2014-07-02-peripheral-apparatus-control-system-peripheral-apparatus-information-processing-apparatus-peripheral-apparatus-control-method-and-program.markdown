---

title: Peripheral apparatus control system, peripheral apparatus, information processing apparatus, peripheral apparatus control method, and program
abstract: In a network printing system utilizing WSD Print Service, a highly operable peripheral apparatus control system that utilizes a mass storage device and a low-cost shared printer that does not include a function for requesting print data to an information processing apparatus is provided. The peripheral apparatus control system includes an information processing apparatus and a peripheral apparatus mutually connected via a network. The information processing apparatus inputs a job request and a reservation request to the peripheral apparatus. The peripheral apparatus includes a first measurement unit that measures the difference between reception timings of the job request and the reservation request. If the difference between the reception timings is equal to or less than a first predetermined time, a reservation ID is input and a reservation of the job request is accepted.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09176684&OS=09176684&RS=09176684
owner: CANON KABUSHIKI KAISHA
number: 09176684
owner_city: Tokyo
owner_country: JP
publication_date: 20140702
---
This application is a continuation of U.S. patent application Ser. No. 12 911 618 filed Oct. 25 2010 which claims the benefit of and priority to Japanese Patent Application No. 2009 270099 filed Nov. 27 2009 the entire contents of each of which are hereby incorporated by reference herein in their entirety.

The present invention relates to a peripheral apparatus control system a peripheral apparatus an information processing apparatus a peripheral apparatus control method and a program.

In recent years a peripheral apparatus control system has been effectively utilized in various environments such as a user s home or offices. In a peripheral apparatus control system like this a peripheral apparatus is connected to an information processing apparatus via various interfaces such as universal serial bus USB Ethernet or a wireless local area network LAN .

As an example of a peripheral apparatus a printer a copying machine a facsimile apparatus a scanner and digital camera or a combination of the above described functions can be used. If a printer is used as an example of a peripheral apparatus the following two types of printers are generally used in a network printing system in which a plurality of information processing apparatuses shares a printer.

One type is a printer that includes a mass storage device for storing print jobs. If this type of printer is used a user executes a print job from the printer. Another type is a printer that manages the order of transmission of print jobs from the information processing apparatus. If this type of printer is used the information processing apparatus transmits a print job when necessary.

In the description above a printer is used as the peripheral apparatus. However a print server can also implement the above described function. If a network print system including a print server is used it becomes unnecessary to provide the printer with a mass storage device for storing a plurality of print jobs. Various types of the above described network printing system have been conventionally provided.

More specifically in a method discussed in Japanese Patent Application Laid Open No. 02 146618 a printer accepts a print reservation from an information processing apparatus. In addition the printer manages the order of receiving print reservations. Furthermore the information processing apparatus inputs print requests according to the print reservation order.

In other words the printer receives a print request from the information processing apparatus as the reservation before completing currently executed print processing. In addition the printer assigns a reservation order number to each print request according to the order of receiving the print requests. Furthermore the printer updates the reservation order every time one print processing is completed. Moreover the printer requests print data to an information processing apparatus whose print request is to be processed next. In addition the printer receives the print data and prints the received print data.

In the printing system discussed in Japanese Patent Application Laid Open No. 02 146618 it is necessary to provide the printer with a function for giving a request for print data to the information processing apparatus. Accordingly costs of manufacture may increase.

On the other hand Japanese Patent Application Laid Open No. 2006 181843 discusses the following method. In this conventional method it is not necessary for the printing system to provide a printer with a function for giving requests for print data to the information processing apparatus. More specifically in the latter conventional method the information processing apparatus inputs a print request requesting processing of a print job.

In this conventional method the printer registers an identifier of the received print request in a waiting list. Furthermore the printer manages execution of print jobs according to the print request by using the waiting list. In addition the printer determines an interval of giving a print request according to the print request priority order stored in the waiting list at the time of reception of the print requests. Furthermore control of request input processing is performed so that the print requests are input at the interval determined in the above described manner.

Meanwhile in recent years a network printing system which includes a plurality of information processing apparatuses that shares a printer has been standardized. More specifically a network printing system that utilizes a Print Service by device profile for web service WSD which will be described in detail later below in an exemplary embodiment of the present invention has been marketed. In the network printing system that utilizes the WSD Print Service an operating system OS issues an operation CreatePrintJobRequest to a printer as a print request for processing of a print job.

If the method discussed in Japanese Patent Application Laid Open No. 2006 181843 is applied to the network printing system that utilizes the WSD Print Service the CreatePrintJobRequest operation which is a print request for processing of a print job is utilized. In this case it becomes necessary to add an identifier which is one of the characteristics of the method discussed in Japanese Patent Application Laid Open No. 2006 181843 to CreatePrintJobRequest.

However because the CreatePrintJobRequest operation is issued by the OS a printer driver or the OS according to an instruction from the printer driver cannot add the identifier to the operation. Accordingly the network printing system discussed in Japanese Patent Application Laid Open No. 2006 181843 cannot be applied to the network printing system that utilizes the WSD Print Service.

In order to solve the above described problem the present invention is directed to provide a highly operable peripheral apparatus control system in a network printing system that utilizes WSD Print Service which utilizes a low cost shared printer that does not include a mass storage device nor a function for requesting print data to an information processing apparatus.

According to an aspect of the present invention a peripheral apparatus control system includes an information processing apparatus and a peripheral apparatus. The information processing apparatus inputs a job request and a reservation request. The peripheral apparatus is in communication with the information processing apparatus via a network to receive the job request and the reservation request. The peripheral apparatus includes a first measurement unit to measure a timing reception difference between a timing of reception of the job request and a timing of reception of the reservation request. If the timing reception difference is equal to or less than a first predetermined time the peripheral apparatus inputs a reservation identification and accept a reservation of the job request.

According to an exemplary embodiment of the present invention the following effects can be implemented.

 i A highly operable peripheral apparatus control system in a network printing system that utilizes WSD Print Service which utilizes a low cost shared printer that does not include a mass storage device or a function for requesting print data to an information processing apparatus can be implemented.

 ii A printer which is capable of receiving only one print job and cannot receive a plurality of print jobs at the same time can print a plurality of print jobs received from one or a plurality of personal computer PC s correctly according to the order of input of the plurality of print jobs.

 iii A highly functional peripheral apparatus control system can be implemented that is capable even in an environment in which print jobs of a plurality of different protocols exist in a mixed state of printing the print jobs input from the PCs correctly and appropriately according to the order of input of the print jobs.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

Note that among information about the Windows Vista operating system OS mentioned here information not described in detail is released on the Internet i.e. on a web page of the Microsoft Developer Network MSDN site of Microsoft Corporation under the following URL as of Jul. 22 2009 

Accordingly such information will not be described in detail here. In addition in the following description a term USB refers to a universal serial bus. Detailed information about USB is released in a USB web site under the following URL as of Jul. 22 2009 

Furthermore a term WSD is an abbreviation of web service on devices . Detailed information about WSD is released in the Windows Hardware Developer Central WHDC web site of Microsoft Corporation under the following URL as of Jul. 22 2009 

Accordingly WSD will not be described in detail here. In addition WSD Print Service Definition Version 1.0 is a print service defined by Microsoft Corporation. Detailed information about WSD Print Service Definition Version 1.0 is released in the WHDC web site of Microsoft Corporation under the following URL as of Jul. 22 2009 

A first exemplary embodiment of the present invention will now be described below. illustrates an exemplary system configuration of a peripheral apparatus control system including an information processing apparatus and a peripheral apparatus according to a first exemplary embodiment of the present invention.

Referring to information processing apparatuses and are general purpose PCs. The PCs and include hardware illustrated in . In the present invention it is supposed that an OS equivalent to Windows Vista has been previously installed on the PCs and . Furthermore it is supposed that an OS equivalent to Windows XP has been previously installed on the PC .

In the example illustrated in each of the PCs and is connected to a network . The network is an Ethernet network. A printer and each of the PC are in communication with one another via a USB interface . The printer which includes a color inkjet printer is an example of a peripheral apparatus according to the present exemplary embodiment. The printer is a printer manufactured by ABC Corporation and having a model name Kmmn . As the peripheral apparatus of the present invention a printer a copying machine a facsimile apparatus a scanner and a digital camera and an apparatus having a combination of functions of the above described apparatuses can be used.

The printer includes hardware that will be described in detail below with reference to . The printer is connected with the PC via the USB interface and the network . Thus the printer and the PC are in interactive communication with each other.

An application includes a file having a .exe format i.e. a file having an extension .exe of Windows. The application is an application capable of executing printing as will be described in detail below with reference to . The PC includes a language monitor . The language monitor will be described in detail below with reference to .

Referring to the PC includes a random access memory RAM unit hereinafter simply referred to as a RAM a hard disk drive HDD a keyboard KBD and a central processing unit CPU . In addition the PC includes a display a liquid crystal display LCD and a network board NB . Furthermore the PC includes a bus . The RAM the HDD the KBD the CPU the LCD and the NB are in communication with one another via the bus .

The HDD is an example of a storage unit. The KBD is an example of an input unit. The CPU is an example of a control unit. The LCD is an example of a display unit. The NB is an example of a communication control unit. A removable portable compact disc read only memory CD ROM or a built in read only memory ROM can be used as the storage unit.

Each module software illustrated in is stored on the HDD and is loaded and executed by the CPU on the RAM where necessary. Thus the CPU implements a function of each module software illustrated in . The printer has the hardware configuration illustrated in .

In the example illustrated in a CPU includes a microprocessor. The CPU which functions as a central processing unit of the printer controls a RAM a communication unit a recording unit an operation unit and a display unit according to a program stored on a ROM .

The ROM stores a program used by the printer for executing recording printing and a program used by the printer to execute processing for notifying information about the status of print processing to the PC under control of a printer driver which will be described in detail below with reference to . The RAM temporarily and primarily stores print data which is transmitted from the PC and based on which an image is printed by the recording unit .

The communication unit includes the USB interface and a connection port for connection via the network . The communication unit controls communication by USB and Ethernet . The recording unit includes a recording unit and an electric circuit. The recording unit of the recording unit includes an inkjet type recording head each color ink a carriage and a recording paper conveyance mechanism. The electric circuit of the recording unit includes an application specific integrated circuit ASIC which is used for generating a printing pulse at the recording head based on the print data.

By executing a printing operation by using an application capable of executing printing a content to be displayed image data of a file opened by the application capable of printing hereinafter simply referred to as a print application is temporarily stored on the HDD of the PC as a spool file of the Enhanced Metafile EMF format. The spool file is then converted by the printer driver into print data including a command for controlling the printer . Furthermore the print data is then transmitted to the printer via the USB interface or the network . The print data received by the printer is converted by the recording unit into a printing pulse and then is printed on a recording paper based on the printing pulse.

The operation unit includes various buttons such as a power button or a reset button. The user can execute a job by using the printer by operating the operation unit . The display unit includes a touch panel which includes an LCD. The display unit can display the status of the printer . Furthermore the user can execute various settings via the display unit . In addition the user can enter display and verify various settings on the display unit .

Meanwhile a standard function of Windows Vista OS Plug and Play Extensions PnP X exists as one of Plug and Play Extension functions for supporting network connected devices. However N PnP is used in the present exemplary embodiment as a function equivalent to PnP X. WSD application programming interfaces APIs which will be described in detail below and controls WSD is included in the WSD control stack . APIs which will be described in detail below and controls an IHV native protocol is included in the IHV native protocol control stack .

Device drivers includes standard drivers which are included in the OS as standards and IHV manufactured drivers which are provided by IHVs. An application device driver interface DDI interface includes an application programming interface API and a DDI. A print application is an application capable of executing printing which will be described in detail below with reference to . Applications include the application .

In the example illustrated in the PC has the above described configuration. However the PC whose OS installed thereon is a Windows XP OS includes the IHV native protocol control stack but does not include the WSD control stack . Accordingly if printing is instructed from the PC the printing is executed by utilizing an IHV native protocol because the PC cannot execute printing by utilizing the WSD Print Service.

A graphics device interface GDI constitutes a part of the OS. A printer queue is included in the spooler as a part thereof. The printer queue queues a print job. A queued print job is displayed in a printer queue folder not illustrated .

A print processor changes a print layout and executes special processing on an image to be printed. A graphics driver which is a core component of the printer driver for image processing executes image processing for printing according to a drawing command from the GDI and generates a print control command.

A user interface UI module provides and controls a UI of the printer driver. A language monitor is a data communication interface I F configured to control transmission and receipt of data. A status monitor displays information about a status of the printer such as the ink remaining amount an issued warning and error events.

A port monitor transmits data received from the language monitor to an appropriate port. In addition the port monitor receives data transmitted from the printer via a class driver . In particular a port monitor for controlling communication via USB is referred to as USBMon . A port monitor for controlling the WSD Print Service is referred to as WSDMon .

The class driver is a low level module provided closest to a port. In the present invention the class driver is equivalent to a WSD or IHV unique protocol printer class driver. The class driver controls a port in the present invention a USB port or a network port . The printer driver is manufactured by ABC Corporation which is the manufacturer of the printer .

Referring to in processing S a user inputs an instruction for starting printing by using the application . Then the OS calls a function StartPrintJob of the spooler . In the function that has been already called in processing S the spooler in processing S calls a function LM StartDocPort of the language monitor .

In the function having been called in processing S the language monitor in processing S calls a function PM StartDocPort of the port monitor . In the function having been called in processing S the port monitor in processing S executes appropriate corresponding processing where necessary. In processing S the port monitor substitutes a return value pmRet with a result of the processing and the processing for the function ends. Then the processing returns to the print job calling source. If the processing is normally executed pmRet is substituted with a value TRUE . On the other hand if the processing is not normally executed pmRet is substituted with a value FALSE .

In processing S the language monitor substitutes a return value lmRet with a return value of the function PM StartDocPort . Then the processing for the function LM StartDocPort ends. In processing S the processing returns to the print job calling source.

In processing S the spooler substitutes spRet with a return value of the function LM StartDocPort . In processing S if the value of spRet is not TRUE i.e. if the value of spRet has a value FALSE then the processing returns to processing S. In processing S the spooler calls the function LM StartDocPort of the language monitor .

On the other hand if spRet has the value TRUE in processing S then the processing advances to processing S. In processing S the spooler calls a function LM WritePort of the language monitor . In the function that has already been called in processing S the language monitor in processing S calls a function PM WritePort of the port monitor .

In the function that has already been called in processing S the port monitor in processing S calls a function CreatePrintJob of the WSD APIs that controls WSD. In the function the PC inputs CreatePrintJobRequest of the WSD Print Service to the printer . The CreatePrintJobRequest includes detailed information about a print job.

In processing S after receiving the CreatePrintJobRequest the printer transmits CreatePrintJobResponse or a negative response Fault ServerErrorNotAcceptingJobs to the PC . More specifically if the printer can receive and has received a print job the printer returns CreatePrintJobResponse to the PC . On the other hand if the printer cannot receive the print job the printer returns Fault ServerErrorNotAcceptingJobs to the PC .

In processing S after receiving the CreatePrintJobResponse the PC substitutes the return value of the function CreatePrintJob with a value TRUE . Then the processing returns to the print job calling source.

On the other hand if the PC has received the Fault ServerErrorNotAcceptingJobs the PC substitutes the return value of the function CreatePrintJob with a value FALSE . In processing S the processing returns to the print job calling source.

In processing S the port monitor substitutes the return value pmRet with the return value of the function CreatePrintJob . Then the processing for the function PM WritePort ends. In processing S the processing returns to the print job calling source.

In processing S the language monitor substitutes a return value lmRet with the return value of the function PM WritePort . Then the processing for the function LM WritePort ends. In processing S the processing returns to the print job calling source.

In processing S the spooler substitutes spRet with the return value of the function LM WritePort . In processing S if spRet does not have a value TRUE i.e. if the value of spRet has a value FALSE then the processing returns to processing S. In processing S the spooler calls the function LM WritePort of the language monitor .

If spRet has the value TRUE in processing S the processing advances to processing for transmitting print data which is executed by the spooler . In processing S the spooler calls a function LM EndDocPort of the language monitor .

In the function that has already been called in processing S the language monitor in processing S calls a function PM EndDocPort of the port monitor . In the function that has already been called in processing S the port monitor in processing S executes appropriate corresponding processing where necessary. Furthermore the port monitor substitutes the return value pmRet with a result of the processing. Then the processing for the function ends. In processing S the processing returns to the print job calling source. If the processing is normally executed pmRet is substituted with a value TRUE . On the other hand if the processing is not normally executed pmRet is substituted with a value FALSE .

In processing S the language monitor substitutes the return value lmRet with the return value of the function PM EndDocPort . Then the processing for the function LM EndDocPort ends. In processing S the processing returns to the print job calling source.

In processing S the spooler substitutes spRet with the return value of the function LM EndDocPort . Then the processing for the function StartPrintJob ends. In processing S the processing returns to the print job calling source.

As described above in the conventional method the printer is not capable of receiving all the print jobs input by a plurality of PCs in order of input of the print jobs. Accordingly in this case a print job input at a later timing may be printed before printing a print job input at an earlier timing.

Referring to in processing S a user inputs an instruction for starting printing by using the application . Then the OS calls a function StartPrintJob of the spooler . In the function that has been already called in processing S the spooler in processing S calls a function LM StartDocPort of the language monitor .

In the function having been called in processing S the language monitor in processing S substitutes lmMultipleJobs with a value FALSE to initialize the lmMultipleJobs.

The lmMultipleJobs is a flag used within the language monitor . More specifically a value TRUE is set to the lmMultipleJobs if the printer has a function for receiving and serially processing a plurality of print jobs. On the other hand a value FALSE is set to the lmMultipleJobs if the printer does not include the function described above.

In processing S the language monitor initializes lmRetry by substituting lmRetry with a value 0 . The lmRetry is a variable used within the language monitor . The lmRetry indicates the number of times of retries of a print job request which is input by the PC to the printer .

In processing S the language monitor initializes lmReceivedId by substituting lmReceivedId with a value None . In processing S and S illustrated in which will be described in detail later below the lmReceivedId is substituted with a print reservation ID which is input by the printer when the printer has received a reservation of a print job request. Subsequently the language monitor executes the same processing as the processing S through S .

In processing S the spooler substitutes spRet with the return value of the function LM StartDocPort which has been returned in the same processing as the processing S. If spRet does not have a value TRUE i.e. if spRet has a value FALSE in processing S then the processing returns to processing S. In processing S the spooler calls the function LM StartDocPort of the language monitor .

On the other hand if spRet has a value TRUE in processing S then the processing advances to processing S illustrated in . Processing for inputting a print job request and reserving a print job will be described in detail below with reference to .

In processing S the spooler calls the function LM EndDocPort of the language monitor . In the function that has already been called in processing S the language monitor in processing S initializes lmMultipleJobs by substituting lmMultipleJobs with a value FALSE . In processing S the language monitor initializes lmRetry by substituting the lmRetry with a value 0 . In processing S the language monitor initializes lmReceivedId by substituting lmReceivedId with a value None .

Then the language monitor executes the same processing as the processing S through S illustrated in . Furthermore the language monitor ends the processing for the function LM EndDocPort . In processing S the processing returns to the print job calling source.

In this processing the language monitor substitutes lmRet with the return value of the function PM EndDocPort by executing the same processing as the processing S. In processing S the language monitor returns the value of the lmRet as the return value of the function LM EndDocPort .

In processing S the spooler substitutes spRet with the return value of the function LM EndDocPort . Then the processing for the function StartPrintJob ends. In processing S the processing returns to the print job calling source.

Referring to in processing S the spooler calls the function LM WritePort of the language monitor . In the function that has been already called in processing S the language monitor in processing S identifies a value of each of lmRetry and lmMultipleJobs.

If the value of lmRetry is greater than 0 and if lmMultipleJobs has a value TRUE then the processing advances to processing S. On the other hand if the value of lmRetry is equal to 0 or if lmMultipleJobs does not have a value TRUE i.e. if lmMultipleJobs has a value FALSE in processing S then the processing advances to processing S.

In processing S the language monitor sets ans ABCCommand as an argument. In addition the language monitor calls a function GetPrinterElements which is a function of WSD APIs that controls WSD.

In the function the PC inputs GetPrinterElementsRequest of the WSD Print Service to the printer . After receiving the GetPrinterElementsRequest in processing S the printer returns GetPrinterElementsResponse to the PC .

After the PC has received the GetPrinterElementsResponse in processing S the PC substitutes the return value of the function GetPrinterElements with a value TRUE . Then the processing returns to the print job calling source.

If the PC has not received GetPrinterElementsResponse during a predetermined specific time period after a timing of inputting the GetPrinterElementsRequest to the printer the PC substitutes the return value of the function GetPrinterElements with a value FALSE . In processing S the processing returns to the print job calling source.

In processing S the language monitor substitutes lmRet with the return value of the function GetPrinterElements . In the present exemplary embodiment a case of an error event in which FALSE is returned as the return value of the function GetPrinterElements will not be described. The GetPrinterElementsRequest input by the PC in processing S and the GetPrinterElementsResponse which the printer returns in response thereto will be described in detail below with reference to .

In processing S the language monitor substitutes lmReceivedId with the value set to the element or included in GetPrinterElementsResponse which has been received as the argument of the function GetPrinterElements processed in S.

In processing S the language monitor verifies the value of lmReceivedId. If the value of lmReceivedId is None in processing S then the processing advances to processing S. In processing S the language monitor initializes the number of retries of the print job request by substituting the lmRetry with a value 0 . On the other hand if the value of lmReceivedId is not None in processing S the processing advances to processing S. In processing S the language monitor updates the number of retries of the print job request by substituting lmRetry with a value lmRetry 1 .

In processing S the language monitor calls a function PM WritePort of the port monitor . In the function that has already been called in processing S the port monitor in processing S calls a function CreatePrintJob of WSD APIs that controls WSD.

In the function the PC inputs CreatePrintJobRequest of the WSD Print Service to the printer . The CreatePrintJobRequest includes detailed information about the print job. In processing S after receiving the CreatePrintJobRequest the printer returns CreatePrintJobResponse or Fault ServerErrorNotAcceptingJobs which is a negative response to the PC .

More specifically if the printer can receive a print job and execute the print job and if the printer has received the print job the printer returns CreatePrintJobResponse to the PC . On the other hand if the printer can receive a print job but cannot execute the print job and if the printer has received the print job then the printer returns Fault ServerErrorNotAcceptingJobs to the PC . In addition if the printer cannot receive a print job the printer also returns Fault ServerErrorNotAcceptingJobs to the PC .

If the CreatePrintJobResponse has been received the PC substitutes the return value of the function CreatePrintJob with a value TRUE . In processing S the processing returns to the print job calling source. On the other hand if the PC has received the Fault ServerErrorNotAcceptingJobs then the PC substitutes the return value of the function CreatePrintJob with a value FALSE . In processing S the processing returns to the print job calling source.

In addition in processing S the port monitor substitutes the return value pmRet with the return value of the function CreatePrintJob . Then the processing for the function PM WritePort ends. In processing S the processing returns to the print job calling source.

In processing S the language monitor substitutes the return value lmRet with the return value of the function PM WritePort . In processing S the language monitor verifies the value of lmRet. If lmRet has a value TRUE in processing S then the processing advances to processing S. On the other hand if lmRet does not have a value TRUE i.e. if lmRet has a value FALSE in processing S then the processing advances to processing S. In processing S the language monitor verifies the value of lmRetry.

If lmRetry has a value 0 in processing S then the processing advances to processing S. In processing S the language monitor sets wprt PrinterDescription as the argument. In addition in processing S the language monitor calls a function GetPrinterElements which is a function of WSD APIs that controls WSD. In the function the PC inputs GetPrinterElementsRequest of the WSD Print Service to the printer .

The GetPrinterElementsRequest includes a function wprt PrinterDescription . The function wprt PrinterDescription is a function necessary for the printer to acquire a function . The function includes information about whether the printer is capable of receiving a plurality of print jobs. The function wprt PrinterDescription and the function will be described in detail below with reference to respectively.

If the GetPrinterElementsRequest has been received in processing S the printer returns GetPrinterElementsResponse to the PC . If the PC has received GetPrinterElementsResponse the PC substitutes the return value of the function GetPrinterElements with a value TRUE . In processing S the processing returns to the print job calling source.

If the PC has not received GetPrinterElementsResponse during a predetermined specific time period after a timing of inputting the GetPrinterElementsRequest to the printer the PC substitutes the return value of the function GetPrinterElements with a value FALSE . In processing S the processing returns to the print job calling source.

In processing S the language monitor substitutes lmRet with the return value of the function GetPrinterElements . In the present exemplary embodiment a case of an error event in which FALSE is returned as the return value of the function GetPrinterElements will not be described.

In processing S the language monitor determines whether the value set to the function included in the GetPrinterElementsResponse which has been received as the argument of the function GetPrinterElements is true . If a value true has been set to the function in processing S then the processing advances to processing S. In processing S the language monitor substitutes lmMultipleJobs with a value TRUE .

If lmRetry has a value other than 0 in processing S then the processing advances to S. In the present exemplary embodiment a value other than 0 actually refers to an integer greater than 0 because the value input in substitution of lmRetry in processing S and S is an integer equal to or greater than 0.

If lmMultipleJobs has a value TRUE in processing S then the processing advances to processing S. In processing S the language monitor sets ans ABCCommand as the argument. In addition the language monitor calls a function GetPrinterElements which is a function of WSD APIs that controls WSD. In the function the PC inputs GetPrinterElementsRequest of the WSD Print Service to the printer .

In processing S if the GetPrinterElementsRequest has been received the printer returns GetPrinterElementsResponse to the PC . If the PC has received GetPrinterElementsResponse the PC substitutes the return value of the function GetPrinterElements with a value TRUE . In processing S the processing returns to the print job calling source.

If the PC has not received GetPrinterElementsResponse during a predetermined specific time period after a timing of inputting the GetPrinterElementsRequest to the printer the PC substitutes the return value of the function GetPrinterElements with a value FALSE . In processing S the processing returns to the print job calling source.

In processing S the language monitor substitutes lmRet with the return value of the function GetPrinterElements . In the present exemplary embodiment a case of an error event in which FALSE is returned as the return value of the function GetPrinterElements will not be described. The GetPrinterElementsRequest input by the PC in processing S and the GetPrinterElementsResponse which the printer returns in response thereto will be described in detail below with reference to .

In processing S the language monitor substitutes lmReceivedId with the value set to the element or included in GetPrinterElementsResponse i.e. a print reservation ID which has been received as the argument of the function GetPrinterElements processed in S.

In processing S the language monitor verifies the value of lmReceivedId. If the value of lmReceivedId is None in processing S then the processing advances to processing S. In processing S the language monitor initializes the number of retries of the print job request by substituting the lmRetry with a value 0 . On the other hand if the value of lmReceivedId is not None in processing S the processing advances to processing S. In processing S the language monitor updates the number of retries of the print job request by substituting lmRetry with a value lmRetry 1 .

If lmMultipleJobs does not have a value TRUE i.e. if lmMultipleJobs has a value FALSE in processing S then the processing advances to processing S. In processing S the processing for the function LM WritePort ends. Then the processing returns to the print job calling source. In this case the value of lmRet is returned as the return value of the function LM WritePort . In processing S the spooler substitutes spRet with the return value of the function LM WritePort .

If spRet does not have a value TRUE i.e. if the value of spRet has a value FALSE in processing S then the processing returns to processing S. In processing S the spooler calls a function LM WritePort of the language monitor . On the other hand if spRet has a value TRUE in processing S then the spooler advances to and executes the print data transmission processing illustrated in .

As described above according to the present invention having the configuration described above if a low cost printer capable of processing and printing one print job only at the same time is used the printer can serially receive print jobs input from a plurality of PCs and print the plurality of print jobs in order of receipt thereof. Accordingly the present exemplary embodiment having the above described configuration can prevent printing of a print job input at a later timing before printing a print job that has been input at an earlier timing.

Therefore the present invention can implement a highly useful peripheral apparatus control system capable of correctly and appropriately printing print jobs in order of receipt of the print jobs.

In the function that has been already called in processing S the language monitor in processing S calls a function PM WritePort of the port monitor . In the function that has been already called in processing S the port monitor in processing S calls a function SendDocument of WSD APIs that controls WSD.

In the function the PC inputs SendDocumentRequest of the WSD Print Service to the printer . In addition by using a message transmission optimization mechanism MTOM the PC transmits print data including a print control command to the printer as unprocessed bytes by using a Simple Object Access Protocol SOAP message. In processing S the printer returns SendDocumentResponse in response to the SendDocumentRequest to the PC .

After the PC has received the SendDocumentResponse and after all print data has been completely transmitted to the printer the PC substitutes the return value of the function SendDocument with a value TRUE . In processing S the processing returns to the print job calling source.

If the PC has input SendDocumentRequest or if the PC has received the SendDocumentResponse and if any error occurs in this state the PC substitutes the return value of the function SendDocument with a value FALSE . In processing S the processing returns to the print job calling source.

In processing S the port monitor substitutes the return value pmRet with the return value of the function SendDocument . Then the processing for the function PM WritePort ends. In processing S the processing returns to the print job calling source.

In processing S the language monitor substitutes the return value lmRet with the return value of the function PM WritePort . Then the processing for the function LM WritePort ends. In processing S the processing returns to the print job calling source.

In processing S the spooler substitutes spRet with the return value of the function LM WritePort . If spRet does not have a value TRUE i.e. if the value of spRet is FALSE in processing S then the processing returns to processing S. In processing S the spooler calls the function LM WritePort of the language monitor . If spRet has a value TRUE in processing S then the processing advances to processing S illustrated in or processing S illustrated in .

When the spooler calls the function LM WritePort of the language monitor by executing the processing illustrated in the processing illustrated in starts. Referring to in step S the language monitor starts the processing for the function LM WritePort .

In step S the language monitor verifies the value of each of lmRetry and lmMultipleJobs. In step S the language monitor determines whether the value of lmRetry is greater than 0 and if the lmMultipleJobs has a value TRUE . If it is determined that the value of lmRetry is greater than 0 and if the lmMultipleJobs has a value TRUE Yes in step S then the processing advances to step S. On the other hand if it is determined that the value of lmRetry is equal to 0 or if the lmMultipleJobs does not have a value TRUE i.e. if the lmMultipleJobs has a value FALSE No in step S then the processing advances to step S.

In step S the language monitor sets ans ABCCommand as the argument. In addition the language monitor calls the function GetPrinterElements which is a function of WSD APIs that controls WSD.

In step S in the function the PC inputs GetPrinterElementsRequest of the WSD Print Service to the printer . After receiving the GetPrinterElementsRequest the printer returns GetPrinterElementsResponse to the PC processing S illustrated in and step S illustrated in .

If the PC has received GetPrinterElementsResponse the PC substitutes the return value of the function GetPrinterElements with a value TRUE . In step S the processing returns to the language monitor which is the print job calling source.

If the PC has not received GetPrinterElementsResponse during a predetermined specific time period after a timing of inputting the GetPrinterElementsRequest to the printer the PC substitutes the return value of the function GetPrinterElements with a value FALSE . In step S the processing returns to the language monitor which is the print job calling source.

Furthermore in step S the language monitor substitutes lmRet with the return value of the function GetPrinterElements . In the present exemplary embodiment a case of an error event in which FALSE is returned as the return value of the function GetPrinterElements will not be described. The GetPrinterElementsRequest input by the PC in processing S and the GetPrinterElementsResponse which the printer returns in response thereto will be described in detail below with reference to .

In step S the language monitor substitutes lmReceivedId with the value set to the element or included in GetPrinterElementsResponse which has been received as the argument of the function GetPrinterElements processed in S. In step S the language monitor determines whether the value of lmReceivedId is None . If the value of lmReceivedId is None Yes in step S then the processing advances to step S. On the other hand if it is determined that the value of lmReceivedId is not None No in step S then the processing advances to step S.

In step S the language monitor initializes the number of retries of the print job request by substituting lmRetry with a value 0 . In step S the language monitor updates the number of retries of the print job request by substituting lmRetry with a value lmRetry 1 .

In step S the language monitor calls the function PM WritePort of the port monitor . The processing executed by the port monitor in the function will be described in detail below with reference to . In step S the language monitor substitutes the return value lmRet with the return value of the function PM WritePort .

In step S the language monitor determines whether the value of lmRet is TRUE . If it is determined that the value of lmRet is TRUE Yes in step S then the processing advances to step S. On the other hand if it is determined that the value of lmRet is not TRUE i.e. if the value of lmRet is FALSE No in step S then the processing advances to step S.

In step S the language monitor determines whether the value of lmRetry is 0 . If it is determined that the value of lmRetry is 0 Yes in step S then the processing advances to step S. On the other hand if the value of lmRetry is a value other than 0 No in step S then the processing advances to step S. More specifically because the value substituted into lmRetry in steps S and S is an integer equal to or greater than 0 the processing actually advances to step S if the value of lmRetry is an integer greater than 0.

In step S the language monitor sets wprt PrinterDescription as the argument. In addition the language monitor calls the function GetPrinterElements which is a function of WSD APIs that controls WSD.

In step S in the function the PC inputs GetPrinterElementsRequest of the WSD Print Service to the printer . The GetPrinterElementsRequest includes a function wprt PrinterDescription . The function wprt PrinterDescription is a function necessary for the printer to acquire a function . The function includes information about whether the printer is capable of receiving a plurality of print jobs. The function wprt PrinterDescription and the function will be described in detail below with reference to respectively.

In step S similarly to the processing in S and S if the GetPrinterElementsRequest has been received the printer returns GetPrinterElementsResponse to the PC . If the PC has received GetPrinterElementsResponse the PC substitutes the return value of the function GetPrinterElements with a value TRUE . Furthermore the processing returns to the language monitor which is the print job calling source.

If the PC has not received GetPrinterElementsResponse during a predetermined specific time period after a timing of inputting the GetPrinterElementsRequest to the printer the PC substitutes the return value of the function GetPrinterElements with a value FALSE . In step S the processing returns to the language monitor which is the print job calling source. In the present exemplary embodiment a case of an error event in which FALSE is returned as the return value of the function GetPrinterElements will not be described.

In step S the language monitor determines whether the value set to the function included in the GetPrinterElementsResponse which has been received as the argument of the function GetPrinterElements is true . If it is determined that the value true has been set to the function Yes in step S then the processing advances to step S. On the other hand if it is determined that a value other than true has been set to the function No in step S then the processing advances to step S.

In step S the language monitor substitutes lmMultipleJobs with a value TRUE . In step S the language monitor determines whether the value of lmMultipleJobs is TRUE . If it is determined that the value of lmMultipleJobs is TRUE Yes in step S then the processing advances to step S. On the other hand if it is determined that the value of lmMultipleJobs is not TRUE i.e. if the value of lmMultipleJobs is FALSE No in step S then the processing advances to step S.

In step S the language monitor sets ans ABCCommand as the argument. In addition the language monitor calls the function GetPrinterElements which is a function of WSD APIs that controls WSD.

More specifically in step S in the function the PC inputs GetPrinterElementsRequest of the WSD Print Service to the printer similarly to processing S and step S . If the PC has received GetPrinterElementsResponse the PC substitutes the return value of the function GetPrinterElements with a value TRUE . Then the processing returns to the language monitor which is the print job calling source.

If the PC has not received GetPrinterElementsResponse during a predetermined specific time period after inputting the GetPrinterElementsRequest to the printer the PC substitutes the return value of the function GetPrinterElements with a value FALSE . In step S the processing returns to the language monitor which is the print job calling source.

Furthermore in step S the language monitor substitutes lmRet with the return value of the function GetPrinterElements . In the present exemplary embodiment a case of an error event in which FALSE is returned as the return value of the function GetPrinterElements will not be described. The GetPrinterElementsRequest input by the PC in processing S and the GetPrinterElementsResponse which the printer returns in response thereto will be described in detail below with reference to .

In step S the language monitor substitutes lmReceivedId with the value set to the element or included in GetPrinterElementsResponse which has been received as the argument of the function GetPrinterElements processed in S. In step S the language monitor determines whether the value of lmReceivedId is None . If the value of lmReceivedId is None Yes in step S then the processing advances to step S. On the other hand if it is determined that the value of lmReceivedId is not None No in step S then the processing advances to step S.

In step S the language monitor initializes the number of retries of the print job request by substituting lmRetry with a value 0 . In step S the language monitor updates the number of retries of the print job request by substituting lmRetry with a value lmRetry 1 .

In step S the language monitor returns lmRet to the spooler as the return value of the function LM WritePort . Then the processing for the function LM WritePort ends. In step S the processing returns to the spooler which is the print job calling source.

After the language monitor has called the function PM WritePort of the port monitor in step S then the processing illustrated in starts. Referring to in step S the port monitor starts the processing for the function PM WritePort .

In step S the port monitor verifies the status of CreatePrintJob. In step S the port monitor determines whether CreatePrintJobResponse has been received in response to an input CreatePrintJobRequest. If it is determined that CreatePrintJobResponse has been already received Yes in step S then the processing advances to step S. On the other hand if it is determined that CreatePrintJobResponse has not been received yet No in step S then the processing advances to step S.

In step S the port monitor substitutes the return value pmRet with a value TRUE . In step S the port monitor calls the function CreatePrintJob of WSD APIs that controls WSD. In step S in the function the PC inputs CreatePrintJobRequest of the WSD Print Service to the printer . The CreatePrintJobRequest includes detailed information about the print job.

Similar to the processing in S after receiving the CreatePrintJobRequest the printer returns CreatePrintJobResponse or Fault ServerErrorNotAcceptingJobs which is a negative response to the PC . To paraphrase this similar to the processing in S More specifically if the printer can receive a print job and execute the print job and if the printer has received the print job the printer returns CreatePrintJobResponse to the PC . On the other hand if the printer can receive a print job but cannot execute the print job and if the printer has received the print job then the printer returns Fault ServerErrorNotAcceptingJobs to the PC . In addition if the printer cannot receive a print job the printer also returns Fault ServerErrorNotAcceptingJobs to the PC .

If the CreatePrintJobResponse has been received the PC substitutes the return value of the function CreatePrintJob with a value TRUE . In step S the processing returns to the port monitor which is the print job calling source. On the other hand if the PC has received the Fault ServerErrorNotAcceptingJobs then the PC substitutes the return value of the function CreatePrintJob with a value FALSE . In step S the processing returns to the port monitor which is the print job calling source. In addition in step S the port monitor substitutes the return value pmRet with the return value of the function CreatePrintJob .

In step S the port monitor returns pmRet to the language monitor as the return value of the function PM WritePort . Then the processing for the function PM WritePort ends. In step S the processing returns to the language monitor which is the print job calling source.

After the language monitor has called the function PM WritePort of the port monitor in processing S then the processing illustrated in starts. Referring to in step S the port monitor starts the processing for the function PM WritePort .

In step S the port monitor verifies the status of SendDocument. In step S the port monitor determines whether SendDocumentResponse has already been received in response to an input SendDocumentRequest. If it is determined that SendDocumentResponse has already been received in response to an input SendDocumentRequest Yes in step S then the processing advances to step S. On the other hand if it is determined that SendDocumentResponse has not been received No in step S then the processing advances to step S.

In step S the port monitor substitutes the return value pmRet with a value TRUE . In step S the port monitor calls the function SendDocument of WSD APIs that controls WSD similarly to the processing S in .

In step S in the function the PC inputs SendDocumentRequest of the WSD Print Service to the printer . In addition in step S by using MTOM message encoding the PC transmits print data including a print control command to the printer as an unprocessed byte by using the SOAP message.

In addition in step S the printer returns SendDocumentResponse to the PC in response to SendDocumentRequest similar to the processing in S illustrated in .

If any error has occurred when the PC inputs SendDocumentRequest or receives SendDocumentResponse the PC substitutes the return value of the function SendDocument with a value FALSE . Furthermore in step S the processing returns to the print job calling source. Moreover in step S the port monitor substitutes the return value pmRet with the return value of the function SendDocument .

In step S after the PC has received the SendDocumentResponse and if all print data has been completely transmitted to the printer the PC substitutes the return value of the function SendDocument with a value TRUE . In step S the processing returns to the port monitor which is the print job calling source. In addition in step S the port monitor substitutes the return value pmRet with the return value of the function SendDocument .

In step S the port monitor returns pmRet to the language monitor as the return value of the function PM WritePort . In step S the processing for the function PM WritePort ends and returns to the language monitor which is the print job calling source.

The general content of the GetPrinterElements and CreatePrintJob is defined by the WSD Print Service Definition Version 1.0. Accordingly the detailed description thereof will be omitted in the present exemplary embodiment.

In the drawing to be described below the name space name wprt is handled in the similar manner. In other words in the drawing to be described below the name space name wprt is effective within the public information defined by the WSD Print Service Definition Version 1.0.

An element which is the public information includes information about a print job. A element is the public information to which a print job name is set. In the example illustrated in a print job name Photo2 is set.

the element is the public information to which the name of a user who has input the print job is set. In the example illustrated in a user name Natsu is set.

In the example illustrated in a description defines a name space of a Print Service that utilizes a WSD of ABC Corporation as a name space name ans. The name space name ans is effective within the private information defined by the Print Service that utilizes the WSD of ABC Corporation. In the drawing to be described below the name space name ans is handled in the similar manner. In other words in the drawing to be described below the name space name ans is effective within the private information defined by the Print Service that utilizes the WSD of ABC Corporation.

An element is public information to which wprt PrinterDescription included in the public information is set as a Name attribute thereof. This indicates that the GetPrinterElementsResponse includes wprt PrinterDescription designated by using the element .

An element which is the public information includes information about a function of the printer . An element is the public information. Data a text string defined in Institute of Electrical and Electronic Engineers IEEE 1284 2000 Device ID is set to the element . The element indicates a device ID of the printer . More specifically in the example illustrated in a device ID MFG ABC CMD ABCCommand MDL Kmmn CLS PRINTER DES ABC Kmmn VER 1.00 INFO 000 is set to the element .

The function which is the private information describes whether the printer includes a function for controlling a plurality of print jobs. If the printer includes the function for controlling a plurality of print jobs the printer is capable of receiving a plurality of print jobs and process and print one print job of the plurality of print jobs.

If the printer includes the function for controlling a plurality of print jobs a value true is set to the function . On the other hand if the printer does not include the function for controlling a plurality of print jobs a value false is set to the function .

Referring to to an element which is the public information ans ABCCommand is set as the value thereof. The ans ABCCommand is the private information. An element which is the private information includes an element an element an element an element and an element .

All of the elements and are private information. The language monitor sets an appropriate value to the elements and of the GetPrinterElementsRequest.

The language monitor transmits a value job ID which has been set to the third argument JobId transferred when the spooler has called the function LM StartDocPort in the processing in S and S to the element . The job ID transferred from the spooler to the language monitor has been input by the OS of the PC . Accordingly the value set to the element is different from the job ID input by the printer and set to the element . In the example illustrated in a value 5 is set to the element .

The function PM WritePort which is an interface for the language monitor and the port monitor has the following specification 

In processing S and processing S and in step S illustrated in the port monitor calls CreatePrintJob of WSD APIs that controls WSD. However the value set to each of the element the element and the element is not transmitted as the argument of the function PM WritePort . Accordingly the language monitor cannot refer to or change the value set to the element or . Due to the same reason the language monitor cannot add the elements and which are the private information to CreatePrintJobRequest by using the CreatePrintJob operation input by the port monitor .

To the element a print reservation ID input when the printer has received the reservation of the print job request is set. In the example illustrated in no print reservation ID has been input by the printer yet. Accordingly a value None is set to the element .

The language monitor sets a value None to the element as an initial value used when head data of print data including a print control command which is a trigger for inputting a print job request from the PC to the printer is to be transmitted to the printer for the first time. In cases other than the above described case the language monitor stores the value set to the element which has been transmitted from the printer to the PC last in lmReceived. Furthermore the language monitor sets the value to the element .

The number of retries of the print job request that the PC inputs to the printer is set to the element . In the example illustrated in a value 0 which indicates that the print job request is to be transmitted from the PC to the printer for the first time is set to the element .

Every time transmission of the head data of the print data including the print control command which is the trigger for inputting the print job request from the PC to the printer is executed the language monitor increments the number of times of retries by 1 and sets the incremented value to the element .

The version of the OS of the PC is set to the element . The language monitor calls a function GetVersionEx which is the API of the OS. In addition the language monitor sets version information about the OS returned by using the argument to the element . More specifically in the example illustrated in a value 6.0 which indicates that Windows Vista is used as the OS is set to the element .

The printer verifies the value set to the element and is capable of changing the control differently for a case where the OS of the PC is Windows Vista and a case where a Windows OS other than Windows Vista is used as the OS of the PC.

More specifically if a timing or control of the WSD protocol is changed in a future Windows OS from that of Windows Vista the printer can change the timing or control of the WSD protocol according to the change. Accordingly the present exemplary embodiment can execute a stable control optimized for each type of OS installed on the PC. Furthermore with this configuration the present exemplary embodiment can prevent malfunction.

The date and time of input of the GetPrinterElementsRequest is set to the element . The language monitor calls the API of the OS to acquire the date and time. In addition the language monitor sets the acquired date and time to the element . In the example illustrated in the date and time 2009 01 01T00 08 00 is set to the element .

Because the PCs the printer and various other devices connected to the network may be in different states the printer may not always receive GetPrinterElementsRequests that have been serially input by a plurality of PCs the PCs and and other PCs not illustrated to the printer in order of input thereof. Accordingly the printer determines the order of processing GetPrinterElementsRequests based on the element . In addition the printer returns GetPrinterElementsResponse to the PC that is a source of input of the GetPrinterElementsRequest which will be described in detail below with reference to according to the determined order.

Referring to to an element which is the public information ans ABCCommand which is the private information is set as the Name attribute thereof. This indicates that the GetPrinterElementsResponse includes the ans ABCCommand designated in the element .

An element which is the private information includes an element an element an element an element and an element . All the elements and are the private information.

The printer sets the same value as the value of the element to the element . More specifically in the example illustrated in a value 5 is set to the element . In addition the printer sets an appropriate value to the element as described in detail below in . In the example illustrated in a value 00000202 is set to the element .

The printer verifies the value set to the element . If a value 0 has been set to the element the printer determines that the GetPrinterElementsRequest is a request for a newly input print job. On the other hand if a value other than 0 has been set to the element the printer determines that the GetPrinterElementsRequest is a request for resuming processing of the print job whose reservation has been received.

The printer sets the same value as the value of the element to the element . In the example illustrated in a value 0 is set to the element which is a trigger for inputting a print job request from the PC to the printer and corresponds to a case where head data of the print data including a print control command to the printer for the first time.

The element describes version information about the OS of the PC the PC . The printer sets the same value as the value of the element to the element . In the example illustrated in a value 6.0 which represents that Windows Vista OS is used as the OS of the PC has been set.

To the element the date and time of input of the GetPrinterElementsResponse is set. More specifically the printer acquires the date and the time from a real time clock built in to the printer . In addition the printer sets the acquired date and time to the element . In the example illustrated in a value 2009 01 01T00 08 01 is set to the element .

The PC can acquire the time elapsed since the timing of input of GetPrinterElementsRequest to the timing of reception of GetPrinterElementsResponse based on the difference of the time described in the element and the element . Furthermore the PC can calculate the communication speed of the communication via the network and predict the traffic on the network by utilizing the above described time. In other words the PC can optimize communication by the WSD protocol and timing control based on the above described time.

In addition the PC calls a timer included in the OS by using the API. Furthermore the PC can compare the time elapsed since a timing of input of the GetPrinterElementsRequest which is calculated according to the timer and the time calculated based on the difference of the time described in the element and the element . The PC can correct the date and time set to the real time clock of the printer and the date and time set within the PC itself based on a result of the comparison.

As described above with reference to the port monitor calls CreatePrintJob of WSD APIs that controls WSD. However the value set to each of the element the element and the element is not transmitted as the argument of the function PM WritePort . Accordingly the language monitor cannot refer to or change the value set to the element or . Due to the same reason the language monitor cannot refer to the elements or in the CreatePrintJobResponse which are the private information by using the CreatePrintJob operation input by the port monitor .

Referring to to an element which is the public information ans ABCCommand is set as the value thereof. The ans ABCCommand is the private information. An element which is the private information includes an element an element an element an element and an element . All of the elements through are the private information. The language monitor sets an appropriate value to each of the above described elements included in the GetPrinterElementsRequest.

The language monitor transmits a value job ID which has been set to the third argument JobId transferred when the spooler has called the function LM StartDocPort in the processing in S and S to the element . In the example illustrated in a value 5 is set to the element .

To the element a print reservation ID which is input if the printer has received a reservation by a print job request is set. In the example illustrated in the printer has already received a reservation by the print job request. Accordingly in the drawing a value 00000202 which has been input at the time of reception of the reservation is set to the element .

The number of retries of the print job request that the PC inputs to the printer is set to the element . In the example illustrated in a value 1 which indicates that the PC transmits a print job request to the printer as a first retry has been set.

Every time transmission of the print data including a first print control command which is the trigger for inputting the print job request from the PC to the printer is executed the language monitor increments the number of times of retries by 1 and sets the incremented value to the element .

The version of the OS of the PC is set to the element . In the example illustrated in a value 6.0 which indicates that a Windows Vista OS is used as the OS of the PC has been set. The date and time of input of the GetPrinterElementsRequest is set to the element . In the example illustrated in a value 2009 01 01T00 08 04 is set to the element .

To an element which is the public information ans ABCCommand which is the private information is set as the Name attribute. This indicates that the GetPrinterElementsResponse includes ans ABCCommand that has been designated in the element .

An element which is the private information includes an element an element an element an element and an element . All of the elements through are the private information.

The printer sets the same value as the value of the element to the element . More specifically in the example illustrated in a value 5 has been set to the element .

As described below with reference to the printer sets an appropriate value to the element . In the example illustrated in a value 00000202 has been set. The printer sets the same value as the value of the element to the element . More specifically in the example illustrated in a value 1 has been set to the element .

The printer sets the same value as the value of the element to the element . In the example illustrated in a value 6.0 is set to the element .

The printer acquires the date and the time from the real time clock built in to the printer . In addition the printer sets the acquired date and time to the element . In the example illustrated in a value 2009 01 01T00 08 05 is set to the element .

In the example illustrated in a description defines a name space of an ABC Print Service that utilizes an IHV native protocol of ABC Corporation as a name space name lans. By comparing the name space with the name space of the Print Service that utilizes the WSD of ABC Corporation the following can be known. More specifically because the element includes the version information v100 while the element includes the version information v200 the name space of the ABC Print Service that utilizes the IHV native protocol of ABC Corporation has a version earlier than the version of the name space of the Print Service that utilizes the WSD of ABC Corporation.

The name space name lans is effective within the private information defined by the ABC Print Service of ABC Corporation. In the drawing to be described below the name space name lans is handled in the similar manner. In other words in the drawing to be described below the name space name lans is effective within the private information defined by the ABC Print Service of ABC Corporation.

The element indicates that the operation to be executed is the StartJob operation. The element includes an element an element an element and an element . All of the elements through are the private information. In addition the language monitor sets an appropriate value to each of the elements through .

A value PC5 has been set to a value of the element as the name of the computer that has input the information. To the element a time stamp input when the printer has received a reservation by the print job start request is set. In the example illustrated in no time stamp has been input by the printer yet. Accordingly the value None is set to the element .

The language monitor sets a value None to the element as an initial value used when head data of print data including a print control command which is a trigger for inputting a print job start request from the PC to the printer is to be transmitted to the printer for the first time. In cases other than the above described case the language monitor stores the value set to an element which has been transmitted from the printer to the PC last in lmReceived. Furthermore the language monitor sets the value to the element .

The number of retries of the print job start request that the PC inputs to the printer is set to the element . In the example illustrated in a value 0 which indicates a case where the PC transmits a print job start request to the printer for the first time has been set.

Every time transmission of the head data of the print data including the print control command which is the trigger for inputting the print job start request from the PC to the printer is executed the language monitor increments the number of times of retries by 1 and sets the incremented value to the element .

The date and time of input of the StartJobRequest is set to the element . The language monitor calls the API of the OS. In addition the language monitor acquires the date and time. Furthermore the language monitor sets the acquired date and time to the element . In the example illustrated in a value 2009 01 01T22 01 30 has been set.

Because the PCs the printer and various other devices connected to the network may be in different states the printer may not always receive StartJobRequests that have been serially input by a plurality of PCs the PC and other PCs not illustrated to the printer in order of input thereof. Accordingly the printer determines the order of processing StartJobRequests based on the element . In addition the printer returns StartJobResponse to the PC that is a source of input of the StartJobRequest which will be described in detail below with reference to according to the determined order.

In the example illustrated in an element includes an element an element an element and the element . All of the elements through are the private information.

The printer sets the same value as the value of the element to the element . In the example illustrated in a value PC5 has been set to the element . The printer sets an appropriate value to the element according to information set to the print queue database illustrated in . In the example illustrated in a value 00000301 has been set to the element .

The printer verifies the value set to the element . If a value 0 has been set to the element the printer determines that the StartJobRequest is a request for a newly input print job. On the other hand if a value other than 0 has been set to the element the printer determines that the StartJobRequest is a request for resuming processing of the print job whose reservation has been received.

The printer sets the same value as the value of the element to the element . In the example illustrated in a value 0 is set to the element which is a trigger for inputting a print job start request from the PC to the printer and corresponds to a case where head data of the print data including a print control command is transmitted to the printer for the first time.

To the element the date and time of input of the StartJobResponse is set. More specifically the printer acquires the date and the time from the real time clock built in to the printer . In addition the printer sets the acquired date and time to the element . In the example illustrated in a value 2009 01 01T22 01 31 has been set to the element .

The PC can acquire the time elapsed since the timing of input of StartJobRequest to the timing of reception of StartJobResponse based on the difference of the time described in the element and the element . Furthermore the PC can calculate the communication speed of the communication via the network and predict the traffic on the network by utilizing the above described time. In other words the PC can optimize communication by the IHV native protocol and timing control based on the above described time.

In addition the PC calls a timer included in the OS by using the API. Furthermore the PC can compare the time elapsed since a timing of input of the StartJobRequest which is calculated according to the timer and the time calculated based on the difference of the time described in the element and the element . The PC can correct the date and time set to the real time clock of the printer and the date and time set within the PC itself based on a result of the comparison.

Referring to a value Null indicates that a corresponding field is an empty field including no data. In addition a mark indicates that the data is undefined i.e. that no data is available .

Referring to a No. field stores the order of currently executed print job or the order of reserved print job request. In the No. field a value 1 indicates a currently printed print job. Values 2 through 8 indicate a reserved print job request. More specifically in the numbers 2 through 8 in the No. field the numerical value 2 indicates the reservation of a print job request having the highest priority which is to be printed next. The numerical value 8 indicates a reservation of a print job request having the lowest priority which is to be printed last.

In the present exemplary embodiment the print queue includes eight operations in total which includes one print job that can be executed by the printer and seven print job requests that can be reserved on the printer .

Referring to a No. field stores the order of currently executed print job or the order of reserved print job request. In the No. field a value 1 indicates a currently printed print job. Values 2 through 4 indicate a print job that has been received whose job ID stored in a wprt JobId field has been input and which is waiting to be printed. Values 5 through 8 indicate a reservation of the print job request.

More specifically for the numbers 2 through 4 in the No. field the numerical value 2 indicates the reservation of a print job request having the highest priority which is to be printed next. The numerical value 3 indicates a print job having the priority immediately below the priority of the second print job. The numerical value 4 indicates a print job having the priority immediately below the priority of the third print job.

For the numbers 5 through 8 in the No. field the numerical value 5 indicates the reservation of a print job having a priority immediately below the priority of the fourth print job. The numerical value 8 indicates a reservation of a print job request having the lowest priority which is to be printed last.

In the present exemplary embodiment the print queue includes eight operations in total including one print job that can be executed by the printer a total of four print jobs that can be received by the printer including the print job that can be executed by the printer and a total of four print job requests that can be reserved on the printer .

Referring to a Computer Name field stores the name of the PC that has input the print job request. A wprt JobName field stores the name of the print job set to the element the element for example . A wprt JobOriginatingUserName field stores the user name set to the element the element for example . The wprt JobId field stores a job ID set to the element the element for example and having been input by the printer .

More specifically a job ID 888 is set in the wprt JobId field of a row corresponding to the No. 1 print job in the example illustrated in . This indicates that the printer currently executes printing of the corresponding print job and a job ID corresponding thereto has been already input.

A value Null is set in the wprt JobId field of each of rows corresponding to the Nos. 2 through 8 jobs and reservations in the example illustrated in . This indicates that the printer has only accepted the reservation of the print job request and printing thereof has not been executed so that no job ID has been input.

For example a job ID 888 is set in the wprt JobId field of the row corresponding to the No. 1 print job in the example illustrated in . This state indicates that the printer currently executes printing of the print job and a job ID corresponding thereto has already been issued.

Values 888 890 and 1001 are set in the wprt JobId field of the rows corresponding to the No. 2 through 4 print jobs in the example illustrated in . This indicates that the printer has received the print jobs and job IDs corresponding thereto have been already issued.

Values Null Null and are set in the wprt JobId field of the rows corresponding to the No. 5 through 8 job reservations in the example illustrated in . This state indicates that the printer has only accepted the reservations of the print jobs and printing thereof has not been executed so that no job ID has been issued.

The value is set to the wprt JobId field for the Nos. 2 5 and 8 print jobs and reservations. This state indicates that the data is undefined unavailable because no element exists in the IHV native protocol.

In the examples illustrated in an ans SplJobId field stores a job ID input by the spooler and set to the element the element or the element for example . Suppose that a user serially and repeatedly prints the same document from one PC for a large number of times. In this case if the spooler is capable of printing a plurality of print jobs in parallel processing by using a plurality of threads the print job name set to the element the element for example included in CreatePrintJobRequest and the user name set to the element the element for example may become the same print job name and the same user name among the plurality of print job requests. Accordingly in this case the print job requests cannot be uniquely identified from one another.

In order to solve the above described problem the print jobs can be discriminated from one another if the job ID input by the spooler is included in the information stored in the print queue database.

A Time field illustrated in stores a time count value indicating the time of reception of a print job request input by the PC or a request for verifying a reservation of a print job request. In the example illustrated in an ans ReceivedId field stores a print reservation ID set to the element the element or the element . In the example illustrated in a Protocol field is a communication protocol used for the network communication between the PC and the printer . In the present exemplary embodiment the WSD protocol or the IHV native protocol is set to the Protocol field.

Referring to a Protocol field stores a communication protocol used for the network communication between the PC not illustrated and the printer or the local USB communication between the PC and the printer . In the present exemplary embodiment a WSD protocol an IHV native protocol IHV Native for network communication or another IHV native protocol IHV Native 2 for local USB communication is set to the Protocol field.

In the example illustrated in each of an ans ReceivedId lans TimeStamp field stores a print reservation ID set to the element the element or the element or the time stamp set to the element the element which is input by the printer to the PC by using the IHV native protocol. The time stamp is equivalent to the print reservation ID of the IHV native protocol. The time stamp is assigned to each print job request as a unique value. To paraphrase this the printer can use the time stamp as the job ID equivalent to the job ID of the element of WSD.

By defining the print reservation ID and the time stamp in the same format as described above the present exemplary embodiment can centrally manage reservations of print job requests. Accordingly the present exemplary embodiment can readily manage and control reservations of print job requests.

The language monitor the language monitor by utilizing the APIs for controlling the IHV native protocol can transmit arbitrary information to the printer by utilizing the IHV native protocol and receive arbitrary information from the printer .

Therefore if the IHV native protocol is utilized it is not necessary to employ a method which is otherwise necessary when the WSD protocol is utilized for reserving print job requests by inputting one print job request by executing two a plurality of operations including the CreatePrintJob operation processing S or step S and the GetPrinterElements operation processing S or step S .

Accordingly if the IHV native protocol is utilized one print job request can be input based on a print job start request only which is equivalent to the CreatePrintJob operation step S illustrated in in the case of using the WSD protocol. More specifically one print job request can be input based on the StartJob operation only.

More specifically suppose that a Windows Vista OS is installed on the PC and if a Windows XP OS is installed on another PC on the network . In this case print jobs that utilize the WSD protocol and print jobs that utilize the IHV native protocol are input by each PC and exist in a mixed state.

As described above even in the environment in which print jobs of a plurality of types of protocols mixes with each other and coexist the present exemplary embodiment can implement a highly useful peripheral apparatus control system capable of printing print jobs input by each PC in the correct order of input thereof by utilizing the print queue database illustrated in .

In addition in the printing using the USB interface by utilizing the IHV native protocol for USB and by utilizing the print queue database illustrated in the present exemplary embodiment can also implement a highly useful peripheral apparatus control system capable of printing print jobs input by each PC via the network and print jobs input by the PC via the USB interface in the correct order of input thereof.

Referring to a port of PC currently executing printing field stores information about the port used when the PC currently executes printing. A port of PC waiting for printing stores information about the port used in printing whose print job is in a waiting state.

In the port of PC currently executing printing field and the port of PC waiting for printing field a value USB corresponds to a USB port used for executing printing via the USB interface . A value WSD protocol corresponds to a network port for executing printing via the network by utilizing the WSD protocol. Furthermore a value IHV Native corresponds to a network port for executing printing via the network by utilizing the IHV native protocol.

A Device ID INFO field stores a value set to the information INFO included in the Device ID. The information stored in the Device ID INFO field includes information about the status of the printer in relation to the PC in the present exemplary embodiment the PC .

If the printer has been powered on but is in a standby online state a value 000 is set to the information Device ID INFO INFO 000 .

In the following description the value set to the information Device ID INFO has the following significance.

The PC can increase the operability of the user by displaying the following message on the application such as a status monitor that monitors and displays the status of the printer based on the above described information.

Suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value USB if the port of PC waiting for printing field has a value IHV Native and if the PC has acquired the Device ID from the printer by utilizing the IHV native protocol then the printer returns the Device ID whose information INFO has a value 101 .

On the other hand suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value USB if the port of PC waiting for printing field has a value WSD and if the PC has acquired the Device ID from the printer by utilizing the GetPrinterElements wprt PrinterDescription then the printer returns the Device ID whose information INFO has a value 101 .

Furthermore suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value IHV Native if the port of PC waiting for printing field has a value IHV Native and if the PC has acquired the Device ID from the printer by utilizing the IHV native protocol then the printer returns the Device ID whose information INFO has a value 102 .

Further still suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value IHV Native if the port of PC waiting for printing field has a value WSD and if the PC has acquired the Device ID from the printer by utilizing the GetPrinterElements wprt PrinterDescription then the printer returns the Device ID whose information INFO has a value 102 .

Moreover suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value WSD if the port of PC waiting for printing field has a value IHV Native and if the PC has acquired the Device ID from the printer by utilizing the IHV native protocol then the printer returns the Device ID whose information INFO has a value 102 .

Still more suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value WSD if the port of PC waiting for printing field has a value WSD and if the PC has acquired the Device ID from the printer by utilizing the GetPrinterElements wprt PrinterDescription then the printer returns the Device ID whose information INFO has a value 102 .

In the example illustrated in during printing by the printer from the PC via the USB interface a message currently used by other interface or the like can be displayed on a status monitor on the PC . Meanwhile in this case a message most appropriate to be displayed on the status monitor on the PC is currently used by other computer .

Suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value USB if the port of PC waiting for printing field has a value IHV Native and if the PC has acquired the Device ID from the printer by utilizing the IHV native protocol then the printer returns the Device ID whose information INFO has a value 102 .

On the other hand suppose that a print job input by the PC is currently printed by the printer . In this case if the port of PC currently executing printing field has a value USB if the port of PC waiting for printing field has a value WSD and if the PC has acquired the Device ID from the printer by utilizing the GetPrinterElements wprt PrinterDescription then the printer returns the Device ID whose information INFO has a value 102 .

In the present exemplary embodiment the print control command for controlling the printer via the USB interface and the corresponding Device ID are the same as the print control command for controlling the printer via the network and the corresponding Device ID respectively. The present exemplary embodiment implements the above described control by merely changing the protocol including the command.

In the present exemplary embodiment it is supposed that the printer has previously initialized the new job flag by using a value 0 during booting. Referring to in step S CreatePrintJobRequest is input by the PC the PC to the printer and the printer receives the input CreatePrintJobRequest. After the printer has received the input CreatePrintJobRequest in step S the processing advances to step S. In step S the printer acquires the count value based on which the present time and the elapsed time can be calculated from the timer built in to the printer . Furthermore in step S the printer stores the acquired count value to Time. The count value is counted in the unit of second sec .

In step S the printer acquires the print job name set to the element and the user name set to the element from the CreatePrintJobRequest. In step S the printer acquires the computer name Computer Name of the PC .

In the present exemplary embodiment an Internet protocol IP address is acquired from a transmission control protocol TCP reception socket in hypertext transport protocol HTTP POST command addressed to the WSD Print Service. Furthermore the computer name is acquired according to the acquired IP address.

In the present exemplary embodiment for easier understanding the computer name is acquired from the IP address the PC is identified based on the acquired computer name and each processing is executed in this state. However the PC can be identified by using the IP address to execute each processing.

In step S the printer temporarily stores the print job name the user name and the computer name. In step S based on the print job name the user name and the computer name the printer verifies whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S may already exist within the print queue database illustrated in .

In step S the printer determines whether a reservation of the print job request may already exist within the print queue database illustrated in . If it is determined that a reservation of the print job request may already exist within the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that it is not likely that a reservation of the print job request already exists within the print queue database illustrated in No in step S then the processing advances to step S. In step S the printer determines whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in . If it is determined that a reservation of the print job request exists within the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that it is not likely that a reservation of the print job request exists within the print queue database illustrated in No in step S then the processing advances to step S. In step S the printer registers the print job request of the print job whose start has been requested by the CreatePrintJobRequest received in step S to the print queue database illustrated in .

In step S the printer returns CreatePrintJobResponse to the PC the PC as a response indicating that the print job request CreatePrintJobRequest received in step S is accepted and executed. In step S the processing for CreatePrintJob ends.

In step S the printer determines whether the value of the new job flag is 1 . If it is determined that the value of the new job flag is 1 Yes in step S then the processing advances to step S. On the other hand if it is determined that a value 0 has been set No in step S then the processing advances to step S.

In step S the printer subtracts Time stored in step S from Time stored in step S to calculate the time elapsed the difference in the request reception time from the timing of reception by the printer of the GetPrinterElementsRequest in step S to the timing of reception by the printer of the CreatePrintJobRequest in step S.

If the elapsed time exceeds five seconds Yes in step S then the processing advances to step S. On the other hand if the elapsed time is less than five seconds No in step S then the processing advances to step S.

In step S the printer searches for a reservation of the print job request having the information same as the print job name the user name and the computer name stored in step S within the print queue database illustrated in based on the print job name the user name and the computer name.

In addition the printer acquires the print reservation ID set to the ans ReceivedId field and the job ID input by the spooler and having been set in the ansSplJobId field from the print queue database and temporarily stores the acquired print reservation ID and the job ID.

In step S the printer acquires the print reservation ID set to the element the element and the job ID input by the spooler and having been set to the element the element from the information included in the element the element or the element stored in step S illustrated in .

In step S the printer compares the print reservation ID acquired in step S and the job ID input by the spooler with the print reservation ID temporarily stored in step S and the job ID input by the spooler respectively. In addition in step S the printer compares the print job name the user name and the computer name acquired from the print queue database based on the print reservation ID temporarily stored in step S with the print job name the user name and the computer name temporarily stored in step S.

If it is determined as a result of the comparison among all comparison target information that all comparison target information match one another Yes in step S then the processing advances to step S. On the other hand if it is determined that at least one piece of information that does not match the other such information exists No in step S then the processing advances to step S.

In step S the printer verifies the print queue database illustrated in . If it is determined that a reservation of another print job request having a priority higher than the priority of the print job whose start has been requested by the CreatePrintJobResponse received in step S exists within the print queue database Yes in step S then the processing advances to step S. On the other hand if it is determined that no such reservation of print job request exists within the print queue database No in step S then the processing advances to step S.

In step S the printer sets a value 1 to the new job flag. In step S the printer in response to the print job request CreatePrintJobRequest received in step S returns Fault ServerErrorNotAcceptingJobs which describes that the print job has not been accepted to the PC the PC . In step S the processing for CreatePrintJob ends.

Referring to in step S GetPrinterElementsRequest A and A is input by the PC the PC to the printer and the printer receives the input GetPrinterElementsRequest. In step S the printer receives the GetPrinterElementsRequest. In step S the printer verifies the value set to the element or from the received GetPrinterElementsRequest.

In step S in order to respond to a case where a plurality of elements exists in the GetPrinterElementsRequest the printer temporarily stores the received values set to all the elements . If wprt PrinterDescription has been extracted as the value set to the element Yes in step S then the processing advances to step S. On the other hand if wprt PrinterDescription has not been extracted No in step S then the processing advances to step S.

In step S the printer verifies all values set to the element and having been stored in step S. If ans ABCCommand has been extracted YES in step S then the processing advances to steps S. On the other hand if ans ABCCommand has been extracted No in step S then the processing advances to step S.

In step S the printer acquires a count value based on which the present time or the elapsed time can be calculated from the timer built in to the printer and stores the acquired count value to Time. The count value is counted in the unit of second sec .

In step S the printer acquires all information included in the element or the element included in the GetPrinterElementsRequest and stores the acquired information.

In step S the printer determines whether the value of the new job flag is 1 . If it is determined that the value of the new job flag is 1 Yes in step S then the processing advances to step S. On the other hand if it is determined that the value of the new job flag is not 1 i.e. if a value 0 has been set No in step S then the processing advances to step S.

In step S the printer subtracts Time stored in step S from Time and calculates the elapsed time the difference in the request reception time from the timing of reception by the printer of the CreatePrintJobRequest in step S to the timing of reception by the printer of the GetPrinterElementsRequest in step S.

If the elapsed time exceeds five seconds Yes in step S then the processing advances to step S. On the other hand if the elapsed time is less than five seconds No in step S then the processing advances to step S.

In step S the printer determines whether the value set to the element or the element is 0 . If it is determined that a value 0 has been set to the element Yes in step S then the processing advances to step S. On the other hand if it is determined that a value other than 0 actually an integer greater than 0 has been set to the element No in step S then the processing advances to step S.

In step S the printer executes processing for inputting a print reservation ID illustrated in . By executing the processing illustrated in the printer determines whether a value None has been set to the element or the element . If a value None has been set to the element Yes in step S then the processing advances to step S. On the other hand if it is determined that a value None is not set to the element No in step S then the processing advances to step S.

In step S if the processing has gone through step S the printer registers each information in the print queue database illustrated in as the reservation of the print job request based on a print reservation ID ans ReceivedId newly input in step S . If the processing has gone through step S No in step S the printer registers each information in the print queue database as a reservation of an existing print job request based on an existing print reservation ID ans ReceivedId and updates the print queue database. In step S the printer also updates the time count value set in the Time field by using the value stored in Time at this timing. In step S the printer initializes the new job flag with a value 0 .

In step S the printer sets each information to GetPrinterElementsResponse by using the information set in step S information set in step S and the information set in the print queue database illustrated in . In addition in step S the printer returns the GetPrinterElementsResponse to the PC the PC in response to the GetPrinterElementsRequest received in step S. In step S the processing for GetPrinterElements ends.

In step S the printer acquires the print reservation ID for example the element set to the element . In step S the printer verifies whether the print reservation ID exists in the ans ReceivedId field or the ans ReceivedId lans TimeStamp field included in the print queue database illustrated in .

If it is determined in step S that a print reservation ID corresponding to the reservation of the print job request exists within the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that no print reservation ID corresponding to the reservation of the print job request exists within the print queue database illustrated in No in step S then the processing advances to step S.

In step S the printer acquires the time count value set in the Time field corresponding to the print job request reserved with the print reservation ID from the print queue database illustrated in . In addition the printer measures the elapsed time from the timing of the last update of the reservation of the print job by subtracting the acquired time count value from Time stored in step S.

If it is determined that the elapsed time exceeds a predetermined time in the present exemplary embodiment twenty seconds Yes in step S then the processing advances to step S. On the other hand if it is determined that the elapsed time does not exceed the predetermined time No in step S then the processing advances to step S.

In step S the printer once deletes print reservation ID ans ReceivedId of the print job request from the print queue database illustrated in . In addition the printer moves the print job request to the tail end of the print queue database so that the print job request becomes the reservation of the print job request having the lowest priority. Then the processing advances to step S.

In step S and step S the fixed timeout value of five seconds is set as the value based on which whether the predetermined time has elapsed. However the present exemplary embodiment is not limited to this. More specifically according to the environment of use of the printer or the environment of the network used by the user any other fixed timeout value of three eight or ten seconds can be set. Alternatively the user can operate the touch panel of the display unit or the operation unit of the printer to set an arbitrary value appropriate for the environment of use of the printer .

In addition the following configuration can be employed. More specifically the printer monitors the PC on the network . The printer recognizes the status of the network traffic according to the number of the PCs on the network . Furthermore the printer can set an optimum timeout value according to the status of the network traffic.

In addition different values can be used for the timeout value used in step S and the timeout value used in step S instead of using the same value therefor. In this case the timeout value used in step S is set at five seconds while the timeout value used in step S is set at three seconds.

When the printer executes the processing for inputting a print reservation ID in step S the processing illustrated in starts from step S. In step S the printer verifies the status of the free field of the print queue database illustrated in . If it is determined that a free field exists in the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that no free field exists No in step S then the processing advances to step S.

In step S the printer newly inputs a print reservation ID ans ReceivedId . In addition the printer sets the print reservation ID to the element or the element . In step S the processing for inputting a print reservation ID ends. Then the processing advances to step S . The print reservation ID input in step S is managed by the printer and is a value uniquely determined within the printer .

In step S the printer sets a value None to the element or the element . In step S the processing for inputting a print reservation ID ends. Then the processing advances to step S .

As described above if any free field that can accept a new print job request does not exist in the print queue database illustrated in the printer cannot accept a reservation of a print job request from the PC the PC . In this case the PC the PC inputs a print job request again according to the calling sequence illustrated in . Accordingly if a free field with which a new print job request can be accepted exists in the print queue database illustrated in the printer accepts the reservation of the print job request.

When the interruption occurs at every 180 seconds according to the count value counted by the timer built in to the printer the processing illustrated in starts. More specifically in step S the processing illustrated in starts when the interruption occurs according to the count value counted by the timer built in to the printer .

In step S the printer acquires a count value based on which the present time and the elapsed time can be calculated from the timer built in to the printer and stores the acquired count value in Time. The count value is counted in the unit of second sec .

In step S the printer acquires and verifies the content of the reservation having the highest priority from among reservations of print job requests included in the print queue database illustrated in . In step S the printer acquires the time count value set to the Time field from the reservation of the print job request acquired in step S.

In step S the printer subtracts the time count value acquired in step S from Time. If the result of the subtraction in step S exceeds a predetermined time sixty seconds Yes in step S then the processing advances to step S. On the other hand if it is determined that the subtraction result does not exceed the predetermined time of sixty seconds No in step S then the processing advances to step S.

In step S the printer deletes the reservation of the print job request acquired in step S from the print queue database illustrated in . Then the processing advances to step S. At the same time the printer also deletes the print reservation ID ans ReceivedId of the print job request therefrom.

In step S the printer determines whether the result of the subtraction in step S exceeds a predetermined time of twenty seconds. If it is determined that the result of the subtraction in step S exceeds the predetermined time of twenty seconds Yes in step S then the processing advances to step S. On the other hand if it is determined that the result of the subtraction in step S does not exceed the predetermined time of twenty seconds No in step S then the processing advances to step S. In the present exemplary embodiment the same twenty seconds as set in step S is set as the predetermined time twenty seconds .

In step S the printer once deletes the print reservation ID ans ReceivedId of the print job request acquired in step S from the print queue database illustrated in . In addition the printer moves the print job request to the tail end of the print queue database so that the print job request is reserved as the reservation of the print job request having the lowest priority. Then the processing advances to step S.

In step S the printer determines whether the reservations of all the print job requests have been completely verified. If it is determined that the reservations of all the print job requests have been completely verified Yes in step S then the processing advances to step S and the processing of interruption for updating the print queue database ends there. On the other hand if it is determined that the reservations of all the print job requests have not been completely verified No in step S then the processing advances to step S.

In step S the printer proceeds to the processing of the reservation of the print job request having the second highest priority at the time of the acquisition of the reservation of the print job request in step S within the print queue database illustrated in . Then the processing returns to step S. In the present exemplary embodiment the interval of the interruption by timer is set at 180 seconds. However the present exemplary embodiment is not limited to this. More specifically a different other arbitrary interval can be set. Alternatively the user can operate the touch panel of the display unit or the operation unit of the printer to set an arbitrary value appropriate for the environment of use of the printer .

In step S and step S the fixed timeout value of twenty seconds is set as the value based on which whether the predetermined time has elapsed. However the present exemplary embodiment is not limited to this. More specifically according to the environment of use of the printer or the environment of the network used by the user any other fixed timeout value of ten thirty or sixty seconds can be set. Alternatively the user can operate the touch panel of the display unit or the operation unit of the printer to set an arbitrary value appropriate for the environment of use of the printer .

In addition the following configuration can be employed. More specifically the printer monitors the PC on the network . The printer recognizes the status of the network traffic according to the number of the PCs on the network . Furthermore the printer can set an optimum timeout value according to the status of the network traffic.

In step S the fixed timeout value of sixty seconds is set as the value based on which it is determined whether the predetermined time has elapsed. However the present exemplary embodiment is not limited to this. More specifically according to the environment of use of the printer or the environment of the network used by the user any other fixed timeout value of thirty ninety or 120 seconds can be set. Alternatively the user can operate the touch panel of the display unit or the operation unit of the printer to set an arbitrary value appropriate for the environment of use of the printer .

In addition the following configuration can be employed. More specifically the printer monitors the PC on the network . the printer recognizes the status of the network traffic according to the number of the PCs on the network . Furthermore the printer can set an optimum timeout value according to the status of the network traffic.

In the examples illustrated in and the count value acquired from the timer built in to the printer is utilized for the method for calculating the elapsed time. However the present exemplary embodiment is not limited to this. More specifically the time acquired from a real time clock built in to the printer can be utilized to implement the function of the present invention.

In the present exemplary embodiment the printer is used as the peripheral apparatus. However the present invention can be implemented by a multifunction peripheral MFP including a printer a facsimile apparatus a scanner and a storage device.

If the MFP includes the WSD the following WSD services can be assigned to the functions of the MFP such as the printer function the facsimile transmission function and the scanner function.

The Print Service is assigned to both the printer function and the facsimile transmission function. The ServiceID differs for the printer function and the FAX transmission function. Accordingly the ServiceType of both the printer function and the FAX transmission function is PrinterServiceType.

As described above the language monitor is capable of inputting GetPrinterElementsRequest from the PC to the printer and receive the GetPrinterElementsResponse returned from the printer to the PC by using the function GetPrinterElements of the WSD APIs.

In this case by designating the ServiceType in the function GetPrinterElements and by calling the function as described below the GetPrinterElements can be utilized.

However if the above described MFP is used the ServiceType of both the printer function and the FAX transmission function is the same type PrinterServiceType . Accordingly if the ServiceType is designated and the function is called in this state the printer function and the FAX transmission function cannot be identified from each other and unique information for each such function cannot be acquired.

In order to solve the above described problem if the MFP described above is used the following configuration can be employed. More specifically the language monitor designates the ServiceID and calls the function to designate the printer function or the FAX transmission function. In this manner the printer can acquire the information about the designated function by utilizing the GetPrinterElements.

By employing the above described configuration if the MFP having the printer function and the FAX transmission function is used the present exemplary embodiment having the above described configuration can implement the peripheral apparatus control system capable of preventing a malfunction and executing a correct and appropriate control.

CreatePrintJobRequest is a print job start request in the WSD Print Service. GetPrinterElementsRequest is a request for acquiring printer information in the WSD Print Service.

As described above in the present exemplary embodiment information included in each of the CreatePrintJobRequest received in step S and GetPrinterElementsRequest ans ABCCommand received within a predetermined time period five seconds in is associated with each other. Furthermore the information is handled as a reservation of one print job request and is registered in the print queue database. Furthermore the reservation of the print job request is managed according to the print reservation ID uniquely determined within the printer .

In other words if different two requests such as a print job start request and a printer information acquisition request have been received within a predetermined time period the present exemplary embodiment mutually associates the information included in the requests handles the same as the reservation of one print job request and registers the same in the print queue database. In addition the reservation of the print job request is managed according to the print reservation ID uniquely determined within the printer .

With the above described configuration if a printer that cannot receive a plurality of print jobs but can receive one print job only is used the present exemplary embodiment can cause the printer to print a plurality of print jobs input by one or more PCs correctly and appropriately in order of input thereof.

Now a second exemplary embodiment of the present invention will be described in detail below. In the first exemplary embodiment described above if a user serially prints the same document from one PC the spooler is capable of processing the print jobs in parallel by using a plurality of threads.

In this case if the spooler is capable of printing a plurality of print jobs in parallel processing by using a plurality of threads the print job name set to the element the element for example included in CreatePrintJobRequest and the user name set to the element the element for example may become the same print job name and the user name among the plurality of print job requests. Accordingly in this case the print job requests cannot be uniquely identified from one another.

In order to solve the above described problem in the first exemplary embodiment described above the job ID input by the spooler is included in the information to be stored in the print queue database to uniquely identify each print job.

In addition as an easiest method executed by the printer for centrally managing the reservations of print job requests the print reservation ID set to the element or the element or the time stamp which is equivalent to the print reservation ID and set to the element is utilized.

Suppose as another exemplary case that a user serially and repeatedly prints the same document from one PC and if the spooler cannot process the print jobs in parallel by using a plurality of threads and that a print job having a highest priority is sequentially processed by one thread.

In this case if the user serially and repeatedly prints the same document from one PC the spooler processes only the print job having the highest priority among jobs stacked in the printer queue .

Accordingly if only the WSD protocol is utilized the reservations of the print job requests can be centrally managed by using three types of information i.e. the computer name stored in the Computer Name field the print job name stored in the wprt JobName field and the user name stored in the wprt JobOriginatingUserName field which is described in the print queue database without using the print reservation ID or the time stamp.

Suppose that the WSD protocol and the IHV native protocol exists in a mixed state. In this case by adding information such as the print job name and the user name to the StartJob illustrated in the reservations of the print job requests can be centrally managed without using the print reservation ID and the time stamp.

However the present exemplary embodiment is useful but useful only in a case where the spooler cannot process a plurality of print jobs in parallel by using a plurality of threads and the print job having the highest priority is sequentially processed by one thread.

As an example of the IHV native protocol an IHV native protocol IHV Native for network or an IHV native protocol IHV Native for local USB communication can be used.

Now a print queue database and processing according to the present exemplary embodiment will be described in detail below with reference to . illustrates an example of a print queue database that manages a print job request that the printer has received and registered as a reservation. The example illustrated in most effectively illustrates characteristics of the present invention.

The print queue database illustrated in is substantially similar to that illustrated in except that the print queue database illustrated in does not include the ans ReceivedID lans TimeStamp field which is included in the print queue database illustrated in . Accordingly the detailed description of the configuration of the print queue database similar to that described above in the first exemplary embodiment with reference to will not be repeated here.

The ans ReceivedID lans TimeStamp field stores a print reservation ID that has been set to the element or and information including a time stamp which have been given by the printer to the PC by using the IHV native protocol and set to the element . As described above the print queue database illustrated in does not include the ans ReceivedID lans TimeStamp field. Accordingly it is not necessary to store the print reservation ID or the time stamp.

After the printer has received the input CreatePrintJobRequest in step S the processing advances to step S. In step S the printer acquires the count value based on which the present time and the elapsed time can be calculated from the timer built in to the printer . Furthermore in step S the printer stores the acquired count value in Time. The count value is counted in the unit of second sec .

In step S the printer acquires the print job name set to the element and the user name set to the element from the CreatePrintJobRequest. In step S the printer acquires the computer name Computer Name of the PC .

In the present exemplary embodiment an IP address is acquired from a TCP reception socket in an HTTP POST command addressed to the WSD Print Service. Furthermore the computer name is acquired according to the acquired IP address.

In the present exemplary embodiment for easier understanding the computer name is acquired from the IP address the PC is identified based on the acquired computer name and each processing is executed in this state. However the PC can be identified by using the IP address to execute each processing.

In step S the printer temporarily stores the print job name the user name and the computer name. In step S based on the computer name the printer verifies whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in .

In step S the printer determines whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in . If it is determined that a reservation of the print job request already exists within the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that no reservation of the print job request exists within the print queue database illustrated in No in step S then the processing advances to step S.

In step S the printer acquires the time count value set in the Time field corresponding to the print job request reserved with the computer name from the print queue database illustrated in . In addition the printer measures the elapsed time from the timing of the last update of the reservation of the print job by subtracting the acquired time count value from Time stored in step S.

If it is determined that the elapsed time exceeds a predetermined time in the present exemplary embodiment twenty seconds Yes in step S then the processing advances to step S. On the other hand if it is determined that the elapsed time does not exceed the predetermined time No in step S then the processing advances to step S.

In step S in the print queue database illustrated in the printer moves the print job request to the tail end of the print queue database so that the print job request becomes the reservation of the print job request having the lowest priority. Then the processing advances to step S. In this case if no free field exists within the print queue database illustrated in then the printer discards the reservation of the print job request i.e. the printer does not store the reservation of the print job request in the print queue database .

In step S the printer updates the print queue database by registering each information in the print queue database illustrated in as a reservation of the print job request based on the computer name. More specifically the printer updates the time count value set to the Time field with the value stored in Time.

In step S the printer registers the print job request of the print job whose start has been requested by the CreatePrintJobRequest received in step S in the print queue database illustrated in . In step S the printer determines whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in . If it is determined that a reservation of the print job request may already exist within the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that it is not likely that a reservation of the print job request exists within the print queue database illustrated in No in step S then the processing advances to step S.

In step S the printer returns CreatePrintJobResponse to the PC the PC as a response indicating that the print job request CreatePrintJobRequest received in step S is accepted and executed. Then the processing advances to step S. In step S the processing for CreatePrintJob ends.

In step S the printer in response to the print job request CreatePrintJobRequest received in step S returns Fault ServerErrorNotAcceptingJobs which describes that the print job has not been accepted to the PC the PC . Then the processing advances to step S. In step S the processing for CreatePrintJob ends.

Referring to in step S GetPrinterElementsRequest is input by the PC the PC to the printer and the printer receives the input GetPrinterElementsRequest. After receiving the GetPrinterElementsRequest in step S the printer in step S verifies the value set to the element from the received GetPrinterElementsRequest and temporarily stores the received values set in all the elements .

In step S in order to respond to a case where a plurality of elements is extracted from the GetPrinterElementsRequest in step S the printer determines whether wprt PrinterDescription has been extracted as the value set to the element . If wprt PrinterDescription has been extracted as the value set to the element Yes in step S then the processing advances to step S. On the other hand if wprt PrinterDescription has not been extracted No in step S then the processing advances to step S.

In step S the printer sets a value true to the function . Then the processing advances to step S. In step S the printer acquires a count value based on which the present time or the elapsed time can be calculated from the timer built in to the printer and stores the acquired count value to Time. The count value is counted in the unit of second sec .

In step S the printer acquires the computer name Computer Name of the PC . In step S based on the computer name the printer verifies whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in .

In step S the printer determines whether a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in . If it is determined that a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in Yes in step S then the processing advances to step S. On the other hand if it is determined that a reservation of a print job request for the print job whose start has been requested by the CreatePrintJobRequest received in step S exists within the print queue database illustrated in No in step S then the processing advances to step S.

In step S the printer acquires the time count value set in the Time field corresponding to the print job request reserved with the computer name from the print queue database illustrated in . In addition in step S the printer measures the elapsed time from the timing of the last update of the reservation of the print job by subtracting the acquired time count value from Time stored in step S.

In step S the printer determines whether the elapsed time exceeds a predetermined time in the present exemplary embodiment twenty seconds . If it is determined that the elapsed time exceeds the predetermined time Yes in step S then the processing advances to step S. On the other hand if it is determined that the elapsed time does not exceed the predetermined time No in step S then the processing advances to step S.

In step S in the print queue database illustrated in the printer moves the print job request to the tail end of the print queue database so that the print job request becomes the reservation of the print job request having the lowest priority. Then the processing advances to step S. In this case if no free field exists within the print queue database illustrated in then the printer discards the print job request i.e. the printer does not store the reservation of the print job request in the print queue database .

In step S the printer updates the print queue database by registering each information in the print queue database illustrated in as a reservation of the print job request based on the computer name. More specifically the printer updates the time count value set to the Time field with the value stored in Time.

In step S the printer returns the GetPrinterElementsResponse to the PC the PC in response to the GetPrinterElementsRequest received in step S. In step S the processing for GetPrinterElements ends.

Each function according to a third exemplary embodiment of the present invention which can be implemented by executing the calling sequence illustrated in each of and and the processing illustrated in the flow charts of each of and can be implemented by an information processing apparatus using a program externally installed on the information processing apparatus.

In this case the present invention can also be applied when a group of information or codes including the program is supplied to the information processing apparatus or a peripheral apparatus from a storage medium such as a CD ROM a flash memory or a flexible disk or from an external storage medium via a network.

The present invention can also be achieved by providing a system or an apparatus with a storage medium storing program code of software implementing the functions of the embodiments and by reading and executing the program code stored in the storage medium with a computer of the system or the apparatus a CPU or a micro processing unit MPU . In this case the program code itself which is read from the storage medium implements the functions of the embodiments described above and accordingly the storage medium storing the program code constitutes the present invention.

As the storage medium for supplying such program code a flexible disk a hard disk an optical disk a magneto optical disk a magneto optic disk MO a CD ROM a compact disc recordable CD R a magnetic tape a nonvolatile memory card a ROM and an electrically erasable programmable ROM EEPROM for example can be used.

In addition the functions according to the embodiments described above can be implemented not only by executing the program code read by the computer but also implemented by the processing in which an OS or the like carries out a part of or the whole of the actual processing based on an instruction given by the program code.

In each exemplary embodiment of the present invention a color inkjet printer is used as an example of the printer. However the present invention is not limited to this. More specifically an arbitrary printer such as a monochromatic laser beam printer LBP can be used.

In each exemplary embodiment of the present invention a PC is used as the information processing apparatus. However the present invention is not limited to this. More specifically an arbitrary information processing apparatus terminal that can be used in the similar manner as described above such as a digital versatile disc DVD player a gaming machine a set top box or a network home appliance can be effectively used to implement the function of the present invention.

In each exemplary embodiment of the present invention a printer is used as an example of the peripheral apparatus. However the present invention is not limited to this. More specifically as the peripheral apparatus a copying machine a facsimile transmission machine a scanner a determination condition or an apparatus having a combination of functions of the above described apparatuses can be used to implement the functions of the present invention.

Furthermore in each exemplary embodiment of the present invention an OS equivalent to a Windows Vista OS is used. However the present invention is not limited to this. More specifically an arbitrary OS can be used. Moreover in each exemplary embodiment of the present invention the network includes Ethernet . However the present invention is not limited to this. More specifically a different arbitrary network configuration can also be used.

In addition in each exemplary embodiment of the present invention USB and Ethernet are used as the interface among the PC the PC and the PC and the printer . However the present invention is not limited to this. More specifically an arbitrary interface such as a wireless LAN Institute of Electrical and Electronic Engineers IEEE 1394 or Bluetooth can be used.

In each exemplary embodiment of the present invention the WSD is used as an example of a web service protocol. However a different arbitrary protocol such as an IHV native protocol can be used instead. In an exemplary embodiment of the present invention an IP address is acquired from a TCP reception socket of HTTP POST addressed to the WSD Print Service. In addition in each exemplary embodiment of the present invention the computer name is acquired according to the IP address and the PC is uniquely identified according to the acquired computer name.

However the PC can be identified by using a method different from the above described method. More specifically the PC can also be identified by utilizing a different unit capable of acquiring an IP address from the TCP reception socket of HTTP POST addressed to WSD Print Service and identifying the PC by using the IP address. BY utilizing the IP address it becomes unnecessary to handle or consider using two byte codes within the WSD protocol. Accordingly the program can have a simple configuration. Therefore the present invention can reduce mistakes in coding to a minimum. Accordingly the quality of the program can be improved by the present invention having the above described configuration.

In an exemplary embodiment of the present invention the printer receives the reservation of the print job request by utilizing the CreatePrintJob operation S and step S in which is a print job start request and the GetPrinterElements operation S and step S utilized to acquire printer information.

However the present invention is not limited to this. More specifically instead of the GetPrinterElements operation a different operation defined by the Definition of the WSD Print Service such as the GetJobElements operation can be performed which is utilized in acquiring the information about a print job.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiment s and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiment s . For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium . For example aspects of the present invention can also be realized by a computer readable medium storing computer executable instructions which when executed by a computer cause the computer to function as an apparatus disclosed herein and or perform a method disclosed herein.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

