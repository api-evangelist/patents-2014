---

title: Information processing apparatus, information processing method and computer-readable storage medium
abstract: It is determined whether a data source can handle an event that an application that operates on an OS (Operating System) receives via a predetermined API. If it is determined that the data source cannot handle the event, the event necessary for the operation of the data source is acquired from the OS.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09552238&OS=09552238&RS=09552238
owner: CANON KABUSHIKI KAISHA
number: 09552238
owner_city: Tokyo
owner_country: JP
publication_date: 20141114
---
The present invention relates to an information processing technique using an application that operates on an OS Operating System and a data source that is a driver configured to control a peripheral device.

There is conventionally known TWAIN that is an interface standard API used to control a data source such as a scanner driver from an application see Japanese Patent Laid Open No. 10 275223 . In this case the application needs to do event handling via the TWAIN.

Recently however in the execution environment of a programming language or framework that does not make a user aware of event handling and is becoming quite common it is difficult to implement a program corresponding to the existing TWAIN and the programming knowledge of the conventional C C language or conventional execution environment is necessary. In particular it is difficult to do implementation according to a restriction that event handling needs to be performed in the same thread. This problem may also arise in an API other than TWAIN.

The present invention provides an information processing technique capable of easily normally operating a data source from an application in accordance with a predetermined API.

In order to achieve the above object an information processing apparatus according to the present invention has the following arrangement.

An information processing apparatus for causing an application that operates on an OS Operating System and a data source that is a driver configured to control a peripheral device to communicate via a predetermined API Application Programming Interface comprising a determination unit configured to determine whether the data source can handle an event that the application receives via the API and an acquisition unit configured to when the determination unit determines that the data source cannot handle the event acquire the event necessary for an operation of the data source from the OS.

According to the present invention it is possible to easily normally operate a data source from an application in accordance with a predetermined API.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Hereinafter embodiments of the present invention will be described in detail with reference to the accompanying drawings. It should be noted that the following embodiments are not intended to limit the scope of the appended claims and that not all the combinations of features described in the embodiments are necessarily essential to the solving means of the present invention.

An application accesses a data source manager to be referred to as a DSM hereinafter defined by a TWAIN standard that is one of APIs Application Programming Interfaces . The DSM is preinstalled in an OS Operating System corresponding to the TWAIN standard for example Windows that is an OS. A plurality of data sources and that are scanner data sources scanner drivers can be connected to the DSM . The data sources and control corresponding scanner devices and respectively. The scanner device reads an image on an original document and transfers thus obtained image data to the data source under the control of the data source . The data source supplies the received image data to the application . The scanner device is controlled by the data source and performs similar processing. The application selects a scanner device data source and acquires read image data obtained by the scanner device.

Each of the application the DSM and the data sources and is software program that operates on the OS.

The DSM accesses the data sources and and transmits a command according to a TWAIN protocol transmitted from the application to a selected data source for example the data source when the data source is selected. Because of this configuration even in an environment where a plurality of data sources are installed the application can selectively access the plurality of data sources by accessing the DSM . The DSM has a function of listing UIs User Interfaces to be used by the application to select the data sources and or listing the installed data sources and .

Note that the application the DSM and the data sources and are installed in an information processing apparatus such as a general purpose computer. The information processing apparatus includes standard constituent elements for example CPU RAM ROM hard disk external storage device network interface display keyboard mouse and the like included in a general purpose computer. The CPU of the information processing apparatus reads out programs stored in a memory RAM or ROM and executes them thereby implementing the application the DSM and the data sources and . These programs are stored in for example a storage device such as a hard disk. The information processing apparatus is connected to the scanner devices and via an external interface such as a USB interface and communicates with them.

Devices connected to the information processing apparatus are not limited to the scanner devices and and peripheral devices multi function peripheral digital camera video camera and the like capable of operating based on the TWAIN standard can be connected. On each device connected to the information processing apparatus various kinds of operations such as function execution and setting for the device can be implemented via a UI displayed on the display unit display of the information processing apparatus.

In this embodiment the TWAIN standard has been exemplified as the interface standard used to control the data source from the application. However the present invention is not limited to this. Any other API standard is usable as long as it is a predetermined interface API that makes the same behavior as the TWAIN standard.

The operation of the application when displaying the UI of the data source and reading an image will be described next with reference to the flowchart shown in .

Note that the processing of is implemented by causing the CPU to read out the application stored in the memory and execute it.

In step S the application loads the DSM . In step S the application transmits a command DG CONTROL DAT PARENT MSG OPENDSM according to the TWAIN protocol to the DSM to make it open. In step S the application selects the data source of the scanner device to be caused to read an image and notifies the DSM of it. As the data source the data source or shown in is usable. For example assume that the data source is selected. A description will be made below using an example in which the data source is selected.

In step S the application transmits a command DG CONTROL DAT IDENTITY MSG OPENDS according to the TWAIN protocol to the DSM to connect the data source . In step S the application transmits to the DSM a capability to acquire device information from the data source or set information in the data source . In step S the application transmits a command DG CONTROL DAT USERINTERFACE MSG ENABLEDS according to the TWAIN protocol to the DSM to enable the data source display the UI of the data source scanner driver .

In step S the application acquires an event using an OS function API of the OS GetMessage PeekMessage . The application adds the acquired event to a command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol and transmits it to the DSM .

In step S the application checks the return value of the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol. Event processing processing according to the contents of the event of the acquired event is performed on the side of the application . Accordingly the process advances to termination processing or scan image reading processing of the data source . Here the application determines whether event processing has ended. If the event processing has not ended NO in step S the process returns to step S. If the event processing has ended YES in step S the process advances to step S. In step S the application executes processing such as termination processing or scan processing in accordance with the state of the event.

Since the above described procedure is a general procedure defined by TWAIN any special processing need not be performed on the side of the application .

As the next operation each command according to the TWAIN protocol which is transmitted from the application to the DSM needs to be transmitted from the DSM to the data source . However each command transmitted to the DSM from step S is directly transmitted from the DSM to the data source selected in step S and a description of exchange between the DSM and the data source will be omitted.

The operation on the side of the data source will be described with reference to the flowchart shown in .

Note that the processing of starts when the application instructs image reading by the scanner device.

Here a case where the data source executes the processing as a data source will be exemplified. This also applies to the data source .

In step S the data source responds to a data source list request from the DSM . With this response the side of the application is notified of the presence of the data source. In step S the data source responds to the command DG CONTROL DAT IDENTITY MSG OPENDS according to the TWAIN protocol. Initialization processing of software or initialization processing of the device is performed here.

In step S the data source responds to the data source setting acquisition setting transmitted from the DSM . The current set value or a set value transmitted from the application for example the color mode resolution and the like for reading are set. In step S the data source responds to the command DG CONTROL DAT USERINTERFACE MSG ENABLEDS according to the TWAIN protocol. Here the data source displays the UI of its own using the Window function or drawing command of the OS.

In step S the data source receives the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol. In step S the data source acquires an event from the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol.

In step S the data source determines whether the acquired event needs to be reacquired. If the event is acquired from a correct message queue in step S event reacquisition is unnecessary. If the event is acquired from an incorrect unintended message queue event reacquisition is necessary. The TWAIN does not take a multithread into consideration and cannot handle an event from the message queue of a different thread.

As the determination method here for example a thread ID obtained from the event using a GetWindowThreadProcessId command that is an OS API is compared with the thread ID of the data source obtained using a GetCurrentThreadProcessId command that is an OS API as well. The thread IDs are represented by integer values and can therefore be compared. If the IDs are the same as the result of comparison it is determined that event reacquisition is unnecessary. If the IDs are different it is determined that event reacquisition is necessary.

As another determination method a window handle representing a window in which the event has occurred is extracted from the event. If the event has occurred from a really existing window using an IsWindow command that is an OS API it is determined that event reacquisition is unnecessary. If the event has not occurred from a really existing window it is determined that event reacquisition is necessary.

As still another determination method a window handle is acquired from the event. If the window handle has a NULL value representing an invalid window it is determined that event reacquisition is necessary because the event impedes the operation of the data source.

Upon determining that the event needs to be reacquired YES in step S the process advances to step S. If no event need be reacquired NO in step S the process advances to step S.

In step S the data source discards event information added to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol and acquires the event using the OS function. In step S the data source processes the event. The window handle of the event that has occurred is added to the event information. For this reason the window including a button and the like managed by the data source can be determined and the data source performs necessary event processing.

In step S the data source transmits the presence absence of execution of event processing or the result of a change in the data source operation caused by the result of event processing to the DSM as a response to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol.

If the application has acquired the event from a correct message queue in step S it is determined by the determination on the side of the data source in step S that event reacquisition is unnecessary and the process advances to step S without performing step S. Since this procedure complies with the processing procedure of the data source defined by the TWAIN the data source correctly operates in combination with the application that operates according to the TWAIN standard.

On the other hand if the application has acquired the event from an incorrect message queue in step S it is determined by the determination on the side of the data source in step S that event reacquisition is necessary. In step S an event necessary for the operation of the data source is acquired using the OS function. For this reason the process of step S on the side of the data source is normally performed and the data source correctly operates.

As described above according to the first embodiment when the event transmitted from the application impedes the operation of the data source the event necessary for the operation is acquired from the OS outside the application and the data source is operated. If the event transmitted from the application is normal processing is executed according to the normal TWAIN.

More specifically even when the application side acquires the event to be added to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol by an incorrect method it is possible to reacquire the event on the data source side and operate the data source.

As described above even when the application transmits an event that is not assumed in the TWAIN to the data source for example the data source can reacquire the event necessary for the operation from the OS and normally operate. In addition by determining and processing whether the event impedes the operation the data source can normally operate even in combination with an application that operates as a general multithread according to the TWAIN standard.

In the first embodiment correction of the TWAIN protocol DG CONTROL DAT EVENT MSG PROCESSEVENT event reacquisition is performed on the side of the data source . In the second embodiment however an arrangement that causes a DSM located between an application and a data source to perform correction event reacquisition will be described.

Processing on the side of the application is the same as the flowchart of according to the first embodiment and a description thereof will be omitted.

The operation on the side of the data source according to the second embodiment will be described next with reference to the flowchart shown in .

Steps S to S of correspond to steps S to S of and a description thereof will be omitted. In addition steps S to S correspond to steps S to S of and a description thereof will be omitted. That is the processes of steps S and S in are omitted in . In the second embodiment since the data source can acquire a normal event from the DSM as will be described later the processes of steps S and S in are unnecessary. Additionally since this procedure is a general procedure defined by TWAIN any special processing need not be performed on the side of the data source .

The operation on the side of the DSM according to the second embodiment will be described with reference to the flowchart shown in .

In step S the DSM receives a command according to the TWAIN protocol which is transmitted from the application . In step S the DSM determines whether the command according to the TWAIN protocol is a specific command DG CONTROL DAT EVENT MSG PROCESSEVENT . If the command is not the specific command NO in step S the process advances to step S. If the command is the specific command YES in step S the process advances to step S.

In step S the DSM acquires the event added to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol. In step S the DSM determines whether the acquired event needs to be reacquired. As the determination method here the determination method in step S of can be used.

Upon determining that the event needs to be reacquired YES in step S the process advances to step S. If no event need be reacquired NO in step S the process advances to step S.

In step S the DSM discards event information added to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol reacquires an event using the OS function and adds the reacquired event to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol. In step S the DSM transmits the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol to the data source .

Commands other than the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol are transmitted to the data source in accordance with the TWAIN standard. Even the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol is transmitted to the data source in accordance with the TWAIN standard if the event added to it need not be reacquired. For this reason the processing of correctly operates in combination with the application according to the TWAIN standard. On the other hand if the event added to the command DG CONTROL DAT EVENT MSG PROCESSEVENT according to the TWAIN protocol needs to be reacquired the event that operates the data source is acquired in step S and transmitted to the data source .

As described above according to the second embodiment even when the application side acquires the event to be added to the TWAIN protocol DG CONTROL DAT EVENT MSG PROCESSEVENT by a method that is not assumed in the TWAIN the DSM side can reacquire the event and operate the data source. For example the data source can normally operate even in combination with an application that operates as a multithread.

Note that the above embodiments have been described by exemplifying TWAIN as the API of the application and the data source device driver . However the embodiments may be applied to any API other than the TWAIN.

Embodiment s of the present invention can also be realized by a computer of a system or apparatus that reads out and executes computer executable instructions e.g. one or more programs recorded on a storage medium which may also be referred to more fully as a non transitory computer readable storage medium to perform the functions of one or more of the above described embodiment s and or that includes one or more circuits e.g. application specific integrated circuit ASIC for performing the functions of one or more of the above described embodiment s and by a method performed by the computer of the system or apparatus by for example reading out and executing the computer executable instructions from the storage medium to perform the functions of one or more of the above described embodiment s and or controlling the one or more circuits to perform the functions of one or more of the above described embodiment s . The computer may comprise one or more processors e.g. central processing unit CPU micro processing unit MPU and may include a network of separate computers or separate processors to read out and execute the computer executable instructions. The computer executable instructions may be provided to the computer for example from a network or the storage medium. The storage medium may include for example one or more of a hard disk a random access memory RAM a read only memory ROM a storage of distributed computing systems an optical disk such as a compact disc CD digital versatile disc DVD or Blu ray Disc BD a flash memory device a memory card and the like.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2013 261830 filed Dec. 18 2013 which is hereby incorporated by reference herein in its entirety.

