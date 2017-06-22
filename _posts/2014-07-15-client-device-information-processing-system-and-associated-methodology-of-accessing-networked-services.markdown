---

title: Client device, information processing system and associated methodology of accessing networked services
abstract: A system provides access to services from different servers via a common API. The system includes service-offering servers, a client that uses services offered by the service-offering servers, and an interchange server that acts as an intermediary when the client uses a service. The client communicates with the interchange server using a common API when the client uses service from the service-offering servers. The interchange server uses a unique API, which is unique to the service-offering server that offers the service being used by the client, to execute a processing sequence that is unique to the service-offering server. Thus client is able to use services offered by the service-offering servers with the use of a common API and without any need to use a different unique API for each service-offering server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09112868&OS=09112868&RS=09112868
owner: SONY ELECTRONICS INC.
number: 09112868
owner_city: Park Ridge
owner_country: US
publication_date: 20140715
---
The present application is a continuation application of U.S. application Ser. No. 13 934 680 filed Jul. 3 2013 which is a continuation application of U.S. application Ser. No. 12 995 619 filed Dec. 1 2010 which is a National Phase of PCT US09 51840 filed Jul. 27 2009 and claims the benefit of U.S. Application Ser. No. 61 137 241 entitled Media Interchange filed Jul. 28 2008 and U.S. Application Ser. No. 61 086 235 entitled System of Uploading and Downloading Images by Using an Interchange Server filed Aug. 5 2008 the entire contents of each of which are incorporated herein by reference.

The present advancements relate to a client device such as a camera to access services offered by service offering servers managed by service providers. For example upload processing may be provided in which a client device transmits user data such as image data and the like to a server so as to store the uploaded data in a server database.

Various types of services are accessible via a network. For example a service that allows user data such as images captured by a digital camera or the like to be uploaded to a server for storage in a database that is managed by the server is known. A user may browse the images that are stored in the database of the server on demand. In addition the uploaded images can be made publicly accessible via a network depending on user preferences. Such an image upload processing is described in for example Japanese Unexamined Patent Application Publication No. 2006 252152 incorporated herein by reference.

The types and modes of services offered differ from one service provider to another. A user can choose any service depending on their preference.

Service providers offering such an image upload service provide an individual solution for uploading an image s via Internet browser that is a solution unique to each individual service provider. For example a client device can perform upload processing by means of the Internet browser. However generally speaking this processing is difficult because there are many restrictions unique to the Internet browser.

In order to improve usability some mobile devices such as some digital cameras have for example an upload processing execution program that has been stored in a memory thereof in advance to be used for uploading a photographed image. Or as another example such a program is downloaded from a server and then stored in the memory of a mobile device such as a camera. Upload processing is performed with the use of the stored upload dedicated program.

However many of such upload processing programs are unique to respective service providers. That is in order to use an image upload service that is offered by a certain service provider a dedicated program that is unique to the above mentioned certain service provider is necessary.

When a dedicated program that uniquely corresponds to a certain service provider is used in a client device such as a digital camera the client uses an API Application Programming Interface that is unique to the service provider. The API is the unit of a program for the execution of predetermined processing. As a certain API is called up predetermined processing that is specified in the called API is performed. For example an API is set so as to correspond to each of server connection processing login processing upload processing and the like. A client can execute a series of processing with the use of these APIs.

In the majority of cases such API is unique to each service provider. That is a dedicated API that corresponds to login processing upload processing or the like that is specified by each service provider is set. Accordingly a client is required to use such a dedicated API.

As explained above a service provider that offers an image upload service sets a plurality of APIs that are unique to services of its own. The service provider allows a client to use these APIs so as to perform upload processing. Through API application processing explained above upload processing such as the creation of upload data that is in conformity with an acceptable data format that is unique to the service provider client server communication processing and the like is executed. By this means upload processing that is free from errors is ensured.

If a client uses services offered by one service provider only it is enough to install a program API that uniquely corresponds to the above mentioned one service provider at the client side. However in a practical sense there are many service providers who offer image upload services. Therefore in order to allow a user to freely select a service provider among them it is necessary to install many programs APIs which respectively correspond to all service providers on the client. This is not desirable for a client device such as a camera that has a limited memory space.

In addition programs APIs are subject to change and or update due to for example change in the modes of services offered by service providers. If such change and or update is effected after a client device in which a plurality of APIs and programs that corresponds to image upload services offered by a plurality of service providers is installed has been supplied to a user it becomes necessary at the client side to update the programs APIs. If a user is required to perform such updating processing it places a burden on the user. Moreover there is a risk of the occurrence of a processing error.

In view of the foregoing the present advancements provide client device an information processing system an information processing method and a computer readable medium for accessing a plurality of service offering servers via a common program and a common API.

The present disclosure provides a method of causing an interchange server to intermediate communication between a client device and a plurality of service offering servers. A user interface is generated at the client device in accordance with a common API that is independent of the plurality of service offering servers. Input data entered into the user interface is received at the interchange server. The input data includes selection of a service corresponding to at least one of the plurality of service offering servers. The input data is translated according to at least one service specific API associated with the at least one service offering server corresponding to the selected service. The service specific API is stored in an electronic memory of the interchange server as part of a plurality of different service specific APIs that respectively correspond to the plurality of service offering servers. The translated data is transmitted from the interchange server to the at least one service offering server in accordance with the at least one service specific API and a response from the at least one service offering server is translated and transmitted to the client in accordance with the common API.

Other objects features and advantages of the present disclosure will be fully understood from the following detailed description of exemplary embodiments of the invention read in conjunction with accompanying drawings.

In the following the present advancement will be discussed by describing a preferred embodiment and by referring to the accompanying drawings. However those skilled in the art will realize other applications and modifications within the scope of the invention as defined in the enclosed independent claims.

The service offering servers are servers that are operated by service providers A F who offer services to the clients and . Specifically for example the service offering servers store image data which is uploaded by a client into a database and manages the stored data. Images that are uploaded by clients are managed on a client by client basis so that the images are available for browsing as demanded by the client user. In addition depending on user setting it is possible to make the images available for public access via a network.

Each of the service offering servers is a server that is operated by a service provider A F that is different from others. Although these service providers A F are the same as one another in that they offer an image upload service modes of services offered thereby differ from one individual service provider to another.

Although the services offered by the service providers A F have a commonality in that each of them manages images that are uploaded by clients specific modes of services offered thereby differ from one service provider to another an example of which is shown in .

 1 The Compatible Picture Format indicates which one or both of the uploading of a still picture and the uploading of a moving picture is allowed under each service.

 2 The Public Non public Setting indicates whether it is possible to set an image that is uploaded by a client user as a publicly available image non public image or not under each service.

 3 The Album Function indicates whether it is possible to set an album as a unit of the management of images that are uploaded by a client or not under each service.

 4 The Album Title Entry indicates whether the inputting of a title for an album that is set for a group of images that are uploaded by a client is accepted or not under each service.

 5 The Image Title Entry indicates whether the titling of an image that is uploaded by a client is allowed or not under each service.

 6 The Image Description Entry indicates whether the inputting of an explanation text of an image that is uploaded by a client is allowed or not under each service.

 7 The Tag Entry indicates whether the affixing of a tag to an image that is uploaded by a client is allowed or not under each service.

 8 The Log in Parameter indicates the type of a login parameter that is required by each service A F at the time of the execution of uploading from a client.

 9 The Still Picture Maximum Size indicates the maximum size of a still image that can be uploaded that is the uploading thereof is allowed under each service.

 10 The Moving Picture Maximum Size indicates the maximum size of a moving image that can be uploaded that is the uploading thereof is allowed under each service.

 11 The Moving Picture Maximum Time indicates the maximum length of time for a moving image that can be uploaded that is the uploading thereof is allowed under each service.

 12 The Maximum Content Number indicates the maximum number of content that can be uploaded that is the uploading thereof is allowed under each service.

 15 The Upload Order indicates the sequential order of the arrangement of images that are uploaded by a client and then arranged at the time of and or for browsing under each service.

 16 The Server side Automatic Processing indicates processing which a server automatically performs at the time of upload processing under each service.

As will be understood from although the services offered by the service providers A F have a commonality in that each of them manages images that are uploaded by clients specific modes of services offered thereby differ from one service provider to another. It should be noted that are merely exemplary and other modes of services are possible. As such the present advancement is not limited in any way by the modes of service included in .

Each of the service providers A F corresponding to service offering servers of offers to clients an image upload service that is unique as explained above. Therefore it is typical that the service provider A F provides a program API that is required for upload processing to clients. Clients can perform upload processing while using the program API that is provided by the service provider .

However as has already been explained above if it is assumed that a client uses services that are offered by various service providers A F it is necessary for the client to memorize all programs APIs that are offered by these service providers A F in its memory. In addition for example when the updating of a program or the addition of a new API occurs it is necessary to respond thereto at the client side.

An information processing system according to the present advancement is provided with an interchange server in order to reduce the burden of a client.

Each of the clients and does not perform direct communication with the service offering server but performs indirect communication therewith. That is the client communicates with the interchange server whereas the client communicates with the Web server .

The client is a client that stores programs APIs for the execution of upload processing in for example a memory unit and executes processing while using them. When using a service offered by the service offering server of each service provider the client uses a common program API which is common to all of these service providers so as to perform communication with the interchange server . That is the client executes the uploading of an image the browsing of an image or the like while utilizing the service offering server through the intermediary of the interchange server .

The client is a client that does not have any program API that is applied to upload processing. Although the client does not directly communicate with the interchange server the client has a browsing function and performs the uploading of an image by means of a Web page which is offered by the Web server . That is the client executes the uploading of an image the browsing of an image or the like while utilizing the service offering server through the intermediary of the Web server and the interchange server .

The Web server is located somewhere between the interchange server and the client . On the basis of data that is offered by the interchange server the Web server creates a web page that is made up of HTML data. Then the Web server provides the created web page to the client . In addition the Web server transfers data that is sent from the client to the interchange server . For example the Web server transfers upload data to the interchange server .

The client performs processing with the use of a common program API for communication with the interchange server when any of services offered by the service offering servers is used. The same holds true for the Web server . Therefore the Web server has the same program execution function as that of the client .

Next with reference to an explanation is given of a communication processing sequence that is executed when a client uses a service that is offered by any of the service offering servers between the client and the service offering server through the intermediary of an interchange server.

Each of shows a client side user a client an interchange server and a service offering server in the order of appearance herein with the user being the leftmost one. Note that the client in corresponds to the client of . The interchange server in corresponds to the interchange server in . The service offering server in corresponds to any one of the service offering servers in .

First of all in a step S a client user launches a client program that has been stored in a client in advance. The client program is a common program that is run for a service of any of the service offering servers .

In a step S the client makes a request for a list of currently available services to the interchange server in accordance with the launched program. When the client submits such a request the client may transmit client local area information and client language information as parameters in addition to the request. Note that the parameter transmission thereof can be performed as processing that is in accordance with user setting.

In a step S the interchange server returns the requested list of currently available services to the client. The interchange server has received information on latest services from the service offering servers shown in in advance. The interchange server creates a service list that is in accordance with the pre received information and then provides the service list to the client. If the interchange server has received local area information and the language information from the client the interchange server may perform the filtering of the service list on the basis of the received information. For example if the local area of the client is Japan and the language of the client is Japanese the interchange server provides a Japanese version list to the client.

Moreover the interchange server may create and or update the service list periodically without input from the client device. For example the interchange server may update the service list in response to notification of updated services by the service offering servers in response to discovery of new service offering servers and or in response to the unavailability of service offering servers whose services are included in the service list. As can be appreciated by one skilled in the art the cases of service list update by the interchange server are merely exemplary and other cases are possible without departing from the scope of the present disclosure.

In a step S the client displays the list of currently available services that has been received from the interchange server on a display screen as for example user interface UI information. The service list is a list that shows services offered by each service provider. The service list is a UI that is set in such a manner that a user can select any service. For example the service list contains 

In a step S the client user selects a specific service from the service list and then commands the execution of processing for example the uploading of an image.

In a step S the client makes a request for detailed information on the selected service i.e. specified service to the interchange server on the basis of the inputted user instructions.

In a step S the interchange server transmits the detailed information on the selected service to the client. As has already been explained above the interchange server has received detailed information on latest services from the service offering servers shown in in advance. The interchange server selects information that corresponds to the service selected by the user out of the pre received latest service detail information and then provides the selected information to the client.

Before transmitting the detailed information the interchange server may validate the client request for detailed information. For example the interchange server may store machine specific information pertaining to the client and may use the machine specific information to validate the client request. Such machine specific information include without limitation a device ID specific to the client and a client version ID. However as can be appreciated by one skilled in the art other machine specific information is also possible such as a serial number or MAC ID.

The machine specific information is not transmitted from the client to the interchange server. Instead it is stored in the interchange server beforehand. The client may then use the machine specific information to generate a checksum that is appended to the request. The interchange server may then validate the request based on the appended checksum by using the machine specific information. Once the request is validated the interchange server transmits the detailed information to the client.

The service detail information contains information that is used for the generation of a user interface UI that is displayed on the display screen of the client when image upload processing is executed. In addition the service detail information contains information on the mode of an image that can be uploaded for example information as to which one of the uploading of a still picture and the uploading of a moving picture is allowed. The service detail information further contains information on the size of an image for example information on the size of a still picture or information on the size of a moving picture. The service detail information further contains information on parameters that are required at the time of and or for login. If there is a plurality of images that should be uploaded the service detail information further contains setting information on the sequential order of images that are to be uploaded. It should be noted that the service detail information illustrated in is merely a simplified example. That is does not show all of the service detail information. One of ordinary skill in the are will readily appreciate that other service detail information is possible without departing from the scope of the present advancement.

The service detail information contains information on the modes of services that have already been explained above while referring to . That is the service detail information contains information on 1 Compatible Picture Format 2 Public Non public Setting 3 Album Function 4 Album Title Entry 5 Image Title Entry 6 Image Description Entry 7 Tag Entry 8 Log in Parameter 9 Still Picture Maximum Size 10 Moving Picture Maximum Size 11 Moving Picture Maximum Time 12 Maximum Content Number 13 Service Logo 14 Service Trademark Credit Line 15 Upload Order and 16 Server side Automatic Processing.

In a step S a client displays a user interface UI that is used for performing image upload processing in accordance with the service detail information which has been received from the interchange server that is the selected information that corresponds to the service selected by the user.

The user interface UI that is used for performing image upload processing differs from one service to another that is depending on the service selected by the user. That is the user interface UI is generated in accordance with the service detail information that corresponds to the service provider which was selected by the interchange server in accordance with the user selected information and then sent to the client.

In a user interface UI that is used for performing image upload processing contains for example the following display data 

 b A log in information input box that is used for inputting information that is necessary for login.

 e Album information setting fields that are provided for a service that offers an album function shown for the service B of only .

In addition thereto various kinds of information are displayed as the UI depending on the service. As will be readily appreciated by one of ordinary skill in the art other user interfaces are also possible without departing from the scope of the present advancement.

In addition filtering processing may be performed so that for example any images that do not conform to the compatible picture format of the service are not displayed. Moreover the display of a trademark credit line notandums that is dos and don ts for uploading right license information EULA and the like is performed. The display of these is performed on the basis of data that is contained in the service detail information that is provided by the interchange server to the client which has already been explained above while referring to .

Referring back to the sequence charts of the communication sequence is further explained below. In the step S of the user interface UI that is used for performing image upload processing for example is presented on the display of the client.

Next in a step S of the user inputs login information authentication information in the login information input box of the presented user interface UI. The login information authentication information differs from one service provider to another. The user inputs the login information in accordance with input instructions shown on the UI. For example if the user uses the service A that is offered by the service provider A shown in the user inputs their user name as the login information authentication information as prompted in a log in information input box

On the other hand if the user uses the service B that is offered by the service provider B the user interface of is used. Therein the user inputs their e mail address as the login information authentication information as prompted in a log in information input box

In a step S the client transmits the login information authentication information to the interchange server.

In a step S the interchange server transmits the login information authentication information to one of the service offering servers of the service providers A F that has already been selected by the user. It should be noted that a program API that is provided for the transmission of login information authentication information by the service provider that has already been selected by the user is used for this login information transmission processing.

Upon the reception of the login information authentication information from the interchange server the service offering server verifies the received login information authentication information . Then if it is verified that the user is a client user person who has due upload authority the service offering server accepts a login request. In a step S the service offering server returns a login verification result Success to the interchange server and establishes a communication connection for maintaining a session.

Next in a step S the interchange server transfers the login verification result Success to the client and issues a session ID for maintaining a communication session between the client and the interchange server. Subsequent communication between the client and the interchange server is performed with the additional notation of the session ID as a parameter.

In a step S the user inputs information that is required for upload processing for example the user sets an upload image s and the like. In this step the user inputs necessary information with the use of the user interface that is provided for image upload processing a few examples of which have been explained earlier with reference to . The user creates an album and inputs a title and or a comment where necessary. Then the user issues upload instructions.

In a step S in response to the upload instructions issued by the user the client sends that is uploads image data that includes an image s to be uploaded and meta data e.g. comment to the interchange server. If a plurality of images is uploaded the sequential order of the uploading thereof is controlled in accordance with the service offered by the service provider that is selected by the user. Such control information is also contained in the service detail information that has already been explained above while referring to .

The reason why the sequential order of the uploading of a plurality of images is changed depending on the service that is selected by the user that is depending on the service provider selected thereby is that the sequential order of the display of a plurality of uploaded images differs from one service provider to another. In other words it is because the sequence format of an image list that is provided for the browsing of uploaded images varies from one service provider to another.

For example some service providers offer a list for browsing images that are arranged in the order of the uploading thereof performed by a client. That is they offer a browsing list that shows the earliest i.e. first uploaded image as the first one and later uploaded images as subsequent ones that are arranged in accordance with the sequential order of the uploading thereof.

Other service providers offer a list for browsing images that are arranged in a sequential order reverse to the order of the uploading thereof performed by a client. That is they offer a browsing list that shows the latest i.e. last uploaded image as the first one and earlier uploaded images as subsequent ones that are arranged in accordance with an order reverse to the sequential order of the uploading thereof.

An example of such an image browse list is explained while referring to . are lists for browsing uploaded images that are offered by two service providers different from each other.

If the arrangement of images contained in one image browse list that is offered to a client by one service provider differs from the arrangement of images contained in another image browse list that is offered to the client by another service provider the client user who uses various kinds of services might be confused. In order to prevent users from being confused the sequential order of uploading images is changed in such a manner that the arrangement of images contained in an image browse list is always the same regardless of which service provider is selected.

That is when a client uploads a plurality of images in a sequential manner the sequential order thereof is controlled so as to ensure that the order of display offered at the time of image browsing is always the same regardless of which service is selected.

For example the display order of images in that is the order of a list for browsing images that are arranged in the sequential order of the uploading thereof by a client is set as normal order . The display order of images in that is the order of a list for browsing images that are arranged in an order reverse to the sequential order of the uploading thereof by the client is set as reverse order .

Under such a setting if the service selected by the user is one that is offered by a service provider who offers a reverse order browsing list upload processing is performed after reversing the sequential order of a plurality of upload images when the client uploads these images.

On the other hand if the service selected by the user is one that is offered by a service provider who offers a normal order browsing list upload processing is performed without reversing the sequential order of a plurality of upload images when the client uploads these images.

Since the sequential order of the uploading of images is controlled as explained above it is possible to browse images that are presented in the form of a normal order browsing list regardless of which service provider is selected.

In the foregoing upload processing example although an explanation is given under the assumption that each of all services presents a normal order image list it is not necessarily limited thereto. That is upload processing may be performed under the setting in which a reverse order image list is presented in each of all services. Under such a modified setting if the service selected by the user is one that is offered by a service provider who offers a reverse order browsing list upload processing is performed without reversing the sequential order of a plurality of upload images when the client uploads these images.

On the other hand if the service selected by the user is one that is offered by a service provider who offers a normal order browsing list upload processing is performed after reversing the sequential order of a plurality of upload images when the client uploads these images.

Since the sequential order of the uploading of images is controlled as explained above it is possible to browse images that are presented in the form of a reverse order browsing list regardless of which service provider is selected.

As explained above when a plurality of images is uploaded in the image uploading step S of control is executed so as to change the sequential order of the transmission of the images depending on the service selected by the user.

Next in a step S the interchange server temporarily stores the image data that has been received from the client into a memory. Then the interchange server uploads the image data to the service offering server that is selected by the user.

It should be noted that a program API that is provided for upload processing by the service provider that has already been selected by the user is used for this upload processing.

In this upload processing the interchange server adds information and or corrects information where necessary. For example the interchange server processes transmission information by affixing meta data title comment and or tag to an image.

Specifically for example if data that has been transmitted from the client to the interchange server does not satisfy upload format conditions that are required by the service provider the interchange server performs the processing of the data for uploading so as to meet the required conditions.

For example in some cases the number of characters contained in a comment that is attached to an image that is included in upload data transmitted from a client to the interchange server may not be in agreement with the acceptable number of characters for the selected service provider. As another example required meta data that is not allowed to be omitted may not be affixed to an image. In such a case the interchange server performs the addition of information and or correction thereof to arrange the format thereof so as to ensure that that no uploading error occurs.

Next in a step S the interchange server transmits upload data e.g. image s meta data and the like that contains an image s that has been received from the client to the service offering server selected by the user.

The service offering server receives the upload data from the interchange server. Then the service offering server keeps and manages the received upload data under the data management policy thereof.

Next in a step S of the service offering server returns the result of upload e.g. Success Failure to the interchange server. The service offering server may return as the uploading result a URL s that is set for the uploaded image s as information for accessing the uploaded image s to the interchange server.

In a step S the interchange server transmits the result of upload together with URL information corresponding to the uploaded image s which have been received from the service offering server to the client.

Upon the reception of the URLs corresponding to the uploaded images from the service provider the interchange server may transfer the URLs corresponding to the uploaded images to the client without performing any processing thereon. Or for example in the flowchart of the interchange server may select one URL out of the URLs corresponding to the uploaded images and then send the selected URL to the client.

The operation flow of includes procedures for selecting one URL that should be provided to the client where the selection is made depending on the actual mode of upload taken by the client out of the following three upload modes.

When a client has uploaded a single image the interchange server provides a URL for direct link to the uploaded image to the client. When a client has uploaded a plurality of images to a service offering server that offers an album function the interchange server provides the URL of the front page of an album to the client. When a client has uploaded a plurality of images to a service offering server that does not offer an album function the interchange server provides the URL of the front page of the user to the client.

The flowchart of is explained below. First of all in a step S the interchange server makes a judgment as to whether the client has uploaded a plurality of images or not.

If it is judged in the step S that the client has uploaded a single image the process moves on to a step S. In the step S the interchange server provides a URL for direct link to the single uploaded image to the client.

If it is judged in the step S that the client has uploaded a plurality of images the process moves on to a step S. In the step S the interchange server judges whether the upload destination service provider offers an album service or not. That is the interchange server confirms whether the upload destination service provider offers a service for managing a group of a plurality of images uploaded in a batch transmission as an album or not.

If it is judged in the step S that the upload destination service provider offers an album management service the process goes to a step S. In the step S the interchange server provides the URL of an album front page to the client.

On the other hand if it is judged in the step S that the upload destination service provider does not offer an album management service the process goes to a step S. In the step S the interchange server provides the URL of a user front page to the client.

As explained above the interchange server selects one URL and then provides the selected URL to the client. If such URL selection processing is performed it is possible for the user to browse images in an efficient manner while utilizing the optimally selected URL. The interchange server executes the URL selection processing explained above as procedures common to all service providers.

Referring back to the entire sequence is further explained below. In the step S the interchange server transmits the result of upload together with URL information corresponding to the uploaded image s which have been received from the service offering server to the client.

Finally in the step S the client displays the result of the upload and the URL s on the display screen and then terminates the processing. The URL s is stored in the memory unit nonvolatile memory of the client. The stored URL is used at the time of the execution of browsing processing.

In the foregoing description it is assumed that the sequence explained above while referring to is performed as communication processing between the client and the service offering server through the intermediary of the interchange server of .

If the sequence is performed as processing between the client and the service offering server through the intermediary of the Web server and the interchange server of the processing between the interchange server and the service offering server is performed as the same processing as that performed between the interchange server and the service offering server that is explained above with reference to .

In addition the processing between the interchange server and the Web server is performed in the same manner as performed between the interchange server and the client that is explained above with reference to . The processing between the client and the user that is explained above with reference to is performed as the processing between the Web server the client and the user.

The Web server creates a web page in an HTML data format in accordance with the data that has been received from the interchange server . Then the Web server presents the created web page to the client . The client uses its browser function to display the web page provided by the Web server .

The user uses the web page that is displayed on the client as user interface and performs the inputting of data the setting of an upload image s and the like. Then the user transmits data including the upload image s with the use of the web page to the Web server . As done by the client A the Web server uses a common program API which is common to all service providers so as to perform communication with the interchange server . By this means the Web server transmits upload information that has been received from the client to the interchange server .

Through such processing the client which is a client that does not have any program API that is applied to upload processing can execute the same image upload processing as that of the client .

As explained above when a service offered by any of the service offering servers is used it is not necessary for the clients and to switch to a program API that is uniquely applied to the selected service. This is thanks to the intermediary of the interchange server.

When any service offered by the service offering servers is used each of the client and the Web server can use a common program API for communications with the interchange server.

An example of the application of APIs is explained below while referring to . Each of includes a client an interchange server and a service offering server in the order of appearance herein as viewed from left to right. The client of corresponds to the client of or the Web server that performs communication with the client of . The interchange server shown therein corresponds to the interchange server of . The service offering server shown therein corresponds to any of the service offering servers of .

A set of sequence charts of include the sequence of the uploading of an image s by the client to the service offering server through the intermediary of the interchange server as has already been explained above while referring to . The sequence charts of are an example of an API that is used by the client or Web server and an API that is used by the interchange server.

When any service that is offered by the service offering servers of is used the client can use an API that is common thereto i.e. common API . Upon the selection of one service at the client side the selected service is notified to the interchange server. Accordingly it should be noted that once one service has been determined at the client side the interchange server uses an API that corresponds to the service selected by the client so as to perform communication processing with the service offering server that offers the selected service.

First of all in a step S the client uses i.e applies a common API GET services so as to make a request for the acquisition of a service list. The API GET services is an API that causes a program that defines a sequence for making a request for a service list to the interchange server to be executed. In a step S the interchange server transmits a service list to the client in response to the request issued from the client.

Next in a step S the client uses a common API GET service so as to make a request for the acquisition of service detail information. The API GET service is an API that causes a program that defines a sequence for making a request for service detail information to the interchange server to be executed. Note that the client transmits the identifier of the selected service to the interchange server when making a request for service detail information to the interchange server.

In a step S in response to the request made by the client the interchange server sends service detail information that corresponds to the service selected by the client. The service detail information is for example information that has been explained earlier while referring to .

Next in a step S of the client inputs login information in the login information input box of a user interface UI refer to that is displayed on a display screen so as to be used for performing image upload processing on the basis of the service detail information. In this way login processing is performed in the step S. The API used for login processing is a common API GET login in step S of . The API GET login is an API that causes a program that defines a sequence for transmitting login information to the interchange server to be executed.

In response to the inputting of login information by the client the interchange server performs login to the service offering server that corresponds to the service selected by the client. An API that is provided by the service provider that corresponds to the service selected by the client is used for this login processing. That is it is executed as login processing that corresponds to a sequence that is unique to the selected service provider.

In at step S processing is performed in a case where the client has selected the service A whereas at steps S S processing is performed in a case where the client has selected the service B. For example the processing of the step S is executed for log in to the service offering server A which offers the service A. A unique API GET login that is supplied from the service provider A which manages the service offering server A is applied to this login processing. The interchange server has been set in advance in such a manner that it can use all APIs that are supplied from all service providers. Having been preset as above the interchange server selects one API that should be applied on the basis of the service selection information that is sent from the client and then uses the selected API.

If the client has selected the service B the steps S S are executed for login to the service offering server B. In order to log in to the service offering server B which offers the service B three APIs that are unique to the service B are used. More specifically GET getservicetoken GET servicelogin and GET getsession are used for log in to the service offering server B. Processing for log in to the service offering server B is executed with the application of these three APIs.

If the client executed login directly to the service offering server B which offers the service B it would be necessary for the client to use these three APIs unlike the configuration according to the present embodiment of the invention. In this respect however since the interchange server executes service login to the selected service in place of the client in the configuration according to the present embodiment of the invention it is possible for the client to always use a common API step S irrespective of which service is used.

The common API POST upload is an API that is used for transmitting upload image s and inputted data that are set in the upload image setting box of the image uploading user interface UI refer to to the interchange server.

Upon the reception of the upload data from the client as done in the login processing explained above the interchange server uses an API that is provided by the service provider that corresponds to the service specified by the client so as to execute image upload processing. That is the interchange server executes image upload processing that corresponds to a sequence that is unique to the selected service provider.

In at step S processing is performed in a case where the client has selected the service A whereas at step S processing is performed in a case where the client has selected the service B. For example the processing of the step S is executed for uploading an image s to the service offering server A which offers the service A. A unique API POST upload A that is supplied from the service provider A which manages the service offering server A is applied to this image upload processing.

The processing of the step S is executed for uploading an image s to the service offering server B which offers the service B. A unique API POST upload B that is supplied from the service provider B which manages the service offering server B is applied to this image upload processing.

As explained above in the configuration according to the present embodiment of the invention the interchange server performs processing while using an API that corresponds to the service offering server so as to perform processing in accordance with a sequence that is unique to the service offering server. In contrast it is possible for the client to perform processing while using a common API which is common to all service offering servers irrespective of which service is used.

In addition in a case where a program API is updated at the service offering server the interchange server acquires the updated program API and uses thereof which makes it unnecessary for the client to perform any updating processing for the program API. Thus the burden of the client is substantially reduced.

As has already been explained above the client that performs processing with the use of the common API of is not limited to the client of . That is the Web server also performs processing with the use of the common API.

With reference to an example of the hardware configuration of each of a client an interchange server and a service offering server is explained below.

In the client is provided with a control unit that performs data processing while using various programs APIs a communication unit that performs communication via a network a memory unit that memorizes programs APIs parameters image data and the like a display unit that displays for example an image and a user interface and an input unit that inputs user manipulation information. The display unit may function also as the input unit if for example the client has a configuration that accepts an input via UI. An example of such a configuration is a touch panel UI.

As has already been explained in the foregoing exemplary embodiment of the present advancement the control unit of the client selectively applies a plurality of APIs Application Programming Interface that define execution processing and performs communication with a service offering server through the intermediary of an interchange server so as to use a service that is offered by the service offering server. When using any service among a plurality of services different from one another which are offered by a plurality of service offering servers the control unit performs processing with the use of a common API.

When performing processing for the use of a service for example the control unit uses the common API so as to transmit service selection information to the interchange server and receives service detail information corresponding to the selected service from the interchange server the control unit uses user interface generation information that is contained in the received service detail information so as to display a user interface and the control unit uses the common API so as to transmit information that is inputted via the user interface to the interchange server.

As has been explained earlier while referring to the common API includes a login processing execution API which defines login functions that should be executed for using a service that is offered by the service offering server. When using the service offering server the control unit uses after that login information defined in a user interface generated on the basis of the service detail information has been inputted the login functions so as to transmit the login information to the interchange server. The interchange server uses the login information that is received from the client so as to execute a login processing sequence that is unique to the service offering server that corresponds to the service selected by the client.

In addition the common API includes an image upload function that is to be used for executing image upload processing which is a service that is offered by the service offering server. When using the service offering server the control unit uses after that data has been inputted in an upload image setting portion defined in a user interface generated on the basis of the service detail information the image upload function so as to transmit upload information to the interchange server. The interchange server uses the upload information that is received from the client so as to execute an upload processing sequence that is unique to the service offering server that corresponds to the service selected by the client.

As has already been explained above the service detail information includes upload sequential order prescription information that prescribes upload sequential order for uploading a plurality of images to the service offering server. When a plurality of images is to be uploaded to the service offering server the control unit performs image upload processing in accordance with the upload sequential order prescription information.

Other functions are also included in the common API. For example an albums function is included to determine a listing of client albums on a service offering server to which the client is logged in. A new album function may be used to create new client albums on the service offering server. Further an image function may be used to display at the client images stored on the service offering server and an assets function may be used to determine client assets stored on the service offering server. Client assets including for example photos videos audio files and other media. As will be appreciated by one skilled in the art other functions are also possible without departing from the scope of the present disclosure.

In the interchange server is provided with a control unit that performs data processing while using various programs APIs a communication unit that performs communication via a network and a memory unit that memorizes programs APIs parameters image data and the like.

The control unit of the interchange server provides service detail information corresponding to a service selected by a client to the client on the basis of service selection information that has been received from the client. Then the control unit of the interchange server receives data that has been inputted via a user interface generated on the basis of the service detail information from the client and then transfers the received data to the service offering server that corresponds to the selected service.

Moreover as has been explained earlier while referring to the control unit uses a unique API which is unique to the service offering server that offers the service selected by the client so as to execute a login processing sequence that is unique to the service offering server or an upload processing sequence that is unique to the service offering server upon the reception of login information or upload data from the client.

Furthermore the control unit of the interchange server receives URLs from the service offering server as information for accessing the data uploaded from the client and performs URL selection processing so as to select a URL that should be transmitted to the client on the basis of the upload data or the modes of service offered by the service offering server. This is the selection processing that has already been explained above while referring to the flowchart of .

The service offering server is provided with a control unit that performs data processing while using various programs APIs a communication unit that performs communication via a network and a memory unit that memorizes programs APIs parameters image data and the like.

Note that a Web server has basically the same configuration as that of the client shown in except that the Web server is not provided with the display unit and the input unit of the client . Each of the clients and has fundamentally the same configuration as that of the client shown in except that the program API execution function of the client is inferior to that of the client . Despite the fact that the program API execution function of the client is inferior to that of the client since the client B is provided with a browsing function the client can perform image upload processing and browsing processing just in the same manner as done by the client by displaying a web page that is presented by the Web server.

A series of processing that is explained in this specification can be implemented by means of hardware software or a combination of hardware and software. If the series of processing that is explained in this specification is implemented by means of software a set of computer readable instructions may be installed in a memory of a computer that is built in dedicated hardware or installed in a general purpose computer that is capable of performing various kinds of processing. For example the computer readable instructions may be pre stored in a computer readable recording medium. The computer readable instructions may be installed on a computer from a recording medium or the computer readable instructions may be received via a network such as LAN Local Area Network or the Internet and then installed on a recording medium such as an internal integral hard disk or the like.

Note that computer readable instructions according to an aspect of the advancement are for example a computer program that can be provided to a general purpose computer system that can execute various program codes in a computer readable form of a storage medium or a communication medium. Since such a program is provided in the computer readable form processing is achieved in accordance with the program on the computer system.

Further various kinds of processing that are described in this specification are not necessarily executed in time series in accordance with the order of appearance in this specification. That is depending on the processing capability of an apparatus apparatuses that performs processing and or according to need processing may be performed in a parallel manner or on an individual basis. The term system used in this specification means a logical set of a plurality of apparatuses. It should be noted that the apparatuses are not necessarily built in the same single frame housing.

As explained above an image processing system according to an exemplary embodiment of the invention includes a plurality of service offering servers a client that uses services offered by the plurality of service offering servers and an interchange server that performs intermediary processing when the client uses a service. In such a configuration the client performs communication with the interchange server while using a common API when using any service among a plurality of services different from one another which are offered by the plurality of service offering servers. The interchange server uses a unique API which is unique to the service offering server that offers the service selected by the client so as to execute a processing sequence that is unique to the service offering server. Such a configuration makes it possible for the client to use any service among services offered by the plurality of service offering servers with the use of a common API without any need to use a unique API which is unique to each of the plurality of service offering servers.

Obviously numerous modifications and variations of the present invention are possible in light of the above teachings. It is therefore to be understood that within the scope of the appended claims the invention may be practiced otherwise than as specifically described herein.

