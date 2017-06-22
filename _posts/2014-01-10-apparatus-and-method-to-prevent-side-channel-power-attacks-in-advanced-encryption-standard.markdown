---

title: Apparatus and method to prevent side channel power attacks in advanced encryption standard
abstract: Apparatus and method for obscuring round 1 power consumption of hardware implementation of the Advanced Encryption Standard (AES) algorithm. Additional hardware circuitry will provide consistent power consumption during round 1 of the AES algorithm. This prevents the opportunity to determine the AES key value during a side channel power attack.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09160523&OS=09160523&RS=09160523
owner: The United States of America as represented by the Secretary of the Air Force
number: 09160523
owner_city: Washington
owner_country: US
publication_date: 20140110
---
This patent application claims the priority benefit of the filing date of provisional application Ser. No. 61 817 372 having been filed in the U.S. Patent and Trademark Office on Apr. 30 2013 and now incorporated by reference herein.

The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

This invention relates to the Advanced Encryption Standard AES outlined in the Federal Information Processing Standards FIPS Publication 197. The AES standard defines the FIPS approved algorithm that is used to encrypt and decrypt 128 bits of data using a 128 192 or 256 bit key. When data is encrypted enciphered the output data is called ciphertext and when data is decrypted deciphered the output data is called plaintext.

Referring to the AES algorithm executes a number of rounds that are dependent on the key size. For 128 bit key 11 rounds are executed for 192 bit key 13 rounds are executed and for a 256 bit key 15 rounds are executed. The AES algorithm for encryption consists of four transformations AddRoundKey SubBytes ShiftRows and MixColumns.

Referring to the AES algorithm for decryption consists of four transformations AddRoundKey InvShiftRows InvSubBytes InvMixColumns. The AES algorithm also defines a method of key expansion that creates a round key for each round execution of the algorithm. These round keys are utilized in the AddRoundKey transformation.

Referring to the AddRoundKey transformation is specified as a simple bitwise exclusive or operation executed on the plaintext encryption ciphertext decryption and round key. Each data bit and each round key bit are combined in exclusive OR operation and stored in flip flop for all 128 data bits. Round 1 of the AES algorithm only executes the AddRoundKey transformation while all remaining rounds execute multiple transformations. This leaves round 1 vulnerable to side channel power attacks.

An object of the present invention is to provide an apparatus and method to prevent side channel power attacks from determining the key when the AES algorithm is implemented in hardware.

Another object of the present invention is to provide a method and apparatus to foreclose the opportunity to measure and detect the power consumed during round 1 of the AES encryption process.

Yet another object of the present invention is to provide a method and apparatus to prevent determination of an AES key value.

In an embodiment of the present invention a method for obfuscating power consumption during round 1 of an Advanced Encryption Standard encryption process where the standard has a data bit and a key bit for each bit of an encryption key each data bit is exclusive OR d with an inverted version of each key bit. The output of the exclusive OR is then latched and the latched output is capacitively stored thereby obfuscating the power consumption of the encryption process.

Another embodiment of the present invention provides an apparatus for preventing the determination of an encryption key in the Advanced Encryption Standard AES having a data bit and a key bit for each bit of an encryption key having an exclusive OR circuit having a first input a second input and an exclusive OR output a flip flop circuit having a signal input a clock input and a latched output and a capacitor having a first terminal and a second terminal where an inverted version of the key bit connected to the first input the data bit is connected to said second input the exclusive OR output is connected to the signal input the latched output is connected to the first terminal of said capacitor and the second terminal of said capacitor is connected to ground.

Yet another embodiment of the present invention provides an apparatus for securing the implementing of each bit of the Advanced Encryption Standard having a data bit and a key bit for each said bit and having first latch having a data input a data output and a clock input a second latch having a data input a data output an inverting data output and a clock input a first exclusive OR gate having a first input a second input and an output a second exclusive OR gate having a first input a second input and an output a third latch having a data input a data output and a clock input a third latch having a data input a data output and a clock input a fourth latch having a data input a data output and a clock input and a capacitor having a first terminal and a second terminal where the data bit is input into said data input of said first latch the key bit is input into the data input of the second latch the data output of the first latch is input into the first input of the first exclusive OR gate the data output of the second latch is connected to the second input of the exclusive OR gate and to the first input of the second exclusive OR gate the inverted data output of the second latch is connected to the second input of the second exclusive OR gate the output of the first exclusive OR gate is connected to the data input of said fourth latch the output of the second exclusive OR gate is connected to the data input of the third latch the data output of the third latch is connected to the first terminal of said capacitor the second terminal of the capacitor is connected to ground and an output bit connection is connected to the data output of the fourth latch.

Briefly stated the present invention provides an apparatus and method for obscuring round 1 power consumption of hardware implementation of the Advanced Encryption Standard ABS algorithm. Additional hardware circuitry will provide consistent power consumption during round 1 of the AES algorithm. This prevents the opportunity to determine the AES key value during a side channel power attack.

Referring to round 1 as specified by the algorithm leaves the key vulnerable to side channel power attacks when the algorithm is implemented in hardware. Round 1 only executes the AddRoundKey transformation see or an exclusive OR operation of the key and data. In order to obfuscate the power consumption during round 1 execution the present invention provides additional hardware as specified for the AddRoundKey transformation shown in .

Referring to the new hardware implementation is shown. A single data bit and a single key bit are combined in exclusive OR and stored in flip flop . This is the necessary output of the AddRoundKey transformation for data bits. Simultaneously data bit and inverted key bit are combined in exclusive OR and stored in flip flop . The output of this flip flop is tied to capacitor to provide consistent power consumption.

Referring to depicts a functional diagram of the AES encryption algorithm with the present invention incorporated and shown as additional hardware .

Referring to depicts a functional diagram of the AES decryption algorithm with the present invention incorporated and shown as additional hardware .

