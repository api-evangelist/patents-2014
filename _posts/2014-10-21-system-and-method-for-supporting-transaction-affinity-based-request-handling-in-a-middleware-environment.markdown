---

title: System and method for supporting transaction affinity based request handling in a middleware environment
abstract: A system and method can support transaction processing in a middleware environment. A processor, such as a remote method invocation stub in the middleware environment, can be associated with a transaction, wherein the transaction is from a first cluster. Then, the processor can handle a transactional request that is associated with the transaction, wherein the transactional request is to be sent to the first cluster. Furthermore, the processor can route the transactional request to a said cluster member in the first cluster, which is an existing participant of the transaction.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09519509&OS=09519509&RS=09519509
owner: ORACLE INTERNATIONAL CORPORATION
number: 09519509
owner_city: Redwood Shores
owner_country: US
publication_date: 20141021
---
A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention is generally related to computer systems and is particularly related to transaction processing in a middleware environment.

The enterprise application servers can process various transactions within an organization such as by taking advantage of the distributed object computing which allows various applications to operate over multiple machines and or virtual machines VMs . With the developments in new technologies such as high performance network and multiprocessor computers there is a need to further improve the performance. This is the general area that embodiments of the invention are intended to address.

Described herein are systems and methods that can support transaction processing in a middleware environment. A processor such as a remote method invocation stub in the middleware environment can be associated with a transaction wherein the transaction is from a first cluster. Then the processor can handle a transactional request that is associated with the transaction wherein the transactional request is to be sent to the first cluster. Furthermore the processor can route the transactional request to a said cluster member in the first cluster which is an existing participant of the transaction.

The invention is illustrated by way of example and not by way of limitation in the figures of the accompanying drawings in which like references indicate similar elements. It should be noted that references to an or one or some embodiment s in this disclosure are not necessarily to the same embodiment and such references mean at least one.

The description of the invention as following uses the WebLogic server WLS environment as an example for a middleware environment. It will be apparent to those skilled in the art that other types of middleware environment can be used without limitation.

Described herein are systems and methods that can support transaction processing in a middleware environment.

A transaction can be a distributed XA transaction or a local transaction. The XA transaction can update multiple resource managers such as databases in a coordinated manner. In contrast a local transaction begins and commits the transaction to a single resource manager.

Furthermore a global transaction is a mechanism that allows a set of programming tasks potentially using more than one resource manager and potentially executing on multiple servers to be treated as one logical unit.

In accordance with an embodiment of the invention the system can route various requests in a global transaction based on the transaction affinity. For example the XA transaction affinity allows server instances that are participating in a global transaction to service related requests rather than load balancing these requests to other member servers. The XA Transaction Affinity allows the transaction to always land on the server where the transaction started in the cluster subsequent requests made in the context of that transaction are also handled on the same server rather than load balancing requests to other servers in the cluster that have the same resources configured.

The transactional requests may target a remote cluster which can include a plurality of cluster members e.g. application servers on host machines . The RMI stub can be used to invoke a remote method provided by an application running on a cluster member in the remote cluster .

As shown in the request may be the first request which is involved in the transaction and targets the remote cluster . For example the RMI stub can route the request to a cluster member in the remote cluster based on a load balancing algorithm e.g. a round robin algorithm since no cluster member in the remote cluster is an existing participant of the transaction .

Then the RMI stub can handle a subsequent request which also targets the cluster . The RMI stub can take advantage of a transaction interceptor which can intercept the request that targets the cluster . Furthermore the RMI stub can use a handler such as a transaction affinity handler to handle the transactional affinity based request routing.

Instead of load balancing the request to other cluster members e.g. the cluster member the transaction affinity handler associated with the clustered RMI stub can route the request to the cluster member which is a host in the set of servers servicing the global transaction since the cluster member is an existing participant of the transaction in the remote cluster .

Thus by selecting a server that is already a participant of the transaction the system can reduce the possibility that the global transaction may span over multiple cluster members in the remote cluster .

The following List shows an exemplary application programming interface API for a transaction interceptor .

As shown in the above the system can call the loadBalance method to choose a remote reference for handling a request before invoking a remote method . Furthermore an implementation of the loadBalance method may return a reference to a server that is currently in use for continuing its usage or return a new reference to a different server for load balancing.

In accordance with an embodiment of the invention a cluster manager can be used for configuring the cluster to support the transaction affinity based request handling. For example the ClusterMBean for a WLS cluster can include an attribute e.g. TxnAffinityEnabled which indicates that the transaction affinity based request handling is required in the WLS cluster.

The following List shows an exemplary application programming interface API for configuring a ClusterMBean.

In WLS the system can enable the transaction affinity by configuring the TxnAffinityEnabled property in the ClusterMBean which function as a cluster manager . Furthermore once the TxnAffinityEnabled property is configured the transaction affinity may apply to the applications that have transactional methods deployed in the cluster .

Subsequently when a method that is marked as transactional is invoked as part of the global transaction the TransactionInterceptor can intercept the request and the TransactionalAffinityHandler can be used for performing the transactional affinity based request routing. Thus the system can choose a WLS server which is an existing participant of a global transaction for handling the clustered requests.

In accordance with an embodiment of the invention the system can provide better overall throughput by reducing inter server transaction coordination traffic improving resource utilization such as the number of the JDBC connections and simplifying asynchronous processing of transactions such as avoiding timing issues related to asynchronous processing of transaction afterCompletion callbacks .

In accordance with an embodiment of the invention the transaction affinity based request handling in the cluster can take precedence over other approaches such as the load balancing options. On the other hand if the cluster does not have a cluster member already participating in the transaction the RMI stub can load balance the request to an available cluster member .

For example in WLS a set of load balancing algorithms can be configured on the ClusterMBean. The set of load balancing algorithms may include various options such as round robin weight based random round robin affinity weight based affinity and random affinity. 

Additionally a user can control the request routing in the middleware environment e.g. by defining a customized call router that can return a name of a server that a request should be routed to.

In accordance with an embodiment of the invention if there is no host that matches the criteria based on the transaction affinity then the request can be failed over to the next host available in the replica list. Also if the selected cluster member fails the system may be able to perform necessary transaction recovery tasks e.g. relying on the Java transaction API JTA transaction recovery service.

In accordance with an embodiment of the invention the transactional affinity based request routing can be used for handling the in doubt transactions e.g. working with the no XA transaction log T Log feature in WLS . Furthermore the transactional affinity based request routing can be significantly advantageous when the in doubt transactions span over multiple application servers clusters.

Furthermore a transaction such as a global transaction can involve multiple applications in the middleware environment . For example the global transaction involves an application A in the cluster A and an application B in the cluster B .

Additionally multiple copies of the same application can be deployed within a cluster for servicing the different requests in the middleware environment . For example each of the application servers can be deployed with a copy of the application A i.e. APP A . Also each of the application servers can be deployed with a copy of the application B i.e. APP B .

At step the APP A which is running on an application server in the cluster A can dequeue a message from a Java message service JMS queue and initiates the global transaction .

At step the APP A can call the APP B which is running on the application server in the cluster B . The application server can function as a sub coordinator in the cluster B for the transaction since the transaction is propagated to the cluster B .

At step the APP B can update the records in the database . Then at step the transaction can be propagated back to the cluster A . With the transaction cluster affinity feature enabled the system may force the transactional request to land on the application server which is coordinating the transaction instead of performing load balancing which may land the transactional request on a different server e.g. the application server or the application server .

In accordance with an embodiment of the invention there is a performance advantage by eliminating the overhead of coordinating resources and sub coordinators across multiple server instances in a cluster.

As shown in there can be at most one application server which functions as the participant in a global transaction per cluster.

Furthermore as the number of the inter cluster RMI invocations increases there may be a large number of application servers participating in the transaction without taking advantage of the transaction affinity based request handling . By using the transaction affinity based request handling the system can limit the number of server participants to one application server in each cluster.

Thus the transaction manager TM e.g. on the application server can have less sub coordinators such as the WLS servers and resources to manage.

In accordance with an embodiment of the invention the transaction affinity based request handling can be used for supporting performing two phase commit calls in a global transaction.

The two phase commit protocol for processing a XA transaction is a method of coordinating a single transaction across two or more resource managers. It guarantees data integrity by ensuring that transactional updates are committed in all of the participating databases or are fully rolled back out of all the databases reverting to the state prior to the start of the transaction. In other words either all the participating databases are updated or none are updated.

In accordance with an embodiment of the invention the system can take advantage of both the transaction affinity optimization and the database instance affinity optimization.

Using the database instance affinity optimization such as the GridLink XA affinity in WLS the database instance information can be stored in middle tier transaction context. The system can limit database communication from one or more application server instances to a single database cluster instance. Thus the database instance affinity optimization can achieve performance gains by reducing database intra cluster communication for a given database transaction branch of a global transaction.

In contrast the transaction affinity optimization such as the WLS cluster XA affinity requires no additional affinity context since RMI request routing can be performed using existing transaction participant information. The transaction affinity optimization may operate solely in the middle tier e.g. within a single domain or across domains. Thus the system can achieve performance gains by reducing global transaction server participants thereby reducing middle tier inter server communication for JTA two phase commit processing.

The present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

In some embodiments the present invention includes a computer program product which is a storage medium or computer readable medium media having instructions stored thereon in which can be used to program a computer to perform any of the processes of the present invention. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many modifications and variations will be apparent to the practitioner skilled in the art. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

