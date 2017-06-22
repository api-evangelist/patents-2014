---

title: Hardening tokenization security and key rotation
abstract: A method of using a hardware security module and an adjunct application programming interface to harden tokenization security and encryption key rotation is disclosed. In various embodiments, the method comprises receiving encrypted data at a processor of a computer system, decrypting the encrypted data to cleartext in the processor, and issuing a unique token associated with the data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09628274&OS=09628274&RS=09628274
owner: Amazon Technologies, Inc.
number: 09628274
owner_city: Seattle
owner_country: US
publication_date: 20141114
---
The present disclosure is a divisional of and claims priority to U.S. patent application Ser. No. 12 242 746 filed Sep. 30 2008 now U.S. Pat. No. 8 892 868 issued Nov. 18 2014 which is incorporated herein by reference.

Organizations utilize a variety of methods to safeguard confidential information such as payment instrument data. Among these are encryption of data and the use of tokens to represent confidential information. However current methods have difficulties scaling to high availability systems with large amounts of encrypted data. Rotating encryption keys for encrypted data can require either taking a system offline or duplicating data and taking the duplicate system offline while rotation occurs. With large amounts of data in a high availability environment taking the system offline or utilizing duplicate hardware may not be viable. Furthermore cryptographic operations taking place on a server may be vulnerable to compromise rendering confidential information accessible.

Given the rapid increase in online commerce online organizations demand hardened and more rapid processing of encryption functions including encryption key rotation.

Organizations with high availability servers seek to provide access to their services and data with minimal or no downtime. Providing that high availability while securing data using encryption or tokens or both using conventional techniques can be highly demanding of computational financial physical and environmental resources.

This disclosure describes a variety of techniques for using a hardware security module HSM and an adjunct application programming interface API to provide access to cryptographic and tokenization functions within the HSM. Improvements in execution time and accessibility of the cryptographic functions are realized and confidential data is present in cleartext only within the hardened environment of the HSM further enhancing security.

The client computer system may contain a processor or multiple processors and a memory for executing a browser or other application which accepts a cleartext secret from the user. Client computer system while illustrated as a workstation and separate physical device may also be another computer server server cluster or other information processing device or virtualized implementation of an information processing device which utilizes the services of the encryption server . Client computer system may also be located within organization . Client computer system may be an application or virtualized computer executing on the encryption server itself.

In operation a user enters a clear text secret here the example string SARA. The client computer system receives the clear text secret .

The clear text secret is encrypted and a client encrypted secret is output from the client computer system now with an example ciphertext string of KA4. The client encrypted secret may be encrypted using a variety of cryptographic methods including but not limited to symmetric key and public key cryptography.

A network communicates the client encrypted secret to an organization . The network represents any one or combination of multiple different types of networks such as cable networks the Internet wired wireless or other local or wide area networks as well as a physical exchange of data stored on memory.

The organization may range from for profit endeavors to government agencies and may encompass a system ranging from a single server at one geographic location to an array of many servers distributed across the world.

An encryption server of the organization is depicted. The encryption server contains one or more processors and memory. The encryption server receives the client encrypted secret and utilizes an adjunct application programming interface API to communicate with a HSM of the encryption server.

An application programming interface API is a set of functions procedures or classes that an operating system library or service provides to support requests made by computer programs stored in memory and executing on a processor. Here the Adjunct API provides the programs executing on the encryption server processor with callable hooks to easily utilize the features available within the HSM.

The hardware security module HSM may be implemented as a plug in card within a host computer system or a physically external device such as one connected via Universal Serial Bus USB Small Computer System Interface SCSI fibre channel Ethernet and the like . A HSM may include a tamper resistant physical package a general purpose processor executing cryptographic functions or processor optimized for cryptographic operations. An HSM may have dedicated memory onboard provide secure storage of keys and have functionality for code signing to enforce access control lists ACL or any combination of these. The HSM provides a hardened environment for cryptographic operations. Among others two suitable HSMs include the nShield device from nCipher Corporation Ltd of Cambridge United Kingdom and the Luna device from SafeNet Inc. of Belcamp Md. United States.

Within the HSM the client encrypted secret is decrypted to render cleartext secret . In this example client encrypted secret having a ciphertext string of KA4 is decrypted to the cleartext string SARA. A more detailed description of the Adjunct API functions and tokenization follow.

A database server in communication with the encryption server receives an HSM encrypted secret version of the cleartext secret and stores it along with a token associated with the cleartext secret . The database server contains one or more processors and memory. While shown as being external to the encryption server the database server may be implemented within the encryption server or on the same physical device as the encryption server using virtualization. Also while database server is described as being part of the organization in other instances database servers may be located or administered by a third party or both such as a credit card company bank or other entity.

All of the computer systems described herein including client computer system encryption server the HSM and database server may contain a processor as well as memory including but not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other computer readable media which can be used to store the desired information and which can be accessed by processor s of the respective computing devices.

The encryption server contains several elements including an operating system Adjunct API and HSM . Operating system may be any suitable operating system including but not limited to Linux UNIX Microsoft Corporation s Microsoft Windows Apple Corporation s Mac OS Apple Corporation s Mac OS X and Wind River Systems Inc. s VxWorks . The operating system manages the resources of the computer and acts as a host to an application program. The HSM may also have a dedicated operating system as well.

The Adjunct API is in communication with the operating system and the hardware security module . The Adjunct API as described above provides the programs executing on the encryption server processor with callable hooks to easily utilize the features available within the HSM.

Decryption module decrypts client encrypted secret here example ciphertext string KA4. Resulting cleartext secret string SARA is processed. Processing of cleartext secret may include assigning a token marking up the cleartext encrypting or a combination of these elements.

A markup cleartext module may add information regarding the type of data the cleartext embodies i.e. that this is a credit card number bank routing number social security number etc. to the cleartext.

An encryption rule module selects and enforces pre defined cryptographic parameters for the encryption based on pre defined parameters including which of the available HSM private keys to use.

After selection by the encryption rules module the encryption module uses an HSM private key to encrypt the marked up cleartext data to produce the HSM encrypted secret . In this example the ciphertext string ti3rn nL results. HSM encrypted secret may be sent out of the HSM for storage in the database server .

The token assignment module within the encryption server assigns HSM encrypted secret a token . A token may also be assigned to marked up text or non marked up text. A token may be used to refer to a piece of confidential data but the token itself is not necessarily confidential and may not even be encrypted. For example a token may simply be a database record identifier which refers to a credit card number. Thus loss or compromise of token data does not necessarily lead to a release of confidential data. While token assignment module is shown outside the hardware security module it may also be located within the Adjunct API or operating system . HSM sends token out of the HSM for storage in database server .

At an encryption server receives an encrypted secret . The encrypted secret may be received via a network or from another application or HSM running on the encryption server .

At the encryption server processes a request for tokenization in the adjunct API . At after passing the encrypted secret to the HSM the HSM decrypts the encrypted secret within the HSM producing cleartext of the secret.

At the cleartext secret may be marked up . Markup may take place to provide additional information for later processing about the nature of the cleartext secret . For example the cleartext secret may be prepended with a particular string to indicate that the cleartext secret is a credit card number among other types of information. At the cleartext secret is encrypted using encryption rules present within the HSM and using the HSM private key set forth in those rules. The encryption rules may set forth roles or define particular categories of data that a requesting client may access. For example a rule may allow client Albert to access credit card numbers encrypted with Albert s assigned encryption key but not bank account numbers encrypted with the same key. These rules and their associated permissions may be stored within the HSM as well.

At the HSM encrypted secret is sent from the HSM to the database for storage. While encrypted secret is depicted as being generated in the HSM encrypted secret may also be generated by another HSM or by a non HSM encryption method.

At a cleartext secret is assigned a token . At the HSM sends the token to the database storing that information. This database may be on the encryption server or stored on a database server .

Certain acts in method need not be performed in the order described may be modified and or may be omitted entirely depending on the circumstances. For example the assignment of a token shown at may occur before the markup of the cleartext secret.

In one example depicts functions available within the Adjunct API . A token assignment module is available. A ciphertext to ciphertext encryption module is available and may be used to rotate encryption keys as described later. A validation data module is available for validation of payment instrument data such as credit card numbers. A get un marked up version of cleartext secret module is available. This module retrieves an encrypted secret decrypts the encrypted secret within the HSM and removes the markup data. This module may be used to facilitate generating settlement data for third party consumption. For example when sending credit card numbers to a bank or processor for settlement the markup information is irrelevant to the bank as they assume they are receiving credit card numbers and not social security numbers. This module may provide cleartext to the third party or re encrypt the data using a key recognized by the third party.

A get BIN range module is available in the Adjunct API . Several types of payment options may be used by an organization including credit cards debit cards charge cards stored value cards electronic benefit transfer cards and the like. In the example of credit cards the first six digits of these payment options denote the Bank Identification Number BIN which identifies the institution that issued the card to the card holder. In several card processing situations production of BIN values for cards may be useful. For example during pre verification prior to submission to a processor. The pre verification may include data validation such as Luhn mod 10 checks checksums BIN range checks or length checks.

The get BIN range module may also be adapted to provide data for use with other payment types. For example it may provide the International Bank Account Number IBAN values for bank account numbers.

The HSM is depicted at . Several functions are available within the HSM. For example the markup cleartext secret for storage module the HSM encryption module and the encryption rules module are available.

Also within the HSM is HSM private key . The HSM private key may be composed of a hardware generated master key or an external key or both. The hardware generated master key may be present within the HSM. Typically each hardware generated master key is unique among all other encryption keys and is not accessible outside of the HSM.

The external key may be a physical device such as a smartcard USB device or other memory containing a cryptographic key. For example a quorum of external key smartcards may be required at the HSM to access administrative functions such as altering the hardware generated master key . However the external key may also be a string entered into the HSM for use.

Encryption keys needed for cryptographic operations or portions thereof may also be stored externally and loaded into the HSM. Encryption keys need not be associated with a physical device attached to the HSM such as a smartcard.

A ciphertext to ciphertext encryption function is called within the Adjunct API . Ciphertext to ciphertext encryption may be used to rotate encryption keys or translate between encryption keys to enable exchange of data.

Rotation of encryption keys involves re encrypting a secret with a different encryption key. Best practices for safeguarding confidential data in many organizations require changing encryption keys on a regular schedule or in the event of a breach of an encryption key.

The ciphertext to ciphertext encryption module in the API communicates with the HSM . An HSM encrypted secret with the example ciphertext string of ti3rn nL is received 504 in the HSM . While encrypted secret is depicted as being generated in the HSM encrypted secret may also be generated by another HSM or by a non HSM encryption method.

The HSM encrypted secret is decrypted within the HSM resulting in cleartext secret for example string SARA. Once in cleartext the markup cleartext module and encryption rules module may be utilized.

HSM encryption module utilizes a first HSM private key or a second HSM private key or both to encrypt the cleartext. The selection of first HSM private key or second HSM private key is discussed in more depth below.

HSM encryption module outputs second HSM encrypted secret with an example ciphertext string of 2k el n . The token assignment module may also be utilized.

Second HSM encrypted secret is output for storage in database server . The database may maintain an association between the HSM encrypted secret and the second HSM encrypted secret in the database stored on the database server. Here HSM encrypted secret and second HSM encrypted secret both encrypt the same cleartext value in this example string SARA. 

A flag maintained in the database indicates which secret is in currently in use by the system. The flag may be implemented at a system level.

At a ciphertext to ciphertext encryption function is called in the adjunct API . At an encryption server determines whether a first HSM encrypted secret such as is present in a database . While encrypted secret is depicted as being generated in the HSM encrypted secret may also be generated by another HSM or by a non HSM encryption method.

If a first HSM encrypted secret is not present in the database for example only a second HSM encrypted secret is present then the method proceeds to . If a first HSM encrypted secret is present in the database then the method proceeds to .

At no first HSM encrypted secret is present and a second HSM encrypted secret is read decrypted encrypted using the first HSM private key and the HSM encrypted secret is sent to the database to backfill the missing entry in the database. If a first HSM encrypted secret at the first HSM encrypted secret is read from the database .

At this first HSM encrypted secret is decrypted within the HSM to produce cleartext . At the cleartext is encrypted using a second HSM private key . This encryption may be subject to the encryption rules module discussed previously. At the second HSM encrypted secret is sent from the HSM to the database .

At an encryption server such as encryption server determines whether all encrypted secrets are encrypted using the second HSM private key and are stored in the database . If not all encrypted secrets are encrypted using a second HSM private key and stored in the database then the method proceeds to . If all encrypted secrets are encrypted using the second HSM private key and are stored in the database then takes place.

At all encrypted secrets are encrypted using the second HSM private key and are stored in the database and a flag indicating that the second HSM encrypted secret is in use is updated.

At the first HSM encrypted keys in the database may be wiped as they have all been superseded by the second HSM encrypted keys .

The first HSM encrypted secret and second HSM encrypted secret may be encrypted by a different HSM or may be encrypted by a device or method which is not an HSM but can be read by the HSM.

Certain acts in method need not be performed in the order described may be modified and or may be omitted entirely depending on the circumstances. For example the reading of the first HSM encrypted secret from the database in may be attempted before the determination at is made.

At a new record has been added to the database while a ciphertext to ciphertext encryption function is in progress. For example this may occur during key rotation of a very large database.

At the new record is decrypted within the HSM if necessary to obtain cleartext . At the cleartext is encrypted within the HSM using the first HSM private key to create a first HSM encrypted secret . This is necessary because at this time the flag indicating which encrypted secret is in use still refers to the first HSM encrypted secret . At the first HSM encrypted secret is output to the database .

At the cleartext within the HSM is encrypted using the second HSM private key to create the second HSM encrypted secret . At the second HSM encrypted secret is output to the database .

Certain acts in method need not be performed in the order described may be modified and or may be omitted entirely depending on the circumstances. For example the method may output both the first HSM encrypted secret and the second HSM encrypted secret to the database in a single operation.

Moreover any of the acts of any of the methods described herein may be implemented at least partially by a processor or other computing device based on instructions stored on one or more computer readable media. Computer readable media can be any available media that can be accessed by a preprocessing system display device and or digital work as appropriate. By way of example and not limitation computer readable media may comprise volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer readable media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can accessed by a processor. Combinations of the any of the above should also be included within the scope of computer readable media.

Although the subject matter has been described in language specific to structural features and or methodological acts it is to be understood that the subject matter defined in the appended claims is not necessarily limited to the specific features or acts described. Rather the specific features and acts are disclosed as illustrative forms of implementing the claims. For example the methodological acts need not be performed in the order or combinations described herein and may be performed in any combination of one or more acts.

