---

title: Processing data
abstract: At a network node separate from a subscriber configuration network node configured to store subscriber configuration data for a plurality of subscriber devices, a request to access configuration data associated with a subscriber stored at the subscriber configuration network node is received. In response to the received access request comprising a private user identity for the subscriber, but not a public user identity for the subscriber, the network node retrieves, from a user identity database configured to store user identity data for identifying subscribers in the network, a public user identity for the subscriber, the retrieval being carried out on the basis of the private user identity for the subscriber comprised in the received access request, and transmits an authorization request to the subscriber configuration network node comprising the public user identity retrieved from the user identity database and the private user identity comprised in the received access request.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09438579&OS=09438579&RS=09438579
owner: Metaswitch Networks Ltd.
number: 09438579
owner_city: Enfield
owner_country: GB
publication_date: 20140128
---
This application claims priority under 35 U.S.C. 119 a to 1 UK patent application no. GB1307811.8 filed Apr. 30 2013 2 UK patent application no. GB 1308080.9 filed May 3 2013 3 UK patent application no. GB 1308078.3 filed May 3 2013 and 4 UK patent application no. GB 1400841.1 filed Jan. 17 2014. Each of the above referenced patent applications is hereby incorporated by reference in its entirety.

The present disclosure relates to processing data. In particular but not exclusively the present disclosure relates to measures including methods apparatus and computer program products for processing data in a telecommunications network.

Internet Protocol Multimedia System IMS networks have the concept of both public and private user identities. Public user identities are how one phone user or subscriber is identified by other phone users for example when making a call one user provides the public user identity of the other user they want to call. Private user identities are how the user identifies themselves to the core of the network in particular they can for example be used for authentication. Different types of subscriber data are associated with public user identities from private user identities for example authentication credentials can be stored at the scope of a private user identity as opposed to a public user identity.

The IMS architecture proposes a Home Subscriber Server HSS component which stores this subscriber data and exposes it over a Cx interface. Authentication credentials can be retrieved from the HSS by using a Cx Multimedia Auth Request Answer flow. This flow requires both a public and a private user identity to be provided even though the underlying data is stored only at the scope of a private user identity.

According to first embodiments there is a method of processing data in a telecommunications network the network comprising 

a subscriber configuration network node configured to store subscriber configuration data for a plurality of subscriber devices and

a user identity database configured to store user identity data for identifying subscribers in the network 

receiving a request to access configuration data associated with a subscriber stored at the subscriber configuration network node 

in response to the received access request comprising a private user identity for the subscriber but not a public user identity for the subscriber 

According to second embodiments there is apparatus for use in processing data in a telecommunications network the network comprising 

a subscriber configuration network node configured to store subscriber configuration data for a plurality of subscriber devices and

a user identity database configured to store user identity data for identifying subscribers in the network 

the apparatus comprising a network node separate from the subscriber configuration network node the apparatus comprising at least one processor and at least one memory including computer program code the at least one memory and the computer program code being configured to with the at least one processor cause the apparatus at least to 

receive a request to access configuration data associated with a subscriber from the subscriber configuration network node 

in response to the received access request comprising a private user identity for the subscriber but not a public user identity for the subscriber 

According to third embodiments there is a computer program product comprising a non transitory computer readable storage medium having computer readable instructions stored thereon the computer readable instructions being executable by a computerized device to cause the computerized device to perform a method for processing data in a telecommunications network the network comprising 

a subscriber configuration network node configured to store subscriber configuration data for a plurality of subscriber devices and

a user identity database configured to store user identity data for identifying subscribers in the network 

receiving a request to access configuration data associated with a subscriber from the subscriber configuration network node 

in response to the received access request comprising a private user identity for the subscriber but not a public user identity for the subscriber 

Further features of embodiments will become apparent from the following description of preferred embodiments given by way of example only which is made with reference to the accompanying drawings.

Network node comprises one or more processors and or one or more memories A for performing various data processing tasks according to embodiments. Network node is separate to subscriber configuration network node but is configured to communicate with subscriber configuration network node client device and user identity database . In some embodiments user identity database is located separately to network node and in other embodiments user identity database is located integrally to network node .

Subscriber configuration network node is responsible for storing subscriber configuration data for subscriber devices in telecommunications network .

Client device may comprise a subscriber device or a network node which is configured to communicate with network node for example to transmit access requests to network node . In some embodiments client device comprises a network node from a cluster of network nodes responsible for conducting registration procedures for subscriber devices such as subscriber device which may for example comprise a cellular telephone and or processing routing data relating to communication sessions conducted in the network.

Embodiments comprise a network node or component or element which is configured to cache user identities in user identity database . In embodiments network node presents a REST ful HTTP interface based on an IMS standard Cx interface. In IMS data is either associated with a public user identity or a private user identity but not both . However the Cx interface requires both to be provided on requests. Users of the HTTP interface don t always have both identities so in embodiments network node caches the mapping between these identities so that it can build Cx interface requests even when one identity is absent.

Embodiments comprise caching the mapping from private user identity to public user identity so that network node is able to construct a suitable authorization request for example a Multimedia Auth Request for transmittal to subscriber configuration network node based on just a private user identity.

Embodiments comprise measures including methods apparatus and or computer program products for use in processing data in telecommunications network . In embodiments the network comprises subscriber configuration network node configured to store subscriber configuration data for a plurality of subscriber devices and user identity database configured to store user identity data for identifying subscribers in the network.

In embodiments a request to access configuration data associated with a subscriber from subscriber configuration network node is received at network node separate from subscriber configuration network node . The access request may have been triggered by a Session Initiation Protocol SIP REGISTER event for example in relation to subscriber device attempting to register with the network. The access request may comprise a SIP digest authentication request.

In embodiments in response to the received access request comprising a public user identity for example public example.com and a private user identity for example private example.com for the subscriber network node transmits an authorization request to subscriber configuration network node comprising the public user identity and the private user identity for the subscriber.

In other embodiments in response to the received access request comprising a private user identity for the subscriber but not a public user identity for the subscriber network node retrieves from user identity database a public user identity for the subscriber where the retrieval is carried out on the basis of the private user identity for the subscriber comprised in the received access request in such embodiments network node then transmits an authorization request to subscriber configuration network node comprising the public user identity retrieved from the user identity database and the private user identity comprised in the received access request.

In embodiments the user identity database comprises a cache configured to store mappings between public and private user identities associated with subscribers. In such embodiments network node prior to receipt of the access request caches a mapping between the public user identity and the private user identity for the subscriber in user identity database . In embodiments the mapping is cached in relation to a previous access request for the subscriber received at the separate network node .

In embodiments multiple public user identities map to the same private user identity. Any valid public user identity can be acceptable in an authorization request such as a Multimedia Auth Request message so in embodiments the most recently used public user identity for each private user identity is employed.

In embodiments in response to transmittal of the authorization request network node receives a successful authentication response from subscriber configuration network node . In embodiments in response to receipt of the successful authentication response from the subscriber configuration network node network node updates the cached mapping between the public user identity and the private user identity for the subscriber in user identity database .

In embodiments network node receives the requested configuration data for the subscriber from subscriber configuration network node . In embodiments the access request was received from client device in the network and network node transmits the configuration data for the subscriber received from subscriber configuration network node to client device .

In some embodiments the access request comprises a public user identity for the subscriber and a private user identity for the subscriber and is associated with a SIP flow. In other embodiments the access request comprises a private user identity for the subscriber but not a public user identity for the subscriber and is associated with a Traversal Using Relay Network Address Translation TURN flow. Note that in some embodiments different devices nodes may handle SIP flows than those which handle TURN flows.

In embodiments telecommunications network comprises an IMS network and subscriber configuration network node comprises an HSS.

In embodiments the authorization request is transmitted to and or the successful authentication response is received via an IMS Cx interface of the separate network node.

In embodiments the access request is received via a Hypertext Transfer Protocol HTTP interface of the separate network node. The HTTP interface may for example comprise a Representational State Transfer REST ful HTTP Application Programming Interface API .

In embodiments network node exposes two REST ful HTTP APIs for retrieving authentication credentials one that provides both the public user identity and the private user identity and one that just provides the private user identity. Client device uses the interface that includes both user identities if it has both available and uses the interface that only includes the private user identity if that is all it has.

In embodiments the separate network node comprises a first Representational State Transfer REST ful HTTP Application Programming Interface API configured to accept a first type of access request comprising a public user identity and a private user identity for a given subscriber and a second Representational State Transfer REST ful HTTP Application Programming Interface API configured to accept a second type of access request comprising a public user identity but not a private user identity for a given subscriber.

If for example network node receives a REST ful HTTP API request with both the public user identity and the private user identity it constructs a Multimedia Auth Request message containing both these identities for transmittal to subscriber configuration network node . If network node receives a REST ful HTTP API request with just the private user identity it looks up the corresponding public user identity in user identity database and then constructs a Multimedia Auth Request message using this public user identity and the provided private user identity for transmittal to the subscriber configuration network node .

In step network node caches a mapping between the public user identity and the private user identity for the subscriber in user identity database if there was already a mapping between the public user identity and the private user identity for the subscriber stored in user identity database then this caching updates the existing mapping stored in user identity database . User identity database confirms the caching of step to network node in step . In step network node transmits the configuration data for the subscriber received from subscriber configuration node to client .

In the embodiments of described above step is depicted as occurring after steps and . In alternative embodiments step is carried out before one or more of steps and . Such embodiments may provide improved latency.

Subscriber configuration node authorises the access request on the basis of the public user identity and a private user identity for the subscriber comprised in the authorization request of step and transmits a successful authentication response to separate node in step . In embodiments the configuration data requested by client in access request is transmitted to network node in conjunction with the successful authentication response of step . In step network node transmits the configuration data for the subscriber received from subscriber configuration node to client .

In embodiments in response to step network node caches not shown a mapping between the public user identity and the private user identity for the subscriber in user identity database if there was already a mapping between the public user identity and the private user identity for the subscriber stored in user identity database then this caching updates the existing mapping stored in user identity database . In embodiments user identity database confirms not shown this caching to network node .

Embodiments comprise a method of processing data in a telecommunications network the network comprising 

a subscriber configuration network node configured to store subscriber configuration data for a plurality of subscriber devices and

a user identity database configured to store user identity data for identifying subscribers in the network 

receiving a request to access configuration data associated with a subscriber from the subscriber configuration network node the received access request comprising a private user identity for the subscriber but not a public user identity for the subscriber 

retrieving from the user identity database a public user identity for the subscriber the retrieval being carried out on the basis of the private user identity for the subscriber comprised in the received access request and

transmitting an authorization request to the subscriber configuration network node comprising the public user identity retrieved from the user identity database and the private user identity comprised in the received access request.

The above embodiments are to be understood as illustrative examples of the present disclosure. Further embodiments of the present disclosure are envisaged.

In alternative embodiments client device communicates directly with user identity database . In some such embodiments both public and private user identities are provided to network node . In some such embodiments both public and private user identities are always provided to network node .

It is to be understood that any feature described in relation to any one embodiment may be used alone or in combination with other features described and may also be used in combination with one or more features of any other of the embodiments or any combination of any other of the embodiments. Furthermore equivalents and modifications not described above may also be employed without departing from the scope of the present disclosure which is defined in the accompanying claims.

