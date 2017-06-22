---

title: Method of encryption and decryption for shared library in open operating system
abstract: A method of encryption and decryption for shared libraries in an open operating system is provided. By encrypting a partial portion of an executable and linkable format (ELF) file, where the ELF file is dependent on the shared libraries, an operating system lacking a secret key is not able to use the encrypted ELF file and thus not able to load the shared libraries into the memory for execution, thereby ensuring the protection of the shared libraries.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09256756&OS=09256756&RS=09256756
owner: GIGA-BYTE TECHNOLOGY CO., LTD.
number: 09256756
owner_city: New Taipei
owner_country: TW
publication_date: 20140224
---
This non provisional application claims priority claim under 35 U.S.C. 119 a on Patent Application No. 102149261 filed in Taiwan R.O.C. on Dec. 31 2013 the entire contents of which are hereby incorporated by reference herein.

The present invention relates to a method of encryption for shared libraries in an open operating system. More particularly the present invention relates to a method for encrypting a partial portion of an executable and linkable format file in an open operating system so as to ensure protection of the shared libraries.

Before a program is executed the operating system first determines whether the program to be executed is dependent on other shared libraries. As indicated in step if the operating system determines that the program is not dependent on any other shared libraries the program is executed directly without linking to or loading the shared libraries.

On the other hand if the operating system determines that the program to be executed is dependent on other shared libraries the program is first linked with the shared libraries. The operating system then passes the control to the loader by which the shared libraries that the program is dependent on are loaded into the memory as indicated in step . After the dependent libraries are loaded into the memory the operating system then executes the shared libraries as indicated in step to complete the process of library loading.

While in practice it is common that the shared libraries in an open operating system are written by a third party and users may have to pay to get access to the shared libraries. However the shared libraries may be subject to stealing by adversaries who may use the libraries without paying causing some loss to the library payers and providers.

In view of the foregoing one object of the present invention is to provide a method of encryption for shared libraries in an open operating system. By encrypting a partial portion of an executable and linkable format ELF formerly called extensible linking format file where the ELF file is dependent on the shared libraries an operating system and or a loader if lacking a secret key are not able to access the information pertaining to the shared libraries through the encrypted ELF file and thus not able to load the shared libraries into the memory for execution thereby ensuring the protection of the shared libraries.

Another object of the present invention is to provide a method of encryption for shared libraries in an open operating system where a partial portion of the ELF file is encrypted to ensure protection of the shared libraries. Since not all of the data in the shared libraries to be protected will be encrypted the time and system resources needed for data encryption are thus substantially reduced.

Another object of the present invention is to provide a method of encryption for shared libraries in an open system where the encrypting method first encrypts a partial portion of the ELF file through a random number and subsequently encrypts the random number through a hash number. Optionally the hash number is stored in a hardware based security engine for improving the level of security of the ELF file and the shared libraries and for reducing the risk of being stolen.

Another object of the present invention is to provide a method of decryption for shared libraries in an open operating system. Once the operating system and or the loader determine that the program to be executed is an encrypted ELF file the decrypting method decrypts the encrypted ELF file through a secret key i.e. the random number . After the encrypted ELF file is decrypted the shared libraries that the ELF file is dependent on are linked and subsequently loaded into the memory for execution.

In sum the present invention provides a method of encryption for shared libraries in an open operating system where the shared libraries are dependent libraries that an ELF file requires and the ELF includes an ELF header at least one program header table and at least one segment. The method of encryption includes the step of encrypting partial portions of the ELF header and the program header table.

In addition to the method of encryption the present invention provides a method of decryption for shared libraries in an open operating system. The method of decryption includes the steps of determining that the program to be executed is an encrypted ELF file decrypting the encrypted ELF file through a random number and restoring the encrypted ELF file to an ELF file.

According to one embodiment of the method of encryption the ELF header includes an identification segment.

According to one embodiment of the method of encryption the method includes the step of encrypting the portion of the ELF header excluding the identification segment.

According to one embodiment of the method of encryption the method includes the step of modifying the identification segment so as to generate a new identification segment different from the previous one.

According to one embodiment of the method of encryption the segment of the ELF includes a dynamic segment PT DYNAMIC .

According to one embodiment of the method of encryption the method includes the step of encrypting the dynamic segment PY DYNAMIC .

According to one embodiment of the method of encryption the method includes the steps of generating a random number and encrypting partial portions of the ELF header and the program header table through the random number.

According to one embodiment of the method of encryption the method includes the steps of providing a string password performing a hash operation on the string password so as to generate a hash number and encrypting the random number through the hash number so as to generate an encrypted random number.

According to one embodiment of the method of encryption the method includes the step of storing the hash number in a hardware based security engine.

According to one embodiment of the method of decryption the method includes the steps of determining that the program to be executed is an encrypted ELF file decrypting the encrypted ELF file through a random number and restoring the encrypted ELF file to an ELF file.

According to one embodiment of the method of decryption the method includes the step of decrypting an encrypted random number through a hash number so as to generate the decrypted random number.

According to one embodiment of the method of decryption the method includes the steps of transmitting an encrypted random number and an encrypted ELF file to a hardware based security engine decrypting the encrypted random number through a hash number stored in the hardware based security engine so as to generate the decrypted random number and returning the decrypted ELF file.

Referring to with reference to the ELF includes an ELF header and subsequent information. In one embodiment of the present invention the subsequent information includes at least one program header table at least one segment and or at least one section header table .

The ELF header recites relevant information regarding the ELF . The information for example may include following contents pertaining to a program ELF file format ELF type ELF host machine ELF version program s start address the offset of the program header table the offset of the section header table the size of the ELF header the size and number of the entry of the program header table and the size and number of the entry of the section header table .

The program header table recites information for each segment including the segment offset virtual address physical address size in file size in memory. The section header table recites zero or multiple sections.

Before a program is executed the operating system determines whether the program is dependent on other shared libraries. The shared libraries will be loaded if the operating system determines that the program to be executed is dependent on the shared libraries. For example in a Linux operating system before a program is executed the operating system first determines according to the ELF header whether the program to be executed is an ELF file. If the program to be executed is determined to be an ELF file the system passes the control to the loader by which the dependent libraries that the program requires is loaded into the memory according to the contents of the ELF .

In other words the operating system has to rely on the information of the ELF in order to load the dependent libraries into the memory for execution. The present invention provides a method of encryption for shared libraries in an open operating system. By encrypting a partial portion of the ELF the operating system or the loader if lacking a secret key is not able to access the information pertaining to the shared libraries through the encrypted ELF file and thus not able to load the shared libraries into the memory for execution thereby ensuring the protection of the shared libraries.

In one embodiment of the present invention as shown in the method of encryption first generates a secret key for example a random number E as shown in step . The method encrypts a partial portion of the ELF through the secret key the random number E as shown in step so as to generate an encrypted ELF file as shown in step . The operating system if lacking a secret key will not be able to decrypt the encrypted ELF file and thus not be able to load the shared libraries into the memory.

In practical applications partial portions of the ELF header and the program header table are encrypted through the secret key the random number E such that the operating system lacking the secret key is not able to decrypt or access the encrypted ELF file nor is able to link and load the shared libraries thereby ensuring the protection of the shared libraries.

In one embodiment of the present invention as shown in the ELF header includes an identification segment through which the operating system determines whether the program to be executed is an ELF file. For example the identification segment may be a magic number. During encryption of the ELF header only the portion of the ELF header excluding the identification segment is encrypted. Therefore the operating system is able to recognize whether the program is of an ELF by checking the unencrypted identification segment .

In one embodiment of the present invention the identification segment may be modified and changed to an updated identification segment for example changing from ELF to SLF. After reading the updated identification segment the operating system and or the loader determine that the ELF file is an encrypted ELF file. As long as the secret key the random number E is available the operating system and or the loader are able to decrypt the encrypted ELF file. For example the operating system decrypts the encrypted ELF header and the program header table through the secret key the random number E .

In one embodiment of the present invention the segment includes a dynamic segment PT DYNAMIC where the dynamic segment includes information required for dynamic linking In practical applications not only the partial portions of the ELF header and the program header table are encrypted but also are the dynamic segment and therefore the level of security of the shared libraries is further increased.

In one embodiment of the method for encrypting the secret key the random number E a string password S is first provided. The string password S is provided and defined only once as indicated in step . A secure hash algorithm SHA is performed on the string password S to generate a hash number M to be stored for future use as indicated in step . For example a SHA 256 algorithm may be applied to the string password S to generate a 32 bit hash number.

After the hash number M is generated the secret key is further encrypted through the hash number M for example the secret key the random number E is encrypted through the hash number M to generate an encrypted random number e as indicated in step . The encrypted random number e is saved for future use for example the encrypted random number e may be compiled into a dynamic loader as indicated in step .

In one embodiment of the method of encryption in addition to encrypting a partial portion of the ELF through the random number E the method further encrypts the random number E into an encrypted random number e through the hash number M. With the random number E being encrypted even a third party has the encrypted random number e he she still cannot decrypt the encrypted ELF file through the encrypted random number e. Therefore the level of security of the ELF file and or the dependent shared libraries are increased.

In one embodiment of the present invention as shown in a system chip is connected to a hardware based security engine via an I O interface where the hardware based security engine manages and or stores the hash number M. In one embodiment of the present invention as shown in the hardware based security engine is integrated in a system chip where the hardware based security engine is connected to a central processing unit CPU via an I O interface and the hardware based security engine manages and or stores the hash number M.

With the hardware based security engines the level of security of the secret key random number the ELF file and or the shared libraries are further increased and the risk of being stolen for the secret key random number is also reduced. In one embodiment of the present invention the hardware based security engines may include memory units and operating units . In practical applications the hash number M is stored in the hardware based security engines for example in the memory units and the encrypted random number e is compiled into the loader. During decrypting the encrypted random number e and or the encrypted ELF file are transmitted to the hardware based security engines and the encrypted random number e and or the encrypted ELF file are decrypted through the hash number M where the hash number M is stored in the hardware based security engines .

After determining that the ELF file is an encrypted file the operating system and or the loader decrypt the encrypted ELF file through the random number E as indicated in step . After being decrypted the encrypted ELF file is restored to an ELF file as indicated in step . The operating system and or the loader are able to link the dependent libraries according to the ELF and load the shared libraries that the ELF file is dependent on into the memory for execution.

In the present embodiment of the method of decryption the operating system and or the loader determine that the program to be executed is an encrypted ELF file according to the identification segment of the ELF for example the magic number. For example the operating system and or the loader determine that the program to be executed is an encrypted ELF file according to the identification segment of the ELF which is SLF as shown in step .

After the operating system and or the loader determine that the ELF file is an encrypted file the encrypted random number e and the encrypted ELF file are transmitted to the hardware based security engines via the I O interfaces as shown in step . The hardware based security engines decrypt the encrypted random number e through the stored hash number M so as to restore the encrypted random number e to the random number E as shown in step .

After the random number E is restored the encrypted ELF file is decrypted through the random number E and restored to the ELF file as shown in step . The decrypted ELF file is transmitted to the loader via the I O interfaces as shown in step . After receiving the ELF file the loader loads the dependent libraries that the ELF file requires into the memory for execution.

The term of connecting or connected in the description refers to any object device that is directly or indirectly in connection to another object device where the two objects devices that are in connection may contain zero or multiple other objects devices in between.

Please note that terms such as may have to and changed recited herein shall not be treated as a limitation of the present invention and all other terminology used in the description is to describe related embodiments of the present invention and nor shall be treated as a limitation of the present invention. In the description of the present invention a singular noun form e.g. a or one may also refer to a plural noun form for example an object device used herein may refer to a combination of objects devices containing two or more than two objects devices.

The foregoing embodiments are illustrative of the characteristics of the present invention so as to enable those skilled in the art to understand the disclosed subject matter and implement the present invention accordingly. The exemplary embodiments however are not intended to restrict the scope of the present invention. Hence all equivalent modifications and variations made in the foregoing embodiments without departing from the spirit and principles of the present invention should fall within the scope of the appended claims.

