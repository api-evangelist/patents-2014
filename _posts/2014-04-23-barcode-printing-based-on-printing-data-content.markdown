---

title: Barcode printing based on printing data content
abstract: A method and system is provided for printing a barcode computed based on content of a printed page data system on a document, the method comprising: using a methodology of regular expression; applying a regular expression subsystem to text contained in a print stream generating data; converting the data to a barcode applying barcode computation, to produce a bitmap barcode representing the barcode; inserting the bitmap barcode into an Enhanced Meta File (EMF) print stream defined by the printing system in the Port Monitor or Print Processor subsystem; inserting the bitmap barcode into an XML Paper Specification (or XPS) print stream defined by the printing system in the Port Monitor or Print Processor subsystem; and combining the barcode with the print stream to contain the barcode in a specific position in the print stream in the Port Monitor or Print Processor subsystem.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09135539&OS=09135539&RS=09135539
owner: Black Ice Software, LLC
number: 09135539
owner_city: Nashua
owner_country: US
publication_date: 20140423
---
This application claims the benefit of U.S. Provisional Application No. 61 814 953 filed Apr. 23 2013. This application is herein incorporated by reference in its entirety for all purposes.

The invention relates to barcode printing and more particularly to a method and system for the insertion of a content based barcode into a print stream.

One embodiment of the present invention provides a method of printing a barcode computed based on content of a printed page data system on a document the method comprising using a methodology of regular expression applying a regular expression subsystem to text contained in a print stream generating data converting the data to a barcode applying barcode computation to produce a bitmap barcode representing the barcode inserting the bitmap barcode into an Enhanced Meta File EMF print stream defined by the printing system in the Port Monitor or Print Processor subsystem inserting the bitmap barcode into an XML Paper Specification or XPS print stream defined by the printing system in the Port Monitor or Print Processor subsystem and combining the barcode with the print stream to contain the barcode in a specific position in the print stream in the Port Monitor or Print Processor subsystem.

Another embodiment of the present invention provides such a method further comprising controlling a characteristic of the printing process via a user interface.

A further embodiment of the present invention provides such a method wherein the characteristic is at least one characteristic selected from the group of characteristics consisting of the Barcode type size location on the printed document and the source of ASCII or UNICODE text data.

Still another embodiment of the present invention provides such a method wherein the print stream outputs a computer file.

A still further embodiment of the present invention provides such a method wherein the computer file is in a format selected from the group of formats consisting of PDF HTML XML JPEG TIFF PNG and GIF.

One embodiment of the present invention provides a system for the printing of a barcode derived from the content of a printed page data system on a document the system comprising a virtual print driver a generate text subsystem generating a stream of text from a file being printed by the virtual print driver a regular expression subsystem reading the text and providing a set of text data a barcode computing module converting the text data to a barcode bitmap a port monitor subsystem receiving the barcode bitmap and inserting the barcode bitmap in a predefined position in a print data stream.

Another embodiment of the present invention provides such a system further comprising a print driver user interface allowing a user to modify characteristics of the print driver.

A further embodiment of the present invention provides such a system wherein the barcode subsystem comprises a dynamically linked library.

Still another embodiment of the present invention provides such a system wherein the dynamically linked library comprises executable computer code to convert ASCII and or binary text data to a barcode using a barcode standard specification.

A still further embodiment of the present invention provides such a system wherein the virtual print driver further comprises a application programming interface.

The features and advantages described herein are not all inclusive and in particular many additional features and advantages will be apparent to one of ordinary skill in the art in view of the drawings specification and claims. Moreover it should be noted that the language used in the specification has been principally selected for readability and instructional purposes and not to limit the scope of the inventive subject matter.

In one embodiment of the present invention a page print is started. A barcode value is computed based on the data content of the printed page. The barcode is inserted into a print page EMF data stream in predefined position on the page. The page printing is completed with the barcode printed on the page.

As illustrated in one embodiment of the present invention is executed on the Microsoft Windows Operating System with the capability of printing. Such an embodiment provides a printing process transfers formatted data through the Operating System printing subsystem Spooler from the application to a physical printer attached to a commuting device including but not limited by common devises such as Personal computer tablet smart phone or to a Virtual printer driver. In case of physical printer the output is generated on a media such as paper plastic etc. In case of virtual printer the output is generated in a form of a file on a storage device or on a virtual file in memory.

The virtual printer driver is a piece of computer software whose user interface and functionality resembles that of a physical printer but the virtual printer driver prints to a file on a storage device or on a virtual file in memory and may be or may not be connected with a physical printer.

The virtual printer driver can insert the computed Barcode into the print stream during printing from three distinct sources.

In one embodiment of the present invention the virtual printer driver extracts ASCII text or UNICODE text date during printing from the print stream in the Port Monitor and writes the data into a separate file X . The Regular Expression subsystem reads the file X and processes and computes a barcode value based on the printed data content in file X by performing a regular expression computation on the printed data. The regular expression process generates a new set of ASCII text or UNICODE text data that is passed to the barcode computing module through an Application Programming Interface API to compute the barcode. The barcode computing subsystem outputs a barcode represented by a bitmap. The generated barcode is passed to the Virtual printer driver subsystem of Port Monitor . The Port Monitor subsystem inserts the barcode represented by a bitmap into a predefined position into the EMF or XPS print data stream .

The print stream is represented by an EMF or XPS data stream and is static data in the Port Monitor . The port Monitor will convert the EMF or XPS data stream to a predefined file format by passing the EMF or XPS data stream to the File Converter subsystem. The file converter subsystem writes the file to the storage device or to a virtual file in memory.

The Enhanced Metafile format or EMF and the XML Paper Specification or XPS document format consists of structured XML markup that defines the layout of a document and the visual appearance of each page. The EMF and XPS data stream is commonly used in Microsoft Operating Systems by the GDI and the Spooler printing subsystem.

In an alternative embodiment of the present invention the virtual printer reads a predefined file Y that contains ASCII text or UNICODE text data. The virtual printer driver passes the ASCII text or UNICODE text data passed to the barcode computing module through an Application Programming Interface API to compute the barcode. The barcode computing module outputs a barcode represented by a bitmap . The generated barcode is passed to the Virtual printer driver subsystem of Port Monitor . The Port Monitor subsystem inserts the barcode represented by a bitmap into a predefined position into the EMF or XPS print data stream.

In an alternative embodiment of the present invention the virtual printer reads a predefined User Interface data from memory that contains ASCII text or UNICODE text data. The virtual printer driver passes the ASCII text or UNICODE text data to the barcode computing module through an Application Programming Interface API to compute the barcode . The barcode computing module outputs a barcode represented by a bitmap. The generated barcode represented by a bitmap is passed to the virtual printer driver subsystem of Port Monitor . The Port Monitor subsystem inserts the barcode represented by a bitmap into a predefined position into the EMF or XPS print data stream.

The Generate Text stream subsystem reads the EMF data stream. The EMF data stream contains well defined records. The records are parsed by a computational methodology using a C and C programming language to extract ASCII or UNICODE text data from the EMF records. The extracted ASCII or UNICODE text data is written to a memory buffer by the virtual printer driver for the Regular Expression subsystem.

The Generate Text stream subsystem reads the XPS data stream. The XPS data stream contains well defined records. The records are parsed by a computational methodology using a C and C programming language to extract ASCII or UNICODE text data from the EMF records. The extracted ASCII or UNICODE text data is written to a memory buffer by the virtual printer driver for the Regular Expression subsystem .

The Regular Expression subsystem is using a well defined Regular Expression parser. In computing a regular expression is a specific pattern that provides concise and flexible means to match specify and recognize string of text such as particular characters words or patterns of characters. The regular expression subsystem relies in one embodiment on Microsoft Corporation wregex regular expression class library to parse the text data Y generated by the virtual printer driver during printing. Barcode subsystems consist of a Dynamically Linked Library DLL written in C programming language of executable code to convert ASCII or Binary text data based on well defined barcode standard specification See Table 1. to a barcode represented by a bitmap. The barcode DLL uses an API to receive input data and to converts the ASCII text or UNICODE text data to a variety of barcode types defined by barcode standards. The barcode standards utilized are listed in Table 1.

The Virtual printer driver User Interface consists of one or more Windows that defines user interaction with the virtual printer driver software specifically to control certain characteristics of the virtual printer driver printing processes defined by a User. The User can determine the Barcode type size location on the printed document and the source of ASCII or UNICODE text data to be used by the virtual printer driver for printing. The User can enter ASCII or UNICODE text data to be used for barcode computation. The ASCII or UNICODE text data is stored in memory to be inserted into the print stream into a specific position for every printed document.

The Port Monitor Subsystem is the last stage of processing the printed data. The Port Monitor subsystem converts the printed page content represented by EMF or XPS data to a format that can be transferred to a physical printing devise or to a storage device as a file. The format can be including but not limited to a device specific command language or a file format PDF HTML XML JPEG TIFF PNG or GIF.

The foregoing description of the embodiments of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of this disclosure. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

