---

title: Method and devices to invite a user from an external chat service to a group chat session
abstract: This is a method and devices used to invite a user from one message chat service into a preexisting group chat session located on another chat service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09391788&OS=09391788&RS=09391788
owner: Infinite Convergence Solutions, Inc
number: 09391788
owner_city: Arlington Heights
owner_country: US
publication_date: 20140416
---
This application claims the benefit of U.S. Provisional Application No. 61 813 556 filed on Apr. 18 2013 by the present inventors which is incorporated by reference into this application.

This relates to a method and devices which invite a user from one message chat service into a preexisting group chat on another service.

With the growing adoption of Internet capable smartphones wireless carriers face competition from Over the Top OTT messaging providers such as Facebook Messenger WhatsApp Kik Tango Viber and others. These OTT providers typically operate closed chat systems designed in such a way that OTT users and RCS messaging users on wireless carriers cannot form mixed group chat sessions. This is a method by which carriers on one chat system such as wireless carriers using Rich Communication Suite can invite and enable OTT messaging users to join an operator based Rich Communication Suite RCS based instant messaging session. Notably this method only requires that one member of an ongoing Rich Communication Suite RCS group chat session be a member of the OTT messaging service in order for all members of the RCS group to exchanges messages with the OTT message service. Conventional solutions have proposed to set up a server to server cooperation chat federation between OTT messaging systems and RCS based messaging systems or use of a gateway. These proposals work for scenarios where every RCS user has an account in both messaging system but they create a poor user experience for group chat sessions involving users who have an account in only one of the messaging systems. What is needed is a method to easily invite members of an OTT message service into an ongoing RCS chat without every member of the RCS chat needing credentials in the OTT messaging system.

This is a new way for users of one chat service to invite users of another chat service into a group chat session. In the preferred embodiment RCS a.k.a Joyn clients in a group chat invite one or more users of over the top OTT instant messaging systems to participate in RCS based instant messaging sessions controlled by a wireless carrier. In the preferred embodiment a network API which may include but is not limited to an XMPP based API is used to invite users on that external chat system to join a chat conversation on a separate local chat system. The invitation partially or wholly consists of a Unifrom Resource Identifier URI and is transmitted over a messaging connection established through the network API provided by the external chat system.

This URI may be transmitted from either a client or the server associated with the first chat system. In the preferred embodiment this URI is accompanied by a text message invitation originating from a user in the first chat system.

When the user on the external chat system receives the URI and clicks on the hyperlink associated with the URI the user device launches a web browser and loads a web based thin client. The thin client then uses asynchronous HTTP requests to participate in the chat conversation in the local chat system in the particular group session which is associated with that URI.

A mobile client on a wireless carrier such as Verizon Wireless could use this to invite users on an OTT chat system such as Facebook Messenger to join an RCS chat session previously established in that wireless carrier s network.

Those with ordinary skill in the art will realize that steps iii and step v can occur in earlier parts of the process. Also step vi can be modified to have the URI sent directly from Chat server A instead of via a client on server A. In addition those with ordinary skill in the art will recognize that is a simplified diagram omitting some network elements such as SGSN GGSN Internet Protocol routers media gateways and other devices.

In order to support this method a messaging client device capable of participating in a group chat on a first chat service is modified to transmit a Uniform Resource Identifier to a different chat service. The messaging client is additionally modified to allow the inviting user to add a custom message including but not limited to a text voice file or custom video to the URI e.g. Mike Please join Jim and I discussing the proposal now. The customization message is often required by terms of service of some OTT providers which prohibit computer generated invitations to chat. Alternately the URI may be sent directly from the messaging server associated with the inviting client with the target recipient and the text supplied by the inviting client.

It is necessary for the messaging server associated with the inviting client to be modified to generate an URI associated with a group message session and also modified to accept asynchronous HTTP requests from the invited user. It is further necessary for the server to be modified to translate the HTTP requests into the protocol used by the particular ongoing group chat.

