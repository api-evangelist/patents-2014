---

title: System and method for securely storing and sharing information
abstract: A method for any community of interest to conduct secure exchange of encrypted data using a three-party security mechanism consisting of key masters, registries and cloud lockboxes. The registries establish unique identities, verify authenticity, and create directories of individuals, members, cloud lockboxes and other registries. The registries manage permissions lists communicated to the cloud lockboxes as well as detecting and halting anomalous activity. The key masters operated by members to manage keys for individuals, handle encryption and decryption and conduct key exchanges with other members. The cloud lockboxes manage file storage, retrieval and access control. Related application programming interfaces support multiple levels of integration and generate metadata specific to the needs of the community of interest. Community of interest establishes operating parameters including: selecting an encryption algorithm, establishing identity verification processes and selecting a security level. The design supports several other key features.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09390228&OS=09390228&RS=09390228
owner: Reid Consulting Group, Inc.
number: 09390228
owner_city: Athens
owner_country: US
publication_date: 20141112
---
This application is a continuation in part of U.S. application Ser. No. 13 665 861 filed on Oct. 31 2012 which claims priority to U.S. Provisional Patent Application Ser. No. 61 553 883 entitled System and Method for Securely Storing and Sharing Information filed Oct. 31 2011 both of which are incorporated by reference in its entirety as if fully set forth herein.

The present application generally relates to systems devices and methods to conduct the secure exchange of encrypted data using a three party security mechanism consisting of the members the registries and the cloud lockboxes. Control of the private key required for decryption is maintained by the information owner. More specifically the mechanism establishes unique identities verifies authenticity generates and securely exchanges encryption key pairs encrypts transmits receives and decrypts data to from cloud lockboxes creates and appends metadata specific to the applications and retrieves and or acts upon metadata. The related application programming interfaces support multiple levels of integration and generate metadata specific to the needs of the application. A community of interest establishes operating parameters including selecting an encryption algorithm establishing identity verification processes and selecting a security level. The design supports several other key features using operating protocols and or metadata.

Certain methods and systems have previously been used for securely storing and sharing confidential information. Some such systems employ cryptography such as public private key encryption to protect information and or identity management.

Cryptography can provide strong protection but the key exchange process makes sharing encrypted data clumsy and sometimes insecure. Weak absent or disconnected identity verification also degrades the effectiveness.

Accordingly there is a need for systems methods and devices that enable secure exchange of encryption keys among any community of interest. Specifically a need exists for a system for securely storing and sharing information which manages encryption keys separately from the encrypted information to limit access to underlying information only to those who are authorized and that integrated identity management and verification as part of the process.

According to a first aspect of the present application a method to conduct secure exchange of encrypted data using a three party security mechanism consisting of the key masters operated by the members of the community of interest the registries and the cloud lockboxes. The registries establish unique identities verify authenticity and create directories of individuals members organizations key masters cloud lockboxes and other registries. The registries manage permissions lists communicated to the cloud lockboxes as well as detecting and halting anomalous activity. The members operate key master software preferably provisioned as an appliance to create and manage keys for individuals handle encryption and decryption and conduct key exchanges with other members. The cloud lockboxes manage file storage retrieval and access control. The related application programming interfaces support with multiple levels of integration and generate metadata specific to the needs of the application. A community of interest establishes operating parameters including selecting an encryption algorithm establishing identity verification processes and selecting a security level.

According to the second aspect of the present application a method for creating a community of interest is disclosed. Any community of interest can establish its own operating parameters including selecting a public key encryption algorithm selecting a registry or registries establishing related membership requirements and identity verification processes selecting a cloud storage provider or providers selecting the optional security features and determining the minimum application integration levels.

According to the third aspect of the present application a method for creating features through protocols operating among the parties and metadata is disclosed. The protocols and metadata enable features including detection and halting of anomalous access time to live settings on the sharing of data key change and access revocation processes key and file recovery processes de identification of data to feed research databases and emergency access protocols. The design supports addition of features by leveraging existing design elements and expanding operating protocols and metadata.

According to the fourth aspect of the present application a method for minimizing the exposure of data to system administrators is disclosed. The protected data is encrypted prior to reaching the cloud lockbox the cloud lockbox never has the decryption key thus the system administrator performing duties for performance optimization and maintenance of the cloud lockboxes has access to the encrypted data but does not have the decryption key. Further when application owners elect to integrate the present application into their native data storage solutions the benefits of this aspect extend into the premises based or cloud based storage of the application itself.

According to the fifth aspect of the present application a method for integrating with applications and creation of hybrid cloud and on premises data storage solutions is disclosed. The invention provides robust approaches for the integration of an application into the community of interest by providing both published and unpublished application programming interfaces supporting multiple levels of application integration ranging from native integration to the use of industry standard interfaces to simple archiving solutions. The method facilitates the creation of hybrid cloud and on premises storage solutions with predictive caching and provides a method to integrate disparate applications within a single enterprise or across multiple enterprises.

According to the sixth aspect of the present application a method for offering a variety of security levels is disclosed. The invention can be deployed in various ways to achieve the security level desired by the community of interest ranging from 

The following reference characters identify the associated elements depicted in the drawings describing the present invention.

This present application describes systems devices and methods for providing secure exchange of encrypted data using a three party security mechanism consisting of the key masters operated by the members the registries and the cloud lockboxes plus the application programming interfaces.

Digital signatures verify the identity of members registries and cloud lockboxes for all communications and protocols. Encryption protects all sensitive data both in motion and at rest. Optional IP address restrictions add another level to the security model. Appliance based option for the encryption decryption and key management further bolsters security.

The method can be deployed in various ways to achieve the security level desired by the community of interest ranging from 

The method provides a solution to integrate disparate applications within a single enterprise or across multiple enterprises by converting data in the application programming interfaces to either industry standard representations or proprietary common formats.

The design supports an approach for storing unstructured data in a key value object data stores to simplify sharing and reduces the need for a relational database yet retains the ability to transfer such information to from relational databases.

The design supports the ability for the individual to review the contents and audit activity on his her files.

The design provides the capability to provide a holistic view of the individual s files for individual or authorized member.

The design supports use of multiple encryption algorithms simultaneously from a single key master for participation in multiple community of interest networks.

The systems devices and methods of the present application are well suited to operate in any industry requiring secure storage and exchange of information. The present application will describe an exemplary embodiment in the health care industry. Of course one of ordinary skill in the art will appreciate that the systems devices and methods of the present application will have applicability in other industries such as the legal service industry and the real estate industry for example.

Recently the storage requirements with respect to patient files and the Federal mandates to share records with other health care providers and with patients have presented daunting problems for those in the health care industry. The exemplary systems and methods described herein generally referred to as a unified health exchange UHE may be used to solve many of the problems created by the increased storage and usage demands in the industry. The operation of the overall mechanism of the UHE will be described with particular applicability to the health care industry. In the health care application of the design consider the correspondence in the following Table I.

The UHE described herein solves critical and previously intractable challenges in the health care industry while simultaneously providing efficient use of resources and generating cost savings. Health care providers HCPs face mounting expenses and downward pressure on reimbursements. Federal mandates require layers of expensive technology that increase the cost of doing business.

Storage demands for Electronic Health Records EHR continue to expand dramatically driven by factors including high resolution imaging data structured and unstructured data longitudinal care needs and regulatory retention requirements. The combination of increased demand and high cost storage results in rapidly growing IT costs for the HCPs.

Cloud services can dramatically reduce this cost but cloud providers have been wary of the liability of storing health care records. The Unified Health Exchange solution encrypts records prior to moving them to the cloud lockboxes and the cloud lockboxes and underlying cloud providers never possess the decryption key. This combination eliminates the need for the cloud providers to conduct breach notifications greatly diminishing their HIPAA exposure.

By relying on the cloud lockboxes for long term record retention the HCPs can dramatically reduce the volume and thus the cost for on premises computer storage. By leveraging intelligent archiving the HCPs may elect to retain onsite only the records needed in the short term. With deployment of a UHE appliance providing predictive caching the HCPs could eliminate storage of patient files in their EHRs instead linking the underlying EHR file management to the UHE model. Further the UHE approach can eliminate duplication of records within a single HCP as well as the duplication of records received from other health care providers.

Existing models for health information exchange involve cumbersome hierarchies of regional state and national exchanges that have failed to gain traction. The financial models underpinning most HIEs do not offer a sustainable path primarily because the current HIEs add incremental costs for HCPs at a time of great budget pressure. Health Care Providers are under increasing deadline pressure to achieve meaningful use of health information exchanges.

The Unified Health Exchange design enables HIE by default as a byproduct of the cost saving storage arrangement with the cloud lockbox combined with the coordination functions of the HIE Registry. Thus the HCP saves money on storage and avoids the cost of supporting a separate HIE infrastructure.

The emerging medical home concept offers tremendous promise for coordination of care to improve wellness and reduce costs. The lack of health information exchange continues to hamper implementation of the medical home and other innovations such as Accountable Care Organizations ACOs . Unified Health Exchange consolidates patient records offering the medical home a holistic picture of the patient. A patient dashboard may provide an easy overview of the patient s medical history and quick review of recent activity and condition.

Providers and payers struggle to identify fraud waste and abuse. The disparate sources of information make compiling a complete view of a patient s care difficult. Once widely adopted Unified Health Exchange can provide a single source of information for a comprehensive utilization review.

Personal Health Records PHR have been envisioned as a key technology enabling patient education and involvement. Unfortunately early PHR efforts have failed to 

The Unified Health Exchange gives patients and or their medical home unprecedented control over their medical records. Because the records are encrypted with individual keys no one can decrypt the records until authorized for that specific individual.

Computer savvy consumers are able to directly authorize an HCP to access records and also exercise the granularity to only provide permission for specific classes of information. For instance a podiatrist may not be allowed access to a patient s cardiac records. With Unified Health Exchange the patient decides who sees what. Further an audit log of access gives the patient complete visibility regarding who has accessed what and when.

For patients unable or not interested in controlling their own health records the patient s medical home can serve as the patient s proxy by obtaining written sign off similar to existing HIPAA forms to manage the access on behalf of the client.

The HIPAA and HITECH rules regarding the privacy of health records have created confusion and additional costs across the US health care industry. Unified Health Exchange reduces HIPAA responsibility for cloud lockboxes by encrypting the records. For HCPs the more of their data they move to UHE the less vulnerability they retain.

For the EHR vendors each of the many HIEs utilize unique interfaces to their software. UHE offers a single interface through industry standard methods to connect to what could serve as a global HIE platform.

Referring now to there is illustrated an example operating environment of the UHE. Example environment may comprise a medical home HCP an EHR system a patient portal a Key Master an HIE Registry a Cloud Lockbox and various HCPs . As illustrated a unified health exchange application programming interface UHE API and a Key Master may be integrated with medical home s HCP 1 EHR to facilitate communication with HIE Registry .

Further a patient may communicate with Medical Home s EHR via patient portal . In addition the Patient Portal could utilized mobile interfaces to provide convenient interface to the Patient via web or mobile app.

In a typical operation medical home s HCP 1 EHR using the UHE API and the Key Master assigns a unique public private key pair and registers patient with HIE Registry . The public key is provided to HIE Registry and the private key is retained by medical home in the Key Master as the only entity initially authorized to decrypt patient files. This activity is depicted by reference numeral .

The HIE Registry updates permissions directory at Cloud Lockbox to authorize medical home s HCP 1 EHR to write files for patient . This activity is depicted by reference numeral .

Medical Home s HCP 1 EHR using the UHE API and the Key Master writes patient files encrypted with the public key to the Cloud Lockbox retaining onsite only what is needed in the short term. HCP using the UHE API and the Key Master can retrieve files as needed for longitudinal patient care scenarios. Medical Home HCP using the UHE API and the Key Master can also access retrieve and decrypt files written for patient by other participating entities such as HCPs . This activity is depicted by reference numeral .

Patient authorizes Other HCP to access files as depicted by reference numeral . Medical home HCP using the UHE API and the Key Master updates permissions in HIE Registry as depicted by reference numeral . HIE Registry updates permissions at Cloud Lockbox in routine synchronization process as depicted by reference numeral . Patient can also audit access to his her files as depicted by reference numeral .

Medical home s HCP 1 EHR using the UHE API and the Key Master sends private key of patient directly to Other HCP s EHR using Other HCP s Key Master and the UHE API . This exchange of private key is conducted via encrypted transmission verified with digital signatures using the respective organizations public private key pairs. The key exchange bypasses both the HIE Registry and the Cloud Lockbox . This activity is depicted by reference numeral .

Other HCP s EHR can now retrieve decrypt and read files for the specific patient using the patient s unique public private key combination. Other HCP s EHR can now also write files for patient to same Cloud Lockbox encrypted using the patient s public key. These activities are depicted by reference numeral .

Participation by pharmacies depicted by reference numeral add a useful function for coordination of medication regimens.

Other entities such as labs and patient telemetry providers can write files encrypted with the patient s public key but cannot retrieve or decrypt files. This reduces HIPAA liability for these entities and such activities are depicted by reference numeral .

Patient authorized payers are provided limited access to patient files. For example payers may to review metadata but not detailed file information. This activity is depicted by reference numeral .

Further patient s medical homes HCP 1 EHR may securely contribute records to de identified research databases as depicted by reference numeral .

Referring now to there is illustrated a schematic block diagram further depicting operation of the UHE of . Each HCP accessing the storage of Cloud Lockbox may comprise or access an HIE Registry . In the illustrated example medical home s HCP 1 EHR utilizes UHE API and Key Master and secondary HCP 2 utilizes UHE API and Key Master . The HIE Registry provides the mechanisms and trust relationships for verifying unique identities creating and updating patient to HCP and patient to cloud lockbox associations and modifying permissions tables. Each HCP communicates with its associated HIE Registry for patient identity matching to minimize duplication. Each HIE Registry also retains mappings of public keys for patients HCPs payers and any other entities involved in UHE. Each HIE Registry also catalogs authorized IP addresses for participating components for all participants.

Although a single Cloud Lockbox is depicted in the example embodiment it should be clear to those of ordinary skill in the art that multiple cloud lockboxes and or multiple cloud storage servers may be employed. The cloud lockboxes such as Cloud Lockbox offer low cost yet responsive storage for the HCPs Encrypted EHR files which may include file metadata used for the indexing searching and features. The cloud lockboxes also retain a Permissions Directory derived from the HIE Registry for determining the mapping of which HCPs can read files for specific patients.

Each of the UHE API comprises software integrated with the HCPs Electronic Health Record EHR system. The UHE API communicates with the API Engine in the Key Master . In turn the API Engine communicates with the Key Manager and File Broker also a component of the Key Master . The API Engine provides a variety of interface options and policy enforcement function. Together these software modules cooperate with the HCP EHRs for issuing and or managing patient public private key combinations interacting with the HIE registries and for reading writing of files to the cloud lockbox s . Each Key Master also manages private key exchanges with other HCPs.

The UHE API and the API Engine may also convert proprietary data formats into standards based formats. Likewise when reading files from the cloud storage the key master would convert standardized formats into proprietary formats for local EHR use.

It should be appreciated that the Key Master can be implemented as hardware software or a combination of both hardware and software. For example the Key Master can be implemented preferably as a stand alone appliance that can be inserted and integrated into an existing system architecture. In another example the Registry cloud Interface can be implemented or installed onto a computer or other hardware identified and configured by a user. Such a computer may be a dedicated computer for example or may share resources between two or more applications or computing processes. A computer may be a suitable computing device having memory and a processor and capable of storing program instructions in memory and executing the program instructions stored in memory using the processor.

In a proxy operation of the design the patient selects one HCP HCP in the illustrated embodiment to serve as his her medical home. This medical home HCP 1 EHR using UHE API and Key Master generates a unique pair of encryption keys using a public private key combination for the patient. The public key is shared with the HCP 1 EHR but the private key is retained only in the Key Manager and File Broker component of the Key Master . This activity is depicted by reference numeral .

The public key would not actually be shared with the general public but rather it would be shared among HCPs participating in the HIE for file encryption and as a mechanism for identifying the unique patient . The public key would also be appended as unencrypted transactional metadata to the files linking the file to the patient.

The private key retained by the medical home would be used to decrypt the data. The Cloud Lockbox would not have the ability to decrypt the files. Only HCPs authorized by the patient would receive the patient s private key 

HCPs cloud lockboxes and HIE registries also have organization specific public private keys utilized for secure communications and digital signatures among registrants.

All communications and updates among entities may be secured through digital signatures and encryption including exchanges between Cloud Lockbox and HIE Registry exchanges between Cloud Lockbox and Key Master between Key Masters of different HCPs between UHE API and API Engine .

In one example within a given HCP communications among components of the UHE and EHRs are restricted to known machine IP addresses to further increase security. Between HCPs cloud lockboxes and HIE registries all communications may also be restricted to known machine IP address to further increase security. In particular an accepted IP addresses list is maintained by the HIE Registry and distributed along with public keys for these entities. When an individual patient elects to own and operate his her own Key Master as depicted in IP restrictions may also be utilized to provide one method to control access.

The UHE environment described herein is designed to protect the privacy and confidentiality of electronic health records and other forms of sensitive information while also allowing such information to be securely shared with others. As such the UHE environment does not include a central key authority governing the UHE encryption. Rather each independent Key Master operates a Key Manager and File Broker that generates public private key pairs and retains the private keys.

Given the modularity and isolation of key creation encryption and decryption within the Key Manager and File Broker a given community of interest electing to use the UHE mechanism could elect to use any suitable public key encryption algorithm of its choosing without impacting the operation of the UHE environment. For example a first key master may operate a key master and file broker using a first public key encryption algorithm while a second key master may operate a key master and file broker using a second and different public key encryption algorithm.

In one example as illustrated in a Key Master may operate multiple Key Manager and File Broker modules in order to participate in multiple community of interest networks utilizing different encryption algorithms.

Listed below are examples of the types of information which may be maintained by HIE Registry . Of course the examples listed below are not meant to be exhaustive or prescriptive but rather merely examples of the ways in which the underlying mechanism may operate.

Listed below are examples of the types of information that may be stored by the Cloud Lockbox . The list is not meant to be exhaustive or prescriptive but rather an example of one way in which the underlying mechanism may operate.

Referring now to there is a schematic block diagram illustrating an HCP registration process using the UHE of and . An entity seeking to participate in the UHE network as a HCP Registrant R may be registered as depicted in .

The HIE Registry maintains database of HCPs labs telemetry providers payers and any other entities that may have permission to read and or write patient files Registrant . As shown by reference numeral HIE Registry utilizes government sources and other trusted databases to assemble and verify entries in the HIE registry database. HIE Registry may also generate its own public private key combination for itself as a corporate entity.

As shown by reference numeral a Registrant R may verify its identity and authority with the HIE Registry through multi factor identity verification and exchange of authorized IP addresses.

Once verification is completed the Registrant R using HCP 1 EHR R UHE API and Key Master generates its own public private key combination to identify itself as a corporate entity.

As shown by reference numeral the Registrant R transmits its public key to HIE Registry encrypted using the HIE registry s public key using the UHE API and the Key Master . HIE Registry decrypts with own private key.

As shown by reference numeral HIE Registry replies with an acknowledgement encrypted with its own private key. The Registrant R verifies HIE Registry transmission by decrypting with HIE registry s public key using the UHE API and the Key Master .

As shown by reference numeral the Registrant completes registration with an acknowledgement to the HIE Registry encrypted with its own private key using the UHE API and the Key Master . HIE Registry verifies the registrant transmission by decrypting with the registrant s public key.

Referring now to there is a schematic block diagram illustrating a patient registration process using the UHE of and . Once an entity is registered as described above it can then serve as a Patient s Medical Home for the patient and conduct the registration process as depicted in .

First an HCP EHR 1 using UHE API and Key Master sends identifying patient demographic information to HIE Registry as shown by reference numeral . The payload may be encrypted with the private key of the HCP decrypted by the HIE Registry with the HCP s public key confirming the identity of the HCP.

Second the HIE Registry communicates to its network of HIE Registries if applicable to verify uniqueness of patient identity as shown by reference numeral .

In all three cases the response is encrypted with the HIE s private key for decryption by the HCP with the HIE registry s public key confirming identity of the HIE registry.

In all three cases the response is encrypted with the HCP s private key for decryption by the HIE registry with the HCP s public key confirming identity of the HIE registry.

In all three cases the response is encrypted with HIE s private key for decryption by the HCP with the HIE registry s public key confirming identity of the HIE registry.

Sixth if the Patient is a new patient to the HIE Registry network then the HIE Registry updates Cloud Lockbox regarding registration of new Patient as shown by reference numeral .

Seventh the Patient s Medical Home is now able to write and read files to the Cloud Lockbox for Patient using the HCP 1 EHR the UHE API and the Key Master .

Referring now to a schematic block diagram illustrates creating and comparing Activity Logs using the UHE of . Creation and comparison of Activity Logs are also supported by the example UHE environment.

An Activity Log UHE API an Activity Log File Broker and an Activity Log Cloud Lockbox capture information representative of writing and reading of UHE files as well as information representative of changes to access by different members. For improved security the Activity Logs are maintained at the HIE Registry separate from the sources of Activity Log records. For example Activity Logs may be maintained in a first data store while UHE files may be maintained in a second distinct data store. An Activity Logs Compare module at the HIE Registry provides a method for detecting and halting unauthorized access to files. The Activity Logs also provide a record of actions for review by the Patient .

Activity Log data may be obtained from one or more of a variety of sources. For example when the UHE API that is integrated with HCP 1 EHR sends a file write or read request to the API Engine in the Key Master as depicted by reference numeral the UHE API simultaneously sends a report of the request to the Activity Log UHE API at the HIE Registry as depicted by reference numeral .

In one example when the Key Manager and File Broker in the Key Master sends a file write or read request to the Cloud Lockbox as depicted by reference numeral the Key Manager and File Broker simultaneously sends a report of the request to the Activity Log File Broker at the HIE Registry depicted by reference numeral .

In one example when the File Handler in the Cloud Lockbox responds to a file write or read request depicted by reference numeral the File Handler simultaneously sends a report of the request to the Activity Log Cloud Lockbox at the HIE Registry depicted by reference numeral .

Periodically the HIE Registry will analyze activity logs using Activity Log Compare module to detect anomalies that could indicate unauthorized access to Encrypted EHR Files stored at the Cloud Lockbox depicted by reference numeral . If such an anomaly is detected then the HIE Registry may alter the Permissions Directory of the Cloud Lockbox in order to halt file retrieval from the suspect Key Master depicted by reference numeral . In one example a Permission Directory setting may indicate to the Key Manager and File Broker the reason for the denial of file retrieval depicted by reference numeral . In one example the HIE Registry may also notify responsible members at the Participating HCP about the detected anomaly and denial of file retrieval. The notification may be performed via a suitable method established at the time of registration depicted by reference numeral . For example a notification may include an email message a text message a telephone call a pager alert and so on.

Even in a proxy situation the patient could also receive notification of the anomalous access and the actions taken to halt such access.

In one example the File Handler Key Manager and File Broker and the UHE API may send periodic heartbeat messages to HIE Registry to confirm ability to communicate. In such an example the Activity Log Compare module is able to detect the absence of heartbeat entries and generate a notification accordingly.

Referring now to there is a schematic block diagram illustrating sharing write only data using the UHE of and . Receiving and sharing lab results and home mobile telemetry is also supported by the example UHE environment.

Certain providers in the health care field provide patient data without being allowed to receive patient data. Such providers generally referred to generally as Write Only Members may include participating vendors providing home or Mobile Health Monitor Software A participating labs running Lab Software B and other participating entities with Write Only Software C.

Like other HCPs these Write Only Members may also associate to and register with an HIE Registry in the UHE network by following the entity registration process described above in reference to .

By following a process similar to patient registration described in reference to the write only Mobile Health Monitor Software A using the UPI API and the Key Master may retrieve a patient s public key and the ID of Cloud Lockbox from the HIE Registry as depicted by reference numeral . The Write Only Participant A could then commence writing files encrypted with patient s public key to Cloud Lockbox as depicted by reference numeral .

Only HCPs authorized by the patient would have the private key to decrypt the files written by Write Only Members. Write Only Members A B and C would not possess any patients private keys nor would such participants be authorized to retrieve files from the Cloud Lockbox .

Referring now to there is a schematic block diagram illustrating communications within the UHE environment in an emergency situation.

It is important for an HIE solution to provide emergency rooms with access to patient data in the event of an emergency that occurs outside of the patient s normal care community. The so called glass break scenario outlined in the shows how such functionality may work within the UHE framework.

In addition to the coordination of care and HIE benefits of UHE the mechanisms also support analytical methods to detect and prevent waste fraud and abuse as illustrated in .

Using the UHE environment described herein one or more HCPs may elect to generate coordinated and longitudinal de identified patient care research databases . Permission to extract such information may be solicited at the time the patient is authenticated at his her medical home . The coordinated care benefits would ripple into the research database providing a complete picture of the individual s health history without any personal identifiers remaining. The communication mechanisms that support the generation of de identified patient data is illustrated in .

Circumstances may arise in which the need for a change of the Patient s public private key pair is required. This need could arise from circumstances such as compromise of the privacy of the public private key pair detection of unauthorized access to EHR files at Cloud Lockbox decisions to revoke decryption authority previously granted to one or more HCPs or decision of Patient to switch to a different HCP as its medical home. Regardless of the reason the mechanism to change or revoke access remains the same and is illustrated in .

Upon receiving a request to change or revoke access HCP 1 EHR using UHE API and Key Master generates a new key pair and updates HIE Registry with the change via a digitally signed transaction including both the old and new public keys of Patient depicted by reference numeral .

HIE Registry updates Permissions Directory with the change and with an indication that key change process is about to commence for Patient via digitally signed transaction depicted by reference numeral .

Permissions Directory and File Handler both at Cloud Lockbox prepare a new set of Receptors for Patient s files.

Patient s Medical Home using HCP 1 UHE API and Key Master then transmits the digitally signed request for the current and new list of Receptors for Patient . HCP 1 EHR identifies Patient based on both the old and new public keys of Patient . Cloud Lockbox responds with two packages of Receptors for the Patient both the old and the new each encrypted with HCP 1 s public key. These activities are depicted by reference numeral .

HCP 1 using Key Master retrieves all Encrypted EHR Files for Patient decrypts the files with the Patient s old private key and re encrypts the files with the Patient s new public key. HCP 1 EHR using UHE API and Key Master then writes Encrypted EHR Files for Patient back to Cloud Storage as managed by the File Handler . These activities depicted by reference numeral .

HCP 1 EHR using the UHE API and Key Master erases the old version of the Patient s Encrypted EHR Files . However the files written to Cloud Storage by HCP 2 EHR now designated at A the entity whose access is being revoked are not erased. This measure is necessary so that HCP 2 s internal operations are not compromised in terms of retaining patient files. These activities depicted by reference numeral .

Cloud Lockbox records the activity in the Activity Log Cloud maintained at HIE Registry as depicted by reference numeral .

HCP 1 EHR using UHE API and Key Master notifies other HCPs still authorized to write to Patient s files such as HCP 3 EHR of the Patient s new public key depicted by reference numeral . HCP 1 EHR using Key Master also notifies other HCPs still authorized to read and decrypt Patient s files such as HCP 3 EHR of the Patient s new private key depicted by reference numeral .

HCP 1 EHR using UHE API and Key Master also issues a file revocation request to the Key Master of HCP 2 EHR for all files that HCP 2 has downloaded for Patient other than those file written by HCP 2 EHR depicted by reference numeral .

If HCP 2 EHR software is compliant with this feature of UHE then it can acknowledge using Key Master the destruction of Patient s Encrypted EHR Files that it had downloaded but not created as depicted by reference numeral .

HCP 1 EHR using UHE API and Key Master writes to Activity Log R CI maintained at the HIE Registry the outcome of revocation requests and the notification of HCPs still authorized to write and or read files depicted by reference numeral .

It should be appreciated that although the file revocation process has been described as occurring in combination with a key change request a file revocation request can also occur independently of a key change process.

In one example HCP 2 using UHE API and Key Master can continue to retrieve and decrypt the files it wrote to Patient s record using the old private key now shown as HCP 2 Encrypted EHR Files A. This measure allows HCP 2 EHR to continue to use the Cloud Lockbox for archival purposes of its own activity. However HCP 2 EHR will no longer be able to retrieve or learn of the existence of other Encrypted EHR Files for the Patient . These activities depicted by reference numeral .

The UHE environment described herein is designed to protect the privacy and confidentiality of electronic health records and other forms of sensitive information while also allowing such information to be securely shared with others. As such there is no central key authority governing the UHE design. Each Key Master operates a Key Manager and File Broker that generates public private key pairs and retains the private keys. Thus a complete loss of the private key s would render the information protected inaccessible without massive computational effort to recover the private key. Only files remaining in local EHR storage would be recoverable directly from within UHE.

This aspect of potential loss of private keys of UHE is a privacy enhancing design feature but does call out the importance of sharing the private keys with at least one other member with its Key Master operating at sufficient physical distance to provide for disaster recovery scenarios. Alternatively HCP 1 EHR may install and register a second Key Master that is automatically granted read and write access for any Patient selecting HCP 1 as its Medical Home .

In the event that a Key Master becomes damaged corrupted or otherwise loses private keys under its control the key recovery process would in most cases resolve the loss of private keys as illustrated in .

In the worst case scenario the Patient s Medical Home has suffered a corruption of the Key Master such that the private key of one or more patients has been lost. Thus the entire operation of the Key Master may have failed.

First the Patient s Medical Home rectifies operational problem affecting the Key Master and re establishes registration of the new software instance with the HIE Registry as depicted by reference numeral .

The U API initiates through the Key Master the key recovery process using the public key of affected patients.

The Key Master then initiates the key recovery process with the HIE Registry . HIE Registry replies with a private key holder e.g. HCP 2 EHR for one or more patients based on the Patient Directory and Permissions . These activities are depicted by reference numeral .

The HIE Registry sends to the Key Master of HCP 2 EHR a list of patients for whom HCP 1 EHR needs private key recovery as depicted by reference numeral . Alternatively if Patient s Medical Home had installed and registered a second Key Master the HIE Registry initiates the key recovery process with this backup Key Master first. The remainder of the process would remain as follows.

Key Master of HCP 2 EHR transmits private keys for patients in a list from HIE Registry to the Key Master of HCP 1 EHR as depicted by reference numeral . This communication would be further secured by digital signatures and optionally IP address restrictions.

Key Masters HCP EHR 2 records this activity in the Activity Log File Broker as depicted by reference numeral .

The HIE Registry then sends to the Key Masters HCP 3 EHR a list of patients for whom the Key Masters of HCP 1 EHR needs private key recovery as depicted by reference numeral .

Key Master of HCP 3 EHR transmits private keys for patients in a list from HIE Registry to the Key Master of HCP 1 EHR as depicted by reference numeral . This communication would be further secured by digital signatures and optionally IP address restrictions.

Key Masters HCP EHR 3 records this activity in the Activity Log File Broker as depicted by reference numeral .

The described process repeats until Patient s Medical Home retrieves private keys for all affected patients.

Should the key for a patient be unrecoverable the Patient s Medical Home may initiate a file recovery process that seeks to restore to the UHE network whatever EHR files for the Patient remain in local storage of the HCP EHR participating in the care of the given Patient . The key change process from and a modification of the key recovery process from that focuses on files instead of keys are then invoked.

A Participating HCP will in most cases operate multiple EHR software systems as well as other auxiliary systems requiring data feeds from EHR systems. These software systems are likely to include but not be limited to an inpatient EHR I EHR A an ambulatory EHR A EHR B and a picture archiving and communication system PACS C as illustrated in . These various systems often function independently within a health care organization requiring internal integration to create a unified view of a given patient.

Each of the EHR software systems will need to run an interface to participate in UHE called the UHE API . However only a single Key Master would be required with the API Engine able to communication with multiple UHE APIs .

In such a configuration UHE can support internal HCP integration efforts by providing the common interface among all systems. For vendors of EHR systems UHE presents a single interface to develop that would serve HCPs with any blend of EHR systems.

While it would be simpler to have a single HIE registry to serve all patients this outcome seems unlikely in our highly competitive health care and IT markets. One of ordinary skill in the art will recognize that the UHE described herein may be embodied in alternate configurations including an environment having multiple HIE registries as illustrated by .

In such an embodiment each HCP A E associates with only one HIE registry A C. The HIE registries A C communicate with each other during 

While it would be simpler to have a single provider of cloud lockboxes to serve all HCPs one of ordinary skill in the art will recognize that such a configuration may not accommodate the highly competitive health care and IT markets. Thus the UHE design accommodates the existence of multiple providers of cloud lockboxes as illustrated in .

As illustrated in HCP is the medical home for patient A. HCP designates cloud lockbox A for patient A. The association is identified during HIE registration of the patient. Patient A authorizes HCP to read write files. HCP writes files for patient A to cloud lockbox A to keep all patient files in one source. Similarly write only input for patient A such as lab results from HCP are also written to cloud lockbox A.

As illustrated in HCP is the medical home for patient B. HCP designates cloud lockbox B for patient B. The association is identified during HIE registration of the patient. Patient B authorizes HCP to read write files. HCP writes files for patient B to cloud lockbox B to keep all patient files in one source. Similarly write only input for patient B such as lab results from HCP are also written to cloud lockbox B.

It should be appreciated different levels of integration may be possible between EHRs and the UHE. For example evolution and extension of the interfaces will progress over time. All levels of integration may be supported by a single API Engine in the Key Master . An example delineation of the levels of integration is depicted in the following table.

In some situations it may not be necessary to access complete data records but rather to only access a partial record of a patient such as basic patient information. For example an insurer may need to know that a certain diagnostic test was performed but the insurer does not need to have access to a full patient file. In another example a physician specializing in one field such as podiatrist may not need to have access to patient information pertaining to another medical field such as the patient s records about a patient s heart condition. Thus in one example a partial data record such as metadata may be provided rather than the entire patient data file.

In some situations it may be undesirable to provide data from which specific patient identities can be determined. For example an organization performing research may be interested in patient outcomes in relation to a specific treatment of a disease. However the organization performing the research may not be permitted to know the identities of the patients. Thus in one example patient data may be anonymized in order to eliminate information such as names addresses and social security numbers.

In one example the patient portal may further provide patient with a patient dashboard. In particular the patient dashboard may provide an overview of the patient s medical history as well as an overview of recent activity and medical conditions. Such a patient dashboard provides a single source of information from which a patient may obtain a personal medical summary as well as a comprehensive medical review.

Given the flexibility of the described systems devices and methods the UHE business model could take other forms. illustrates one such alternate embodiment. depicts an environment similar to that of except that an entity other than a health care provider may become a patient s medical home for the purposes of medical record aggregation called a Medical Home Health Record Representative HRR .

The HCPs are or will soon be required by Federal mandate to be able to share patient records through a set of HIE standards. Thus the HIE goals of UHE could be met even if the HCP did not directly participate in the UHE mechanism. Such an HCP would sacrifice the cost savings inherent in the UHE design in terms of reducing storage costs unless they transferred their long term record retention responsibilities to the HRR.

The HRR could also operate a blended architecture offering a choice between the standards based HIE interface solutions and the full UHE implementation.

The systems devices and methods of the present application have been described primarily in relation to an example health care system. The systems devices and method are also applicable in a wide variety of other industries in which confidential information needs to be selectively and securely shared among multiple business entities.

Referring now to there is illustrated a schematic block diagram depicting a system supporting the legal industry using a similar design as in for the medical industry but with different entities. Following the concept of the medical home this model addresses the creation of a legal home for the client. Such a home selection does not preclude the use of other lawyers but the home lawyer does become the initial issuer and owner of the public private key set. Similar to the health care industry other business entities could provide the legal home other than law firms.

Other law firms prosecutors and courts may be granted granular read write access on a client by client basis. Write only participants such as court reporters and labs could securely write files to the client s case file without gaining the ability to retrieve and or decrypt any other files related to the case. The client would have a complete view of all files related to his her case and the ability to audit access.

Referring now to there is illustrated a schematic block diagram depicting a system supporting the real estate industry using a similar design as in for the medical industry but with different entities. Once again following the concept of the medical home this model addresses the creation of a real estate home for the client. Such a home selection does not preclude the use of other realtors but the home realtor does become the initial issuer and owner of the public private key set. Similar to the health care industry other business entities may provide the real estate home other than real estate firms.

Other realtors mortgage brokers lawyers developers etc. may be granted granular read write access on a client by client basis. Write only participants such as appraisers and inspectors could securely write files to the client s file without gaining the ability to retrieve and or decrypt any other files related to the business situation. The client may have a complete view of all files related to his her business situation and the ability to audit access.

The preceding depictions of the system have assumed the presence of a proxy acting on the information owners request to manage the owner s information. However as shown in an example design also supports a stand alone use of the mechanism operated by the owner to directly manage multiple types of information using a similar design as in . In this scenario there is no medical home or legal home with default access. Instead the information owner originates the key pairs and all permissions. In this scenario all activities including registration sharing of private keys revocation requests and key pair changes would originate with the owner using his her own Key Master .

The API Engine could support APIs for a variety of desktop and mobile applications running on any suitable operating system.

In one example information owner may elect to run multiple Key Manager and File Broker modules in the Key Master . In this way the Information Owner can participate in multiple community of interest networks operating with different encryption algorithms. In this example the Key Master contains two Key Manager and File Brokers A and B each operating a different encryption algorithm specific to the two specific communities of interest depicted. In particular Key Manager and File Broker A A uses an encryption algorithm shared by all members of the community of interest participating in the health care network represented by Cloud Lockbox Health Care A and HIE Registry A. Key Manager and File Broker B B uses an encryption algorithm shared by all members of the community of interest participating in the legal network represented by Cloud Lockbox Legal B and Legal Exchange Registry B. Thus a single Key Master could support multiple Key Manager and File Broker modules for participation in multiple community of interest networks.

With three examples of industries that can utilize the described systems devices and methods one can easily imagine other applications of this flexible system in any situation in which multiple members need to have access to confidential information regarding an individual such as the insurance industry social service agencies commercial research and development scientific research and finance for example.

From the information contained herein those skilled in the art will perceive improvements changes and modifications to the systems devices and methods disclosed herein. Such improvements changes and modifications within the skill of the art are intended to be covered by the present application.

Notwithstanding that the numerical ranges and parameters setting forth the broad scope of the invention are approximations the numerical values set forth in the specific examples are reported as precisely as possible. Any numerical value however inherently contains certain errors necessarily resulting from the standard deviation found in their respective testing measurements.

Furthermore while the systems devices methods and so on have been illustrated by describing examples and while the examples have been described in considerable detail it is not the intention of the applicants to restrict or in any way limit the scope of the appended claims to such detail. It is of course not possible to describe every conceivable combination of components or methodologies for purposes of describing the devices systems methods and so on provided herein. Additional advantages and modifications will readily appear to those skilled in the art. Therefore the invention in its broader aspects is not limited to the specific details and illustrative examples shown and described. Accordingly departures may be made from such details without departing from the spirit or scope of the applicant s general inventive concept. Thus this application is intended to embrace alterations modifications and variations that fall within the scope of the appended claims. The preceding description is not meant to limit the scope of the invention. Rather the scope of the invention is to be determined by the appended claims and their equivalents.

Finally to the extent that the term includes or including is employed in the detailed description or the claims it is intended to be inclusive in a manner similar to the term comprising as that term is interpreted when employed as a transitional word in a claim. Furthermore to the extent that the term or is employed in the claims e.g. A or B it is intended to mean A or B or both. When the applicants intend to indicate only A or B but not both then the term only A or B but not both will be employed. Similarly when the applicants intend to indicate one and only one of A B or C the applicants will employ the phrase one and only one. Thus use of the term or herein is the inclusive and not the exclusive use. See Bryan A. Garner A Dictionary of Modern Legal Usage 624 2d. Ed. 1995 .

