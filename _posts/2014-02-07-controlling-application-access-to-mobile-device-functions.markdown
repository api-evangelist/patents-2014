---

title: Controlling application access to mobile device functions
abstract: There is described a method of controlling application access to predetermined functions of a mobile device (), the method comprising (a) providing a set of keys, each key corresponding to one of the predetermined functions, (b) receiving () an application from an application provider () together with information identifying a set of needed functions, (c) generating a signed application by signing the received application with each of the keys that correspond to one of the needed functions identified by the received information, and (d) transmitting () information identifying the needed functions and the signed application and a set of access rules to a Secure Element of the mobile device (). There is also described a device for controlling application access and a system for controlling and authenticating application access. Furthermore, there is described a computer program and a computer program product.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09226143&OS=09226143&RS=09226143
owner: NXP B.V.
number: 09226143
owner_city: Eindhoven
owner_country: NL
publication_date: 20140207
---
This application claims the priority under 35 U.S.C. 119 of European patent application no. 13154657.4 filed on Feb. 8 2013 the contents of which are incorporated by reference herein.

The present invention relates to the field of controlling application access to certain functions of a mobile device such as functions relating to NFC Near Field Communication and SEs Secure Elements .

Recent mobile communication devices such as e.g. cellular phones smartphones PDAs and tablets are often equipped with various advanced technologies for handling and using sensitive information. An example of such technologies is the combination of NFC and Secure Elements which may e.g. be used in connection with various payment applications which involve use of sensitive information such as credit card information bank account numbers passwords etc. This sensitive information has to be protected but at the same time the applications need to be able to access the relevant secure functions in order to serve their intended purpose.

Some mobile device operating systems such as the Android based operating systems include functions for authenticating applications. This may be done by determining whether the application is genuine i.e. by validating that the application has been signed by the application provider. However the number of secure functions which an application actually needs to access may differ in dependence on its specific purpose. Accordingly simply giving an application access to all or none of the secure functions may constitute a security risk in cases where an application is allowed to access more secure functions than it actually needs. Furthermore when a new application provider enters the market authentication of applications provided by the new provider will not be possible until the mobile operating system has been updated to include the corresponding certificate.

In view of the above it has been suggested to let a trusted third party also referred to as a Trusted Service Manager or TSM sign the applications with keys corresponding to the functions or sets of functions which the application needs to access. By storing corresponding certificates in the operating system of the mobile device the mobile device may determine whether an application s request for accessing a particular function should be allowed by verifying whether the application has been signed accordingly. Although this approach overcomes many of the problems described above it still suffers from some drawbacks.

One drawback is that the access certificates are pre installed as part of the mobile device operating and may therefore not be accessible to the TSM in case the TSM needs to manage the certificates e.g. upon expiry of a certificate or in order to delete replace or add a new certificate. Thus an over the air OTA update is required to perform the desired certificate management.

A further drawback is that it is difficult to change application permissions once these have been granted by signing the application at the TSM. More specifically a removal or change of access permissions for one or more installed applications while other applications are still allowed access will require that these other application are signed anew with new valid certificates. Again an additional OTA which involves OEM original equipment manufacturer and or MNO mobile network operator interaction is required to update the access certificates.

Finally having different TSMs and hence different access certificates in different geographical regions forces the OEM to provide different i.e. region specific operating system image builds.

There may accordingly be a need for an improved way of controlling application access to secure functions of mobile devices without the drawbacks described above.

This need may be met by the subject matter according to the independent claims. Advantageous embodiments of the present invention are set forth in the dependent claims.

According to a first aspect there is provided a method of controlling application access to predetermined functions of a mobile device the method comprising a providing a set of keys each key corresponding to one of the predetermined functions b receiving an application from an application provider together with information identifying a set of needed functions c generating a signed application by signing the received application with each of the keys that correspond to one of the needed functions identified by the received information and d transmitting information identifying the needed functions and the signed application and a set of access rules to a Secure Element of the mobile device.

This aspect is based on the idea that by associating each of the mobile device s predetermined functions with a unique key access to a particular set of the predetermined functions can be controlled for a given application by signing the application with the keys corresponding to the particular set of functions. Thereby the mobile device is able to determine which of its predetermined functions a given application is allowed to access by checking which keys the application has been signed with. Furthermore by transmitting information identifying the needed functions and the signed application and a set of access rules to the Secure Element of the mobile device the access rules can be defined and even amended without the need for updating the operating system of the mobile device.

In the present context the term mobile device may particularly denote a mobile communication device such as a mobile phone a smart phone a personal digital assistant PDA a tablet computer a laptop or any similar device capable of communication via a data communication network such as cellular communication network or a wired or wireless data network.

In the present context the term predetermined functions may particularly denote a selection of functions or features provided by a mobile device operating system and or mobile device hardware. In some embodiments a predetermined function may particularly denote a group of functions which together provide a certain service or feature which an application may want to access.

In the present context the term information identifying a set of needed functions may in particular denote a list e.g. in a text file of those of the predetermined functions which the application needs to be able to use.

In the present context the term keys may particularly denote cryptographic keys which can in particular be used to electronically sign a file or a set of data by applying a suitable cryptographic algorithm to the file or set of data together with the key.

In the present context the term application may particularly denote a program for a mobile device such as the program applications commonly referred to as apps or a remote application residing at a location external to the mobile device e.g. in the cloud .

In the present context the term signed application denotes an installation file or an executable file or program which has been signed with one or more cryptographic keys.

In the present context the term application provider may particularly denote a server or an entity which directly or indirectly makes applications available to users of mobile devices. In other words the application provider may be a developer or an application store through which the application is available for download to mobile devices.

In the present context the term needed functions may particularly denote a subset of the predetermined functions which the application needs to be able to access in order to perform as intended by the application developer.

In the present context the term access rules may particularly denote a rule specifying that a particular application should be given access to a particular function provided the particular application has been signed with a key corresponding to a particular certificate.

In the present context the term Secure Element may particularly denote a Secure Element as specified by the GlobalPlatform standard.

By signing the application with those keys that correspond to the set of functions which the applications needs to be able to access it becomes possible to determine whether the application is authorized to access a particular function or not by checking whether the application has been signed with the key corresponding to the particular function. Further by storing information identifying the needed functions and the signed application and a set of access rules in the Secure Element of the mobile device the access rules can be defined and even amended without the need for updating the operating system of the mobile device. The transmission of the information and access rules to the Secure Element is secure in the sense that the transmitting party or device such as a TSM Trusted Service Manager has to be authorized to access the Secure Element and also in the sense that the transmission takes place via a secured i.e. encrypted connection to the Secure Element.

Thereby application access to the predetermined functions can be managed updated and controlled in a simple and secure way without the need for OEM MNO interaction for an OTA update of the mobile device. In particular the security can be ensured by assuring that the set of keys used to sign the application is kept confidential e.g. at a designated entity.

According to an embodiment the transmitted information includes a set of function identifiers and an application identifier.

In other words the application is identified by a unique application identifier and each of the functions is identified by a unique function identifier.

According to a further embodiment the method further comprises transmitting the signed application to the application provider.

Thereby the application provider is able to distribute the signed application to users of mobile devices such that the users may use the application.

According to a further embodiment the method further comprises transmitting a set of certificates corresponding to the set of keys together with information mapping each certificate to one of the predetermined functions to the Secure Element of the mobile device.

In the present context the term certificate may particularly denote a data element or file which is related to a key in such a way that by applying a cryptographic algorithm to the certificate and a file such as an application it can be determined whether the file e.g. application has been signed with the key. A certificate may also be referred to as a public key .

In the present context the term mapping may particularly denote a relationship between corresponding items in two distinct groups. In other words the mapping between certificates and predetermined functions may determine e.g. in a table or similar structure which key corresponds to which predetermined function.

Upon receiving the set of certificates and the mapping information the mobile device can store these items in the Secure Element of the mobile device. Thereby the will be able to apply the certificates and mapping information in order to determine whether a request from an application to access a particular function should be granted.

According to a further embodiment the step of generating a set of keys comprises a transmitting an initial set of keys to an owner of the predetermined functions wherein each key of the initial set of keys corresponds to one of the predetermined functions b at the owner root signing each key of the transmitted initial set of keys and c receiving the set of keys which has been root signed by the owner.

In the present context the term owner of the predetermined functions may in particular denote a server belonging to the entity that provides the hardware and or software which performs the predetermined functions.

By having the keys root signed by the owner it can be assured that only keys validated by the owner can be used to authorize access to the predetermined functions. Thereby by letting the owner act as a certificate authority CA security can be further improved.

According to a further embodiment the predetermined functions relate to mobile device services involving Near Field Communication NFC and or the Secure Element SE .

By signing applications with a number of keys where each key is associated with a particular function relating to e.g. use of the NFC and or SE features of a mobile device it becomes possible to control how many and which specific functions each application is allowed to access and use. In other words access to the predetermined functions can be controlled in a dynamic and scalable manner without interaction from OEM and or MNO as required for a OTA update of the mobile device operating system.

According to a further embodiment the method further comprises determining whether the received application is to be signed based on an identity of the application provider wherein the step of generating a signed application is only carried out if it is determined that the received applications is to be signed.

The determination of the whether the received application is to be signed may e.g. be based on checking a list of approved application providers e.g. application providers which have a corresponding business agreement with the involved parties such as a trusted service manager TSM who performs the checking and signing a function owner and a mobile device manufacturer.

According to a second aspect there is provided a device for controlling application access to predetermined functions of a mobile device the device comprising a a unit adapted for generating a set of keys each key corresponding to one of the predetermined functions b a unit adapted for receiving an application from an application provider together with information identifying a set of needed functions c a unit adapted for generating a signed application by signing the received application with each of the keys that correspond to one of the needed functions identified by the received information and d a unit adapted for transmitting information identifying the needed functions and the signed application and a set of access rules to a Secure Element of the mobile device.

The device according to the second aspect is adapted to perform the method according to the first aspect or any of the above described embodiments.

The units of the device may be implemented as separate hardware units or as functional units in a single hardware unit such as a server.

The unit adapted for receiving an application together with information may receive the aforementioned items from the application provider via a network connection e.g. through the Internet or by means of any suitable input interface such as via USB optical or other storage media.

The device can e.g. as an independent server provide a secure and effective way of controlling application access to sensitive functions in mobile devices. In particular by using a key for each predetermined function it is possible to allow a given application to access exactly the needed sensitive functions instead of merely giving full access or no access at all. Thereby the device allows for scalable and dynamic access control.

According to a third aspect there is provided a system for controlling and authenticating application access to predetermined functions of a mobile device the system comprising a a device according to the second aspect b an application provider and c a mobile device comprising a Secure Element wherein d the application provider is adapted to transmit an application together with information identifying a set of needed functions to the device e the device is adapted to generate a signed application based on an application and information identifying a set of needed functions received from the application provider f the device is adapted to transmit the signed application to the application provider g the device is adapted to transmit information identifying the needed functions and the signed application a set of access rules and a set of certificates corresponding to the generated set of keys together with information mapping each certificate to one of the predetermined functions to the Secure Element of the mobile device and h the mobile device is adapted to store the information identifying the needed functions and the signed application the set of access rules and the set of certificates and the mapping information in the Secure Element.

The transmissions between the application provider and the device as well as from the device to the mobile device may preferably be performed via a communications network such as the Internet or any other suitable way of transmission. The transmissions are preferably secure such that unauthorized parties can neither access the transmitted data nor transmit false data to any of the authorized parties i.e. device application provider and mobile device.

The system according to this aspect is based on the idea that by associating each of the mobile device s predetermined functions with a unique key access to a particular set of the predetermined functions can be controlled for a given application by signing the application with the keys corresponding to the particular set of functions and storing corresponding access rules in the Secure Element of the mobile device.

According to an embodiment the mobile device is further adapted to retrieve access rules stored in the Secure Element and to apply the retrieved access rules in order to determine whether an application is to be allowed access to a function.

In other words when an application requests access to a particular function the mobile device retrieves the relevant access rules by sending a corresponding request to the Secure Element. Based on the retrieved access rules the mobile device then determines whether access to the requested function is to be granted or not.

According to a further embodiment the system comprises an owner of the predetermined functions the owner being adapted to receive an initial set of keys from the device wherein each key of the initial set of keys corresponds to one of the predetermined functions the owner being further adapted to root sign each key of the received initial set of keys and to transmit the root signed keys to the device.

By having the keys root signed by the owner it can be assured that only keys validated by the owner can be used to authorize access to the predetermined functions.

According to a further embodiment the mobile device is adapted to receive a signed application from the application provider and to determine which of the predetermined functions the signed application is authorized to access based on the set of certificates and the access rules stored in the Secure Element.

Thereby the mobile device is able to determine which of its predetermined functions a given application is allowed to access by checking which keys the application has been signed with and utilizing the access rules and the stored mapping information.

The determination may e.g. be performed by the mobile device during installation of the application and or every time the application attempts to access one of the predetermined functions. Alternatively the mobile device may refer to a stored cached authentication result from a previous attempt. With the latter approach the use of processing resources as well as time consumption can be reduced.

Further enhancement of security may be achieved by verifying that the trust chain of the certificate contains the issuer identity of the root signer.

According to a fourth aspect there is provided a computer program comprising computer executable instructions which when executed by a computer causes the computer to perform the steps of the method according to the first aspect or any of the above embodiments thereof.

According to a fifth aspect there is provided a computer program product comprising a computer readable data carrier loaded with a computer program according to the fourth aspect.

It has to be noted that embodiments of the invention have been described with reference to different subject matters. In particular some embodiments have been described with reference to method type claims whereas other embodiments have been described with reference to apparatus type claims. However a person skilled in the art will gather from the above and the following description that unless otherwise indicated in addition to any combination of features belonging to one type of subject matter also any combination of features relating to different subject matters in particular a combination of features of the method type claims and features of the apparatus type claims is part of the disclosure of this document.

The aspects defined above and further aspects of the present invention are apparent from the examples of embodiment to be described hereinafter and are explained with reference to the examples of embodiment. The invention will be described in more detail hereinafter with reference to examples of embodiment to which the invention is however not limited.

The illustration in the drawing is schematic. It is noted that in different figures similar or identical elements are provided with the same reference signs or with reference signs which differ only within the first digit.

As can be seen the setup shown in makes it possible to check whether each application is authentic i.e. whether it has been signed with the corresponding application provider s key. However the system is static and non scalable as it is not possible to give an application access to a subset of the available secure functions. Furthermore new application developers will have to await an update of the mobile device software operating system to have a certificate added to the certificate store .

The TSM corresponds to the device of the present invention and is adapted to create a set of keys for signing applications where each key is unique and associated with one and only one of the restricted mobile device functions a group of the functions or all functions. In the latter case the key is intended to give full access e.g. for administration purposes. The TSM may be constituted as a dedicated server under the control of a mobile device manufacturer e.g. OEM a mobile network operator MNO a service provider etc. and thereby constitute a trusted third party TTP relative to the providers and the OEM in the sense that these entities do not have access to the keys.

The providers develop and or distribute applications for mobile devices e.g. by making them available for download in an online store or by providing them directly to a mobile device manufacturer for pre installation on the device. In order to gain access to sensitive mobile device functions such as e.g. services involving NFC and SE technology the providers transmit the applications i.e. new or updated applications to the TSM for signing as indicated by arrow . Together with each transmitted application the providers transmit a list of the relevant functions to allow the TSM to sign the application with the corresponding keys. After signing the applications the TSM transmits the signed applications back to the providers as indicated by arrow . Thereafter the signed applications are as indicated by arrow provided to a relevant mobile device upon request i.e. after a user of the mobile device has bought the application in an online application store or accepted to download an updated version of the application.

The TSM also transmits as indicated by arrow an application identifier appID identifying the signed application one or more function identifiers funcID and a set of access rules to the Secure Element of the mobile device . Furthermore the transmission to the Secure Element of the mobile device may include a set of certificates corresponding to the set of keys with which the application has been signed by the TSM . The latter is the case when certificates are updated or changed. The access rules define which certificate s an application has to be signed with in order to obtain access to a particular function. Thereby by changing the certificates and or access rules stored in the Secure Element of the mobile device the TSM can control access and change which functions a specific application identified by a unique appID has access to without the need for an update of the complete operating system of the mobile device .

The set of certificates corresponds to the set of keys in the sense that each certificate is paired with one and only one key such that the certificate can be used to determine whether an application or another set of data has been signed with the corresponding key.

Thereby using the access rules stored in the Secure Element the mobile device can determine whether an application is allowed to access particular functions by using the certificates to determine whether the application has been signed with the keys corresponding to the particular functions.

The TSM also optionally transmits as indicated by arrow a master certificate to the OEM . The master certificate is only used to sign one or more TSM specific application s . The OEM implements the master certificate in the operating system s which is installed into its devices during the manufacturing process or later on in connection with an update of the operating system. This is indicated by arrow .

As illustrated by the arrows and the system provides the further optional feature that the TSM transmits the generated initial set of keys to the owner who root signs the keys and transmits them back to the TSM . This way the owner e.g. a manufacturer or provider of NFC and SE technology may act as a certificate authority CA .

An example of the operation of a mobile device running an Android operating system and comprising an SE in accordance with the GlobalPlatform standard will now be given with reference to . It is noted that shows a standard structure in accordance with GlobalPlatform which is used in the present embodiment of the invention. During operation of the mobile device an application provided by one of the application providers and installed on the mobile device requests access to a function of the Secure Element via the Access Control Enforcer ACE of the SE Access API in the operating system of the mobile device . The ACE communicates the corresponding appID and funcID s to the Access Rule Application Master ARA M in the SE . The ARA M determines based on the received IDs whether corresponding access rules are stored in the ARA M and communicates the result back to the ACE. If an access rule is present which permits the application request the ACE allows the requesting application to access the requested function by setting up a corresponding connection to the requested function in the SE. However in accordance with the present invention the structure shown in may also be used to control access to mobile device functions. This can be done by assigning GlobalPlatform like appIDs to represent the mobile functions. In this case the ARA M determines based on the request from the ACE a relevant set of access rules i.e. a subset of the access rules stored by the ARA M corresponding to the mobile function appIDs. Alternatively the ACE could retrieve all the access rules in the ARA M and use a subset corresponding to mobile function appID for mobile function access control. This subset is output to the ACE which then applies the received set of access rules to determine whether access to the requested mobile device functions should be granted. In yet another alternative the GlobalPlatform ACE is not modified for the mobile function appID and access rules. Instead a separate GlobalPlatform ACE like function is implemented for mobile function access which handles the mobile function appIDs and access rules. The access rules stored in the ARA M of the SE may be managed by the TSM . Thereby by allowing the TSM to control via a secure connection the access rules stored in the ARA M of the SE it is possible to use the GlobalPlatform structure shown in to implement the present invention.

A detailed description of the SE Access API and the ARA M can be found in GlobalPlatform Device Technology Secure Element Access Control Version 1.0 Public Release. May 2012 Document Reference GPD SPE013 available from http www.globalplatform.org.

It is noted that unless otherwise indicated the use of terms such as upper lower left and right refers solely to the orientation of the corresponding drawing.

It should be noted that the term comprising does not exclude other elements or steps and that the use of the articles a or an does not exclude a plurality. Also elements described in association with different embodiments may be combined. It should also be noted that reference signs in the claims should not be construed as limiting the scope of the claims.

