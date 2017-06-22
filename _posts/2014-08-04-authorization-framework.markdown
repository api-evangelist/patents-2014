---

title: Authorization framework
abstract: Embodiments disclosed herein provide an authorization framework. An apparatus may include a data storage to store a first plurality of authorization plugin modules and a server coupled to the data storage. The server may receive a request to access a resource, identify a second plurality of authorization plugin modules that is a proper subset of the first plurality of authorization plugin modules, execute each of the second plurality of authorization plugin modules to generate a plurality of authorization decisions and determine whether to grant the request in view of plurality of authorization decisions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09369472&OS=09369472&RS=09369472
owner: Red Hat, Inc.
number: 09369472
owner_city: Raleigh
owner_country: US
publication_date: 20140804
---
This application is a continuation of U.S. patent application Ser. No. 11 761 175 filed on Jun. 11 2007 and hereby incorporated by reference in its entirety.

The present invention relates to computer security and more particularly it relates to controlling access to resources of a computer system.

Java has a security architecture that is intended to protect systems from malicious code. In particular the Java security system includes an authentication subsystem and an authorization subsystem which is known as the Java Authentication Authorization Service JAAS . The JAAS authorization scheme is designed to ensure that only authorized code are granted access to the resources of a computer.

JAAS uses a security model that is code centric or user centric in combination with a policy file. In particular JAAS primarily evaluates whether the code being executed can be trusted or whether the user of the code can be trusted. The policies for evaluating the level of trust to be granted to the code or user is then specified by the policy file.

However this security model may not be enough for many enterprise applications. For example an enterprise may want to use custom security repositories such as LDAP lightweight directory access protocol a database or another file system. Typically this sort of custom security logic is implemented by writing customized modules or policy files that interface into JAAS.

Unfortunately such modification of JAAS requires a good understanding of the modules and processes involved in JAAS. Although JAAS allows for customization of authorization and policies implemented this customization requires a significant amount of coding to create proper classes and take care of both the configuration and policy files.

Accordingly it would be desirable to provide an authorization framework that is easily configured to accommodate a custom security repository. It would also be desirable to provide an authorization framework that can allow access control mechanisms to be added or changed as needed.

The present invention is an authorization framework that can accept one or more pluggable authorization modules and determines an authorization decision based on the decisions of these pluggable authorization modules. The authorization decision is a collective decision which is based on a configurable criteria or policy. Each pluggable authorization module can be configured and or developed to perform its own authorization decision making process independent of the processes used by the other pluggable authorization modules 

The concept of the present invention is to allow for a plugin architecture so that multiple decisions can be made weighted and combined into a final decision by the authorization framework. This architecture allows a computer system to dynamically add new authorizations more easily than is possible with known authorization systems such as JAAS.

JAAS essentially takes a monolithic approach to authorization. That is JAAS performs authorization using the concept of least privilege. Under least privilege authorization is based on the intersection of privileges granted to a user or code. As a result the least amount of privilege granted is the determining factor for JAAS authorization. Deviating from this approach requires special method calls or custom policies. This approach by JAAS is difficult to customize and requires a significant amount of code.

For example if a user of an application is supposed to have rights to resource A which implies rights to resources B C etc. then under JAAS this is declared as permissions in the Java code which a call to the JAAS service. However suppose at a later time after the code for the application has been deployed the same user should now be given rights to another resource D. In known Java and JAAS this new permission must typically be added to the code as a new permission or the code must be modified which is a tedious process subject to error and the like.

In contrast the authorization framework of the present invention could simply incorporate a new that evaluates the condition and permits the new authorization to resource D without having to modify the existing code base. Instead a plugin would merely have to be created and interfaced to the authorization framework for this new permission. In essence an abstraction or indirection mechanism has been provided to allow for authorization decisions to be made.

In some embodiments the plugin modules can be written according to a standardized adapter or application programming interface API without having to understand or know the details of the authorization framework. A new plugin could be declared to the authorization framework in various ways such as a change to configuration file referenced by the authorization framework.

Reference will now be made in detail to the exemplary embodiments of the invention which are illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts. In an overall system in which the present invention may be implemented is illustrated. is then provided to illustrate an exemplary application server in which the present invention may be implemented. illustrates an exemplary software architecture for the authorization framework of the present invention. Finally is provided to illustrate an authorization process flow in accordance with the principles of the present invention. These figures will now be described below.

Client may be any computer system that utilizes the services of another computer system i.e. web server and application server . As shown in client may be implemented using components well known to those skilled in the art such as a personal computer laptop computer personal digital assistant a mobile phone and the like. In the embodiments shown in client may be used to run Web applications via an application such as web browser.

Web server is computer system that accepts requests from clients such as client and serving responses along with optional data contents. In the embodiment shown this content served by web server is usually one or more Web pages that includes hypertext markup language HTML documents and linked objects images video audio etc. .

Web server may be implemented on a machine that comprises well known hardware and software. Well known software for web server may be software such as Apache HTTP Server from the Apache Software Foundation Internet Information Services by Microsoft Corporation and Sun Java System Web Server from Sun Microsystems Inc. One skilled in the art will recognize that any of the many different Web server programs available are consistent with the principles of the present invention.

Application server is software that provides applications to client . Application server may be configured to handle security business logic data access for the applications provided to the client . Application server may provide a variety of Web based applications such as e commerce applications content management applications customer relations management applications and the like.

Application server may be implemented on various software platforms. For example application server may be implemented on the well known J2EE platform from Sun Microsystems Inc. In addition application server may comprise middleware to enable applications to intercommunicate with dependent applications like web server database management systems etc.

Application server may be implemented using well known software. For example application server may be implemented using software such WebLogic server from BEA Systems Inc. JBoss from Red Hat Inc. Websphere from the IBM Corporation and the like.

Accordingly application server may implement the Java programming language and provide Web modules using servlets and JavaServer pages. Other functions of application server may also employ Java. For example business logic provided by application server may be built into Enterprise JavaBeans EJBs . J2EE provides standards for containing the Web components. Security services such as authentication and authorization may be implemented using Pluggable Authentication Modules PAM and the authorization framework of the present invention.

Authentication is the process of determining the identity of a user. The Java platform provides APIs that enable an application to perform user authentication via pluggable login modules available via PAM. For example applications provided by application server may call into a login class which in turn references a configuration in application server . The configuration specifies which login module is to be used to perform the actual authentication.

The authorization framework protects access to sensitive resources for example files in data storage or sensitive application code. All access control decisions are mediated by the authorization framework. The authorization framework of the present invention will be further described below.

Data storage refers to the infrastructure of components that store resources of system . For example data storage may comprise devices such as hard disks optical drives disk array controllers tape libraries and servers.

Network represents the communications infrastructure for allowing client and web server to communicate with each other. For example network may represent the Internet which is a worldwide publicly accessible network that uses the Internet Protocol IP suite of standards.

Network represents the communications infrastructure that allows web server application server and data storage to communicate with each other. Network may be implemented as a local area network or may utilize one or more larger networks such as the Internet.

Code represents the code that application server is running for web server . For example code may be a container which is a data structure whose instances are collections of other objects. As a container code can be used to store objects in an organized way following specific access rules. In addition code may implement various methods to perform its functions 

For example code may be an Enterprise Java Bean EJB . An EJB is a managed server sided component for modular construction of enterprise applications provided by application server for web server . EJBs are structured according to the well known Java APIs. EJB encapsulates the business logic of an application and as a result may require authorization services to access to sensitive resources. Of course code may represent any code that requests access to a sensitive resource via the authorization framework of the present invention.

Security interceptor is the part of code that calls for services of the authorization framework . Accordingly security interceptor is where security is enforced in code .

Authorization framework provides authorization services to application server . Authorization is the process of protecting the resources of system by only allowing those resources to be used by users that have been granted authority to use them. Resources may be individual files or data in data storage computer programs other devices or the functionality of other applications. Of note users of authorization framework may be any entity that requires access to resources of system . As such computer programs and other devices on the computer may be users of authorization framework .

In some embodiments authorization framework may have a stack of configurable authorization modules implemented by plugins . In addition these modules can implement extensible access control markup language XACML Java authorization contract for containers JACC a custom policy etc.

Authorization framework provides a reusable design that readily accessible via APIs and may include support programs code libraries a scripting language or other software to help develop and glue together the different components of an application being provided by application server . As noted various parts of authorization framework may be exposed through an API. For example authorization framework may provide APIs for authorization plugin modules and for a policy such as a policy retrieved from a policy database .

Configuration may be a file that configures the settings of the authorization framework . In some embodiments configuration may be edited as needed to allow authorization framework to adapt its authorization services. Hence configuration may be a file written in ASCII or a simple database.

Authorization framework may read its configuration only at startup or may periodically check configuration for changes. Alternatively authorization framework may be triggered to read its configuration and apply the changes to the current authorization process or read one or more external files as the new configuration.

Plugins is code that interacts with authorization framework to perform specific authorization processes on demand. Authorization framework may provide an API which plugins can use. For example the API may specify the way for plugins to register themselves and a protocol by which data is exchanged with authorization framework or other plugins. Of note the pluggable architecture of authorization framework allows it to be independent of the plugins and makes it possible for plugins to be added and updated dynamically without significant changes to authorization framework .

Each of plugins may implement their own individual authorization process. For example one of plugins may implement an XACML policy. XACML is a well known declarative access control policy language. Meanwhile another of plugins may implement a JACC policy for authorization. JACC is a binding of container access decisions to operations on instances of these permission classes. JACC defines the installation and configuration of authorization providers for use by containers in J2EE.

Policy database serves as source of the overall security policy implemented by authorization framework . A security policy may be any definition of the constraints on behavior of users and components in system . The security policy may also specify functions and flow among them access by external systems and adversaries including programs and access to data by users.

Permissions indicate the authorization decision of authorization framework . For example in J2EE authorization framework may issue its permissions using an abstract Java class for representing access to a system resource. These permissions may have a name whose interpretation depends on the subclass as well as abstract functions for defining the semantics of a particular permission subclass. Permissions may also include an actions list that tells the actions that are permitted for the object. For example for a java.io.FilePermission object the permission name is the pathname of a file or directory and the actions list such as read write specifies which actions are granted for the specified file or for files in the specified directory .

Access manager is the component in charge of integrating the individual authorization decision of plugins and making an overall authorization decision. In particular access manager may operate in accordance with settings provided to it from configuration and enforce the policy provided from policy database . Access manager may request and collect authorization decisions of authorization plugins . Access manager may then combine or accumulate these individual decisions to make an overall authorization decision. In some embodiments access manager provides its authorization decisions in the form a permission object.

Of note this architecture of authorization framework is different from the conventional technology such as JAAS. In JAAS for example authorization is performed based on a policy based architecture. In contrast authorization framework utilizes a plugin architecture. This allows authorization framework to provide finer grain authorization decisions than what is possible with JAAS or the other known authorization technologies. Some of the other components of authorization framework will now be further described.

Access checker invokes one or more of authorization plugins . Access checker selects which of authorization plugins to invoke based on commands from access manager .

Adapter serves as an interface layer between access checker and authorization plugins . For example adapter may be implemented in accordance with an API that support requests for services from authorization plugins .

Policy adapter serves as an interface layer between access manager and policy database . In particular policy adapter allows access manager to utilize external mechanisms for retrieving the security policy it is intended to implement. Policy adapter may also be implemented in accordance with an API.

In phase authorization framework responds to security interceptor and calls one or more of authorization plugin . In particular access manager may read configuration to identify which of authorization plugins need to be called. Access manger may then pass this information to access checker .

Access checker then utilizes the API in adapter to call and execute the appropriate authorization plugins among plugins . Of note each authorization plugins may execute its own authorization process independent of the other plugins. For example as noted above one plugin may implement a XACML policy while another plugin may implement a JACC policy. Of course one or more of plugins may depend on each other. Each of plugins that were called then provides their authorization decision back to access checker via adapter .

For example one set of modules may implement authorization decisions based on user roles. Privileges and permissions to access computing resources are granted to roles instead of or in addition to granting privileges directly to users. Users that need access to resources are then assigned membership in those roles. A role can be any group of users requiring similar or identical access to computing resources. Each permission or privilege in role may specify the allowed operations e.g. read write delete create on any number of objects. Individual objects may be identified individually or by groups.

However others of plugins may be used to implement other parameters of interest for authorization. For example a set of modules may be used to represent a domain of users such as an office location a department etc. As another example a set of modules may be used to implement various profiles such as time of day time of year type of resource and the like. Various plugins can be tailored to specific purposes in order to assist in fine tuning the authorization decisions made by authorization framework .

In phase access manager makes an overall authorization decision for the requested resource. In particular access checker passes the individual authorization decisions of the one or more authorization plugins that were called. Access manager may then combine these individual decisions to make an overall authorization decision. In some embodiments access manager may retrieve a policy from an external mechanism such as policy database via policy adapter . Of course access manager may attempt to implement several policies in reaching its overall authorization decision. This architecture allows access manager to make its authorization decisions more flexibly in comparison to prior authorization schemes. Access manager may for example assign weights to each of the individual decisions by plugins and reach an overall decision based on their respective weights. Of course other logic specified in the security policy may be used in access manager .

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

