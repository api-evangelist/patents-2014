---

title: Wireless internet gateway limiting message distribution
abstract: A wireless Internet gateway bridges wireless devices to the Internet, e.g., via a short message service center (SMSC). The gateway provides a portal to SMPP, HTTP, TNPP, or other protocol messages using Java Remote Method Invocation (RMI) techniques. Application servers insert RMI objects containing messages in a message queue handler of the gateway. The RMI objects are queued and passed either directly to a destination delivery handler (e.g., SMPP, SMTP, HTTP or TNPP protocol handler), or passed through a generic destination interface. An SMTP handler provides direct communication of SMTP protocol messages (i.e., email) to the message queue. An SMPP link proxy module provides direct access between a local application server and the destination delivery handler. The messages are packaged into relevant messages of the particular destination protocol (e.g., SMPP), and transmitted to the relevant network element (e.g., to an SMSC).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09172821&OS=09172821&RS=09172821
owner: TeleCommunication Systems, Inc.
number: 09172821
owner_city: Annapolis
owner_country: US
publication_date: 20141016
---
