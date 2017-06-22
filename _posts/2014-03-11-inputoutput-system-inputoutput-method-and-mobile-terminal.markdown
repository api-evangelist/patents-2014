---

title: Input/output system, input/output method, and mobile terminal
abstract: An input/output system interconnects a mobile terminal, a cooperative processing apparatus, and a plurality of electronic devices, and is configured to implement a cooperative process of prompting an electronic device corresponding to an input apparatus to input electronic data and prompting an electronic device corresponding to an output apparatus to output the input electronic data. The input/output system includes an acquisition unit that acquires input/output apparatus information from the electronic device corresponding to the input/output apparatus, an input control unit that controls the electronic device specified by the input apparatus information to input electronic data, and an output control unit that controls the electronic device specified by the output apparatus information to output the input electronic data in an output format compatible with the electronic device specified by the output apparatus information if the electronic device is capable of directly outputting the input electronic data from the mobile terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09451432&OS=09451432&RS=09451432
owner: Ricoh Company, Ltd.
number: 09451432
owner_city: Tokyo
owner_country: JP
publication_date: 20140311
---
The present invention relates to an input output system an input output method and a mobile terminal.

In attempting to print data stored in a file server using a printer when data conversion between the file server and the printer is not prescribed the printer may not be able to process the data and may therefore be incapable of printing the data. Control systems for solving such a problem are known see e.g. Japanese Laid Open Patent Publication No. 2005 292903 .

Currently users use a variety of electronic devices for inputting outputting electronic data such as a printer a multifunction peripheral MFP and a projector and a variety of information processing apparatuses such as a mobile phone a smartphone and a tablet terminal. Systems using such electronic devices and information processing apparatuses may increase their utility value by enabling cooperation between a wide variety of electronic devices and information processing apparatuses.

However conventional systems using electronic devices and information processing apparatuses have no mechanism for enabling cooperation between an electronic device that inputs electronic data and an electronic device that outputs electronic data.

In view of the above one aspect of the present invention relates to providing an input output system an input output method and a mobile terminal that are capable of facilitating cooperation between an electronic device that inputs electronic data and an electronic device that outputs electronic data.

According to one embodiment of the present invention an input output system interconnects a mobile terminal a cooperative processing apparatus and a plurality of electronic devices and is configured to implement a cooperative process of prompting an electronic device corresponding to an input apparatus of the plurality of electronic devices to input electronic data and prompting an electronic device corresponding to an output apparatus of the plurality of electronic devices to output the input electronic data. The input output system includes an acquisition unit that prompts the mobile terminal to acquire input apparatus information specifying the electronic device corresponding to the input apparatus from the electronic device corresponding to the input apparatus and acquire output apparatus information specifying the electronic device corresponding to the output apparatus from the electronic device corresponding to the output apparatus an input control unit that controls the electronic device specified by the input apparatus information acquired by the acquisition unit to input electronic data and an output control unit that controls the electronic device specified by the output apparatus information acquired by the acquisition unit to output the electronic data input by the input control unit in an output format compatible with the electronic device specified by the output apparatus information in a case where the electronic device specified by the output apparatus information is capable of directly outputting the input electronic data from the mobile terminal.

According to an aspect of the present invention a mechanism may be provided for facilitating cooperation between an electronic device that inputs electronic data and an electronic device that outputs electronic data.

In the following certain illustrative embodiments of the present invention are described with reference to the accompanying drawings.

The network N may be a network within a private environment such as an intranet for example. The smartphone and the tablet terminal are examples of mobile terminals that may be carried and operated by a user. Note that examples of the mobile terminal are not limited to the smartphone and the tablet terminal but may also include other devices that may be carried and operated by a user such as a mobile phone and a notebook PC personal computer for example.

The MFP and the projector are examples of electronic devices corresponding to input output apparatuses that input output e.g. print scan project electronic data. The digital camera the microphone and the speaker are also examples of electronic devices that input output electronic data. Note that examples of electronic devices are not limited to the above but may include other devices that can input output electronic data such as a printer a scanner a copier and an image display apparatus for example.

The MFP may have an image capturing function an image forming function and a communication function and may be used as a printer a facsimile machine a scanner and a copier for example. The MFP may act as an image scanning apparatus that generates image data by scanning a document and an image forming apparatus that prints out outputs image data for example.

The MFP may also have a web browser function and may display a user interface UI by drawing HTML data stored within the information storage apparatus for example. Further the MFP may run a JavaScript registered trademark program on the UI to accept requests such as a print request or a scan request from a user. The projector is an example of an image display apparatus. The projector may have an image projection function and a communication function and may act as an image display apparatus that displays outputs image data. The digital camera is an example of an image capturing apparatus. The microphone and the speaker are examples of audio input output apparatuses.

The information storage apparatus is an example of a cooperative processing apparatus. The information storage apparatus may execute processes as a file server and sophisticated processes that cannot be performed by the MFP and the projector for example. The information storage apparatus cooperates with information processing apparatuses such as the smartphone and the tablet terminal to prompt electronic apparatuses such as the MFP and the projector to input output electronic data. Note that in some embodiments the information storage apparatus may be configured by a plurality of computers in a decentralized manner.

The information storage apparatus may be implemented by a computer system having a hardware configuration as illustrated in for example. Also other information processing apparatuses such as the smartphone and the tablet terminal may include the hardware configuration of . illustrates an exemplary hardware configuration of a computer system according to the present embodiment.

The computer system of includes an input device a display device an external I F a RAM a ROM a CPU a communication I F and a Hard Disk Drive HDD which are interconnected via a bus B. The input device may include a keyboard and a mouse for example and is used to input operation signals to the computer system .

The display device may include a display for example and is configured to display processing results of the computer system . The communication I F is an interface for connecting the computer system to the network N. In this way the computer system may establish data communication with other apparatuses such as the mobile terminals and electronic devices via the communication I F .

The HDD is a nonvolatile storage device storing programs and data. The programs stored in the HDD may include an Operating System OS corresponding to basic software controlling the overall computer system and application software providing various functions under the control of the OS for example. The HDD manages the stored programs and data using a predetermined file system and or DataBase DB .

The external I F is an interface between the computer system and external devices. The external devices may include a recording medium for example. In this way the computer system may read write information from on the recording medium via the external I F . Examples of the recording medium include a flexible disk a CD a Digital Versatile Disk DVD a SD memory card a Universal Serial Bus memory USB memory etc.

The ROM is a nonvolatile semiconductor memory storage device and thus can retain programs and or data even after the power is turned off. The ROM may store programs and data such as a Basic Input Output System BIOS to be executed when the computer system is started OS settings and network settings for example. The RAM is a volatile semiconductor memory storage device that temporarily stores programs and or data.

The CPU is a processing unit that controls overall operations and functions of the computer system by reading programs and or data from storage device s such as the ROM and or HDD to the RAM and executing corresponding processes.

The computer system according to the present embodiment may implement various processes described below using the above hardware configuration.

The CPU controls overall operations of the mobile terminal. The ROM stores basic input output programs. The RAM is used as a working area for the CPU . The EEPROM reads writes data according to control by the CPU . The CMOS sensor captures an image of an imaging object and obtains image data according to control by the CPU . The accelerometer orientation sensor may be an electromagnetic compass or a gyrocompass that detects geomagnetism or an accelerometer for example. The medium drive may control data reading writing from on a recording medium such as a flash memory. Such control by the medium drive enables pre recorded data to be freely retrieved from the recording medium and new data to be written on the recording medium for example.

Note that the EEPROM may store association information required for network setting for example. In the present embodiment applications for executing cooperative processing services referred to as cooperative processing applications hereinafter may be stored in the EEPROM or the recording medium .

Also the CMOS sensor is an image sensor that converts light into electric charges and produces a computerized image of an imaging object. Note that in some embodiments a CCD charge coupled device sensor may be used instead of the CMOS sensor for example.

The mobile terminal also includes an audio input unit an audio output unit an antenna a communication unit a wireless LAN communication unit a near field communication unit antenna a near field communication unit a display a touch panel and a bus line .

The audio input unit converts audio into an audio signal. The audio output unit converts an audio signal into audio. The communication unit uses the antenna to establish communication with a nearby base station using a wireless communication signal. The wireless LAN communication unit establishes wireless communication with an access point according to the IEEE 80411 standard. The near field communication unit establishes near field communication Bluetooth registered trademark communication using the near field communication antenna .

The display may be a liquid crystal display LCD or an organic EL electroluminescence display that displays an image of an imaging object and various icons for example. The touch panel may be a pressure sensitive touch panel or an electrostatic touch panel that is placed on the display and is configured to detect a touch position of a touch by a finger or a touch pen on the display for example. The bus line may be an address bus or a data bus for establishing electrical connection between the above described components for example.

The mobile terminal also includes a dedicated battery . The mobile terminal is driven by the battery . The audio input unit includes a microphone for inputting audio. The audio output unit includes a speaker for outputting audio.

The mobile terminal of the present embodiment may implement various processes described below using the above described hardware configuration.

The information storage apparatus according to the present embodiment may be implemented by processing blocks as illustrated in for example. illustrates an exemplary functional configuration of the information storage apparatus . The information storage apparatus executes programs to implement an OS a Web server a PC browser UI a MFP UI a WebApi a shared folder a document management unit and a Web control unit .

The OS is an operating system for the information storage apparatus and controls the overall system of the information storage apparatus . The OS may be for example Windows registered trademark Linux registered trademark or some other operating system.

The Web server is software for transmitting and receiving information using Hyper Text Transfer Protocol HTTP . The Web server may be for example Apache Tomcat registered trademark IIS registered trademark or some other web server.

The PC browser UI displays a system setting screen page at the mobile terminal in response to a HTTP request. A user may change settings via the system setting screen page using a Web browser not shown .

The MFP UI displays a screen page including code information such as a QR code registered trademark on an electronic device such as the MFP in response to a HTTP request. The QR code is a type of matrix code two dimensional code . The MFP UI may also display a print screen or a scan screen on the electronic device in response to a HTTP request. A user may prompt printing or scanning operations using the web browser function of the MFP for example.

The WebApi Web application programming interface can be used via the network N. The WebApi receives a HTTP request executes a process according to the HTTP request and sends an HTTP response. The WebApi also generates a QR code.

The WebApi is a pre defined interface for receiving a request from the mobile terminal such as the smartphone and the tablet terminal and may be configured by functions and or classes for example.

Also the WebApi of the information storage apparatus may be provided as a Software Development Kit SDK to a developer that develops applications to be installed in the mobile terminal. The developer can develop an application using the SDK. The SDK may also be provided to a third vendor other than the provider of the information storage apparatus . The third vendor can develop an application using the SDK. The application developed using the SDK may be installed in the mobile terminal.

By providing the WebApi of the information storage apparatus as a SDK the mobile terminal may install not only an application developed by the provider of the information storage apparatus but also an application developed by a third vendor.

The shared folder is a folder published on the network N using the Server Message Block SMB protocol. A user may access the shared folder using the mobile terminal such as the smartphone and the tablet terminal .

The document management unit manages a file placed in the shared folder and carries out data conversion in response to a request from the Web control unit . Note that in the present embodiment a file corresponds to one form of electronic data. The Web control unit carries out a process of controlling the document management unit according to a request from the WebApi .

Note that generally two processes operate in the information storage apparatus . One of these two processes includes the Web server the PC browser UI the MFP UI and the WebApi . The other process includes the shared folder the document management unit and the Web control unit . The WebApi and the Web control unit establish inter process communication with each other.

The mobile terminal of the present embodiment may be implemented by process blocks as illustrated in for example. illustrates an exemplary functional configuration of the mobile terminal of the present embodiment. The mobile terminal may execute programs to implement an OS an information storage apparatus communication unit a print management unit a projector management unit a file list display unit a setting information display unit an upload screen display unit a QR code read unit and a preview display unit .

The OS is an operating system for the mobile terminal. For example iOS registered trademark or Android registered trademark may be used as the OS to enable overall system control of the mobile terminal.

The information storage apparatus communication unit exchanges information with the WebAPI of the information storage apparatus using HTTP. The information storage apparatus communication unit also accesses the shared folder of the information storage apparatus using SMB.

For example the file list display unit the setting information display unit and the upload screen display unit may use the information storage apparatus communication unit to acquire electronic data and information from the information storage apparatus and send a process request to the information storage apparatus .

The file list display unit displays a list of files stored within the information storage apparatus and accepts a file selection by a user. The setting information display unit may enable designation of connection settings with the information storage apparatus and display the setting information at the mobile terminal for example. The upload screen display unit displays a menu for uploading a file to the information storage apparatus and uploads a file to the information storage apparatus .

An exemplary method of uploading data to the information storage apparatus may involve reading a QR code of the MFP having the MFP scan an image and uploading the scan data in the information storage apparatus . Another exemplary method of uploading data to the information storage apparatus may involve uploading data of the mobile terminal to the information storage apparatus . Another exemplary method of uploading data to the information storage apparatus may involve uploading data captured by a camera function of the mobile terminal to the information storage apparatus .

The preview display unit displays a preview of a file selected by a user from a list of files displayed by the file list display unit . The preview display unit also displays a menu for projection or printing. The projector management unit performs processes such as searching registering the projector and prompting the projector to project an image of a selected file. The print management unit performs processes such as searching registering the MFP and prompting the MFP to print out a selected file.

The QR code read unit may be used by the preview display unit the setting information display unit and the upload screen display unit upon reading a QR code using the mobile terminal. The QR code read by the QR code read unit may be a QR code for specifying the MFP that is to be used for printing or scanning data or a QR code for specifying the projector that is to be used for image projection for example.

In the following detailed processes of the input output system according to the present embodiment are described.

Herein exemplary processes are described that may be executed in the case of prompting the MFP to scan an image and prompting the projector to project the scan data. are sequence charts illustrating process steps executed in the input output system of the present embodiment.

In step S a user operates the smartphone to request for the display of an upload screen. illustrates an exemplary upload screen that may be displayed at the smartphone . When an upload destination setting button is pressed the smartphone sends a folder list request to the information storage apparatus in step S and acquires the requested folder list from the information storage apparatus . In turn the smartphone may display a folder selection screen as illustrated in for example. illustrates an exemplary folder selection screen.

In step S the user operates the smartphone to select an upload destination folder from the folder list displayed in the folder selection screen of . Note that when the user presses a read setting button of the upload screen of a read setting screen as illustrated in may be displayed at the smartphone for example.

In step S the user operates the MFP to request for the display of a QR code screen. Upon receiving the QR code screen display request from the user the MFP sends a QR code screen request to the information storage apparatus in step S and acquires the requested QR code screen from the information storage apparatus . In step S the MFP sends a QR code generation request to the information storage apparatus and acquires the generated QR code from the information storage apparatus . Then the MFP displays the acquired QR code screen including the acquired QR code.

The QR code displayed within the QR code screen includes the IP address of the information storage apparatus that has generated the QR code and the IP address of the MFP displaying the QR code.

While displaying the QR code screen including the QR code the MFP polls the information storage apparatus to check whether there is a scan request using the QR code. The process of inquiring whether there is a scan request at the information storage apparatus may be performed as a background process. In step S the MFP makes an inquiry as to whether there is any scan request at the information storage apparatus but receives a response indicating no scan requests are present.

Note that the order of the process steps S S for selecting the upload destination file and setting up scan conditions and the process steps S S for displaying the QR code screen are not limited to the above order but may be altered.

In step S the user operates the smartphone to press a designate MFP with QR code button displayed at the upload screen of and select scanning using a QR code.

When the designate MFP with QR code button is pressed the smartphone may display a QR code read screen as illustrated in for example. illustrates an exemplary QR code read screen. The QR code read screen of includes a QR code display region . The QR code display region is where an image captured by a camera function of the smartphone is displayed.

In step S the user captures an image of the QR code on the QR code screen displayed by the MFP using the camera function of the smartphone . The user adjusts the position of the smartphone with respect to the QR code on the QR code screen so that the image of the QR code captured by the camera function of the smartphone may be displayed within the QR code display region of the QR code read screen.

The smartphone reads the QR code on the QR code screen. As described above the QR code includes the IP address of the information storage apparatus corresponding to the transmission destination of scan data and the IP address of the MFP corresponding to the sender of the scan data.

In step S the smartphone uses the IP address of the information storage apparatus corresponding to the scan data transmission destination to send a scan request including an upload destination folder path and scan conditions to the information storage apparatus .

In step S the MFP polls the information storage apparatus to check whether there is a scan request using the QR code in a manner similar to step S. By making the inquiry as to the presence of a scan request to the information storage apparatus the MFP receives the scan request including the upload destination folder path and the scan conditions from the information storage apparatus . In step S the MFP executes scanning according to the scan conditions included in the received scan request.

In step S the MFP transmits scan data image data of a document one page at a time to the upload destination folder path of the information storage apparatus corresponding to the scan data transmission destination and stores the scan data in the upload destination folder. In step S transmission of scan data is repeated for the number of pages included in the scanned document. The scan data may be in JPEG format or TIFF format depending on whether the scan data is in color or black and white.

After scanning all pages of the document the MFP sends a scan data conversion request to the information storage apparatus in step S. The scan data conversion request includes the upload destination folder path and the scan conditions.

In step S the information storage apparatus consolidates the scan data of multiple pages transmitted from the MFP and converts the scan data into a PDF file. Note that the data format into which the scan data is converted in step S is not limited to the PDF file format. That is the scan data may be converted into some other data format for consolidating the scan data or a data format display format for enabling display of the scan data by the smartphone for example.

In step S the information storage apparatus sends a scan request acceptance completion notification to the MFP . Upon receiving the scan request acceptance completion notification the MFP displays a scan completion screen indicating that scanning has been completed in step S.

Referring to in step S the user operates the smartphone to request for the display of a main screen as illustrated in for selecting a scan file. illustrates an exemplary main screen.

Upon receiving the main screen display request from the user the smartphone sends a file list request to the information storage apparatus in step S and acquires the requested file list from the information storage apparatus . In turn the smartphone displays the main screen including a file list as illustrated in for example.

In step S the user operates the smartphone to select a file referred to as scan file from the file list of . In step S the smartphone sends a file acquisition request to the information storage apparatus to acquire download the scan file selected by the user from the information storage apparatus .

The smartphone may display a preview of the downloaded scan file as illustrated in for example. illustrates an exemplary main screen displaying a preview.

In step S the user operates the smartphone to select press a select projector with QR code button displayed on the main screen of for prompting image projection by a projector. When the select projector with QR code button is pressed the smartphone may display a QR code read screen as illustrated in for example.

In step s the user captures an image of the QR code of the projector using the camera function of the smartphone . For example the QR code of the projector may be attached to a chassis of the projector . In some embodiments the projector may project a screen indicating the QR code of the projector .

The user adjusts the position of the smartphone with respect to the QR code of the projector so that the image of the QR code captured by the camera function of the smartphone may be displayed within the QR code display region of the QR code read screen.

The smartphone reads the QR code of the projector . The QR code of the projector includes the IP address device information and direct projection capability information of the projector that is to project the scan file. The device information of the projector includes information on communication protocols such as HTTP and SMB that may be used by the projector and information on data formats such as JPRG and PDF that may be used by the projector . The direct projection capability information is an example of direction output capability information indicating whether the projector is capable of directly projecting outputting data from the smartphone .

In step S based on the direct projection capability information the smartphone transmits a file to the projector to determine whether the projector is capable of directly projecting data from the smartphone .

In step S upon determining that the projector is capable of direct projection the smartphone converts the PDF scan file acquired in step S into a file in a data format compatible with projection by the projector . The scan file is converted into a file in a compatible data format based on the device information of the projector including information on the data format that may be used by the projector .

In step S the smartphone transmits the file in the compatible data format projection file to the projector . In step S the projector projects the projection file received from the smartphone .

On the other hand in a case where the smartphone determines in step S that the projector is not capable of direct projection in step S the smartphone sends a scan file projection request to the information storage apparatus designating the IP address and the device information of the projector . In step S the information storage apparatus converts the PDF scan file into a projection file in a compatible data format that may be used by the projector based on the device information of the projector .

In step S the information storage apparatus sends a projection start request to the projector using the IP address of the projector . In step S the projector sends a file acquisition request to the information storage apparatus and receives the projection file from the information storage apparatus . In step S the projector projects the received projection file.

By implementing the process steps illustrated in cooperation may be facilitated between the MFP that is to scan input data and the projector that is to project output the data. Note that although the user explicitly selects data input by scanning in step S of in other embodiments such a step may be omitted and the selection may be implicitly recognized based on function information included in the QR code of the MFP for example.

Also although the user explicitly selects data output by projection in step S of in other embodiments the selection may be implicitly recognized based on function information included in the QR code of the projector for example.

In a further embodiment after step S of an error determination step may be made for determining whether the function explicitly selected by the user in step S matches a function represented by the function information included in the QR code of the MFP . For example an error may be detected in a case where the function explicitly selected by the user in step S is not included in the function information of the QR code of the MFP .

Also after step S of an error determination step may be made for determining whether the function explicitly selected by the user in step S matches a function represented by the function information of the QR code of the projector . For example an error may be detected in a case where the function explicitly selected by the user in step S is not included in the function information of the QR code of the projector .

Also although the MFP polls the information storage apparatus to check whether there is a scan request at the information storage apparatus in in other embodiments the smartphone may send a scan request to the MFP .

In the following the process steps S and S performed by the smartphone are described in greater detail. is a flowchart illustrating process steps for determining whether the smartphone or the information storage apparatus is to transmit the projection file.

In step S the smartphone captures and reads the QR code of the projector using the camera function of the smartphone . In step S the smartphone analyzes the data included in the read QR code.

In step S based on the analysis of step S the smartphone acquires the IP address the device information and the direct projection capability information of the projector that is to project the scan file.

In step S the smartphone determines whether the projector is capable of direct projection based on the direct projection capability information acquired in step S. If the projector is capable of direct projection the smartphone prompts the projector to directly project data from the smartphone in step S. Note that the process of step S corresponds to steps S S of .

If the projector is not capable of direct projection the smart phone prompts the projector to project data via the information storage apparatus in step S. Note that the process of step S corresponds to steps S S of .

In the present embodiment the direct projection capability information is included in the QR code of the projector so that the smartphone may determine whether to have the projector use a projection method of directly projecting data from the smartphone or the projecting data via the information storage apparatus depending on whether the projector is capable of direct projection. In an alternative embodiment the determination of whether to use the method of directly projecting outputting data from the smartphone or the method of projecting outputting data via the information storage apparatus may be made based on a combination of device information.

For example in a case where device information of an input apparatus designates scanning and device information of an output apparatus designates the projector a method of directly outputting data from the smartphone may be used and in a case where device information of an input apparatus designates scanning and device information of an output apparatus designates the MFP a method of outputting data via the information storage apparatus may be used. Note that in the above described embodiment the direct projection capability information is included in the QR code to determine whether the smartphone is capable of directly communicating with the electronic device corresponding to the output apparatus. However the present invention is not limited to such an embodiment. For example the IP address and device information of the output apparatus may be included in the QR code and a determination of whether the smartphone is capable of direct communication with the output apparatus may be made based on whether the smartphone can access the output apparatus using the IP address acquired from the QR code. Also note that the determination of the projection method may be performed by the smartphone as in the above described embodiment or alternatively the device information may be transmitted to the information storage apparatus and the determination of the projection method may be made by the information storage apparatus for example.

In the input output system according to the present embodiment a user may hold a mobile terminal such as the smartphone or the tablet terminal against an electronic device such as the MFP or the projector to acquire information such as a QR code specifying the electronic device. In this way the user may easily designate an electronic device for inputting electronic data and an electronic device for outputting electronic data from a plurality of electronic devices.

Also in the input output system according to the present embodiment cooperation may be facilitated between an electronic device for inputting electronic data an electronic device for outputting electronic data and a cooperative processing apparatus such as the information storage apparatus to provide a variety of services.

Also in the input output system according to the present embodiment direct projection from the smartphone may be implemented if the projector is capable of direct projection from the smartphone and projection via the information storage apparatus may be implemented if the projector is not capable of direct projection.

Note that the IP address included in the QR code of the MFP may be an exemplary embodiment of input apparatus information specifying an electronic device corresponding to an input apparatus of the present invention. The IP address included in the QR code of the projector may be an exemplary embodiment of output apparatus information specifying an electronic device corresponding to an output apparatus of the present invention. The IP address of the information storage apparatus may be an exemplary embodiment of cooperative processing apparatus information of the present invention. Also an acquisition unit of the present invention may include the QR code read unit for example. An input control unit of the present invention may include the information storage apparatus communication unit and the upload screen display unit for example. Also an output control unit of the present invention may include the information storage apparatus communication unit the print management unit and the projector management unit for example.

Further the present invention is not limited to the embodiments described above but encompasses numerous variations and modifications that may be made without departing from the scope of the present invention.

The present application is based on and claims the benefit of priority of Japanese Patent Application No. 2013 052476 filed on Mar. 14 2013 and Japanese Patent Application No. 2014 037007 filed on Feb. 27 2014 the entire contents of which are hereby incorporated herein by reference.

