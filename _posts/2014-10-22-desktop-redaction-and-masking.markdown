---

title: Desktop redaction and masking
abstract: Redacting material in a user interface is provided. A monitoring agent waits for a change in input or output of user content. A change comparator identifies the change for sensitive material. A type comparator identifies the type of sensitive material. A redaction engine redacts the change according to the identified type of sensitive material.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09519794&OS=09519794&RS=09519794
owner: International Business Machines Corporation
number: 09519794
owner_city: Armonk
owner_country: US
publication_date: 20141022
---
This Application is a counterpart of and claims the benefit of priority to United Kingdom Patent Office Application Serial No. 1321768.2 filed on Dec. 10 2013 the contents of which are hereby incorporated by reference.

Increasingly users of information technology IT systems are required to handle sensitive information such as personal identifiable information PII sensitive personal information SPI and information that is otherwise of a secret sensitive or proprietary nature.

Solutions are known in the enterprise environment for redacting masking and otherwise anonymizing or privatizing information either at rest within a database file system or other static structure or in flight upon a communications wire pipe socket or similar. In general these solutions work within a predefined structure associated with one or more enterprise applications databases and or the customer s network and operating system infrastructure. For ad hoc use however on a user s graphical workstation for example on Windows operating system Mac OS X operating system or Linux operating system there is no practical solution for day to day use by enterprise workers. Windows is a trademark of Microsoft Corporation in the US and other countries. Mac is a trademark of Apple Corporation in the US and or other countries. Linux is a registered trademark of Linus Torvalds.

In the current art each individual user must convert the information to specific formats or move the information into a specific application then trigger redaction software. This is because existing solutions require the information to be in a particular document format or to be moved to a specific application for a redaction or masking solution to be able to ingest analyze and redact or mask the information. These limited solutions are restricted to specific client applications part of enterprise grade redaction systems or else they rely on application specific plugins some of which connect to redaction systems and some of which offer a more limited functionality based only on patterns such as regular expressions that can filter contents.

When a user wants to move sensitive information available within one or more standard graphical application environments such as a browser or desktop application it is natural to use standard copy paste and drag and drop operations but in the current art this leaves the sensitive information unprotected and as is.

There is a strong need for a convenient redaction solution which can be part of the day to day activity of an enterprise user. In this use case the originating user has full access to the document so such a solution does not need to protect the data from the originating user.

Rather it would be advantageous to increase compliance rates by making sure that as the user conducts his or her ordinary work moving around information and sending it out as needed the redaction or masking of PII and SPI is a completely natural and straightforward part of her ordinary workflow.

In a first embodiment of the invention there is provided a computer processing system for redacting in a user interface comprising a monitor agent for waiting for a change in input or output of user content a change comparator for identifying the change for sensitive material a type comparator for identifying the type of sensitive material and a redaction engine for redacting the change according to the identified type of sensitive material.

In a second embodiment of the invention there is provided a method for redacting in a user interface comprising waiting for a change in input or output of user content identifying the change for sensitive material identifying the type of sensitive material and redacting the change according to the identified type of sensitive material.

Redacting in this publication encompasses different forms of obfuscating sensitive material including removing blanking masking and encrypting some or all of the sensitive material.

The embodiments automatically and accurately hide sensitive information as part of a user interface graphical or text based including cut copy paste operations drag and drop operations and clipboard operations.

The embodiments make a visual difference to any external process that relies on the operating system clipboard for content. The embodiments operate at a system level of a computer and below an overlying application level that uses a clipboard.

The change in input or output of user content is determined from an operating system clipboard status.

The clipboard content is removed or the clipboard is disabled while the identifying and redacting steps are performed.

Sensitive material types and corresponding redaction methods can be added or removed by a third party. An application programming interface API to change the sensitive material types and corresponding redaction methods is provided to third parties on request.

In a third embodiment of the invention there is provided a computer program product for redacting content in a user interface the computer program product comprising a computer readable storage medium having computer readable program code embodied therewith and the computer readable program code configured to perform all the steps of the methods.

The computer program product comprises a series of computer readable instructions either fixed on a tangible medium such as a computer readable medium for example optical disk magnetic disk solid state drive or transmittable to a computer system using a modem or other interface device over either a tangible medium including but not limited to optical or analogue communications lines or intangibly using wireless techniques including but not limited to microwave infrared or other transmission techniques. The series of computer readable instructions embodies all or part of the functionality previously described.

Those skilled in the art will appreciate that such computer readable instructions can be written in a number of programming languages for use with many computer architectures or operating systems. Further such instructions may be stored using any memory technology present or future including but not limited to semiconductor magnetic or optical or transmitted using any communications technology present or future including but not limited to optical infrared or microwave. It is contemplated that such a computer program product may be distributed as a removable medium with accompanying printed or electronic documentation for example shrink wrapped software pre loaded with a computer system for example on a system ROM or fixed disk or distributed from a server or electronic bulletin board over a network for example the Internet or World Wide Web.

In a fourth embodiment of the invention there is provided a computer program stored on a computer readable medium and loadable into the internal memory of a computer comprising software code portions when the computer program is run on a computer for performing all the steps of the method claims.

In a fifth embodiment of the invention there is provided a data carrier aspect of the preferred embodiment that comprises functional computer data structures to when loaded into a computer system and operated upon thereby enable the computer system to perform all the steps of the method claims. A suitable data carrier may be a solid state memory magnetic drive or optical disk. Channels for the transmission of data may likewise comprise storage media of all descriptions as well as signal carrying media such as wired or wireless signal carrying media.

Referring to the deployment of a preferred embodiment in computer processing system is described. Computer processing system is operational with numerous other general purpose or special purpose computing system environments or configurations. Examples of well known computing processing systems environments and or configurations that may be suitable for use with computer processing system include but are not limited to personal computer systems server computer systems thin clients thick clients hand held or laptop devices multiprocessor systems microprocessor based systems set top boxes programmable consumer electronics network PCs minicomputer systems mainframe computer systems and distributed cloud computing environments that include any of the above systems or devices.

Computer processing system may be described in the general context of computer system executable instructions such as program modules being executed by a computer processor. Generally program modules may include routines programs objects components logic and data structures that perform particular tasks or implement particular abstract data types. Computer processing system may be embodied in distributed cloud computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed cloud computing environment program modules may be located in both local and remote computer system storage media including memory storage devices.

Computer processing system comprises general purpose computer server and one or more input devices and output devices directly attached to computer server . Computer processing system is connected to network . Computer processing system communicates with user using input devices and output devices . Input devices include one or more of a keyboard a scanner a mouse trackball or another pointing device. Output devices include one or more of a display or a printer. Computer processing system communicates with network devices not shown over network . Network can be a local area network LAN a wide area network WAN or the Internet.

Computer server comprises central processing unit CPU network adapter device adapter bus and memory .

CPU loads machine instructions from memory and performs machine operations in response to the instructions. Such machine operations include incrementing or decrementing a value in register not shown transferring a value from memory to a register or vice versa branching to a different location in memory if a condition is true or false also known as a conditional branch instruction and adding or subtracting the values in two different registers and loading the result in another register. A typical CPU can perform many different machine operations. A set of machine instructions is called a machine code program the machine instructions are written in a machine code language which is referred to a low level language. A computer program written in a high level language needs to be compiled to a machine code program before it can be run. Alternatively a machine code program such as a virtual machine or an interpreter can interpret a high level language in terms of machine operations.

Network adapter is connected to bus and network for enabling communication between computer server and network devices.

Device adapter is connected to bus and input devices and output devices for enabling communication between computer server and input devices and output devices .

Bus couples the main system components together including memory to CPU . Bus represents one or more of any of several types of bus structures including a memory bus or memory controller a peripheral bus an accelerated graphics port and a processor or local bus using any of a variety of bus architectures. By way of example and not limitation such architectures include Industry Standard Architecture ISA bus Micro Channel Architecture MCA bus Enhanced ISA EISA bus Video Electronics Standards Association VESA local bus and Peripheral Component Interconnects PCI bus.

Memory includes computer system readable media in the form of volatile memory and non volatile or persistent memory . Examples of volatile memory are random access memory RAM and cache memory . Generally volatile memory is used because it is faster and will hold the data longer. Computer processing system may further include other removable and or non removable volatile and or non volatile computer system storage media. By way of example only persistent memory can be provided for reading from and writing to a non removable non volatile magnetic media not shown and typically a magnetic hard disk or solid state drive . Although not shown further storage media may be provided including an external port for removable non volatile solid state memory and an optical disk drive for reading from or writing to a removable non volatile optical disk such as a compact disk CD digital video disk DVD or Blu ray. In such instances each can be connected to bus by one or more data media interfaces. As will be further depicted and described below memory may include at least one program product having a set for example at least one of program modules that are configured to carry out the functions of embodiments of the invention.

The set of program modules configured to carry out the functions of the preferred embodiment comprise clipboard redaction module and operating system . Operating system includes clipboard . Clipboard is an area of memory persistent or volatile that saves user selected matter from a particular context as a temporary holding place before that selected matter is placed somewhere other than the context from where it came. Further program modules that support the preferred embodiment but are not shown include firmware boot strap program operating system and support applications. Each of the operating system support applications other program modules and program data or some combination thereof may include an implementation of a networking environment.

Computer processing system communicates with at least one network such as a local area network LAN a general wide area network WAN and or a public network like the Internet via network adapter . Network adapter communicates with the other components of computer server via bus . It should be understood that although not shown other hardware and or software components could be used in conjunction with computer processing system . Examples include but are not limited to microcode device drivers redundant processing units external disk drive arrays redundant array of independent disks RAID tape drives and data archival storage systems.

Referring to clipboard module comprises the following components a clipboard monitor agent clip board buffer sensitive material buffer sensitive material type register redaction type methods third party redaction methods change comparator type comparator and clipboard redaction method .

Sensitive material buffer is for storing that part of clipboard contents that has been identified as sensitive.

Third party redaction methods are redacting methods that can be loaded from third party sources and for performing a type of redaction.

Clipboard redaction method is for performing redaction on clipboard changes according to the detailed description below.

Step is for determining whether to continue monitoring the clipboard and branching back to step if so. Else step .

In the preferred embodiment the user copies content with sensitive information from an application and wants to put it to another purpose for example to send it to a colleague by email. In the current art the user would have to create a document in the right format and move it to the relevant software for redaction and masking.

The preferred embodiment intercepts matter as it gets copied into the clipboard. When the user pastes the content to its email application the preferred embodiment redacts the content so that the content is free from sensitive information. To do this a background agent process monitors the contents of the clipboard mouse gestures and keyboard short cuts including screen shots allowing information from any source and in virtually any format to be analyzed and redacted or masked.

The embodiments can support almost all applications in operating systems with graphical user interfaces GUIs . Though each application offers a varying degree of customization and plug in capabilities almost all applications support basic clipboard mouse gesture and keyboard monitoring allowing either automated or user selected anonymization of the content copied or dragged from another application.

Windows UNIX Linux and Mac OS X graphical environments contain public application programming interfaces APIs for monitoring the contents of the clipboard s as well as monitor mouse gestures and keyboard short cuts. UNIX is a registered trademark of The Open Group.

This allows an application such as a background agent or daemon to actively participate in the general workflow initiated by the user. When detecting new or changed information placed in the clipboard a paste operation or a drag and drop operation entering the drop phase the agent can either automatically or based on user gestures perform one or more of the following 

redact or mask sensitive information such as but not limited to names addresses birthdates national identifiers credit card numbers email addresses and network addresses such as host names Internet Protocol addresses and universal recourse locators URLs 

place the redacted or masked data in a secondary clipboard on platforms that support multiple clipboards .

For the redaction masking phase dedicated software can be used. These products analyze various document formats including plaintext rich text forms and graphics and identify sensitive information. Once identified the information is redacted or masked and an anonymized version of the document created.

On various graphical desktop environments data transfer between applications using the clipboard and drag and drop follow similar data format standards such as but not limited to plain text formatted text Rich Text Format RFT Hyper Text Markup Language HTML Tagged Image File Format TIFF Windows bitmaps Windows Metafile WMF Portable Document Format PDF and PostScript PS .

Once data arrives in the clipboard or is about to be dropped the embodiment can determine the format and perform analysis followed by redaction or masking with all data and information in memory yielding acceptable performance for the various user interface gestures.

In addition to the user interface gesture monitoring and hooking described above most operating systems support various additions to the graphical user interface for example right click menus allowing contextual services to be made available to the user. This feature can be leveraged to provide the user with dedicated redaction and masking capabilities of text and graphical information.

The redaction policy of the invention can be configured by rules so the redaction or masking will take place only for specific sources or applications or content types.

In one use case a doctor wants to discuss a patient s case with a colleague but must protect the patient s PII since this colleague is an external consulting physician. Policy specifies that people with this role may not see a patient s PII.

In the current art the doctor would have to copy the information from the medical records system into a redaction application then use the tools in this redaction application to redact the text and then move the text into the email client. The difficulty of such a procedure would lead to many cases of non compliance.

In the preferred embodiment the doctor simply selects the text of the medical case record and drags it to his email agent. The embodiment intercepts the drag and drop determines the role of the recipient in this case an external consulting physician and his permissions in this case that the doctor may not see PII .

The embodiments take into account the source application a medical records system and the target application the email client .

The source application is known to contain sensitive data and the target application is known to transmit data out of the organization and thus policies specify a particularly strict level of redaction.

The embodiments redact the PII and put the privatized text into the target application. The content that appears in the email agent will be redacted so that it contains no PII. It is ready to send.

Text field is a text box that provides output for the user interface. In this example the number 123 45 6789 is displayed. The user may copy the number to a clipboard.

Input field is a text input box that receives input it also provides output . Initially the input field is blank or null but after a user inputs or pastes contents into the box then the input will be displayed. In the example a redacted string 123 45 XXXX is displayed after a paste operation by a user.

Also shown in are representations of a clipboard and and clipboard buffer and after the example has been performed. This is not part of a user interface but represent internal parts of the embodiment.

At step a user initiates copying of the text in text field . The text 123 45 6789 is transferred to the clipboard .

At step the clipboard contents 123 45 6789 are transferred to clipboard buffer when a change is detected in the clipboard and the embodiment is initiated.

At step the embodiment performs redaction on the content of clipboard buffer . The type of change equates to a redaction method that crosses out the last four characters and clipboard buffer now contains the string 123 45 XXXX .

At step a user paste operation is allowed and the redacted string is pasted into input field as 123 45 XXXX .

Further embodiments of the invention are now described. It will be clear to one of ordinary skill in the art that all or part of the logical process steps of the preferred embodiment may be alternatively embodied in a logic apparatus or a plurality of logic apparatuses comprising logic elements arranged to perform the logical process steps of the method and that such logic elements may comprise hardware components firmware components or a combination thereof.

It will be equally clear to one of skill in the art that all or part of the logic components of the preferred embodiment may be alternatively embodied in a logic apparatus comprising logic elements to perform the steps of the method and that such logic elements may comprise components such as logic gates in for example a programmable logic array or application specific integrated circuit. Such a logic arrangement may further be embodied in enabling elements for temporarily or permanently establishing logic structures in such an array or circuit using for example a virtual hardware descriptor language which may be stored and transmitted using fixed or transmittable carrier media.

In a further alternative embodiment the present invention may be realized in the form of a computer implemented method of deploying a service comprising steps of deploying computer program code operable to when deployed into a computer infrastructure and executed thereon cause the computer system to perform all the steps of the method.

It will be appreciated that the method and components of the preferred embodiment may alternatively be embodied fully or partially in a parallel computing system comprising two or more processors for executing parallel software.

It will be clear to one skilled in the art that many improvements and modifications can be made to the foregoing exemplary embodiments without departing from the scope of the present invention.

