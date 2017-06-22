---

title: External injection of cloud based network functions into network services
abstract: Disclosed herein are system, method, and computer program product embodiments for providing an API description of an external network service and using the API to integrate the external service into a network. An embodiment operates by receiving, from a service provider, a description of an application programming interface (API), transmitting a call to the service provider using the API for creating a new instance of a service and transmitting to the service provider a traffic flow upon which the service will be applied.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08832321&OS=08832321&RS=08832321
owner: tw telecom holdings, inc.
number: 08832321
owner_city: Littleton
owner_country: US
publication_date: 20140212
---
Embodiments generally relate to virtual network services and in particular to integrating external network functions into network services.

Cloud based network services can allow integration of various independently provided solutions into a virtual network in a manner that is transparent to service users. For example a cloud based network service provided by one entity can incorporate a firewall service provided by a second entity expanding the services available to the user as third parties make them available.

Generally a network integrates externals services by adapting to an external service s application programming interface API . A network can modify its operation to implement the API instantiate the external service and properly route traffic through the external service. However modifying a network s operation to integrate to an API can require substantial time and effort.

In view of the above it would be advantageous to provide a mechanism for external network service providers to communicate an API description that can be incorporated into a network s operation to utilize the external service.

In an embodiment a system receives from a service provider a description of an application programming interface API . The system generates based on a traffic flow an API call to create a new instance of a service provided by the service provider such that the call is formatted as specified by the description and transmits the API call to the service provider. The system transmits the traffic flow to the service provider and receives the traffic flow wherein the service provider has applied the service to the traffic flow.

Further embodiments and features as well as the structure and operation of the various embodiments are described in detail below with reference to accompanying drawings.

In the drawings like reference numbers generally indicate identical or similar elements. Additionally generally the left most digit s of a reference number identifies the drawing in which the reference number first appears.

Provided herein are system method and or computer program product embodiments and or combinations and sub combinations thereof for providing an API description of an external network service and using the API to integrate the external service into a network.

In an embodiment clients and communicate through network . Each of clients and can be any computing device or combination of computing devices that can communicate through a network such as for example personal computers servers mobile devices local area networks LANs etc. Client and can be clients of network . In another embodiment clients and communicate through a virtual LAN VLAN set up by network .

Network includes a network of nodes configured to route data traffic between clients for example clients and . For example network is a metropolitan area network MAN or a wide area network WAN . In an embodiment network provides virtual networking services such as for example VLANs virtual private networks VPNs etc. In an embodiment network provides Ethernet connectivity between clients in remote locations. For example network provides a virtual circuit with dedicated bandwidth for data communications between clients in remote locations. Network may utilize any point to point point to multipoint or multipoint to multipoint networking protocols. Network access protocols used may include for example Ethernet Asynchronous Transfer Mode ATM High Level Data Link Control HDLC Frame Relay Synchronous Optical Networking SONET Synchronous Digital Hierarchy SDH Internet Protocol IP Transmission Control Protocol TCP User Datagram Protocol UDP Multiprotocol Label Switching MPLS etc.

Network service providers provides network services independently from network . For example providers is a hosted by third party entities. An example network service is a firewall that filters a traffic flow between two communicating clients. Other examples of network services are intrusion detection systems antivirus systems anti spam filters etc. In an embodiment network service providers provide network services to multiple networks. Network service providers provides network services by providing an API for creating an instance of a network service and for formatting traffic to be serviced. Networks uses a provider s respective API to provision the provider s services.

In an embodiment network also provides clients with network services. For example network implements its own firewall service for its clients. In an embodiment a client of network can choose to use services provided by network or external providers for additional or alternate services. In an embodiment a client chooses the services and service sources through a client portal webpage.

According to an embodiment network service providers provides a description of the API to network during a registration process. In this manner providers communicates to network how to interact with and provision the services of provider . Network then uses this API description to format a service request and traffic forwarding through the service providers. In this manner network provisions the services of multiple network service providers without having to modify its code for every provider. In an embodiment providers register their respective service APIs by calling a registration API of network and including the provider API description as a parameter.

As depicted in an exemplary network node includes an API registration module a service call module a client portal module and an API database .

In an embodiment API registration module receives API registration calls from network service providers. The API registration calls include an API description of the API call to provision a network service function provided by a service provider. API registration module stores the API description in API database .

In an embodiment service call module generates and transmits API calls to provision a network service. When network seeks to initiate an external network service from a service provider service call module queries API database for the API description of the API call to initiate the service function.

In an embodiment client portal module receives commands from clients of network to initiate external network services. For example client portal module may receive a command from client to include firewall provided by firewall.com for the connection between client and client . In an embodiment client portal module provides a graphical user interface for clients to provision configuration and services settings. Client portal module may then forward the instruction to service call module to initiate the service. Client portal module may provide a confirmation to the client that the external service has been properly initiated or that the service is unavailable. For example if no API for the service has been registered in API database client portal module may notify the client that the service requested is unavailable.

As depicted in an exemplary service provider includes an API publishing module and a service module .

In an embodiment API publishing module communicates a registration API call for registering a network service function with a network that service provider seeks to receive service requests from. In an embodiment API publishing module registers service APIs when a new service is provided or when an API for an existing service has changed.

In an embodiment service module receives API service calls from networks and initiates network service functions accordingly.

In an embodiment a registration API call includes two parts a registration API identifier and an API description .

In an embodiment registration API identifier identifies API call as a call to register an external function with network . Registration API identifier may for example be a flag that differentiates API call from other calls received by network .

In an embodiment API description specifies the format and parameters that are to be passed when calling external network API function . In an embodiment API description includes an external service identifier and parameters .

Service identifier identifies the external network API function that is being registered. Service identifier may be for example a number or a set of characters identifying API function .

Parameters specify the parameters that network needs to pass when provisioning the external API function. In an embodiment parameters are specified from a list of parameters associated with a traffic flow that the external network API function is applied to.

For example network may implement a VLAN between clients and and may seek to establish a firewall for the traffic through the VLAN. In an example embodiment network calls an external API function for the firewall as described by a corresponding API description to establish a firewall service provided by external provider . As part of the API function call network may pass parameters such as for example an identifier of the traffic flow the source and destination addresses of the traffic the source and destination ports etc.

In an embodiment network has a list of available parameters associated with traffic flows and descriptors for these parameters. In an embodiment a provider registering an API function describes the API functions parameters using descriptors from the list of available parameters associated with traffic flows in network . In an embodiment API description specifies the format of an API call with parameters represented as variables in appropriate locations. When forming an API call network replaces the variables with the corresponding parameters for the desired service.

As described above service provider registers an API function for a service provided. To register the API function so network can call the function a provider places a registration API call to network service as shown at step . Network stores the received API description in an API registration database for future reference in initiating the external service function.

At step network initiates the external service by retrieving the appropriate API description for the service from the API database and transmitting the API call to provider

At step network begins to send traffic through provider to perform the provided service. For example if a firewall service is initiated through an API call network sends traffic through provider for processing.

If the format for an API call changes an external service provider updates the API description by for example performing process again.

At step network receives a request from a client to incorporate an external service into a traffic flow. For example client may want to add a firewall provided by firewall.com to a VLAN connection between client and client

At step network checks whether the requested external service has been registered. In an embodiment network checks the API registration database and tries to retrieve a description of the API corresponding to the requested external service. If network does not find an API description for the service network does not create the service instance and notifies the requesting client with an error message as shown in step .

If at step network finds an API description corresponding to the requested service the process moves to step and creates an API call in the format described by the API description. For example network may prepare an API call to create a firewall in a format specified by firewall.com. The API call include parameters in the place of variables specified in the description. For example an API description for creating a firewall using firewall.com may be fw FLOW ID SRC ADDR DST ADDR SRC PORT DST PORT. An API call to establish a firewall between two clients would then substitute the variables for the corresponding parameters of the traffic flow for example fw 60 110.20.30.1 110.20.42.1 88 89. 

At step network transmits the API call to the external service and initiate the service by forwarding traffic in the appropriate format. In the above example network would transmit the API call as described above and then forward flow traffic coming from node 110.20.30.1 88 and directed to 110.20.42.1 89 and divert it through the firewall.com network.

API database may be any stored type of structured memory including a persistent memory. In examples each database may be implemented as a relational database or file system.

Each of the blocks and modules in may be implemented in hardware software firmware or any combination thereof.

Each of the blocks and modules in may be implemented on the same or different computing devices. Such computing devices can include but are not limited to a personal computer a mobile device such as a mobile phone workstation embedded system game console television set top box or any other computing device. Further a computing device can include but is not limited to a device having a processor and memory including a nontransitory memory for executing and storing instructions. The memory may tangibly embody the data and program instructions. Software may include one or more applications and an operating system. Hardware can include but is not limited to a processor memory and graphical user interface display. The computing device may also have multiple processors and multiple shared or separate memory components. For example the computing device may be a part of or the entirety of a clustered computing environment or server farm.

Identifiers such as a b i ii etc. are sometimes used for different elements or steps. These identifiers are used for clarity and do not necessarily designate an order for the elements or steps.

The present invention has been described above with the aid of functional building blocks illustrating the implementation of specified functions and relationships thereof. The boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries can be defined so long as the specified functions and relationships thereof are appropriately performed.

The foregoing description of the specific embodiments will so fully reveal the general nature of the invention that others can by applying knowledge within the skill of the art readily modify and or adapt for various applications such specific embodiments without undue experimentation without departing from the general concept of the present invention. Therefore such adaptations and modifications are intended to be within the meaning and range of equivalents of the disclosed embodiments based on the teaching and guidance presented herein. It is to be understood that the phraseology or terminology herein is for the purpose of description and not of limitation such that the terminology or phraseology of the present specification is to be interpreted by the skilled artisan in light of the teachings and guidance.

The breadth and scope of the present embodiments should not be limited by any of the above described examples but should be defined only in accordance with the following claims and their equivalents.

