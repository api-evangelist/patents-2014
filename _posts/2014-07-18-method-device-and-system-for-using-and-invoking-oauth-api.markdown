---

title: Method, device and system for using and invoking Oauth API
abstract: The present invention provides methods, devices and systems for using and invoking an Oauth API. The method includes: receiving registration information for registering an Oauth API; generating an Oauth API invoking associated interface according to the registration information, and binding it with the registered Oauth API, to generate binding information; receiving an increasing Oauth API message and responding, generating a client requesting Oauth API interface, an Oauth API returned information processing interface and a client customer serial number managing interface, which correspond to the registered Oauth API; receiving a publishing application message, responding to the publishing application message, and generating a deployment package which includes the client requesting Oauth API interface, the Oauth API returned information processing interface and the client customer serial number managing interface; sending the binding information and the deployment package to an application running engine, based on which the application running engine complete Oauth API scheduling.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09430302&OS=09430302&RS=09430302
owner: Huawei Technologies Co., Ltd.
number: 09430302
owner_city: Shenzhen
owner_country: CN
publication_date: 20140718
---
This application is a continuation of International Patent Application No. PCT CN2013 070753 filed on Jan. 21 2013 which claims priority to Chinese Patent Application No. 201210018877.4 filed on Jan. 20 2012 both of which are hereby incorporated by reference in their entireties.

The present invention relates to authorization access technologies and in particular to a method a device and a system for using and invoking an Oauth API which belong to the field of communication technology.

An open authorization protocol An open protocol to allow secure API authorization in a simple and standard method from desktop and web applications Oauth has been widely used on the Internet as a third party API authentication and authorization access protocol which is currently most popular in the industry this standard can enable a user to expose private information which is saved at a certain service provider to third party applications without exposing the user key for example Google Sina Tencent and others publish abundant APIs based on the Oauth standard. A trust mechanism of different services is established through the Oauth protocol which greatly promotes the Internet s opening.

Although the purpose of protecting access resources can be achieved currently by providing APIs under the Oauth protocol by the service providers for developers using open authorization application programming interface Oauth Application Programming Interface Oauth API the Oauth API can only be used by way of writing code. For example the work of integrating the Oauth API is completed through citing software development kit Software Development Kit SDK provided by an Oauth API provider Provider invoking a authentication interface and a service interface in the SDK by writing code and tightly coupling Oauth authorization logic into application code. The developers use the Oauth API by way of writing code such a method for using the Oauth API is complicated and inefficient thereby exposing the problem of how to use the Oauth API efficiently.

For the deficiencies in the prior art the present invention provides a method device and system for using and invoking an Oauth API so as to use the Oauth API efficiently.

binding the Oauth API invoking associated interface with the registered Oauth API and generating binding information 

receiving an increasing Oauth API message responding to the increasing Oauth API message and generating a client requesting Oauth API interface an Oauth API returned information processing interface and a client customer serial number managing interface which correspond to the registered Oauth API 

receiving a publishing application message responding to the publishing application message and generating a deployment package which includes the client requesting Oauth API interface the Oauth API return information processing interface and the client customer serial number managing interface 

sending the binding information and the deployment package to an application running engine so that the application running engine complete Oauth API scheduling according to the binding information and the deployment package.

Another aspect of the present invention also provides an application developing platform the application developing platform includes 

an Oauth API registration module configured to receive registration information for registering an Oauth API 

an invoking associated interface generating module configured to generate an Oauth API invoking associated interface according to the registration information 

a binding module configured to bind the Oauth API invoking associated interface with the registered Oauth API and generate binding information 

a use interface generating module configured to receive an increasing Oauth API message respond to the increasing Oauth API message and generate a client requesting Oauth API interface an Oauth API returned information processing interface and a client customer serial number managing interface which correspond to the registered Oauth API 

a deploying module configured to receive a publishing application message respond to the publishing application message and generate a deployment package which includes the client requesting Oauth API interface the Oauth API returned information processing interface and the client customer serial number managing interface 

a sending module configured to send the binding information and the deployment package to an application running engine so that the application running engine complete Oauth API scheduling according to the binding information and the deployment package.

Still another aspect of the present invention also provides a method for invoking an Oauth API the method includes 

intercepting a client request message allocating a customer serial number for a client and storing the customer serial number 

receiving an Oauth API invoking request carrying the customer serial number where the Oauth API invoking request is sent by the client through invoking a client requesting Oauth API interface 

authenticating Oauth API invoking according to the customer serial number carried by the Oauth API invoking request and obtaining interface binding information corresponding to an Oauth API which is requested to be invoked after the authentication is passed 

performing authorization and authentication according to the interface binding information and obtaining an access token 

injecting the access token into the Oauth API invoking request and sending the Oauth API invoking request into which the access token is injected to an Oauth API provider so that the Oauth API responds to the Oauth API invoking request into which the access token is injected and returns Oauth API returned information 

A further aspect of the present invention also provides an application running engine the application running engine includes 

a client customer serial number managing module configured to intercept a client request message allocate a customer serial number for a client and store the customer serial number 

an Oauth API invoking request receiving module configured to receive an Oauth API invoking request carrying the customer serial number wherein the Oauth API invoking request is sent by the client through invoking a client requesting Oauth API interface 

an authenticating module configured to authenticate Oauth API invoking according to the customer serial number carried by the Oauth API invoking request and obtaining interface binding information corresponding to an Oauth API which is requested to be invoked after the authentication is passed 

an authorization and authentication module configured to perform authorization and authentication according to the interface binding information and obtain an access token 

an Oauth API invoking module configured to inject the access token into the Oauth API invoking request and send the Oauth API invoking request into which the access token is injected to an Oauth API provider so that the Oauth API responds to the Oauth API invoking request into which the access token is injected and returns Oauth API returned information 

an Oauth API returned information processing module configured to return the Oauth API returned information to the client so as to complete the Oauth API invoking.

A further aspect of the present invention also provides a system for using an Oauth API the system includes an application developing platform according to embodiments of the present invention and an application running engine according to embodiments of the present invention.

According to the method device and system for using and invoking an Oauth API of the present invention a set of universal authentication interfaces are formed through abstracting Oauth authentication logic when developers develop applications the application developing platform automatically generates executable interfaces and injects them into the application running engine so that the application running engine can automatically execute these executable interfaces to complete Oauth API invoking when determining that the client needs the Oauth API invoking. It can be seen that in the method for using the Oauth API according to the above embodiment the developers only need to introduce the Oauth API registration into the application developing platform that is provide Oauth API registration information to the application developing platform the remaining generating of the executable interfaces and related processing are all completed automatically by the application developing platform thereby greatly simplifying the application development procedure and improving development efficiency.

The technical solutions in embodiments of the present invention are described clearly and comprehensively with reference to the accompanying drawings obviously the embodiments described are only some exemplary embodiments of the present invention and the present invention is not limited to such embodiments. Other embodiments derived by those skilled in the art on the basis of the embodiments herein without any creative effort fall within the protection scope of the present invention.

Step S generating an Oauth API invoking associated interface according to the registration information 

Step S binding the Oauth API invoking associated interface with the registered Oauth API and generating binding information 

Step S receiving an increasing Oauth API message responding to the increasing Oauth API message and generating a client requesting Oauth API interface an Oauth API returned information processing interface and a client customer serial number managing interface which correspond to the registered Oauth API 

Step S receiving a publishing application message responding to the publishing application message and generating a deployment package which includes the client requesting Oauth API interface the Oauth API returned information processing interface and the client customer serial number managing interface 

Step S sending the binding information and the deployment package to an application running engine so that the application running engine complete Oauth API scheduling according to the binding information and the deployment package.

Specifically in the method for using the Oauth API according to the above embodiment a developer registers the Oauth API in the application developing platform and provides the registration information of the Oauth API where the Oauth API is an available Oauth API provided by an Oauth API provider. The application developing platform automatically generates the Oauth API invoking associated interface according to the registration information for registering the Oauth API where the Oauth API invoking associated interface is used for achieving the support for the Oauth API invoking. In addition the increase of the Oauth API in the application developing platform can also be triggered according to the registered Oauth API.

According to the method for using the Oauth API of the above embodiment a set of universal authentication interfaces are formed through abstracting Oauth authentication logic when developers develop applications the application developing platform automatically generates executable interfaces and injects them into the application running engine so that the application running engine can automatically execute these executable interfaces to complete Oauth API invoking when determining that the client needs the Oauth API invoking. It can be seen that in the method for using the Oauth API according to the above embodiment the developers only need to introduce the Oauth API registration into the application developing platform that is provide Oauth API registration information to the application developing platform the remaining generating of the executable interfaces and related processing are all completed automatically by the application developing platform thereby greatly simplifying the application development procedure and improving development efficiency.

Where the information needs to be registered includes the following domain information which is needed when accessing an Oauth API 

a communication use protocol Use SSL the communication use protocol includes the hyper text transfer protocol HyperText Transfer Protocol HTTP and the secure hyper text transfer protocol Secure Hyper Text Transfer Protocol HTTPS one protocol of the two must be selected when registering such as selecting the HTTP 

a request token Request Token uniform resource locator Uniform Universal Resource Locator URL which is used for identifying the service address provided by the Oauth API provider to the customer for obtaining the request token such as api.t.sina.com.cn oauth request token 

an authorization and authentication URL which is used for identifying the official authentication address provided by the Oauth API provider for user authorization such as api.t.sina.com.cn oauth authorize 

an access token URL which is used for identifying the address provided by the Oauth API provider to the customer for obtaining the access token and the access signature such as api.t.sina.com.cn oauth access token 

an application serial number consumer Key which is used for identifying the application serial number needed for accessing a service and provided by the Oauth API provider such as 4018652807 

an application signature consumer Secret which is used for identifying the application signature needed for accessing a service and provided by the Oauth API provider such as 5ee8fc57a5c8a9589a3933b92576a0b6 .

Step S after receiving the message for registering the Oauth domain the application developing platform records the Oauth domain registration information and notifies the application running engine to save the Oauth domain registration information 

Where the registration information needs to be provided by the developer includes API information needed for invoking the Oauth API which specifically includes the following information 

a HTTP method method which is used for identifying the method for invoking the service where the method for invoking the service includes two kinds POST and GET and only one of these two kinds needs to be selected when registering such as POST 

an URL which is used for identifying the URL which API accesses such as http api.t.sina.com.cn statuses update.json 

an output Output format which is used for identifying the format of API returned data where the format of the API returned data includes two kinds json and xml and only one of these two kinds is selected such as json 

Step S after receiving the message for registering the Oauth API the application developing platform generates a server Oauth API invoking interface 

Specifically the application developing platform generates the interface for invoking the Oauth API in the application running engine according to the Oauth API registration information registered by the developer this service OauthAPI invoking interface is the interface for sending request process to the Oauth API after the request signature information and the access token are injected after authentication succeeds. For example the generating mode is generating the interface by taking the name of the registered Oauth API as the name of the server Oauth API invoking interface and taking url httpmethod paramStr signature accessToken as the interface parameter names. For example the generated server Oauth API invoking interface is 

Step S the application developing platform generates the Oauth authorization and authentication interface 

After receiving the message for generating the Oauth authorization and authentication interface the application developing platform automatically generates the interface needed for the Oauth authorization and authentication. There are two modes of generating the interface one is that generating an executable function interface the other is that generating an interface docking with the SDK which supports to bind an authorization and authentication interface generated dynamically and an OauthSDK interface deployed in the running engine.

a signature interface the generating mode is such as taking the registered OauthAPI name and the keyword which means signature as the interface name and taking url key paras as the parameter names to generate the signature interface. The generated signature interface is such as 

an obtaining request token interface the generating mode is such as taking the registered OauthAPI name and the keyword which means RequestToken as the interface name and taking consumerkey consumersecret requestTokenURL signature as the parameter names to generate the interface. The generated obtaining request token interface is such as 

a requesting user authorization interface the generating mode is such as taking the registered OauthAPI name and the keyword which means user authorization as the interface name and taking requestToken authoticationURL as the parameter names to generate the interface. The generated requesting user authorization interface is such as 

an obtaining Oauth access token interface the generating mode is such as taking the registered OauthAPI name and the keyword which means obtaining access token as the interface name and taking requestToken AccessTokenURL Verifier as the parameter names to generate the interface. The generated obtaining Oauth access token interface is such as 

Step S the application developing platform binds the authorization and authentication interface according to the API name and defines the procedure of invoking the interface.

Specifically the bound interface may be an executable function interface and may also be an interface docking with the SDK. When the SDK interface is bound the authorization and authentication interface needed for invoking the Oauth API and the authorization and authentication interface in the OauthSDK are bound and mapped. When defining the procedure of invoking the interface for example determining to bind the procedure of either application automatically triggering Oauth authentication and authorization or user triggering Oauth authentication and authorization according to the configuration information of the application developing platform the various authorization procedure is bound according to the configuration information.

The binding information includes the bound Oauth API name the name of the interface for the server invoking the OauthAPI and the interface parameter names the name of the interface corresponding to the signature and parameter names thereof the name of the interface corresponding to obtaining the RequestToken and parameter names thereof the name of the interface corresponding to triggering the user authorization and parameter names thereof the name of the interface corresponding to obtaining the AccessToken and parameter names thereof and the bound interface execution sequence.

Step S the application developing platform notifies the application running engine to inject the registration information of the registered Oauth API and the binding information 

Step S the developer uses Oauth API developing service and triggers the application developing platform to increase the Oauth API 

Step S after receiving the message for increasing the Oauth API the application developing platform generates an interface for triggering the Oauth authentication procedure.

Specifically if the application developing platform determines that the Oauth authorization and authentication procedure is user triggering Oauth authorization and authentication procedure according to the configuration information then the generated interface information includes 1. user triggering authentication and authorizing entrance button link 2. the interface for requesting the Oauth authentication and authorization from the server after the user triggers the authorization and authentication procedure OauthAPI requesting authorization interface where the OauthAPI requesting authorization interface includes parameters OauthAPI name and customer serial number ClientKey .

Specifically the generated client OauthAPI requesting interface is used when the application is running the client requests the application running engine by invoking this client OauthAPI requesting interface to call the OauthAPI. The generating mode of the client OauthAPI requesting interface is such as taking the registered OauthAPI name and the keyword which means invoke as the interface name and taking apiName clientKey paras injectedInterfaceName as the parameter names to generate the interface. The generated client OauthAPI requesting interface is such as 

Step S the application developing platform generates OauthAPI returned information processing interface 

Specifically the generated OauthAPI return information processing interface is used for processing the information returned by the OauthAPI after the application running engine invokes the OauthAPI successfully. The generating mode of the OauthAPI returned information processing interface is such as taking the registered OauthAPI name and the keyword which means inject as the interface name and taking result as the parameter name to generate the interface definition information. The generated OauthAPI returned information processing interface is such as 

Specifically the generated client ClientKey managing interface is used for saving the ClientKey of the legal access identifier allocated by the application running engine for the client. The generating mode of the client ClientKey managing interface is such as taking the keyword which means client key as the interface name taking the keyword which means save client key as the name to generate a functional method and its parameter name is url and taking the keyword which means getClientKeyKey as the name to generate a non parametric functional method so as to generate the interface. The generated client ClientKey managing interface is such as 

Specifically after receiving the message for publishing the application which is sent by the developer the application developing platform generates the deployment package according to the application information and notifies the application running engine to deploy.

an Oauth API registration module configured to receive registration information for registering an Oauth API 

an invoking associated interface generating module configured to generate an Oauth API invoking associated interface according to the registration information 

a binding module configured to bind the Oauth API invoking associated interface with the registered Oauth API and generate binding information 

a use interface generating module configured to receive an increasing Oauth API message respond to the increasing Oauth API message and generate a client requesting Oauth API interface an Oauth API returned information processing interface and a client customer serial number managing interface which correspond to the registered Oauth API 

a deploying module configured to receive a publishing application message respond to the publishing application message and generate a deployment package which includes the client requesting Oauth API interface the Oauth API returned information processing interface and the client customer serial number managing interface 

a sending module configured to send the binding information and the deployment package to an application running engine so that the application running engine complete Oauth API scheduling according to the binding information and the deployment package.

Where the use interface generating module includes for example a client requesting Oauth API interface generating unit an Oauth API returned information processing interface generating unit and a client customer serial number managing interface generating unit.

The procedure of the application development which is performed by the application developing platform of the above embodiment using the Oauth API is the same as the method for using the Oauth API according to the aforementioned embodiments which will not be repeated here.

According to the application developing platform of the above embodiment a set of universal authentication interfaces are formed through abstracting Oauth authentication logic when developers develop applications the application developing platform automatically generates executable interfaces and injects them into the application running engine so that the application running engine can automatically execute these executable interfaces to complete Oauth API invoking when determining that the client needs the Oauth API invoking. It can be seen that in the method for using the Oauth API according to the above embodiment the developers only need to introduce the Oauth API registration into the application developing platform that is provide Oauth API registration information to the application developing platform the remaining generating of the executable interfaces and related processing are all completed automatically by the application developing platform thereby greatly simplifying the application development procedure and improving development efficiency.

Further in the application developing platform of the above embodiment the registration token includes the name of the registered Oauth API a request method a uniform resource locator an input format an output format an identification indicating whether open authorization protocol Oauth authentication needs to be opened and the domain name of the Oauth domain corresponding to the registered Oauth API.

an Oauth domain registering module configured to receive registration information for registering an Oauth domain where the registered Oauth domain corresponds to the registered Oauth API.

Further in the application developing platform of the above embodiment the call associated interface generating module includes 

a server Oauth API invoking associated interface generating unit configured to generate a server Oauth API invoking interface 

an Oauth authorization and authentication interface generating unit configured to generate an authorization and authentication interface.

Further in the application developing platform of the above embodiment the binding information includes the name of the registered Oauth API the server Oauth API invoking interface the authorization and authentication interface and an interface executing procedure.

The method for invoking an Oauth API according to embodiments of the present invention may also be implemented based on the system architecture shown in where the method for invoking the Oauth API is performed by the application running engine shown in the following describes the method for invoking the Oauth API according to embodiments of the present invention in detail from the point of the application running engine.

Step S intercepting a client request message allocating a customer serial number for a client and storing the customer serial number 

Step S receiving an Oauth API invoking request carrying the customer serial number where the Oauth API invoking request is sent by the client through invoking a client requesting Oauth API interface 

Step S authenticating Oauth API invoking according to the customer serial number carried by the Oauth API invoking request and obtaining interface binding information corresponding to an Oauth API which is requested to be invoked after the authentication is passed 

Step S performing authorization and authentication according to the interface binding information and obtaining an access token 

Step S injecting the access token into the Oauth API invoking request and sending the Oauth API invoking request into which the access token is injected to an Oauth API provider so that the Oauth API responds to the Oauth API invoking request into which the access token is injected and returns Oauth API returned information 

Step S returning the Oauth API returned information to the client so as to complete the Oauth API invoking.

In the method for invoking the Oauth API according to the above embodiment the interface binding information and all executable interfaces which are involved during the Oauth API invoking process executed by the application running engine responding to the client request are pre generated by the application developing platform the specific generating process is the same as that in the method for using the Oauth API according to the aforementioned embodiments which will not be repeated here.

According to the method for invoking the Oauth API of the above embodiment since the application running engine automatically uses the executable interfaces provided by the application developing platform to complete the Oauth API invoking a convenient Oauth API invoking is achieved.

Further in the Oauth API calling method according to the above embodiment the trigger of the authorization authentication includes two cases that is the application automatically triggers the Oauth authorization authentication and the user triggers the Oauth authorization authentication. The following describes these two cases respectively.

Step S a user accesses an application deployed in the application running engine via a client tool and initiates an application request 

Step S intercepting the application request sent by the client and recording the first URL which is requested to be accessed 

Step S allocating a unique identified customer serial number ClientKey for the client and recording the ClientKey 

Where the rule of generating the ClientKey value is according to the client IP the current SessionlD the application name the user ID the GUID and the current request time signing by HMAC SHA1 algorithm to generate.

Step S according to the URL recorded in the step S and the ClientKey generated in the step S redirecting the user to the second URL with the ClientKey 

Step S when the application is running on the client invoking ClientKey managing Interface to obtain the ClientKey value and save it 

Step S the client requests the application running engine to invoke the OauthAPI where the request parameters include the ClientKey recorded in the step S the name of the invoked OauthAPI the parameters needed for invoking the OuathAPI and the name of the interface for the client processing the returned result.

Step S the application running engine obtains the ClientKey and authenticates it so as to determine whether it is a legal ClientKey an authenticating method is such as 

1 checking whether the ClientKey provided by the client is recorded in the application running engine being illegal if not.

3 obtaining the client IP the current SessionlD the request application name the user ID according to the client request.

4 matching each item of the information obtained upon 2 and the information obtained upon 3 being legal if the two match being illegal if not.

Step S according to the request information obtaining and recording the URL of the application which requests the Oauth the parameters the OauthAPI name the name of the OauthAPI returned information processing interface 

Step S querying the corresponding interface binding information according to the requested OauthAPI name the interface binding information is the binding information generated in the procedure of the application developing platform using the OauthAPI 

Step S obtaining and executing the Oauth authorization and authentication interface according to the interface binding information obtained in the step S and obtaining an AccessToken 

1 obtaining the authorization and authentication interface according to the interface binding information and executing the authorization and authentication interface 

2 when triggering the user authorization interface to redirect to the Oauth provider authorization page is executed setting CALLBACK of the Oauth provider as the URL for the application running engine receiving the certificating result service 

3 obtaining an authenticator by receiving the authentication result service and obtaining the access token 

4 combining the customer serial number and the identifier of the Oauth API as an identifier for recording the access token according to the stored customer serial number the identifier of the Oauth API and the access token and recording the access token.

Step S re performing the signing by HMAC SHA1 algorithm to the ClientKey and OauthAPI according to the earlier recorded ClientKey the OauthAPI name and the obtained AcceessToken and recording the AccessToken by taking the generated signature value as an identifier of recording the AcceessToken.

Step S executing server OauthAPI invoking interface to inject the AccessToken according to the earlier recorded parameters and the AccessToken and sending a request to the OauthAPI 

Step S executing generating client script interface to generate a dynamic script according to the obtained OauthAPI returned information and the interface name of the recorded injecting result 

Step S the client executes the injected script and invokes OauthAPI returned information processing interface to complete processing the returned information such as displaying and calculating result information.

Step S after receiving a message for invoking an OauthAPI the client OauthAPI requesting interface opens the client triggering Oauth authentication procedure interface prompting the user to trigger the authorization and authentication procedure after the user triggers the certificating authorization procedure requesting the application running engine to perform the Oauth authorization the content of the message for invoking the OauthAPI received by the client requesting OauthAPI Interface includes the OauthAPI name the service interface URL turned to after the authorization succeeds the corresponding parameter values when invoking the OauthAPI 

Step S after receiving the authorization request the application running engine intercepts the request and records the URL and the OauthAPI name which is requested to be authorized 

Step S the application running engine allocates a unique identifier ClientKey as a client legal identifier and records the ClientKey 

Step S obtaining interface binding information of the requested OauthAPI according to the requested OauthAPI name 

Step S executing the authorization and authentication interface according to the binding information and obtaining an AccessToken 

Step S redirecting the user to a new URL generated by combining the recorded URL and the ClientKey the client obtains and records the ClientKey 

Step S the client requests according to the ClientKey the application running engine to invoke the OauthAPI 

Step S obtaining and recording the ClientKey the OauthAPI name the request URL the request parameters the callback interface name 

Step S if the ClientKey is authenticated as legal and if it is determined that the ClientKey has been authorized obtaining the recorded AccessToken according to the ClientKey and the OauthAPI name if the ClientKey is authenticated as illegal returning ClientKey invalid information and if it is determined that the ClientKey has not been authorized going back to the step S to re authorize the ClientKey 

Step S injecting the obtained AccessToken into the request and sending the request to the Oauth provider 

In the method for invoking the Oauth API according to the above embodiment one to one mode is formed through executing authorization authentication at the server in a concentrated mode thereby many to one mode by which the application client and the Oauth provider interact directly with each other is avoided interaction endpoints are reduced and the risk of sensitive data being transmitted on the Internet can be reduced.

Further in the method for invoking the Oauth API according to the above embodiment performing the authorization and authentication according to the interface binding information specifically includes 

obtaining the authorization and authentication interface from the interface binding information and running the authorization and authentication interface to complete the authorization and authentication or

obtaining the interface mapping information corresponding to the interface in the Oauth SDK from the interface binding information invoking the specific interface in the Oauth SDK through the mapped interface name and the mapped parameter name to complete the authentication and authorization.

According to the method for invoking the Oauth API of the above embodiment Oauth API authentication procedure interface is invoked and executed by adopting a common manner thereby avoiding introducing SDK of different providers when using the Oauth API provided by different Oauth providers will cause space to be wasted.

a client customer serial number managing module configured to intercept a client request message allocate a customer serial number for a client and store the customer serial number 

an Oauth API invoking request receiving module configured to receive an Oauth API invoking request carrying the customer serial number wherein the Oauth API invoking request is sent by the client through invoking a client requesting Oauth API interface 

an authenticating module configured to authenticate Oauth API invoking according to the customer serial number carried by the Oauth API invoking request and obtaining interface binding information corresponding to an Oauth API which is requested to be invoked after the authentication is passed 

an authorization and authentication module configured to perform authorization and authentication according to the interface binding information and obtain an access token 

an Oauth API invoking module configured to inject the access token into the Oauth API invoking request and send the Oauth API invoking request into which the access token is injected to an Oauth API provider so that the Oauth API responds to the Oauth API invoking request into which the access token is injected and returns Oauth API returned information 

an Oauth API returned information processing module configured to return the Oauth API returned information to the client so as to complete the Oauth API invoking.

The specific procedure of executing the Oauth API invoking by the application running engine according to the above embodiment is the same as the method for invoking the Oauth API according to the above embodiments which will not be repeated here.

According to the application running engine of the above embodiment a convenient Oauth API invoking is achieved through automatically using the executable interfaces provided by the application developing platform to complete the Oauth API invoking.

Further in the application running engine according to the above embodiment the client request message includes the URL that the client requests to access.

Further in the application running engine according to the above embodiment the client request message comprises an identifier of an Oauth API which the client requests to invoke a service page URL turned to after the authorization succeeds and corresponding parameter values for invoking the Oauth API.

Further in the application running engine according to the above embodiment the authorization and authentication module specifically includes 

a first processing unit configured to obtain the authorization and authentication interface according to the interface binding information and execute the authorization and authentication interface 

a second processing unit configured to when triggering the user authorization interface to redirect to the Oauth provider authorization page is executed set CALLBACK of the Oauth provider as the URL for the application running engine receiving the authentication result service 

a third processing unit configured to obtain an authenticator by receiving the authentication result service and obtain an access token 

a fourth processing unit configured to according to the stored clientkey the Oauth API identifier and the access token combine the customer serial number and the identifier of the Oauth API as an identifier for recording the access token according to the stored customer serial number the identifier of the Oauth API and the access token and recording the access token.

Embodiments of the present invention also provide a system for using an Oauth API the system includes an application developing platform according to any one of the above embodiments and an application running engine according to any one of the above embodiments.

According to the system for using the Oauth API of the above embodiment a set of universal authentication interfaces are formed through abstracting Oauth authentication logic when developers develop applications the application developing platform automatically generates executable interfaces and injects them into the application running engine so that the application running engine can automatically execute these executable interfaces to complete Oauth API invoking when determining that the client needs the Oauth API invoking. It can be seen that in the method for using the Oauth API according to the above embodiment the developers only need to introduce the Oauth API registration into the application developing platform that is provide Oauth API registration information to the application developing platform the remaining generating of the executable interfaces and related processing are all completed automatically by the application developing platform thereby greatly simplifying the application development procedure and improving development efficiency.

Finally it should be noted that the above embodiments are merely provided for describing the technical solutions of the present invention but not intended to limit the present invention It should be understood by those skilled in the art that although the present invention has been described in detail with reference to the foregoing embodiments modifications can be made to the technical solutions described in the foregoing embodiments or equivalent replacements can be made to some technical features in the technical solutions however such modifications or replacements do not cause the essence of corresponding technical solutions to depart from the spirit and the scope of the present invention.

