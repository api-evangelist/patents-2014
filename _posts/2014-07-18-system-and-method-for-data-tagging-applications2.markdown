---

title: System and method for data tagging applications
abstract: The present invention relates to a method and system for data tagging in the field of computer technologies. In this method, a user terminal acquires tag data, obtains information about services and functions associated with the tag data, then interacts with target servers to exchange service and function information, and fulfills appropriate services and functions to complete the business application. The disclosed data tagging method and system allow user terminal to interact with directly target servers that are associated with relevant services and functions, which allows functions to be realized in distributed target servers, which simplifies the implementations of tag data, reducing the cost to setting servers. The disclosed data tagging methods allow more extensive applications of data tagging, improved user experiences, simplified processes, and lower costs.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09595060&OS=09595060&RS=09595060
owner: Lidong Qu
number: 09595060
owner_city: Beijing
owner_country: CN
publication_date: 20140718
---
The present application relates to the field of computer application technologies especially the field of data coding and data tagging.

Two dimensional 2D codes also referred as two dimensional barcodes data matrix codes or QR codes have large information capacity high security high rate of data retrieval and error correction ability. After they were invented 2D codes have been widely applied to logistics and operations management and identification card management.

With increased popularity of smart phones 2D codes can be captured and uploaded onto real time Internet by smart phones in real time and used cross media channels which enable them to find wide applications in Object to Object OTO fields such as information acquisition mobile shopping commodity counterfeiting identity authentication coupon distribution and so on.

The mobile OTO applications of 2D codes currently focus on providing convenience in e commerce it still lacks in depth applications.

On challenge to conventional 2D codes is that the servers that issue the 2D codes are responsible for the whole application process after the 2D codes are issued. For complex business applications issuing 2D codes with comprehensive functions and integration of various stages of 2D code application require a lot of human and financial investments which poses a barrier to 2D codes application in large and complete business models. There is therefore a need to simplify the processes in order for 2D codes to be effectively used in a wider range of and especially large scale business applications. Moreover there is also a need for better user experiences in 2D code applications.

The present application discloses systems and methods intended to overcome the above mentioned disadvantages in the conventional systems. The disclosed data tagging methods and systems are simplified and easier to use comparing to conventional technologies which are suitable for large scale applications. The disclosed data tagging methods and systems also provide better user experiences and low cost data tagging methods and systems.

To achieve the above objectives the disclosed data tagging methods can include one or more of the following steps 

 1 A user terminal acquires tag data and parses the tag data to obtain a set of information about the services and functions related to a business application. The service information and function information correspond to respective target servers 

 2 The user terminal and the target servers exchange information about the services and functions in order to accomplish the services and functions and fulfill the business application.

 11 The user terminal acquires tagging data from a data tag issuing server parses the tag data and obtains corresponding information about the business application in the tag data 

 12 Based on the information about the business application the user terminal obtains the set of service and function information and information about target servers related to the services and the functions.

The service and function information can include service Software Development Kits SDK and function SDKs respectively corresponding to the services or functions. The service SDK and the function SDK respectively include information about their respective target servers comprising application programming interface API parameters and protocol associated with the target servers.

 21 based user operations the user terminal selects some or all in the set of service and function information 

 22 the user terminal interacts with each target server to exchange the selected service and function information to accomplish appropriate services and functions and to complete the business application.

In the disclosed method the step of user terminal interacting with each target server to exchange the selected service and function information includes the following steps 

The user terminal determines whether the selected service and function information will be exchanged with the target servers in sequential or in parallel order 

The user terminal exchanges the selected service and function information with the target servers in sequence or in sequential or in parallel order.

The present disclosure also provides a data tagging system comprising a user terminal which can include a tag data acquisition module a tag data analysis module and an interaction control module. The tag data acquisition module is configured to acquire data from data tags and store the data. The tag data analysis module parses the tag data to obtain a set of data corresponding to services and functions for business applications. The interaction control module exchanges service and function information with corresponding target servers to accomplish appropriate services and or functions and to complete the business application.

The disclosed data tagging system also includes a data tag issuing server that is configured to provide to the user terminal tag data according to the services as well as service and function information corresponding to respective target servers.

In the disclosed data tagging system the data tag issuing server can store a list of application services and corresponding service and function information and information about target servers associated with the service and function information. The target server information includes API parameters and protocol about the associated target server.

In the disclosed data tagging system the user terminal can be a wired or a wireless terminal wherein the data tag issuing server is connected to the user terminal through a computer network.

In the disclosed data tagging system the user terminal further includes a selection control module operated by a user and configured to select some or all in the set of the service and function information.

In the disclosed data tagging system the user terminal further includes a sequence control module configured to determine the order i.e. sequential parallel of the selected service and function information to exchange with target servers.

In the disclosed data tagging method and system the tag data acquisition module in the user terminal obtains tag data the tag data analysis module parses the tag data to obtain a set of data corresponding to services and functions for business applications the interaction control module exchanges service and function information with corresponding target servers to accomplish appropriate services and or functions and to complete the business application. The disclosed data tagging method and system enables the user terminal to directly interact with target servers to accomplish the business application defined by the service and function information which allows the tasks in complex business applications to be accomplished by distributed servers and eliminates the need for building application servers in a network system. The disclosed data tagging method and system can thus reduce the cost for application service providers to building dedicated application servers allow the data tags to be used more broadly and provide better user experiences and low cost data tagging methods and system.

These and other aspects their implementations and other features are described in detail in the drawings the description and the claims.

The disclosed invention can be more clearly understood with the following detailed descriptions of the exemplified embodiments.

Step 1 the user terminal acquires data from data tag which can be one dimensional barcode two dimensional or three dimensional code. The data tag can also include a RFID tag and near field communication NFC data. The user terminal parses the data tag to obtain a set of service and function information related to a business application. The service and function information are corresponding to respective target servers. Examples of target servers include data tag issuing server configured to generate data tags that define services functions and target servers that implement the services and the functions analysis server configured to extract service and function information from tag data selection servers configured to allow user to select a service location server configured to determine a user s location authentication server configured to authenticate user s identification and purchase server configured to process a user s order.

Step 2 the user terminal exchanges the service and function information with the target servers in order to accomplish the services and functions and fulfill the business application.

 11 The user terminal acquires tagging data from a data tag issuing server parses the tag data and obtains corresponding business application information in the tag data 

 12 Based on the business application information the user terminal obtains a set of service and functions information and information about target servers related to the services and functions. Service information and function information can include product information location information logistics shopping mode selection and order and payment information.

In some embodiments the service and function information can include service Software Development Kits SDK and function SDKs corresponding to the services or functions. The service SDK and the function SDK respectively include information about their respective target servers comprising application programming interface API parameters and protocol associated with the target servers.

 21 Based user operations the user terminal selects some or all in the set of the service and function information 

 22 The user terminal interacts with each target server to exchange the selected service and function information to accomplish appropriate services and functions and to complete the business application.

In some embodiments the step of user terminal interacting with each target server to exchange the selected service and function information includes the following steps 

The user terminal determines whether the selected service and function information will be exchanged with the target servers in sequential or in parallel order 

The user terminal exchanges the selected service and function information with the target servers in sequence or in sequential or in parallel order.

As shown in the above examples and illustrated in a data tagging system can include a service definition server a data tag server for generating and issuing data tag e.g. 2D code and for analyzing data obtained from data tag data tags published on electronic media or printed on paper media a smart user terminal e.g. a smart phone installed with a software application configured to capture an image of the data tag and decode the data tag which is subsequently analyzed by the data tag server and one or more target servers that provide services for business applications.

The user terminal can include a smart phone or a tablet computer equipped with a camera handheld scanner and RFID sensing device. The user terminal can include a tag data acquisition module a tag data analysis module and an interaction control module. The tag data acquisition module is configured to acquire data from data tags and store the data. The tag data analysis module parses the tag data to obtain a set of data corresponding to services and functions for a business application. The interaction control module exchanges service and function information with corresponding target servers to accomplish appropriate services and or functions and to complete the business application.

The data tag server is configured to provide to the user terminal tag data according to the services as well as service and function information corresponding to respective target servers . In some embodiments at least part of data tag decoding tasks is conducted by the data tag server . The user terminal can be a wired or a wireless terminal wherein the data tag server communicates with the user terminal through a computer network.

In the disclosed data tagging system the data tag server that issues data tag can store a list of application services and corresponding service and function information and information about target servers associated with the service and function information. The target server information includes API parameters and protocol about the associated target servers .

Still referring to service information and function information can include product information location information logistics information shopping mode selection and order and payment information. In some embodiments the service and function information include SDK SDK . . . SDK n which can include service Software SDKs and function SDKs corresponding to the services or functions. The service SDK and the function SDK respectively specify information about their respective target servers such as application programming interface API parameters and protocol associated with the target servers .

In some embodiments the user terminal further includes a selection control module operated by a user and configured to select some or all in the set of the service and function information.

In some embodiments the user terminal further includes a sequence control module configured to determine the order i.e. sequential parallel of the selected service and function information to exchange with target servers.

By realizing OTO service definitions integration and collaboration the disclosed system and methods transformed how services are organized and provided can achieve real time services by collaboration across organizations and enable flexible combination of services refinement of service units and automated service coordination.

During store shopping a consumer can use a mobile phone to take picture of data tag such as a 2D code on a commodity. An application i.e. APP installed on the mobile phone can decode the 2D code in the captured image and obtain application service embedded in the 2D code to order the commodity. The consumer can also obtain service information and function information such as product information location information logistics information shopping mode selection and order and payment information.

Specifically the mobile phone first uses the application to connect to the server that maintains the product information via a mobile wireless network acquires the product information and displays it on the mobile phone. Then a location server an example of a target server determines the location of the consumer and his or her relative location to the manufacturer and the storage warehouse. Web based product order information is provided to the consumer. A purchase method selection server another example of a target server integrates product and logistic information and provides the consumer different purchase prices for different purchase methods. After the consumer confirms a purchase method an order server another example of a target server transmits the order to the store for ordering from existing stock. Alternatively the order server can send to order directly to the manufacturer and a logistics vendor through a computer network. Finally the consumer can complete product purchase by making payment using his or her mobile phone. It should be noted that such 2D codes can also be printed directly in advertisements on newspapers and magazines. Consumers can process the product purchase by capture the image of the 2D codes on newspapers or magazines.

Thus the generation of a 2D code for product ordering only requires that the service and function information and information about corresponding target servers to be contained in the corresponding SDKs. The user terminal can decode the 2D code and communicate with target servers directly to fulfill orders. Thus the tasks of an order server are decomposed which refines the 2D code application providing more flexible services and functions at lower cost.

With the increased popularity of high definition television TV set top boxes become common household electronic devices and in hotels. HD programs typically require users to pay a fee. However the right to watch HD programs is tied to a specific TV set top box. It is difficult for a user to watch the HD programs on a different TV set top box. Moreover another difficulty is to allow users to watch HD TV programs for a short term in hotels and other venues.

The data tagging method and system enable a data tag such as a 2D code to be displayed on TV after the TV set top box is turned on. A user can take a picture of the 2D code using a mobile phone. The mobile phone can decode the 2D code extract service information for the paid TV programs and can obtain information about authentication permissions payment information and other services and features.

First the 2D code includes information about an authentication server another example of a target server . The user can authenticate his or her identification through authentication server and then register or login via an authorization server. If the user has purchased the pay TV service the authorization server sends to right to use confirmation via a computer network to the specific TV set top box that the user is using which allows the user to TV programs on the specific TV connected to the TV set top box. Thus the right to watch pay TV is no longer tied to a specific TV set top box. A consumer can watch pay TV programs on any set top box. If the user has not purchased a pay TV service the user can pay for the pay TV service using the purchase information extracted from the 2D code on his or her mobile phone. The mobile phone can communicate directly with a purchase server another example of a target server to complete the order. The simplified pay TV process is very suitable for short term user of pay TV services in hotels etc.

Moreover suitable data tags can include printed data codes 1D 2D 3D codes and RFID tags. Examples of 2D codes include but not limited to two dimensional barcodes data matrix codes or QR codes etc. The 2D codes are first captured the smart user terminal and decoded by the software application on the smart user terminal to obtain tag data. The tag data is then parsed and analyzed by the analysis server to extract service and function information from the tag data. The software application e.g. the mobile application on the smart phone receives the service and function information and displays them on the smart terminal as shown in . On the other hand RFID tags can store service and function. Once retrieved the mobile application can display such information at the user terminal without involving an analysis server.

1. Unified encoding rules for tag data. A data tag issuing server generates data tags according to services and functions to be provided and received wherein the data tags can be retrieved by applications on intelligent user terminals.

2. Tag data retrieved by the intelligent terminals are defined by a combination of the data tag issuing server and intelligent user terminals target servers that provide services and collaborative approach to provide services.

3. An analysis server parses the tag data retrieved by the intelligent terminal to obtain SDKs related to target servers and services and provides the SDKs the intelligent terminal.

4. The tag data is configured to provide and or receive all services and functions necessary for a business application. A user can choose a service or function through a software application e.g. a mobile App at an intelligent terminal to interact with target servers to accomplish actions and service contracts by coordinating services and the corresponding target servers.

1. Flexible combination of services. Services can be flexibly combined and coordinated in response to data tag scanning by a user and user defined services. Tag data include SDKs that define relationship between different target servers based on services target servers and service contracts. The disclosed methods also assure coordination among services and in depth specialization and optimization of resources.

2. More user friendly experiences. The disclosed tag data improve friendliness and user operability of the user interface. A user can select appropriate services at a user interface according to the specific combination of services that is desirable to the user.

3. In depth utilization of a portfolio of services allows separation of authentication payment and service fulfillment which increases the system security.

In the disclosed data tagging methods and system a user terminal obtains data from data tag using a tag data acquisition module parses the tag data using a tag data analysis module to acquire corresponding business applications and associated service and function information. An interaction control module in the user terminal then interactively communicates with target servers to exchange service and function information to fulfill business application. In the disclosed data tagging methods and system the user terminal can implement business application based on the tag data and directly accomplish services and functions by interacting with target servers that provide such services and functions which eliminates the need for a central application server to fulfill the services. Different in complex business applications can therefore by accomplished by distributed interactive target servers which effectively simplifies operation of utilizing tag data reduces the costs of building application servers by service providers. The disclosed data tagging methods and system are more convenient and of lower cost which allow wider applications data tagging with improved user experiences.

In the present specification the present invention has been described with specific examples. However it should be noted that various modifications and variations may be made without departing from the spirit and scope of the invention. Accordingly the specification and drawings are to be regarded for illustrative rather than restrictive purposes.

