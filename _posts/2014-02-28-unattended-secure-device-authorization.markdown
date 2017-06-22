---

title: Unattended secure device authorization
abstract: Unattended secure device authorization techniques are provided. An operating system (OS) module, which is responsible for device validation when that device is interfaced to a host device, is enhanced. The enhanced OS module silently checks the peripheral device's identifier against a white list and if a match occurs, the enhanced OS module grants permission to the host device applications; if no match occurs, the enhanced OS module silently rejects application access to the device. In an embodiment, the enhanced OS module interacts with the device to determine whether the device is to be authorized or rejected.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09311473&OS=09311473&RS=09311473
owner: NCR Corporation
number: 09311473
owner_city: Duluth
owner_country: US
publication_date: 20140228
---
Most operating systems OSs default behavior for authorization of peripheral devices interfaced to a host device having the OSs are to present popup windows for the users to accept or decline permission for access to the peripherals upon host device connection.

This can be unacceptable for an unattended operation an operation processing when no user is present to accept or decline the OS presented accept or deny request permission of the popup window . Such a situation could prevent the host device from automatically starting an application which may be needed for the host device before starting that application.

Moreover in many cases the user permission needs to be renewed after application installation. So even if permission was granted during a user attended situation to provide peripheral permission and the application is executing normally on the host device if the application is subsequently upgraded updated which could occur automatically by the OS when the user is not present then the issue resurfaces on the upgrade update of the application when the user is not present to provide the needed OS permission.

There are also general concerns around the connection of unauthorized peripheral devices being connected to a host device host system such as 

1 security because connecting unauthorized hardware may be an attempt to get the OS to automatically perform some unauthorized action on the host device such installation of spyware malware etc. and

2 parts protection because some secure host devices systems may only authorize peripherals from known vendors such that the secure device system may operate improperly with other vendor products may expose security holes and may be detrimental to the products and reputation of the known vendors.

In various embodiments methods and system unattended secure device authorization for host devices are presented.

According to an embodiment a method for unattended secure device authorization for a host device is provided. A coupled device is detected as being connected to a host device. A device identifier which is acquired from the device is checked against authorized device identifiers. Application access to the device is silently granted when the device identifier is one of the authorized device identifiers. Application access is silently denied when the device identifier is unmatched in the authorized device identifier.

The techniques methods system and SST presented herein and below for unattended secure device authorization can be implemented in whole or in part in one all or some combination of the components shown with the . The techniques and methods are programmed as executable instructions in memory and or non transitory computer readable storage media and processed on one or more processors associated with the components may also be referred to as modules .

The SST includes a SST core and a device . The SST core also includes an operating system OS a device validator having device valid identifiers and one or more applications processing on the SST core using the OS platform. The device optionally includes a secure storage having a security key and a device identifier for the device . It is noted that although the device validator is depicted in the SST core as being outside the OS in many cases explained herein it is part of OS such that the device validator is considered to be part of the OS .

When the device is coupled to the SST core through the device port the OS is notified or detects this event using the device validator . The mechanism for the OS to discover or receive the event remains unchanged herein. The OS is an enhanced OS because the typical device validator is replaced with the device validator .

In an embodiment the event detected by the OS includes the device identifier with the event such that the OS does not have to query the device for its device identifier .

In an embodiment the device validator queries the device over the device port to obtain the device identifier .

In an embodiment the device validator sends a query to the device which the device supplied back to the device validator in an encrypted format. That is the device validator may issue a hello message and the device receives the message and uses its security key from secure storage to encrypt the hello message which is then sent back to the device validator for validation. Alternatively the encrypted response may be the device identifier . It may also be that the device validator initially sends the hello message in an encrypted format and the device uses the security key to decrypt that message and send the decrypted version back to the device validator . This processing ensures that the device is capable of passing a security check of the SST core and as enforced by both the device validator and the device . It is also noted that other cryptology based mechanism can be used between the device validator and the device without departing from the teachings of this embodiment. Security is of particular concern when the SST is an Automated Teller Machine ATM .

Moreover it may be that no cryptology is used at all between the device validator and the device . In this scenario the device responds to a request with a serial number or part number which can also be checked against another list of serial numbers or part numbers maintained by the device validator .

Once the device validator has the device identifier and optionally has assured itself that the device is authenticate such as through the cryptology embodiment discussed above or a non cryptographic approach also discussed above then the device validator is in a configured position to determine whether an application processing on the SST core and in the processing environment of the OS can be provided access to the device .

So the device validator checks the device identifier against the device valid identifiers which are controlled by the device validator . In an embodiment the device valid identifiers represent a white list of known device identifiers for devices that are permitted to be interfaced and coupled to the SST core through the device port .

When the device validator matches the device identifier to one of the device valid identifiers then the device validator silently and transparently grants permission to the application for using the device . That is there is no affirmative action request made to the application which requires the application to positively take some action to grant the device or deny the device access to the SST core . The application need not perform any action to assure access to the device the device validator performs the necessary validation of and automatic access to the device on behalf of the application . Thus if the application is unattended no user interacting with the application on the SST core or no actual running instance up and running on the SST core the device validation and permissions are set by the device validator . Moreover should the application need to be updated or upgraded for any reason the update or upgraded application will not be subsequently required to provide permission to access the device since this is managed on behalf of the application by the device validator .

When the device validator determines either that the device identifier is unmatched in the device valid identifiers or the device was unable to pass an authentication procedure discussed above the device validator silently and transparently the processing unknown to and requiring no action from the application denies or rejects access to the device on the SST core . So the application is unaware that the device is even present on the SST core .

Many applications that run on SSTs may be automated or semi automated such that the convention approach to peripheral device verification and access are problematic because the applications may need to affirmatively take some action before the OS permits the applications to continue processing or to be updated or upgraded. These problems are eliminated by the techniques discussed herein. That is secure authentication of a device can take place and access to the SST core determined without any input being required from the application this is achieved through the device validator .

In an embodiment the OS is an enhancement to an open source OS such as but not limited to Android Tizen Unix Suse Linux etc.

In an embodiment the OS is an enhancement to a proprietary OS such as but not limited to Windows iOS Blackberry etc.

In an embodiment the device validator acts as a proxy to an OS s device validation module to intercept and perform the processing discussed above with the device validator . In this embodiment the device validator may or may not be part of the actual OS .

In an embodiment the device port is one of an Ethernet port connection a Universal Serial Bus USB port connection a coaxial cable port connection a secure digital SD card slot connection and a wireless transmitter and receiver enabled port connection.

In an embodiment the device is one of a USB device a SD card and any processing and or memory enabled device having a port connector to interface with the device port .

In an embodiment the device is one of a dispenser to dispense currency or other valuable media a printer for printing receipts a card reader for reading consumer cards a monitor for presenting information on screens of a display associated with the SST an encrypted PINpad for encrypting consumer passwords or Personal Identification Numbers PINs entered on an input device of the SST and a keypad as an input device to the SST .

In an embodiment the device valid identifiers include a variety of information organized in a table as records. Each record including a vendor identifier and a device identifier. In some embodiments each record can include a variety of additional information such as but not limited to a device serial number descriptive information for a device a reference to an authentication procedure and or key s to use for that authentication procedure a reference to logging or auditing procedures and the like.

Some of the above discussed embodiments and other embodiments of the invention are now presented with the discussions of the .

For purposes of discussion of the the device that executes the authenticator is referred to as a host device or host. It is a host because a peripheral device is attempting to connect to the host for access on the host by one or more applications that execute on the host. It is to be noted that the host can be any device discussed in the aforementioned embodiments.

At the authenticator identifies a device interfaced to the host. The interface can be a wired connection through a hardware port of the host that the device is coupled to. Alternatively the interface can be a wireless connection through a wireless transceiver port that receives and transmits wireless communications from the host device the device having a transceiver as well .

According to an embodiment at the authenticator obtains an event from an OS of the host. The event is associated with the device being newly interfaced to the host. That is when the device interfaces to the host the OS detects the connected device and raises an event which is monitored by the authenticator.

In an embodiment of and at the authenticator acts as a proxy interface for an OS application that typically handles the event for the OS host. Here the authenticator intercepts communications from or is configured to know where the OS application communicates the event and the authenticator handles the event. This may be a useful scenario when the OS application that typically handles the event is not available for modification or replacement such that the OS application can remain unchanged for achieving the teachings presented herein.

In another embodiment of and at the authenticator replaces a reference to an OS application that typically handles the event for the OS of the host with a reference to the authenticator. Here the device present module of the OS is modified to call the authenticator instead of the OS application that typically handles the event. Alternatively the OS s device present module can be modified to change an event type produced by the OS application that typically handles the event such that the OS application never receives an event type that it looks to process rather the event type is captured by the authenticator.

It may also be that the OS is an open source OS such as Android and the OS application that typically handles the event is replaced by the authenticator.

At the authenticator checks a device identifier obtained from the device against a list of authorized device identifiers for previously authorized devices. The device identifier may be obtained by querying an interface of the device or the device identifier may be attached or associated with the event.

At the authenticator automatically grants an application which is executing on the host access to the device when the device identifier of the device is one of the authorized device identifiers securely maintained by or securely accessible to the authenticator from the host.

According to an embodiment at the authenticator interacts with a device interface of the device to authenticate the device for application access before automatically granting access. So even if the device identifier is matched to one of the authorized device identifiers the authenticator can take additional authentication procedures to ensure the device is authorized to be accessed by the application on the host.

In an embodiment of and at the authenticator encrypts a message with a key and the encrypted message is sent to the device interface. The authenticator then receives from the device interface a decrypted version of the encrypted message which was sent from the authenticator. When the decrypted received message matches the message that the authenticator had originally encrypted then access is granted and the authenticator considers authentication to have passed the application is provided access to the device.

In an embodiment at the authenticator performs the access on behalf of the application without any action being required from the application and without any awareness by the application of the processing performed by the authenticator.

At the authenticator automatically denies the application access to the device when the device identifier is unable to be matched or unmatched in the authorized device identifiers.

In an embodiment at the authenticator logs to a log file on the host or on a secure server accessible to the host one or more of a host identifier for the host the device identifier a calendar date for the denial a time of day for the denial and a processing state of the application. Such information may prove useful for subsequent analysis to identify if there are patterns for the application state and types of hosts when unauthorized devices are trying to connect to the host device.

In an embodiment at the authenticator automatically sends a notification to a predefined resource using a predefined communication channel based on the denial. In other words policy conditions evaluated by the authenticator can dictate that a person receives an email notice or that a reporting application receives the notice via an Application Programming Interface API . The policy conditions can be configured in the authenticator or acquired from a file by the authenticator such that they can dynamically change as needed.

In an embodiment at the authenticator performs the denial of access without any action being required from the application and without any awareness by the application.

One now fully appreciates how OS messages that require application attention to accept or deny can be achieved in a secure manner without such attention unattended .

At OS device validator identifies a notification that a peripheral device is interfaced to a device port of the SST. Mechanisms for identifying the notification were discussed above with reference to the .

At the OS device validator attempts to authenticate the peripheral device for access by an application executing on the SST this is done without any action being required on the part of the application unattended validation .

In an embodiment at the OS device validator compares a peripheral device identifier for the peripheral device and received from the peripheral device against known authorized peripheral device identifiers for known authorized peripheral devices in order to resolve a first portion of the authentication.

In an embodiment of and at the OS device validator interacts with the peripheral device such as through a peripheral device interface using cryptographic message passing to resolve a remaining portion of the authentication.

According to an embodiment at the OS device validator provides the application access when authentication was successful. Again this is done without any action being required on the part of the application unattended access .

In an embodiment at the OS device validator prevents the application from having access to the peripheral device when the authentication failed the denial achieved without any action being required on the part of the application.

In an embodiment at the OS device validator logs the actions that the OS device validator took when attempting to authenticate the peripheral device.

The SST includes one or more processors memory non transitory computer readable storage media an OS executing on the hardware components of the SST a communication port for interfacing to peripheral devices and the OS validation module .

The OS validation module is configured or operable to execute on one or more processors of the SST and identify a connected device such as a peripheral device to a communication port of the SST . The OS validation module is also configured or operable to authenticate the connected device for access by an application executing on the SST the authentication achieved without any action by the application unattended authentication .

According to an embodiment the OS validation module is further configured or operable to compare a connected device identifier for the connected device against a white list of authorized device identifiers for authorized devices for a potential match in order to resolve authentication.

In an embodiment the OS validation module is further operable to query the connected device with an encrypted message and receive back from the connected device a decrypted message that the OS validation module validates to resolve the authentication.

In an embodiment the OS validation module is part of an open source OS such as Android and the OS validation module is an enhancement to or a replacement of an existing device validation module of that OS.

It should be appreciated that where software is described in a particular form such as a component or module this is merely to aid understanding and is not intended to limit how software that implements those functions may be architected or structured. For example modules are illustrated as separate modules but may be implemented as homogenous code as individual components some but not all of these modules may be combined or the functions may be implemented in software structured in any other convenient manner.

Furthermore although the software modules are illustrated as executing on one piece of hardware the software may be distributed over multiple processors or in any other convenient manner.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

