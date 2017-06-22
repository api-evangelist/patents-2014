---

title: Mobile application for gardening
abstract: A system and method using a native mobile application for gardening is disclosed herein. An image of a plant or plant disease is uploaded and sent to a site for identification and advise from an expert or expert database. A response is provided to the gardener, along with helpful information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09417224&OS=09417224&RS=09417224
owner: 
number: 09417224
owner_city: 
owner_country: 
publication_date: 20140720
---
The Present Application claims priority to U.S. Provisional Patent Application No. 61 858 111 filed on Jul. 24 2013 which is hereby incorporated by reference in its entirety.

Application Programming Interface API is a collection of computer software code usually a set of class definitions that can perform a set of related complex tasks but has a limited set of controls that may be manipulated by other software code entities. The set of controls is deliberately limited for the sake of clarity and ease of use so that programmers do not have to work with the detail contained within the given API itself.

BLUETOOTH technology is a standard short range radio link that operates in the unlicensed 2.4 gigaHertz band.

Code Division Multiple Access CDMA is a spread spectrum communication system used in second generation and third generation cellular networks and is described in U.S. Pat. No. 4 901 307.

CRM Customer Relationship Management is a widely implemented strategy for managing a company s interactions with customers clients and sales prospects. CRM involves using technology to organize automate and synchronize business processes and the like principally sales activities but also business processes and the like for marketing customer service and technical support.

Direct Inward Dialing DID involves a carrier providing one or more trunk lines to a customer for connection to the customer s private branch exchange PBX and a range of telephone lines are allocated to this line.

FTP or File Transfer Protocol is a protocol for moving files over the Internet from one computer to another.

Hypertext Transfer Protocol HTTP is a set of conventions for controlling the transfer of information via the Internet from a web server computer to a client computer and also from a client computer to a web server and Hypertext Transfer Protocol Secure HTTPS is a communications protocol for secure communication via a network from a web server computer to a client computer and also from a client computer to a web server by at a minimum verifying the authenticity of a web site.

Internet is the worldwide decentralized totality of server computers and data transmission paths which can supply information to a connected and browser equipped client computer and can receive and forward information entered from the client computer.

Media Access Control MAC Address is a unique identifier assigned to the network interface by the manufacturer.

Organizationally Unique Identifier OUI is a 24 bit number that uniquely identifies a vendor manufacturer or organization on a worldwide basis. The OUI is used to help distinguish both physical devices and software such as a network protocol that belong to one entity from those that belong to another.

Probe Request A frame that contains the advertisement IE for a device that is seeking to establish a connection with a proximate device.

Probe Response A frame that contains the advertisement IE for a device. The Probe Response is sent in response to a Probe Request.

SSID Service Set Identifier is a 1 to 32 byte string that uniquely names a wireless local area network.

User Interface or UI is the junction between a user and a computer program. An interface is a set of commands or menus through which a user communicates with a program. A command driven interface is one in which the user enter commands. A menu driven interface is one in which the user selects command choices from various menus displayed on the screen.

Web Browser is a complex software program resident in a client computer that is capable of loading and displaying text and images and exhibiting behaviors as encoded in HTML HyperText Markup Language from the Internet and also from the client computer s memory. Major browsers include MICROSOFT INTERNET EXPLORER NETSCAPE APPLE SAFARI MOZILLA FIREFOX and OPERA.

Web Server is a computer able to simultaneously manage many Internet information exchange processes at the same time. Normally server computers are more powerful than client computers and are administratively and or geographically centralized. An interactive form information collection process generally is controlled from a server computer to which the sponsor of the process has access.

Wireless Application Protocol WAP is an open global specification that empowers users with mobile wireless communication devices such as mobile phones to easily access data and to interact with Websites over the Internet through such mobile wireless communication device. WAP works with most wireless communication networks such as CDPD CDMA GSM PDC PHS TDMA FLEX reflex iDEN TETRA DECT DataTAC Mobitex and GRPS. WAP can be built on most operating systems including PalmOS WINDOWS CE FLEXOS OS 9 JavaOS and others.

WAP Push is defined as an encoded WAP content message delivered pushed to a mobile communication device which includes a link to a WAP address.

Wireless AP access point is a node on the wireless local area network WLAN that allows wireless devices to connect to a wired network using Wi Fi or related standards.

There is a need for providing gardeners with a rapid response to an inquiry which is correct and beneficial to the gardener.

A method and system for using a mobile application to identify unknown plants or plant diseases. An image of a plant or plant disease is uploaded and sent to a site for identification and advise from an expert.

One aspect of the present invention is a method for using a mobile native application resident on a mobile communication device to identify an unknown plant or a plant disease. The method includes receiving an image inquiry message at a server from a mobile native application of a mobile communication device. The mobile communication device comprises a camera component and a GPS component. The image message comprises an image geographical location information for the image and comments about the image provided by an end user. The image is of a plant plant disease or plant pest. An inquiry concerns the identification of the plant plant disease or plant pest. The method also includes analyzing the image at the server to determine if the image is acceptable. The method also includes transferring the image at the server for substantive content analysis. The method also includes categorizing the image into a predetermined category. The method also includes preparing a response to identify the plant plant disease or plant pest. The response is based on the image the geographical location the comments and information contained in a database of the server. The method also includes transmitting a response message from the server to the mobile native application of a mobile communication device. The response message identifies the plant plant disease or plant pest.

Another aspect of the present invention is a system for using a mobile application resident on a mobile communication device to identify an unknown plant or a plant disease. The system includes a server a network and a mobile communication device. The mobile communication device comprises a mobile native application a camera component and a GPS component. The camera component of the mobile communication device is configured to take an image of a plant plant disease or plant pest. The GPS component is configured to generate a geographical location of the image. The mobile native application is configured to generate an image inquiry message comprising the image the geographical location information for the image and comments about the image provided by an end user. An inquiry concerns the identification of the plant plant disease or plant pest. The server is configured to analyze the image to determine if the image is acceptable. The server is configured to transfer the image for substantive content analysis. The server is configured to categorize the image into a predetermined category. The server is configured to prepare a response to identify the plant plant disease or plant pest wherein the response is based on the image the geographical location the comments and information contained in a database of the server. The server is configured to transmit a response message from the server to the mobile native application of a mobile communication device wherein the response message identifies the plant plant disease or plant pest.

Having briefly described the present invention the above and further objects features and advantages thereof will be recognized by those skilled in the pertinent art from the following detailed description of the invention when taken in conjunction with the accompanying drawings.

As shown in a system for using a mobile application resident on a mobile communication device to identify an unknown plant or a plant disease is generally designated . A gardener end user takes an image of a plant with her mobile communication device . She then sends a message with the image over a communications network to a server that is in communication with a database . At the server site a non expert receives the message with the image and processes the message with the image for further analysis as set forth below. The analysis includes identification and further advice for the gardener.

The client side experience is set forth below. The client device is preferably a mobile communication device such as a mobile phone or a tablet computer. The mobile communication device has a native mobile application resident in a memory of the mobile communication device . The native application is preferably downloaded from the APP STORE provide by Apple Computer or the ANDROID application website. Alternatively the client device is a laptop computer or a desktop computer and the application is a web application.

In practice end users owners of the client device upload a photo plus optional geolocation using the mobile application . The geolocation assist in identifying the plant or disease and assist in determining what advice to provide to the end user gardener.

First as shown in the end user opens the application on the mobile communication device and accesses a plant identifier page. The plant identifier page preferably provides two options take a new image or use an existing image from a camera roll in a memory of the mobile communication device . An application menu is also provided on each page for allowing the user to make immediate actions. The end user uses the take photo button to take a new image.

Alternatively as shown in the end user opens the application and accesses a pest identifier page for identifying a pest or a disease. The pest identifier page preferably provides two options take a new image or use an existing image from a camera roll in a memory of the mobile communication device . An application menu is also provided on each page for allowing the user to make immediate actions. The end user uses the take photo button to take a new image of a pest.

Once the image is attached to the page then optionally as shown in the end user adds any additional comments that may help in the identification of the plant or disease in the comment menu . A transmission button is provided for sending the message to the server over a network such as the Internet or a communications network.

As shown in the image message is then submitted to the server side . In a preferred current application the image message submission is sent over HTTP possibly HTTPS i.e. HTTP with SSL security layer as shown in . In an alternative embodiment the submission is sent as an Email. As shown a geo location latitude and longitude is included in the message transmission which provides location information to the server side .

Once received the message is preferably processed by a team of horticultural experts. The response is preferably delivered by Email. Alternatively the response is delivered as a smartphone notification i.e. iOS or Android notification.

The first message received by the end user from the server side iGarden is to inform the end user that the image message has been received as shown in .

The message also contains queue position information which informs the end user of their position in the queue. This provides the end user an idea of how long the end user has to wait before they receive a response from the experts on the server side . In the event that the response takes more than 24 hours a 2nd message is sent to let the end user know that the experts of the server side are still working on their request. The 2nd message shows their new position in the queue.

From within the application the end user sees a list of all their photo submissions answers and where the end user is in the queue for any unanswered questions.

Once an answer has been found a response message is sent to the end user. The response message has the following attributes as shown in .

The response message includes recommendations for other flowers that the end user may be interested in. For diseases and pests inquiries the response message recommends products that will help the diseased plant. In addition the response message includes a rating link to allow the end user to rate the native application on the iOS or Android stores.

In an alternative embodiment shown in the response message contains a link to link to a web site. As shown in the answer and product recommendation web page of the web site is tailored for the end user s question. The page is constructed so that the page is viewed from any mobile or desktop client device or from within the mobile application itself .

The link of the response message links the mobile device to the web site so that pertinent information about the end user such as their email home address credit card etc. is linked to their custom answer so an end user can quickly make a purchase. In other words the end user only has to provide their personal information to the server side once and an account is created for the end user based on their email and unique phone identifier telephone number MAC address UUID . The web page also contains a login button for the end user to access their account.

An account is also created for the end user from their email. The end user is able to set up a password for their account.

Once an image is received on the server side the image is stored on the server side in a database and is placed into the submitted by user folder as shown in .

Preferably then a non horticultural expert decides which folder to drop the image question into based on the type of image e.g. flower tree vegetable fruit house plant weed lawn pest disease and geolocation. The non expert moves the image from the submitted by user to the ready for review by . . . folder. In addition to moving the photos the non expert rejects any incoming image that does not meet minimum criteria i.e. geolocation information photo invalid blurry photo photo taken too far away photo taken too close etc according to a menu as shown in .

If the non expert makes a mistake in their assignment of the image photo to an expert the expert can reassign it to another expert or put it back into the general box.

As words are typed the system automatically suggests answers that have been given in the past. If a good match is found then the expert can select it and avoid having to type in the full answer from scratch.

The category is used to automatically suggest relevant products solutions for the given photo submission along with the expert s answer.

In addition to human experts answering questions the system of the server side searches for plant suggestions from a submitted mobile camera photo as shown in .

The uploaded photo is analyzed and a color and texture feature vector is created. This feature vector is then compared to a database of available plants. Close matches are stored and sent down to the end user s mobile device as shown in .

Once the end user clicks on a plant he can purchase it. Specifically one or more items can be added to a cart and then purchased together.

The answer response message is sent to the mobile native application on the mobile device of the end user . The answer message contains a link. The end user clicks on the link and a webpage is generated on a website for the end user. Additional product information that may be helpful to the end user is provided on the webpage.

The mobile communication devices utilized with the present invention preferably include mobile phones smartphones tablet computers PDAs and the like. Examples of smartphones and the device vendors include the IPHONE smartphone from Apple Inc. the DROID smartphone from Motorola Mobility Inc. GALAXY S smartphones from Samsung Electronics Co. Ltd. and many more. Examples of tablet computing devices include the IPAD tablet from Apple Inc. and the XOOM tablet from Motorola Mobility Inc.

A mobile communication service provider aka phone carrier of the customer such as VERIZON AT T SPRINT T MOBILE and the like mobile communication service providers provide the communication network for communication to the mobile communication device of the end user.

Wireless standards include 802.11a 802.11b 802.11g AX.25 3G CDPD CDMA GSM GPRS radio microwave laser Bluetooth 802.15 802.16 and IrDA.

Each of the interface descriptions preferably discloses use of at least one communication protocol to establish handshaking or bi directional communications. These protocols preferably include but are not limited to XML HTTP TCP IP Serial UDP FTP Web Services WAP SMTP SMPP DTS Stored Procedures Import Export Global Positioning Triangulation IM SMS MMS GPRS and Flash. The databases used with the system preferably include but are not limited to MSSQL Access MySQL Progress Oracle DB2 Open Source DBs and others. Operating system used with the system preferably include Microsoft 2010 XP Vista 200o Server 2003 Server 2008 Server Windows Mobile Linux Android Unix I series AS 400 and Apple OS.

The underlying protocol at a server is preferably Internet Protocol Suite Transfer Control Protocol Internet Protocol TCP IP and the transmission protocol to receive a file is preferably a file transfer protocol FTP Hypertext Transfer Protocol HTTP Secure Hypertext Transfer Protocol HTTPS or other similar protocols. The transmission protocol ranges from SIP to MGCP to FTP and beyond. The protocol at the server is preferably HTTPS.

As shown in a typical mobile communication device includes an accelerometer a headphone jack a microphone jack a speaker a GPS component a Bluetooth component a Wi Fi component a 3G 4G component a Baseband Processor for radio control an applications processor a JTAG debugger a SDRAM memory a Flash memory SIM card LCD display a camera component a power management circuit and a battery or power source .

From the foregoing it is believed that those skilled in the pertinent art will recognize the meritorious advancement of this invention and will readily understand that while the present invention has been described in association with a preferred embodiment thereof and other embodiments illustrated in the accompanying drawings numerous changes modification and substitutions of equivalents may be made therein without departing from the spirit and scope of this invention which is intended to be unlimited by the foregoing except as may appear in the following appended claim. Therefore the embodiments of the invention in which an exclusive property or privilege is claimed are defined in the following appended claims.

