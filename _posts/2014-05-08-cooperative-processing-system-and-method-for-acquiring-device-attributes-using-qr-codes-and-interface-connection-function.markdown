---

title: Cooperative processing system and method for acquiring device attributes using QR codes and interface connection function
abstract: A cooperative processing system includes an operation terminal and a cooperative processing device connected to each other, and is connectable to a plurality of electronic devices. The cooperative processing system causes one of electric devices to function as an input device to cause electronic data to be input therefrom and one of the electric devices to function as an output device to output the electronic data. The cooperative processing system includes an obtaining unit to obtain input device information to specify the input device and output device information to specify the output device, an input control unit to cause the input device to input electronic data through a first interface according to the input device information, and an output control unit to cause the output device to output the electronic data through a second interface according to the output device information in an format appropriate for the output device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08988722&OS=08988722&RS=08988722
owner: Ricoh Company, Ltd.
number: 08988722
owner_city: Tokyo
owner_country: JP
publication_date: 20140508
---
The present invention relates to a cooperative processing system and a cooperative processing method.

Conventionally a control system is known that causes devices connected to a network and handle data having different data formats from each other to cooperate with each other as disclosed in Japanese Laid Open Patent Application Publication No. 2005 292903.

In recent years users are likely to utilize various electronic devices such as a printer a complex machine a projector and the like that output electronic data or various operation terminals such as a mobile phone a smartphone a tablet terminal and the like. In a form that utilizes these electronic devices and operation terminals i.e. a system improvement of utility value is expected by causing the various electronic devices and operation terminals to cooperate with each other.

However in the conventional system utilizing the electronic devices and the operation terminals there has been no structure that provides a plurality of services by causing at least one electronic device among the plurality of electronic devices connected to the system to cooperate with each other.

Accordingly embodiments of the present invention may provide novel and useful cooperative processing system and cooperative processing method solving or reducing one or more of the above described problems.

More specifically the embodiments of the present invention may provide a cooperative processing system and a cooperative processing method that can provide a plurality of services by causing at least one electronic device among a plurality of electronic devices.

According to one embodiment of the present invention there is provided a cooperative processing system including an operation terminal and a cooperative processing device connected to each other. The cooperative processing system is connectable to a plurality of electronic devices. The cooperative processing system performs a cooperative process causing one of the plurality of electric devices to function as an input device to cause electronic data to be input therefrom and one of the plurality of electric devices to function as an output device to output the electronic data. The cooperative processing system includes an obtaining unit provided in the operation terminal and configured to obtain input device information from the input device to specify the input device from the plurality of electronic devices and output device information from the output device to specify the output device from the plurality of electronic devices an input control unit configured to cause the input device specified by the input device information to input electronic data therefrom through a first interface according to the input device information and an output control unit configured to cause the output device specified by the output device information to output the electronic data through a second interface according to the output device information in an output format appropriate for the output device.

According to another embodiment of the present invention there is provided a cooperative processing method using a cooperative system including an operation terminal and a cooperative processing device connected to each other. The cooperative system is connectable to a plurality of electronic devices. The cooperative processing system performs a cooperative process causing one of the plurality of electric devices to function as an input device to cause electronic data to be input therefrom and one of the plurality of electric devices to function as an output device to output the electronic data. In the cooperative processing method input device information is obtained from the input device to specify the input device from the plurality of electronic devices and output device information is obtained from the output device to specify the output device from the plurality of electronic devices by the operation terminal. Next an input is controlled by causing the input device specified by the input device information to input electronic data therefrom through a first interface according to the input device information and an output is controlled by causing the output device specified by the output device information to output the electronic data through a second interface according to the output device information in an output format appropriate for the output device.

Other objects features and advantages of the present invention will become more apparent from the following detailed description when read in conjunction with the accompanying drawings.

A description is given with reference to the accompanying drawings of embodiments of the present invention.

A private environmental network such as an intranet office network is available for the network N. The smartphone and the tablet terminal are examples of an operation terminal that a user can carry and operate. The operation terminal may be a terminal device that a user can operate such as a mobile phone and a notebook PC Personal Computer in addition to the smartphone and the tablet terminal .

The MFP and the projector are examples of electronic devices that input and output electronic data e.g. printing scanning projection and the like . Moreover the digital camera the microphone and the loudspeaker are also examples of electronic devices that input and or output electronic data. The electronic devices may be devices that input and or output electronic data such as a printer a scanner a copier a display and the like in addition to the MFP and the projector . The display is an example of an image display device.

The MFP is an example of an image forming device. The MFP has an imaging function an image forming function and a communication function and can be used as a printer a facsimile a scanner and a copier. The MFP has a Web browser function and displays a UI User Interface by drawing HTML Hyper Text Markup Language data in the information storage device . Furthermore the MFP can receive a request such as printing and scanning from a user by running a Javascript Trademark program on the UI. The projector is an example of an image projection device. The projector has a projection function and a communication function. The projector projects and outputs image data. The digital camera is an example of an image taking device.

The microphone and the loudspeaker are examples of sound input and output devices. The server device is an example of an apparatus that implements some process such a high functional process as the MFP or the projector cannot process a process as a file server and the like. The interactive whiteboard is an example of a device that displays electronic data such as image data and document data as an output and creates electronic data such as image data and document data by receiving a writing input and the like from a user.

The information storage device is an example of an information processing device. The information storage device implements such a high functional process as the MFP or the projector cannot process or a process as a file server. The information storage device provides the input and or output of electronic data by the electronic device such as the MFP or the projector as a service by cooperating with the operation terminal such as the smartphone or the tablet terminal . The information storage device may be configured to be dispersed to a plurality of computers.

The information storage device is implemented by for example a computer system having a hardware configuration illustrated in . The operation terminal such as the smartphone or the tablet terminal is configured to include the hardware configuration illustrated in . is a hardware configuration diagram of an example of the computer system of the present embodiment.

The computer system in includes an input device a display an external I F a RAM a ROM a CPU a communication I F and an HDD each of which is connected to each other by a bus B. The input device includes a keyboard a mouse and the like and is used to input each manipulate signal to the computer system .

The display device includes a display and the like and displays processing results by the computer system . The communication I F is an interface that connects the computer system to the network N. This allows the computer system to perform data communication with the operation terminal the electronic device and the like through the communication I F .

The HDD is a non volatile storage that stores a program and data. The program and the data includes an OS Operating System that is basic software to control the whole computer system an application program that provides a variety of functions on the OS and the like. The HDD manages the stored program and data by a predetermined file system and or a DB Data Base .

The external I F is an interface between the computer system and an external device. The external device includes a recording medium and the like. This enables the computer system to read and or write to the recording medium through the external I F . Here the recording medium includes a flexible disk a CD Compact Disc a DVD Digital Versatile Disk an SD Secure Digital memory card a USB Universal Serial Bus memory and the like.

The ROM is a non volatile semiconductor memory storage device that can retain a program and data even when the computer is turned off. The ROM stores a program and data such as a BIOS Basic Input Output System that is executed when the computer starts up an OS setting a network setting and the like. The RAM is a volatile semiconductor memory storage device that holds a program and data temporarily.

The CPU is an arithmetic device that implements control or a function of the whole computer system by reading the program and data from the storage device such as the ROM or the HDD on the RAM and by executing the process.

The computer system of the present embodiment can implement a variety of processes by causing the hardware resource and the program to cooperate with each other by combining the above hardware resource the program and the data.

The operation terminal such as the smartphone or the tablet terminal is for example implemented by a hardware configuration illustrated in . is a hardware configuration diagram illustrating an example of the operation terminal of the present embodiment. The operation terminal in includes a CPU a ROM a RAM an EEPROM a CMOS sensor an acceleration direction sensor a media drive .

The CPU controls the whole operation of the operation terminal. The ROM stores a basic input and output program. The RAM is used as a work area of the CPU . The EEPROM reads or writes data in accordance with the control of the CPU . The CMOS sensor takes an image of an object of shooting in accordance with the control of the CPU and obtains image data. The acceleration direction sensor is for example an electromagnetic compass a gyrocompass an acceleration sensor and the like.

The media drive controls reading or writing storing data to a recording medium such as a flash memory. The media drive is configured to be able to receive and eject the recording medium that stores readable data having been already recorded therein or stores new data to be written therein.

Here the EEPROM stores association information and the like necessary for an OS executed by the CPU and network setting. An application to implement various processes in the embodiments of the present invention is stored in the EEPROM the recording medium or the like.

Moreover the CMOS sensor is an electric charge coupling device that digitizes an image of an object of shooting by converting light to an electric charge. As long as the CMOS can image the object of shooting for example the CMOS can be replaced by a CCD Charge Coupled Device sensor.

Furthermore the operation terminal includes a voice input part a voice output part an antenna a communication part a wireless LAN communication part a short range wireless communication antenna a short range wireless communication part a display a touch panel and a bus line .

The voice input part converts a voice to a voice signal. The voice output part converts a voice signal to a voice. The communication part communicates with the nearest base station device by a wireless communication signal by using the antenna . The wireless LAN communication part communicates with an access point by wireless LAN communication conforming to the IEEE 80411 standard. The short range wireless communication part performs a short range wireless communication Bluetooth Trademark communication using the short range wireless communication antenna .

The display is made of a liquid crystal display organic EL Electroluminescence display or the like that displays an image of the object of shooting and a variety of icons. The touch panel is placed on the display constituted of a sensitive type or electrostatic type panel and detects a touched position on the display based on a touch by a finger a touch pen or the like. The bus line is an address bus a data bus or the like to electrically connect each part with each other.

In addition the operation terminal includes a dedicated battery . The operation terminal is driven by the battery . The voice input part includes a microphone to allow a voice to be input. The voice output part includes a loudspeaker to output a voice.

Thus the operation terminal of the present embodiment can implement a variety of processes as described later by the above hardware configuration.

The information storage device of the present embodiment is implemented by for example a processing block as illustrated in . is a processing block diagram of an example of the information storage device of the present embodiment. The information storage device implements an OS a Web server a UI for PC browser a UI for MFP a WebApi a shared folder a document management part and a Web control part by running a program.

The OS is an operating system of the information storage device and controls the whole system. The OS is for example Windows Trademark Linux Trademark or the like.

The Web server is software that sends and receives information by HTTP Hyper Text Transfer Protocol . The Web server is Apache Tomcat Trademark IIS Trademark or the like.

The UI for PC browser displays a system setting screen on the operation terminal by a HTTP request. A user can change the setting from the system setting screen by using a Web browser not shown in the drawing .

The UI for MFP displays a screen of QR code Trademark an example of code information on the electronic device such as the MFP in accordance with the HTTP request. The QR code is a matrix type two dimensional code. Moreover the UI for MFP displays a print screen and a scanning screen by the HTTP request. The user can perform printing and scanning operation by utilizing the Web browser function of the MFP .

The WebApi Application Programming Interface is available through the network N. The WebApi receives the HTTP request performs a process in accordance with the HTTP request and performs an HTTP response. The WebApi also creates the QR code.

The WebApi is a preliminarily defined interface provided to receive a request from the operation terminal such as the smartphone and the tablet terminal and is for example constituted of a function a class or the like.

Furthermore the WebApi of the information storage device can be provided for a developer of an application installed in the operation terminal as an SDK Software Development Kit . The application developer can develop the application by using the SDK. The SDK can be provided for a third vendor other than the provider of the information storage device . The third vendor can develop an application by using the provided SDK. The application developed by using the SDK can be installed into the operation terminal.

By providing the WebApi of the information storage device as the SDK the operation terminal can install not only the application developed by the provider of the information storage device but also the application developed by the third vendor.

The shared folder is a folder published on the network N by a SMB Server Message Block protocol. A user can access to the shared folder by using the operation terminal such as the smartphone or the tablet terminal .

The document management part manages a file put in the shared folder and performs a process of converting data in response to a request from the Web control part . Here the file in the present embodiment is one form of electronic data. The Web control part performs a process of controlling the document management part in response to a request from the WebApi .

Here there are roughly divided into two processes running in the information storage device . One process functions as the Web server the UI for PC browser the UI for MPF and the WebApi . Another process functions as the shared folder the document management part and the Web control part . Accordingly the WebApi and the Web control part perform interprocess communication.

The operation terminal of the present embodiment is for example implemented by a processing block illustrated in . is a processing block diagram of an example of the operation terminal of according to the present embodiment. The operation terminal implements an OS an information storage device communication part a printing management part a projector management part a file list display part a setting information display part an upload screen display part a QR code reading part and a preview display part by running a program.

The OS is an operating system of the operation terminal . The OS is for example iOS Trademark Android Trademark or the like that controls the whole system.

The information storage communication part sends and receives information to and from the WebApi of the information storage device by the HTTP. In addition the information storage device communication part can access the shared folder of the information storage device by the SMB.

For example the file list display part the setting information display part and the upload screen display part obtains electronic data or information from the information storage device or requests a process to the information storage device by utilizing the information storage device communication part .

The file list display part displays a list of files in the information storage device and receives selection of a file from a user. The setting information display part performs a connection setting with the information storage device and or displays the setting information of the operation terminal . The upload screen display part displays a menu for uploading a file to the information storage device and uploads the file to the information storage device .

For example there is a method of reading the QR code on the MFP and uploading the file to the information storage device by causing the MFP to scan the file as an uploading method to the information storage device .

Moreover for example there is a method of uploading the data of the operation terminal to the information storage device as an uploading method to the information storage device . Furthermore for example there is a method of uploading picture data taken by a camera function of the operation terminal as an uploading method to the information storage device .

When a user selects a file from the list of the files displayed by the file list display part the preview display part previews the selected file. In addition the preview display part displays a menu of projection and or printing. The projector management part performs search and registration of the projector and a process of causing the projector to project the selected file. The printing management part performs search and registration of the MFP and a process of causing the MFP to print the selected file.

When the operation terminal reads the QR code the QR code reading part is utilized by the preview display part the setting information display part and the upload screen display part . The QR code that the QR code reading part reads includes a QR code for connecting the operation terminal to the information storage device a QR code for specifying the MFP to be caused to print or scan a QR code for specifying the projector to be caused to project and the like.

Detailed description is given below of a process by the cooperative processing system according to the present embodiment.

More specifically a description is given below of a process when causing data to be input from an input device and the input data to be output by an output device . is a sequence diagram of an example of illustrating a processing procedure of a cooperative processing system of the present embodiment.

In step S a user operates the input device to allow the user to input data and requests the input device to display a QR code screen. In step S the input device displays the QR code screen including a QR code. The QR code displayed by the input device includes input device information e.g. an IP address and capability information of the input device for specifying the input device . Here the capability information only has to be information from which an interface or a function that the input device retains can be determined. The capability information may be an ID of the input device or a character string formed by listing the interface or the function retained by the input device . The IP address functions as connection information to be connected to the input device .

In step S the user operates the output device to output data and requests the output device to display a QR code. In step S the output device displays a QR code screen including the QR code. The QR code displayed by the output device includes output device information e.g. an IP address and capability information of the output device for specifying the output device . Here the capability information only has to be information from which an interface or a function that the output device retains can be determined. The capability information may be an ID of the output device or a character string formed by listing the interface or the function retained by the output device . The IP address functions as connection information to be connected to the output device .

Here a description is given of an example of displaying the QR code screens including the QR codes in the sequence diagram in but for example a QR code preliminarily printed on a sheet of paper and the like and attached to a casing may be available.

In step S the user operates the operation terminal and selects input and output as a service to be utilized for example from a screen illustrated in . is a schematic diagram of an example of a service list screen. One of the services of the input the output and the input and output is selected by the user from the service list screen of on the operation terminal .

The operation terminal determines that the service selected by the user is the input and output and that the IP address the capability information and input and output conditions of the input device and the output device are information necessary for the input and output service.

To begin with the operation terminal displays a selection screen of the input device illustrated in and requests the user to specify the input device . is a schematic diagram of an example of the selection screen of the input device . The operation terminal receives the selection of the input device by the user from the selection screen of the input device . For example the user operates the operation terminal and requests the operation terminal to read the QR code of the input device . Here as illustrated in the user may select the input device from a device list displayed on the selection screen of the input device .

In response to the request of reading the QR code from the user the operation terminal takes a picture of the QR code by using a camera function in step S see and reads the QR code. The operation terminal obtains the IP address and the capability information of the input device from the QR code.

Next the operation terminal displays a selection screen of the output device similar to the selection screen of the input device and requests the user to specify the output device . The operation terminal receives the selection of the output device by the user from the selection screen of the output device .

For example the user operates the operation terminal and requests the operation terminal to read the QR code of the output device to specify the output device . In response to the request of reading the QR code from the user the operation terminal takes a picture of the QR code by using a camera function in step S and reads the QR code. The operation terminal obtains the IP address and the capability information of the output device from the QR code. Here as illustrated in the user may select the output device from a device list displayed on a selection screen of the output device or may select the output device by reading the QR code.

In step S the operation terminal displays an input condition setting screen illustrated in to specify input conditions of the input device selected by the user. is a schematic diagram illustrating an example of the input condition setting screen. The operation terminal receives the setting of the input conditions from the input condition setting screen by the user. Here in the input condition setting screen receives a setting of reading scanning conditions as an example of the input conditions.

In step S the operation terminal displays an output condition setting screen that sets output conditions of the output device selected by the user and is similar to the input condition setting screen in . The operation terminal receives a setting of the output conditions from the output condition setting screen by the user.

In step S the operation terminal sends the input device information and the output device information set by the user to the information storage device and requests execution of the input and output service. Here the input device information includes the capability information the IP address and the input conditions of the input device . The output device information includes the capability information the IP address and the output conditions of the output device .

In step S the information storage device confirms an interface utilized by the input device and a file format available for the input device from the capability information included in the input device information as illustrated in .

Moreover the information storage device confirms an interface utilized by the output device and a file format available for the output device from the capability information included in the output device information as illustrated in . Then the information storage device determines the interface available for the input device and the output device . In addition the information storage device determines a file format to be utilized based on the format available for the input device and the output device and further determines whether data conversion is necessary or not.

Here when there is a plurality of interfaces available for the input device and the output device the interface to be utilized may be determined by preliminarily established priority or the like. When there is a plurality of file formats that the input device and the output device can handle the information storage device may determine the file format to be used by the input device and the output device by preliminarily established priority or the like.

In step S the information storage device provides an input instruction according to the input conditions for the input device by way of the interface determined to be used in step S. Upon receiving the input instruction from the information storage device the input device executes an input process according to the input conditions in step S. After finishing the input process the input device sends obtained input data to the information storage device as input process results in step S to the information storage device .

In step S the information storage device converts the input data received from the input device to the file format of the output device that the information storage device has determined to use in step S.

In step S the information storage device provides an output instruction according to the output conditions for the output device by way of the interface determined to be used in step S. Upon receiving the output instruction from the information storage device the output device executes an output process according to the output conditions in step S.

Here a description is given below of a process of the operation terminal in steps S through S by using a flowchart describing the process in detail illustrated in .

The operation terminal displays a screen such as and allows the user to select a service the user wants to use from the displayed screen step S . Next the operation terminal determines whether the selected service is the input service or not step S .

When the selected service is the input service step S YES the operation terminal obtains capability information of the input device by taking a picture of the QR code displayed on or attached to the input device step S . Furthermore the operation terminal displays an input condition setting screen as illustrated in to set input conditions of the input device selected by the user and receives an input of the input conditions from the user step S .

With respect to the output conditions for example the operation terminal may preliminarily store the conditions set for each device as illustrated in and may display setting items corresponding to the capability information of the output device having been obtained in step S as the setting items of the output conditions. Moreover the capability information of the output device having been obtained in step S may include the setting items of the output conditions and the operation terminal may display the setting items contained in the obtained capability information of the output device . The operation terminal sends the capability information that the operation terminal has obtained in step S and the input conditions that the operation terminal has accepted as the input in step S to the information storage device step S .

When the selected service is not the output service step S NO the operation terminal obtains capability information of the input device similarly to step S step S . Next the operation terminal obtains the capability information of the output device similarly to step S step S . Subsequently the operation terminal receives the setting of the input conditions similarly to step S step S . Next the operation terminal receives the setting of the output conditions similarly to step S step S .

After that the operation terminal sends the capability information that the operation terminal has obtained insteps S and S and the input conditions and the output conditions that the operation terminal has accepted in steps S and S respectively to the information storage device step S .

The cooperative processing system of the present embodiment is not limited to the above. A variety of configurations can be implemented such as a configuration of providing an input and output instruction for the input and output device from the information storage device by way of the operation terminal a configuration of the operation terminal converting the input data and a configuration of sending the output data to the output device by way of the output device .

Moreover capability information of an electronic device may contain information of interfaces corresponding to the electronic device and the information storage device may determine an interface to connect with the electronic device based on received capability information.

As described above according to the cooperative processing system of embodiments of the present invention a user can obtain information to specify an electronic device such as a QR code by passing the operation terminal such as the smartphone or the tablet terminal over the electronic device such as the MFP or the projector . The user can readily specify an electronic device to input electronic data and an electronic device to output electronic data from a plurality of electronic devices. The information storage device can determine an interface to be utilized by the electronic device to input the electronic data and the electronic device to output the electronic data and can control the electronic devices through the interface.

Accordingly according to the cooperative processing system of the embodiments of the present invention the user can provide a variety of services by causing the operation terminal and an information processing device such as the information storage device to cooperate to control one or more electronic device.

Thus according to the embodiments of the present invention a plurality of services can be provided by cooperating one or more electronic device among a plurality of electronic devices.

The present invention is not limited to the specifically disclosed embodiments and variations and modifications may be made without departing from the scope of the present invention. For example an obtaining unit recited in claims corresponds to the setting information display part and the QR code reading part . In addition for example an available interface determination unit and a data conversion necessity determination unit correspond to the WebApi . For example a cooperative processing device corresponds to the information storage device .

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2013 100634 filed on May 10 2013 and Japanese Priority Patent Application No. 2014 90952 filed on Apr. 25 2014 the entire contents of which are incorporated herein by reference.

