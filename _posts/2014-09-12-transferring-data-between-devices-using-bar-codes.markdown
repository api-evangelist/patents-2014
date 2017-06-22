---

title: Transferring data between devices using bar codes
abstract: Improved techniques involve transferring data into a target device using bar codes. Along these lines, suppose that someone wants to send a message to the target device via a source device. For some messages, the source device may encode the message into a single bar code that the target computer may decode back into the message. However, for a sufficiently large message, the source device breaks the message into a series of message portions, encodes each of the portions into a distinct bar code, and outputs the bar codes, e.g., on sheets of paper using a laser printer. From these sheets, an operator scans each bar code into the target device. The target computer then decodes the scanned bar codes back into message portions and reassembles them into the message.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09454605&OS=09454605&RS=09454605
owner: EMC Corporation
number: 09454605
owner_city: Hopkinton
owner_country: US
publication_date: 20140912
---
An air gap or air wall refers to an approach to protecting a computer or computer network from malicious attacks. In particular the operator of such a computer isolates the computer from untrusted networks e.g. no physical connectivity to a public network no WiFi etc. . Accordingly the computer is well protected from malware viruses network hacking and so on.

During operation of the computer a user may enter data into the computer by typing into a standard keyboard. In this manner the user is able to input information as well as direct the computer to perform various tasks.

It should be understood that there are deficiencies to the above described approach to operating a computer protected by an air gap. For example suppose that there is a relatively large amount of data to be entered into the computer. Unfortunately manually typing data into the computer is burdensome prone to error and time consuming.

In contrast to the above described approach to operating a computer protected by an air gap which requires a user to manually type data into the computer improved techniques are directed to transferring data into a target computer via a series of bar codes. Along these lines an untrusted computer is able to divide the data into separate data portions and provide multiple bar codes each bar code containing a respective data portion and metadata identifying how that respective data portion relates to the other data portions e.g. data portion 1 of 3 data portion 2 of 3 etc. . In some arrangements the metadata provides additional information such as a series identifier to enable the target computer to distinguish one series of bar codes from another a checksum for error detection and or correction a time to live parameter to prevent the target computer from processing a stale series of bar codes and so on. With such an improvement a large amount of data can be input into the target computer easily quickly and without error. Moreover when the data of the bar codes is interpreted as text only by the target computer there is no opportunity for the target computer to succumb to malware viruses network hacking etc.

One embodiment of the improved techniques is directed to a method of transferring a message into a target device. The method includes receiving a set of bar codes provided by a source device. The method also includes decoding the set of bar codes to reveal i message portions and ii a sequencing scheme for arranging the message portions into the message. The method further includes arranging the message portions according to the sequencing scheme to produce the message.

Additionally some embodiments of the improved technique are directed to an apparatus. The apparatus includes memory and control circuitry coupled to the memory. The memory stores instructions which when carried out by the control circuitry cause the control circuitry to perform the method of transferring a message into a target device.

Furthermore some embodiments of the improved technique are directed to a computer program product comprising a non transitory computer readable storage medium which stores executable code which when executed by a target device causes the computing device to perform the method of transferring a message into a target device.

Improved techniques involve transferring data into a target device using bar codes. Along these lines suppose that someone wants to send a message to the target device via a source device. For some messages the source device may encode the message into a single bar code that the target computer may decode back into the message. However for a sufficiently large message the source device breaks the message into a series of message portions encodes each of the portions into a distinct bar code and outputs the bar codes e.g. on sheets of paper using a laser printer. From these sheets an operator scans each bar code into the target device. The target computer then decodes the scanned bar codes back into message portions and reassembles them into the message.

Source device is configured to encode a message in bar codes . In the example shown in source device is implemented as a computer that includes a processor memory and an output device . Source device may be connected to a public network such as the internet but this is not a requirement.

Processor is a central processing unit CPU configured to execute encoding instructions stored in memory . Processor may be a single or multi core with each core capable of executing multiple threads.

Memory is configured to store various software constructs running on source device such as encoding instructions . As illustrated in memory further stores data such as message portions including sequencing scheme and message .

Encoding instructions when executed by processor cause processor to encode message portions into bar codes . Encoding instructions when executed by processor also cause processor to break message up into message portions .

It should be understood that encoding instructions as part of breaking message up cause processor to generate sequencing scheme . For example sequencing scheme may take the form of labeling a message portion as portion x of y total portions in message .

Output device is configured to provide bar codes on output media. In this example output device is a laser printer that prints bar codes on sheets of paper . Alternatively output device may be a tablet computer that displays bar codes on a LED screen.

Bar codes may take the form of any standard bar code. In the description that follows each bar code is a data matrix although in other arrangements each bar code may be a QR code a 1D bar code or the like.

Target device is configured to decode bar codes and hence produce message . In the example shown in target device is implemented as a computer that includes a processor memory an input device and an output device . Target device is completely isolated from any public network and untrusted devices by air gap .

In this example processor is a central processing unit CPU configured to execute decoding instructions stored in memory among other functions. Processor may be a single or multi core with each core capable of executing multiple threads.

Memory is configured to store various software constructs running on target device such as decoding instructions . Memory further stores data such as decoded message portions and sequencing scheme .

Decoding instructions when executed by processor cause processor to decode bar codes to reveal decoded message portions . It should be understood that due to input errors decoded message portions might not necessarily be the same as respective message portions stored in memory on source device . Decoding instructions when further executed by processor cause processor to arrange message portions into message according to sequencing scheme .

Input device is configured to transfer information encoded within bar codes into target device . In this example input device is a bar code reader that may scan a data matrix efficiently such as a laser scanner or a digital camera.

Output device is configured to communicate error information with an operator who inputs bar codes into target computer . In this example output device is a display device such as a monitor.

During operation source device receives message to be sent to target computer . For example message may represent data for updating a database stored in a storage device connected to target device . In some arrangements message represents a set of instructions arranged as a web service message having e.g. SOAP or REST formats. In such arrangements message contains textual strings.

In some arrangements after receiving message processor performs a compression operation on message that converts e.g. textual strings of message into a binary string. The compression operation may use an algorithm to compress message into a binary string of a smaller size. In some further arrangements processor uses a public key from a public private key pair generated by target device to encrypt as well as compress message . Such encryption may provide additional security as a human operator would be prevented from accessing the content of message .

Regardless of representation processor then breaks message up into equally sized message portions . Processor determines the size of each portion based on the size of a bar code . For example bar codes that take the form of data matrices can hold up to 500 bytes of data. For the case of a binary string processor may then break the binary string up into 500 byte portions i.e. 4000 binary digits .

However in order to facilitate an error tolerant message transfer between source device and target device processor adds data to each message portion that indicates the position of that portion in message . The data forms part of sequencing scheme which processor stores in memory along with message portions . In some arrangements sequencing scheme represents an assignment of a distinct sequence number e.g. portion x of y portions to each respective message portion. In this case processor adds such a sequence number as well as the total number of portions in message to each respective message portion . Because each bar code represents a fixed data size processor takes into account the number of bytes in the sequence numbers when breaking message up into message portions .

In some arrangements after processor creates message portions processor converts each message portion to a base64 representation. An advantage of using base64 representation is a reduction in the likelihood of transmission errors. For the case of a binary string processor maps sextets of binary digits in each binary string to a 64 bit character symbol.

Regardless of representation processor encodes each message portion in a bar code e.g. a data matrix. Processor then sends bar codes to output device message may be transferred to target device over air gap e.g. by an operator. Typically processor sends data representing bar codes to output device via an SSL or another secure connection. In some arrangements output device is a printer e.g. a laser printer which prints bar codes on sheets of paper. However it should be understood that output device may instead take the form of a tablet computer.

Once processor has output bar codes processor may receive the data from bar codes via input device . For example an operator may manually scan each bar code via a scanner connected to target device . Because each bar code contains information about its position with respect to message e.g. from sequence numbers processor will be capable of assembling message independent of the order in which bar codes are scanned.

Upon receiving bar codes processor decodes each of bar codes to reveal respective message portions and sequencing scheme . It should be understood that operator and or device error may render the message portions different from message portions . For example if a defect in a bar code leads to a misread then the resulting message portion may differ from respective message portion used to create that bar code .

Once message portions and sequencing scheme have been revealed through decoding processor arranges message portions according to sequencing scheme . If there are no errors then processor may produce message from the arranged message portions . If however there are errors then processor will likely not be able to produce message from the arranged message portions . Nevertheless processor is capable of detecting an error condition and communicating it to e.g. an operator. In this way the operator need only be concerned with correcting a single bar code rather than restarting the scan of all bar codes . Such detection is discussed in connection with and .

Once bar codes are scanned target device performs a decoding operation to produce decoded bar codes for storage in memory . For each bar code there is a corresponding decoded bar code and .

Each decoded bar code includes a message portion and a sequence number. For example decoded bar code resulting from bar code includes a message portion and a sequence number 1 meaning that this message portion is the first message portion in message . Decoded bar code resulting from bar code includes another message portion and a sequence number 2 meaning that this message portion is the second message portion in message and so on. It should be understood however that bar codes might be scanned in any order so that the message portions may be arranged in memory in any order.

Along these lines sequencing scheme see is an assignment of a sequence number to a message portion. Target device arranges the message portions according to the sequencing scheme so that upon performing a concatenation operation the message portions are in the correct order to produce message .

In the example scenario illustrated in decoding operation in the process of producing decoded bar codes produces computed checksums which are hashes of respective message portions. For example decoding bar code produces a message portion with a sequence number 4 as before but also having a checksum 00100101 . However as part of decoding operation target device also computes the hash of this message portion which produces computed checksum equal to 01110000 . As the included checksum in decoded bar code and the respective computed checksum differ there is a possible error in decoding bar code . In response target device produces error message and displays error message on output device . For example error message may notify an operator that bar code has an error and may need to be regenerated on source device .

Target device then performs a concatenation operation on binarized message portions to produce a binarized message. Concatenation operation is the reverse of the step breaking up a binarized message on source device . Again concatenation operation assumes that the message portions have been sorted according to respective sequence numbers as described above.

The binarized message represents in this example an encrypted form of message . As described above source device may have encrypted message using a public key belonging to a public private key pair generated on target device . Target device then performs a decryption operation using the private key from this pair producing message .

In some arrangements decryption operation also reveals an encrypted digital signature for additional message security. Such an encrypted digital signature would be generated by source device using a private key from a public private key pair generated on source device . Target device then uses the public key from the pair to decrypt digital signature . If digital signature is deemed valid then target device may accept message otherwise target device may reject message .

In step a target device e.g. target device receives a set of bar codes e.g. bar codes provided by a source device e.g. source device .

In step the target device decodes the set of bar codes to reveal i message portions e.g. message portions and ii a sequencing scheme e.g. sequencing scheme for arranging the message portions into the message.

In step the target device arranges the message portions according to the sequencing scheme to produce the message.

While various embodiments of the invention have been particularly shown and described it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined by the appended claims.

For example while the bar codes illustrated in the above description have been formatted as data matrices any bar code format may work e.g. QR codes. 2D bar codes may be preferable to 1D bar codes because of the data density but 1D bar codes may also be considered as part of this discussion.

Also it should be understood that while the decoding process described in was applied to an error free scan the error correcting techniques described in and may be combined with the process of .

Furthermore it should be understood that some embodiments are directed to target computer which is constructed and arranged to transfer a message into a target device. Some embodiments are directed to a target device. Also some embodiments are directed to a computer program product that enables computer logic to cause a computer to transfer a message into a target device.

In some arrangements target device is implemented by a set of cores or other types of control processing circuitry running software. In such arrangements the software instructions can be delivered within target device either in the form of a computer program product or simply instructions on disk or pre loaded in memory of target device the computer program product having a computer readable storage medium which stores the instructions in a non volatile manner. Alternative examples of suitable computer readable storage media include tangible articles of manufacture and apparatus such as CD ROM flash memory disk memory tape memory and the like.

