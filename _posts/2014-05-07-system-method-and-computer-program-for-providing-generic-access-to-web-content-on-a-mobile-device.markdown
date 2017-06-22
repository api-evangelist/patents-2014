---

title: System, method, and computer program for providing generic access to web content on a mobile device
abstract: A system, method, and computer program product are provided for providing generic access to web content on a mobile device. In use, a request for requested web content is received from a web runtime component associated with a mobile device, the requested web content corresponding to a particular user of the mobile device. Additionally, it is determined whether the particular user is permitted to access the requested web content. Further, the requested web content is retrieved from one or more network based servers associated with the requested web content, in response to determining that the particular user is permitted to access the requested web content. In addition, one or more instructions for modifying the retrieved requested web content are executed, thereby generating modified web content. Furthermore, the modified web content is sent to the web runtime component for rendering.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09369467&OS=09369467&RS=09369467
owner: Amdocs Software Systems Limited
number: 09369467
owner_city: Dublin
owner_country: IE
publication_date: 20140507
---
This application claims the benefit of U.S. Provisional Application No. 61 820 722 filed May 8 2013 the entire contents of which are incorporated herein by reference.

The present invention relates generally to mobile web applications which are applications developed for mobile devices and are typically based on standard web technologies e.g. HTML5 etc. .

The HITML5 hybrid paradigm includes using a web to native abstraction layer enabling access to device capabilities that are not accessible in pure mobile web applications such as an accelerometer a camera and local storage. The HTML5 hybrid approach suffers from technical limitations due to the web ecosystem and specifically regarding how content from different sources can be aggregated and used as inputs in a single mobile application.

A system method and computer program product are provided for providing generic access to web content on a mobile device. In use a request for requested web content is received from a web runtime component associated with a mobile device the requested web content corresponding to a particular user of the mobile device. Additionally it is determined whether the particular user is permitted to access the requested web content. Further the requested web content is retrieved from one or more network based servers associated with the requested web content in response to determining that the particular user is permitted to access the requested web content. In addition one or more instructions for modifying the retrieved requested web content are executed thereby generating modified web content. Furthermore the modified web content is sent to the web runtime component for rendering.

Coupled to the network is a plurality of devices. For example a server computer and an end user computer may be coupled to the network for communication purposes. Such end user computer may include a desktop computer lap top computer and or any other type of logic. Still yet various other devices may be coupled to the network including a personal digital assistant PDA device a mobile phone device a television etc.

As shown a system is provided including at least one central processor which is connected to a communication bus . The system also includes main memory e.g. random access memory RAM etc. . The system also includes a graphics processor and a display .

The system may also include a secondary storage . The secondary storage includes for example a hard disk drive and or a removable storage drive representing a floppy disk drive a magnetic tape drive a compact disk drive etc. The removable storage drive reads from and or writes to a removable storage unit in a well known manner.

Computer programs or computer control logic algorithms may be stored in the main memory the secondary storage and or any other memory for that matter. Such computer programs when executed enable the system to perform various functions to be set forth below for example . Memory storage and or any other storage are possible examples of tangible computer readable media.

As shown a request for requested web content is received from a web runtime WRT component associated with a mobile device the requested web content corresponding to a particular user of the mobile device. See operation . In one embodiment the request may include an HTTP request.

Further the mobile device may include any mobile device capable of accessing web content. For example in various embodiments the mobile device may include a mobile phone a tablet computer a laptop computer and or any other computing device.

In one embodiment the request may be received by a local web server component associated with the mobile device. In the context of the present description the local web server component refers to a component e.g. computer code and or hardware components etc. capable of delivering content to the web runtime component and functioning as a non transparent proxy fully configurable by computer programming code e.g. JavaScript codes etc. .

As shown further in it is determined whether the particular user is permitted to access the requested web content. See operation . For example in one embodiment a content compliancy verification request may be received.

In this case the content compliancy verification request may function to initiate the determination of whether the particular user is permitted to access the requested web content. In one embodiment the content compliancy verification request may be sent from the web runtime component to a content validation component e.g. a profiler etc. associated with the mobile device.

Accordingly in one embodiment determining whether the particular user is permitted to access the requested web content may include determining whether the requested content is compliant with user permissions associated with the particular user.

In response to determining that the requested content is compliant with user permissions associated with the particular user in one embodiment a native application programming interface API associated with the web runtime component may be executed. Additionally a specific session token that corresponds to the request for the requested web content may be set.

In this case the request for the requested web content may include an HTTP request including the specific session token and the request may be received by the local web server component associated with the mobile device In response the web server component may verify with the content validation component that the specific session token is valid. Moreover the local web server component may retrieve user profile parameters associated with the particular user from the content validation component.

With further reference to the requested web content is retrieved from one or more network based servers associated with the requested web content in response to determining that the particular user is permitted to access the requested web content. See operation . The requested web content may be retrieved from any servers and or databases associated with the requested web content e.g. over the Internet etc. .

In addition one or more instructions for modifying the retrieved requested web content are executed thereby generating modified web content. See operation . The instructions for modifying the retrieved requested web content may include any instructions or rules for formatting adapting parsing and or in any other way modifying the requested web content.

For example in one embodiment the instructions for modifying the retrieved requested web content may include one or more content adaptation rules. As an example the content adaptation rules may include a rule or rules for removing elements from the requested web content adding elements to the requested web content and or modifying portions of elements of the requested web content. As another example the content adaptation rules may include a rule or rules for removing advertisements from the requested web content or adding advertisements to the requested web content.

In another embodiment the instructions for modifying the retrieved requested web content may include one or more transcoding instructions. In this case the transcoding instructions may include instructions for converting data of the requested content from a first format to a second format such as from XML to JSON etc. .

In another embodiment the instructions for modifying the retrieved requested web content may include one or more rules for caching the requested content or the modified content. As another example instructions for modifying the retrieved requested web content may include one or more integrity verification rules for verifying an integrity and an origin of the requested content. In another embodiment the instructions for modifying the retrieved requested web content may include one or more decryption rules for decrypting the requested content.

As shown further in the modified web content is sent to the web runtime component for rendering. See operation . Thus the modified web content may be rendered for the particular user of the mobile device thereby providing generic access to web content on the mobile device.

Utilizing this technique a system may function to overcome limitations of the web runtime WRT when working with external content sources such as Cross Origin Resource Sharing limitations specified in W3C HTML5 standard and may function to implement content mashups in applications for instance when the local web server retrieves content from different external web servers . This technique also allows a system to manage client server independent code with any remote content source adapting the code thanks to the code executed by the local web server for rendering into the application.

More illustrative information will now be set forth regarding various optional architectures and uses in which the foregoing method may or may not be implemented per the desires of the user. It should be strongly noted that the following information is set forth for illustrative purposes and should not be construed as limiting in any manner. Any of the following features may be optionally incorporated with or without the exclusion of other features described.

As shown the system includes one or more mobile devices that have access to one or more databases and or one or more servers over a network . In operation the components associated with the mobile device may function to provide generic access to web content on the mobile device . In one embodiment the databases are used by the local web server to obtain HTML content independent data content adaptation rules or adaptation programmatic codes. represents the web servers where the web content should be retrieved from.

Developing mobile HITML5 applications with native capabilities is a relatively new domain and is undergoing frequent innovation and improvements. Typical mobile web applications are composed of web content embedded on a mobile device and remote Web XML JSON content received from servers.

In one embodiment components associated with the mobile device may function to allow decoupling a mobile application from a content access policy entity. These components may be referred to collectively as the content access entity.

In one embodiment the content access entity may be divided into two modules. The first module or component referred to as a profiler or content validation component is in charge of checking the access policy. The profiler may implement specific and complex logic for accessing and proxying content.

The second module performs the content retrieval works as a proxy and may adapt the content for aggregation into the mobile application. In one embodiment none of this logic may be executed in the web runtime component and therefore the logic need not comply with the web runtime component operations which is dictated by the W3C mobile standard and any device vendor restrictions and thus suffer from its limitations.

This logic may thus be written in device independent code such as for example JavaScript Java Ruby and Python etc. This code may be executed on servers such as NodeJS or Rhino etc. This technique allows JavaScript components to be executed either on the client or the server without any modifications.

In operation the system uses a client side execution environment running on a mobile device which may load and run mobile HTML5 application code. The system allows retrieving web content from any HTTP data sources to modify it and to transfer the modified content to a web runtime component as regular content coming from any HTTP source.

As shown the system includes a mobile application that includes a local web server component which delivers content to the web runtime component and acts as a non transparent proxy fully configurable by JavaScript codes.

Additionally the mobile application includes a content validator referred to as a profiler that executes permissions and filtering based on user profile rules. Still yet the system includes the web runtime component that executes in memory web content composed of for example HTML pages JS libraries CSS pages or instructions and media.

In operation the web runtime component triggers the retrieval of the bootstrap HTML content via for example a URL or a local file. A request is then sent to the profiler for content compliancy checking. The profiler checks that the content is compliant with the user permissions as detailed for example in white lists and black lists and implements a native API with the web runtime component that functions to set a specific session token which corresponds to this first request.

The local web server receives the HTML content request as an HTTP request referred to as the original content OCT or requested content. The local web server verifies with the profiler that the session token included in the HTTP request is valid and retrieves user profile parameters UPP from the profiler .

The local web server reads the version of the content from external servers executes the JavaScript script code referred to as the adaptation rules code ARC or modification instructions which function to parse and adapt this content. The local web server then delivers the adapted content ACT to the web runtime component .

Lastly the web runtime component renders the adapted content for the end users. Some HTTP hyperlinks may be activated from the adapted content and the process may repeat for each activated hyperlink.

In another embodiment the profiler may just accept requests. In this case the profiler may then process the requests outside of a user context and the UPP data will be empty.

When developing hybrid applications the developer is able to separate the JavaScript code used for the modification instructions e.g. the ARC etc. and executed by the local web server and the HTML content in the embedded web content executed by the web runtime component OCT and ACT .

The modification instructions e.g. the ARC may be associated with a variety of tasks. For example the modification instructions may be associated with content adaptation. For example the code may cause element removal for advertisements filtering or enrichments by using data from different sources and based on UPP data.

As another example the code may cause transcoding. For example the code may modify a payload from one data source of one format to another such as from XML to JSON without impacting either the data source or the mobile application embedded content.

As another example the code may cause content caching. For example the code may instruct caching of the content to ensure that it is still available offline.

As another example the code may implement content control functionality. For example the code may be used to return default content instead of the exact content if the latter is from a forbidden web source.

As another example the code may implement integrity verification. For example using a signature mechanism the code may verify the integrity and origin of the content e.g. the OCT .

Further the code may function to implement decryption. For example the code may decrypt the content if it was encrypted by a server for protecting it to any men in the middle attack such as an agent listening to the HTTP socket.

In one embodiment the modification instruction code may already be installed with the application and may not need to be downloaded from any remote source. In another embodiment the modification instruction code may be downloaded at the time of the request and the location from where modification instruction code is retrieved may depend on the HTTP request used to retrieve the content.

While various embodiments have been described above it should be understood that they have been presented by way of example only and not limitation.

Thus the breadth and scope of a preferred embodiment should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

