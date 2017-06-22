---

title: Method and system for mobile structured collection of data and images
abstract: The present invention is a method for improving functionality of a smart device to perform mobile structured collection and transformation of data includes instantiating an ATAK Session Object having multiple Session Object Attributes including a geo-specific location attribute having a geo-specific location attribute value. The method then updates the geo-specific location attribute of the ATAK Session Object to reflect a geo-specific location and links an Image Object with the ATAK Session Object to create a Linked ATAK Image Object. Next, the method instantiates an Observational Record Object (ORO) having an ORO attribute value reflecting an observation instance at the geo-specific location. Finally, the method creates a Linked ORO by linking the ORO with the Linked ATAK Image Object. The present invention also includes an apparatus and system for performing the above method.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09418080&OS=09418080&RS=09418080
owner: The United States of America, as represented by the Secretary of the Navy
number: 09418080
owner_city: Washington
owner_country: US
publication_date: 20141021
---
This application is a non provisional application of and claims priority to U.S. Patent Application 61 894 282 filed on Oct. 22 2013 which is hereby incorporated by reference in its entirety.

This invention relates to the field of data processing and more specifically to preparing data for information retrieval by transforming data structures and data objects.

A smart device is an electronic communications device capable of performing operations independently or interactively with other devices. Smart devices have independent processing capability and connect to wireless networks using various protocols such as Bluetooth allowing them to operate interactively and autonomously. Manufacturers continuously update smart devices and their protocols to allow faster communications and more complex processing. Many smart devices known in the art boot up rapidly and provide quick connectivity using their respective protocols.

The Android Tactical Assault Kit ATAK is a government open source software project with the objective of providing troops with geo specific information during operations using smart devices such as smart phones and tablets.

ATAK currently utilizes the Android operating system and associated protocols in conjunction with commercially available smart devices such as Android phones and tablet. The Android operating system and other smart phone operating systems offer GPS capability and the ability to interact with object oriented programming tools and data management programs known in the art such as Java and SQL.

The military currently utilizes the GPS capability of the Android operating system for intelligence gathering and during military operations to collect location specific data. For example military observers can identify items that appear in the images such as schools or hospitals to avoid damaging them during an operation designate pickup points for evacuation or note the presence of weapons and hostile persons. The ability to provide annotated visual data in real time reduces military dependence on voice channels and can graphically designate points of interest more accurately.

ATAK enables the collection of large amounts of data and collection of countless on site observations. ATAK integrates capabilities for gathering image and other data from individual observers and for associating data collected from each user. ATAK also allows collaborative mapping and sharing of drawings created by each user as well as features that facilitate real time intelligence gathering including file sharing photo sharing video sharing data streaming and interfaces for military communications systems. ATAK also includes Java programming capabilities and the development of applications to customize the operating system.

Despite the integration of these sophisticated tools ATAK has several known limitations that prevent the use of ATAK for rapid analytics using data gathered during battle. A major limitation is that data from multiple observers appears in heterogeneous non standard formats since each user has an individualized approach to gathering data. This requires subjective interpretation and human correlation of data obtained from each user. In some instances a third party receiving data may need to correlate and create reports from multiple observers through intensive time consuming review.

Additionally since observers do not gather data in a structured manner many of their observations may be irrelevant or incomplete. Gathering irrelevant data adds time to the process during critical missions.

Currently despite the near real time communications capability of smart devices and the broad functionality of ATAK it is not possible to retrieve cross reference and validate intelligence data gathered from multiple observers in real time during military operations.

In accordance with one embodiment a method for improving the functionality of a smart device to perform mobile structured collection and transformation of data includes instantiating an ATAK Session Object having a plurality of Session Object Attributes including at least one geo specific location attribute having a geo specific location attribute value. The method then updates the geo specific location attribute of the ATAK Session Object to reflect at least one geo specific location. Next the method links at least one Image Object with the ATAK Session Object to create at least one Linked ATAK Image Object. The method then instantiates at least one Observational Record Object ORO having at least one ORO attribute value reflecting at least one observation instance at one of the at least one geo specific location. Finally the method links the at least one ORO with the at least one Linked ATAK Image Object to create at least one Linked ORO.

In accordance with one embodiment an apparatus for mobile structured collection of data and images includes a smart device configured with software to create a smart device processing component functionally capable of displaying and updating a graphical user interface GUI to receive user input data associated with observations and to transform the user input data into object databases configured for search and retrieval operations wherein the smart device processing component is configured to perform transformative functions to create quasi unique data structures using the above method.

In accordance with one embodiment a system for mobile structured collection of data and images includes at least one smart device configured with software to instantiate update and link at least one ATAK Session Object at least one ATAK Image Object and at least one ORO at least one remote computer configured to receive the at least one ATAK Session Object the at least one ATAK Image Object and the at least one Observational Record Object and a connection interface which allows the smart device to transmit data associated with the at least one ATAK Session Object the at least one ATAK Image Object and the at least one ORO to the at least one remote computer.

In various embodiments smart device is programmed receive data in a structured format and to prompt the user to enter values necessary to completely describe observations relevant to a location depicted in an image taken by smart device using imaging components known in the art.

In various embodiments the data may be entered in structured formats using GUI prompts and updated GUI screens. In the exemplary embodiment shown data entered by an observer updates the attribute values and fields of the novel software objects described herein. An update may include instantiating a new instance of an object described herein creating a new field populating a data field or changing the value within a data field to reflect user observation.

Method creates various novel software objects for collecting observational data consistent with an object oriented programming language known in the art or any program capable of creating and utilizing heterogeneous data structures for collection of observational data. In the embodiment shown a heterogeneous data structure is a data structure exhibiting consistent characteristics that render the data structure suitable for search query and analytical operations.

In the exemplary embodiment shown programming utilizes Java and other Application Programming Interface API language incorporated into ATAK and or the operating system of smart device . The exemplary embodiment described herein uses the Java programming language or any API available and capable of interfacing with the operating system of the smart device. Observational data may include data images and any other information capable of being transmitted by smart device using any signal computer language computer protocol or transmission protocol known in the art.

In the exemplary method an observer updates data by entering values in GUI of smart device . As data updates the data instantiates or creates novel objects further described herein to populate attribute values e.g. fields which define a characteristic or value associated with objects. As used herein the term object refers to any data structure known in the art and may include data of any type. Objects may or may not include functions which are invoked when data attribute values update or change or when certain thresholds or other criteria are met. As used herein the term attribute refers to any specification that defines a property of an object. As used herein the term attribute value refers the specific data populating such an attribute. As used herein the term real time refers to events observations and transmissions that occur during or in a time frame that is proximate to the time frame during which a user enters observation data. A proximate time frame may vary but is generally a time frame during which observational data remains current and usable.

In operation method instantiates an ATAK Session Object . ATAK Session Object has multiple Session Object Attributes . Session Object Attributes include at least one geo specific location attribute having a geo specific location attribute value . As used herein the term geo specific location attribute refers to an attribute specifically to a geographical location such as but not limited to geographical coordinates. In various embodiments Session Object Attributes may also include quasi unique identifying numbers data or time attributes. As used herein the term quasi unique refers to an element different from other elements within the same method device or system.

In operation method updates geo specific location attribute of ATAK Session Object to reflect at least one geo specific location .

In operation method links at least one Image Object with ATAK Session Object to create at least one Linked ATAK Image Object . Image Object may include image files in raster formats vector formats or compound formats.

In operation method instantiates at least one Observational Record Object ORO having at least one ORO attribute value reflecting at least one observation instance at geo specific location . In one exemplary embodiment a user instantiates ORO reflecting one of the following biometrics buildings documents drugs electronics explosives materials persons relational sites vehicles or weapons. For example a user may select building to instantiate ORO reflecting that the user has noted a building. In the exemplary embodiment ORO attribute values relating to buildings may include building type number of entrances number of people in residence construction type and owner.

In operation method links at least one ORO with at least one Linked ATAK Image Object to create at least one Linked ORO .

In optional operation method updates multiple Session Object Attributes . Each Session Object Attribute reflects data about an observational session .

In optional operation method continuously updates at least one geo specific location attribute value within ATAK Session Object to reflect a change in at least one geo specific location .

In optional operation method continuously adds a new geo specific location attribute within ATAK Session Object to correspond to additional geo specific locations observed within observational session associated with ATAK Session Object .

In optional operation method links at least one ORO to at least one other ORO by updating at least one object relationship attribute value within each ORO . For example if ORO indicates a building and another ORO indicates a person object relationship attribute value may indicate that the person is the building owner or a resident. In another example if ORO indicates a vehicle and another ORO indicates drugs object relationship attribute value may indicate that the drugs were found in the vehicle.

In optional operation method assigns at least one time attribute value to at least one object selected from a group consisting of ATAK Session Object Linked ATAK Image Object ORO and Linked ORO .

In optional operation method continuously instantiates and links Image Objects to create additional Linked ATAK Image Objects associated with ATAK Session Object .

In optional operation method updates at least one ORO attribute value of ORO until all mandatory fields of ORO have been populated. As used herein the term mandatory fields refers to preselected attributes of ORO that method must populate.

In optional operation method updates at least one database to reflect instantiation of an object. Database is selected from the group consisting of an ATAK Session Object database a geo location database an Image Object database an ORO database and a user defined database . Database is located on smart device or on at least one external computer on a network . External computer is configured with database management software capable of performing a query of database to identify objects having queried attributes or to identify objects are linked to other objects having queried attributes.

In optional operation method updates Linked ATAK Image Object by using a drawing function to update visual attribute values that appear on GUI .

In optional operation method instantiates a Drawing Object by entering a plurality of image coordinate values and at least one visual attribute value and linking Drawing Object to at least one ATAK Image Object .

In optional operation method transmits in real time at least one object from smart device to at least one external computer on network .

An observer instantiates ATAK Session Object and ORO by entering observational data through GUI and implementing method . Similarly once instantiated a user may update ATAK Session Object and ORO to reflect additional data using GUI . In the embodiment shown GUI displays options to allow an observer to enter data to perform each step of method .

Imaging components allow an observer to create Image Object . Imaging components may be still or video cameras known in the art.

Smart device processing component is configured with software functionally capable of displaying and updating GUI . This allows smart device processing component to receive user input data associated with observations and to transform said user input data into objects such as ATAK Session Object and ORO and databases configured for search and retrieval operations. Smart device processing component is configured to perform the transformative functions of method to create quasi unique data structures.

Connection interface allows smart device to transmit data associated with ATAK Session Object ATAK Image Object and ORO .

In the exemplary embodiment shown system comprises a plurality of devices configured to perform method . In various embodiments external computer is also configured to perform method . External computer may also include additional database management capability through optional database management software . External computer may be a single computer or a plurality of geographically distributed computers.

System of the exemplary embodiment further includes ATAK Session Object database geo location database Image Object database ORO database and user defined database . In the embodiment shown ATAK Session Object database geo location database Image Object database ORO database and user defined database are Structured Query Language SQL databases. In various embodiments ATAK Session Object database geo location database Image Object database ORO database and user defined database may by any type of relational database known in the art that may be used for updating objects and files pertaining to observational data.

In the embodiment shown any database management system may be used including database management systems that perform some or all of the functions of Sybase Microsoft SQL Server Access Ingres etc.

In the exemplary embodiment system transmits objects via network to external computer for storage in a format retrievable using any database management system known in the art having data search and retrieval capability. Network enables communication and data transmission between multiple devices or between device and another element of system such as but not limited to external computer . In the exemplary embodiment network is a cloud based network. In various embodiments network is a virtual private network a local area network or a wide area network.

System is implemented on geographically distributed hardware components for structured data collection by multiple observers. The components of system may reside on any combination of hardware devices including processors smart devices and data storage components configured to provide functionality to system . One or more of the components shown in in may reside on a single or multiple devices or a single or multiple networks .

It will be understood that many additional changes in the details materials procedures and arrangement of parts which have been herein described and illustrated to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

