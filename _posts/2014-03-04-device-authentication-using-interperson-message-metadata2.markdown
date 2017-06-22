---

title: Device authentication using inter-person message metadata
abstract: A device authentication server authenticates a remotely located device using unique data associated with the user of the device stored on a remotely located server that has an established relationship with the device, such as client logic installed on the device and authentication data of the user stored on the device. The unique data can be unique metadata associated with inter-person messages. Since each user receives and sends a unique collection of messages, the unique message meta-data associated with a user's account is, in aggregate, unique.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09578502&OS=09578502&RS=09578502
owner: Uniloc Luxembourg S.A.
number: 09578502
owner_city: Luxembourg
owner_country: LU
publication_date: 20140304
---
This application claims priority to U.S. Provisional Application 61 811 066 filed Apr. 11 2013 which is fully incorporated herein by reference.

The present invention relates generally to network based computer security and more particularly methods of and systems for authenticating a device for computer network security.

Device identification through digital fingerprints has proven to be invaluable in recent years to such technologies as security and digital rights management. In security authentication of a person can be restricted to a limited number of previously authorized devices that are recognized by their digital fingerprints. In digital rights management use of copyrighted or otherwise proprietary subject matter can be similarly restricted to a limited number of previously authorized devices that are recognized by their digital fingerprints.

Digital fingerprints are particularly useful in uniquely identifying computing devices that are historically know as IBM PC compatible . Such devices have an open architecture in which various computer components are easily interchangeable with compatible but different components. There are two primary effects of such an open architecture that facilitate device identification through digital fingerprints.

The first facilitating effect is diversity of device components. Since numerous components of IBM PC compatible devices are interchangeable with comparable but different components generation of a digital fingerprint from data associated with the respective components of the device are more likely to result in a unique digital fingerprint.

The second facilitating effect is discoverability of details of the various components of IBM PC compatible devices. Since the particular combination of components that make up a given device can vary widely and can come from different manufacturers the components and the operating system of the device cooperate to provide access to detailed information about the components. Such information can include serial numbers firmware version and revision numbers model numbers etc. This detailed information can be used to distinguish identical components from the same manufacturer and therefore improves uniqueness of digital fingerprints of such devices.

Laptop computing devices evolved from desktop computing devices such as IBM PC compatible devices and share much of the architecture of desktop computing devices albeit in shrunken form. Accordingly while users are much less likely to replace graphics circuitry in a laptop device and components therefore vary less in laptop devices laptop devices still provide enough detailed and unique information about the components of the laptop device to ensure uniqueness of digital fingerprints of laptop devices.

However the world of computing devices is rapidly changing. Smart phones that fit in one s pocket now include processing resources that were state of the art just a few years ago. In addition smart phones are growing wildly in popularity. Unlike tablet computing devices of a decade ago which were based on laptop device architectures tablet devices available today are essentially larger versions of smart phones.

Smart phones are much more homogeneous than older devices. To make smart phones so small the components of smart phones are much more integrated including more and more functions within each integrated circuit IC chip. For example while a desktop computing device can include graphics cards and networking cards that are separate from the CPU smart phones typically have integrated graphics and networking circuitry within the CPU. Furthermore while desktop and laptop devices typically include hard drives which are devices rich with unique and detailed information about themselves smart phones often include non volatile solid state memory such as flash memory integrated within the CPU or on the same circuit board as the CPU. Flash memory rarely includes information about the flash memory such as the manufacturer model number etc.

Since these components of smart phones are generally tightly integrated and not replaceable the amount and variety of unique data within a smart phone that can be used to generate a unique digital fingerprint is greatly reduced relative to older device architectures. In addition since it is not expected that smart phone components will ever be replaced there is less support for access to detailed information about the components of smart phones even if such information exists.

Accordingly it is much more difficult to assure that digital fingerprints of smart phones and similar portable personal computing devices such as tablet devices are unique. What is needed is a way to uniquely identify individual devices in large populations of homogeneous devices.

In accordance with the present invention a device authentication server authenticates a remotely located device using data uniquely associated with the user of the device stored on a remotely located server that has an established relationship with the device. The established relationship can be client logic installed on the device and authentication data of the user stored on the device. As such the remotely located device can be directed to access data associated with the user from the remotely located server without requiring intervention by the user.

For example the remotely located server can provide a social networking server in which inter person messages are associated with unique metadata to distinguish otherwise indistinguishable messages. Since each user receives and sends a unique collection of messages the unique message metadata associated with a user s account is in aggregate unique.

By combining unique data associated with the user with internal attributes of the remotely located device the device can be distinguished from similar devices when internal attributes alone are insufficient to uniquely identify the device.

For registration for subsequent authentication of the device the device provides the device authentication server with data representing a relatively complete set of message metadata sometimes referred to tag data that the device retrieves from the remotely located server. The device authentication server stores this data and uses it subsequently as reference message metadata.

In subsequent authentication of the device the device authentication server sends a device key challenge to the device. The device key challenge specifies a randomized selection of device attribute parts to be collected from the device and the manner in which the device attribute parts are to be combined to form a device key. The device key is data that identifies and authenticates the device and includes a device identifier and message metadata.

The device authentication server authenticates the device when the device identifier of the device key identifies the device and the message metadata is consistent with the reference message metadata.

In accordance with the present invention a device authentication server authenticates a computing device using unique data of the user of device that is stored by another server . In effect device authentication server leverages from an established relationship between device and server to more uniquely identify device . Server is a server that requires authentication by device authentication server as a precondition for receiving services from server .

The relationship between device and server that device authentication server leverages for better identification and authentication of device is embodied in a social networking application in this illustrative embodiment. Social networking application is a client application for a social networking service provided by server . Social networking application is configured by the user to supply authentication details to server automatically so that the user need not enter such details each time social networking application interacts with server .

In one illustrative example server implements the currently used social networking service called Twitter. A number of inter person messages referred to by Twitter as tweets appear in association with each user s account. An inter person message is a message composed by one person and intended to be received by one or more other persons. Since each message might not be unique among all messages processed by server each message is associated with an identifier that is unique among messages processed by server . Since each user receives and sends a unique collection of messages the unique message identifiers of messages associated with a user s account is in aggregate unique.

Currently Twitter s social networking service includes message metadata in web pages. Examples include data item id 276764531101929123 id stream item tweet 276674531101929473 data feedback key stream status 276764531102829473 and data tweet id 276764531198929473 . Herein items of message metadata are sometimes referred to as tags. 

Device authentication system includes device a server device authentication server and a service that are connected to one another through a wide area computer network which is the Internet in this illustrative embodiment. Device can be any of a number of types of networked computing devices including smart phones tablets netbook computers laptop computers and desktop computers. Server is a server that provides services to remotely located devices such as device but that is configured to require authentication of device prior to providing those services. Device authentication server is a server that authenticates devices sometimes on behalf of other computers such as server . Server provides a social networking service to other devices such as device for example.

Device attributes are described briefly to facilitate understanding and appreciation of the present invention. In this illustrative embodiment tags associated with the user of device are combined with other attributes of device to form a digital fingerprint of device . Such other attributes include hardware and system configuration attributes of device that make up an internal state of device . Known device record includes device attributes both of which are described in greater detail below. Each device attribute includes an identifier and a value . Other than tags examples of device attributes of device include a serial number of a storage device within device and detailed version information regarding an operating system executing within device . In the example of a serial number of a storage device identifier specifies the serial number of a given storage device such as C or dev sdal as the particular information to be stored as value and value stores the serial number of the given storage device of device .

In the example of tags value will be in the form of tag log that is described in greater detail below in the context of registration of device for subsequent authentication.

For subsequent authentication of device registration in the manner illustrated in transaction flow diagram retrieves tag data from device .

In step device sends a request for registration to device authentication server . The request can be in the form of a URL specified by the user of device using a web browser executing in device and conventional user interface techniques involving physical manipulation of user input devices . Web browser and user input devices and other components of device are described in greater detail below.

The request sent to device includes content that causes web browser of device to gather attribute data representing hardware and other configuration attributes of device . In one embodiment a web browser plug in is installed in device and invoked by web browser processes the content of the web page to gather the attribute data in step . In other embodiments the attribute data can be gathered in step by other forms of logic of device such as DDK generator installed in device . The various elements of device and their interaction are described more completely below.

The content that causes web browser of device to gather attribute data representing hardware and other configuration attributes of device includes extraction logic for each of the attributes web browser is to gather. In an alternative embodiment DDK generator already includes extraction logic for all attributes and device receives data identifying the particular attributes requested by device authentication server . Extraction logic defines the manner in which a client device is to extract data to be stored as value of device attribute .

Step for gathering attribute data regarding logged environmental data is shown in greater detail as logic flow diagram . In step device determines start and end times for tag data to be collected.

In step device extracts the tag data for the interval of time determined in step . Device extracts the tag data from server . In this illustrative embodiment device causes social networking application to retrieve all messages within the interval of time and associated with authentication data already provided to social networking application . In some embodiments web browser is configured to use previously stored authentication data to access the messages of the user of device from server and is used to retrieve the messages from server instead of social networking application .

Device parses message metadata from the retrieved messages to form tag log . Tag log is generally of the form of tag log . Tag log includes a number of tag records each representing a tag parsed from messages retrieved by social network application . The particular tag represented by tag record is sometimes referred to as the subject tag in the context of .

Tag represents the subject tag itself. For example if tag record represents message metadata of data item id 276764531101929123 tag includes data specifying that the subject tag is 276764531101929123 or in some embodiments data item id 276764531101929123 .

Context specifies a context in which the subject tag appears in the message from which it was parsed. The context is any characteristic of a message or data in which the subject tag is found and that can be used to improve the uniqueness of the subject tag. For example context can specify the length of the message from which the subject tag is parsed and or the relative position of the subject tag within the message.

Time stamp specifies the date and time of the message from which the subject tag is parse. The start and end times determined by device in step specify which of tag records are to be collected from messages. In one embodiment device determines that the start time is the very first available tag record and that the end time is the current time retrieving the entirety of all tags. In other embodiments device can determine that the start and end times represent a more limited amount of time such as the first month of tag data available or the most recent week as examples.

In step device forms a device identifier from the extracted device attributes including the tag data. The device identifier can be a hash of all or selected parts of collected device attributed data for example. After step processing according to logic flow diagram and therefore step completes.

In this illustrative embodiment device in particular web browser plug in or DDK generator encrypts the attribute data using a public key of device authentication server and public key infrastructure PKI thereby encrypting the attribute data such that it can only be decrypted by device authentication server .

In step device authentication logic of device authentication server creates a device registration record for device from the received attribute data. Device authentication server creates a device registration record in the form of known device record for device by creating a globally unique identifier for device or using the identifier formed by device in step as device identifier and storing the values of the respective attributes including the tag data received in step as value in respective device attributes . Known device record is described more completely below in greater detail.

In step device authentication server sends a report of successful registration to device providing device identifier of device for subsequent identification particularly if it differs from the one generated by device . After step processing according to transaction flow diagram completes and device is registered for subsequent authentication with device authentication server .

Known device record is a registration record and in this illustrative example represents registration of device . Known device record includes a device identifier and a number of device attributes which are described briefly above. Each device attribute includes an identifier specifying a particular type of information and a value representing the particular value of that type of information from device . For example if identifier specifies a serial number of a given storage device value stores the serial number of that storage device within device . Similarly if identifier specifies tags stored by device value stores data representing the tags themselves.

In this illustrative embodiment value stores the tag data in the form of tag log . In alternative embodiments value can store an abstraction of the tag data. For example value can store a hash of the tag data e.g. a hash of all tags concatenated to one another in chronological order.

Device attribute also includes extraction logic comparison logic alert logic and adjustment logic . The particular device attribute represented by device attribute is sometimes referred to as the subject device attribute in the context of .

Extraction logic specifies the manner in which the subject device attribute is extracted by device . Logic flow diagram described above is an example of extraction logic for tag data.

Comparison logic specifies the manner in which the subject device attribute is compared to a corresponding device attribute to determine whether device attributes match one another. For example if tag data is gathered with a specific time range the comparison can be equivalence of the tag data received for authentication with that stored in value for the specific time range. If the tag data is gathered in its entirety and represented as a cumulative collection of tags the tag data received for authentication should represent more tags than that stored in value by an amount roughly predicted by the rate of accumulation of tags over time.

Alert logic can specify alerts of device matches or mismatches or other events. Examples of alert logic include e mail SMS messages and such to the owner of device and or to a system administrator responsible for proper functioning of device .

Adjustment logic specifies the manner in which the subject device attribute is to be adjusted after authentication. For example if the tag data received for authentication includes tag data that is not already stored in value adjustment logic can cause value to be updated to include the additional tag data. Similarly if the tag data received for authentication is a cumulative representation of the tag data adjustment logic can cause value to be updated to include the newly received cumulative representation.

Device attribute is shown to include the elements previously described for ease of description and illustration. However it should be appreciated that a device attribute for a given device can include only identifier and value while a separate device attribute specification can include extraction logic comparison logic alert logic and adjustment logic . In addition all or part of extraction logic comparison logic alert logic and adjustment logic can be common to attributes of a given type and can therefore be defined for the given type.

Transaction flow diagram illustrates the use of device authentication server to authenticate device with server .

In step device sends a request for a log in web page to server by which the user can authenticate herself. The request can be in the form of a URL specified by the user of device using web browser and conventional user interface techniques involving physical manipulation of user input devices .

In step server sends the web page that is identified by the request received in step . In this illustrative example the web page sent to device includes content that defines a user interface by which the user of device can enter her authentication credentials such as a user name and associated password for example.

In step web browser of device executes the user interface and the user of device enters her authentication credentials e.g. by conventional user interface techniques involving physical manipulation of user input devices . While the user is described as authenticating herself in this illustrative example it should be appreciated that device can be authenticated without also requiring that the user of device is authenticated.

In step device sends the entered authentication credentials to server . In this illustrative embodiment device also sends an identifier of itself along with the authentication credentials. Server authenticates the authentication credentials in step e.g. by comparison to previously registered credentials of known users. If the credentials are not authenticated processing according to transaction flow diagram terminates and the user of device is denied access to services provided by server . Conversely if server determines that the received credentials are authentic processing according to transaction flow diagram continues.

In step server sends a request to device authentication server for a session key using the device identifier received with the authentication credentials.

In response to the request device authentication server generates and cryptographically signs a session key. Session keys and their generation are known and are not described herein. In addition device authentication server creates a device key challenge and encrypts the device key challenge using a public key of device and PKI.

To create the device key challenge device authentication server retrieves the known device record representing device using the received device identifier and comparing it to device identifier . The device key challenge specifies all or part of one or more of device attribute to be included in the device key and is described in greater detail below.

In step device authentication server sends the signed session key and the encrypted device key challenge to server .

In step server sends a device authenticating page to device along with the device key challenge. The device authenticating page includes content that provides a message to the user of device that authentication of device is underway and content that causes device to produce a dynamic device key in the manner specified by the device key challenge.

The device key challenge causes web browser of device to generate a device identifier sometimes referred to herein as a dynamic device key DDK for device e.g. dynamic device key . In one embodiment a web browser plug in is installed in client device and invoked by web browser processes the content of the web page to generate the DDK. In other embodiments DDK of device can be generated by other forms of logic of device such as DDK generator which is a software application installed in device .

The device key challenge specifies the manner in which DDK is to be generated from the attributes of device represented in device attributes . The challenge specifies a randomized sampling of attributes of device allowing the resulting DDK to change each time device is authenticated. There are a few advantages to having DDK represent different samplings of the attributes of device . One is that any data captured in a prior authentication of device cannot be used to spoof authentication of device using a different device when the challenge has changed. Another is that since only a small portion of the attributes of device are used for authentication at any time the full set of attributes of device cannot be determined from one a few several or even many authentications of device .

The device key challenge specifies items of information to be collected from hardware and system configuration attributes of device and the manner in which those items of information are to be combined to form DDK . In this embodiment the challenge specifies one or more attributes related to tag data associated with device within server e.g. cached as tag log or retrieved anew from server .

The device key challenge can specify multiple parts of a device attribute to include in the device key. For example the device key challenge can specify that the tags associated with device associated with the month of February and the first quarter of the year including February twice are to be collected from tag log or server and included in the device key.

To provide greater security DDK includes data representing the tag data obfuscated using a nonce included in the challenge. While use of randomized parts of the tag data precludes capture of any single DDK to be used in subsequent authentication use of the nonce thwarts collection of randomized parts of the tag data over time to recreate enough of tag log to spoof authentication in response to a given challenge.

In step device gathers tag data for inclusion in the DDK according to the device key challenge. Step is shown in greater detail as logic flow diagram .

In step device determines start and end times for tag data to be collected. The start and end times are specified in the device key challenge and the device key challenge can include multiple start end time pairs.

In step device extracts the tag data for the one or more intervals of time determined in step . Device can extract the tag data from server in the manner described above or alternatively can extract the tag data cached in tag log .

In step device packages the extracted tag data in the manner specified in the device key challenge. As noted above the device key challenge can specify that the an abstraction of the extracted tag data such as a hash of the extracted tag data for example. After step processing according to logic flow diagram and therefore step completes.

Once DDK is generated according to the received device key challenge device encrypts DDK using a public key of device authentication server and PKI.

In step device sends the encrypted dynamic device key to server and server sends the encrypted dynamic device key to device authentication server in step .

In step device authentication logic of device authentication server decrypts and authenticates the received DDK. Step is shown in greater detail as logic flow diagram .

In step device authentication logic identifies device . In this illustrative embodiment the received DDK includes a device identifier corresponding to device identifier . Device authentication logic identifies device by locating a known device record in which device identifier matches the device identifier of the received DDK.

In test step device authentication logic determines whether device is identified. In particular device authentication logic determines whether a known device record with a device identifier matching the device identifier of the received DDK is successfully found in known device data . If so processing transfers to step . Otherwise processing transfers to step which is described below.

In step device authentication logic retrieves the known device record for the identified device e.g. device using the identifier determined in step .

In step device authentication logic authenticates the received DDK using the retrieved device record . Device authentication logic authenticates by applying the same device key challenge sent in step to the known device record that corresponds to the identified device. In this illustrative embodiment the device key challenge produces a DDK in which a portion of the DDK generated from non interactive attributes can be parsed from a portion generated from interactive attributes such that device can be authenticated separately from the user of device .

In test step device authentication logic determines whether the received DDK authenticates device by comparing the resulting DDK of step to the received DDK. In this illustrative embodiment device authentication logic uses comparison logic for each of the device attributes included in the device key challenge.

If the received DDK does not authenticate device processing transfers to step and authentication fails or alternatively to step in which device authentication logic sends another device key challenge to re attempt authentication. If the received DDK authenticates device processing transfers to step .

In step device authentication logic applies adjustment logic of each of device attributes uses to generate the received DDK. For example adjustment logic can specify that if the received DDK includes tag data not already included in value device authentication logic incorporates the new tag data into value . After step processing according to logic flow diagram and therefore step completes. As described above authentication failure at either of test steps and transfers processing to step .

In step device authentication logic determines that device is not authentic i.e. that authentication according to logic flow diagram fails.

In step device authentication logic logs the failed authentication and in step applies alert logic to notify various entities of the failed authentication. After step processing according to logic flow diagram and therefore step completes.

In step device authentication server sends data representing the result of authentication of device to server .

In step server determines whether to continue to interact with device and in what manner according to the device authentication results received in step .

Server computer is shown in greater detail in . Server includes one or more microprocessors collectively referred to as CPU that retrieve data and or instructions from memory and execute retrieved instructions in a conventional manner. Memory can include generally any computer readable medium including for example persistent memory such as magnetic and or optical disks ROM and PROM and volatile memory such as RAM.

CPU and memory are connected to one another through a conventional interconnect which is a bus in this illustrative embodiment and which connects CPU and memory to network access circuitry . Network access circuitry sends and receives data through computer networks such as wide area network .

A number of components of server are stored in memory . In particular web server logic and web application logic including authentication logic are all or part of one or more computer processes executing within CPU from memory in this illustrative embodiment but can also be implemented using digital logic circuitry.

Web server logic is a conventional web server. Web application logic is content that defines one or more pages of a web site and is served by web server logic to client devices such as device . Authentication logic is a part of web application logic that carries out device authentication in the manner described above.

Device authentication server is shown in greater detail in . Device authentication server includes one or more microprocessors collectively referred to as CPU memory a conventional interconnect and network access circuitry which are directly analogous to CPU memory conventional interconnect and network access circuitry respectively.

A number of components of device authentication server are stored in memory . In particular device authentication logic is all or part of one or more computer processes executing within CPU from memory in this illustrative embodiment but can also be implemented using digital logic circuitry. Known device data is data stored persistently in memory and includes known device records such as known device record for all devices that can be authenticated by device authentication logic . In this illustrative embodiment known device data is organized as all or part of one or more databases.

Device is a personal computing device and is shown in greater detail in . Device includes one or more microprocessors collectively referred to as CPU that retrieve data and or instructions from memory and execute retrieved instructions in a conventional manner. Memory can include generally any computer readable medium including for example persistent memory such as magnetic and or optical disks ROM and PROM and volatile memory such as RAM.

CPU and memory are connected to one another through a conventional interconnect which is a bus in this illustrative embodiment and which connects CPU and memory to one or more input devices output devices and network access circuitry . Input devices can include for example a keyboard a keypad a touch sensitive screen a mouse a microphone and one or more cameras. Input devices detect physical manipulation by a human user and in response to such physical manipulation generates signals representative of the physical manipulation and sends the signals to CPU . Output devices can include for example a display such as a liquid crystal display LCD and one or more loudspeakers. Network access circuitry sends and receives data through computer networks such as wide area network .

A number of components of device are stored in memory . In particular web browser operating system DDK generator and social networking application are each all or part of one or more computer processes executing within CPU from memory in this illustrative embodiment but can also be implemented using digital logic circuitry. As used herein logic refers to i logic implemented as computer instructions and or data within one or more computer processes and or ii logic implemented in electronic circuitry.

Web browser plug ins are each all or part of one or more computer processes that cooperate with web browser to augment the behavior of web browser . The manner in which behavior of a web browser is augmented by web browser plug ins is conventional and known and is not described herein.

Operating system is a set of programs that manage computer hardware resources and provide common services for application software such as web browser web browser plug ins and DDK generator .

Social networking application is a client application for a network implemented social networking service.

Tag log is data stored persistently in memory and each can be organized as all or part of one or more databases. Tag log is generally of the structure of tag log .

The above description is illustrative only and is not limiting. The present invention is defined solely by the claims which follow and their full range of equivalents. It is intended that the following appended claims be interpreted as including all such alterations modifications permutations and substitute equivalents as fall within the true spirit and scope of the present invention.

