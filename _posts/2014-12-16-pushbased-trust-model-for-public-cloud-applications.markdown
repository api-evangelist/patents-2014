---

title: Push-based trust model for public cloud applications
abstract: In accordance with the exemplary embodiments of the invention there is at least a method and apparatus to perform operations including deploying, with a device of a private network, an application instance with an application web service in a cloud network; and based on the deploying, communicating with the application web service in the cloud network to establish a trust relationship with the application web service for the application instance.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09473482&OS=09473482&RS=09473482
owner: Nokia Technologies Oy
number: 09473482
owner_city: Espoo
owner_country: FI
publication_date: 20141216
---
This patent application claims priority under 35 U.S.C. 119 e from U.S. Provisional Patent Application No. 61 919 164 filed Dec. 20 2013 the disclosure of which is incorporated by reference herein in its entirety.

The teachings in accordance with the exemplary embodiments of this invention relate generally to cloud centric application trust validation and more specifically relate to a solution to deploy sensitive applications to a public cloud by utilizing a model where master keys are reliably pushed to the cloud from a trusted zone such as within a corporate network.

This section is intended to provide a background or context to the invention that is recited in the claims. The description herein may include concepts that could be pursued but are not necessarily ones that have been previously conceived or pursued. Therefore unless otherwise indicated herein what is described in this section is not prior art to the description and claims in this application and is not admitted to be prior art by inclusion in this section.

Certain abbreviations that may be found in the description and or in the Figures are herewith defined as follows 

Cloud computing is an approach to sharing computing resources over the Internet. One area of cloud computing includes a host provider for example cloud provider providing virtual server instances on which devices can run applications. Public Cloud Applications often need to secure sensitive information such as data encryption keys or user system credentials. Main challenges in securing such information are to deliver master keys to cloud applications and to establish trust to instances and applications running in public cloud environment. Examples of applications available in such a cloud environment can include social media applications and applications provided by Yahoo EBay and Amazon to name only a few. As these applications are run in a cloud separate from a private cloud device and its application service provider special attention needs to be given to application data security. In this regard at least a problem exists in that application data security may not be trusted to be provided by the cloud provider. This invention presents solutions to at least the above described problems.

In an exemplary aspect of the invention there is a method comprising deploying with a device of a private network an application instance with an application web service in a cloud network and based on the deploying communicating with the application web service in the cloud network to establish a trust relationship with the application web service for the application instance.

In another exemplary aspect of the invention there is an apparatus comprising at least one processor and at least one memory including computer program code where the at least one memory and the computer program code are configured with the at least one processor to cause the apparatus to at least deploy with a device of a private network an application instance with an application web service in a cloud network and based on the deploying communicate with the application web service in the cloud network to establish a trust relationship with the application web service for the application instance.

In another exemplary aspect of the invention there is an apparatus comprising means for deploying with a device of a private network an application instance with an application web service in a cloud network and means based on the deploying for communicating with the application web service in the cloud network to establish a trust relationship with the application web service for the application instance.

In accordance with the exemplary embodiments as described in the paragraph above the means for deploying and the means for communicating comprises an interface to a communication network and a computer readable medium including computer program code the computer program code executed by at least one processor.

The exemplary embodiments of the invention provide at least a method to provide cloud centric trust validation including deploying sensitive applications to a public cloud by utilizing a model and pushing master keys to the cloud from a trusted zone such as within a corporate network.

Current state of technology depends on encryption operations and key management systems deployed within public cloud environments and or leveraging trust validation solution that exclusively or significantly depend on validation of applications from within the public cloud. Both of these factors will pose various security and compliance risks to users and other entities.

Establishing trust between cloud applications and corporate network is usually done using pull mechanism where cloud application connects to a corporate network and identifies itself with specific authentication information such as SSH keys or other credentials. The challenge in this kind of model is how to deliver that authentication information to cloud applications in the first place. Previous solutions have not been very secure because of a chicken and egg type of situation or they ve been very dependent on specific cloud provider security controls. The exemplary embodiments of the invention provide at least a method and apparatus to push master keys generated for a private network such as a corporate network for establishing a most secure trust between the cloud applications and the corporate network.

This invention presents a model where only non sensitive information is required to be stored to cloud and using that public and non sensitive information corporate network can safely and securely deploy new applications by pushing the required master keys to new cloud instances. Exemplary embodiments of the invention are described in at least .

Although the invention may be described and or illustrated using references to particular entities such as Nokia and Amazon the use of these entities is non limiting and the invention can be practiced to the benefit of any entities which incorporate similar technology.

In accordance with an exemplary embodiment of the invention which will be described in more detail below there is at least a method to deploy sensitive applications to a public cloud by utilizing a model where master keys are pushed to the cloud from a trusted zone such as within a corporate network.

Before describing in further detail the exemplary embodiments of this invention reference is made to for illustrating a simplified block diagram of various electronic devices and apparatus that are suitable for use in practicing the exemplary embodiments of this invention.

The server of can be associated with a public cloud . The server includes a controller such as at least one computer or a data processor DP A at least one computer readable memory medium embodied as a memory MEM B that stores a program of computer instructions PROG C and at least one suitable RF transceiver D for communication with the ED via antennas F several when MIMO operation is in use . The server is coupled via a data control path F to the ED . The path F may be implemented such as by a wired and or wireless connection. The server can also be coupled to another device such as via the data control path F to the KMS .

The ED includes a controller such as at least one computer or a data processor DP A at least one non transitory computer readable memory medium embodied as a memory MEM B that stores a program of computer instructions PROG C and at least one suitable radio frequency RF transmitter and receiver pair transceiver D for bidirectional wireless communications with the key management system the application server and or another device associated with the cloud via an antenna or antennas F and or a hardwired connection. In addition the KMS may be directly or indirectly connected to the ED such as via a connection F.

For the purposes of describing the exemplary embodiments of this invention the application server the application provider device and or the key management system may be assumed to include a trust establishmnent function TEF . The TEF G TEF G and or the TEF G are assumed to be configured to operate in accordance with the non limiting examples of the embodiments of this invention as described herein.

At least one of the programs C C and C is assumed to include program instructions that when executed by the associated data processor enable the device to operate in accordance with the exemplary embodiments of this invention as will be discussed below in greater detail. That is the exemplary embodiments of this invention may be implemented at least in part by computer software executable by the DP A DP A and or DP A or by hardware or by a combination of software and hardware and or firmware . Likewise the TEF G TEF and the TEF G may be implemented at least in part by executable computer software or by hardware or by a combination of software and hardware and firmware .

The various data processors memories programs transceivers and interfaces depicted in may all be considered to represent various means for performing operations and functions that implement the several non limiting aspects and embodiments of this invention.

In general the various embodiments of the ED may include but are not limited to a server cellular mobile devices personal digital assistants PDAs having wireless and or wired communication capabilities portable computers having communication capabilities GPS devices image capture devices such as digital cameras having communication capabilities gaming devices having communication capabilities music storage and playback appliances having communication capabilities Internet appliances permitting wireless Internet access and browsing as well as portable units or terminals that incorporate combinations of such functions.

The computer readable memories B B and B may be of any type suitable to the local technical environment and may be implemented using any suitable data storage technology such as semiconductor based memory devices random access memory read only memory programmable read only memory flash memory magnetic memory devices and systems optical memory devices and systems fixed memory and removable memory. The data processors A A and A may be of any type suitable to the local technical environment and may include one or more of general purpose computers special purpose computers microprocessors digital signal processors DSPs and processors based on multi core processor architectures as non limiting examples.

Application data security in cloud is reliant on application credential and or key security. Sensitive data associated with an application running in a cloud provider network and or a public cloud can more easily be compromised. The exemplary embodiments of the invention include a method and apparatus to provide with an application service provider or a third party provider who is separate from the cloud provider a unique key and or master key which can be used by an application server and a private cloud device to authenticate an application running in a public cloud. The method in accordance with the exemplary embodiments providing novel authentication means and protection against security threats when running such cloud centric applications as will be described in more detail below.

Most AWS deployments need to secure some kind of sensitive information database encryption keys passwords to mount volumes user system credentials in configuration files. However at least for applications that maintain classified or restricted data a master key KEK can be provided from an independent and trusted location outside of AWS.

There are many alternatives for providing the master key from a trusted location. Due to increased complexity implementing these alternatives can be quite challenging especially when deployments must be automated. The exemplary embodiments of the invention provide novel different alternatives for providing a master key are described in this application.

These features blocks of are described as follows with regards to an SSH based trust model establishment and application provisioning in the cloud features blocks. In accordance with the exemplary embodiments of the invention as illustrated in there is at 

The feature blocks of are described as follows with regards to an API based trust model establishment and application provisioning in the cloud. In accordance with the exemplary embodiments of the invention as illustrated in there is at 

In accordance with the exemplary embodiments of the invention as described in the paragraph above the deployment script is defined in a machine image for the application instance.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above the machine image when started passes at least one of a username and password or a security key to the application instance.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above the communicating comprises connecting to the application image using the security key passed to the application instance deploying a child certificate into the application image for the trusted relationship.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above there is after the connecting assigning secrets read from environmental variables to the application instance for the trusted relationship wherein the environmental variables are from a location controlled by the private network.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above the machine image when started for the application instance loads a deployment agent to connect back to the private network.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above a validation of the connection back is performed based at least one of a username and password or the security passed to the application instance.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above based on the validating a child certificate and corresponding configuration information is assigned to the application instance.

In accordance with the exemplary embodiments of the invention as described in the paragraphs above the deployment script comprises an auto scaling rule.

In accordance with the exemplary embodiments of the invention there is An apparatus comprising means for deploying with a device of a private network an application instance with an application web service in a cloud network and means based on the deploying for communicating with the application web service in the cloud network to establish a trust relationship with the application web service for the application instance.

In accordance with the exemplary embodiments of the invention as described in the paragraph above the means for communicating and deploying comprises an interface to a communication network and a computer readable memory embodying computer program code the computer program code executed by at least one processor.

The foregoing description has provided by way of exemplary and non limiting examples a full and informative description of the best method and apparatus presently contemplated by the inventors for carrying out the invention. However various modifications and adaptations may become apparent to those skilled in the relevant arts in view of the foregoing description when read in conjunction with the accompanying drawings and the appended claims. However all such and similar modifications of the teachings of this invention will still fall within the scope of this invention.

It should be noted that the terms connected coupled or any variant thereof mean any connection or coupling either direct or indirect between two or more elements and may encompass the presence of one or more intermediate elements between two elements that are connected or coupled together. The coupling or connection between the elements can be physical logical or a combination thereof. As employed herein two elements may be considered to be connected or coupled together by the use of one or more wires cables and or printed electrical connections as well as by the use of electromagnetic energy such as electromagnetic energy having wavelengths in the radio frequency region the microwave region and the optical both visible and invisible region as several non limiting and non exhaustive examples.

Furthermore some of the features of the preferred embodiments of this invention could be used to advantage without the corresponding use of other features. As such the foregoing description should be considered as merely illustrative of the principles of the invention and not in limitation thereof.

