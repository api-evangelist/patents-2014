---

title: Apparatus and method for providing virtual API for mashup service
abstract: The present invention relates to an apparatus and a method for providing a virtual API for a web-application mashup service. The apparatus for providing a virtual API includes: a screen data obtaining unit configured to obtain a website screen by accessing a website based on website access information or obtain an application program execution result screen by executing an application program based on application program execution information; and a virtual API processing unit configured to capture an interested area from the website screen related to a virtual API called by a client or from the application program execution result screen and provide the captured predetermined area of interest to the client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09329878&OS=09329878&RS=09329878
owner: ELECTRONICS AND TELECOMMUNICATIONS RESEARCH INSTIT
number: 09329878
owner_city: Daejeon
owner_country: KR
publication_date: 20140716
---
This application claims the benefit of Korean Patent Application No. 10 2014 0009760 filed with the Korean Intellectual Property Office on Jan. 27 2014 the disclosure of which is incorporated herein by reference in its entirety.

Exemplary embodiments broadly relate to an apparatus and a method for providing a virtual API for a web applicable mashup service more specifically to an apparatus and a method for providing functions that are not provided through an open API which is provided by a web server by having these functions implemented in a virtual API.

Mashup refers to creating new software service database etc. by combining open application programming interfaces API provided in the web.

However the information e.g. data content service provided through the open API may have limits or may not contain required information.

Accordingly a new method is needed to obtain required information regardless of provision of relevant API by the website in order to develop various creative mashup services. Moreover in order to provide user friendly information the obtainable information should be what the users want and find valuable rather than what the providers want to disclose and non web based application programs should be also utilizable in the mashup services.

Exemplary embodiments are developed to resolve the disadvantages associated with the related art technologies. Exemplary embodiments provide an apparatus and a method for providing at least some of the functions that are not provided in an open API form in the web and or some of the functions of application programs in the form of a virtual API.

Illustrative non limiting embodiments may overcome the above disadvantages and other disadvantages not described above. The present invention is not necessarily required to overcome any of the disadvantages described above and the illustrative non limiting embodiments may not overcome any of the problems described above. The appended claims should be consulted to ascertain the true scope of the invention.

According to an aspect of exemplary embodiments there is provided an apparatus for providing a virtual API. The apparatus for providing a virtual API in accordance with an embodiment of the present invention can include a screen data obtaining unit configured to obtain a website screen by accessing a website based on website access information or obtain an application program execution result screen by executing an application program based on application program execution information and a virtual API processing unit configured to capture an interested area from the website screen related to a virtual API called by a client or from the application program execution result screen and provide the captured predetermined area of interest to the client.

According to an exemplary embodiment the screen data obtaining unit can include access execution information DB having the website access information and the application program execution information stored therein.

According to an exemplary embodiment the website access information stored in the access execution information DB can include at least one of web browser size information access URL information log in information and menu selection procedure information provided by the website and the website access information stored in the access execution information DB is for a website that does not support an open API.

According to an exemplary embodiment the application program execution information stored in the access execution information DB can include program screen size information and program execution commands.

According to an exemplary embodiment the virtual API processing unit can include interested area information DB configured to store interested area information in the website screen or the application program execution result screen virtual API DB configured to store virtual API information corresponding to the interested area and a virtual API daemon configured to provide the virtual API information stored in the virtual API DB to the client and when a virtual API call command is received from the client to capture and encode an interested area corresponding to the called virtual API from the website screen or application program result screen associated with the virtual API and to provide the captured and encoded interested area to the client.

According to an exemplary embodiment the interested area information can include at least one of target website or application program screen information initial position height and width of an interested area and area capture information.

According to an exemplary embodiment the virtual API information can include virtual API name and virtual API factor.

According to yet another aspect of an exemplary embodiment there is provided a method for providing a virtual API. The method for providing a virtual API can include storing website access information and application program execution information obtaining at least one of website screen and an application program execution result screen when a virtual API is called by a client by accessing a website associated with the virtual API based on the stored website access information or executing an application program associated with the virtual API based on the stored application program execution information and capturing an interested area corresponding to the virtual API from the website screen or the application program execution result screen and providing the captured interested area to the client.

According to an exemplary embodiment the method can further include receiving and storing interested area information in a website screen and the application program execution result screen generating and storing virtual API information corresponding to the interested area and providing the stored virtual API information to a client.

According to yet another aspect of an exemplary embodiment there is provided a computing device including a processor and a memory which includes instructions when executed by the processor perform operations including storing website access information and application program execution information obtaining at least one of a website screen and an application program execution result screen when a virtual API is called by a client by accessing a website associated with the virtual API based on the stored website access information or executing an application program associated with the virtual API based on the stored application program execution information and capturing an interested area corresponding to the virtual API from the website screen or the application program execution result screen and providing the captured interested area to the client.

Moreover the operations can include receiving and storing interested area information in a website screen and the application program execution result screen generating and storing virtual API information corresponding to the interested area and providing the stored virtual API information to a client.

The present invention can be utilized for developing a variety of creative mashup services for allowing users to utilize valuable information. Moreover the present invention allows for enhanced utilization of information by virtualizing a web and an application in the form of an API in order to utilize the information that has not been accessible through open APIs.

Since there can be a variety of permutations and embodiments of the present invention certain embodiments will be illustrated and described with reference to the accompanying drawings. This however is by no means to restrict the present invention to certain embodiments and shall be construed as including all permutations equivalents and substitutes covered by the ideas and scope of the present invention.

Throughout the description of the present invention when describing a certain relevant conventional technology is determined to evade the point of the present invention the pertinent detailed description will be omitted.

Unless otherwise stated any expression in singular form in the description and the claims shall be interpreted to generally mean one or more. 

Moreover any terms module unit interface etc. used in the description shall generally mean computer related objects and can mean for example hardware software and a combination thereof.

As illustrated a web application API virtualization platform can include a virtual API providing server which provides a virtual API and a client which calls the virtual API.

In order to virtualize functions that are not supported with open API to API and provide the virtualized API to users the virtual API providing server can obtain a screen having user required functions included therein and provide the screen in the form of virtual API to the users by accessing a website or running an application program. For example the virtual API providing server can access corporate groupware not exposed to outside sites on a web browser run a video transcoder program or produce a virtual API form of a partial function e.g. searching employee information of the groupware that is not provided in an open API form or of an encoding function of the application program and can provide the virtual API form to the client .

The client can call the virtual API and display results of the virtual API on a selected screen area. As illustrated in the client can display a screen that includes a service area using a web virtual API and a service area using an application virtual API and also can display results of calling a conventional open API in a screen of a service area using an open API.

As shown in an apparatus for providing a virtual API in accordance with an embodiment of the present invention can include a screen data obtaining unit and a virtual API processing unit .

In one embodiment the screen data obtaining unit can obtain a website screen by accessing a website based on website access information or obtain an application program execution result screen by running an application program based on application program execution information.

The virtual API processing unit can capture an interested area from the website screen related to the virtual API called by the client or from the application program execution result screen and provide the captured predetermined area of interest to a relevant client.

Hereinafter the screen data obtaining unit and the virtual API processing unit will be described in more detail with reference to .

As shown in the screen data obtaining unit includes access execution information DB a web browser and an application program execution unit .

The access execution information DB has website access information and application program execution information stored therein.

In one embodiment the website access information and application program execution information stored in the access execution information DB can be inputted from outside for example from a user or administrator.

In one embodiment the website access information may include at least one of web browser size information access URL information log in information and menu selection procedure information provided by the website and the website to be accessed that has the access information thereof stored in the access execution information DB does not support open API.

In one embodiment the application program execution information may include program screen size information and program execution commands.

The web browser can use the website access information stored in the access execution information DB to access a website and obtain the website screen thereof. For example in the case where a partial function of groupware is made to an API an employee information search menu screen can be obtained by accessing the groupware using web browser size information groupware access URL information groupware log in information and employee information search menu selection procedure information which are stored in the access execution information DB .

The application program execution unit can obtain the application program execution result screen by running an application program by use of the application program execution information stored in the access execution information DB .

As shown in the virtual API processing unit can include interested area information DB virtual API DB and virtual API daemon .

The interested area information DB has interested area information in the website screen and the application program execution result screen stored therein.

In one embodiment the interested area information can be determined through an input from outside for example an input by the administrator or user.

In one embodiment the interested area information can include at least one of target website or application program screen information initial position height and width of an interested area and area capture information e.g. sampling rate .

Once the interested area information is inputted a virtual API corresponding to the inputted interested area information is created and stored in the virtual API DB .

The virtual API DB is where virtual API information corresponding to the interested area is stored and can include virtual API name and virtual API factor information.

The virtual API daemon can provide the virtual API information stored in the virtual API DB to the client refer to the interested area information DB once a virtual API call command is received from the client capture and encode an interested area corresponding to the called virtual API from the website screen or application program result screen related to the virtual API and provide the captured and encoded interested area to the client.

For example in case where employee search function of groupware is to be provided as a virtual API a user inputs information on the interested area where employee information is displayed when the groupware is accessed through the web browser. The information on the interested area is then stored in the interested area DB and an employee information search virtual API API name search employee API factor ID name etc. is created and the created employee information search virtual API is registered in the virtual API DB . Once the newly registered virtual API is registered the virtual API daemon can receive the virtual API call request. Once the virtual API call request for employee information search is received from the client the virtual API daemon will capture and encode an employee information area from the web browser screen associated with the pertinent menu and transfer the captured and encoded employee information area to the client.

As illustrated it is assumed that a program using open APIs and virtual APIs are run on a client. For instance in the case where the program has to search additional information using employee information the program calls the virtual API for searching employee information receives a screen providing the employee information as a result of calling the API displays it in a screen area calls an open API using the employee information as a factor thereof and receives and displays the result in a screen area .

In step S website access information and application program execution information are stored in access execution information DB.

In one embodiment the website access information includes at least one of web browser size information access URL information log in information and menu selection procedure information provided by the website. Here the website access information to be stored in the access execution information DB is for a website that does not support open API.

In one embodiment the application program execution information may include program screen size information and program execution commands.

In step S interested area information in a website screen and an application program execution result screen is received and stored in interested area DB.

In one embodiment the interested area information can include at least one of target website or application program screen information initial position height and width of an interested area and area capture information e.g. sampling rate .

In step S virtual API information corresponding to the interested area is created and registered and stored in virtual API DB.

In one embodiment the virtual API information can include virtual API name and virtual API factor information.

In step when the virtual API is called by the client the website screen and the application program execution result screen are obtained by accessing a website associated with the virtual API based on the stored website access information or executing an application program associated with the virtual API based on the stored application program execution information.

In step S an interested area corresponding to the virtual API can be captured in the website screen or the application program execution result screen and provided to the client.

The above described steps for the method for providing a virtual API in accordance with an embodiment of the present invention are not necessarily restricted to the order described herein and it shall be appreciated by those of ordinary skill in the art that the order of the steps can be varied depending on the embodiment. For example although it is described in the present embodiment that the website and application program screens are obtained after the virtual API is called by the client there can be other embodiments in which the screens are obtained before the virtual API is called and then the interested area corresponding to the virtual API is captured after the virtual API is called.

As shown in a computer system may include one or more of a processor a memory a storage a user interface input unit and a user interface output unit each of which communicates through a bus . The computer system may also include a network interface that is coupled to a network. The processor may be a central processing unit CPU or a semiconductor device that executes processing instructions stored in the memory and or the storage . The memory and the storage may include various forms of volatile or non volatile storage media. For example the memory may include a read only memory ROM and a random access memory RAM .

Accordingly an embodiment of the invention may be implemented as a computer implemented method or as a non transitory computer readable medium with computer executable instructions stored thereon. In one embodiment when executed by the processor the computer readable instructions may perform a method according to at least one aspect of the invention.

The program instructions stored in the computer readable medium can be designed and configured specifically for the present invention or can be publically known and available to those who are skilled in the field of software. Examples of the computer readable medium can include magnetic media such as a hard disk a floppy disk and a magnetic tape optical media such as CD ROM and DVD magneto optical media such as a floptical disk and hardware devices such as ROM RAM and flash memory which are specifically configured to store and run program instructions. Moreover the above described media can be transmission media such as optical or metal lines and a waveguide which include a carrier wave that transmits a signal designating program instructions data structures etc. Examples of the program instructions can include machine codes made by for example a compiler as well as high language codes that can be executed by an electronic data processing device for example a computer by using an interpreter.

The above hardware devices can be configured to operate as one or more software modules in order to perform the operation of the present invention and the opposite is also possible.

Hitherto certain embodiments of the present invention have been described and it shall be appreciated that a large number of permutations and modifications of the present invention are possible without departing from the intrinsic features of the present invention by those who are ordinarily skilled in the art to which the present invention pertains. Accordingly the disclosed embodiments of the present invention shall be appreciated in illustrative perspectives rather than in restrictive perspectives and the scope of the technical ideas of the present invention shall not be restricted by the disclosed embodiments. The scope of protection of the present invention shall be interpreted through the claims appended below and any and all equivalent technical ideas shall be interpreted to be included in the claims of the present invention.

