---

title: Global relationship model and a relationship search method for internet social networks
abstract: The present application provides a peer-to-peer networking method and system for integrating heterogeneous social networks. The method applied in a server device includes the following steps: First, the server device connects with a plurality of peer nodes; each of the peer node defines a user end and accessing at least one social network. Then, the server device according to a social relationship of the social networks links to the corresponding peer nodes for integrating a peer-to-peer social network (P2P-iSN) which configures a plurality of social paths among the peer nodes from the different social networks.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09477994&OS=09477994&RS=09477994
owner: NATIONAL TAIWAN UNIVERSITY
number: 09477994
owner_city: Taipei
owner_country: TW
publication_date: 20140626
---
The present application relates to a relationship network search method. More particularly the present application relates to a relationship search method based on integrated heterogeneous social network.

Social Network Sites SNSs such as Facebook and Linkedin have transformed today s society by providing easily accessible platforms for users to connect communicate and share vast amount of information. With SNSs people keep in touch with their contacts reconnect with old acquaintances and establish new relationships with others based on shared features such as hobbies interests and overlapping friendship. The population of SNS users and the number of SNSs has been growing rapidly. For example Facebook is estimated to have over one billion active users. Although it is hard to obtain an accurate estimate there are thousands of SNSs all over the world that provide different kinds of services.

As a result a user may register with multiple SNSs for different social network applications carry multiple SNS accounts interact with contacts from different SNSs publish and access different web contents and share contents within each SNS community. While SNSs offer different services one key feature shared among SNSs is how they are built around users and users existing social networks. Yet each SNS is isolated so users manage their profiles and build relationships separately on different SNSs. The content for the same user in different SNSs may overlap so it becomes a burden for users to manage contents across different SNSs.

Thus providing a system and method for integrating heterogeneous social network demand of the area is a technical issue need to be solved in the technical field.

To solve the aforementioned technical issue of conventional technologies one objective of the invention is to provide a system and method for integrating the heterogeneous social network.

To achieve the aforementioned objective the present application provides a peer to peer networking method for integrating heterogeneous social networks applied in a server device. The method comprises of the steps listed below. First the server device connects with a plurality peer nodes. Each of the peer nodes defines a user end and accessing at least one social network. Then the server device according to a social relationship of the social networks links the corresponding peer nodes for integrating a peer to peer social network P2P iSN which configures a plurality of social paths among the peer nodes from the different social networks.

To achieve the aforementioned objective the present application provides a peer to peer networking system for integrating heterogeneous social networks. The system comprises of a communication module and a process module. The communication module connects with a plurality peer nodes. Each of the peer nodes defines a user end and accessing at least one social network. The processing module connects with the communication module the processing module according to a social relationship of the social networks links the corresponding peer nodes for integrating a peer to peer social network P2P iSN which configures a plurality of social paths among the peer nodes from the different social networks.

As aforementioned description the system and method of present application integrates the heterogeneous network and generates corresponding social paths which are provide the user connect to his friends by the same social network or different social network in the same time.

To express the technical features contents advantages and effects of the present application to assist examiner in understanding the present application the specification and drawings are expressed in embodiments as followed. The drawings are provided to exemplarily show the present application and may not show the true ratio and arrangement of the present application. The drawings are not intended to limit the scope of the present application with the ratio and arrangement thereof.

A peer node is installed on an end device e.g. PDA smart phone or desktop for a user to access SNSs and connect to server device and its main functionality is to integrate heterogeneous SNSs. The user of a peer node may register to one or more SNSs on his end device and possibly login to one or more SNSs at the same time. Present application uses a unique user ID to associate these different accounts of the same user from heterogeneous SNSs. A unique user ID can be some kind of authenticated information like user s cell phone number or verifiable email address. The index peer node is installed in a server device and responsible for maintaining the communication status i.e. online or off line and the routing information i.e. IP address of each peer node. When a peer node is turned on it reports to the index peer node the online status which comprises of its ID and IP address of the peer node. Upon receiving the online status the index peer node updates the online status for the peer node. If a user a of the peer node na and a user b of the peer node nb are on each other s friend list in a SNS and na and nb are turned on these two online peer nodes can communicate with each other by using the corresponding IP addresses queried from the index peer node. The peer nodes can establish social paths among users from different SNSs and build the so defined global relation ship.

With the peer to peer network architecture P2P iSN allows users from heterogeneous SNSs to communicate without involving any specific SNS and the integration is independent of any specific SNS. In other words the integration does not incur overhead to the SNSs. By applying P2P iSN present application provides a Global Relationship Model to assess the strength of the global relationship between two users from heterogeneous SNSs. Based on the global relationship model present application provides a searching mechanism namely i Search to find the social path between two users from heterogeneous SNSs. Present application also provides an analytical model to evaluate the performance of the i Search mechanism in terms of the path found probability and conduct extensive simulation studies to validate our analytical results.

Present application uses the cell phone number as an example for the unique ID. The phone book in a peer node e.g. Jenny s end device is used as the base to integrate heterogeneous SNSs. Take as an example. Jenny has a friend John with phone number 0910456. 

A database friend list is maintained to store the information about a user s friends. shows the format of a friend list. The friend list comprises three kinds of information personal information social network information and address information.

Personal information field stores the IDs of the user s friends including the ID in SNS phone number and email address. In different SNSs users may use different IDs. As shown in for example Jenny s friend John uses the ID John f on Facebook and use the ID John t on Twitter . The phone number associates the entry in the phone book with the entry in the friend list. An entry in the phone book may be mapped to multiple entries in the friend list.

Social Network Information field comprises four subfields including SN Type T Value Timestamp and Online. The SN Type indicates which SNS the friend has registered. For example in Jenny s friend John registered to Facebook using ID John f. The T Value stores the result calculated by using Eq. 1 in the global relationship model indicating the frequency that a user performs some kind of social activities on his friend e.g. Jenny posts a comment click a Like or send a message on John s wall in Facebook . For example in 1 in the T Value for Jenny John on Facebook is 0.9. The Timestamp field stores the time when the T Value was calculated. The Online indicates that whether the friend is on the SNS now or not and when John logins to the Facebook last time. If the value of Online is On Off the time is when John logins logouts Facebook . For example in FIG. On 12 0215 1430 implies that John f logins Facebook at 14 00 on Feb. 15 2012 and is now on Facebook .

Address Information field stores the IP address and the port number of the friend s end device. This information is valid when the peer node of the friend is turned on.

The FeedRequestListener . is responsible for getting the status of a user s social activities on SNS by invoking the API mAsyncRunner.request me feed newFeedRequestListener . provided by the SNS e.g. Facebook Graph API Twitter REST API other social network API etc. .

The SampleAuthListener . is responsible for authenticating a user when he turns on the peer node and login an SNS. The SampleAuthListener . is implemented by using the API SessionEvents.addAuthListener new SampleAuthListener . provided by the SNS.

The CreateFriendListListener . is responsible for obtaining the IDs of a user s friends in an SNS by invoking the API mAsyncRunner.request me friends new CreateFriendListListener . and maintaining the user s friend list.

The BackgroundService class . is responsible for the message exchange between two peer nodes and between a peer node and an index peer node . The class provides the communication channel among peer nodes for the i Search mechanism. To be more specific a peer node uses this class to request another peer node to execute the i Search mechanism to be elaborated later. The peer node uses this class to inform his online status to the index peer node.

The Peer Agent . is the main class. There are three functions defined in Peer Agent. . including the following functions Update Tvalue . the Update FriendList . and the Relationship Finding .. The Update Tvalue . and the Update FriendList . are used to respectively update the T Value and Online field in the friend list. The Relationship Finding . implements the i Search mechanism to identify the directional social path between two users.

The Phone Book API . is used to fetch a user s phone book friends. Several smart phone operating systems provides such an API for example Android API. It is executed in the login procedure. By using the phone number it can identify two or more accounts of the same user to integrate different SNSs.

An index peer node is a database that maintains the GlobalID list . with the format as shown in . For each online peer node an entry is created in the GlobalID List . for the peer node. Similar to the Friend List . the GlobalID List . comprises three kinds of information Personal Information Social Net work Information and Address Information for an online user.

The Personal information field stores the IDs of a user including the ID in SNS used by the user to login an SNS phone number and email address. Note that a user may turn on a peer node by logging into one or more SNSs concurrently there may be one or more SNS IDs for the same user i.e. multiple entries for the same user exist in the GlobalID List .. These multiple entries are linked using the same phone number or email address of the user. Note that in our implementation we may select only one of the IDs for a user to be stored in the index peer node e.g. the user s phone number so that the IDs for a user can be kept unknown to the index node.

The Social Network Information field stores the SNS Type indicating which SNS the user logins currently i.e. online .

The Address Information field stores the IP address and the port number of the peer node turned on by the user. This information is valid when the peer node is turned on.

When a user turns on the peer node on his end device the Login procedure is executed. illustrates the message flow for the Login procedure with the following steps 

Step 1. When a user turns on the peer node a SampleAuthListener . is created and the SessionEvents.addAuthListener new SampleAuthListener function is exercised to authenticate the user in an SNS.

Step 2. If the authentication is successful the SNS responds with the user SNS ID in the return of theSessionEvents.addAuthListener function.

Step 3. The peer node creates a Background Service . class to send a message i.e. the User Online Message message carrying the user s ID Phone No. Email IP address port number and SN Type to the index peer node . The index peer node creates an entry for the user in the global ID list.

Steps 4 and 5. The peer node creates a CreateFriendListListener . i.e. the FriendList Request andFriendList Response message pair to get the IDs of the user s friends from the SNSs and creates an entry for each friend in the Friend List.

Steps 6 and 7. The peer node uses the BackgroundServiceclass to send a message i.e. theFriends OnlineStatus Request and Friends OnlineSta tus Response message pair to the index peer node to query the online friends of the user.

Steps 8 and 9. The peer node creates a FeedRequestListener . class to collect the social activity information to calculate the T value from the SNS by exchanging the T Value Parameter Request and the T Value Parameter Response message pair.

Present application according to P2P iSN provides the Global Relationship Model to identify the global relationship between two users across heterogeneous SNSs. Present application first provides a tool to measure the global relationship strength between any two users across heterogeneous SNSs. Then present application provides an i Search mechanism to find a meaningful directional social path between two peer nodes in P2P iSN.

Before searching for users global relationships we need a tool to measure the relationship strength between any two users across heterogeneous SNSs. Present application modifies the decay function defined in classical sociology on network relations to come up with more precise measurements on global relationship strength in heterogeneous SNSs.

A directional social link a b is associated with frequency which is denoted by f a b to capture how often a user a performs some kind of social activities with user b e.g. user a posts a comment on user b s wall click a Like send a message or makes user a call to user b . Consider there are C kinds of social activities. For 1 i C let denote the frequency that a user a performs the ith kind of activity with user b. We define f a b by

where wis the weight for the ith kind of activity 0 w 1 for 1 i C and w 1. Note that in Eq. 1 the weight wis a fine tuning tool to reflect different degrees of interactions in a relationship. For example while clicking a Like often carries a more casual connotation sending an email message implies stronger intention to communicate with another user so we can use a larger wto the latter kind of social activity. As for it can be obtained from the measurement in an SNS for a given time period e.g. per month or per day . In the directional social link a b a larger f a b value implies that user a pays more attention to user b. For example assume there is only one kind of social activity i.e. w 1 comment posting. If a user a posts five comments on average per day on b s wall in the SNS i.e. 5 day then f a b w 5 day. We use a threshold to bound f a b . In other words if f a b we say that user a has enough attention on user b.

Present application descripts that an interaction factor exists between user a and user b if a b and b a exist and the value F a b for an interaction factor is defined by

A larger F a b means more interactions between user a and user b and from Eq. 2 we have 0 F a b 1 and F a b F b a .

Consider a social graph formed by heterogeneous SNSs. For example in there are two SNSs in a social graph. Suppose that a directional social path exists from user u in the SNS S1 to user u in the SNS S2 through users u u . . . u where at least one of the L 1 users is a peer node. Denote the directional social path as a set of links P u u u u . . . u u u u . This directional social path comprises of L directional links i.e. the distance between uand uis P L. To convey this directional social path we say that a global relationship exists between uand u. Present application a function Z P to measure the strength of the global relationship between u1 and uL 1 which is defined by

From Eq. 2 we have 0 F u u 1 and F u u F u u for 1 i L. Then 0 Z P 1. Furthermore for the reverse directional path P of P i.e. P u u . . . u u u u we have Z P Z P . A larger Z P implies stronger global relationship. The strength Z P provide more precise friend recommendation and trust reputation metrics and also serve as a basis for content sharing across SNSs.

Present application provides an i Search mechanism to find a directional social path between two peer nodes in P2P iSN. The i Search mechanism establishes social paths link by link. When a link is added into a path global relationship strength is calculated for the new path using the Z . function in Eq. 3 . If the global relationship strength for the new path is below a threshold value the social path search stops. Threshold value is used to guarantee that the global relationship strength for the constructed path is strong enough so that users are motivated to use the global social relationship for further SNS applications.

Present application set up based on the research findings in the sociology i.e. the interaction factor for link a b is F a b 0.5 . Considering a path P with length P 4 then using the Z . function in Eq. 3 the global relationship strength for the path is Z P 0.5 0.0625 which is considered very weak relationship. Therefore in the performance study later we set 0.5 0.125.

In other words it is likely that the social path searched by the i Search mechanism has path length no larger than 3. As long as the interaction factor for link a b is F a b 

Details of the i Search mechanism are given below The index peer node maintains the online status including the ID and IP address of the peer node for the online peer nodes. A friend list is maintained in the peer node which stores the online information for all friends of the peer node. To simplify the description present application uses the friend b of a peer node a to imply that the social link a b exists.

When a peer node is turned on it reports its online status to the index peer node and receives the latest online status for his friends from the index peer node. With the latest online information the peer node can determine whether his friend is online i.e. a peer node is turned on . An online peer node can communicate with his online friends directly. Present application executes a recursive algorithm i Search in the peer node . In this algorithm the set G is the friend list of a peer node. The input parameter s stores the ID of the peer node who calls Algorithm 1 and r is the ID of the peer node to be searched. Initially we set P .

Consider the scenario where the peer node a searches for the peer node d. A user a can request his friend b to execute the i Search algorithm i.e. b.iSearch in Algorithm 1 through the direct communication if b is online. That is the directional social path P is established along the online peer nodes.

Note that the i Search mechanism may find multiple global social relationships between two peer nodes. For the peer node who triggers the i Search mechanism he can use the one with the largest global social relationship strength. Furthermore the system can speed up the execution of the i Search mechanism by caching the searching results on the peer nodes.

All peer nodes and the corresponding social links in P2P iSN form a social graph. A peer node may be turned on or off during the execution of i Search and the i Search request can reach the friends only when the friends are online. In other words a social link a b does not exist if peer node a or b is turned off i.e. off line . Therefore the physical network topology of P2P iSN changes dynamically when the i Search mechanism is being executed.

Let Pbe the path found probability that a directional social path exists when a peer node a executes the i Search mechanism to find a peer node d. The online status of a peer node affects the Psignificantly. In this section present application provides an analytical model to obtain an approximation value for P.

To simplify our discussion we assume that the peer nodes in P2P iSN are independently and identically distributed i.i.d in terms of network behaviors such as online status interactions etc. As discussed earlier in this article we set 0.5 0.125 in the i Search mechanism. In present application analytical model we use the constraint P 3 instead of 0.125 i.e. the i Search mechanism quits when the path length reaches 3 with conclusion that no global social path is found. Assume that a peer node is turned on i.e. online for a time period x with the density function . and mean 1 u and then it is turned off i.e. off line for a time period y with the density function . and mean 1 u . The peer node alternates between x and y. Suppose that i Search request arrivals to a peer node form a Poisson process. The probability pthat an i Search request arrives when a peer node is online can be obtained by

Present application provides the social graph for P2P iSN using the Watts Strogatz model with the three parameters a i.e. there wire probability n i.e. the total number of peer nodes in P2P iSN and m i.e. the average number of friends of a peer node . With the setup 0m ln n 1 5 

The Watts Strogatz model has the small world property including small average path length and high clustering which can also be applied to study SNS.

Let Ndenote the expected number of the peer nodes that receive the i Search request message during the execution of the i Search mechanism. Consider the scenario that the peer node a executes the i Search mechanism to search for a directional social path to d. If d belongs to one of the Npeer nodes then the directional social path from a to d is found. Therefore we have

Present application derives Nas follows. There are two types of nodes including far nodes and near nodes defined in the Watts Strogatz model. The far nodes represents the peer nodes that have social links after rewiring with probability a. The near nodes represents the peer nodes that have social links initially.

In the social graph of the P2P iSN let Nf and Nn respectively be the expected numbers of far nodes and near nodes that receive an i Search request when the i Search mechanism is executed. Then we have N N N

Nand Nare obtained as follows. One round means that the i Search request is delivered using a directional social link a b when both peer nodes a and b are online. In the i Search mechanism there are at most three rounds to construct a directional social path. In each round a peer node that triggers the round can be either a far node or near node 

Case 1 The peer node that triggers the round is a far node. In this case there are on average m pfar nodes and m 1 pnear nodes that can receive the i Search request.

Case 2 The peer node that triggers the round is a near node. Because there is high probability that the near node sends the i Search request to another near node that has received this i Search request previously we consider that only far nodes can receive the i Search request for the approximation. In this case there are on average m pfar nodes that can receive the i Search request.

The analytical model is validated by simulation experiments of a discrete event driven simulation model which has been widely adopted to simulate the mobile communications network in several studies. The simulation model simulates the online off line behavior of a peer node and the behavior of the i Search mechanism.

In the simulation model we adopt the aforementioned discrete event driven approach and define five types of events listed below 

The QUERY ARRIVAL event represents that an online peer node starts the i Search mechanism to find another peer node.

The QUERY FORWARD event represents that an online peer node sends a i Search request to his online friend.

The QUERY RESPONSE event represents that an online peer node returns the results i.e. a path is found for the execution of the i Search algorithm to the peer node who sends the i Search request.

Present application maintains a timestamp tto indicate the time when an event occurs. The events are inserted into an event list and deleted processed from the list in a non decreasing timestamp order. During execution of the simulation a simulation clock tis maintained which indicates the progress of simulation. The following variables are used in the simulation model 

Present application repeats the simulation runs until Cexceeds 100 000 to ensure the stability of the simulation results. Then we obtain the output measure 

In the following we study the effects of the input parameters on the Pperformance for the i Search mechanism. In our study we set the input parameters following the constraints in Eq. 5 and we set the total number of Peer nodes n 1000. The effects of the input parameters are described as follows.

In and we change u ufrom 0.5 to 8. A larger u uimplies that the peer node spends more time online. For example when u u 0.5 and u u 8 from Eq. 4 we have p 1 3 and p 8 9 respectively. Both figures show that the path found probability pincreases as u uincreases. It is worth noticing that we have plarger than 15 percent when u u 8 and 0.8 as shown in with m 6 and pis around 40 percent when u u 8 and m 10 as shown in .

Observing where we set m 6 we study the effects of . A larger implies that the social graph of P2P iSN is sparser i.e. more far nodes . indicates that pincreases as increases which means that in a sparser social graph the i Search mechanism attains better found probability. In we study the effects of m where we set 0.4. A larger m implies more friends of a peer node. shows that with more friends the i Search mechanism achieves better pperformance.

In summary when in a sparser social graph and a peer node has more friends there is 40 percent probability that the i Search mechanism could find a global social relationship for the user i.e. a social path with strong relationship strength.

