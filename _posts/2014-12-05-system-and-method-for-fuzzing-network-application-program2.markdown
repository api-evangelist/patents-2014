---

title: System and method for fuzzing network application program
abstract: A system and method for fuzzing a network application program, which use a captured packet upon fuzzing a network application program, and thus neither a protocol analysis procedure nor the production of a fuzzer program is required. The system for fuzzing a network application program includes a fuzzing performance client program unit for generating a packet to be transmitted from a captured packet, applying a fuzzing rule to the packet to be transmitted, and outputting a resulting packet. A fuzzing supervisor program unit provides the packet from the fuzzing performance client program unit to a target program to be fuzzed, monitors an event and abnormal termination of the target program to be fuzzed, and analyzes a situation of termination to verify security vulnerabilities if abnormal termination has occurred.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09654490&OS=09654490&RS=09654490
owner: ELECTRONICS AND TELECOMMUNICATIONS RESEARCH INSTITUTE
number: 09654490
owner_city: Daejeon
owner_country: KR
publication_date: 20141205
---
This application claims the benefit of Korean Patent Application No. 10 2014 0065519 filed May 30 2014 which is hereby incorporated by reference in its entirety into this application.

The present invention relates generally to a system and method for fuzzing a network application program and more particularly to a system and method that perform fuzzing by injecting a random value into a packet during the transmission of the packet using a captured packet upon conducting a fuzz testing on a network application program.

Fuzzing denotes a technique for searching for security vulnerabilities in software by repeatedly inputting random data to software and by causing systematic failures in software.

A fuzzing technique is based on fault injection that transmits various input values to an analysis target system so as to detect security vulnerabilities.

The principal advantages of such a fuzzing technique are that in a procedure for detecting security vulnerabilities simplicity efficiency automation and speed may be improved and the fuzzing technique is usefully used to test a plurality of applications.

Such a conventional technology requires the analysis of protocols for packets that are exchanged between a client and a server upon fuzzing a network application program and needs the production of a separate program depending on the analysis of protocols. Since this is a procedure requiring a lot of manpower and time the manpower and time are regarded as costs required for fuzzing. Further in a situation in which detailed analysis forms for the protocols of network application programs that are targets to be fuzzed are not present the analysis of protocols and the production of programs require much higher costs.

As related preceding technology Korean Patent Application Publication No. 10 2008 0043209 is disclosed. In this technology a socket Application Programming Interface API hooking function is inserted into a network program running on a Microsoft MS Windows operating system via Dynamic Linked Library injection hereinafter referred to as DLL injection so that a network program intercepts a packet transmitted or received to or from a counterpart network program using a socket API function fabricates the corresponding packet or deforms the packet into an abnormal packet by adding various fuzzing data sets to the data of the packet and transmits the abnormal packet thus performing network fuzzing on unknown protocols as well as universal protocols.

Accordingly the present invention has been made keeping in mind the above problems occurring in the prior art and an object of the present invention is to provide a system and method for fuzzing a network application program which use a captured packet upon fuzzing a network application program and thus neither a protocol analysis procedure nor the production of a fuzzer program is required.

In accordance with an aspect of the present invention to accomplish the above object there is provided a system for fuzzing a network application program including a fuzzing performance client program unit for generating a packet to be transmitted from a captured packet applying a fuzzing rule to the packet to be transmitted and outputting a resulting packet and a fuzzing supervisor program unit for providing the packet from the fuzzing performance client program unit to a target program to be fuzzed monitoring an event and abnormal termination of the target program to be fuzzed and analyzing a situation of termination to verify security vulnerabilities if abnormal termination has occurred.

The fuzzing performance client program unit may include a captured packet database DB for storing packets captured from content communicated by the target program to be fuzzed a packet generation unit for loading the captured packet stored in the captured packet DB and generating the packet to be transmitted a fuzzing rule DB for storing fuzzing rules required to apply malformation for fuzzing to the packet generated by the packet generation unit and a fuzzing rule application unit for applying a corresponding fuzzing rule stored in the fuzzing rule DB to the packet generated by the packet generation unit and outputting a resulting packet.

The fuzzing rules stored in the fuzzing rule DB may include rule application conditions required to determine whether to apply a rule to malformation of data for fuzzing and application rules enabling any data to be inserted into a specific field of the generated packet or to be deleted from the specific field or enabling data in the specific field to be malformed for individual fields of a network protocol.

Each of the rule application conditions may include one or more of a packet sequence and a packet data pattern.

The fuzzing rule application unit may be configured to apply or not apply the fuzzing rule to the packet generated by the packet generation unit depending on whether an application condition to be applied to the packet is present in the fuzzing rule DB.

The fuzzing rule application unit may be configured to if the fuzzing rule is applied malform and output single bit or multi bit data of the packet generated by the packet generation unit before the corresponding packet is output.

The fuzzing rule application unit may be configured to if the fuzzing rule is not applied output the packet generated by the packet generation unit without modifying the packet.

The fuzzing supervisor program unit may include a state monitoring unit for monitoring an event and abnormal termination of the target program to be fuzzed an event recording unit for recording the event monitored by the state monitoring unit and an analysis unit for as the state monitoring unit detects occurrence of abnormal termination of the target program to be fuzzed analyzing a situation of abnormal termination to verify security vulnerabilities.

The fuzzing performance client program unit may initiate fuzzing after the target program to be fuzzed has been executed.

The fuzzing supervisor program unit may be installed on a server computer and is operated in a form of a local proxy.

In accordance with another aspect of the present invention to accomplish the above object there is provided a method for fuzzing a network application program including generating by a fuzzing performance client program unit a packet to be transmitted from a captured packet applying by a fuzzing performance client program unit a fuzzing rule to the packet to be transmitted and outputting by the fuzzing performance client program unit a resulting packet providing by a fuzzing supervisor program unit the packet output from the fuzzing performance client program unit to a target program to be fuzzed and monitoring by the fuzzing supervisor program unit an event and abnormal termination of the target program to be fuzzed and analyzing by the fuzzing supervisor program unit a situation of termination to verify security vulnerabilities if abnormal termination of the target program to be fuzzed has been detected.

The present invention may be variously changed and may have various embodiments and specific embodiments will be described in detail below with reference to the attached drawings.

However it should be understood that those embodiments are not intended to limit the present invention to specific disclosure forms and they include all changes equivalents or modifications included in the spirit and scope of the present invention.

The terms used in the present specification are merely used to describe specific embodiments and are not intended to limit the present invention. A singular expression includes a plural expression unless a description to the contrary is specifically pointed out in context. In the present specification it should be understood that the terms such as include or have are merely intended to indicate that features numbers steps operations components parts or combinations thereof are present and are not intended to exclude a possibility that one or more other features numbers steps operations components parts or combinations thereof will be present or added.

Unless differently defined all terms used here including technical or scientific terms have the same meanings as the terms generally understood by those skilled in the art to which the present invention pertains. The terms identical to those defined in generally used dictionaries should be interpreted as having meanings identical to contextual meanings of the related art and are not interpreted as being ideal or excessively formal meanings unless they are definitely defined in the present specification.

Embodiments of the present invention will be described in detail with reference to the accompanying drawings. In the following description of the present invention the same reference numerals are used to designate the same or similar elements throughout the drawings and repeated descriptions of the same components will be omitted.

The system for fuzzing a network application program according to the embodiment of the present invention includes a fuzzing performance client program unit a fuzzing supervisor program unit and a fuzzing target server program unit .

In a captured packet database DB captures and stores packets from content communicated by the fuzzing target server program unit before the fuzzing method of the present invention is performed. That is the captured packet DB stores the captured packets and has a format in which each packet occurring in transmission reception over a network is captured using a tool such as tcpdump or Wireshark which is developed using for example a packet capture pcap library and is stored as a file.

The fuzzing rule DB stores fuzzing rule data sets required to apply malformation for fuzzing to each packet loaded and generated from the captured packet DB .

The fuzzing performance client program unit is installed on the client computer and both the fuzzing supervisor program unit and the fuzzing target server program unit are installed on a server computer .

The fuzzing performance client program unit loads a captured packet from the captured packet DB generates data of a packet to be transmitted applies or does not apply a fuzzing rule to the generated packet depending on whether an application condition which will be applied to the packet data to be transmitted is present in the fuzzing rule DB and transmits the packet to the fuzzing supervisor program unit . If a rule application condition is not applied when the captured packet is transmitted through the fuzzing performance client program unit the generated packet is transmitted with the stored content of the packet maintained without the packet data thereof being modified.

Accordingly the fuzzing performance client program unit may be regarded as including a packet generation unit and a fuzzing rule application unit . The packet generation unit loads a captured packet from the captured packet DB and generates packet data to be transmitted. The fuzzing rule application unit applies or does not apply a fuzzing rule to the packet data generated by the packet generation unit depending on whether an application condition is present in the fuzzing rule DB . Here when the fuzzing rule is applied the fuzzing rule application unit malforms single bit data or multi bit data of the packet generated by the packet generation unit and outputs the malformed data before the corresponding packet is transmitted.

The fuzzing supervisor program unit is operated in the form of a local proxy on the server computer and is configured to exchange packets with the fuzzing target server program unit and monitor an event in and abnormal termination occurring in the fuzzing target server program unit .

Accordingly the fuzzing supervisor program unit may be regarded as including a state monitoring unit an event recording unit and an analysis unit . The state monitoring unit exchanges packets with the fuzzing target server program unit and monitors an event and abnormal termination occurring in the fuzzing target server program unit . The event recording unit records the event monitored by the state monitoring unit . As the state monitoring unit detects the abnormal termination of a program occurring in the fuzzing target server program unit the analysis unit analyzes the situation of termination that is a situation in which the program is abnormally terminated so as to verify security vulnerabilities.

The fuzzing target server program unit is equipped with a fuzzing target server program that may be regarded as a target program to be analyzed. The fuzzing target server program unit executes the fuzzing target server program in compliance with a fuzzing initiation command output from the fuzzing supervisor program unit .

In the case of the configuration shown in the fuzzing performance client program unit is initially executed on the client computer and the fuzzing supervisor program unit is executed on the server computer .

The fuzzing target server program unit is executed by the fuzzing supervisor program unit on the server computer .

In the performance of fuzzing is initiated by the fuzzing supervisor program unit and the fuzzing target server program unit is executed and thereafter the fuzzing initiation command is transferred to the fuzzing performance client program unit .

Accordingly the packet generation unit of the fuzzing performance client program unit loads a captured packet from the captured packet DB and generates a packet and the fuzzing rule application unit searches the fuzzing rule DB for a fuzzing rule corresponding to the generated packet finds the fuzzing rule applies the fuzzing rule to the corresponding packet and generates from the packet a request packet malformed for fuzzing.

Thereafter the fuzzing performance client program unit transmits the request packet malformed for fuzzing to the fuzzing supervisor program unit .

Therefore the fuzzing supervisor program unit transfers the request packet malformed for fuzzing to the fuzzing target server program unit receives a response from the fuzzing target server program unit and then forwards the response to the fuzzing performance client program unit .

The fuzzing rule DB stores fuzzing rules which include rule application conditions and application rules .

Each of the rule application conditions includes a packet sequence or a packet data pattern . The rule application condition specifies conditions corresponding to one or more of the packet sequence and the packet data pattern and determines whether to apply the corresponding rule to the malformation of data for fuzzing.

The application rules enable any data to be inserted into a specific field of packet data or to be deleted from the specific field or enable the data in the specific field to be malformed for individual fields of a network protocol.

First before fuzzing is performed the fuzzing performance client program unit is installed and executed on the client computer and the fuzzing supervisor program unit is installed on the server computer and executed in the form of a local proxy.

At step S the fuzzing supervisor program unit in the server computer executes the fuzzing target server program unit .

At step S the fuzzing supervisor program unit transfers a fuzzing initiation command to the fuzzing performance client program unit currently running on the client computer . In this case the request packet is prevented from being lost by causing the execution of the fuzzing target server program unit to precede the initiation of fuzzing performed by the fuzzing performance client program unit .

At step S the fuzzing performance client program unit that received the fuzzing initiation command loads a captured packet from the captured packet DB and the packet generation unit generates a packet to be transmitted.

At step S the fuzzing performance client program unit generates a request packet malformed for fuzzing by searching the fuzzing rule DB for a rule to be applied and by applying the found rule to the generated packet.

At step S the fuzzing performance client program unit transfers the request packet malformed for fuzzing to the fuzzing supervisor program unit of the server computer .

At step S the fuzzing supervisor program unit forwards the request packet malformed for fuzzing to the fuzzing target server program unit .

At step S the fuzzing target server program unit transfers a response packet to the request packet malformed for fuzzing to the fuzzing supervisor program unit .

At step S the fuzzing supervisor program unit forwards the received response packet to the fuzzing performance client program unit .

The fuzzing performance client program unit loads a packet to be transmitted from captured packets generates a request packet malformed for fuzzing by applying the fuzzing rule stored in the fuzzing rule DB to the packet and transfers the request packet to the fuzzing supervisor program unit of the server computer .

At step S the fuzzing performance client program unit loads a packet to be transmitted from the captured packet DB .

At step S the fuzzing performance client program unit generates data of a packet to be transmitted via the packet generation unit .

Then at step S the fuzzing performance client program unit determines via a search whether a fuzzing rule to be applied is present in the fuzzing rule DB by means of the packet sequence in the content of the generated packet data and pattern matching based on the packet content.

At step S if it is determined that the fuzzing rule to be applied is present the fuzzing performance client program unit applies the fuzzing rule to the packet via the fuzzing rule application unit . A type of packet in which the fuzzing rule is applied to the packet may be regarded as the request packet malformed for fuzzing.

Next at step S the fuzzing performance client program unit transmits the request packet malformed for fuzzing to the fuzzing supervisor program unit of the server computer .

If the rule application condition is not applied when the captured packet is transmitted through the fuzzing performance client program unit No at step S the packet is transmitted with the stored content of the packet maintained without the packet data being modified.

First at step S the fuzzing supervisor program unit executes the fuzzing target server program unit . By this operation the fuzzing target server program unit initiates a fuzzing target server program.

At step S the fuzzing supervisor program unit transfers a fuzzing initiation command to the fuzzing performance client program unit at the request of a network. Accordingly the fuzzing performance client program unit initiates a fuzzing performance client program.

At step S the fuzzing supervisor program unit receives a packet that is a request packet malformed for fuzzing from the fuzzing performance client program unit .

At step S the fuzzing supervisor program unit transmits the packet that is the request packet malformed for fuzzing received from the fuzzing performance client program unit to the fuzzing target server program unit .

Accordingly at step S an event for a fuzzing target server program that is running in the fuzzing target server program unit is monitored.

As a result of the monitoring at step S if the abnormal termination of the fuzzing target server program has been detected the event is recorded and analyzed at step S and the process returns to step S.

Meanwhile as a result of the monitoring at step S if an additional event other than the event for abnormal termination has occurred the corresponding event is recorded at step S and the process returns to step S.

In accordance with the present invention an existing packet that was exchanged between a client and a server in the past is used and thus a protocol analysis procedure may be omitted. A fuzzing performance client program for applying a fuzzing rule to a packet depending on the rules in a fuzzing rule DB and for performing fuzzing is used and thus a separate procedure for producing a fuzzing performance program may be omitted.

In other words the present invention is advantageous in that upon fuzzing a network application program a method of applying a fuzzing rule to a captured packet and transmitting a resulting packet is used so that fuzzing is possible in a situation in which a fuzzing target server program and a captured packet are present and conventional protocol analysis and the production of a separate program are not required thus improving the efficiency of manpower and time upon performing fuzzing.

As described above optimal embodiments of the present invention have been disclosed in the drawings and the specification. Although specific terms have been used in the present specification these are merely intended to describe the present invention and are not intended to limit the meanings thereof or the scope of the present invention described in the accompanying claims. Therefore those skilled in the art will appreciate that various modifications and other equivalent embodiments are possible from the embodiments. Therefore the technical scope of the present invention should be defined by the technical spirit of the claims.

