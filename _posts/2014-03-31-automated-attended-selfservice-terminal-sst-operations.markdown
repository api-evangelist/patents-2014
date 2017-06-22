---

title: Automated attended self-service terminal (SST) operations
abstract: A security level for an attendant at a Self-Service Terminal (SST) is automatically resolved. An operation is automatically processed on behalf of the attendant based on the resolved security level and a condition associated with the SST.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09361475&OS=09361475&RS=09361475
owner: NCR Corporation
number: 09361475
owner_city: Duluth
owner_country: US
publication_date: 20140331
---
Increasingly enterprises are deploying Self Service Terminals SSTs at various locations for use by consumers. The locations can include financial institutions grocery stores retail stores government venues entertainment venues gaming venues transportation venues and the like.

One type of SST is an Automated Teller Machine ATM . ATMs present unique changes to a servicing enterprise because security is of utmost concern. In fact network access to the network which the ATM communicates with for financial transactions is often unavailable for access to servicing engineers. As a result most service for ATMs occurs in person where the service personnel are physically present at the ATM.

Service personnel have restricted access to assets of the ATM based on their security level. Many times lower level employees are just performing routine operations such as paper replenishment. The employees are forced to toggle through many hierarchical screens to reach the proper printer functions from the administrative interface. Often they activate the wrong selections and are informed of such errors by the ATM software. Sometimes they are unsure of where the printer functions are located within the administrative interface. Possibly they activate a selection that they were not blocked from using or that they are unauthorized to use and end up performing a function that is unrelated to the printer functions. Because of the complexity with the administrative interface lower level employees have to undergo training for even the simplest and non volatile tasks before given access to the ATM. This can be time consuming and expensive and particularly so for an enterprise having locations and employees located worldwide.

In various embodiments methods and a Self Service Terminal SST for automated attended SST operations are presented.

According to an embodiment a method for automated attended SST operations is provided. Specifically a security level for an attendant at the SST is automatically obtained. Next an operation is automatically processed on behalf of the attendant the operation resolved based on the security level and a condition of the SST.

Furthermore the various components that are identified in the are illustrated and the arrangement of the components is presented for purposes of illustration only. It is to be noted that other arrangements with more or less components are possible without departing from the teachings of the automated attended SST operations presented herein and below.

Furthermore methods and SST presented herein and below for automated attended SST operations can be implemented in whole or in part in one all or some combination of the components shown with the diagram . The methods are programmed as executable instructions in memory and or non transitory computer readable storage media and executed on one or more processors associated with the components.

Specifically the diagram permits execution of automated attended ATM operations utilizing a portable device to transfer information to and from the ATM for purposes of authenticating the portable device and an attendant in possession of the portable device . The details of this approach in view of the components within the diagram are now presented with reference to an embodiment of the within the context of ATM maintenance and support systems where the SST is ATM and the portable device is a secure Universal Serial Bus USB device for referred to as key dongle .

However before discussion of the architecture is presented it is to be noted that the methods and SST presented herein are not limited to ATM solutions that is any SST terminal kiosk vending machine check in and or check out terminal such as those used in retail hotel car rental healthcare or financial industries etc. for any industry can benefit from the automated attended SST operations discussed herein including SSTs that lack a network connection entirely such as some vending machines.

The diagram includes an ATM and a key dongle . The ATM includes a device port a system application and an administrative interface . The key dongle includes secure storage having a security key .

The techniques and features of automated attended SST operations is illustrated with reference to the components of the diagram for a bank employee that needs access to the ATM for purposes of replenishing printer supplies such as paper for the receipts and or ink.

The bank employee is provided a secure key dongle for access the ATM through device port . Once the key dongle is interfaced to the device port the system application sends an encrypted message to the key dongle . The key dongle access secure storage to obtain the security key and decrypt the encrypted message. The key dongle then sends a reply message back to the system application over device port . The reply message is used to authenticate the key dongle and obtain the key dongle s serial number. The serial number is used to lookup the level of security associated with the bank employee.

In an embodiment the system application checks on a status or condition of the ATM and its peripheral devices value media dispenser monitor keyboard printer for receipts camera etc. to determine whether the status or condition is related to an operation that the level of security for the bank employee is permitted to perform such as replenishing paper for the printer.

The system application automatically initiates the paper replenishment operations on the ATM on behalf of the bank employee based on the status of condition and the level of security associated with this bank employee based on the interfaced key dongle . The automatic operations may include unlocking and perhaps opening the door to the receipt printer and pausing the printer functions for paper replenishment.

Additionally the relevant menu selections and guidance associated with paper replenishment from the administrative interface are automatically initiated in the administrative interface and presented on a screen of the ATM display monitor.

So the bank employee needed no prior training and can be walked through the relevant procedures on the ATM by automatic processing performed by the system application . The system application can access and control the administrative interface through an Application Programming Interface API . The actions of the bank employee can also be monitored by the system application to ensure the bank employee performed the proper actions based on what is presented in the administrative interface to the employee by the system application .

It is noted that all selections that are not available to the bank employee based on the security level of the key dongle can be removed from the administrative interface by the system application such that the bank employee is unable to inadvertently perform a wrong operation. This greatly simplifies the process for the bank employee and automatically identifies and initiates operations that the system application determines the bank employee should perform based on the interfaced key dongle .

Also the system application can be used to present via the administrative interface or via other screens of the ATM display instructions to the bank employee when physical actions of the bank employee are needed such as press the paper release lever remove the paper insert the new paper and press the feed advance button.

The system application may also note when actions were taken or not taken such as lever pushed or not assuming a sensor or communication mechanism for the lever or any mechanical device of the ATM can provide such status to the system application . Selections made within the administrative interface by the bank employee are noted and recorded to a log by the system application .

It is noted that many key dongles can be authorized to access the ATM . Each key dongle based on its serial number is assigned a security level role set of privileges and each different security level can be tied to different operations available from the administrative interface . The system application therefore customizes what is presented by the administrative interface to just those selections associated with just those operations for a given security level based on the presented key dongle .

It is also noted that some users of the key dongles can have a variety of available operations such as a customer engineer that may be performing diagnostic tests gathering logs installing updates etc. For these users their available operations are custom presented for selection in the administrative interface by the security application . However even for custom engineers the system application may be configured to perform operations which it knows that need to be performed based on a current condition or state of the ATM such as run a diagnostic on the dispenser because a dispense door failed to open for dispensing status was reported.

So the system application is capable of a broad range of automated actions to alleviate proprietary knowledge about the administrative interface for the person who is present at the ATM attending to the ATM . This avoids navigation through a variety of hierarchical screens associated with the administrative interface and presents the person present at the ATM with just selections relevant to that person and automatically performs one or more operations on behalf of that person when a detected condition or status indicates it is proper to do so.

Some embodiments of the diagram and other embodiments of the automated attended SST operations are now discussed with the descriptions of the .

In an embodiment the device that executes the SST automation manager is a Self Service SS checkout station at a retail store.

At the SST automation manager automatically obtains a security level for an attendant at the SST. The security level can be automatically obtained in a variety of manner.

For example at the SST automation manager interacts with a portable device interfaced to the SST without any action from the attendant to resolve the security level.

In an embodiment at The SST automation manager receives a barcode or a Quick Response QR code supplied by the attendant. The barcode or QR code scanned at the SST such as through a scanner or camera peripheral of the SST and the SST automation manager processes the barcode or QR code to resolve the security level. The barcode or QR code can be scanned from a display of a mobile device or scanned from a paper.

In an embodiment at the SST automation manager receives an image or an attendant made gesture supplied from a camera or the SST to resolve an identity for the attendant and acquire the security level. So facial and or body gestures can be used to identify the attendant and obtain the security level associated with the attendant.

At the SST automation manager automatically processes an operation relevant to the security level and a condition of the SST on behalf of the attendant. The condition can be a status for the SST a status for a peripheral device interfaced to the SST or information housed in a log that is accessible to the SST automation manager.

In an embodiment at the SST automation manager obtains the condition for a peripheral device associated with the SST the peripheral device relevant to the security level for the attendant. So the peripheral device may be an interfaced device that the attendant is authorized to service at the SST.

According to an embodiment at the SST automation manager customizes selections of an administrative interface presented on a screen of a display for the SST based on the security level. This was discussed above with reference to the .

In an embodiment of and at the SST automation manager presents instructions on the screen or a different screen related to manual tasks to be performed by the attendant. So tasks of the attendant and how to perform those tasks can be presented in the screen or different screen for the attendant to receive guided assistance while at the SST.

In an embodiment of and at the SST automation manager monitors and logs actions taken by the attendant with respect to the selection of the administrated interface.

In an embodiment of and at the SST automation manager monitors and logs whether each of the manual tasks presented to the attendant were performed by the attendant. This permits the attendant s performance to be evaluated and monitored by supervisors or permits trends with respect to certain tasks to be mined from a log based on what was captured for the attendant and for other attendants authorized to perform the tasks.

In an embodiment the SST that executes the SST maintenance manager is a SS checkout station at a retail establishment.

The SST maintenance manager is presented as another processing perspective of and in some was an enhancement of the SST automation manager presented above with reference to the .

In an embodiment the portable device is one of a phone a wearable processing device a laptop a Secure Digital SD card a Subscriber Identity Module SIM card and a magnetic card a tablet.

In an embodiment at the SST maintenance manager detects the portable device as connected to a device port or the SST. This is a wired connection.

In an embodiment at the SST maintenance manager detects the portable device as connected to a wireless port.

In an embodiment at the SST maintenance manager resolves an identity for the attendant based on an authenticated identifier for the portable device this was discussed above with reference to the .

At the SST maintenance manager resolves an access role assigned to the attendant based on the portable device.

At the SST maintenance manager automatically configures an administrative interface to include just those selections available the attendant based on resolved access role.

In an embodiment at the SST maintenance manager removes all unauthorized selections from the administrative interface based on the resolved access role.

In an embodiment at the SST maintenance manager automatically processes a maintenance operation on behalf of the attendant based on the resolved access role and a status relevant to the SST.

The SST includes one or more processors one or more device ports one or more peripheral devices one or more displays and one or more input devices.

The SST also includes an SST automation manager . The SST automation manager is implemented as one or more software modules that execute on processors of the SST .

The SST automation manager is configured and adapted to authenticate a portable device coupled to an SST port resolve a security level associated with an attendant at the SST and automatically process an operation on behalf of the attendant and the operation relevant to the security level and a condition of the SST .

In an embodiment when the SST automation manager automatically processes the operation the SST automation manager resolves the operation based on the condition in view of the security level.

In an embodiment the SST automation manager is further adapted and configured to customize an administrative interface presented in a screen on a display of the SST.

One now appreciates how maintenance operations of an SST can be automated on behalf of an attendant that is present at the SST to perform some tasks.

It should be appreciated that where software is described in a particular form such as a component or module this is merely to aid understanding and is not intended to limit how software that implements those functions may be architected or structured. For example modules are illustrated as separate modules but may be implemented as homogenous code as individual components some but not all of these modules may be combined or the functions may be implemented in software structured in any other convenient manner.

Furthermore although the software modules are illustrated as executing on one piece of hardware the software may be distributed over multiple processors or in any other convenient manner.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

