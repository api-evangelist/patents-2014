---

title: Apparatus and method to prevent side channel power attacks in advanced encryption standard using floating point operation
abstract: Apparatus and method for obscuring round  power consumption of hardware implementation of the AES algorithm. By simultaneously executing a processor floating point operation while executing round  of the AES algorithm power consumption of the AddRoundKey transformation is obscured. This prevents the opportunity to determine the AES key value during a side channel power attack.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09135834&OS=09135834&RS=09135834
owner: The United Sates of America as represented by the Secretary of the Air Force
number: 09135834
owner_city: Washington
owner_country: US
publication_date: 20140123
---
This patent application claims the priority benefit of the filing date of provisional application Ser. No. 61 817 374 having been filed in the United States Patent and Trademark Office on Apr. 30 2013 and now incorporated by reference herein.

The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

This invention relates to the Advanced Encryption Standard AES outlined in the Federal Information Processing Standards FIPS Publication 197. The AES standard defines the FIPS approved algorithm that is used to encrypt and decrypt 128 bits of data using a 128 192 or 256 bit key. When you encrypt encipher data the output is called ciphertext and when you decrypt decipher the ciphertext the output is called plaintext.

The AES algorithm executes a number of rounds that is dependent on the key size. For 128 bit key rounds are executed for 192 bit key rounds are executed and for a 256 bit key rounds are executed. Referring to the AES algorithm for encryption consists of four transformations AddRoundKey SubBytes ShiftRows and MixColumns .

Referring to the AES algorithm for decryption consists of four transformations AddRoundKey InvShiftRows InvSubBytes and InvMixColumns . The AES algorithm also defines a method of key expansion that creates a round key for each round execution of the algorithm. These round keys are utilized in the AddRoundKey transformation.

The AddRoundKey transformation is specified as a simple bitwise exclusive or operation executed on the plaintext encryption ciphertext decryption and round key. Referring to schematically depicts the transformation. Each data bit and each round key bit are combined in exclusive OR and stored in flip flop or latch for all 128 data bits. Round of the AES algorithm only executes the AddRoundKey transformation while all remaining rounds execute multiple transformations. This leaves round vulnerable to side channel power attacks.

An object of the present invention is to provide an apparatus and method to prevent side channel power attacks from determining the key when the AES algorithm is implemented in hardware.

Another object of the present invention is to provide a method and apparatus to foreclose the opportunity to measure and detect the power consumed during round of the AES encryption process.

Yet another object of the present invention is to provide a method and apparatus to prevent determination of an AES key value.

Briefly stated the present invention provides an apparatus and method for obscuring round power consumption of hardware implementation of the AES algorithm. By simultaneously executing a processor floating point operation while executing round of the AES algorithm power consumption of the AddRoundKey transformation is obscured. This prevents the opportunity to determine the AES key value during a side channel power attack.

In an embodiment of the present invention an apparatus is provided which acts on each pair of said data bits and said key bits for preventing the determination of the encryption key. The apparatus comprises a first circuit acting on each pair of data bits and key bits where the first circuit has a first flip flop circuit having a signal input a clock input and a latched output a second flip flop circuit having a signal input a clock input and a latched output an exclusive OR XOR circuit having a first input a second input and an exclusive OR XOR output a third flip flop circuit having a signal input a clock input and a latched output. The apparatus further comprises a second circuit acting on each said data bit where the second circuit has a floating point processor circuit having an input corresponding to each data bit and an output and a fourth flip flop circuit having a signal input a clock input and a latched output where a latched version of the key bit is connected to the first input of the exclusive OR XOR circuit a latched version of the data bit is connected to the second input of the exclusive OR XOR circuit the exclusive OR XOR output is connected to the signal input of the third flip flop circuit the data bit is connected to the corresponding floating processor circuit input and the output of the floating processor circuit is connected to the signal input of the fourth flip flop circuit.

In another embodiment of the present invention a method for preventing the determination of an encryption key in the Advanced Encryption Standard the following steps are performed on each pair of data bits and key bits in the encryption key. The data bit and key bit are latched then exclusively ORed XOR together with the output of the XOR operation being again latched. Simultaneously a floating point operation is performed on each latched data bit with the output of floating point operation being latched.

Referring to round as specified by the algorithm leaves the key vulnerable to side channel power attacks when the algorithm is implemented in hardware. Round only executes the AddRoundKey transformation or an exclusive or operation of the and data see . In order to obfuscate the power consumption during round execution the present invention also uses the plaintext data input as an input to a processor floating point unit.

Referring to the present invention s physical implementation in the Advanced Encryption Standard AES process is schematically depicted. The plaintext data is not only input to the AddRoundKey transformation but is also simultaneously used as input to a processor floating point unit and latched in flip flop . The floating point operation obfuscate the power consumption of the AddRoundKey due to the new plurality of lower level gates that will be exercised during the floating point unit operation. The present invention is intended to conduct this operation on all 128 bits of the plain text.

Referring to and functionally depict the present invention s placement in the AES encryption and decryption processes respectively.

