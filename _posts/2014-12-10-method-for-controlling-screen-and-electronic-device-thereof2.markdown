---

title: Method for controlling screen and electronic device thereof
abstract: A method for controlling a screen of an electronic device is provided. The method includes displaying a plurality of subscreens by dividing a screen, the plurality of subscreens comprising an overlapping region of a certain area with a neighboring subscreen, selecting one of the plurality of subscreens, displaying the selected one of the plurality of subscreen in a mirroring region, and displaying, when receiving a user drag from the selected one of the plurality of subscreens displayed in the mirroring region to a neighboring screen comprising the overlapping region with the selected one of the plurality of subscreens, the neighboring screen comprising the overlapping region with the selected one of the plurality of subscreens, in the mirroring region according to the drag.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09626102&OS=09626102&RS=09626102
owner: Samsung Electronics Co., Ltd.
number: 09626102
owner_city: Suwon-si
owner_country: KR
publication_date: 20141210
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed on Dec. 16 2013 in the Korean Intellectual Property Office and assigned Serial number 10 2013 0156364 the entire disclosure of which is hereby incorporated by reference.

With advances in information communication technology and semiconductor technology various electronic devices are advancing to multimedia devices for providing various multimedia services. For example the electronic device provides various multimedia services such as messenger service broadcasting service wireless Internet service camera service and music play service.

For the portability the electronic devices are getting slimmer and lighter and include a touch screen for touch input. Since users want a large screen the electronic devices including the touch screen are getting bigger.

However while the user of the electronic device desires to control the electronic device with one hand it is difficult to control the screen due to the large screen of the electronic device. In this regard the electronic device needs to satisfy the one handed control by the user.

The above information is presented as background information only to assist with an understanding of the present disclosure. No determination has been made and no assertion is made as to whether any of the above might be applicable as prior art with regard to the present disclosure.

Aspects of the present disclosure are to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present disclosure to provide a screen control method for controlling an entire screen using a subscreen in an electronic device and the electronic device thereof.

Another aspect of the present disclosure is to provide a screen control method for controlling an entire screen with one hand in an electronic device and the electronic device thereof.

Another aspect of the present disclosure is to provide a screen control method for effectively utilizing a large screen in an electronic device and the electronic device thereof.

In accordance with an aspect of the present disclosure a method for controlling a screen of an electronic device is provided. The method includes displaying a plurality of subscreens by dividing a screen the plurality of subscreens comprising an overlapping region of a certain area with a neighboring subscreen selecting one of the plurality of subscreens displaying the selected one of the plurality of subscreens in a mirroring region and displaying when receiving a user drag from the selected one of the plurality of subscreens displayed in the mirroring region to a neighboring screen comprising the overlapping region with the selected one of the plurality of subscreens the neighboring screen comprising the overlapping region with the selected one of the plurality of subscreens in the mirroring region according to the drag.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes a touch screen a memory and a processor configured to display a plurality of subscreens by dividing a screen the plurality of subscreens comprising an overlapping region of a certain area with a neighboring subscreen to select one of the plurality of subscreens to display the selected one of the plurality of subscreens in a mirroring region and to display when receiving a user drag from the selected one of the plurality of subscreens displayed in the mirroring region to aneighboring screen comprising the overlapping region with the selected one of the plurality of subscreens to display the neighboring screen comprising the overlapping region with the selected one of the plurality of subscreen in the mirroring region according to the drag.

Other aspects advantages and salient features of the disclosure will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses various embodiments of the present disclosure.

Throughout the drawings like reference numerals will be understood to refer to like parts components and structures.

The following description with reference to the accompanying drawings is provided to assist in a comprehensive understanding of various embodiments of the present disclosure as defined by the claims and their equivalents. It includes various specific details to assist in that understanding but these are to be regarded as merely exemplary. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the various embodiments described herein may be made without departing from the scope and spirit of the present disclosure. In addition descriptions of well known functions and constructions may be omitted for clarity and conciseness.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the present disclosure. Accordingly it should be apparent to those skilled in the art that the following description of various embodiments of the present disclosure is provided for illustration purpose only and not for the purpose of limiting the present disclosure as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

By the term substantially it is meant that the recited characteristic parameter or value need not be achieved exactly but that deviations or variations including for example tolerances measurement error measurement accuracy limitations and other factors known to those of skill in the art may occur in amounts that do not preclude the effect the characteristic was intended to provide.

An electronic device according to the present disclosure may include one or more of a smart phone a tablet Personal Computer PC a mobile phone a video phone an e book reader a desktop PC a laptop PC a netbook computer a Personal Digital Assistant PDA a Portable Multimedia Player PMP an MP3 player an accessory an electronic appcessory a camera a wearable device a wrist watch a refrigerator an air conditioner a vacuum cleaner an artificial intelligence robot a television TV a Digital Versatile Disc DVD player an audio system an oven a microwave oven a washing machine an electronic bracelet an electronic necklace an air purifier a digital frame medical appliances a navigation device a Global Positioning System GPS receiver an Event Data Recorder EDR a Flight Data Recorder FDR a set top box a TV box an electronic dictionary an in vehicle infotainment electronic equipment for ship avionics a security device an e textile a digital key a camcorder a game console a Head Mounted Display HMD a flat panel display device an electronic album part of furniture or building structure having the communication function an electronic board an electronic sign input device and a projector. Those skilled in the art shall understand that the electronic device of the present disclosure is not limited those devices.

Referring to the electronic device may include a bus a processor a memory an input part a touch screen and a communication part but is not limited thereto.

The bus may interlink the components e.g. the processor the memory the input part the touch screen and the communication part of the electronic device and transferring communication between the components.

The processor may receive an instruction from the components of the electronic device via the bus interpret the received instruction and perform an operation or a data processing according to the interpreted instruction. The processor controls to execute at least one program stored in the memory and to provide a service corresponding to the program. For example the processor may execute a mirroring region control program a screen split program and a display control program to display a plurality of subscreens by splitting the screen to select one of the subscreens to display the selected subscreen in a mirroring region and when receiving a user drag from the subscreen displayed in the mirroring region to a neighboring screen including an overlapping region with the subscreen to display the neighboring screen including the overlapping region with the subscreen in the mirroring region according to the drag.

The processor may include one or more Application Processor APs not shown and one or more Communication Processors CPs not shown . Herein the AP and the CP may be included in the processor or in different Integrated Circuit IC packages. The AP and the CP may be included in a single IC package.

The AP may control hardware or software components connected to the AP by driving an operating system and or an application program and carry out data processing and operations including multimedia data. Herein the AP may be implemented using a System on Chip SoC . The CP may perform at least part of the multimedia control function.

The CP may identify and authenticate a terminal in a communication network using a Subscriber Identity Module SIM card. In so doing the CP may provide the user with the service including voice telephony video telephony text message and packet data. The CP may control the data transmission and reception of the communication part .

The AP or the CP may load and process the instruction and or the data received from its non volatile memory or at least one of the other components in a volatile memory. The AP or the CP may store data received from or generated by at least one of the other components in the non volatile memory. The CP may manage data links and convert the communication protocol in the communication between the electronic device including the hardware and the other electronic devices connected over the network. Herein the CP may be implemented using a SoC. Additionally the processor may further include a Graphics Processing Unit GPU .

The memory may store the instruction and or the data received from or generated by one or more components e.g. the processor the input part the touch screen and the communication part of the electronic device .

The memory stores one or more programs for the service of the electronic device . For example the memory may include the mirroring region control program the screen split program and the display control program . Each program may include a program module and the program module may be implemented using software firmware and hardware or a combination of at least two of them.

The mirroring region control program may include at least one software component for determining one of the subscreens to display in the mirroring region. For example the mirroring region control program may display an icon corresponding to the other subscreen not displayed in the mirroring region around the mirroring region. When the displayed icon is selected the mirroring region control program may control to display the subscreen corresponding to the selected icon in the mirroring region.

For example the mirroring region control program may detect the touch during a reference time around the mirroring region. The mirroring region control program may display an object corresponding to the multiple subscreens at the detected touch point. When the displayed object is selected the mirroring region control program may control to display the subscreen corresponding to the selected object in the mirroring region.

For example the mirroring region control program may detect a vertical drag in a certain region of the mirroring region. The mirroring region control program may control to display the corresponding subscreen in the mirroring region according to a movement distance of the detected drag.

For example the mirroring region control program may determine whether the user s drag moves from the one subscreen displayed in the mirroring region to the overlapping region. The electronic device user may drag the screen displayed in the mirroring region to a certain distance. When receiving the user drag from the one subscreen displayed in the mirroring region to a neighboring screen including the overlapping region with the subscreen the mirroring region control program may display the neighboring screen including the overlapping region with the one subscreen in the mirroring region according to the drag. In so doing the mirroring region control program may identify a drag direction to the overlapping region and display the neighboring screen including the overlapping region with the subscreen in the mirroring region.

The screen split program may include at least one software component for determining the multiple subscreens of the screen. For example the screen split program may determine whether a particular input pattern is detected in the screen. The particular input pattern may determine the multiple subscreens to be displayed in the screen.

Referring the screen split program may determine an area of the subscreens to display in a screen according to a user s particular input pattern. The particular input pattern may touch a corner point of the screen during a certain time and then draw a parabola from the corner point to a left lower point also as a drag end point . Based on such a gesture the screen split program may predict a one hand touch region and calculate the area of the subscreens to display in the screen .

For example the screen split program may detect a closed curve region defined by the input parabola and a horizontal line of the drag end point . The screen split program may determine the greatest square of the closed curve region as the area of the subscreens to display in the screen .

For example the screen split program may determine the multiple subscreens to display in the screen based on a preset criterion. The screen split program may arrange the subscreens of a certain area at regular intervals according to the number of icons or contents displayed in the screen. In so doing the screen split program may arrange the neighboring subscreens of the multiple subscreens to include the overlapping region of the certain area.

The display control program may include at least one software component for displaying screen information in the touch screen . For example the display control program may graphically display the multiple subscreens and the mirroring region in the touch screen . The display control program may include instructions for displaying one of the subscreens in the mirroring region.

The memory may include an internal memory and an external memory. The internal memory may include at least one of the volatile memory e.g. Dynamic Random Access Memory DRAM Static RAM SRAM and Synchronous DRAM SDRAM and the non volatile memory e.g. One Time Programmable Read Only Memory OTPROM PROM Erasable PROM EPROM Electrically EPROM EEPROM mask ROM flash ROM NAND flash memory and NOR flash memory . The internal memory may employ a Solid State Drive SSD . The external memory may include at least one of a Compact Flash CF a Secure Digital SD a Micro SD a Mini SD an extreme digital xD and a memory stick.

The kernel maycontrol or manage system resources e.g. the bus the processor and or the memory used to execute the operation or the function of the other programming modules e.g. the middleware the API and the application . The kernel mayprovide an interface allowing the middleware the API and or the application to access and control or manage the individual component of the electronic device .

The middleware may relay data in the communication between the API or the application and the kernel. The middleware may perform load balancing for a work request received from the at least one application by giving priority of the system resource e.g. the bus the processor and or the memory of the electronic device .

The API which is an interface for the application to control the kernel or the middleware may include at least one interface or function for file control window control image processing or text control.

The input part may send the instruction and or the data generated by the user selection to the processor or the memory via the bus . For example the input part may include a touch panel a pen sensor a key and an ultrasonic input device.

The touch panel may recognize the touch input using at least one of capacitive resistive infrared and Surface Acoustic Wave SAW techniques. The touch panel may further include a controller. The capacitive touch panel may recognize not only the direct touch but also the proximity touch. The proximity touch may be referred to as non contact touch or hovering. The touch panel may further include a tactile layer to provide a tactile response to the user.

The touch screen may display image video and or data to the user. The touch screen includes a touch panel for conducting the input function and the display function at the same time. The touch panel may employ a Liquid Crystal Display LCD or an Active Matrix Organic Light Emitting Diode AMOLED and may be implemented flexibly transparently or wearably.

The touch screen may include a hologram. The hologram may present a three dimensional image in the air using interference of light. The touch screen may further include a control circuit for controlling the touch panel or the hologram.

The communication part may connect the communication between the electronic device and one or more other electronic devices e.g. the electronic device or or the server . The communication part may support short range communication protocol e.g. Wireless Fidelity Wi Fi Bluetooth BT Near Field Communication NFC or network communication e.g. Internet Local Area Network LAN Wide Area Network WAN telecommunication network cellular network satellite network or Plain Old Telephone Service POTS . For example the may communicate across the network with the electronic device or server .

The electronic device may further include a sensor module. The sensor module may include at least one of a gesture sensor a gyro sensor an atmospheric pressure sensor a magnetic sensor an acceleration sensor a grip sensor a proximity sensor a Red Green Blue RGB sensor a biometric sensor a temperature humidity sensor a light sensor and an UltraViolet UV sensor. The sensor module may measure a physical quantity or detect the operation status of the electronic device and convert the measured or detected information to an electric signal. The sensor module may include an E noise sensor an electromyography EMG sensor an electroencephalogram EEG sensor an electrocardiogram ECG sensor or a finger print sensor.

The names of the hardware components of the present disclosure may vary according to a type of the electronic device . Depending on the type of the electronic device the electronic device may include at least one of the components omit some components or further include other components.

Referring to the processor includes a mirroring region controller a screen splitter and a display controller but is not limited thereto.

The mirroring region controller may execute the mirroring region control program stored in the memory and determine one of the subscreens to display in the mirroring region.

For example the mirroring region controller may display the icon corresponding to the other subscreen not displayed in the mirroring region around the mirroring region. When the displayed icon is selected the mirroring region controller may control to display the subscreen corresponding to the selected icon in the mirroring region.

For example the mirroring region controller may detect the touch during the reference time around the mirroring region. The mirroring region controller may display an object corresponding to the multiple subscreens at the detected touch point. When the displayed object is selected the mirroring region controller may control to display the subscreen corresponding to the selected object in the mirroring region.

For example the mirroring region controller may detect the vertical drag in a certain region of the mirroring region. The mirroring region controller may control to display the corresponding subscreen in the mirroring region according to the movement distance of the detected drag.

For example the mirroring region controller may determine whether the user s drag moves from the one subscreen displayed in the mirroring region to the overlapping region. The electronic device user may drag the screen displayed in the mirroring region to a certain distance. When receiving the user drag from the one subscreen displayed in the mirroring region to the neighboring screen including the overlapping region with the subscreen the mirroring region controller may display the neighboring screen including the overlapping region with the one subscreen in the mirroring region according to the drag. In so doing the mirroring region controller may identify the drag direction to the overlapping region and display the neighboring screen including the overlapping region with the subscreen in the mirroring region.

The screen splitter may execute the screen split program stored in the memory and determine the multiple split subscreens of the screen. The screen splitter may provide the display controller with the determined subscreen information. For example the screen splitter may determine whether the particular input pattern is detected in the screen. The particular input pattern may determine the multiple subscreen regions to display in the screen.

For example the screen splitter may determine the area of the subscreens to display in the screen according to the user s particular input pattern as shown in . The particular input pattern may touch the corner point of the screen during the certain time and then draw the parabola from the corner point to the left lower point . Based on such a gesture the screen splitter may predict the one hand touch region and calculate the area of the subscreens to display in the screen .

For example the screen splitter may detect the closed curve region defined by the input parabola and the horizontal line of the drag end point . The screen splitter may determine the greatest square of the closed curve area as the area of the subscreens to display in the screen .

For example the screen splitter may determine the multiple subscreens to display in the screen based on the preset criterion. The screen splitter may arrange the subscreens of the certain area at regular intervals according to the number of icons or contents displayed in the screen. In so doing the screen splitter may arrange the neighboring subscreens of the multiple subscreens to include the overlapping region of the certain area.

The display controller may execute the display control program stored in the memory and graphically display the screen information fed from the mirroring region controller and the screen splitter through the touch screen .

While the components of the processor may be the separate modules a single module may include them as software components.

Referring to the electronic device displays the multiple split subscreens in operation . In so doing the electronic device may determine whether the particular input pattern is detected in the screen. The particular input pattern may determine the multiple subscreens to be displayed in the screen.

For example the electronic device may determine the area of the subscreens to display in the screen according to the user s particular input pattern as shown in . The particular input pattern may touch the corner point of the screen during the certain time and then draw the parabola from the corner point to the left lower point . Based on such a gesture the electronic device may predict the one hand touch region and calculate the area of the subscreens to display in the screen .

For example the electronic device may detect the closed curve region defined by the input parabola and the horizontal line of the drag end point . The electronic device may determine the greatest square of the closed curve area as the area of the subscreens to display in the screen .

For example the electronic device may determine the multiple subscreens to display in the screen based on the preset criterion. The electronic device may arrange the subscreens of the certain area at regular intervals according to the number of icons or contents displayed in the screen. In so doing the electronic device may arrange the neighboring subscreens of the multiple subscreens to include the overlapping region of the certain area.

Referring to the electronic device may display the multiple split subscreens and of the screen as shown in . The subscreens and may display a text indicating their screen label. The subscreens and may include an overlapping region of a certain area in relation to the neighboring subscreen. A plurality of the overlapping regions may exist and the overlapping regions may be identical or different in area or in shape.

For example the electronic device may further display a mirroring region in part of the screen. The mirroring region may serve as a screen selection input part for selecting one of the subscreens and to be explained. In so doing the mirroring region may display the selected subscreen. For example the mirroring region may be displayed at a preset location or at various locations according to the grip type of the electronic device . The mirroring region may have but not limited to the same size as the subscreen.

For example the electronic device may display one or more function buttons and around the mirroring region . The function buttons and may include but not limited to an option button for the smooth operation of the mirroring region and a cancel button for canceling the recent operation.

Referring to in operation the electronic device selects one of the displayed subscreens. For example the electronic device may select the subscreen by inputting the label of the subscreen to display in the mirroring region . For example the electronic device may select the subscreen by touching the label of the subscreen displayed in the mirroring region . The selection is not limited to those examples and the subscreen to display in the mirroring region may be selected in various manners.

Referring to in operation the electronic device displays the selected subscreen in the mirroring region. In so doing the electronic device may transparently display the other subscreens and so that the user may identify the subscreen to be displayed in the mirroring region . The electronic device may highlight the corresponding subscreen displayed in the mirroring region .

For example the electronic device may allow various gestures such as touch drag swipe and hovering in the mirroring region . The electronic device may process various functions for example execute or edit icons and displayed in the mirroring region . The electronic device may move the corresponding subscreen displayed in the current mirroring region using the overlapping region displayed in the mirroring region to be explained.

Referring to in operation the electronic device determines whether the user drag from the one subscreen displayed in the mirroring region to the neighboring screen including the overlapping region with the one subscreen is received. For example the electronic device user may drag the screen displayed in the mirroring region to a certain distance.

When receiving the user drag from the one subscreen displayed in the mirroring region to the neighboring screen including the overlapping region with the one subscreen the electronic device displays the neighboring screen including the overlapping region with the one subscreen in the mirroring region according to the drag in operation . In so doing the electronic device may identify the drag direction to the overlapping region and display the neighboring screen including the overlapping region with the subscreen displayed in the mirroring region.

Referring to E when the electronic device user drags rightward from the mirroring region to the overlapping region as shown in the electronic device may display a neighboring screen which is on the right of the selected subscreen . For example the electronic device may display the neighboring region in proportion to a drag length moved in the overlapping region . For example when the drag moves into the overlapping region the electronic device may display a preset neighboring screen according to the drag direction. For example when the drag moves into the overlapping region the electronic device may display other neighboring screen according to the drag direction. The displayed subscreen is not limited those neighboring screens and the neighboring screen may be displayed in the mirroring region based on the drag in various fashions. The electronic device may allow various gestures such as touch drag swipe and hovering in the mirroring region . The electronic device may process various functions for example execute or edit the icons and displayed in the mirroring region .

The present disclosure has described but not limited to the screen for selecting the application. For example the electronic device may be operable in the screen where every available application is executed.

Referring to the electronic device displays the one selected subscreen in the mirroring region in operation of and then displays the icons corresponding to the other subscreens around the mirroring region in operation . In so doing the other subscreens may include the other subscreens not displayed in the mirroring region.

Referring to the electronic device may display icons and corresponding to the other subscreens and around a mirroring region . Herein the mirroring region is displaying the selected subscreen . The icons and may include respective screen label information of the other subscreens and .

For example the electronic device may arrange the icons and in an up down left or right side of the mirroring region based on the current subscreen displayed in the mirroring region . For example since the first subscreen and the second subscreen are above the selected subscreen the first icon and the second icon corresponding to the first subscreen and the second subscreen may be placed above the mirroring region . Similarly the third icon corresponding to the third subscreen is placed on the left side of the mirroring region and the fifth icon corresponding to the fifth subscreen is placed below the mirroring region .

For example the electronic device may arrange the icons and at preset locations. Such locations may be defined by the user or at random.

Referring to in operation the electronic device selects the displayed icon. For example the electronic device may touch and select one of the displayed icons and . In so doing the subscreen corresponding to the selected icon may be marked.

Referring to in operation the electronic device displays the subscreen corresponding to the selected icon in the mirroring region. For example the electronic device may display the first subscreen corresponding to the selected icon of in the mirroring region. In so doing the icons may be rearranged around the mirroring region . For example the icons and corresponding to the other subscreens and not displayed in the mirroring region may be arranged in the up down left or right side of the first subscreen based on the first subscreen displayed in the mirroring region . For example the electronic device may rearrange the icons and at preset locations. Such locations may be defined by the user or at random. The electronic device may allow various gestures such as touch drag swipe and hovering in the mirroring region . The electronic device may process various functions for example execute or edit the icons and displayed in the mirroring region .

The present disclosure has described but is not limited to the screen for selecting the application. For example the electronic device may be operable in the screen where every available application is executed.

Referring to the electronic device may display the one selected subscreen in the mirroring region in operation of and then detect the touch during the reference time around the mirroring region in operation . For example the electronic device may detect but not limited to the touch on the corner point of the screen during a certain time. The electronic device may detect the touch on a preset point.

Referring to in operation the electronic device displays the object corresponding to the multiple subscreens at the detected touch point. For example the electronic device may display an object corresponding to the multiple subscreens and based on the touch point. Herein the mirroring region displays the one selected subscreen . The object may include screen label information and of the subscreens and . The screen label information and may be arranged at regular intervals or in a particular region. The object is in but not limited to a fan shape and may have various shapes and sizes.

In operation the electronic device selects the displayed object. For example the electronic device may touch and select one of the screen label information and of the displayed object . In so doing the subscreen corresponding to the selected screen label information may be marked.

In operation the electronic device displays the subscreen corresponding to the selected object in the mirroring region.

Referring to the electronic device may display in the mirroring region the fourth subscreen corresponding to the screen label information of of the selected object of . The electronic device may allow various gestures such as touch drag swipe and hovering in the mirroring region . The electronic device may process various functions for example execute or edit the icons and displayed in the mirroring region .

The present disclosure has described but is not limited to the screen for selecting the application. For example the electronic device may be operable in the screen where every available application is executed.

Referring to the electronic device displays the one selected subscreen in the mirroring region in operation of and then detects the vertical drag in a certain region of the mirroring region in operation .

Referring to the electronic device may detect the vertical drag in a certain region of a mirroring region . The certain region may include but not limited to a right corner region of the mirroring region . Herein the mirroring region displays the one selected subscreen .

Referring to in operation the electronic device displays the corresponding subscreen in the mirroring region according to the movement distance of the drag. In so doing the electronic device may detect the movement distance of the drag. For example when the movement distance of the drag is shorter than a reference distance the electronic device may display a second subscreen in the mirroring region .

Referring to when the movement distance of the drag is longer than the reference distance the electronic device may display a third or fourth subscreen in the mirroring region . As such the electronic device may determine the subscreen to display in the mirroring region based on the movement distance of the drag.

The present disclosure has described but is not limited to the screen for selecting the application. For example the electronic device may be operable in the screen where every available application is executed.

Referring to the electronic device displays the one selected subscreen in the mirroring region in operation of and then determines whether a popup screen to display is detected in operation . For example the popup screen may include but not limited to a message notification screen and may include every content information displayed in the screen.

Referring to in operation the electronic device displays the popup screen in the mirroring region. For example the electronic device may display a popup screen in a mirroring region . The popup screen may be displayed at a certain location of the mirroring region and the user may set the display location.

The present disclosure has described but is not limited to the screen for selecting the application. For example the electronic device may be operable in the screen where every available application is executed.

As set forth above the electronic device controls the unreached screen region within the touched screen region using the subscreen and thus enhances usability for controlling the electronic device with one hand.

While the present disclosure has been shown and described with reference to various embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present disclosure as defined by the appended claims and their equivalents.

