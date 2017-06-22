---

title: Server for managing home appliance and system including the same
abstract: A server includes a memory, a communication module configured to exchange data with a mobile terminal or a home appliance, and a processor configured to receive login information from the mobile terminal based on a first communication mode, to perform login based on the login information, to receive a session maintenance request from the mobile terminal based on a second communication mode after login, and to initialize a session duration according to the session maintenance request. Thus, it is possible to control the home appliance in real time via the server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09467853&OS=09467853&RS=09467853
owner: LG ELECTRONICS INC.
number: 09467853
owner_city: Seoul
owner_country: KR
publication_date: 20141017
---
This application claims the priority benefit of prior U.S. Provisional Patent Application No. 61 892 182 filed on Oct. 17 2013 in the USPTO whose entire disclosure is hereby incorporated by reference.

The present disclosure relates to a server for managing a home appliance and a system including the same and more particularly to a server capable of performing real time control and a system including the same.

Among home appliances provided in a building a refrigerator stores food a washing machine processes laundry an air conditioner adjusts indoor temperature and a cooker cooks food. As various communication methods have been developed a variety of research in hopes of increasing user convenience in terms of communication with a home appliance has been conducted.

The home appliance may be an electric device for a user and may include a refrigerator of a washing machine of an air conditioner of a cooker of and a cleaner of etc. The home appliance includes a communication unit not shown and may exchange data with electric devices in an internal network or electric devices connectable over an external network . For data exchange the communication unit not shown may exchange data with the AP apparatus by wire or wirelessly.

The AP apparatus may provide the internal network and more particularly a wireless network to adjacent electric devices. The AP apparatus may allocate radio channels according to a predetermined communication method to the electric devices in the internal network and perform wireless data communication via the channels. The predetermined communication method may be one of Wi Fi communication Bluetooth communication and or Zig Bee communication. The mobile terminal which may be located in the internal network may communicate with the home appliance via the AP apparatus thereby performing monitoring and remote control of the home appliance .

The AP apparatus may perform data communication with an external electric device via the external network in addition to the internal network . For example the AP apparatus may perform wireless data communication with an externally located mobile terminal via the external network .

The mobile terminal which may also move to be located in the external network may communicate with the home appliance via the external network and the AP apparatus thereby performing monitoring remote control smart diagnosis etc. of the home appliance. As another example the AP apparatus may perform wireless data communication with the externally located server via the external network .

The server may store firmware information and operation information course information of the home appliance and register product information of the home appliance. For example the server may be operated by a manufacturer or vendor of the home appliance . As another example the server may be operated by a public application store operator.

The server receives login information from the mobile terminal based on a first communication mode performs login based on the login information receives a session maintenance request from the mobile terminal based on a second communication mode after login and initiates a session duration according to the session maintenance request. The server provides information about the registered home appliance to the mobile terminal . Thus real time control of the home appliance via the server is possible.

The server assigns control rights to the first logged in user or mobile terminal and transmits a message indicating no control rights to the other users or mobile terminals such that control rights are assigned to one user or mobile terminal . The server provides monitoring data to all connected users or mobile terminals such that all the users or mobile terminals perform monitoring regardless of the control rights.

The server may transmit to the home appliance any one of a control command a monitoring command a diagnosis command and a software download command for the home appliance from the mobile terminal thereby providing user convenience. Detailed functions of the server will be described in greater detail with reference to .

For example if the home appliance is a refrigerator the driving unit may include a refrigerating compartment driving unit for driving a refrigerating compartment fan for supplying cooled air to a refrigerating compartment a freezer compartment driving unit for driving a freezer compartment fan for supplying cooled air to a freezer compartment and a compressor driving unit for driving a compressor for compressing a refrigerant.

As another example if the home appliance is a washing machine the driving unit may include a driving unit for driving a drum or a tub.

As another example if the home appliance is an air conditioner the driving unit may include a compressor driving unit for driving a compressor in an outdoor unit an outdoor fan driving unit for driving a fan of the outdoor unit for heat exchange and an indoor fan driving unit for driving a fan of an indoor unit for heat exchange.

As another example if the home appliance is a cooker the driving unit may include a microwave driving unit for outputting microwaves into a cavity.

As another example if the home appliance is a cleaner the driving unit may include a fan motor driving unit for air suction.

The communication unit may include at least a near field communication NFC module capable of performing NFC a Wi Fi module a Bluetooth module a Zig Bee module etc. The communication unit may access the AP apparatus access the server via the AP apparatus or receive a power information signal from the server .

The controller may control the driving unit based on the power information signal received via the communication unit . In addition a memory for storing data in the home appliance may be further included.

When Wi Fi communication with the AP apparatus is performed the communication unit may include a Wi Fi communication module and the second interface may include a Wi Fi application for data exchange between the controller and the AP apparatus . Thus data conversion etc. may be performed which will be described with reference to .

The communication module may receive home appliance related information and more particularly home appliance product information from the mobile terminal . The communication module may transmit product information registration result information of the received home appliance product information to the mobile terminal .

The communication module may include an Internet module or a mobile communication module. The memory may store the received home appliance product information and include the received product information for product registration of the home appliance.

The processor may perform overall control of the server . The processor may control generation of the product registration result information of the home appliance when receiving the product information of the home appliance from the mobile terminal . The processor may control transmission of the generated product registration result information to the mobile terminal .

As another example if the home appliance related information is power consumption information of the home appliance the processor may control transmission of power information such as power price information on peak time power information off peak time power information real time power information etc. stored in the memory to the mobile terminal .

The processor receives login information from the mobile terminal based on a first communication mode performs login based on the login information receives a session maintenance request from the mobile terminal based on a second communication mode after login and initiates a session duration according to the session maintenance request.

The processor may search for a registered home appliance in the memory and control transmission of product information a notify server address for TCP connection and port information to the mobile terminal after login.

The processor may check whether the home appliance requested by the mobile terminal has been registered or connected to the server according to a home appliance connection state request from the mobile terminal and control transmission of result information to the mobile terminal .

The processor may check the connection state of the home appliance according to a remote control request from the mobile terminal and control transmission of a remote control command to the home appliance based on a second communication mode.

The processor may transmit a notify message for software update to the home appliance according to a software update request from the mobile terminal and control transmission of URL information for software download to the home appliance according to a software download request from the home appliance.

The processor may control transmission of a command to the home appliance according to a camera start request or a camera stop request from the mobile terminal and the memory may store media data of a camera received from the home appliance. At this time the processor may control transmission of the media data to the mobile terminal .

The processor may perform authentication processing based on login information transmission and transmission of file data stored in the memory based on the first communication mode and perform control command delivery and result reception and monitoring data transmission and result reception based on the second communication mode.

The first communication mode is based on an open application programming interface API and the second communication mode is based on a real time interface. The processor may control transmission of a message indicating that the home appliance is operating to the mobile terminal in the first communication mode upon management of a specific home appliance.

The processor assigns control rights to a user or mobile terminal which first performs login and controls transmission of a message indicating no control rights to the other users or mobile terminals via the second communication mode. If the user or mobile terminal having the control rights logs out the processor may assign the control rights to a user or mobile terminal which has first requested a control command among the other users or mobile terminals .

The processor may control transmission of monitoring data to all connected users or mobile terminals. The processor may control transmission of a session ID to the mobile terminal after login. The processor may control transmission of the session ID and a device list of a manageable home appliance to the mobile terminal after login.

Referring to the mobile terminal may include a radio transceiver an audio video A V input unit a user input unit a sensing unit an output unit a memory an interface a controller and a power supply .

The radio transceiver according to the embodiment of the present disclosure may exchange data with a power management unit via a network router . For example if the mobile terminal is a power monitoring mode for an internal power grid the radio transceiver may transmit a power monitoring request and thus receive monitoring information. As another example if the mobile terminal is in a remote control mode for an internal power grid the radio transceiver may transmit a remote control signal and receive remote control result information.

The radio transceiver may include a broadcast reception module a mobile communication module a wireless Internet module a near field communication NFC module a global positioning system GPS module etc.

The broadcast reception module may receive at least one of a broadcast signal and broadcast related information from an external broadcast management server through a broadcast channel. The broadcast channel may include a satellite channel and a terrestrial channel. The broadcast signal and or the broadcast related information received through the broadcast reception module may be stored in the memory .

The mobile communication module transmits or receives a wireless signal to or from at least one of a base station an external terminal and a server over a mobile communication network. The wireless signal may include a voice call signal a video call signal or various types of data associated with transmission and reception of a text multimedia message.

The wireless Internet module is an internal or external module for wireless Internet access which may be provided to the mobile terminal . For example the wireless Internet module may perform Wi Fi based wireless communication or Wi Fi Direct based wireless communication.

The NFC module may perform NFC. The NFC module may receive data from the home appliance or transmit data to the home appliance if an NFC tag or an NFC module is brought within a predetermined distance of the home appliance that is upon tagging.

As short range wireless communication technology Bluetooth Radio Frequency IDentification RFID Infrared Data Association IrDA Ultra WideBand UWB and ZigBee may be used.

The A V input unit receives an audio signal or a video signal and may include a camera and a microphone .

The user input unit generates key input data enabling the user to control the operation of the mobile terminal. The user input unit may include a keypad a dome switch a touchpad static pressure static electrical etc. In particular if the touchpad and the display have a layered structure this may be called a touchscreen.

The sensing unit detects a current state of the mobile terminal such as whether the mobile terminal is opened or closed the position of the mobile terminal and contact non contact of a user and generates a sensing signal for controlling the operation of the mobile terminal .

The sensing unit may include a proximity sensor a pressure sensor and a motion sensor . The motion sensor may sense motion or position of the mobile terminal using an acceleration sensor a gyroscopic sensor and a gravity sensor. In particular the gyroscopic sensor measures an angular speed and senses a direction angle in which the mobile terminal rotates from a reference direction.

The output unit may include a display an audio output module an alarm unit and a haptic module . The display displays information processed by the mobile terminal .

As described above if the display and the touchpad have the layered structure to configure the touchscreen the display can be used not only as an output device but also as an input device for inputting information via user touch.

The audio output module may output audio data received from the radio transceiver or stored in the memory . The audio output module may include a speaker a buzzer etc.

The alarm unit outputs a signal notifying the user that an event has occurred in the mobile terminal . For example the alarm unit may output a signal in the form of vibrations.

The haptic module generates a variety of tactile effects that the user can feel. A typical example of the tactile effect generated by the haptic module is vibration.

The memory may store a program for processing and control of the controller and may temporarily store input or output data for example a phonebook messages still images and moving images .

The interface serves as an interface with all external devices connected to the mobile terminal . The interface may receive data from an external device or receive power and transmit power to the components of the mobile terminal or transmit data of the mobile terminal to an external device.

The controller controls the overall operation of the mobile terminal . For example the controller performs control and processing associated with voice communication data communication video communication and the like. The controller may include a multimedia playback module for multimedia playback. The multimedia playback module may be implemented in the controller in hardware form or may be implemented in software form separately from the controller .

The power supply receives external power or internal power and supplies power required for operation to each component under control of the controller .

The block diagram of the mobile terminal shown in is only exemplary. Depending upon the specifications of the mobile terminal in actual implementation the components of the mobile terminal may be combined or omitted or new components may be added. That is two or more components may be incorporated into one component or one component may be configured as separate components as needed. In addition the function of each block is described for the purpose of describing the embodiment of the present disclosure and thus specific operations or devices should not be construed as limiting the scope and spirit of the present disclosure.

The home appliance system of may perform the following various functions. Hereinafter the various functions will be described with reference to .

The server may perform member registration member management member withdrawal etc. The server may perform member registration using two methods. For example member registration may be performed via a website or an application.

The method using the website may be performed via a website based user interface UI provided by a membership server. The method using the application provides an open application programming interface API .

The server may register two classes that is a standard member and a smart member upon member registration. The standard member performs member registration via a website or application and uses only a function provided by the website and application without performing product registration. The smart member should perform member registration and product registration in order to use an overall service of the server .

Upon member registration information for identifying a user such as email user id password country code etc. needs to be input. The server may store mail user id password country code etc. of each user. In the rule for the email or user id of the server the email may be restricted to 60 digits including and the password may be restricted to 6 to 12 digits. The server may use an email authentication method for member authentication. Other authentication methods such as authentication of the mobile terminal are applicable.

The server may provide functions such as member information change password change via both the website and the application. The server may allow registration using one email account in one country. This is referred to as single ID policy. The server may disallow overlapping registration in a plurality of countries. After member registration in one country is withdrawn member re registration may be performed in another country.

The service of the server is no longer used after member withdrawal. Therefore the server deletes product information associated with user information. The user may withdraw from the server via a website or an application.

Product registration is a mapping process between the user of the home appliance and the server . In order to use the service of the server via the home appliance product registration for the server is required. The product registration process may be divided into a TFT model having a display and an LED model without a TFT LCD. In the TFT model product information may be directly input via an input unit of the home appliance . In the LED model product information may be input using the mobile terminal . The server receives product information and identifies the TFT model or the LED model.

For product registration first the home appliance is powered on and a communication unit needs to be in a Wi Fi connection state. A member ID should be registered with the server . The home appliance calls an open API via a display screen and transmits a product registration request to the server . An open API calling method is performed in an extensible markup language XML format. For product registration product registration request information or product information transmitted from the home appliance to the server may include user id password device type device id model name etc.

The device id is a universal unique identifier UUID of the home appliance and may be directly generated by the communication unit of the home appliance . A UUID generation logic may be changed. The server may confirm that the model name is valid using the received device id without overlapping of the device id and store the device id in the memory . After the product registration request has finished the home appliance may attempt to first access the server .

If the home appliance does not include a display screen product registration may be performed using the mobile terminal . When the home appliance is first turned on the home appliance is not in a Wi Fi connection state station mode . The mobile terminal is switched to the Wi Fi connection state.

For product registration the home appliance is turned on and the communication unit is particularly in the Wi Fi connection state. The member ID needs to be registered with the server . In a product registration process the mobile terminal requests product information from the home appliance .

The mobile terminal calls the open API and transmits the product information received from the home appliance to the server. In particular a product registration request is transmitted to the server . For product registration the product registration request information or product information transmitted from the home appliance to the server may include user id password device type device id model name etc.

The server may confirm that the model name is valid using the received device id without overlapping of the device id and store the device id in the memory . After the product registration request has finished the home appliance may attempt to first access the server .

The server may perform product registration if a member registration country and a release country of the home appliance are the same. The server may initialize registration information of the home appliance of an existing user if a registration request for the home appliance is received with respect to an already registered home appliance and register the home appliance as a new account.

The user terminal may perform user authentication in order to use the home appliance . First in the user authentication process performed in the mobile terminal the mobile terminal may call the open API and request login from the server .

The server may authenticate login information create a session if authentication is successful and transmit a response including a response code a session value registered appliance information a server address etc. to the mobile terminal . The session value may be created by the server upon first login. Thereafter the mobile terminal may perform authentication using the session value.

The mobile terminal may be connected via TCP connection using the received server address and a port. The mobile terminal may control the home appliance using the information received from the server . For example monitoring remote control diagnosis etc. may be performed.

Next in the user authentication process performed in the home appliance the home appliance may call the open API and request login from the server . The server may transmit a response including the result value of the authentication process to the home appliance .

For authentication of the home appliance the home appliance may be connected to the server over a network. The server may determine whether product registration is performed using the product information received from the home appliance and transmit a response including the result value of the authentication process.

Since the home appliance uses a private IP network the server or the mobile terminal may not be easily connected to the home appliance . In order to solve this problem the server may provide a stable connection function with the home appliance . A server agent may be installed in the home appliance .

If the home appliance is booted the server is accessed over a network using a server address URI of the server agent. The server agent of the home appliance may receive and process a terminal management command in real time.

Network connection between the home appliance using a private IP network and the server is maintained. Network connection between the home appliance and the server is maintained via a KeepAlive ACK message. A current session timeout time of the server is set to 70 seconds. In order to maintain a connection state the home appliance should request KeepAlive ACK every 60 seconds.

In order to continuously use the service of the server via the mobile terminal connection and session maintenance with the server may be required. A connection and session maintenance method between the mobile terminal and the server includes an OpenAPI method and a TCP connection method.

A session timeout time of the server may be set to a first time and may be changed. If logout is performed in the mobile terminal the two connection methods the OpenAPI method and the TCP connection method are stopped and the session in the server is removed.

The server enables multi session. In order to use services of several servers in one home appliance the server may generate multiple sessions using a single ID or multiple IDs.

The server may enable multiple users to use one home appliance . If product registration is performed the home appliance is initialized and master rights are assigned to a user who performs product registration.

A master user may manage the user of the home appliance product registration of which has been performed perform user inquiry deletion registration and transfer master rights. A slave user may request that the master user transfer rights but may not manage the user of the home appliance .

If a specific mobile terminal has rights to control the home appliance another mobile terminal does not have rights to control the home appliance regardless of multi user or multi session. If the master user performs member withdrawal all the registered slave users for the home appliance should be deleted.

In order to use a remote control function of the home appliance in the mobile terminal control rights are required. Only the master user who has first requested a control command from the server has control rights. Server services such as diagnosis or monitoring except for remote control may be provided to all users regardless of control rights.

A message no rights may be transmitted to a user who wishes to obtain control rights after initial connection. If a user who has first requested a control command from the server logs out of the server control rights are transferred to a user who has first requested a control command among the connected users.

In order to use the service of the server in real time the server agent installed in the home appliance performs connection session maintenance with the server . The server agent may process a service command of the server .

The server agent is turned on after power on of the home appliance product registration and Wi Fi connection to perform session connection with the server . Thereafter if Wi Fi is disconnected or the home appliance is powered off the server agent is turned off. If the home appliance is powered on and Wi Fi connection is performed again session connection with the server may be automatically performed.

An admin portal site may be used to confirm member information and registration of the home appliance . The admin portal site may be used to inquire about a variety of statistical information such as use history statistics. The admin portal site may be used for site management menu right management notice material management code management right management of each user or home appliance management for confirming information about or history of home appliances . The admin portal site may be used for firmware SW management schedule management push management push message management push messaging history query file download management etc.

A control service refers to a service for enabling the mobile terminal to remotely control the home appliance . Only a mobile terminal master which has first requested a control command from the server may use the control service. If a user who has first requested a control command from the server logs out of the server control rights are transferred to a user who has first requested a control command among the connected users.

A control procedure requested by the mobile terminal will now be described. First an authentication request is transmitted from the mobile terminal to the server a terminal connection state inquiry request is transmitted from the mobile terminal to the server a control command for a home appliance to be controlled is transmitted from the mobile terminal to the server and the control command is transmitted from the server to the home appliance . The home appliance performs the control command and transmits a control result value to the server and the server transmits the received control result value to the mobile terminal .

A monitoring service is provided to monitor a current state of the home appliance . The monitoring service may be provided to all users requesting the monitoring service regardless of control rights. The monitoring procedure requested by the mobile terminal will now be described.

The mobile terminal may transmit an authentication request to the server . The mobile terminal may transmit a terminal connection state inquiry request to the server . The mobile terminal may transmit information about a home appliance to be monitored to the server .

The server transmits a requested monitoring command to the home appliance. The home appliance extracts monitoring data and transmits the extracted data to the server . The server transmits the received monitoring data to the mobile terminal .

For example monitoring data is transmitted only once upon monitoring request if a home appliance to be monitored is a refrigerator and may be transmitted several times if the home appliance to be monitored is not the refrigerator

The refrigerator which is the home appliance may store some recipe information. However if a new recipe is developed or a previously provided recipe contains errors the recipe information needs to be updated.

The server or the refrigerator which is the home appliance may request recipe information distribution. The refrigerator may check recipe update and transmit a recipe information distribution request. In particular the refrigerator may request update information via a display unit .

The refrigerator receives the update information from the server and displays the update information. If update is necessary the home appliance may download a recipe information file from the server .

The server may transmit a guide message update guide message to the home appliance . The home appliance which has received the message may download the recipe information file from the server .

A washing machine may store some information about basic washing courses. However if a new washing course method is developed the information about the washing courses needs to be updated.

The mobile terminal the washing machine or the server may request washing course information distribution.

The washing machine transmits an update list inquiry request for washing course information to the server receives an update list from the server and displays the update list.

The washing machine may select an update item according to user input and download a washing course information file for the update item.

The mobile terminal transmits an update list inquiry request for washing course information to the server via the Open API. The server inquires about a course list installed in the washing machine . The mobile terminal receives an update list from the server via the Open API. At this time the course list installed in the washing machine and the total course list registered with the server may be transmitted together.

The mobile terminal may display the update list received from the server . At this time the mobile terminal may distinguishably display the list installed in the washing machine

The mobile terminal transmits an update item to the server via the Open API according to user input. The server transmits update notification to the washing machine . The washing machine downloads washing course information content selected by a user from the server .

The server may transmit a guide message for example an update guide message to the washing machine . The washing machine displays the message and transmits an update list inquiry request for washing course information to the server according to user input. The washing machine receives an update list from the server and displays the update list. The washing machine may select an update item and download a washing course information file for the update item according to user input.

The server may transmit an update package generated for firmware update to the home appliance . The server receives and stores the update package from a manufacturer. The server transmits a notification message to the home appliance in order to perform update using the registered update package. The home appliance downloads and installs the update package and then reboots. A firmware update result is transmitted to the server .

A smart diagnosis service refers to a service for diagnosing the state of the home appliance and displaying a diagnosis result to a user. The diagnosis service may be used by all requesting users.

First a diagnosis procedure using a mobile terminal will be described. The mobile terminal issues an authentication request to the server . The mobile terminal transmits a terminal connection state inquiry request to the server . The mobile terminal selects a home appliance to be diagnosed via the server .

The server transmits a diagnosis command for the selected home appliance to the home appliance . The home appliance extracts diagnosis data and transmits the extracted diagnosis data to the server . The server transmits the diagnosis data to the mobile terminal .

A diagnosis procedure requested by the home appliance will be described. According to user input the home appliance transmits a Wi Fi diagnosis request via a user interface UI of a display. The home appliance transmits a diagnosis data value to the server . The server which has received the diagnosis data value stores diagnosis data. The server may transmit the diagnosis data to a call center server without processing the diagnosis data.

The server may provide firmware of a ZigBee modem for performing communication with respect to a smart grid. ZigBee modem FW update may be performed in two steps from the viewpoint of the user.

The user may call an electric power company to check whether a smart meter or an energy management system EMS used in a user s home may perform communication before purchasing the home appliance . The user may call the electric power company to check the version of the smart meter or the EMS used in the user s home before utilizing the ZigBee modem. The user may check whether the version displayed on the setting screen of the home appliance is equal to the version of the smart meter or the EMS checked via the electric power company. If these versions are different the user may execute ZigBee FW update according to predetermined input.

Then the home appliance may access the server based on user input and receive a ZigBee FW list from the server . The home appliance displays the received list and downloads selected ZigBee FW according to user input. At this time the ZigBee FW may be downloaded via Wi Fi communication. The home appliance may update the received ZigBee FW. After update the home appliance may be reset to access the smart meter.

The home appliance may use a push service for transmitting a message from the server to the home appliance in order to transmit a real time event or a completion state. If a push function is activated in the mobile terminal the home appliance may transmit a state message of various functions a course progress state of the washing machine a refrigeration freezing setting state of the refrigerator a course progress state of a cooker etc. to the mobile terminal . In the push service procedure if the home appliance registers the push message with the server the server transmits the push message to a push center and the push center transmits the message to the mobile terminal .

Examples of the push message of the refrigerator may include special freezing setting notification special freezing release notification special freezing completion notification etc.

Examples of the push message of the washing machine may include error notification of the washing machine washing completion notification etc.

Examples of the push message of the cooker may include cooking completion notification cleaning time notification of the cooker cooking course notification warming up notification of the cooker water supplementation notification for steaming etc.

A food list and a shopping list of the refrigerator may be sent to the mobile terminal via the server . The refrigerator requests the food list from the server . The refrigerator receives the food list from the server and displays the food list. The food list and the shopping list may be updated according to user input. The refrigerator may transmit the updated food list and shopping list to the server .

Alternatively the food list and the shopping list may be updated using the mobile terminal. The mobile terminal logs in to the server using an ID and a password. The mobile terminal requests the food list from the server via the Open API. The mobile terminal receives the food list from the server via the Open API and displays the food list. The mobile terminal may update the food list and the shopping list according to user input. The mobile terminal may transmit the updated food list and shopping list to the server via the Open API.

The mobile terminal may transmit photo data of the user to the refrigerator which is the home appliance . The mobile terminal may transmit photo data selected from the gallery to the server and the server may transmit the received photo data to the home appliance . The home appliance may receive the selected photo data from the server .

When member registration is performed with respect to the server the server may store member information in a database DB . In the member information a password an email a telephone number a mobile phone number etc. all of which are personal information may be encrypted and stored. When the user withdraws from the server the server may delete the personal information and store an ID a registration date a withdrawal date etc. to prevent overlapping registration.

When the user performs product registration for mapping between the user and the home appliance the server may store and manage product information. The product information may include a UUID of the home appliance a model name a user ID a product registration date etc. If the user deletes the product information the information about the home appliance is not deleted and the user ID value mapped to the home appliance may be set to null.

The server may store a service history of the user. The stored service history may be used as data for providing a better service. If the user deletes the product information the user history of the home appliance may be deleted after being backed up to the server .

The user may use a diagnosis data history stored in the server in order to view the diagnosis state of the home appliance . Accordingly the server may store and manage diagnosis data in the server when executing a diagnosis service of the home appliance . When the user deletes product information the diagnosis history of the home appliance may be deleted after being backed up to the server .

In order to use the amount of power used by the home appliance in the mobile terminal the home appliance periodically transmits power information to the server and the server stores the power information. In particular the server may store the power data in minutes hours days. The method for managing the home appliance may include a method for managing the home appliance by accessing a portable server via a terminal and a method for managing the home appliance using the mobile terminal .

The server may include a plurality of internal servers. In the figure the server includes a DM server a DL server a notify server a portal server a report server and a legacy server . The DM server may include an Open API and a real time interface and perform Open API based communication and real time interface based communication.

When accessing the server via the terminal the DM server and a DM client interwork using a centralized management method and a plurality of home appliance may be batch processed via one registration operation. Statistical management may be performed via work management. When accessing the server via the mobile terminal the user may remotely manage the home appliance thereof and interwork with the DM client or an SA agent installed in the home appliance via an Open API real time interface of the DM server

The real time interface method has higher speed than that of the Open API method but transmission of file data to the home appliance may be difficult. The mobile terminal may access the server using the AP apparatus a network a mobile network etc. The mobile terminal may remotely manage the home appliance using the Open API or the real time interface provided by the DM server

The interworking method between the mobile terminal and the server may be divided into an Open API communication method and a real time interface based communication method. The Open API communication method may be used upon authentication processing or when the file data stored in the server is transmitted to the home appliance . The real time interface based communication method may be used for real time processing such as control command delivery and result reception or monitoring.

In the authentication process Sa the mobile terminal transmits authentication information to the server via the Open API Sa1 . The server transmits authentication approval and TCP port information in response thereto Sa2 . The mobile terminal determines whether to access the server via the Open API or the real time interface Sa3 .

The management process Sb via an Open API may include step Sb1 of transmitting a work request via the Open API from the mobile terminal to the server and step Sb2 of transmitting a work result from the server to the mobile terminal in response thereto. The management process Sc via the real time service may include a work request and result reception step Sco via a TCP channel.

The server may perform multi session processing and session maintenance time synchronization. The server processes sessions between the mobile terminal and the home appliance if multiple sessions are present. The server may perform session maintenance time synchronization between the Open API and the real time interface RTI .

For example after the mobile terminal logs in to the server using the Open API session maintenance time processing according to the RTI communication method with the mobile terminal may be performed according to a session maintenance period.

The server may perform device multi session processing. The server may perform authentication of the mobile terminal via the Open API and perform registration via the RTI. The server may manage device multi session via authentication and registration of the mobile terminal . The mobile terminal requests user authentication from the server using a user ID and a password via the Open API. The server transmits a device ID list and an RTI URL manageable by the user ID to the mobile terminal .

The mobile terminal starts management of the home appliance via the Open API using the device ID list and the RIT URL.

Multi user authentication may be processed via the Open API and multi user management using a single ID via the Open API is possible.

When the server manages the home appliance via the Open API if the management operation is being performed in the home appliance DM session processing is impossible and thus a message indicating that the management operation is being performed may be returned via the Open API.

The server may not simultaneously transmit two or more management commands of the home appliance via the Open API but may receive a result of one management command and then transmit another management command.

The mobile terminal may transmit a device ID of the home appliance to be managed and a home appliance connection state request message to the server using the URL of an RTI server in the DM server

The mobile terminal is registered with the RTI of the server and the RTI may transmit manageable state information in response to the home appliance connection state request message.

If the number of home appliances to be managed is N before the management command request of the home appliances the device ID is included in the home appliance connection state request message and the manageable state of the home appliance is checked by the response of the RTI of the server. At this time multi device management is possible by one open RTI TCP socket and re access is not necessary.

Multi user management using a single ID is possible via the RTI. All users may perform diagnosis monitoring management etc.

In the robot cleaner only the mobile terminal which has first accessed the RTI of the server may access the RTI and mobile terminals which have accessed the RTI thereafter may not access the RTI.

Control is possible by the user or the mobile terminal which has been first registered with the RTI of the server only. In particular a message no rights may be transmitted to a user or mobile terminal which wishes to have control rights after initial connection.

If a user or mobile terminal which has been first registered with the RTI of the server logs out of the server control rights are transferred to a user or mobile terminal which has first requested a control command among the registered users or mobile terminals.

Referring to a first mobile terminal first transmits login information to the server to log in to the server Sd1 . Then the server transmits a device list and a session ID for the home appliance to the first terminal via the Open API Sd2 . The first mobile terminal which has received the device list and the session list accesses the RTI of the server using the session ID Sd3 . Then the first mobile terminal acquires control rights.

After the first mobile terminal accesses the RTI of the server if a second mobile terminal accesses the RTI of the server Sd4 the second mobile terminal does not acquire control rights. Thereafter if the first mobile terminal has logged out from the server the second mobile terminal may acquire control rights.

A single user may simultaneously manage N home appliances via the RTI . If all users who are registered with or connected to the RTI request monitoring the RTI transmits one monitoring start request to the home appliance and distributes monitoring data to all users or mobile terminals.

If the mobile terminal logs in via the Open API and accesses the RTI the Open API and the RTI module preferably maintain the same session with respect to the mobile terminal . If the mobile terminal logs in via the Open API and is registered with the RTI the mobile terminal has a session maintenance time corresponding to the time set in the server . The mobile terminal preferably transmits a session maintenance request to the Open API and the RTI before the set time has elapsed in order to add the session maintenance time to the set time.

The mobile terminal transmits a session maintenance request to the Open API Se4 for session duration maintenance and the Open API initializes the session duration. The mobile terminal transmits a session maintenance request to the RTI Se5 for session duration maintenance and the RTI initializes the session duration. Thus it is possible to maintain the session duration.

At this time data further transmitted to the mobile terminal may not include a device type unlike . That is a device list of all manageable home appliances corresponding to the user ID may be further transmitted from the server to the mobile terminal . If an RTI service is used authentication may be requested via an interface. That is separate authentication may be necessary in the RTI of the server.

If real time processing is necessary during the service of the Open API a real time interface protocol may be used. Such a protocol may use a JSON format having easy extensibility in a body of a transport layer. As the protocol of the mobile terminal and the notify server for extensibility a JSON protocol may be used. JSON is an abbreviation for JavaScript Object Notation is notation of an object using JavaScript and enables light data exchange because few supplementary separators are used when data is exchanged over the Internet.

In message transmission the mobile terminal transmitter may transmit JSON data to the real time interface receiver of the server . In message reception the real time interface receiver of the server may transmit JSON data to the transmitter the mobile terminal in response to message transmission in the following format.

For example a real time interface command based on a JSON data format may be a diagnosis start command a diagnosis command processing result diagnosis data monitoring start stop command monitoring command processing result monitoring stop notification state change upon monitoring a remote control command a remote control command processing result etc. of the server.

For example the mobile terminal may transmit a connection state information request of the home appliance to the RTI of the server based on the JSON data format and receive connection state result information from the RTI of the server based on the JSON data format.

Similarly the mobile terminal may transmit a session maintenance request to the RTI of the server based on the JSON data format and receive a session maintenance request result from the server based on the JSON data format. The mobile terminal may transmit a home appliance diagnosis start stop request to the RTI of the server based on the JSON data format and receive a result from the server based on the JSON data format.

The home appliance may transmit a diagnosis result to the RTI of the server based on the JSON data format and the RTI of the server may transmit a diagnosis result to the mobile terminal based on the JSON data format upon diagnosis completion.

The mobile terminal may transmit a home appliance monitoring start stop request to the RTI of the server based on the JSON data format and receive a result from the server based on the JSON data format. The mobile terminal may transmit a remote control command to the RTI of the server based on the JSON data format and receive a result from the server based on the JSON data format.

The portal server stores the product information Si2 . The portal server transmits the product information to an Open API of the server Si3 . The Open API stores the product information Si4 . The Open API transmits a product information storage result to the portal server Si4 .

The portal server transmits product registration result information to the home appliance Si5 . The home appliance is connected to the server more particularly a notify server of the server via TCP connection Si6 . Thereafter the notify server may transmit a product registration result to the mobile terminal .

The mobile terminal requests initialization after TCP connection with the home appliance Sj3 . The home appliance responds to the request Sj4 the mobile terminal requests product information Sj5 and the home appliance transmits the product information to the mobile terminal in response thereto Sj6 . The mobile terminal requests an AP apparatus list Sj7 and the home appliance transmits the AP apparatus list stored in the home appliance to the mobile terminal Sj8 .

The mobile terminal transmits an AP apparatus setting request to the home appliance by referring to the received AP apparatus list Sj9 . The home appliance sets the AP apparatus in response to the request and transmits an AP apparatus setting response Sj10 . The mobile terminal transmits a request to release the set AP apparatus Sj11 and the home appliance transmits a release response to the request Sj12 . Thereafter the home appliance performs access to the AP apparatus. The home appliance ends the soft AP mode and operates in a client mode.

The home appliance transmits a product registration request to the server e.g. the portal server of the server after switching to the client mode Sj12 . At this time the product information may also be transmitted. The product information may include user id password device type device id model name etc.

The portal server stores the product information Sj14 . The portal server transmits the product information to the Open API of the server Sj15 . The Open API stores the product information Sj16 . The Open API transmits a product information storage result to the portal server Sj17 .

The portal server transmits product registration result information to the home appliance Sj18 . The home appliance is connected to the server e.g. the notify server of the server via TCP connection Sj19 . Thereafter the notify server may transmit a product registration result to the mobile terminal .

The notify server checks a connection state of the home appliance Sk2 . If the home appliance is not connected the notify server transmits to the mobile terminal a response indicating that the home appliance is not connected.

If the home appliance is connected the notify server transmits a TCP relay including a remote control command to the home appliance e.g. an agent of the home appliance Sk3 . The agent calls the API via the controller of the home appliance Sk4 . The controller of the home appliance transmits an API response result the remote control result according to the remote control command to the agent Sk5 .

The home appliance e.g. the agent of the home appliance transmits a TCP relay including a remote control result according to the remote control command to the server e.g. the notify server of the server Sk6 . The server e.g. the notify server of the server transmits a server control response to the mobile terminal Sk7 . Therefore the mobile terminal may receive remote control and a result thereof.

The Open API of the server searches for a registered home appliance and searches for product information a notify server address for TCP connection and a port S14 after login approval. The Open API of the server transmits the product information the notify server address for TCP connection and the port to the mobile terminal . Therefore the mobile terminal can make a TCP connection request.

The notify server checks whether the home appliance requested by the mobile terminal has been registered or connected to the server Sm2 . A result value thereof is transmitted to the mobile terminal Sm3 . Therefore it is possible to determine registration and connection of a specific home appliance to the server via the server .

The home appliance transmits an address information request for the DL server to the DM server Sn3 for update to a higher firmware version. The DM server transmits address information of the DL server to the home appliance Sn4 .

The home appliance transmits a download request for a firmware update file to the DL server using the address information of the DL server Sn5 . The DL server transmits the firmware update file to the home appliance Sn6 . The home appliance performs firmware update using the received firmware update file.

The home appliance transmits a firmware update completion report to the DM server Sn7 after firmware update completion. The DM server transmits a response to the firmware update completion report to the home appliance Sn8 . Therefore the home appliance may update firmware and the server may confirm firmware update completion of the home appliance .

The home appliance transmits a firmware update file download request to the DL server without a DL server address information request described with reference to So3 . The DL server transmits the firmware update file to the home appliance So4 . The home appliance performs firmware update using the received firmware update file.

The home appliance transmits a firmware update completion report to the DM server So5 after firmware update completion. The DM server transmits a response to the firmware update completion report to the home appliance So6 . Therefore the home appliance may update firmware and the server may confirm firmware update completion of the home appliance .

The mobile terminal selects specific software from the software update list based on user input and transmits a software update request to the Open API Sp3 . The Open API transmits a work ID to the mobile terminal and transmits a notify message for update to the notify server Sp4 .

The notify server transmits the notify message for software update to the home appliance e.g. the agent of the home appliance Sp5 . The notify message is sent to the controller of the home appliance .

The home appliance e.g. the controller of the home appliance transmits a software download request to the server e.g. the Open API of the server Sp6 . The Open API of the server transmits URL information for software download to the home appliance Sp7 . The home appliance is connected to the server in DL using the URL information and transmits a download request Sp8 .

The server transmits a software file to the home appliance Sp9 . The home appliance downloads a software file. After download completion the controller of the home appliance finishes DL connection Sp10 . The controller of the home appliance transmits a software download result to the server Sp11 and the server e.g. the Open API of the server transmits a result to the home appliance as a response Sp12 .

The mobile terminal may inquire of the server e.g. the Open API of the server about a software download result Sp13 and the Open API may transmit the result to the mobile terminal Sp14 . Therefore it is possible to perform software download of the home appliance and check the result thereof using the mobile terminal .

The home appliance accesses the server e.g. the media server Sq5 . After connection the home appliance transmits media data including at least one of video data and audio data to the media server Sq6 .

The mobile terminal transmits an access request to the media server Sq7 and receives a response thereto Sq8 . If the mobile terminal has accessed the media server the mobile terminal requests media data from the media server Sq9 . Then the mobile terminal receives a response thereto Sq10 . The media server transmits the media data to the mobile terminal according to the media data request and the mobile terminal receives the media data Sq11 .

The mobile terminal transmits a camera stop request to the server e.g. the notify server Sq10 . The server e.g. the notify server transmits the camera stop request to the home appliance Sq11 and receives a response thereto Sq12 . The response is transmitted to the mobile terminal Sq13 .

The home appliance capable of providing the messenger function exchanges data with a DM server of the first server via TCP communication. A representative server or portal server of the first server may exchange member management information or home appliance management information with the chat server . The DM server of the first server may exchange control information content information push message etc. of the home appliance using an Open API or RTI method.

The TV may manage the home appliance as a terminal or a chat service. Remote control or monitoring of the TV is possible. The second server for the TV may be separately provided.

The TV may transmit login information to the first server e.g. the DM server via the Open API to complete login authentication. The first server e.g. the DM server may issue a session key of the second server and transmit session key information of the second server to the TV

The TV transmits the session key information of the second server to the second server . The second server may access the first server e.g. the DM server via the Open API. After connection the second server and the first server may perform UDP communication.

According to embodiments of the present disclosure since the server includes a memory a communication module configured to exchange data with a mobile terminal or a home appliance and a processor configured to receive login information from the mobile terminal based on a first communication mode to perform login based on the login information to receive a session maintenance request from the mobile terminal based on a second communication mode after login and to initialize a session duration according to the session maintenance request it is possible to control the home appliance in real time via the server.

In particular since the server provides information about a registered home appliance to the mobile terminal after login it is possible to control the home appliance in real time via the server.

Since the server assigns control rights to a user or mobile terminal which first performs login and transmits a message indicating no control rights to the other users or mobile terminals it is possible to assign control rights to one user or mobile terminal.

Since the server provides monitoring data to all connected users or mobile terminals all users or mobile terminals may perform monitoring regardless of control rights.

Since the server may transmit any one of a control command a monitoring command a diagnosis command and a software download command for the home appliance from the mobile terminal to the home appliance it is possible to provide user convenience.

The home appliance according to the foregoing embodiments is not restricted to the embodiments set forth herein. Therefore variations and combinations of the exemplary embodiments set forth herein may fall within the scope of the present disclosure.

The home appliance according to the foregoing embodiments may be implemented as code that can be written to a computer readable recording medium and can thus be read by a processor. The computer readable recording medium may be any type of recording device in which data can be stored in a computer readable manner. Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disk optical data storage and a carrier wave e.g. data transmission over the Internet . The computer readable recording medium may be distributed over a plurality of computer systems connected to a network so that computer readable code is written thereto and executed therefrom in a decentralized manner. Functional programs code and code segments to realize the embodiments herein can be construed by one of ordinary skill in the art.

In accordance with an aspect of the present disclosure the above and other objects can be accomplished by the provision of a server including a memory a communication module configured to exchange data with a mobile terminal or a home appliance and a processor configured to receive login information from the mobile terminal based on a first communication mode to perform login based on the login information to receive a session maintenance request from the mobile terminal based on a second communication mode after login and to initialize a session duration according to the session maintenance request.

In accordance with an aspect of the present disclosure there is provided a home appliance system including a mobile terminal configured to transmit login information based on a first communication mode and to transmit a session maintenance request based on a second communication mode a server configured to receive login information from the mobile terminal based on the first communication mode to perform login based on the login information to receive the session maintenance request from the mobile terminal based on the second communication mode after login and to initialize a session duration according to the session maintenance request and a home appliance connected to the server.

The terms module and unit used in description of components are used herein to aid in the understanding of the components and the terms module and unit may be used interchangeably.

Any reference in this specification to one embodiment an embodiment example embodiment etc. means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the disclosure. The appearances of such phrases in various places in the specification are not necessarily all referring to the same embodiment. Further when a particular feature structure or characteristic is described in connection with any embodiment it is submitted that it is within the purview of one skilled in the art to effect such feature structure or characteristic in connection with other ones of the embodiments.

Although embodiments have been described with reference to a number of illustrative embodiments thereof it should be understood that numerous other modifications and embodiments can be devised by those skilled in the art that will fall within the spirit and scope of the principles of this disclosure. More particularly various variations and modifications are possible in the component parts and or arrangements of the subject combination arrangement within the scope of the disclosure the drawings and the appended claims. In addition to variations and modifications in the component parts and or arrangements alternative uses will also be apparent to those skilled in the art.

