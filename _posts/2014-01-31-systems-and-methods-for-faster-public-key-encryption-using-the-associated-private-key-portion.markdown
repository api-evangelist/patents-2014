---

title: Systems and methods for faster public key encryption using the associated private key portion
abstract: Systems and methods for faster public key encryption using the associated private key portion are described, including encrypting a plaintext into a ciphertext, where the encrypting uses a public key and a corresponding private key; and storing the ciphertext.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09264221&OS=09264221&RS=09264221
owner: GOOGLE INC.
number: 09264221
owner_city: Mountain View
owner_country: US
publication_date: 20140131
---
The subject matter discussed herein relates generally to data processing and more particularly to systems and methods for faster public key encryption using the associated private key portion.

In public key cryptography or asymmetric cryptography a cryptosystem consists of three algorithms one algorithm for key generation which generates a private key maintained by the owner and a public key published by the owner to the public one algorithm for encryption which allows anyone who has access to the published public key to perform encryption using the public key and one algorithm for decryption which allows the owner having private key or trapdoor information to decrypt with the private key data encrypted using the public key.

In the RSA Rivest Shamir and Adleman algorithm for example both the private key and the public key are generated using the two prime numbers. The owner knows the two prime numbers and can perform decryption using the prime numbers. The public i.e. those who are provided with the public key which is based on at least some form of composite of the two prime numbers can perform encryption using the public key. The public cannot effectively factor the composite and cannot perform decryption.

In certain scenarios the party performing the encryption is also the owner of the private key. For example the owner may want to encrypt data for transmission across a public network and or storing at a third party storage e.g. cloud storage . The encrypted data can be retrieved later and decrypted by the owner.

The subject matter includes methods for faster public key encryption using the associated private key portion are described including encrypting a plaintext into a ciphertext where the encrypting uses a public key and a corresponding private key and storing the ciphertext.

The methods are implemented using one or more computing devices and or systems. The methods may be stored in computer readable media.

The subject matter described herein is taught by way of example implementations. Various details have been omitted for the sake of clarity and to avoid obscuring the subject matter. The examples shown below are directed to structures and functions for implementing systems and methods for faster public key encryption using the associated private key portion.

Fast encryption can be implemented in any cryptosystem for encryption authentication digital signatures etc. which uses a public key or the likes and a private key or the likes. Example algorithms that can be made faster using techniques describe herein include but are not limited to Transport Layer Security TLS Pretty Good Privacy PGP Rivest Shamir and Adleman RSA homomorphic encryption e.g. Paillier Encryption and the likes. An algorithm may include key distribution or secret key distribution e.g. using Diffie Hellman key exchange etc. .

As described in below ciphertext C may be equivalent to another ciphertext C encrypted using a conventional encryption algorithm that uses only the public key to encrypt data. In other words the same decryption engine can decrypt ciphertext C and ciphertext C and cannot distinguish whether C is encrypted using a fast encryption algorithm or a conventional encryption algorithm.

Key generation generates keys e.g. public key and private key by for example computing or selecting two prime numbers p and q randomly and independently of each other. Implementations may use prime numbers p and q of equivalent length e.g. 256 bits 512 bits 1024 bits 2048 bits a length that is not 2 etc. . A greatest common divisor i.e. gcd may be computed to verify the property of gcd pq p 1 q 1 1. To generate a public key e.g. public key key generation computes n pq and selects a random integer g such as g n 1 where g n n i 1

A plaintext m can be encrypted into a ciphertext c using the formula c g r mod nin the example described herein where m n and r is randomly select and where r n or r n. n 0 1 . . . n 1 and n i 1

Only the owner or the party doing the decryption knows or should know p and q. The private key may be easily generated once p and q are known. To generate the corresponding private key e.g. private key for decrypting ciphertexts encrypted using public key key generation computes lcm p 1 q 1 where lcm is the least common multiple. Key generation also computes L g mod n mod n where L 1 n. The private decryption key is . The decryption formula in the example described herein is m L c mod n mod n.

Another example way to generate the private key e.g. and if p and q are of equivalent length is by computing n p 1 q 1 n mod n and g n 1.

For example p and q can be 512 bit long numbers and the resulting n can be a 1024 bit long composite number. If p and q are 1024 bit long primes n in turn can be a 2048 bit long this composite is referred to as an RSA number .

Since only the owner or the party doing the decryption knows or should know p and q only the owner e.g. computing devices or systems of the owner can perform encryption using p and or q. Fast encryption is for example implemented to use private key or components of the private key e.g. p and q to speed up encryption.

As shown in fast encryption uses both a public key and the corresponding private key or portion thereof to encrypt data e.g. a message M to produce ciphertexts e.g. ciphertext C .

The EQ encryption formula is c g e mod n. If n 1 is used as g then the encryption formula becomes c n 1 e mod n which can be reduced to c 1 nm r mod n referred to as EQ due to binomial expansion of n 1 mod n. In EQ one exponentiation i.e. g has eliminated which may reduce computation time. EQ has only one remaining exponentiation i.e. r .

The remaining exponentiation can be eliminated or its computation time reduced by using p and q. Pre computation may be fast if the base is fixed and the exponent is varying. To speed up encryption using p and q i.e. this can only be done by the owner of private key who has knowledge of or access to p and q the well known Chinese Remainder Theorem CRT may be used to convert the r mod n portion of EQ to be able to perform pre computation with a fixed base.

Note that n pq. The operation of selecting a random r from the nth residue of ncan be replaced by selecting a random r from the nth residue of pand selecting a random r from the nth residue of q. Using the CRT r and r can be combined to get the nth residue of pqor n. Using the CRT r mod n r mod pqcan be converted to r mod pand r mod qfor random r and r where r r r r p and r q.

The value of r can be selected randomly by selecting a generator g of a cyclic group pof order p and selecting a random element s from p then computing y g mod p. p is Euler s totient or phi function the number of positive integers less than p i.e. 1 2 . . . p 1 that are relative prime to p.

The value of r can be selected randomly by selecting a generator g of a cyclic group qof order q and selecting a random element s from q then computing y g mod q. q is Euler s totient or phi function the number of positive integers less than q i.e. 1 2 . . . q 1 that are relative prime to q.

To obtain the nth residues y and y are raised to the nth power. Thus y g mod p g mod p g mod p and y g mod q g mod q g mod q. For reference gmod pcan be referred to as GN and gmod q GN. The results are a fixed based GN raised to an exponent of a random s mod p i.e. GNmod p and a fixed based GN raised to an exponent of a random s mod q i.e. GNmod q .

Fast encryption pre computes the values once and only once for each combination of p and q. For simplicity of description small p and q values are selected as examples. In actual implementations by computing devices or systems the values of p and q may be 256 bits 512 bits 1024 bits 2048 bits or other numbers of bits in length. For example in the present example shown below p 5 and q 7. The foregoing example implementation is applied to the values of p and q as indicated in the following sequence of operations 

g of p 1 1 2 20 3 20 4 10 5 2 6 5 7 4 8 20 9 10 10 2 11 5 12 20 13 20 14 10 15 2 16 5 17 20 18 4 19 10 20 2 21 5 22 20 23 20 24 2 with the maximum order being 20. The generator g can be 2 3 8 12 13 17 22 or 23 .

g of q 1 1 2 21 3 42 4 21 5 42 6 14 7 2 8 7 9 21 10 42 11 21 12 42 13 14 14 2 15 7 16 21 17 42 18 3 19 6 20 14 21 2 22 7 23 21 24 42 25 21 26 42 27 14 28 2 29 7 30 3 31 6 32 21 33 42 34 14 35 2 36 7 37 21 38 42 39 21 40 42 41 14 42 2 43 7 44 21 45 42 46 21 47 42 48 2 with the maximum order being 42. The generator g can be 3 5 10 12 17 24 26 33 38 40 45 or 47 .

After pre computing the above constant values fast encryption can encrypt any data or message m into ciphertext c using for example the following algorithm.

EQ is c 1 nm e mod n and the r mod n portion can be computed using the CRT Chinese Remainder Theorem on GNmod pand GNmod q.

Let D 1 nm mod n. Accordingly the computation of D is basically one multiplication in terms of the highest computational cost e.g. in time and or resource consumption .

The operations of selecting a random element s from p and selecting a random element s from q as performed are negligible in terms of computational cost.

Compute E GNmod pand F GNmod q. The computational cost is basically two exponentiation operations with fixed base. Fixed base exponentiation can be accelerated via methods of addition chains and especially Pippenger s Exponentiation Algorithm.

Fast encryption performs the computation using the CRT to combine E and F to yield a result H r mod n. The computational cost does not include performing any exponentiation operation.

For example as shown in fast encryption may encrypt a message M to produce a ciphertext C. M 12 i.e. m 12 . Using the pre computed constants GN and GN based on p 5 and q 7 fast encryption selects and or computes the following 

If data to be encrypted by fast encryption is larger or longer than the amount that can be encrypted at a time e.g. m n the data may be broken into segments to meet the condition that each segment n. The resulting ciphertexts can be concatenated. In the reverse process or decryption process the concatenated ciphertext can be broken up into individual ciphertexts before decrypting into individual plaintexts. The plaintexts can be concatenated to form the original data.

After fast encryption encrypts M to create C C can be for example stored in a database controlled by party A or owner . C may also be transmitted through path over a network e.g. a public network or Internet to for example party C . Party C may be a third party that provide data store services e.g. a cloud storage service provider . In some implementations ciphertext C may be transmitted over network for storage or processing by a device or system not shown controlled by party A. When party A wants to access M or the plaintext data of C party A may retrieve C from database if stored there or from party C through network and path . Regardless of the source of C party A can decrypt C using decryption engine or decryption .

In contrast with fast encryption a party e.g. party B who has access to public key i.e. without the knowledge of p and q and only perform encryption using the public key. For example party A provides public key to party B for party B to encrypt a message M into ciphertext C to send to party A. M can be any value. Party B s encryption engine encrypts M using EQ c g e mod n. For example n 35 and g 36 for example. Party B does not know the factors p and q of the composite number n. Encryption engine selects a random r as described above. For example r 23. For comparison M 12 i.e. m 12 . EQ becomes C g r mod n 36 23 mod 1225 522. Party B send C to party A. Note that EQ does not use the private key e.g. the factors p and q or the values and or .

Party A s decryption engine can decrypt C i.e. encrypted by fast encryption using private key and public key and C i.e. encrypted by encryption engine of party B using just the public key the same way. Regardless of when C and C arrive e.g. separately C and C are decrypted independently using the same decryption key or private key e.g. .

Decryption engine decrypts C to obtain the plaintext M and decrypts C to obtain the plaintext M. Decryption engine computes the following values to decrypt C C 1147 produced by fast encryptions 

The same decryption engine can decrypt ciphertexts C and C regardless of Cs being encrypted using a fast encryption algorithm and C being encrypted using a conventional encryption algorithm.

In some examples process may be implemented with different fewer or more blocks. Process may be implemented as computer executable instructions which can be stored on a medium loaded onto one or more processors of one or more computing devices and executed as a computer implemented method.

Another example for using the private key in a public key operation is signature verification e.g. verifying the authenticity of a message or data signed using a digital signature . For example to create RSA signature keys generate an RSA key pair containing a modulus N that is the product of two large primes e.g. p and q along with integers e and d such that e d mod N where is the Euler phi function. The signer s public key consists of N and e and the signer s private key contains d.

To sign a message m the signer computes m mod N . To verify a digitally signed message a the receiver checks that m mod N . The party who holds the prime factors p and q i.e. private key can implement an RSA signature verification which instead of raising to the e th power mod the composite N performs the operations mod p and mod q and using CRT to accelerate the computation of the message to the e th power mod N similar to the conversion of the r mod n portion of EQ described above.

For example the operation of raising to the e th power mod the composite N can be replaced by selecting a random r from the nth residue of p and selecting a random r from the nth residue of q. Using the CRT r and r can be combined to get the eth residue of pq or N. Using the CRT mod N mod pq can be converted to r mod p and r mod q for random r and r where r r r p and r q. The operations continue after computing r and r as described above.

The same operation is applicable for yet another example of RSA encryption by the party who knows the factors private key . For example to verify data or a message that has been digitally signed using a private key a verification result based on the message may be generated using at least a portion of the private key and the corresponding public key e.g. by the party knowing the private key . The verification result may be verified or rejected for example. The result may be stored in for example a log or database.

An example of one or more devices may be computing device described below in . Devices may include but are not limited to a computer e.g. a laptop computing device a mobile device e.g. smartphone or tablet a television a device associated with a vehicle a server computer computing devices storage devices and .

In some implementations devices may be considered user devices e.g. devices used by users to access data such as data stored with a cloud storage service provider . Devices may be devices associated with service providers e.g. used by service providers to provide services and or store data such as storing encrypted webpages text text portions images image portions audios audio segments videos video segments and or information thereabout .

For example a user e.g. Alice may use device or to send encrypted data to a storage provider supported by one or more devices . Alice may encrypt the data using a private key to save computing time and or resources. The encrypted data cannot be decrypted by the storage provider. When Alice wants to access the data Alice retrieves the data e.g. in encrypted form from the storage provider and decrypts the data on Alice s device or .

Computing device can be communicatively coupled to input user interface and output device interface . Either one or both of input user interface and output device interface can be a wired or wireless interface and can be detachable. Input user interface may include any device component sensor or interface physical or virtual that can be used to provide input e.g. buttons touch screen interface keyboard a pointing cursor control microphone camera braille motion sensor optical reader and or the like . Output device interface may include a display television monitor printer speaker braille or the like. In some example implementations input user interface and output device interface can be embedded with or physically coupled to the computing device . In other example implementations other computing devices may function as or provide the functions of input user interface and output device interface for a computing device .

Examples of computing device may include but are not limited to highly mobile devices e.g. smartphones devices in vehicles and other machines devices carried by humans and animals and the like mobile devices e.g. tablets notebooks laptops personal computers portable televisions radios and the like and devices not designed for mobility e.g. desktop computers other computers information kiosks televisions with one or more processors embedded therein and or coupled thereto radios and the like .

Computing device can be communicatively coupled e.g. via I O interface to external storage and network for communicating with any number of networked components devices and systems including one or more computing devices of the same or different configuration. Computing device or any connected computing device can be functioning as providing services of or referred to as a server client thin server general machine special purpose machine or another label.

I O interface can include but is not limited to wired and or wireless interfaces using any communication or I O protocols or standards e.g. Ethernet 802.11x Universal System Bus WiMax modem a cellular network protocol and the like for communicating information to and or from at least all the connected components devices and network in computing environment . Network can be any network or combination of networks e.g. the Internet local area network wide area network a telephonic network a cellular network satellite network and the like .

Computing device can use and or communicate using computer usable or computer readable media including transitory media and non transitory media. Transitory media include transmission media e.g. metal cables fiber optics signals carrier waves and the like. Non transitory media include magnetic media e.g. disks and tapes optical media e.g. CD ROM digital video disks Blu ray disks solid state media e.g. RAM ROM flash memory solid state storage and other non volatile storage or memory.

Computing device can be used to implement techniques methods applications processes or computer executable instructions in some example computing environments. Computer executable instructions can be retrieved from transitory media and stored on and retrieved from non transitory media. The executable instructions can originate from one or more of any programming scripting and machine languages e.g. C C C Java Visual Basic Python Perl JavaScript and others .

Processor s can execute under any operating system OS not shown in a native or virtual environment. One or more applications can be deployed that include logic unit application programming interface API unit input unit output unit pre computation engine random number generator encryption engine and inter unit communication mechanism for the different units to communicate with each other with the OS and with other applications not shown . For example pre computation engine random number generator and encryption engine may implement one or more processes shown and described in . The described units and elements can be varied in design function configuration or implementation and are not limited to the descriptions provided.

In some example implementations when information or an execution instruction is received by API unit it may be communicated to one or more other units e.g. logic unit input unit output unit pre computation engine random number generator and encryption engine . For example after input unit has detected a message M input unit may use API unit to communicate the message M to pre computation engine . pre computation engine checks to ensure that constants and or values needed in encryption operations are available. If not pre computation engine generates or pre computes these constants and or values. Pre computation engine then calls encryption engine to encrypt M. Encryption engine calls random number generator if needed to generate the s and s random numbers for use in encryption. After encryption engine encrypted M into a ciphertext C encryption engine passes C to output unit which may interacts with i o interface to store C or transmit it on a network.

In some instances logic unit may be configured to control the information flow among the units and direct the services provided by API unit input unit output unit pre computation engine random number generator and encryption engine in some example implementations described above. For example the flow of one or more processes or implementations may be controlled by logic unit alone or in conjunction with API unit .

Although a few example implementations have been shown and described these example implementations are provided to convey the subject matter described herein to people who are familiar with this field. It should be understood that the subject matter described herein may be implemented in various forms without being limited to the described example implementations. The subject matter described herein can be practiced without those specifically defined or described matters or with other or different elements or matters not described. It will be appreciated by those familiar with this field that changes may be made in these example implementations without departing from the subject matter described herein as defined in the appended claims and their equivalents.

