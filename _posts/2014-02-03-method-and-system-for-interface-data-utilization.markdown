---

title: Method and system for interface data utilization
abstract: Methods and system for interface data utilization are described. In one embodiment, source interface data may be provided from a provider. The source interface data may be capable of being used to provide a source user interface for a networked resource associated with the provider. A user request may be received through the source user interface. A service call may be provided over a network to an application based on the receiving of the user request. The application may be associated with an application manager. Response data may be received over the network from the application based on the service call. Target interface data may be rendered based on the response data. The target interface data may be provided from the provider.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09454292&OS=09454292&RS=09454292
owner: PAYPAL, INC.
number: 09454292
owner_city: San Jose
owner_country: US
publication_date: 20140203
---
This application is a continuation of Ser. No. 12 129 492 filed May 29 2008 which is incorporated herein by reference in its entirety.

A provider of applications may seek to provide additional functionality to its users. Embedding applications that are not controlled by the provider may increase security risks associated with the user of the embedded applications. The provider may have little control over the output of the embedded applications. Applications provided to the provider by others for deployment may be difficult and expensive to manage.

Example methods and systems for interface data utilization are described. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of example embodiments. It will be evident however to one skilled in the art that embodiments of the present invention may be practiced without these specific details.

In an example embodiment source interface data may be provided from a provider. The source interface data may be capable of being used to provide a source user interface for a networked resource associated with the provider. A user request may be received through the source user interface. A service call may be provided over a network to an application based on the receiving of the user request. The application may be associated with an application manager. Response data may be received over the network from the application based on the service call. Target interface data may be rendered based on the response data. The target interface data may be provided from the provider.

In an example embodiment application source data may be received over a network from an application. A policy of a provider may be accessed. Target interface data may be rendered based on the application source data and the policy of the provider. The target interface data may be capable of being used to provide a user interface for a networked resource associated with the provider. The target interface data may be provided from the provider.

In an example embodiment an application may be configured to offer a service. Origination data including a service call to the service offered by the application may be received. The origination data may be provided to a provider. The provider may be capable of utilizing the origination data to provide interface data.

Examples of the client machine include a set top box STB a receiver card a mobile telephone a personal digital assistant PDA a display device a portable gaming unit and a computing system however other devices may also be used.

The network over which the client machine the provider the networked resource the application and or the application manager are in communication may include a Global System for Mobile Communications GSM network an Internet Protocol IP network a Wireless Application Protocol WAP network a WiFi network or a IEEE 802.11 standards network as well as various combinations thereof. Other conventional and or later developed wired and wireless networks may also be used.

The provider may provide interface data to enable a user of the client machine to access functionality associated with the networked resource . A user request may be received from the client machine through the user interface. The provider may then provide a service call over the network to the application . The service call may be made in an example embodiment when the provider does not have the functionality associated with the user request and the application has the functionality. The application may process the service call and provide response data to the provider in response. The provider may then render target interface data based on the response data and providing the target interface data to the client machine .

The provider may use additional data to render the target interface data. For example the provider may obtain provider data and or a policy from a provider database . The provider data may include user information additional functionality associated with the provider or the like. The policy may include by way of example a developer branding of the networked resource a look and feel of the networked resource a workflow of the networked source or the like.

The application may be by way of example a bookkeeping application a tax calculation application an invoicing application a savings application e.g. certificate of deposit or a video advertising application. However other applications which include functionality to be provided by the provider may also be used. In an example embodiment the provider may utilize the functionality of the application while controlling the interface data provided to the client .

The application manager may access interface definition data from a manager database and use the interface definition data in an example embodiment in providing response data to the provider . The interface definition data may include a user interface specification in user interface specification language.

The application verification module verifies the application . The origination data receiver module receives origination data from the application . The login module receives a login request and processes the login request.

The source interface data provider module provides source interface data from the provider . The source interface data may be capable of being used to provide a source user interface for the networked resource associated with the provider . The providing of the source interface data may be based on the processing of the login request. The source user interface may be a source web page or another type of interface.

The user request receiver module receives a user request through with the source user interface. The receiving of the user request may be based on a service reference. The service call provider module provides a service call over the network to the application based on the receiving of the user request.

The specification provider module provides a response data specification and or an application source data specification to the application manager . The application request receiver module receives an application request over the network from the application based on the providing of the service call.

The data provider module provides the provider data from the provider to the application based on the receiving of the application request. The response data receiver module receives response data over the network from the application based on the service call. The receiving of the response data may be based on the response data specification and or responsive to the providing of the provider data .

The application source data receiver module receives application source data over the network from the application . The receiving of the application source data may be based on the application source data specification. The policy access module accesses the policy of the provider .

The storage module stores at least a portion of the response data and or the source data. The interface definition data module receives the interface definition data from the application manager verifies the interface definition data stores the interface definition data and or accesses the interface definition data associated with the application .

The provider data access module accesses the provider data associated with the provider e.g. based on the user request . The data processing module processes the response data and or the application source data.

The interface data rendering module renders target interface data based on the response data and or the application source data and or renders the source interface data based on the origination data.

The source interface data may include a service reference for the application . The rendering of the target interface data may be based on the response data the provider data the policy the interface definition data and or the processing of the application source data.

The interface data provider module provides the target interface data from the provider . The target interface data may be provided from the provider through an application programming interface API or otherwise provided.

The application configuration module configures the application to offer a service. The interface definition provider module provides interface definition data to the provider .

The origination data receiver module receives origination data including a service call to the service offered by the application . The origination data provider module provides the origination data to the provider . The provider may be capable of utilizing the origination data to provide interface data.

The service call receiver module receives a service call over the network based on the providing of the origination data. The application request provider module provides an application request over the network to the provider based on the receiving of the service call.

The provider data receiver module receives provider data from the provider based on the providing of the application request. The specification receiver module receives a response data specification from the provider .

The response generation module generates response data from the application based on the service call the provider data and or on the specification. The response data provider module provides the response data over the network to the provider .

In an example embodiment the method may be used to enable the provider to offer functionality beyond its own capabilities or specialization. This additional functionality may be provided from the application or a service within the application . Providing the additional functionality to users in this leveraged manner may increase the value and relevance of the provider .

The application may be verified at block . The verification may include a security check validating the application and the like. A response data specification may be provided to the application manager at block .

Source interface data is provided from the provider at block . The source interface data may be capable of being used to provide a source user interface for the networked resource associated with the provider . The source user interface may be a source web page a programmable interface or a different type of interface

In an example embodiment a login request may be received and the login request may be processed prior to the providing of the source interface data.

In an example embodiment origination data may be received from the application and the source interface data provided during the operations at block may be rendered based on the origination data. The source interface data may include a service reference for the application .

A user request is received through with the source user interface at block . The receiving of the user request may be based on the service reference.

At block a service call is provided over the network to the application based on receipt of the user request.

Response data is received over the network from the application based on the service call at block . The receiving of the response data may be based on the response data specification.

In an example embodiment an application request may be received over the network from the application based on the providing of the service call and the provider data may be provided from the provider to the application based on the receiving of the application request. The response data may be received during the operations performed at block responsive to the providing of the provider data.

At least a portion of the response data may be stored at block . The response data may be processed at block . The provider data associated with the provider may be accessed based on the user request at block .

The policy of the provider may be accessed at block . The policy may include by way of example a developer branding of the networked resource a look and feel of the networked resource a workflow of the networked source or the like.

The interface definition data associated with the application may be accessed at block . The interface definition data may include in an example embodiment a user interface specification in user interface specification language.

In an example embodiment the interface definition data may be received from the application manager the interface definition data may be verified e.g. citified identification of security holes and the like and the interface definition data may be stored. The accessing of the interface definition data during the operations at block may be based on the storing of the interface definition data .

The target interface data is rendered based on the response data the provider data the policy and or and or the interface definition data at block . The rendering may include by way of example translation and or conversion of the response data. The target interface data may be capable of being used to provide a target user interface for the networked resource .

The target interface data is provided from the provider at block . The target interface data may be provided from the provider through an application programming interface API or may be otherwise provided.

In an example embodiment the method may be used to enable the provider to offer functionality beyond its own capabilities or specialization. This additional functionality may be provided from the application or a service within the application . Providing the additional functionality to users in this leveraged manner may increase the value and relevance of the provider .

An application source data specification may be provided to the application manager at block . The application manager may be associated with the application . The application may be verified at block .

Application source data is received over the network from the application at block . The receiving of the application source data may be based on the application source data specification.

A login request may be received at block . The login request may be processed at block . At least a portion of the application source data may be stored at block .

The policy of the provider is accessed e.g. from the provider database at block . The provider data associated with the provider may be accessed at block . The interface definition data may be received from the application manager at block .

The interface definition data may be verified at block . The verification may include certifying the interface definition data identifying security holes in the interface definition data or the like.

The interface definition data may be stored at block . The storing of the interface definition data may be based on verification of the interface definition data.

The interface definition data associated with the application may be accessed at block . The interface definition data may include a user interface specification in user interface specification language. The accessing of the interface definition data may be based on storage of the interface definition data . The application source data may be processed at block .

At block target interface data is rendered based on the application source data the response data the provider data the policy and or interface definition data of the provider . The target interface data may be capable of being used to provide a user interface for the networked resource associated with the provider .

The target interface data may be provided from the provider at block . The target interface data may be provided from the provider through an application programming interface API or otherwise provided. The providing of the target interface data may be based on the processing of the login request.

The application is configured to offer a service at block . The Interface definition data may be provided to the provider at block .

Origination data including a service call to the service offered by the application is received at block . The origination data is provided to the provider at block . The provider may be capable of utilizing the origination data to provide interface data.

At block a service call may be received over the network based on the providing of the origination data. An application request may be provided over the network to the provider based on the receiving of the service call at block . The provider data may be received from the provider based on the providing of the application request at block .

A response data specification may be received from the provider at block . Response data may be generated from the application based on the service call at block . The generation of the response data may be based on the service call and the provider data. The generation of the response data may be based on the response data specification.

A networked system in the example forms of a network based marketplace or publication system provides server side functionality via a network e.g. the Internet or Wide Area Network WAN to one or more clients. illustrates for example a web client e.g. a browser such as the Internet Explorer browser developed by Microsoft Corporation of Redmond Wash. State and a programmatic client executing on respective client machines and .

An Application Program Interface API server and a web server are coupled to and provide programmatic and web interfaces respectively to one or more application servers . The application servers host one or more marketplace applications and authentication providers . The application servers are in turn shown to be coupled to one or more databases servers that facilitate access to one or more databases .

The marketplace applications may provide a number of marketplace functions and services to users that access the networked system . The authentication providers may likewise provide a number of payment services and functions to users. The authentication providers may allow users to accumulate value e.g. in a commercial currency such as the U.S. dollar or a proprietary currency such as points in accounts and then later to redeem the accumulated value for products e.g. goods or services that are made available via the marketplace applications . While the marketplace and authentication providers and are shown in to both form part of the networked system in alternative embodiments the authentication providers may form part of a payment service that is separate and distinct from the networked system .

Further while the system shown in employs a client server architecture embodiments of the present invention are of course not limited to such an architecture and could equally well find application in a distributed or peer to peer architecture system for example. The various marketplace and authentication providers and could also be implemented as standalone software programs which need not have networking capabilities.

The web client accesses the various marketplace and authentication providers and via the web interface supported by the web server . Similarly the programmatic client accesses the various services and functions provided by the marketplace and authentication providers and via the programmatic interface provided by the API server . The programmatic client may for example be a seller application e.g. the TurboLister application developed by eBay Inc. of San Jose Calif. to enable sellers to author and manage listings on the networked system in an off line manner and to perform batch mode communications between the programmatic client and the networked system .

The networked system may provide a number of publishing listing and price setting mechanisms whereby a seller may list or publish information concerning goods or services for sale a buyer can express interest in or indicate a desire to purchase such goods or services and a price can be set for a transaction pertaining to the goods or services. To this end the marketplace applications are shown to include at least one publication application and one or more auction applications which support auction format listing and price setting mechanisms e.g. English Dutch Vickrey Chinese Double Reverse auctions etc. . The various auction applications may also provide a number of features in support of such auction format listings such as a reserve price feature whereby a seller may specify a reserve price in connection with a listing and a proxy bidding feature whereby a bidder may invoke automated proxy bidding.

A number of fixed price applications support fixed price listing formats e.g. the traditional classified advertisement type listing or a catalogue listing and buyout type listings. Specifically buyout type listings e.g. including the Buy It Now BIN technology developed by eBay Inc. of San Jose Calif. may be offered in conjunction with auction format listings and allow a buyer to purchase goods or services which are also being offered for sale via an auction for a fixed price that is typically higher than the starting price of the auction.

Store applications allow a seller to group listings within a virtual store which may be branded and otherwise personalized by and for the seller. Such a virtual store may also offer promotions incentives and features that are specific and personalized to a relevant seller.

Reputation applications allow users that transact utilizing the networked system to establish build and maintain reputations which may be made available and published to potential trading partners. Consider that where for example the networked system supports person to person trading users may otherwise have no history or other reference information whereby the trustworthiness and credibility of potential trading partners may be assessed. The reputation applications allow a user for example through feedback provided by other transaction partners to establish a reputation within the networked system over time. Other potential trading partners may then reference such a reputation for the purposes of assessing credibility and trustworthiness.

Personalization applications allow users of the networked system to personalize various aspects of their interactions with the networked system . For example a user may utilizing an appropriate personalization application create a personalized reference page at which information regarding transactions to which the user is or has been a party may be viewed. Further a personalization application may enable a user to personalize listings and other aspects of their interactions with the networked system and other parties.

The networked system may support a number of marketplaces that are customized for example for specific geographic regions. A version of the networked system may be customized for the United Kingdom whereas another version of the networked system may be customized for the United States. Each of these versions may operate as an independent marketplace or may be customized or internationalized and or localized presentations of a common underlying marketplace. The networked system may accordingly include a number of internationalization applications that customize information and or the presentation of information by the networked system according to predetermined criteria e.g. geographic demographic or marketplace criteria . For example the internationalization applications may be used to support the customization of information for a number of regional websites that are operated by the networked system and that are accessible via respective web servers .

Navigation of the networked system may be facilitated by one or more navigation applications . For example a search application as an example of a navigation application may enable key word searches of listings published via the networked system . A browse application may allow users to browse various category catalogue or system inventory structures according to which listings may be classified within the networked system . Various other navigation applications may be provided to supplement the search and browsing applications.

In order to make listings available via the networked system as visually informing and attractive as possible the marketplace applications may include one or more imaging applications utilizing which users may upload images for inclusion within listings. An imaging application also operates to incorporate images within viewed listings. The imaging applications may also support one or more promotional features such as image galleries that are presented to potential buyers. For example sellers may pay an additional fee to have an image included within a gallery of images for promoted items.

Listing creation applications allow sellers conveniently to author listings pertaining to goods or services that they wish to transact via the networked system and listing management applications allow sellers to manage such listings. Specifically where a particular seller has authored and or published a large number of listings the management of such listings may present a challenge. The listing management applications provide a number of features e.g. auto relisting inventory level monitors etc. to assist the seller in managing such listings. One or more post listing management applications also assist sellers with a number of activities that typically occur post listing. For example upon completion of an auction facilitated by one or more auction applications a seller may wish to leave feedback regarding a particular buyer. To this end a post listing management application may provide an interface to one or more reputation applications so as to allow the seller conveniently to provide feedback regarding multiple buyers to the reputation applications .

Dispute resolution applications provide mechanisms whereby disputes arising between transacting parties may be resolved. For example the dispute resolution applications may provide guided procedures whereby the parties are guided through a number of steps in an attempt to settle a dispute. In the event that the dispute cannot be settled via the guided procedures the dispute may be escalated to a merchant mediator or arbitrator.

A number of fraud prevention applications implement fraud detection and prevention mechanisms to reduce the occurrence of fraud within the networked system .

Messaging applications are responsible for the generation and delivery of messages to users of the networked system such messages for example advising users regarding the status of listings at the networked system e.g. providing outbid notices to bidders during an auction process or to provide promotional and merchandising information to users . Respective messaging applications may utilize any one have a number of message delivery networks and platforms to deliver messages to users. For example messaging applications may deliver electronic mail e mail instant message IM Short Message Service SMS text facsimile or voice e.g. Voice over IP VoIP messages via the wired e.g. the Internet Plain Old Telephone Service POTS or wireless e.g. mobile cellular WiFi WiMAX networks.

Merchandising applications support various merchandising functions that are made available to sellers to enable sellers to increase sales via the networked system . The merchandising applications also operate the various merchandising features that may be invoked by sellers and may monitor and track the success of merchandising strategies employed by sellers.

The networked system itself or one or more parties that transact via the networked system may operate loyalty programs that are supported by one or more loyalty promotions applications . For example a buyer may earn loyalty or promotions points for each transaction established and or concluded with a particular seller and may be offered a reward for which accumulated loyalty points can be redeemed.

Interfacing applications may enable functionality from one or more applications not deployed on the application to be available to a user. For example the application may used in place of one of the applications may supplement the functionality of the applications or provide additional functionality not provided by the applications .

In an example embodiment the machine operates as a standalone device or may be connected e.g. networked to other machines. In a networked deployment the machine may operate in the capacity of a server or a client machine in server client network environment or as a peer machine in a peer to peer or distributed network environment. The machine may be a server computer a client computer a personal computer PC a tablet PC a set top box STB a Personal Digital Assistant PDA a cellular telephone a web appliance a network router switch or bridge or any machine capable of executing a set of instructions sequential or otherwise that specify actions to be taken by that machine. Further while only a single machine is illustrated the term machine shall also be taken to include any collection of machines that individually or jointly execute a set or multiple sets of instructions to perform any one or more of the methodologies discussed herein.

The example computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU or both a main memory and a static memory which communicate with each other via a bus . The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device e.g. a keyboard a cursor control device e.g. a mouse a drive unit a signal generation device e.g. a speaker and a network interface device .

The drive unit includes a machine readable medium on which is stored one or more sets of instructions e.g. software embodying any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system the main memory and the processor also constituting machine readable media.

The software may further be transmitted or received over a network via the network interface device .

While the machine readable medium is shown in an example embodiment to be a single medium the term machine readable medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine readable medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the embodiments of the present invention. The term machine readable medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media and carrier wave signals.

Certain systems apparatus applications or processes are described herein as including a number of modules or mechanisms. A module or a mechanism may be a unit of distinct functionality that can provide information to and receive information from other modules. Accordingly the described modules may be regarded as being communicatively coupled. Modules may also initiate communication with input or output devices and can operate on a resource e.g. a collection of information . The modules be implemented as hardware circuitry optical components single or multi processor circuits memory circuits software program modules and objects firmware and combinations thereof as appropriate for particular implementations of various embodiments.

Thus methods and systems for interface data utilization have been described. Although the present invention has been described with reference to specific example embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the invention. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.

The Abstract of the Disclosure is provided to comply with 37 C.F.R. 1.72 b requiring an abstract that will allow the reader to quickly ascertain the nature of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims. In addition in the foregoing Detailed Description it can be seen that various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting an intention that the claimed embodiments require more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Detailed Description with each claim standing on its own as a separate embodiment.

