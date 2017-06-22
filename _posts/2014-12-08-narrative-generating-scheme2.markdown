---

title: Narrative generating scheme
abstract: In one example embodiment, A narrative method includes registering an application, from among a plurality of applications installed on a mobile device; identifying at least one action corresponding to the application; receiving recorded usage history of the at least one action corresponding to the application; and generating a narrative based on the received usage history of the at least one action corresponding to the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09639525&OS=09639525&RS=09639525
owner: KT CORPORATION
number: 09639525
owner_city: Seongnam-si, Gyeonggi-Do
owner_country: KR
publication_date: 20141208
---
A life log enables a user using digital devices to record data pertaining to myriad life experiences via text messages pictures video files and audio files. Alternatively users may record their experiences through social network services.

In one example embodiment a narrative method may include registering an application from among a plurality of applications installed on a mobile device identifying at least one action corresponding to the application receiving recorded usage history of the at least one action corresponding to the application and generating a narrative based on the received usage history of the at least one action corresponding to the application.

In another example embodiment a computing device may include a memory configured to store narratives and a processing unit configured to register an application from among a plurality of applications installed on a mobile device identify at least one action corresponding to the application receive recorded usage history of the at least one action corresponding to the application and generate a narrative based on the received usage history of the at least one action corresponding to the application.

In yet another example embodiment a computer readable storage medium having thereon computer executable instructions that in response to execution cause a device to perform operations may include registering an application from among a plurality of applications installed on a mobile device identifying at least one action corresponding to the application receiving recorded usage history of the at least one action corresponding to the application and generating a narrative based on the received usage history of the at least one action corresponding to the application.

The foregoing summary is illustrative only and is not intended to be in any way limiting. In addition to the illustrative aspects embodiments and features described above further aspects embodiments and features will become apparent by reference to the drawings and the following detailed description.

In the following detailed description reference is made to the accompanying drawings which form a part of the description. In the drawings similar symbols typically identify similar components unless context dictates otherwise. Furthermore unless otherwise noted the description of each successive drawing may reference features from one or more of the previous drawings to provide clearer context and a more substantive explanation of the current example embodiment. Still the example embodiments described in the detailed description drawings and claims are not meant to be limiting. Other embodiments may be utilized and other changes may be made without departing from the spirit or scope of the subject matter presented herein. It will be readily understood that the aspects of the present disclosure as generally described herein and illustrated in the drawings may be arranged substituted combined separated and designed in a wide variety of different configurations all of which are explicitly contemplated herein.

Network may be a wired or wireless information or telecommunications network. Non limiting examples of network may include a wired network such as a LAN Local Area Network a WAN Wide Area Network a VAN Value Added Network or the like. Other non limiting examples of network may include wireless networks such as a mobile radio communication network including at least one of a 3rd 4th or 5th generation mobile telecommunications network 3G 4G or 5G various other mobile telecommunications networks a cabling telecommunications network a fiber optics telecommunications network a satellite network WiBro Wireless Broadband Internet Mobile WiMAX Worldwide Interoperability for Microwave Access HSDPA High Speed Downlink Packet Access or the like.

Computing device may include for example but not as a limitation an IPTV Internet Protocol Television a Smart TV Smart TV a Connected TV a notebook computer a personal computer a smart phone a digital camera a remote controller a tablet computer a phablet device or a personal communication terminal such as PCS Personal Communication System GMS Global System for Mobile communications PDC Personal Digital Cellular PDA Personal Digital Assistant IMT International Mobile Telecommunication 2000 CDMA Code Division Multiple Access 2000 W CDMA W Code Division Multiple Access and Wibro Wireless Broadband Internet terminal.

As referenced herein a narrative application which may alternatively be referred to as a storytelling application may be regarded as a mobile application installed on computing device to generate story contents based on recorded history of actions.

External server may be configured to receive from computing device a request for data and to provide the requested data to computing device . External server may include one or more servers. The requested data which may be alternatively referred to as external data because it may be retrieved and or received from external sources may be related to a plurality of mobile applications installed and or running on computing device .

For example if a narrative application installed on computing device receives transmits includes or otherwise makes reference to an electronic book e.g. E book the requested or external data may include as non limiting examples a cover of the E book information regarding an author of the E book on line ratings of the E book or links thereto users reviews of the E book information regarding sales of the E book etc stored in external server that a non stand alone mobile application selling the E book may access through application programming interfaces APIs . External server may be configured to retrieve and or receive the requested or external data from one or more local servers or from associated with other entities and to transmit the requested or external data to the requesting computing device .

As another example if the narrative application receives transmits includes or otherwise makes reference to movie the requested or external data may include as non limiting examples a promotional poster or other graphics for the movie information regarding the director of the movie information regarding actors in the movie on line ratings of the movie or links thereto audience reviews of the movie etc stored in external server that a non stand alone mobile application for booking the movie ticket may access through application programming interfaces APIs . External server may be configured to retrieve and or receive the requested or external data from one or more local servers or from associated with other entities and to transmit the requested or external data to the requesting computing device .

Computing device may be operable to download a narrative or storytelling application hereinafter referred to as narrative application to generate a user s narrative or story from application distribution platforms such as the Apple App Store Google Play Windows Phone Store and BlackBerry App World. The narrative application may be a computer program designed to run on any implementation of computing device .

The narrative application downloaded and hosted on computing device may register a third party mobile application hereinafter referred to as the third party application which may be one of a plurality of mobile applications that are also downloaded from one or more of the application distribution platforms and installed on computing device .

According to some embodiments for example a user of computing device may drag an icon or representation of the third party application onto an icon or representation of the narrative application on a user interface UI of computing device . Then the narrative application may receive a third party application ID from an OS running on computing device and store the third party application ID. Further the narrative application may call an API function provided by the third party application to get recorded data regarding the third party application from external server or computing device .

Examples of the third party mobile applications that may be registered to the narrative application may include the Amazon Kindle Store application that facilitates purchases and downloads of E books the Yahoo music application that facilitates purchases and downloads of music the AMC grand application that facilitates ticket purchases for movies the TNT application that provides e.g. viewing guides for the corresponding TV channel the BluePay application that facilitates mobile payments payment or the Angry Bird game application.

The registered narrative application may be configured to identify one or more user actions that may be taken while using the registered narrative application. Such actions may be predefined by the narrative application and stored in computing device . Further the actions may be a user defined action implemented by computing device .

As an example of identifying at least one action the registered narrative application may display the predefined list of actions in a drop down menu of a pop up window corresponding to the registered application. Then the narrative application may receive one or more user inputs to select at least one action from the predefined list of actions in the drop down menu e.g. by clicking selections of the one or more actions.

As non limiting example of the actions list if the narrative application registers Amazon Kindle Store the narrative application may display in e.g. a pop up window or drop down menu a predefined list of actions including as non limiting examples read hold like dislike purchase read again highlight annotate preview etc. using a UI on computing device or the narrative application server.

As another example if the narrative application registers Yahoo Music as a mobile music store application the narrative application may display in e.g. a pop up window or drop down menu actions that include as non limiting examples listen hold purchase download like dislike rate add to favorites remove from favorites read a review comment etc.

As another example of identifying at least one action the narrative application may identify a category of the registered application and display a predefined list of actions stored in computing device corresponding to the category of the application. Then the narrative application may receive one or more user inputs to select at least one action from the list of actions.

For example if the narrative application registers Amazon Kindle Store and Google eBook the narrative application may determine based on metadata of the two applications that Amazon Kindle Store and Google eBook are both E book store applications. Then the narrative application may display the same predefined list of actions corresponding to all registered E book store application.

As still another example of identifying at least one action the narrative application may receive user defined actions corresponding to the registered application. After the narrative application displays a list of actions predefined and stored in computing device corresponding to the registered application the narrative application may receive one or more user inputs to enter new actions associated with the registered third party application.

After the narrative application identifies at least one action the narrative application may be configured to receive recorded usage history of the at least one action corresponding to the registered third party application transmitted from external server and computing device .

The recorded usage history of the at least one action corresponding to the registered application may include an executed function an execution time an execution location of the at least one application along with a title a starting time and a location transmitted from external server . Further the recorded usage history of the at least one action corresponding to the application may include an image a rating an author an actor actress and a review associated with the application.

The information regarding the executed function the execution time and the execution location may be stored in computing device and the narrative application may receive such information transmitted from computing device by calling application programming interfaces APIs because the usage record of applications installed on computing device may be stored in computing device .

On the contrary the information regarding the title the starting time and the location may be stored in external server linked to the registered application and the narrative application may receive such information transmitted from external server by calling application programming interfaces APIs . The information regarding a subject matter of the registered application e.g. e Book of Amazon Kindle Store or a movie ticket of AMC grand may be stored in external server linked to the registered application.

For example if a narrative application registers the AMC grand application and the narrative application receives at least one user input to select watch a movie from a list of actions the narrative application may receive one or more UI fields or windows to facilitate a book a ticket function an indication of 14 00 or 2 00 p.m. as a starting time for execution of the function 00 05 as a duration of execution of the function home as a location of execution of the function etc. Such information regarding execution of the function may be stored in computing device and be transmitted to the narrative application that may utilize such information to write a story when a user utilizes the AMC grand application for booking a movie ticket.

In addition in order to include more specific story of the user s life the narrative application may receive from external server Dark Knight as a movie title 16 00 or 4 00 p.m. as a starting time for the movie Beverly Center as the location of a desired movie theater etc. Further the narrative application requests background information regarding the Dark Knight from external server associated with the AMC grand application to generate a more specific and or interesting story for the user. Thus the narrative application may retrieve and or receive from external server promotional images and or videos for the Dark Knight information regarding the director reviews of the Dark Knight information regarding actors in the Dark Knight etc. which may be stored in external server associated with the AMC grand application.

After the narrative application receives a history of the action. The history may include information such as an executed function an execution time an execution location etc. the narrative application may generate a narrative to be viewed on a user interface of the computing device based on the received usage history of the action corresponding to the registered application. For example after a user has booked a ticket for Dark Knight using the AMC grand application which has been registered by the narrative application and the user further selects the action watch movie using the AMC grand application the narrative application may generate a narrative to record such actions in one or more of various narrative formats.

As depicted in the narrative application may display a narrative In Beverly Hills I dropped by the Dunkin Donuts at 3 00 p.m. After that I watched Dark Knight at 4 00 p.m. at the AMC Grand Theater. It was so exciting as people said based on the predefined expression stored in computing device such as It was so exciting as people said. 

Further when the narrative application requests background information regarding the Dark Knight to external server associated with the AMC grand application to generate a more interesting and or specific story for the user the narrative application may retrieve and or receive from external server promotional images and or videos for the Dark Knight information regarding the director reviews of the Dark Knight information regarding actors in the Dark Knight etc. which may be stored in external server associated with the AMC grand application.

After the narrative application generates the narrative the narrative application may be configured to display at least part of the generated narrative and highlight at least one of the actions in the displayed narrative. The highlighting may include underlining and or coloring. Then the narrative application may receive an input to revise the highlighted action or to add new information to the highlighted action e.g. one or more user inputs to selection another action in the pop up menu or drop down menu on which a list of actions may be displayed or user input to type other action in an appropriate UI field or window.

For example based on the generated narrative I watched the Dark Knight at 4 00 p.m. at the AMC Grand Theater. It was so exciting as said the reviews stated. If the narrative application receives one or more user inputs to select watched and also to select give a present in a pop up menu or a drop down menu the narrative application may display alternatively or additionally a revised narrative that indicates as a non limiting example I gave my friend a ticket to watch the Dark Knight. He should like it since the reviews have been good. 

Further after the narrative application generates the narrative the narrative application may be configured to insert to the narrative at least one picture taken when receiving the recorded usage history of the actions corresponding to the application. In addition the narrative application may transmit the generated narrative to external server to be shared through the Internet.

Thus shows example system in which one or more embodiments of a narrative generating scheme may be implemented in accordance with various embodiments described herein.

Processing unit may include a registering component configured to register an application from among a plurality of applications installed on a mobile device an identifier configured to identify at least one action corresponding to the application a receiver configured to receive recorded usage history of the at least one action corresponding to the application a narrative generator configured to generate a narrative based on the received usage history of the at least one action corresponding to the application and an analyzer configured to collect and analyze external data transmitted from an external server.

Processing unit may further include a display configured to display at least part of the generated narrative a highlighter configured to highlight the at least one action in the displayed narrative an input receiver configured to receive an input to revise the at least one action or to add new information to the at least one action an attachment component configured to attach to the narrative at least one file e.g. picture video file audio file and a transmitter configured to transmit the narrative to an external server.

In some embodiments if a narrative application generates a plurality of narratives then memory may be configured to store the plurality of narratives. Further processing unit may be configured to read the narrative application s instructions received from a user s inputs e.g. mouse click touch input stylus input voice command gesture command etc.

In accordance with the narrative application s instruction registering component may be configured to register one of the third party applications including the Amazon Kindle Store application that facilitates purchases and downloads of E books the Yahoo music application that facilitates purchases and downloads of music the AMC grand application that facilitates ticket purchases for movies the TNT application that provides e.g. viewing guides for the corresponding TV channel the BluePay application that facilitates mobile payments payment or the Angry Bird game application etc.

Identifier may be configured to identify one or more user actions that may be taken while using the registered narrative application. Such actions may be predefined by the narrative application and stored in computing device . As an example of identifying user actions display may display the predefined list of actions in a drop down menu of a pop up window corresponding to the registered application.

Then input receiver may receive one or more user inputs to select at least one action from the predefined list of actions in the drop down menu e.g. by clicking selections of the one or more actions. Based on the one or more user inputs identifier may identify the one or more actions that may be taken while using the registered narrative application.

Receiver may be configured to receive recorded usage history of at least one action of the actions corresponding to the registered third party application transmitted from external server and computing device . The recorded usage history of the at least one action corresponding to the registered application may include an executed function an execution time an execution location of the at least one application along with a title a starting time and a location transmitted from external server .

Further the recorded usage history of the at least one action corresponding to the application may include an image a rating an author an actor actress and a review associated with the application. In addition to the received usage history of the action analyzer may be configured to collect and analyze external data including the image the rating the author the actor actress and the review associated with the application transmitted from an external server that are associated with the recorded usage history.

For example if registering component registers Amazon Kindle Store E book application and identifier identifies read as an action receiver may receive interest as executed function 14 10 as starting time for execution 00 01 as execution duration home as execution location.

In addition receiver may receive from external server Life Lesson as book title that may be included in the received usage history. In addition to the recorded usage history analyzer may collect and analyze as external data images of Life Lesson the author s information review about Life Lesson and other people s rating of Life Lesson transmitted from external server .

Narrative generator may be configured to generate a narrative to be viewed on a user interface of the computing device based on the received usage history of the action corresponding to the registered application. For example after a user has read The Great Gatsby and the user has further selected the action read both using the Yahoo books application registering component may register the Yahoo books application. Then registering component may receive the Yahoo books application ID from an OS running on computing device and store the Yahoo books application ID. Further registering component may call an API function provided by the Yahoo books application to get recorded data regarding the Yahoo books application from external server or computing device . Then identifier may identify read as a selected action for the Yahoo books application. Then narrative generator may generate the first narrative to record such actions in one or more of various narrative formats.

That is display may display I read The Great Gatsby starting at 14 00 for 30 minutes. I eventually finished reading it after starting it six months ago. I do not like this book despite the high rating because it is so boring to read. Receiver may also receive from external server images of The Great Gatsby information regarding the author F. Scott Fitzgerald ratings from the registered application etc.

As another example after a user has booked a ticket for the Dark Knight using the AMC grand application which has been registered by the narrative application and the user further selects the action watch movie using the AMC grand application narrative generator may generate the second narrative to record such actions in one or more of various narrative formats.

Display may display a narrative In Beverly Hills I dropped by the Dunkin Donuts at 3 00 p.m. After that I watched Dark Knight at 4 00 p.m. at the AMC Grand Theater. It was so exciting as people said based on the predefined expression stored in computing device such as It was so exciting as people said. 

Narrative generator may be configured to generate the first and the second narratives based on execution count of the corresponding applications. The execution count may indicate how many times the corresponding applications have been used during a certain period of time. For example if the Yahoo books application has been executed three times in a week while the AMC grand application has been executed once a month display may display on a user interface of computing device the first narrative generated based on Yahoo books before the second narrative generated based on AMC grand.

As another example of identifying at least one action identifier may identify a category of the registered application and display a predefined list of actions stored in computing device corresponding to the category of the application. Then input receiver may receive one or more user inputs to select at least one action from the list of actions.

For example if registering component registers Amazon Kindle Store and Google eBook identifier may determine based on metadata of the two applications that Amazon Kindle Store and Google eBook are both E book store applications. Then display may display the same predefined list of actions corresponding to all registered E book store application.

Processing unit may be configured to revise the generated narrative or add new information to the generated narrative. Display may display at least part of the generated narrative and highlighter may highlight at least one action in the displayed narrative. The highlighting may include underlining and or coloring.

Input receiver may receive an input to revise the highlighted action or to add new information to the highlighted action e.g. one or more user inputs to selection another action in the pop up menu or drop down menu on which a list of actions may be displayed or user input to type other action in an appropriate UI field or window.

For example based on the generated narrative I watched Dark Knight at 4 00 p.m. at the AMC Grand Theater. It was so exciting as people said. if the narrative application receives one or more user inputs to select watched and also to select give a present in a pop up menu or a drop down menu the narrative application may display alternatively or additionally a revised narrative that indicates as a non limiting example I gave a my friend a ticket to watch the Dark Knight. He should like it since the reviews have been good. 

Further attachment component may attach to the narrative at least one file e.g. picture video file audio file such as Dark Knight Poster spoiler or advertisement video clip of Dark Knight. In addition transmitter may transmit the narrative to an external server to be shared with other people through Internet.

Thus shows example device by which one or more embodiments of a narrative generating scheme may be implemented in accordance with various embodiments described herein.

Action may include user defined actions and a user may attach additional actions to action or delete one or more of actions included in action . For example actions READ HOLD RATE WATCH LISTEN DOWNLOAD PLAY BUY and GIVE A PRESENT TO may respectively match with action ID 1 to 10.

Thus shows an example table implemented by at least portions of a narrative generating scheme in accordance with various embodiments described herein.

Thus shows another example table implemented by at least portions of a narrative generating scheme in accordance with various embodiments described herein.

As depicted in application category determined based on the analysis may be stored in application information table with matched application ID and application title . For example if application ID 1 matches with application title Amazon Kindle Store table may store 1 in application category representing E books together with the corresponding application ID and application title.

If application ID 2 matches with application title Yahoo music table may store 4 in application category representing music together with the corresponding application ID and application title .

If application ID 3 matches with application title AMC grand table may store application category 2 representing movies together with the corresponding application ID and application title .

If application ID 4 matches with application title TNT table may store application category 3 representing TV together with the corresponding application ID and application title .

If application ID 5 matches with application title BluePay table may store application category 6 representing payment together with the corresponding application ID and application title .

If application ID 6 matches with application title Angry Bird table may store application category 5 representing game together with the corresponding application ID and application title .

Thus shows another example table implemented by at least portions of a narrative generating scheme in accordance with various embodiments described herein.

The recorded usage history may include application ID application category executed function execution time execution duration and execution location . Also the recorded usage history may include a title a starting time and a location transmitted from external server .

For instance processing unit may receive from AMC grand application application ID 3 AMC grand application category 2 movies execution function book a ticket . Then processing unit may receive that execution time of AMC grand corresponds to 14 00 that execution duration corresponds to 00 05 and that execution location corresponds to home.

When AMC grand may request further information to external server processing unit may further receive external data such as title Dark Knight starting time 16 00 movie time and location Beverly Center . Such external data may be received by calling API provided by AMC grand application developer or by requesting a server managed by AMC grand developer.

For other example processing unit may receive from Amazon Kindle Store application application ID 1 Amazon Kindle Store application category 1 E book execution function interest favorite . Then processing unit may receive that execution time of Amazon Kindle Store is 14 10 that execution duration is 00 01 and that execution location is home. In case that Amazon Kindle Store communicates with external server processing unit may further receive external data such as title Life Lesson .

For instance processing unit may receive from Amazon Kindle Store application application ID 1 Amazon Kindle Store application category 1 E book execution function read . Then processing unit may receive that execution time of Amazon Kindle Store is 14 10 that execution duration is 00 30 and that execution location is home. In case that Amazon Kindle Store communicates with external server processing unit may further receive external data such as title The Great Gatsby .

Thus shows another example table implemented by at least portions of a narrative generating scheme in accordance with various embodiments described herein.

For example processing unit may generate the first narrative associated with application ID 1 Amazon Kindle Store. After processing unit registers Amazon Kindle Store and receives a user input of hold and executed function interest in a book titled Life Lesson processing unit may generate the first narrative including an expression of hold combined with Life Lesson .

For example processing unit may generate the first narrative of I am interested in Life Lesson. Please place this on hold. In addition processing unit may display a book cover for Life Lesson information regarding the book s author and the rating transmitted from external server .

For another example processing unit may generate the second narrative associated with application ID 2 Amazon Kindle Store . After processing unit registers Amazon Kindle Store and receives a user input of read and executed function read in a book titled The Great Gatsby processing unit may generate the second narrative including an expression of read combined with The Great Gatsby. 

That is processing unit may generate the second narrative of I had read The Great Gatsby at 14 00 for 30 minutes. I eventually finished reading it since I started reading it six months ago. I do not like this book because it is so boring based on the predefined expression stored in computing device such as I do not like this book because it is so boring. 

As yet another example processing unit may generate the third narrative associated with application ID 3 AMC grand . After processing unit registers AMC grand and receives a user input of watch and execution function watch for the movie Dark Knight processing unit may generate the third narrative including an expression of watch combined with Dark Knight. 

That is processing unit may generate the third narrative of In Beverly Hills I dropped by Dunkin Donuts at 15 00. I watched Dark Knight at 16 00 in the AMC grand. It was so exciting as people said based on the predefined expression stored in computing device such as It was so exciting as people said. 

Thus shows an illustrative user interface by which one or more embodiments of a narrative generating scheme may be implemented in accordance with various embodiments described herein.

As depicted in the action watch may be underlined or colored as a means of highlighting. With regard to the highlighted action processing unit may receive a user input to replace watch with replacement action give a present e.g. by clicking give a present in drop down menu or by deleting watch and typing in the UI field or window give a present .

In addition to add more actions to the predefined action watch processing unit may display an add icon beside a watch icon to receive one or more actions that a user may type when a user clicks a right mouse button. Further processing unit may attach to the narrative at least one picture taken when receiving the recorded usage history of the at least one action corresponding to the application. Processing unit may transmit the narrative to external server to be shared through the Internet.

Thus shows another illustrative user interface by which one or more embodiments of a narrative generating scheme may be implemented in accordance with various embodiments described herein.

Processing flow may include one or more operations actions or functions as illustrated by one or more blocks and or . Although illustrated as discrete blocks various blocks may be divided into additional blocks combined into fewer blocks or eliminated depending on the desired implementation. Processing may begin at block .

Block register application may refer to a narrative application downloaded and hosted on computing device for generating a user s narrative based on recorded history of actions. The narrative application downloaded and hosted on computing device may register a third party mobile application hereinafter referred to as the third party application which may be one of a plurality of mobile applications that are also downloaded from one or more of the application distribution platforms and installed on computing device . According to some embodiments a user of computing device may drag an icon or representation of the third party application onto an icon or representation of the narrative application on a user interface UI of computing device . Processing may proceed from block to block .

Block identify action corresponding to application may refer to the narrative application identifying one or more user actions that may be taken while using the registered narrative application. The actions may be a user defined actions implemented by computing device .

As an example of identifying at least one action the registered narrative application may display the predefined list of actions in a drop down menu of a pop up window corresponding to the registered application. Then the narrative application may receive one or more user inputs to select at least one action from the predefined list of actions in the drop down menu e.g. by clicking selections of the one or more actions.

As non limiting example of the actions list if the narrative application registers Amazon Kindle Store the narrative application may display in e.g. a pop up window or drop down menu a predefined list of actions including as non limiting examples read hold like dislike purchase read again highlight annotate preview etc. using a UI on computing device or the narrative application server. Processing may proceed from block to block .

Block receive recorded usage history pertaining to action may refer to the narrative application receiving recorded usage history of the at least one action corresponding to the registered third party application transmitted from external server and computing device .

The recorded usage history of the at least one action corresponding to the registered application may include an executed function an execution time an execution location of the at least one application along with a title a starting time and a location transmitted from external server . Further the recorded usage history of the at least one action corresponding to the application may include an image a rating an author an actor actress and a review associated with the application.

The information regarding the executed function the execution time and the execution location may be stored in computing device and the narrative application may receive such information transmitted from computing device by calling application programming interfaces APIs because the usage record of applications installed on computing device may be stored in computing device .

On the contrary the information regarding the title the starting time and the location may be stored in external server linked to the registered application and the narrative application may receive such information transmitted from external server by calling application programming interfaces APIs . The information regarding a subject matter of the registered application e.g. e Book of Amazon Kindle Store or a movie ticket of AMC grand may be stored in external server linked to the registered application. Processing may proceed from block to block .

Block generate narrative based on usage history may refer to the narrative application generating a narrative to be viewed on a user interface of the computing device based on the received usage history of the action corresponding to the registered application. For example after a user has booked a ticket for Dark Knight using the AMC grand application which has been registered by the narrative application and the user further selects the action watch movie using the AMC grand application the narrative application may generate a narrative to record such actions in one or more of various narrative formats.

That is the narrative application may display a narrative In Beverly Hills I dropped by the Dunkin Donuts at 3 00 p.m. After that I watched Dark Knight at 4 00 p.m. at the AMC Grand Theater. It was so exciting as people said based on the predefined expression stored in computing device such as It was so exciting as people said. 

Thus shows an example processing flow of operations by which at least portions of a narrative generating scheme may be implemented in accordance with various embodiments described herein.

In a very basic configuration a computing device may typically include at least one or more processors a system memory one or more input components one or more output components a display component a computer readable medium and a transceiver .

Processor may refer to e.g. a microprocessor a microcontroller a digital signal processor or any combination thereof.

Memory may refer to e.g. a volatile memory non volatile memory or any combination thereof. Memory may store therein an operating system an application and or program data. That is memory may store executable instructions to implement any of the functions or operations described above and therefore memory may be regarded as a computer readable medium.

Input component may refer to a built in or communicatively coupled keyboard touch screen or telecommunication device. Alternatively input component may include a microphone that is configured in cooperation with a voice recognition program that may be stored in memory to receive voice commands from a user of computing device . Further input component if not built in to computing device may be communicatively coupled thereto via short range communication protocols including but not limitation radio frequency or Bluetooth.

Output component may refer to a component or module built in or removable from computing device that is configured to output commands and data to an external device.

Display component may refer to e.g. a solid state display that may have touch input capabilities. That is display component may include capabilities that may be shared with or replace those of input component .

Computer readable medium may refer to a separable machine readable medium that is configured to store one or more programs that embody any of the functions or operations described above. That is computer readable medium which may be received into or otherwise connected to a drive component of computing device may store executable instructions to implement any of the functions or operations described above. These instructions may be complimentary or otherwise independent of those stored by memory .

Transceiver may refer to a network communication link for computing device configured as a wired network or direct wired connection. Alternatively transceiver may be configured as a wireless connection e.g. radio frequency RF infrared Bluetooth and other wireless protocols.

From the foregoing it will be appreciated that various embodiments of the present disclosure have been described herein for purposes of illustration and that various modifications may be made without departing from the scope and spirit of the present disclosure. Accordingly the various embodiments disclosed herein are not intended to be limiting with the true scope and spirit being indicated by the following claims.

Thus shows an illustrative computing embodiment in which any of the processes and sub processes of a narrative generating scheme may be implemented as computer readable instructions stored on a computer readable medium in accordance with various embodiments described herein.

