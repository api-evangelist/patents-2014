---

title: Systems and methods for trading of text based data representation
abstract: A method for sharing encrypted data and encryption keys through a system comprised of the following data types, but not limited to a; 1) Record and its encryption key, 2) RecordSet and its encryption key, and 3) Entity and its encryption key. A Record is encrypted using an encryption key, furthermore, the Record encryption key is encrypted using a RecordSet encryption key, and finally, both the encrypted Record and its encrypted encryption key are wrapped as a single unit, to avoid key the expensive operations of key lookup and general key operation overhead. Access control to the RecordSet encryption keys are provided by a combination of data types, but not limited to a; 1) Entity and its encryption key, 2) Ciphers, and 3) Trusted Entity Lists. For each Entity which is authorized access to access a RecordSet, an encrypted Cipher, made of both the Entity encryption key and RecordSet encryption key, is added to a Trusted Entity List. Tokens are protected by user defined secrets, comprised of Entity encryption keys.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09436849&OS=09436849&RS=09436849
owner: 
number: 09436849
owner_city: 
owner_country: 
publication_date: 20141121
---
Data storage in a trust no one environment requires encryption keys to be protected. Data sharing requires keys to be shared. These two requirements contradict each other which is what our key encryption mechanism will solve A key encryption mechanism that achieves a trust no one architecture and facilitates data sharing.

Having direct hardware or database access typically provides a backdoor to shared data in most conventional computer systems compromising security. An invention of trust no one access control is highly desirable.

In a typical computer system individual records need to be decrypted in order to be shared or regrouped. An invention that can share or regroup encrypted data without any decryption is a more efficient improvement.

In most modern systems sharing encrypted data requires sharing encryption keys in order for recipients to trust data to trust the data s origin and to decrypt data. Key management is an expensive operating overhead in systems that have a lot of keys data and users. Alternatively some systems decrypt and share unencrypted data to avoid key management overhead and consequently compromising data security and privacy. An invention that allows sharing encrypted data and encryption keys with minimal key management overhead is highly desirable.

Using this mechanism records can be stored in their encrypted form without storing any of the encryption keys. No centralized key store is required. None of the record keys recordset keys entity keys token secrets or the user s passwords are stored directly in the database. Having direct hardware or database access does not automatically mean one has data access which is the cornerstone of Trust No One Architecture.

A key encryption mechanism that achieves a trust no one architecture and facilitates data sharing. This mechanism is also distributed and requires no centralized key store. All access control is achieved through the encryption of different keys.

Having direct hardware or database access does not automatically mean one has data access which is the cornerstone of a Trust No One Architecture.

The individual record keys purpose is so that when sharing records or during regrouping the records do not need to be decrypted.

Among the many different possibilities contemplated additional methods may advantageously be provided to share tokens create keys update keys distribute keys and modify shared records.

Various objects features aspects and advantages of the present invention will become more apparent from the following detailed description of preferred embodiments of the invention along with the accompanying drawings in which like numerals represent like components

A System is referring to both a software and hardware implementation of this invention. The techniques presented herein may be implemented with any state of the art computer programming languages including but not limited to Javascript Java Objective C C C C PHP Python Swift development tools platforms or frameworks including but not limited to LAMP and MEAN stacks .

The Token Key Entity Key Record Key and RecordSet Key are all generated using a bitstream which can either be a byte an integer or a bit sequence. The bitstream can be either system generated or user defined.

The RecordSet maintains a list of trusted entities . The Trusted Entity List is used for sharing and access control. The Trusted Entity list may contain one or more Entity References . The Entity Reference is referring to Entity record that has access to the particular RecordSet . When an entity is being assigned to RecordSet that Entity Reference is added to the Trusted Entities list .

The Entity Reference contains 3 sections Entity Name Access Level and RecordSetKeyCipher . The Entity Name is the name of the entity that has access to the RecordSet . The Access Level indicates the abilities the entity can perform on the RecordSet . The Access Level can have the value of either READONLY or READWRITE. The RecordSetKeyCipher is essentially the encrypted RecordSet key . The RecordSet key is a random generated key that was created when the RecordSet got created. The RecordSet key is encrypted by the Entity key to form the RecordSetKeyCipher .

Data in the Record Data section is protected by a Record key . The Record key is generated during record creation time and will stay with the record for the life time of the record. The purpose of having individual Record keys is so that the records do not need to be decrypted when sharing records or during regrouping.

The Record MetaData section may contains one or more RecordSet References . The RecordSet Reference is referring to a logical group of Records which is know as RecordSet in this invention. The implication is that each Record can belong to multiple logical groups. Data sharing and data access control of this invention is being controlled via the use of the RecordSet Reference . The Record can be shared to multiple users entities. The Entity would only have access to records based on the RecordSet that the entity belongs to.

Each RecordSet Reference contains the RecordSetId and the RecordKeyCipher . The RecordSetId identifies the RecordSet that Record belongs to. The Record key is encrypted by the RecordSet key to form the RecordKeyCipher . The RecordKeyCipher is stored in the Record MetaData section and will be used with the RecordSet key to obtain the Record key to unlock the encrypted data .

The Token Key must match with the Token Key of the Sharing Token . The Expiration Date allows the system to determine if the token is still valid. The Type identifies the type of the sharing. The Target Entity Id identifies the entity that has access to use the share token. The RecordSetKeyCipher is the encrypted RecordSet that can be decrypted by using the Sharing Token Secret .

Record Key may not be publicly shared. As such vulnerabilities of any sharing acts alone would not compromise access to Record Key . At renewal of some RecordSet Key there would be no need to renew associated Record Keys . There would also be no need to generate new Record Keys and no need to encrypt again Record Data . The is a potential gain in performance and efficiency as a result. However using new Record Keys while replacing a RecordSet Key may be useful in some alternative use cases.

RecordSet and Shared Tokens may be associated with Access. When access is revoked RecordSet Keys may be renewed yet no need to renew Record Keys . Expiration by date and time is a preferred embodiment while alternative embodiments may also be implemented using a shared token or RecordSet or Trusted Entity List . In some alternative embodiments renewal of Record Keys and Record Data may also be advantageous.

In the preferred embodiment JSON is thought to be the choice of data representation and thus is used for illustration purpose in many of the diagrams wherever applicable.

Method illustrates the flow of turning JSON data into a single cipher. JSON data enters the system in step which is then encrypted using an encryption method in step . The result of the encryption is a long string as seen in step resulting in a single cipher.

Method illustrates the flow of turning JSON data into a composite cipher structure. JSON data enters the system in step which is then encrypted using an encryption method in step resulting in the same JSON structure wherein all contained values are encrypted as ciphers. The result found in step is still a JSON data where the original name value pair structure is preserved.

The encryption method used can be any modern methods capable of carrying out cryptology. SHA and AES are among the many alternatives contemplated.

The JSON Data Core section contains the encrypted JSON Sale Data . A Record key is a randomly generated key that was generated at encryption time. Each Encrypted JSON Record is associated to a unique Record key . The Record key should stay with the Encrypted JSON Record for the lifetime of the Encrypted JSON Record . The Record key is used to encrypt and decrypt the JSON Sale Data . The Record key is encrypted and stored in the Record Meta Data section as the RecordKeyCipher attribute .

The Encrypted JSON Meta Data section contains elements that provide information about the encryption of the data such as RecordKeyCipher Algorithm and idFields . In some embodiments the Record Meta Data may contain an array of one or more of these attributes.

The RecordKeyCipher element contains the encrypted Record key . The Access key encrypts the Record key . The Access key is a randomly generated key string. The purpose of the Access key is to provides users with access to the JSON Sale Data . Only users with the Access key would be able to decrypt the Record key and ultimately using the Record key to decrypt JSON Data Core to obtain the Sale Data . An important advantage of using Access key during sharing and data transfer is that the encrypted JSON Data Core does not need to be decrypted and the Record key does not need to be shared. In some embodiments the Access key may be used to encrypt group of Record keys hence giving users access to a subset of records.

The Algorithm attribute identifies the crypto algorithm used to encrypt the data as well as the Record key . This helps to ensure obtaining the original sale data by using the same consistent algorithm for decryption.

The idFields contains a list of id fields that will not be encrypted by the encryption method. The ID field attribute contains a list of attributes that represent the object s identities. These attributes will not be encrypted and will remain in plain text. Many databases require ID fields in order to store JSON objects. If the content in the ID fields point to an embedded object the entire object will not be encrypted.

In the preferred embodiment a composite cipher structure is used to store individually encrypted values . The advantage of a composite cipher structure is the capability to support discovery and analysis of the Sale Data without decrypting any of the values. Note that there is an additional price element in this illustration. The price element is an example of a core attribute that is stored unencrypted in the Data Core .

Upon receiving both the JSON record and the Shared key the Target system generates a new target Access key in step . In step the Target system decrypts the RecordKeyCipher using the Shared key to obtain the Record key . The Target system then encrypts the Record key with the new target Access key . The Shared key can now be discarded as it is no longer needed. The Target system stores the Encrypted JSON objects into their data stores in step . The Target system securely protects the new Access key in step .

On the other hand the online API makes it possible for buyers carry out various trade transactions such as browsing for sale data and their list prices . When trade transactions successfully complete access keys are typically provided through the online API to buyers for the delivery of purchased digital merchandise. Furthermore the online API provides support of transactions that may not be directly related to transactions of trading of sale data. Examples include support of social network tags or feedback provided by potential buyers. The online API to the product attributes of sale data typically applies such updates.

Service providers are authorized parties who have administrative access to sale data who can provide updates to the servicing attributes of sale data . One of the many servicing attributes that have been contemplated is a warranty expiration date whose values can vary depending on one or more factors such as date of transaction license agreements and so on.

In addition to data providers buyers and service providers other roles have also been contemplated in alternative embodiments. It is thought that their use of the marketplace is to be carried out through the same online API identified in the preferred embodiment.

Data can be changed efficiently. The same Record Key can be used to encrypt changed data and Record Data can be replaced without changing any Record Key or RecordSet Keys . illustrates a Data Update Diagram . Operations and are the Data Decryption steps found in diagram. Data is updated with the changes in operation . Using the same Record Key data is encrypted and updated to the data store in operation .

Access Control module RecordSet Sharing module and Key Wrap module can run all at the same location see diagram separate locations or a combination of both. There may or may not be firewalls between each modules. Data and keys may not be required to upload to a single location in order to share. illustrates an Alternative System Architecture Diagram . In some scenarios there may be a need for each module to be on different computing environments.

