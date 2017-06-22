---

title: Server system and control method
abstract: There is provided a method of a server system including identifying a first token and a second token based on an identifier received from a first external information processing apparatus, acquiring data from the first external information processing apparatus with use of the first token, generating a document from the acquired data, transmitting the second token to an authentication processing apparatus, acquiring a verification result of the second token from the authentication processing apparatus, and transmitting the generated document to a second external information processing apparatus with use of the second token.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09185102&OS=09185102&RS=09185102
owner: Canon Kabushiki Kaisha
number: 09185102
owner_city: Tokyo
owner_country: JP
publication_date: 20140214
---
Japanese Patent Application Laid Open No. 2009 251709 discusses a technique in which an image forming apparatus issues a token to a terminal apparatus and the terminal apparatus is authenticated by the image forming apparatus with use of the issued token. Further Japanese Patent Application Laid Open No. 2009 251709 also discusses a technique in which the token is verified by the image forming apparatus.

Now suppose an environment under which data is acquired from a first external information processing apparatus with use of a first token corresponding to an identifier a document is formed from the acquired data and the generated document is transmitted to an authentication processing apparatus with use of a second token corresponding to the same identifier.

However since the above described environment is not assumed in the technique discussed in Japanese Patent Application Laid Open No. 2009 251709 the first token and the second token cannot be identified from the identifier. Therefore obviously this technique cannot achieve both acquisition of the data from the first external information processing apparatus with use of the first token and transmission of the document to the authentication processing apparatus with use of the second token.

The present invention is directed to a technique for identifying a first token and a second token based on an identifier and taking advantages of the tokens by using the identified first token for a first external information processing apparatus and using the identified second token for an authentication processing apparatus.

According to an aspect of the present invention a server system includes a reception unit configured to receive an identifier from a first external information processing apparatus an identification unit configured to identify a first token for acquiring data from the first external information processing apparatus and a second token for acquiring a verification result from an authentication processing apparatus based on the identifier a generation unit configured to acquire data from the first external information processing apparatus with use of the first token to generate a document from the acquired data an acquisition unit configured to acquire the verification result of the second token from the authentication processing apparatus by transmitting the second token to the authentication processing apparatus and a transmission unit configured to transmit the generated document to a second external information processing apparatus with use of the second token.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

How business data is managed and how various kinds of processing are performed on a cloud platform will be now described. A user accesses a web page of the cloud platform from a browser of a client personal computer PC via the Internet and displays business data that the user wants to view on the web page. For example if the user issues a document generation instruction from this screen the user is redirected to a document generation server and the document generation server acquires business data stored in the cloud platform to generate a document and transmits the generated document to the client personal computer PC or the cloud platform. Representative examples of the cloud platform include Salesforce CRM registered trademark provided by Salesforce.com Incorporated.

The cloud platform and the document generation server operate in a multi tenant manner. The tenant is a unit of a company and an organization under a contract to use the cloud platform and the document management server. A service that operates in a multi tenant manner manages data pieces of a plurality of tenants by a single system and manages them while separating the data pieces of the respective tenants from one another in such a manner that data of one tenant cannot be referred to by another tenant. The cloud platform and the document generation server authenticate users to allow the tenants to refer to only their respective own data pieces.

When the cloud platform and the document generation server cooperate with each other authentication can be shared between the servers without requiring a user to be authenticated by the respective servers. One of techniques for sharing authentication among a plurality of servers is a Single Sign On hereinafter referred to as SSO system based on Security Assertion Markup Language SAML . According to the SSO system based on SAML a user has user identifications IDs for both a server that provides an authentication service IdentityProvider hereinafter referred to an IdP and a server that trusts an authentication result of the authentication service to provide a service ServiceProvider hereinafter referred to as an SP . Once the user is authenticated by the IdP the SP trusts this authentication result and authenticates this access as the ID managed within the SP IdP initiated SSO . Further when an unauthenticated user who is not authenticated by the IdP yet accesses the SP the SP guides the unauthenticated user to the appropriate IdP so that the user is authenticated by the IdP SP initiated SSO .

To realize SSO based on SAML the ID owned by the IdP and the ID owned by the SP are managed by associating them with each other hereinafter referred to as user mapping . Especially for cooperative use of a service for which user identification is indispensable and the document generation server IDs should be managed by the user mapping. Examples of services for which user identification is indispensable include a printing service in which documents are managed and printed by IDs.

However the above described method involves the following problems. If an automatic workflow system that can work through the cooperation among a plurality of service provider servers for example nighttime batch printing is realized in the cloud environment the authentication system designed for normal users cannot be used therefor because of nonintervention of a user. Further if account information such as a username and a password is held in both sides of the service provider servers cooperating with each other this leads to the necessity of managing even account information of another service increasing in a security risk such as an illicit identify fraud and an information leak.

Further the respective services in the cloud environment need to operate in a multi tenant manner. Therefore during execution of an automatic workflow based on cooperation among the servers which tenant is running this workflow needs to be identified. Further information for identifying the respective tenants needs to be separated tenant by tenant and be safely managed.

A case will be described where a system is configured in such a manner that service provider servers therein cooperate with each other to carry out a scheduled job and this system carries out a scheduled job that works under a system authority without intervention of a user such as nighttime batch printing. In the following description this example will be described. At this time a method in which cooperation among the servers can be safely realized without holding a username and a password in all servers will be also described below.

In the present exemplary embodiment a World Wide Web WWW system is established via a wide area network WAN . A local area network LAN connects respective constituent elements to one another. A plurality of LANs is connected to one another via the WAN so that respective apparatuses become communicatable to one another.

The client PC is operated by a user and issues a request to the service provider server A and the service provider server B which will be described below with use of the browser . Hereinafter the browser launched on the client PC will be referred to as simply the browser .

Authentication servers A and B authenticate a user respectively and both of them operate as identity provider apparatuses IdPs . The number of authentication services is not limited to two. Which IdP actually authenticates a user varies depending on a user accessing the system. The service provider servers A B and C provide services respectively. They provide services to an authenticated user. The service provider server A receives a request from the client PC and the service provider server B and generates a document. The service provider server B for example displays and updates data held thereby according to a request from the client PC and the service provider server A . The service provider server C receives a request from the client PC and the service provider server A and prints a document. The service provider server A the service provider server B and the service provider server C are not limited to providing the document generation service the cloud platform and the document printing service and the services may be other services. Further the client PC the authentication service determination server the authentication server A the authentication server B the service provider server A the service provider server B and the service provider server C are connected to one another via the WAN network and the LANs respectively. The client PC and the respective servers may be set up in respective individual LANs or may be set up in a same LAN. Further they may be set up in a same PC. The authentication service determination server the authentication server A the service provider server A and the service provider server C belong to a server group established in a same network in an intranet and the authentication server B and the service provider server B belong to a server group established in a same network in an intranet . Further each server may be constituted by a single apparatus or may be constituted by a plurality of apparatuses. The system including one or more apparatuses in this manner is called a server system.

First the client PC accesses the service provider server B to register a scheduled job for batch printing. Upon receiving unauthorized user access the service provider server B displays an authentication screen not illustrated and authenticates the user. Upon authenticating the user the service provider server B displays a scheduled job registration screen for batch printing.

Next the client PC accesses the service provider server A to perform preliminary settings for batch printing. Upon receiving unauthorized user access the service provider server A displays an authentication screen not illustrated and authenticates the user. Upon authenticating the user the service provider server A displays a setting screen for batch printing.

Further the client PC accesses the service provider server B to perform preliminary settings for batch printing. The authentication procedure in the service provider server B is similar to the above described procedure. If the user has been authenticated already the service provider server B displays a secret key registration screen.

The service provider server B starts the scheduled job when the start time of the scheduled job has come and requests batch printing to the service provider server A .

Upon receiving the request for batch printing the service provider server A verifies whether this request is appropriate. If this request is appropriate the service provider server A acquires data from the service provider server B using the server B access token. Then the service provider server A transmits a document generated based on the acquired data to the service provider server C using the server C access token.

Referring to a central processing unit CPU executes a program such as an operating system OS and an application stored in a program read only memory ROM of a ROM or loaded from a hard disk HD to a random access memory RAM . The HD may be a solid state disk SSD . The OS stands for an operating system that runs on a computer. Hereinafter the operating system will be referred to as the OS. Processing of respective flowcharts that will be described below can be realized by executing this program. The RAM functions as for example a main memory or a work memory for the CPU . A keyboard controller KBC controls a key input from a keyboard KB and a pointing device not illustrated . A cathode ray tube CRT controller CRTC controls a display of a CRT display . A disk controller DKC controls data access to the HD a floppy registered trademark disk FD and the like that store various kinds of data. A network card NC is connected to the network and controls communication with another apparatus connected to the network.

In all of the following descriptions the hardware that actually executes the processing is the CPU and the software that actually executes the processing is the application program installed in the HD unless otherwise indicated.

Further the CPU performs the processing based on the program stored in the HD thereby realizing software configurations illustrated in and processes in respective steps in flows that will be described below.

After the service provider server B receives an access the access control module determines whether the user s access has been authenticated already. If the user s access is not authenticated yet the page generation module provides the authentication screen to the browser . If the user s access has been authenticated already the service provider server B provides the service.

The scheduled job registration modules and register a scheduled job. Information regarding a scheduled job such as a job start time is managed by the scheduled job information management modules and .

When a start time of a scheduled job has come the scheduled job execution module or carries out the scheduled job. The batch printing request module or is invoked by the scheduled job execution module or and issues a request for requesting batch printing to the service provider server A . The secret key management module or stores and acquires the secret key so that the service provider server A checks the validity of the batch printing request. Then the authentication information addition module or generates information required for the validity check and adds it to the request.

After the service provider server B receives a request for acquiring business data the business data management module or acquires business data and returns it to an apparatus which has issued the request.

Further the service provider server B manages the scheduled job registration modules and the scheduled job information management modules and the scheduled job execution modules and the batch printing request modules and the secret key management modules and the authentication information addition modules and and the business data management modules and for each tenant. These modules managed for each tenant may be stored in the same HD and may be managed in such a manner that data pieces for the respective tenants are logically separated from one another. Alternatively the modules may be managed while being physically separated from one another in different HDs . Further these modules are one as an entity. The service provider server B provides a tenant ID to the respective modules by which the respective modules perform operations dedicated to this tenant. For example access limitation is imposed on only a data area specific to the tenant. illustrates the modules grouped for each tenant according to this intention.

After the service provider server A receives access the access control module determines whether this access has been authenticated already. If the access has been authenticated already the service provider server A provides the service.

The service provider server A performs batch printing in response to the batch printing request from the service provider server B . Upon receiving the batch printing request the authentication information verification module verifies the received printing request. Information required for the verification is stored in the HD in advance and is managed by the batch printing information management module .

The secret key in the batch printing information stored in the HD in advance is generated by the secret key generation module and is managed while being associated with the tenant ID of the service provider server A . Further the server B access token and the service C access token in the batch printing information are acquired by the access token acquisition module from the service provider server B and the service provider server C respectively. Then they are also managed while being associated with the tenant ID of the service provider server A .

The data acquisition module acquires the business data from the service provider server B with use of the server B access token. The document generation module acquires a form managed by a form management module not illustrated and generates a document from the business data acquired by the data acquisition module and the form. The document transmission module transmits the document generated by the document generation module to the service provider server C with use of the server C access token. The access token verification module determines whether the server B access token and the server C access token have expired and reacquires the tokens if they have expired.

After the service provider server C receives access the access control module determines whether the user s access has been authenticated already. If the user s access has not been authenticated yet the page generation module provides an authentication screen to the browser . If the user s access has been authenticated already the service provider server C provides the service.

The document printing module prints the document transmitted from the service provider server A . The details thereof will be described in a description of step S.

In the following description preparations for performing batch printing will be described with reference to .

In step S the service provider server A receives a request for setting the server C access token. The browser has already completed user authentication to the service provider server A by a login operation before the present flow starts and an authentication session ID of the service provider server C has been already issued by the authentication server A . The authentication session ID of the service provider server C is specified in a Uniform Resource Locator URL parameter AUTH ID by the browser and is contained in the request for requesting setting of the server C access token in the present step S.

In the present exemplary embodiment the present flow is performed assuming that the authentication session ID is added to Cookie AUTH SESSION ID . However the authentication session ID may be added by another method than Cookie.

In step S the service provider server A acquires the authentication session ID of the service provider server C which is contained in the parameter AUTH ID as the URL parameter of the above described request for requesting setting of the server C access token.

In step S the service provider server A invokes an application programming interface API for acquiring an access token which is prepared in the authentication server A while specifying the authentication session ID of the service provider server C acquired in the above described step S as a parameter.

In step S the authentication server A receives the invocation of the API for acquiring the server C access token from the service provider server A . Then in step S the authentication server A issues the server C access token and the server C refresh token. Then the authentication server A returns the issued access token and refresh token to the service provider server A .

In step S the service provider server A receives the server C access token and the server C refresh token as return values of the API.

In step S the service provider server A stores the server C access token and the server C refresh token received in step S into the HD while associating them with the tenant ID of the service provider server A . The tenant ID has been already identified and recognized by the service provider server A at the time of completion of the login before the present flow starts.

In step S the service provider server A returns a storage completion screen which indicates completion of the storage of the server C access token and the server C refresh token to the browser .

Then the present flow which is performed by the browser the service provider server A and the authentication server A ends. The above described flow is a flow for acquiring the access token using the API for issuing an access token which is prepared in the authentication server A but this flow may be realized by any other method that enables the service provider server A to acquire information required for the service provider server A to access the service provider server C .

In step S the service provider server A determines whether the service provider server A could acquire the server C access token and the server C refresh token appropriately in step S. For example the service provider server A may have failed to acquire the access token when the authentication session ID acquired in step S has expired.

If the service provider server A could acquire the access token appropriately YES in step S the processing proceeds to step S. If the service provider server A has failed in acquiring the access token NO in step S the processing proceeds to step S.

If the service provider server A has failed in acquiring the server C access token and the server C refresh token NO in step S in step S the service provider server A returns an error screen that indicates the failure in acquiring the server C access token and the server C refresh token to the browser .

Then the present flow which is performed by the service provider server A regarding acquisition and storage of the server C access token ends.

In step S the service provider server A receives a request for setting the access token of the server provider service B .

In step S the service provider server A instructs the browser to be redirected to the authentication server B . At that time the service provider server A adds a client identifier of a source that requests setting of the access token and a redirection URL to a URL as redirection parameters so that the authentication server B can recognize the source that requests setting of the access token i.e. the service provider server A and a redirection destination after completion of authentication. The client identifier is an identifier indicating that the source that accesses the authentication server B is the service provider server A .

In step S the authentication server B returns a display of a login screen not illustrated to the browser .

In step S the browser displays the login screen returned in step S. The user inputs a user ID and a password of the service provider server B on the login screen displayed on the browser and presses a permission button for authentication.

In response to the user s pressing of the authentication button in step S the browser requests the authentication server B to allow access from the service provider server A to the service provider server B .

In step S the authentication server B receives the authentication request from the browser . In step S the authentication server B instructs the browser to be redirected to the service provider server A . The redirection destination is added to the URL by the service provider server A as the parameter at the time of redirection to the authentication server B in step S. An authentication code is contained in a URL parameter of the redirection to the service provider server A . The authentication code is a token valid for only a short time period to indicate permission for user s access which is used to acquire the access token.

Upon receiving the redirected access in step S the service provider server A transmits a request for acquiring the server B access token to the authentication server B . At that time the service provider server A attaches the authentication code contained in the URL parameter of the redirection as a URL parameter of the request.

In step S the authentication server B receives the request for acquiring the server B access token from the service provider server A . In step S the authentication server B issues the server B access token and the server B refresh token. Then the authentication server B returns these tokens to the service provider server A as a response.

In step S the service provider server A receives the server B access token and the server B refresh token as the response.

In step S the service provider server A stores the server B access token and the server B refresh token received in step S into the HD while associating them with the tenant ID of the service provider server A . The tenant ID has been already identified and recognized by the service provider server A at the time of completion of the login before the present flow starts.

In step S the service provider server A returns a storage completion screen which indicates completion of the storage of the server B access token and the server B refresh token to the browser .

The browser the service provider server A and the authentication server B perform the flow regarding acquisition and storage of the server B access token in the above described manner. The above described flow is a flow for acquiring the access token according to OAuth. However this flow may be realized by any other method that allows the service provider server A to acquire information required for the service provider server A to access the service provider server B .

In step S the service provider server A issues generates a secret key. In the present exemplary embodiment the secret key is a combination of a Universally Unique Identifier UUID generated by the service provider server A and the tenant ID of the service provider server A but may have another content.

In step S the service provider server A stores the secret key issued in step S into the HD while associating it with the tenant ID of the service provider server A . The tenant ID has been already identified and recognized by the service provider server A at the time of completion of the login before the present flow starts. Further once the secret key is stored in step S the secret key is not generated again in step S.

In step S the service provider server A returns the secret key confirmation screen which allows the user to confirm the secret key issued in step S to the browser .

In step S the browser displays the secret key confirmation screen that has been returned in step S. The user writes down or copies the displayed secret key to specify the secret key on the secret key registration screen which will be described below.

In step S the browser accesses the secret key registration screen provided by the service provider server B . The user is authenticated at this time if necessary.

In step S the service provider server B returns the secret key registration screen which allows the user to register the secret key to the browser .

In step S the browser displays the secret key registration screen that has been returned in step S. Then the user inputs the written or copied secret key into the displayed secret key registration screen .

In step S the browser issues a request for registering the secret key to the service provider server B . It is desirable that the communication between the client PC and the service provider server B is encrypted because the secret key is contained as a parameter of a URL of the request. The present exemplary embodiment has been described based on an example of the GET method according to which the secret key is transmitted with use of the parameter of the URL. However obviously the secret key may be transmitted by the POST method.

In step S the service provider server B receives the request for registering the secret key from the browser .

In step S the service provider server B stores the secret key contained in the request received in step S into the HD while associating it with the tenant ID of the service provider server A . The tenant ID has been already stored in the service provider server B in advance with use of a storage screen not illustrated . The tenant ID of the service provider server A and the tenant ID of the service provider server B are associated with each other in a one to one relationship. Further it is desirable that the secret key and the tenant ID of the service provider server A are stored in a different area for each tenant of the service provider server B and managed so as to prevent access from a tenant other than the tenant to be processed. Further a same secret key is used for even different scheduled jobs as long as these jobs correspond to a same tenant ID of the service provider server B .

Then the present flow which is performed by the browser the service provider server A and the service provider server B ends.

Next batch printing which is performed after completion of the preparations described with reference to will be described.

In step S the scheduled job execution module or of the service provider server B starts to carry out the scheduled job. The scheduled job execution module or checks execution start times of all of the scheduled jobs managed by the scheduled job information management module or and starts to carry out a scheduled job the execution start time of which has come. Upon starting to carry out the scheduled job the scheduled job execution module or invokes the batch printing request module or and passes over the subsequent processing thereto.

In step S the batch printing request module or of the service provider server B requests the service provider server A to carry out batch printing. Because the batch printing request is issued as a scheduled job that does not require user s login the system of the service provider server B itself carries out this job actually under the system authority instead of a certain specific user unlike a normal printing request issued after use s login. Therefore the service provider server A which receives the request cannot determine the validity of the batch printing request based on a user and a tenant ID.

In step S the access control module of the service provider server A receives the batch printing request. As described above since information for identifying a user such as an authentication session ID is not contained in the batch printing request therefore the service provider server A verifies whether the service provider server A can accept the batch printing request by steps S to S which will be described below.

In step S the authentication information verification module of the service provider server A transmits a challenge of Digest authentication to the service provider server B .

In step S the access control module of the service provider server B receives the challenge of Digest authentication and provides it to the authentication information addition module or .

In step S the secret key management module or of the service provider server B acquires the secret key stored into the HD in step S. The secret key management module or identifies the tenant ID corresponding to the current scheduled job and acquires the secret key associated with this tenant ID. The secret key management module or provides the acquired secret key to the authentication information addition module or .

In step S the authentication information addition module or of the service provider server B acquires the tenant ID corresponding to the scheduled job.

In step S the authentication information addition module or of the service provider server B generates a response of Digest authentication from the challenge of Digest authentication provided from the access control module in step S the secret key provided from the secret key management module or in step S the tenant ID of the service provider server A acquired in step S and the like.

In step S the authentication information addition module or of the service provider server B transmits the response of Digest authentication generated in step S to the service provider server A . At that time the authentication information addition module or sets the tenant ID of the service provider server A acquired in step S to a URL parameter tenant ID separately from the response of Digest authentication.

In step S the access control module of the service provider server A receives the response of Digest authentication and the URL parameter transmitted from the service provider server B . In this step S the access control module acquires the value of the URL parameter tenant ID to determine which tenant is accessing.

In step S the batch printing information management module of the service provider server A searches the batch printing information stored in the HD using the value of the URL parameter tenant ID received in step S as a key. Then the batch printing information management module identifies and acquires the secret key associated with this tenant ID. After that the batch printing information management module provides the acquired secret key and the tenant ID to the authentication information verification module .

In step S the authentication information verification module of the service provider server A verifies the validity of the response of Digest authentication received in step S. The authentication information verification module connects the username the realm the nonce and the cnonce in the response of Digest authentication the Authorization request header received in step S and the secret key provided in step S by the same method as the method when the authentication information addition module or generated the response and forms a digest from the connected string with use of SHA 256 specified in the algorithm . The authentication information verification module verifies the validity by comparing the value formed as the digest to the value in the response in the response of Digest authentication and determining whether they match each other. If they match each other the authentication information verification module determines that the response of Digest authentication is valid. If the authentication information verification module determines that the response of Digest authentication is valid the processing proceeds to step S illustrated in . If the authentication information verification module determines that the response of Digest authentication is invalid the page generation module of the service provider server A generates an error screen and returns it to the service provider server B . In this case the scheduled job of batch printing is suspended here.

In the processing illustrated in the secret key is used as the identifier for performing Digest authentication as described above. Therefore the processing illustrated in has been described as an example in which the secret key itself is not used for encryption and decryption. However the present exemplary embodiment is not limited thereto and may be configured so as to encrypt and decrypt the response of Digest authentication itself by the secret key.

Through the above described steps the reception of batch printing at the service provider server A is completed.

A flow when the service provider server A carries out the received batch printing which will be performed after the processing in will be described with reference to .

In step S the batch printing information management module of the service provider server A searches the batch printing information stored in the HD using the value in the URL parameter tenant ID received in step S as a key. Then the batch printing information management module identifies and acquires the server B access token associated with this tenant ID.

In step S the batch printing information management module of the service provider server A searches the batch printing information stored in the HD using the value in the URL parameter tenant ID received in step S as a key. Then the batch printing information management module identifies and acquires the server C access token associated with this tenant ID.

In step S the access token verification module of the service provider server A invokes an API for verifying validity of an access token which is prepared in the authentication server A while specifying the server C access token acquired in step S and verifies whether this access token is valid. Document generation in step S which will be described below takes a long time if the acquired data has a large volume for example. Therefore in this step S the access token verification module verifies the validity of the server C access token in advance.

In step S in response to the invocation of the API for verifying validity of an access token the authentication server A verifies whether the specified access token is valid and returns the verification result to the service provider server A . If the acquired verification result indicates that the server C access token is valid the processing proceeds to step S. If the server C access token is not valid i.e. invalid the processing proceeds to step S in . A flow when the access token is not valid will be described separately with reference to .

In step S the data acquisition module of the service provider server A transmits a request query for acquiring business data to the service provider server B . The data acquisition module can acquire the business data by specifying the server B access token acquired in step S to a parameter of a Web service API published by the service provider server B .

In step S the service provider server B transmits the business data to the service provider server A in response to the API request for acquiring the business data.

In step S the document generation module of the service provider server A acquires a form managed by the form management module not illustrated and generates a document from the acquired business data and the acquired form. At that time the document generation module uses the form set on the scheduled job registration screen illustrated in .

Steps and are performed again after the process of step S. Thus the service provider server A reacquires a result of verification of the server C access token. This is because if the processes from step S to step S take a long time the server C access token may be invalidated by the time immediately after step S even if the server C access token had been valid until immediately before step S.

In steps and are performed twice but the present exemplary embodiment may be configured to perform them only once.

In step S the document transmission module of the service provider server A transmits the document generated in step S to the service provider server C . The document transmission module can transmit the document by specifying the server C access token acquired in step S to a parameter of a Web server API published by the service provider server C .

In step S the access control module of the service provider server C receives the document. In step S the document printing module prints this document. The term print here is used to refer to converting the document into a Page Description Language PDL format transmitting the PDL data to a printer and causing the printer to print a document based on the PDL data.

In step S the document transmission module of the service provider server A returns a notification that indicates completion of the document transmission to the browser . In the present flow the service provider server A returns the notification that indicates completion of the document transmission to the browser without waiting for completion of the printing of the document at the service provider server C step S . However the service provider server A may wait for completion of the printing of the document and return a notification that indicates the completion of the printing to the browser .

In step S the browser receives the notification that indicates completion of the document transmission returned in step S.

Then the present flow which is performed by the service provider server A the service provider server C the service provider server B and the authentication server A ends.

Step S indicates a process for verifying the validity of the server C access token. In the following description the process performed in step S will be described.

In step S the access token verification module of the service provider server A determines whether the server C access token is valid based on the result of the verification of the validity of the server C access token returned from the authentication server A in step S.

If the server C access token is valid YES in step S the processing proceeds to step S. If the server C access token is not valid NO in step S the processing proceeds to step S. As described with reference to the service provider server A performs the process of step S for verifying the validity of the server C access token twice. Therefore if the access token verification module determines that the server C access token is valid in step S in step S performed after step S the processing proceeds to step S.

In step S the batch printing information management module of the service provider server A identifies and acquires the server C refresh token stored in step S illustrated in . The batch printing information management module searches the batch printing information in the HD using the value of the URL parameter tenant ID received in step S as a key to identify the server C refresh token associated with this tenant ID.

In step S the access token acquisition module of the service provider server A invokes an API for reacquiring the server C access token which is prepared in the authentication server A . At that time the access token acquisition module of the service provider server A specifies the server C refresh token acquired in step S as a parameter when invoking the API. In response to the invocation of the API the authentication server A verifies the refresh token. If the refresh token is valid the authentication server A reissues the server C access token and returns this token to the service provider server A as a return value of the API.

In step S the service provider server A determines whether the service provider server A has succeeded in reacquisition of the server C access token in step S. As a result of the determination if the service provider server A has succeeded in reacquisition of the server C access token YES in step S the processing proceeds to step S. If the service provider server A has not succeeded in reacquisition of the server C access token NO in step S the processing proceeds to step S. Then the processing is suspended.

In step S the batch printing information management module of the service provider server A stores the server C access token reacquired from the authentication server A in step S into the HD again while associating it with the tenant ID of the service provider server A .

Next step S in which is a subsequent step to step S will be described. In step S the data acquisition module of the service provider server A determines whether the data acquisition module has succeeded in acquisition of the business data in step S. If the data acquisition module has succeeded in acquisition of the business data YES in step S the processing proceeds to step S. If the data acquisition module has failed in acquisition of the business data NO in step S the processing proceeds to step S. The data acquisition module may fail in acquisition of the business data when the access token has expired or there is some problem with the query for acquiring the data.

In step S the data acquisition module of the service provider server A analyzes an error that is issued from the service provider server B in the case of a failure in acquisition of the business data and determines whether this error is an error due to expiration of the server B access token. If the error is an error due to expiration of the server B access token YES in step S the processing proceeds to step S. If not NO in step S the data acquisition module determines that the data acquisition module cannot acquire the business data for some reason for example a non existent table is specified in the query . Then in step S the flow is suspended.

In step S the batch printing information management module of the service provider server A identifies and acquires the server B refresh token stored in step S illustrated in . The batch printing information management module searches the batch printing information in the HD using the value of the URL parameter tenant ID received in step S as a key to identify the server B refresh token associated with this tenant ID.

In step S the access token acquisition module of the service provider server A transmits a request for reacquiring the server B access token to the authentication server B . At that time the access token acquisition module of the service provider server A attaches the refresh token acquired in step S as a URL parameter of the request. Upon receiving the request the authentication server B verifies the refresh token. If the refresh token is valid the authentication server B reissues the server B access token adds this token to a response and returns the response to the service provider server A .

In step S the batch printing information management module of the service provider server A stores the server B access token reacquired from the authentication server B in step S into the HD again while associating it with the tenant ID of the service provider server A .

Next a second exemplary embodiment of the present invention will be described with reference to the drawing. Descriptions of similar portions to the first exemplary embodiment will be omitted. In the following description only differences from the first exemplary embodiment will be described.

According to the second exemplary embodiment even when there are both a batch printing request issued from the service provider server B and a normal printing request issued from the browser by a user s operation it is possible to respond to both of the requests without changing the configuration of the service provider server A .

This processing is by supplying software a program capable of realizing the functions of the above described exemplary embodiments to a system or an apparatus via a network or various kinds of storage media and causing a computer or for example a CPU or a micro processing unit MPU of the system or the apparatus to read out this program to execute it.

According to the present invention it is possible to identify the first token and the second token based on the identifier and to take advantage of the tokens by using the identified first token for the first external information processing apparatus and using the identified second token for the authentication processing apparatus.

Embodiments of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions recorded on a storage medium e.g. non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s of the present invention and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more of a central processing unit CPU micro processing unit MPU or other circuitry and may include a network of separate computers or separate computer processors. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2013 027837 filed Feb. 15 2013 which is hereby incorporated by reference herein in its entirety.

