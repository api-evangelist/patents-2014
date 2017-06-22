---

title: Dynamic tunnel for real time data communication
abstract: A tunneled session management (“TSM”) server manages a dynamic datagram tunnel (“DDT”) for a real time communication (“RTC”) with a TSM client. The TSM server establishes a stream based tunnel with the TSM client and then establishes the RTC via the stream based tunnel, where the RTC includes communicating a first channel for signaling traffic and a second channel for media traffic. Then, it is determined whether to establish the DDT for communicating the media traffic, and if so, the DDT is established and the second channel is communicated via the DDT while the first channel is maintained on the stream based tunnel.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09444792&OS=09444792&RS=09444792
owner: Oracle International Corporation
number: 09444792
owner_city: Redwood Shores
owner_country: US
publication_date: 20141021
---
One embodiment is directed generally to a communication network and in particular to delivering real time media over a communication network.

Many enterprises have moved from telephony services using the Public Switched Telephone Network PSTN provided by a traditional telephone company to telephony services using the Internet Protocol IP provided by an IP Telephony service provider . Such services are commonly known as Voice over IP VoIP or IP Telephony. IP Telephony uses an IP network e.g. the Internet as a backbone and can thus provide advanced features such as video conferencing call recording and call forwarding.

Embodiments manage a dynamic datagram tunnel DDT for a real time communication RTC with a tunneled session management TSM client. Embodiments establish a stream based tunnel with the TSM client and then establish the RTC via the stream based tunnel where the RTC includes communicating a first channel for signaling traffic and a second channel for media traffic. Then it is determined whether to establish the DDT for communicating the media traffic and if so the DDT is established and the second channel is communicated via the DDT while the first channel is maintained on the stream based tunnel.

One embodiment provides real time communication RTC services in a network environment by establishing a dynamic datagram tunnel DDT that carries real time media traffic between end users and remote servers while traversing security devices such as firewalls. Accordingly by traversing security devices this embodiment provides secure RTC services. Further by using a datagram tunnel this embodiment addresses RTC requirements such as call quality which may be affected by impairments such as latency packet loss and or jitter .

In order to communicate media and provide RTC UE communicates with media server and signaling server over two channels a first channel for signaling traffic via a Session Initiation Protocol SIP and a second channel for media traffic. SIP is a signaling communications protocol conventionally used for controlling multimedia communication sessions such as voice and video calls over IP networks.

Network further includes a tunneled session management TSM client included within UE and a TSM server that together establish and manage tunnels e.g. and for supporting RTC over IP network . In general using a tunnel for communication refers to using a delivery protocol to encapsulate a different payload protocol. TSM client includes a tunnel service client TSC and an application . In one embodiment application is SIP based and relies on a TSM library such as the TSM library provided by Oracle s TSM software development kit SDK . TSM server includes a tunnel service control function TSCF and a session border controller SBC . SBC is a device regularly deployed in Voice over IP VoIP networks to control the signaling and typically also the media streams involved in setting up conducting and tearing down phone calls or other interactive media communications.

Network further includes security devices such as firewalls or proxies not shown that provide security for end user traffic. In general a firewall is a software or hardware based network security system that controls the incoming and outgoing network traffic based on applied rules. In network tunnels may traverse firewalls so that RTC services are provided in a secure manner.

System includes a bus or other communication mechanism for communicating information and a processor coupled to bus for processing information. Processor may be any type of general or specific purpose processor. System further includes a memory for storing information and instructions to be executed by processor . Memory can be comprised of any combination of random access memory RAM read only memory ROM static storage such as a magnetic or optical disk or any other type of computer readable media. System further includes a communication device such as a network interface card to provide access to a network. Therefore a user may interface with system directly or remotely through a network or any other method.

Computer readable media may be any available media that can be accessed by processor and includes both volatile and nonvolatile media removable and non removable media and communication media. Communication media may include computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media.

Processor may further be coupled via bus to a display such as a Liquid Crystal Display LCD . A keyboard and a cursor control device such as a computer mouse may further be coupled to bus to enable a user to interface with system on an as needed basis.

In one embodiment memory stores software modules that provide functionality when executed by processor . The modules include an operating system that provides operating system functionality for system . The modules further include a dynamic tunnel module for providing secure RTC communications and all other functionality disclosed herein. In one example embodiment dynamic tunnel module may include TSM server of . System can be part of a larger system such as added functionality to the Acme Packet from Oracle Corp. Therefore system can include one or more additional functional modules to include the additional functionality. A database is coupled to bus to provide centralized storage for modules and .

Referring again to with known systems when communicating first channel for signaling traffic via SIP and second channel for media traffic between UE and servers these channels may not go through firewalls because firewalls are normally filtered to a specific port and transport type and may only pass one type of traffic.

One known solution to communicate both of these channels through firewalls is to encapsulate both channels within a tunnel with a delivery protocol such as a transmission control protocol TCP . TCP is one of the core protocols of the IP suite and provides reliable ordered and error checked delivery of a stream of octets between programs running on computers connected to an IP network such as local area network intranet or the public Internet. Accordingly a TCP tunnel is stream based. The resulting TCP tunnel that encapsulates the SIP channel i.e. first channel and the media channel i.e. second channel can then traverse a firewall .

One disadvantage with this known approach is that this tunnel runs over TCP which is a stream based protocol and therefore not appropriate for media type of traffic as media is susceptible to delay and jitter.

In contrast to the known solutions one embodiment of the present invention dynamically supports two concurrent tunnels a stream based tunnel for communicating first channel for signaling traffic and a dynamic datagram tunnel DDT for communicating second channel for media traffic. A datagram is a basic transfer unit associated with a packet switched network. For such datagram the delivery arrival time and order of arrival need not be guaranteed by the network. In this embodiment stream based tunnel may use a stream based protocol such as TCP or a Transport Layer Security TLS protocol while DDT may use a protocol appropriate for media such as a User Datagram Protocol UDP or a Datagram Transport Layer Security DTLS protocol.

TLS is a cryptographic protocol designed to provide communication security over the Internet. UDP is a protocol that uses a simple connectionless transmission model with a minimum of protocol mechanism. Applications that do not require the reliability of a TCP connection may instead use UDP which emphasizes low overhead operation and reduced latency rather than error checking and delivery validation. DTLS protocol provides communications privacy for datagram protocols. UDP and DTLS are optimized for real time media transport. On the contrary TCP and TLS have head of line blocking issues which may be further aggravated by possible extensive packet loss and network latency. However TCP TLS are needed for some VoIP services where signaling e.g. call invites must arrive via a TCP channel in order to wake up a called party. TCP TLS firewall bindings are usually kept open much longer than those of UDP DTLS.

In one embodiment DDT is provided by dynamically determining whether to use a single stream based e.g. TCP or TLS based tunnel or to use both a stream based tunnel and a datagram based e.g. UDP or DTLS based tunnel. In one embodiment a switch may be provisioned e.g. programmed at the client e.g. within TSM client so that while communicating over an existing stream based tunnel the client may designate a specific real time protocol RTP channel to run in DDT mode. Accordingly DDT service is provided by creating on demand datagram tunnels based on client configuration. Upon activation of such switch TSM client creates a parallel datagram based tunnel DDT which is reliable for media and also minimizes latency. Then TSM client moves the designated RTP to DDT while SIP remains on stream based tunnel . Accordingly based upon the state of the switch TSM client dynamically moves RTP between stream based tunnel and DDT to improve voice quality.

In one alternative embodiment the decision on whether to use only stream based tunnel or to use both stream based tunnel and DDT may be based on the quality of the two tunnels instead of or in addition to the status of a switch at the client.

In one embodiment based on the status of DDT service at TSM client TSCF of TSM server provides configuration to disable enable DDT service at TSCF .

In one embodiment when DDT service is enabled at TSM client the protocol used to establish DDT is based on the protocol of the existing stream based tunnel . If DDT service is enabled while stream based tunnel is TCP based DDT will be UDP based running on the same port as stream based tunnel . If DDT is enabled while stream based tunnel is TLS based DDT tunnel will be DTLS based running on the same port as stream based tunnel . In this embodiment when DDT service is enabled TSCF of TSM server may detect any missing tunnel pairs and warn TSM client .

In one embodiment DDT service is activated at TSM client and TSM server according to the following functionality 

In one embodiment in the most common scenario and to guarantee performance TCP TLS tunnels i.e. stream based tunnel are used for sending receiving signaling and connection maintenance information and UDP DTLS tunnels i.e. DDP are used for sending receiving media i.e. audio video fax . In this embodiment during datagram tunnel reservation TSM server reserves a new datagram tunnel i.e. DDT that is configured to provide the same inner IP address as that used by the main stream tunnel i.e. stream based tunnel . For example if 1.1.1.2 is used for a TLS tunnel 1.1.1.2 will be also used for the matching DTLS tunnel thereby guaranteeing transparent transition of media traffic from stream based tunnel to DDT . Accordingly SIP signaling will use the IP address of TLS tunnel 1.1.1.2 and SDP offer or answer will include the same IP address 1.1.1.2. In this embodiment TSM server associates assigned IP addresses with specific tunnels and routes packets via the corresponding tunnels.

In one embodiment DDT service is one of the assigned services that a TSCF interface can have. If it is present in the corresponding comma separated assigned services list DDT service will be enabled for the applicable TSCF interface and if it is absent DDT service will be disabled. By default DDT service is disabled.

In one embodiment TSC client can request DDT service by sending a client service request message. Upon receiving this request TSCF at TSM server checks if DDT service is enabled for the TSCF interface on which the client service request is received. If DDT service is enabled TSCF sends a response message indicating success. Otherwise TSCF sends a response message indicating that DDT service is unavailable.

In one embodiment DDT service is requested by the client application i.e. application via an API for example by setting the appropriate TSM SDK socket option as follows 

In this embodiment if tsc setsockopt returns 1 the option has not been set correctly. If it returns 0 it has been set correctly but DDT service will not be officially enabled until the new datagram tunnel i.e. DDT is created. A new notification tsc notification ddt can be used to notify TSM client about DDT enablement. The following pseudo code illustrates how the notification is enabled and further shows callback 

The fourth NULL parameter in tsc notification enable is an opaque private data pointer that can be recovered in the tsc notification data structure upon callback.

In this example embodiment the changes to the corresponding Extensible Markup Language XML file are as follows 

In one embodiment the assigned services parameter is real time reconfigurable. However new values are only applied to newly established tunnels.

In one embodiment messages exchanged between clients are logged by TSM SDK in their corresponding client logs. In this embodiment control messages forwarded by the session director are logged in a corresponding data log.

At TSM server establishes stream based tunnel with the TSM client . For example a TSM library at application creates stream based tunnel and once a SIP call is established on stream based tunnel and RTP is negotiated by SDP information exchange an RTP media socket is created on stream based tunnel .

At TSM server establishes RTC via stream based tunnel with TSM client where the RTC includes communicating first channel for signaling traffic and second channel for media traffic.

At TSM server determines whether to establish DDT for communicating media traffic for example based on a message received from TSM client and or dynamically based on the quality of stream based tunnel and DDT . For example to induce DDT on RTP media socket it is marked to run on a new separate datagram tunnel. When a binding function is executed on the RTP media socket and since it resides on stream based tunnel the CSM at TSM client sends a TSCF service request to TSM server to initiate DDT services.

At TSM server establishes DDT with the TSM client . For example when TSM server receives the TSCF service request it reserves DDT which is UDP or DTLS based if stream based tunnel is TCP or TLS based respectively. TSM server sends a service response back to TSM client indicating the TSCF TID of DDT . CSM then negotiates DDT by sending a configuration request and processing the corresponding response. At this point CSM moves RTP media socket from stream based tunnel to DDT . While DDT is being negotiated and until RTP media socket is moved from stream based tunnel to DDT all traffic sent received by RTP media socket is on stream based tunnel .

At TSM server communicates second channel via DDT while maintaining first channel on stream based tunnel .

As disclosed embodiments use on demand datagram tunnels in parallel with stream based tunnels for providing real time communication. This gives the end user the possibility of having secure real time communication that also meets real time application quality requirements.

Several embodiments are specifically illustrated and or described herein. However it will be appreciated that modifications and variations of the disclosed embodiments are covered by the above teachings and within the purview of the appended claims without departing from the spirit and intended scope of the invention.

