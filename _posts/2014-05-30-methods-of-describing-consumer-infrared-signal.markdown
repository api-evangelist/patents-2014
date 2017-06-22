---

title: Methods of describing consumer infrared signal
abstract: The present invention discloses a method of describing infrared signal, and infrared signal has a continuous infrared wave type, the method comprises: a step (a) separating the continuous infrared wave into at least one frame; a step (b) separating the at least one frame into at least one signal sequence and at least one data sequence; a step (c) separating the at least one signal sequence into a signal with a level and a duration; a step (d) separating the at least one data sequence into at least one logic signal set, wherein the at least one logic signal set is separated into at least one signal with a level and a duration; and (e) unifying description for the plurality of infrared signals having the same control function.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09396650&OS=09396650&RS=09396650
owner: BOMEANS INDUSTRIAL INC.
number: 09396650
owner_city: Apia
owner_country: WS
publication_date: 20140530
---
The present invention relates to a method of decomposing consumer infrared signals and describing the same in a unified description language.

Infrared IR light is wildly used in industrial scientific communication and medical applications. In 1980s remote controllers utilizing infrared were developed which rapidly took the place of typical ultrasound devices. This usage of infrared for remotely controlling the consumer electronic appliances such as a TV or DVD is then categorized as Consumer IR CIR . Nowadays although some advanced radio transmission technologies such as Wireless or Bluetooth were developed the IR technology is still wildly used in remote controllers due to its small footprint low cost and low power consumption.

IR remote controls involve both the transmission and receiving which have the functionalities as followed 

At the transmission side as a key is pressed on the remote controller the controlling command is correspondingly generated and then encoded as a series of formatted data signals known as IR protocol or format. The data signals are then modulated and transmitted by an infrared transmitter. Those IR signals while being received at the receiving end are demodulated and decoded as the original control command.

Most of the modulations used in CIR are pulse width modulation PWM and pulse distance modulation PDM . For the PWM modulations the common carrier frequency is 38K but other frequencies such as 56K 40K 36K etc are also used. At the early stage of CIR dedicated ICs were developed by various vendors with their own protocol designs. Since lack of standard protocol specification the developed IR protocols are different from one another. The situation is getting more complicated after the introduction of micro controllers. More IR protocols were developed since they can be easily defined programmatically. This complexity becomes the major issue for the vendors of universal remote controller which is a kind of remotes that can be programmed to transmit various IR protocols to control various electronic appliances.

To tackle this issue many vendors have their own ways to record and reproduce the IR protocols. Most of them are just hardcoding the IR timing signals of the transmission protocols. This approach is easy to implement but lack of flexibility and extensibility. For example when a new protocol is to be added to the exiting protocol pool the associated firmware or software has to be altered accordingly.

This invention is hereby to provide a method to decompose the CIR signals into a layered structure and then describe it by using a unified scripting language with defined specification. The resulting scripts can then be interpreted and reassembled into the original IR protocol by the firmware of universal remotes software applications of PC or the APPs on the mobile devices. By using this approach when a new IR protocol is launched in market only a new scripting file for this new protocol needs to be added into the local memory or Cloud storage without the need of updating the existing interpreting firmware or software.

The present invention provides a method for describing consumer infrared protocols in a common way. The script description which is capable of describing different CIR protocols from all of the manufacturers is in the XML format or its JSON counterpart that can be stored in local memory or Cloud storage.

As a result when a specific CIR protocol is to be reproduced the XML JSON file describing the protocol is accessed from the local memory in the case of stand alone remotes or from the web storages via dedicated application programming interfaces APIs in the case of network enabled devices. The fetched scripting file is then be interpreted and reassembled into the CIR protocol which can be sent to the transmission hardware to send out the IR signals.

To aim at the above purpose of the present invention the method of describing infrared signal comprises 

a step b separating the at least one frame into at least one signal sequence and at least one data sequence 

a step d separating the at least one data sequence into at least one logic signal set wherein the at least one logic signal set is separated into at least one signal with a level and a duration and

a step e unifying description for the plurality of infrared signals having the same control function.

The invention is more fully appreciated by reference to the following description including the following glossary of terms and the concluding examples. For the sake of brevity the disclosures of the publications including patents cited in this specification are herein incorporated by reference.

Recall that prior art defects most of these remote controls communicate to their respective devices such as stereo systems DVD players via some specific infrared protocol and a few via radio signals. In other words as far as the current technology of remote controls is taken into consideration a specific electronic device is merely controlled by a specific remote control made by specific customer manufacturers such as Sony Panasonic Sampo etc. This means that the more electronic devices growth quickly the more IR remote controls become enormous in number.

A step b comprises separating the at least one frame into at least one signal sequence and at least one data sequence 

A step c comprises separating the at least one signal sequence into a signal with a level and a duration and

A step d comprises separating the at least one data sequence into at least one logic signal set wherein the at least one logic signal set is separated into at least one signal with a level and a duration.

A step e comprises unifying description for the plurality of infrared signals having the same control function.

After processing IR wave types of consumer infrared remote controllers a common format for describing those IR parameters which is capable of accessing utilizing a new transmission protocol is taken into consideration. Thus the present method adopts a set of rules for encoding those processed IR wave types in the common format such as Extensible Markup Language XML which is widely used for the representation of arbitrary data structures of IR wave types especially in web service. Thus a step e is further provided comprising unifying description for the plurality of infrared signals having the same control function.

Upon an introduction to the key constructs of those processed IR wave types in XML below is an example according to that is an infrared signal wave type of 

Upon another introduction to the key constructs of those processed IR wave types in XML below is an example according to that is another infrared signal wave type of 

The above two examples including and in this section are based on the XML Specification. This is not only involving an exhaustive list of all the constructs such as frame sequence and signal that appear in XML but also providing definition to each of the key constructs being most often encountered IR parameters in use.

The frame tag specifies an IR frame which is usually composed of lead code data bits and end code sequences.

When a new IR protocol such as is described in an XML format as stated previously in the present specification the new IR protocol associated with other IR remote control parameters including each key s function is also described in the XML format as below 

For example encoding XML tag and of wherein each value information of custom code bits 16 and key code bits 8 is referred to the following contents 

Therefore not only the new IR protocol is described in the XML format but also it is associated with other IR remote control parameters such as each key s whose function adopt the same describing manner. And those XML format are all together stored in the local memory or Cloud storage.

Apart from XML mentioned in the above readings an example could include JSON to fulfill this tag role which is an open standard format that uses human readable text to transmit data objects consisting of attribute value pairs. So it is used primarily to transmit data between a server and web application as well as XML both of these formats have widespread support for creation reading and decoding.

One advantage of the present invention is that when a new IR protocol is launched in market only a new scripting file for this new protocol in XML JSON format is added into in local memory or Cloud storage without updating the existing interpreting firmware or software.

As a result after the XML JSON file describing the IR protocol is accessed from the local memory or Cloud storage in the case of stand alone remotes or from the web storages via dedicated application programming interfaces APIs in the case of network enabled devices. The fetched scripting file is then be interpreted and reassembled into the IR protocol which can be sent to the transmission hardware to send out the IR signals. For example the descriptions of from the step d to the step a in XML format is parsed to the original IR signals in a reverse direction.

After receiving the IR signals by the receiving end such as electronic consumer appliances those signals are demodulated and decoded as the original control command In detail when the receiving end successfully recognizes the new IR protocol later other IR commands of the keys cause the device to respond accordingly.

So one to one dependent control relationship even if universal remote controller mentioned in prior art cannot easily overcome a new protocol issue added into the current firmware or software that is thus free from after the XML JSON file for describing the IR protocol is accessed from the local memory or Cloud storage realized in the present specification.

In this document the terms a and an are used which are common in patent documents to include one or more than one independent of any other instances or usages of at least one or one or more. In this document the term or is used to refer to a nonexclusive or such that A or B includes A but not B B but not A and A and B unless otherwise indicated. In this document the terms including and in which are used as the plain English equivalents of the respective terms comprising and wherein. Also in the following claims the terms including and comprising are open ended that is a system device article or process that includes elements in addition to those listed after such a term in a claim are still deemed to fall within the scope of that claim

Those skilled in the art recognize the foregoing outline as a description of the method for communicating hosted application information. The skilled artisan will recognize that these are illustrative only and that many equivalents are possible.

