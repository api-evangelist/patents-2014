---

title: System and method for providing data interoperability in a distributed data grid
abstract: A system and method can support data interoperability in a distributed data grid. The system can provide an acceptor in the distributed data grid, wherein the acceptor is associated with a cache that is based on the distributed data grid. Furthermore, the acceptor can receive incoming data from a first client, which can be a non-native client that is associated with a client application. Additionally, the system allows a second client, which can be a native client associated with the distributed cache, to share the received incoming data with the first client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09497283&OS=09497283&RS=09497283
owner: ORACLE INTERNATIONAL CORPORATION
number: 09497283
owner_city: Redwood Shores
owner_country: US
publication_date: 20140619
---
This application claims the benefit of priority to U.S. Provisional Patent Application No. 61 915 923 entitled SYSTEM AND METHOD FOR PROVIDING DATA INTEROPERABILITY IN A DISTRIBUTED DATA GRID filed Dec. 13 2013 Attorney Docket No. ORACL 05468US0 which application is herein incorporated by reference in its entirety.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention is generally related to computer systems and is particularly related to a distributed data grid.

Modern computing systems particularly those employed by larger organizations and enterprises continue to increase in size and complexity. Particularly in areas such as Internet applications there is an expectation that millions of users should be able to simultaneously access that application which effectively leads to an exponential increase in the amount of content generated and consumed by users and transactions involving that content. Such activity also results in a corresponding increase in the number of transaction calls to databases and metadata stores which have a limited capacity to accommodate that demand.

Described herein are systems and methods that can support data interoperability in a distributed data grid. The system can provide an acceptor in the distributed data grid wherein the acceptor is associated with a cache that is based on the distributed data grid. Furthermore the acceptor can receive incoming data from a first client which can be a non native client that is associated with a client application. Additionally the system allows a second client which can be a native client associated with the distributed cache to share the received incoming data with the first client.

Described herein are systems and methods that can provide data interoperability in a distributed data grid.

In accordance with an embodiment as referred to herein a data grid cluster or data grid is a system comprising a plurality of computer servers which work together to manage information and related operations such as computations within a distributed or clustered environment. The data grid cluster can be used to manage application objects and data that are shared across the servers. Preferably a data grid cluster should have low response time high throughput predictable scalability continuous availability and information reliability. As a result of these capabilities data grid clusters are well suited for use in computational intensive stateful middle tier applications. Some examples of data grid clusters e.g. the Oracle Coherence data grid cluster can store the information in memory to achieve higher performance and can employ redundancy in keeping copies of that information synchronized across multiple servers thus ensuring resiliency of the system and the availability of the data in the event of server failure. For example Coherence provides replicated and distributed partitioned data management and caching services on top of a reliable highly scalable peer to peer clustering protocol.

An in memory data grid can provide the data storage and management capabilities by distributing data over a number of servers working together. The data grid can be middleware that runs in the same tier as an application server or within an application server. It can provide management and processing of data and can also push the processing to where the data is located in the grid. In addition the in memory data grid can eliminate single points of failure by automatically and transparently failing over and redistributing its clustered data management services when a server becomes inoperative or is disconnected from the network. When a new server is added or when a failed server is restarted it can automatically join the cluster and services can be failed back over to it transparently redistributing the cluster load. The data grid can also include network level fault tolerance features and transparent soft re start capability.

In accordance with an embodiment the functionality of a data grid cluster is based on using different cluster services. The cluster services can include root cluster services partitioned cache services and proxy services. Within the data grid cluster each cluster node can participate in a number of cluster services both in terms of providing and consuming the cluster services. Each cluster service has a service name that uniquely identifies the service within the data grid cluster and a service type which defines what the cluster service can do. Other than the root cluster service running on each cluster node in the data grid cluster there may be multiple named instances of each service type. The services can be either configured by the user or provided by the data grid cluster as a default set of services.

In a Coherence data grid Both the native client and the non native client can store data in a named cache. For example the native client can be a Coherence native client and the non native client can be a representational state transfer REST client or a memcached client.

In accordance with an embodiment of the invention the distributed data grid can support data interoperability between the native client and the non native client based on software object serialization. For example the system can use a portable object format POF to allow the native client and the non native client to share data e.g. software objects .

The distributed data grid allows the cache to be configured with an acceptor . The native client can use the acceptor e.g. a TCP acceptor to access the cache in the distributed data grid . Additionally the acceptor can be configured to run on a proxy server associated with the distributed data grid .

Furthermore the acceptor can support a binary pass through feature . Before the native client sends data to the acceptor the native client can use a serializer e.g. a POF serializer to convert the data into binary objects such as the POF encoded binary objects. Using the binary pass through feature the acceptor can store the binary data directly in the distributed cache without a need for wrapping the in coming binary data from the native client into another binary object.

Additionally a non native client in the distributed data grid can share the binary data with the native client . As shown in the distributed data grid can use an acceptor for communicating with the native client . Furthermore the acceptor can use a serializer to convert the data received from the non native client into a binary format e.g. POF . Then the acceptor can store the binary data in the cache .

Furthermore the memcached client can interact with a memcached server which provides a caching solution in a computing environment . The memcached server can be an open source in memory key value store that supports ASCII binary and other types of protocols.

In accordance with an embodiment of the invention the memcached acceptor allows the distributed data grid to be a drop in replacement for the memcached server . Using the memcached acceptor the memcached client can easily replace the memcached server with the distributed cache provided by the distributed data gird with no changes required in the client application .

Additionally the memcached acceptor can be used to extend the distributed data grid . For example the memcached acceptor allows the distributed data grid to leverage various open source memcached client libraries which are available in different programming languages including Java Python and C C .

Thus using the memcached acceptor the distributed data grid can accept clients which are implemented using the programming languages that are not supported natively by the distributed data grid . For example the client application which are implemented in the programming languages that are not supported in Coherence such as python ruby etc can use the Coherence data grid for caching purposes. Also the memcached acceptor can provide multi language support for a cloud caching service e.g. the Oracle Public Cloud Caching Service.

In accordance with an embodiment of the invention the client application can use a native client to replace the memcached client in order to take advantage of the advanced features which are provided by the distributed data gird and are only available to the native clients.

As shown in the memcached client may be restricted from using various advance features that are provided by the distributed data grid . For example the memcached client may not use the EntryProcessor feature which may only be available to the native Coherence clients. Subsequently the client application can replace the memcached client with the new native client in order to take advantage of these advance features.

In accordance with an embodiment of the invention the distributed data grid can support data interoperability between the native client and the memcached client based on software object serialization.

As shown in the native client can use the acceptor to access the cache in the distributed data grid . Before the native client sends data to the acceptor the native client can use a serializer to convert the data into binary objects such as the POF encoded binary objects. Using the binary pass through feature the acceptor can store the binary data directly in the distributed cache .

Additionally the memcached client in the distributed data grid can share the binary data with the native client . As shown in the distributed data grid allows the cache to be configured with an acceptor which supports a binary pass through feature . Before the memcached client sends data to the acceptor the memcached client can use a serializer e.g. a pluggable POF serializer to convert the data into binary objects such as the POF encoded binary objects. Using the binary pass through feature the acceptor can store the binary data directly in the distributed cache without a need for wrapping the in coming binary data from the memcached client into another binary object.

In accordance with an embodiment of the invention an exemplary memcached acceptor implementation such as a Coherence memcached adapter can be used for supporting interoperability between the memcached clients and the Coherence clients based on portable object format POF .

For example the Coherence memcached adapter can use the EntryProcessor feature to implement various operations. Additionally Coherence can store different flag and version information as decorations on the binary entry. Also the system allows the memcached clients to use pluggable serializers.

Furthermore the Coherence memcached adaptor can be configured as an acceptor in the proxy service in a fashion similar to a HTTP acceptor. The following List 1 shows an XML configuration file that is used to configure the Coherence memcached adapter to run on a proxy server associated with the Coherence data grid.

Additionally Coherence can enable the memcached adaptor when the interop enabled flag is set to be true in the configuration file. Furthermore the memcached acceptor can use the SelectionService in Coherence Commons for socket channel input output I O .

Additionally the Coherence memcached adaptor can support various authentication mechanisms. For example the Coherence memcached adaptor can use a Coherence Java authentication and authorization service JAAS identity asserter to support the simple authentication and security layer SASL PLAIN authentication mechanism. Also the Coherence memcached adaptor can take advantage of the Coherence proxy security framework for user authorization.

In accordance with an embodiment of the invention the Coherence memcached adaptor supports a protocol that involves running a command against an item by a memcached client. This item can include any one of the followings 

Additionally the memcached client can use various retrieval commands such as the get gets commands. Also the memcached client can use other commands such as the delete stat version touch flush commands.

In accordance with an embodiment of the invention the memcached client can support the simple authentication and security layer SASL which is a framework for authentication. Moreover the memcached client can use different serialization formats since the memcached binary protocol may not specify a serialization format.

The present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

In some embodiments the present invention includes a computer program product which is a storage medium or computer readable medium media having instructions stored thereon in which can be used to program a computer to perform any of the processes of the present invention. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many modifications and variations will be apparent to the practitioner skilled in the art. The modification and variation include any relevant combination of the described features. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

