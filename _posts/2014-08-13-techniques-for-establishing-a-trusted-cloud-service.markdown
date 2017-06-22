---

title: Techniques for establishing a trusted cloud service
abstract: Techniques for establishing a trusted cloud service are provided. Packages are created for services that include certificates, configuration information, trust information, and images for deploying instances of the services. The packages can be used to deploy the services in trusted environments and authenticated to deploy in sub environments of un-trusted environments. The sub environments are trusted by the trusted environments. Also, clouds are prospected for purposes of identifying desirable clouds and creating the packages for deployment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09369494&OS=09369494&RS=09369494
owner: Novell, Inc.
number: 09369494
owner_city: Provo
owner_country: US
publication_date: 20140813
---
This application is a divisional of U.S. patent application Ser. No. 13 100 937 filed on May 4 2011 now issued as U.S. Pat. No. 8 813 192 which is incorporated herein by reference in its entirety.

Cloud computing is rapidly changing the Internet into a collection of clouds which provide a variety of computing resources storage resources and in the future a variety of resources that are currently unimagined.

Yet frequently it is difficult to effectively provide a given service from a single environment. This is so because a product or service offering often requires the cooperation of multiple services in providing functionality sufficient to be considered holistic.

Historically service offerings deployed in an enterprise data center could be sufficiently controlled to ensure that trust relationships between the cooperating services were maintained. However as seen in recent years many service offering deployments grow to include multiple heterogeneous environments which span multiple network segments data center locations and or include both data center inside the firewall and cloud un protected by firewall environments. Such data center cloud deployment environments are unsuitable for many service offerings hampering the desired flexibility of the Information Technology IT department in providing low cost services to the enterprise.

That is it is cost ineffective and impractical to think a given service can in all cases be wholly contained with all the supporting services it needs within a single cloud environment and yet the trend in the industry is to outsource services and data to cloud environments.

Various embodiments of the invention provide techniques for establishing a trusted cloud service. Specifically and in one embodiment a method for deploying services to an ad hoc environment from a trusted environment where the ad hoc environment is un trusted is presented.

An environment specification for a target environment is obtained that is un trusted the environment specification obtained within a trusted environment. Next a package is created to include certificates a service image for a migrating service that is migrating to the target environment a service identifier for the migrating service and a package identifier for the package. Then trust configuration information is established for the target environment having a trust configuration identifier. The trust configuration information is included in the package and the package is sent to a target service in the target environment for deployment of an instance of the migrating service via the service image within a created sub environment of the target environment that establishes trust with the trusted environment by processing components of the package.

A resource includes a user service system device directory data store groups of users combinations and or collections of these things etc. A principal is a specific type of resource such as an automated service or user that acquires an identity. A designation as to what is a resource and what is a principal can change depending upon the context of any given network transaction. Thus if one resource attempts to access another resource the actor of the transaction may be viewed as a principal.

An identity is something that is formulated from one or more identifiers and secrets that provide a statement of roles and or permissions that the identity has in relation to resources. An identifier is information which may be private and permits an identity to be formed and some portions of an identifier may be public information such as a user identifier name etc. Some examples of identifiers include social security number SSN user identifier and password pair account number retina scan fingerprint face scan etc.

A processing environment defines a set of cooperating computing resources such as machines processor and memory enabled devices storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X can be logically combined with another computing resource at network site Y to form a logical processing environment.

The phrases processing environment cloud processing environment and the term cloud may be used interchangeably and synonymously herein.

Moreover it is noted that a cloud refers to a logical and or physical processing environment as discussed above.

Various embodiments of this invention can be implemented in existing network architectures. For example in some embodiments the techniques presented herein are implemented in whole or in part in the Novell operating system products directory based products cloud computing based products workload management products and other products distributed by Novell Inc.

Also the techniques presented herein are implemented in machines such as processor or processor enabled devices. These machines are configured to specifically perform the processing of the methods and systems presented herein. Moreover the methods and systems are implemented and reside within a non transitory computer readable storage media or machine readable storage medium and are processed on the machines configured to perform the methods.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms devices operating and server systems and or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit aspects of the invention.

As will be demonstrated in greater detail herein and below the techniques provide mechanisms by which a service deployed in an ad hoc environment can initiate other services where a trust relationship between the initiator and the service is established. The mechanisms can also be used to establish the secure communication channels in preparation for other trusted services to be deployed in the same ad hoc environment.

The embodiments are broken into three primary areas 1 deploying to an ad hoc environment from a trusted environment where the ad hoc environment is un trusted 2 deploying to an ad hoc environment from a trusted environment where the ad hoc environment is also trusted and 3 finding a new un trusted ad hoc environment via client prospecting analysis and deploying to that new un trusted ad hoc environment .

It is within this context that embodiments of the invention are now discussed within the context of the .

The components of the are implemented in non transitory and processor readable storage medium and are executed on physical processors on one or more networks. Each processor specifically configured to execute the components.

The embodiments herein proceed as follows where the Provider Trusted Environment is deploying to an un trusted Endpoint Environment .

Manage Endpoints is used to maintain an Endpoint Specification where the Endpoint Specification specifies the information concerning the Endpoint Environment . The Manage Endpoints then invokes Create Package .

Create Package utilizes the Endpoint Specification the Public Certificates of the Provider Trusted Environment the Process Images and the EPID where the Public Certificates contains the public key certificates used by the Provider Trusted Environment to encrypt information that can only be decrypted by the associated private key owned by The Provider Trusted Environment where the Process Images contains the process images to be delivered to the Endpoint Environment which will commence the establishment of a trusted environment and finish with a fully deployed trusted environment where the Trust configuration contains previously defined Trust Configuration information which provides the Create Package with information necessary to properly construct Package and where the Trust Configuration is annotated by the Create Package concerning the FinalID used to secure the new Endpoint Trusted Environment . In an embodiment the Trust Configuration is also annotated with the EPID Ephemeral Package Identifier and ESID Ephemeral Service Identifier .

The final result of the Create Package is the creation of the Package which contains a package of information usable by the Endpoint Environment to build the Endpoint Trusted Environment .

The Create Package invokes Deliver Trust Boot which consumes the information from the Endpoint Specification to determine how to deliver the notification that the Package is available. The Deliver Trust Boot creates Trust Information which contains the full information of the trust content to be delivered as the Trust Boot . The value of EPID which is to be used to secure the Package for the creation of the Endpoint Trusted Environment is also contained within the notification to the Receive Trust Boot .

The Receive Trust Boot receives the notification from the Trust Boot along with the contents of the notification from the Trust Information and invokes the Authorized Trust Boot . The Authorize Trust Boot is a process which requires a trusted authority to authorize the creation of the Endpoint Trusted Environment and to specify the Environment Location . The Authorize Trust Boot creates Trust Information as a part of the authorization step and then invokes the Receive Package .

Part of the information delivered via the Deliver Trust Boot to the Receive Trust Boot is the location where the Receive Package is to retrieve the Package from the Provide Package using the EPID as proof of trust. In an embodiment the Provide Package receives the address of the Receive Package from the Authorize Trust Boot dataflow not shown in the and the Package is delivered along with the ESID . In either embodiment the resultant Package is provided and if necessary is decrypted according to the information received in the Trust Information .

At this point a trusted authority has authorized the deployment of the Package from the Provider Trusted Environment into an environment specified in the Environment Location .

The Deployed Package deploys the various processes contained in the Package utilizing the information in the Trust Information and the Environment Location to begin creating the Endpoint Trusted Environment .

The beginning of the creation of the Endpoint Trusted Environment is the deployment and instantiation by the Deployed Package of the Set up Trust Environment and the creation of the Configuration File . The Configuration File contains information received from the Provider Trusted Environment via either the Trust Information or the Package .

The Setup Trust Environment is a process instantiated within the Endpoint Trusted Environment which was received by the Endpoint Environment from the Provider Trusted Environment . Thus the process has been retrieved from the Provider Trusted Environment . The Provider Trusted Environment configures itself according to the information in the Configuration File and instantiates another process provided by the Configuration File called Gen Local Keys Certs . The Gen Local Keys Certs constitutes the public and private keys and associated certificates used to establish the Endpoint Trusted Environment . It is critical that the keys and certificates in the Local Keys Certs be generated at the endpoint to provide both an Endpoint Trusted Environment and to secure the information in the Endpoint Trusted Environment even from the Provider Trusted Environment .

The Setup Trust Environment now instantiates the Establish Trust which using the Configuration File communicates with the Establish Trust via an address provided by the Establish Trust and proves that the environment being created at the Endpoint Trusted Environment is authentic by establishing trust credentials using the ESID which was delivered as part of either the Receive Trust Boot or the Package .

The Establish Trust creates the Trust Definition from the information delivered via the Receive Trust Boot and the Package and augments the Trust Definition with information received from the Establish Trust as a result of the successful trust establishment because of the utilization of the correct ESID Ephemeral Service Identifier as well as receiving the FinalID which becomes the permanent identifier for the trusted communication path between the Provider Trusted Environment and the Endpoint Environment . Part of the establishment of this trust is the delivery of the FinalID from the Establish Trust to the Establish Trust which is key and certificate information used in communicating with the Provider Trusted Environment . The FinalID is communicated to the Establish Trust and saved in the Trust Definition only if the correct information is exchanged between the Public Certificates and the Establish Trust utilizing either encryption and or digital signature technology which uses the FinalID and other certificates and or keys as the active crypto material.

If the trust is established the Establish Trust invokes the Production Images which utilizes the Trust Information the Endpoint Speciation and process images in the Production Image Library to provide the Production Processes . The Trust Definition utilizes the Private Keys or crypto material associated with the Private Keys with the Public Certificates as appropriate.

The end result is the secure and trusted transmission of the Production Processes which is utilized by the Deployed Processes together with the Trust Definition and the Production Processes to deploy the final Endpoint Trusted Environment as shown by the cascaded process bubbles in the . In an embodiment the appropriate public key certificates are exchanged between the Establish Trust and the Establish Trust and stored as an annotation in the Trust Configuration dataflow not shown in the .

In an embodiment the Setup Trust Environment the Deliver Trust Boot the Configuration File and the Establish Trust are no longer used when the Endpoint Trusted Environment is restarted or re instantiated because the information has already been exchanged trust established and the appropriate key information provided.

The end result of the above invention mechanisms is the creation of the Endpoint Trusted Environment where the processes within the environment can be trusted by the Provider Trusted Environment as can any traffic communicated between the production processes instantiated at identified in the as the cascading bubbles .

According to the the embodiment provides for mechanisms to create an Endpoint Trusted Environment within an already trusted environment known by the Provider Trusted Environment . In an embodiment the Provider Trusted Environment and the Endpoint Trusted Environment may even be in the same physical location or owned by a same cloud provider. The embodiment operates whether the Provider Trusted Environment and the Endpoint Trusted Environment are in the same location or different locations the only requirement being that network conductivity between the two environments is provided.

The process proceeds the same as discussed above with reference to the except that the authorization of the Trust Boot and is not required because the two environments already trust each other.

In an embodiment the local keys and certificates are generated in the Endpoint Trusted Environment via the Gen Local Keys Certs and stored in the Local Keys Certs . In another embodiment those keys are created in the Gen Local Keys Certs and stored the Local Keys Certs and are provided as part of the exchange between the Establish Trust and the Establish Trust . These two embodiments are possible because the Provider Trusted Environment and the Endpoint Trusted Environment are already in a trusted environment and it is immaterial whether the local keys and certificates are generated in the Provider Trusted Environment or the Endpoint Trusted Environment . In an embodiment the customer of the cloud provider that will be using the Endpoint Trusted Environment may want to be sure that the keys generated by Gen Local Keys Certs are generated in the environment where the trusted processing is taking place. Thus there are two embodiments where keys and certificates can be generated either in the Provider Trusted Environment or the Endpoint Trusted Environment .

The depicts novel mechanisms which allow for the discovery and creation of ad hoc processing locations which are on trusted environments as in the . The purpose is the discovery of new and previously unknown Cloud Providers and that can be used to create trusted environments. Note that while only two clouds are shown e.g. and that the actual number of clouds operable can be from one to many. Of course zero clouds may be qualified which would not involve any useful creation of a trusted environment.

The material in the utilizes the Cloud Monitor and the . . . between 410 and 415 indicate that from one to many such Cloud Monitors may be in use .

The Cloud Monitors and produce the Cloud Metrics and . These captured metrics provide information concerning relevant processing network bandwidth file access etc. at the clouds being monitored.

Likewise Cloud Services and known to the prospecting service depicted in the are sending Service Metrics and which provide information concerning relevant processing network bandwidth file access etc. at the various locations where the cloud services are operable.

Cloud Measurement analyzes the information in the Cloud Metrics and and the Service Metrics and to produce the Cloud Sites Cloud Costs Cloud Performance and Cloud Reputation which is aggregated information concerning Cloud Sites Cloud Costs Cloud Performance and Cloud Reputation. In an embodiment the Cloud Reputation also provides information concerning cloud reputations as gathered the Cloud Reputation from sources external to the embodiments discussed herein.

The Cloud Analysis utilizes the information in Environment Requirements to analyze the content of the Cloud Sites Cloud Costs Cloud Performance and Cloud Reputation in response to a query or interaction with Environment Management . The results of this analysis is the recommendation to the Environment Construction which utilizes the Environment Requirements the Environment Components to create the Environment Packages which are specific packages that can be used according to the to create a new trusted environment at the cloud site recommended by the Cloud Analysis .

The Environment Deployment utilizes the Environment Packages to create the various Cloud Package and and then instantiates the Cloud Agents and which are specific agents that operate within the application programming interface of the Cloud Provider and to deploy the Cloud package and . This is according to the discussion presented above with respect to the .

In an embodiment the various certificates keys configurations images specifications and information may be stored in and provided by Configuration Management Database CMDB such as an Information Technology Infrastructure Library ITIL CMDB.

Some of the keys and certificates may be specified for signature only while other keys and certificates are specified for encryption only. Moreover utilization of asymmetric keys in conjunction with symmetric keys in order to encrypt information can be used. Embodiments herein utilize these technologies in ways that are appropriate.

At the ad hoc and un trusted service deployer obtains an environment specification for a target environment. The target environment is un trusted and the environment specification is obtained within a trusted environment.

At the ad hoc and un trusted service deployer creates a package data structure to include certificates a service image for a migrating service that is migrating to the target environment a service identifier for the migrating service and a package identifier for the package.

At the ad hoc and un trusted service deployer establishes trust configuration information for the target environment that has a trust configuration identifier. Details of the trust configuration information were provided above with reference to the .

According to an embodiment at the ad hoc and un trusted service deployer identifies certificates as public key certificates for keys used by the trusted environment to encrypt information that can only be decrypted by an associated private key which is owned and controlled by the trusted environment. In other words keys are provided for verification and encryption to the un trusted environment via the package so secure communications can be achieved with the instance of the migrating service once it is deployed in the un trusted target environment.

At the ad hoc and un trusted service deployer includes the trust configuration information in the package.

At the ad hoc and un trusted service deployer sends the package to a target service in the target environment for deployment of an instance of the migrating service via the service image within a created sub environment of the target environment that establishes trust with the trusted environment by processing components of the package. The components of the package are processed in the manner discussed above with respect to the and the Endpoint Environment target un trusted environment . Essentially the un trusted environment has a sub environment carved out of it by processing the package and that sub environment is where the instance of the migrating service is deployed. The sub environment is trusted by the trusted environment.

According to an embodiment at the ad hoc and un trusted service deployer authenticates the trusted service of the package via information received back from the target service and acquired from the trusted service from the package. The details of this authentication mechanism were presented above with reference to the .

Continuing with the embodiment of and at the ad hoc and un trusted service deployer provides the trusted service a setup trust service for use in establishing the sub environment.

Still continuing with the embodiment of and at the ad hoc and un trusted service deployer receives a request from a sub environment service created with the sub environment to establish trust with the trusted environment.

Also continuing with the embodiment of and at the ad hoc and un trusted service deployer authenticates the sub environment as being trusted with the trusted environment based on interactions with the sub environment service.

Continuing with the embodiment of and at the ad hoc and un trusted service deployer interacts with the instance of the migrating service within the trusted environment. The instance of the migrating service processes in the trusted sub environment of the target environment.

Finally continuing with the embodiment of and at the ad hoc and un trusted service deployer uses the service identifier of the instance of the migrating service and a trusted sub environment identifier of the trusted sub environment when interacting.

The processing of the and the ad hoc and un trusted service deployer demonstrate how a trusted environment can package one or more services together for deployment in an un trusted environment by creating and authenticating a trusted sub environment from which interaction with the one or more service can occur with the trusted environment.

At the ad hoc and trusted service deployer obtains an environment specification for a trusted target environment. The environment specification is obtained within an initiating trusted environment.

According to an embodiment at the ad hoc and trusted service deployer recognizes the initiating trusted environment and the target trusted environment are in the same physical location or in clouds owned by a same cloud provider.

In an embodiment at the ad hoc and trusted service deployer recognizes the initiating trusted environment and the target trusted environment are in different physical locations or in clouds owned by different cloud providers.

At the ad hoc and trusted service deployer creates a package to include certificate keys a service image for a migrating service that is migrating to the trusted target environment a service identifier for the migrating service and a package identifier for the package.

In an embodiment at the ad hoc and trusted service deployer generates the certificates and the keys within the initiating trusted environment.

Alternatively in another case at the ad hoc and trusted service deployer receives the certificates and the keys from the trusted target environment.

Because both of the environments are trusted the certificates and keys can be generated in either environment unlike the scenario of the where initially the certificates and the keys are generated from the trusted environment.

At the ad hoc and trusted service deployer establishes trust configuration information for the trusted target environment for the trusted target environment having a trust configuration identifier.

At the ad hoc and trusted service deployer includes the trust configuration information in the package.

At the ad hoc and trusted service deployer sends the package to a target service in the trusted target environment for deployment of an instance of the migrating service via the service image within the trusted target environment by processing the components of the package as discussed above with reference to the .

According to an embodiment at the ad hoc and trusted service deployer receives notice from the trusted target environment that the instance of the migrating service is deployed for interacting with the initiating trusted environment.

In still another case at the ad hoc and trusted service deployer receives interaction from the instance of the migrating service by one or more other services within the initiating target environment.

It is now seen via the discussion of the and the processing of the ad hoc and trusted service deployer that two trusted environments can deploy services between them for purposes of establishing trust between the services.

At the un trusted ad hoc environment prospector gathers cloud metrics from a plurality of first clouds.

According to an embodiment at the un trusted ad hoc environment prospector collects the cloud metrics as processing information network bandwidth and file access information for each of the first clouds.

At the un trusted ad hoc environment prospector obtains service metrics from a plurality of first services that processes in the first clouds.

According to an embodiment at the un trusted ad hoc environment prospector collects the service metrics as processing information network bandwidth and file access information for each of the first services.

At the un trusted ad hoc environment prospector analyzes the cloud metrics and the service metrics to produce cloud cost metrics cloud performance metrics and cloud reputation metrics.

In an embodiment at the un trusted ad hoc environment prospector collects the cloud reputation metrics from an external source providing reputation information.

At the un trusted ad hoc environment prospector uses environment requirements for the first clouds and the cloud cost metrics cloud performance metrics and cloud reputation metrics to produce a cloud package agent for the target cloud selected from the first clouds. The cloud package includes a cloud agent that is deployed to the target cloud and that permits the target cloud to establish trust with other trusted environments.

According to an embodiment at the un trusted ad hoc environment prospector includes in the cloud package certificates keys and trust information in the cloud package along with an image for installing an instance of the cloud agent.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

