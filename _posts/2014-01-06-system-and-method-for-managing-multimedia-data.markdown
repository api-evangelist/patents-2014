---

title: System and method for managing multimedia data
abstract: A networking system and method is disclosed in this specification. The system hosts a virtual environment that is populated with avatars. Each avatar displays a video stream of a corresponding user and defines a virtual view point that represents the user's perspective of the virtual environment. The system implements a method that comprises monitoring movement of the avatars within the virtual environment and capturing a media stream from the virtual view point of each avatar as a corresponding user navigates the virtual environment. The captured video stream is relayed to a user's local client and displayed to the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09420229&OS=09420229&RS=09420229
owner: Smart Internet Technology CRC Pty Ltd
number: 09420229
owner_city: Eveleigh
owner_country: AU
publication_date: 20140106
---
The present invention relates to a system and method for managing multimedia data in a virtual environment.

Traditional video conferencing systems are limited in the number of participants that can participate. Most limitations are attributable to the large amount of bandwidth required in order to transmit multimedia data to a large number of participants simultaneously.

The major bottleneck for such a system is the required network and server transmission capacity to support the service which in the case of a traditional video conferencing system grows in proportion to the square of the number of participants.

In another embodiment the method comprises determining a line of sight for each avatar and generating the media stream displayed to the corresponding user based on the line of sights.

In another embodiment the method comprises constructing the media stream for each avatar from a plurality of data culling techniques that are used to define an avatars line of sight.

In another embodiment the method comprises constructing an avatars line of sight by applying any one or more of 

In another embodiment the method comprises determining a virtual distance between avatars within the virtual environment and moderating the reproduction of an avatar s video stream in the media stream associated with another avatar based on the proximity of the respective avatars within the virtual environment.

In another embodiment the method comprises reducing the bit rate and or frame rate of the reproduced video stream for distant avatars.

In another embodiment the method comprises generating a virtual display screen that displays images sourced from a client associated with an avatar within the virtual environment the virtual display screen being visible within the virtual environment.

In another embodiment the server determines a line of sight for each avatar within the virtual environment the line of sight defining the media stream that is relayed to the corresponding user.

In another embodiment the server directs the transmission of the video stream associated with each avatar based on the line of sight determined for the corresponding avatar the video stream being transmitted directly between clients associated with the avatars.

In another embodiment the server receives a video stream from a client associated with each avatar and relays the media stream for each avatar to a corresponding user based on the line of sight of the avatar.

In another embodiment the server implements a plurality of data culling techniques to define an avatars line of sight.

In another embodiment the server determines a virtual distance between avatars within the virtual environment and moderates the reproduction of an avatar s video stream in the media stream associated with another avatar based on the proximity of the respective avatars within the virtual environment.

In another embodiment the server reduces the bit rate and or frame rate of the reproduced video stream for distant avatars.

In another embodiment the server generates a virtual display screen that displays images sourced from a client associated with an avatar within the virtual environment the virtual display screen being visible within the virtual environment.

According to another aspect of the invention there is provided a method of managing multimedia data in a virtual environment comprising the steps of 

In another embodiment the step of satisfying the pre determined criterion includes the further step of applying at least one data culling technique to the one or more virtual clients.

In another embodiment the view field culling technique includes determining whether the one or more clients reside within a view field within the virtual environment.

In a further embodiment the method comprises the further step of defining the view field relative to the location of the one or more clients.

In a yet another embodiment the view field is defined as a geometric shape the edges of the shape defining the limits of the view field of the one or more users.

In an additional embodiment the view field culling technique includes the further step of excluding all client that are not located within the view field.

In an additional embodiment the method comprises the step of defining a maximum range of visibility within the view field.

In another embodiment the visibility culling technique includes the further step of excluding all clients that are located beyond the maximum range of visibility.

In a further embodiment the back face culling technique step is performed after the application of the view field culling technique and the visibility culling technique.

In one more embodiment the occlusion culling technique step is performed after the visibility culling technique step and after back face culling technique step.

In another embodiment the occlusion culling technique the further steps of determining the distance of each one of the virtual clients in the view field relative to the one or more clients defining a visible angle range for each one of the virtual clients determining whether each one of the clients is occluded by another of the at least one of the clients and excluding each one of the clients that are occluded.

In a further embodiment the method comprises the additional step of determining the virtual motion of the one or more clients.

A further embodiment of the method comprises the additional step of assigning a motion vector to each one of the one or more clients and each one of the one or more clients.

In another embodiment the motion vector includes a translational velocity vector and an angular velocity vector.

In a further embodiment the motion vector of the one or more clients is utilized to adjust the view field to determine a conservative view field.

In another embodiment the data culling techniques are performed based on the conservative view field.

According to another aspect of the invention there is provided a method of managing multimedia data in a virtual environment the method of comprising the steps of 

In another embodiment the step of satisfying the pre determined criterion includes the further step of applying at least one data culling technique to the one or more virtual clients.

In a further embodiment the view field culling technique includes determining whether the one or more clients reside within a view field within the virtual environment.

In another embodiment the method comprising the further step of defining the view field relative to the location of the one or more clients.

In another embodiment the view field is defined as a geometric shape the edges of the shape defining the limits of the view field of the one or more clients.

In a further embodiment the view field culling technique includes the further step of excluding all clients that are not within the view field.

In a different embodiment the method comprising the step of defining a maximum range of visibility within the view field.

In yet another embodiment the visibility culling technique includes the further step of excluding all clients that are located beyond the maximum range of visibility.

In an additional embodiment the back face culling technique step is performed after the application of the visibility culling technique and the view field culling technique.

In yet another embodiment the occlusion culling technique step is performed after the view field culling technique the visibility culling technique step and after back face culling technique step.

In a further embodiment the occlusion culling technique the further steps of determining the distance of each one of the virtual clients in the view field relative to the one or more clients defining a visible angle range for each one of the virtual clients determining whether each one of the clients is occluded by another of the at least one of the clients and excluding each one of the clients that are occluded.

In another embodiment the method comprising the additional step of determining the virtual motion of the one or more clients.

In a further embodiment the method comprising the additional step of assigning a motion vector to each one of the one or more clients and each one of the one or more clients.

In an additional embodiment the motion vector includes a translational velocity vector and an angular velocity vector.

In yet another embodiment the motion vector of the one or more clients is utilized to adjust the view field to determine a conservative view field.

In another embodiment the data culling techniques are performed based on the conservative view field.

According to a further aspect the invention there is provided a system for managing multimedia data in a virtual environment comprising 

The present invention relates to a system and method for managing multimedia data in particular for one or more entities in a virtual environment comprising an interface for receiving instructions from a user and allowing a user to interact with the system and manage multimedia data. The system includes at least one processor for generating a virtual environment and managing multimedia data. In the following example embodiments the interface and processor are implemented by a computer having an appropriate user interface. The computer may be implemented by any computing architecture including a stand alone PC a client server architecture a dumb terminal mainframe architecture or any other appropriate architecture. The computing device is appropriately programmed to implement an embodiment of the invention.

Referring to there is a shown a schematic diagram of a general computing device . The computing device comprises suitable components necessary to receive store and execute appropriate computer instructions. The components may include a processing unit read only memory ROM random access memory RAM and input output devices such as disk drives input devices such as an Ethernet port a USB port etc. Display such as a liquid crystal display a light emitting display or any other suitable display and communications links . The server includes instructions that may be included in ROM RAM or disk drives and may be executed by the processing unit . There may be provided a plurality of communication links which may variously connect to one or more computing devices such as a server personal computers terminals wireless or handheld computing devices. At least one of a plurality of communications link may be connected to an external computing network through a telephone line or other type of communications link.

The service may include storage devices such as a disk drive which may encompass solid state drives hard disk drives optical drives or magnetic tape drives. The server may use a single disk drive or multiple disk drives. The server may also have a suitable operating system which resides on the disk drive or in the ROM of the server .

The device may include a database residing on a disk or other storage device which is arranged to store data. The database is in communication with an interface which is implemented by computer software residing on the computing device . The interface provides a means by which to communicate with a human user. In the specification reference to servers processors clients user devices or computing devices are implemented using a computing device described earlier.

The clients are adapted to communicate with the central server . The clients are arranged to communicate with each other in the virtual environment via the central server . The central server creates the virtual environment and manages or controls the data flow to and from the virtual environment . The instructions regarding the contents of the virtual environment may be stored on the database and can be accessed by the central server. In another form the system may include a further media server that controls the media data sent to and from the virtual environment. The media server is adapted to be in communication with the central server and may in some forms be controlled by the central server. The media server may be arranged to communicate with the database also.

The central server creates and manages a virtual environment . The virtual environment in one form is a 3D three dimensional environment adapted for video conferencing. shows an image of the virtual environment with two avatars that each represent a corresponding client within the virtual environment. The figure shows a 2D two dimensional image of the virtual environment. There are a plurality of users and the users can interact with the virtual environment through the clients . The clients may include a user interface such as a screen or display that allows a user to view the virtual environment and view and interact with other avatars in the virtual environment.

The database stores instructions regarding the components of the virtual environment. The database may be arranged to store a plurality of different types of virtual environments. The database may include instructions or information regarding graphics rendering bounds limits and objects that are common to all virtual environments. The database can be accessed by the server that uses information relating to a virtual environment to create the virtual environment . Once the virtual environment is created it can be populated with participants. The central server receives information from the clients that want to be positioned in the virtual environment as participants. The central server may process information from the database and the clients in order to create a virtual environment and populate the virtual environment with participants.

In another form the media server receives instructions regarding creation of a virtual environment from the central server . The media server may access the database and use the stored information to create a virtual environment. The media server may also receive instructions relating to the clients from the central server . The media server can process this information and populate the virtual environment with participants. In an alternate form the clients may communicate with the media server directly the media server processing the information from the clients and populating the virtual environment with participants. In this alternate form the media server may communicate directly with the database to gather necessary information in order to create a virtual environment.

A networking system is illustrated in the Figures. The system illustrates a networking method that allows users to correspond with live video and audio streams.

The networking method comprises generating a virtual environment and populating the virtual environment with a plurality of avatars . The avatars each represent a corresponding user. Each avatar displays a video stream of the corresponding user that is displayed in the virtual environment. The avatars also define a virtual view point from which the virtual environment is reproduce for the corresponding user.

Each user controls the movement of the corresponding avatar within the virtual environment. The movement of the avatars within the virtual environment is monitored by the central server . The server also captures a media stream from the virtual view point of each avatar as users navigate the virtual environment. The captured media stream is displayed to the user on a corresponding local client such as the user s personal computer .

The server determines a line of sight for each avatar within the virtual environment. The media stream displayed to the corresponding user is generated based on the line of sight for the corresponding avatar. The server may construct the media stream for each avatar from a plurality of data culling techniques that are disclosed later in this specification. The data culling techniques are used to define the avatars line of sight.

The server ideally determines a virtual distance between avatars within the virtual environment. The virtual distance may be used to moderate the quality of the video stream relayed to a user s local client. Ideally quality of an avatar s video stream as reproduced in the media stream of another avatar is based on the proximity of the respective avatars within the virtual environment. The server may reduce the bit rate and or frame rate of the reproduced video stream for distant avatars to moderate the video stream quality.

The server may generate a virtual display screen that displays images sourced from a client associated with an avatar within the virtual environment in the virtual environment. The virtual display screen being visible within the virtual environment.

The illustrated networking system comprises a server that hosts a virtual environment and a plurality of user avatars stored in server memory. The server is connected to a data network. The avatars are accessible through the data network. Each user avatar displays a video stream of a corresponding user. The avatars also define a virtual view point that dictates the perspective of the virtual environment that is relayed to a corresponding user. The server documents movement of the avatars within the virtual environment and defines a media stream that is captured from the virtual view point of each avatar. The media stream is relayed to a corresponding user.

The server determines a line of sight for each avatar within the virtual environment. The line of sight defines the media stream that is relayed to the corresponding user. The server may direct the transmission of the video stream associated with each avatar based on the corresponding line of sight directly between clients associated with the avatars. Alternatively the server may receive the video stream associated with each avatar and relay the media stream for each avatar to a corresponding user s local client. This increases the bandwidth loading on the server as the server receives a full video stream for each user client but reduces the bandwidth loading on the individual clients as the local clients only receive the video stream for other avatars that are within their line of sight .

The virtual environment may include a plurality of avatars etc. as seen in . Each one of the avatars exist in the environment in the form of a simplified visual representation of the user. The avatar may take any suitable form and may be customisable to allow a user to create their own avatar. In one form as shown in the avatar includes a display . The display in one form is a live video feed. The video feed can be recorded and streamed live from a video recording device such as a camera that may be associated with the client . The video stream is transmitted to the central server and then projected into the virtual environment as part of the avatar. In another form the video stream may be sent by the server to the media server which then transmits the information to the avatar in the virtual environment .

The clients may be able to communicate with the virtual environment in order to control the avatar associated with the client. The user can control the motion of the avatar in the virtual environment. Avatars can move freely within the virtual environment and an avatar can interact with other avatars. The illustrated avatars display a corresponding user s multimedia data feed. User s can therefore communicate with other users in the virtual environment through their respective avatars. A user can speak directly to another user via the multimedia data feed of the other user s avatar.

The avatars also include a virtual camera that receives multimedia data from other avatars. The multimedia data streams are transmitted either to the media server or the central server and then transmitted back to the end user associated with the avatar . The camera allows the end user to view the virtual environment and the avatars of other users and receive communication from the other users in the virtual environment through their respective avatars. The multimedia data stream can involve video and audio data or simply video data or simply audio data.

In the specification the word avatar relates to a virtual representation of a user in the virtual environment. The avatar is an electronic representation of a user that can communicate with the network and system components described earlier. Where ever there is reference to an avatar performing an action it will be understood it is the client associated with that avatar that is performing that action in the physical world.

The pre determined criterion specified in both methods may include at least one data culling technique applied to one or more of the avatars in the virtual environment. Possible data culling techniques include 

The view field culling technique includes defining a view field for each avatar. Each avatar includes a view field which is defined in a coded set of rules. The rules regarding the size of the view field can be modified and altered by an authorised person such as an administrator. These rules may be stored on the database or the central server or the media server .

The view field may be any other suitable shape that extends outwardly from the avatars. For example the view field may be a diverging shape originating at the avatar . The maximum visibility range is defined by the edge of the view field.

In one form the central server determines the location information of each one of the avatars in the virtual environment. The central server may also determine the orientation of the avatars relative to the other avatars. The central server can transmit this information to the clients such that the clients are aware of the location and orientation of the other avatars in the virtual environment. In an alternate form the individual clients may determine the orientation of other avatars within the virtual environment. The client may also determine the position of the other avatars within the virtual environment.

The view field culling technique includes the step of excluding or culling avatars that are outside the view field of the local avatar. As seen in avatars and are outside the view field and hence the multimedia data from these avatars are not delivered to the client associated with the local avatar . This results in a reduction of total bandwidth usage due to a reduced amount of multimedia data being transmitted across the network .

The visibility culling technique includes the step of excluding all the avatars that are located beyond the maximum range of visibility. If an avatar is outside the maximum visibility range of the local avatar then the multimedia data for the avatar outside the visibility range is not delivered to the local avatar reduces the total bandwidth requirement.

The back culling technique involves the step of excluding avatars that have their back facing the local avatar . The local avatar uses orientation information to determine which avatars are facing away i.e. the orientation of the other avatar relative to the local avatar . If another avatar for example avatar is facing away from the local avatar then the video data of the back facing avatar is not required by the client associated with the local avatar . As seen from avatar is facing away from the avatar hence the multimedia data of avatar is not supplied to avatar thereby reducing the bandwidth requirement across the network because less video data is being transmitted over the network.

The occlusion culling technique involves the step of determining which avatars are covered by other avatars from the perspective of a local avatar. If an avatar is fully occluded or partially occluded by an object within the virtual environment or another avatar then video data for the occluded avatar is not delivered to the client associated with the local avatar. As can be seen from the angle of the occlusion lines and lines that emanate from the view point and extend to the extremities of the occluding avatar to define the shadow created by the occluding avatar in the local avatar s view field are calculated and for each avatar. The angle from to is termed the avatar s blocking angle range. This angle defines the part of the local avatars view that is blocked due to another avatar being present in the view field. From the nearest avatar to the furthest avatar an overlap test is applied to check if the blocking ranges of avatars result in any overlap within the total visible angle range of the local avatar. Each avatar s blocking angle range is first compared to the blocked area. If there is any overlap then further testing needs to be done to determine avatar priority based on proximity to is the local avatar otherwise it is assumed that the avatar is visible. Finally the angle range is added to the blocked area.

Applying these data culling techniques results in a reduction of the amount of data sent to each client and hence reduces the bandwidth requirements of the network. The data culling techniques only allows multimedia data of avatars that are visible to a local avatar to be sent to the corresponding client. The implementation of this data culling techniques simulates real life interaction in the virtual environment meaning the local avatar does not see other avatars that are occluded either by other avatars or objects within the virtual environment facing away or outside a defined field on view such as behind the local avatar .

Each client may maintain a list of visible avatars and requests multimedia data relating to the visible avatars. The visible avatars are determined by applying one or more of the data culling techniques described earlier. In one form the client requests multimedia data for visible avatars from the central server . The central server gathers multimedia data from all the avatars and only sends multimedia data for the identified visible avatars. In another form the client for a local avatar requests multimedia data from other clients that relate to visible avatars.

Due to the distributed nature of the system delay is is inevitable and must be considered. There is a network delay associated with transmitting multimedia data once a client requests data for a list of visible avatars. This means that the list should be valid until the client associated with the local avatar receives the requested video streams. Otherwise there may be a discrepancy between the desired view of the end user and the actual information received on the client.

As a solution a conservative visible set is introduced which not only contains the visible avatars at the current point in time but also the avatars that may become visible during the interval between sending a request and receiving the corresponding response. To construct this list a motion vector is derived for each avatar which indicates the current speed and direction of the avatar. Based on the motion vector the next position of a local avatar is predicted. At least one or more data culling techniques described earlier may then be applied based on the predicted position of the local avatar as well as the current position.

For instance in the local avatar moves in the direction defined by the motion vector . The view field of the avatar also moves due to the motion of the avatar in the virtual environment. All the avatars within the virtual environment are assigned a motion vector for example etc. The motion vector may include a translational velocity component or a rotational velocity component or both translational and rotational velocity components. As seen from avatar is not visible but the predicted position of avatar is in the view frustum of the predicted position of the local avatar . Moreover avatar and will exit out of the local avatar s view field when the local avatar reaches the predicted position. Hence the list of visible avatars should include avatar but not avatar or avatar

In order to compensate for the movement of the local avatar the movement of the other avatars and network delay a conservative view field is determined and utilised to perform the data culling techniques. The motion vector of the local avatar includes a translational and rotational component. shows the conservative view field. The visible angle range is denoted and the maximum visible distance is denoted b.

A conservative view field CVF is not only the view field at the current moment in time but extended by all possible view fields during the network response interval. A CVF is constructed based on the maximum translation velocity v maximum angular velocity and network delay t using the formula 2 1 2 

The first formula formula 1 is multiplied by two because an avatar can either turn right or left and by this multiplication all possible future view fields are covered.

The predicted motions and locations of other avatars based on the motion vectors of the respective avatars are added to the virtual environment. By applying the data culling techniques described earlier but using the larger view field represented by the conservative view field a conservative visible set is constructed. As can be seen from the original view field was defined by and . The new conservative view field is defined by and The extended view field is increased to compensate for the velocity shown by vector of the avatar .

In another embodiment the occlusion culling test can be modified for 3D purposes. The proposed occlusion culling technique as described above is based on a technique called ray casting. However when utilising the ray casting technique the viewpoint is not the source of rays but the destination of them. An alternate form of ray casting for an alternate form of occlusion culling is shown in . In the alternate form of the occlusion culling technique rays and are emitted toward the view point camera from each of the four corners of each avatar s video display . If all rays are intersected by objects including other avatars or any static or dynamic opaque object forming part of the virtual environment the avatar is occluded. Otherwise the avatar is visible even if only one ray is received by the view point .

When an avatar is rotating away from the view point the rays are not received and the avatar is not visible. Hence this method covers occlusion culling and back face culling simultaneously and has the advantage that the system only needs to perform the occlusion culling technique instead of two data culling techniques such as back face culling and the occlusion culling described earlier with respect to . The reduced processing steps are advantageous since they allow for faster processing times.

An alternate form of 3D occlusion culling is shown in . In the illustrated form of occlusion culling the source of rays from an avatar may form any arbitrary shape based on the content of the target avatars video stream. Each vertex can be given a weight which shows the priority of the ray. For instance in the sources of rays make a triangular shape for a talking head video. Vertex A has the highest priority weight 2 and the two other vertices B C both have a lower priority weight 1 .

Rays are emitted toward the view point in order of their priorities for instance in this particular example the first a ray is emitted and processed from vertex A. If the ray is not intersected by an object in the virtual environment the avatar is considered fully visible and no other calculation is performed. This method minimises the processing cost.

To avoid incorrect detections of fully visible avatars based on the characteristics of the virtual environment and the shapes of obstacles the sources of rays can have different shapes and multiple vertices can share the same priority.

There is a trade off between detection accuracy and computation cost. Nevertheless this occlusion culling method provides a flexible solution that is capable of satisfying either criterion.

If the source or sources with the highest priority are intersected by objects the other rays in order of their priorities are emitted and checked for the intersection. When a ray with a specific weight is received by the view point all other sources of rays with the same weight or lower weights are discarded and never processed. If all rays from the actual avatar are blocked by objects the rays from the corresponding shadow avatar are emitted in order of the priorities.

Based on the weight of the received rays from the view point and the source of the rays actual or shadow avatar the avatar is categorised as one of the following 

The spatial distance and angular state of all avatars are categorised as the first three categories fully visible partially visible partially occluded are calculated as mentioned in this specification.

The multimedia data of other avatars are delivered to the local client in differing quality. The quality is determined based on the mentioned categories spatial distance and angular state of each client in the area of interest of the local client.

In another embodiment the multimedia data delivered to a client may be delivered in differing quality. The bandwidth usage of the system may be reduced by judiciously reducing the quality of video both in terms of resolution spatial quality and frame rate temporal quality depending on the virtual distance to the local avatar. In other words the quality of avatars videos that are further away can be reduced without any significant perceptual impact on the viewer. shows an embodiment of a local avatar and other visible avatars The visible avatars are determined after applying the data culling techniques and using position and orientation information of the avatars in the virtual environment. High quality multimedia data with a high bit rate is delivered for the avatars which are determined to be closest and visible to the local avatar such as avatar as shown in . A medium quality multimedia data is delivered for avatars that are at a medium distance and visible for example avatars The bit rate for the multimedia data may differ depending on the orientation of the other avatars to the local avatar. Low quality multimedia data is supplied for avatars that are at a greater distance from the local avatar for example at the edge of the visible range such as avatar from . The distance requirement for various quality of multimedia can be pre set at the central server or set by the local client or media server. The determination of which avatars are within which distance limits may be performed by the client. In another form this determination may be performed by the central server . In a further alternate form the data quality determination may be performed by the media server . In one form the central server may condition the data stream from a client to the appropriate quality before delivering it to another client.

At step the motion vectors of the avatars in the virtual environment are determined. At step a view field of the local avatar is determined. At step a conservative view field is determined based on the motion of the local avatar.

At step the central server performs the view field culling technique in which the server checks for which other avatars are within the conservative view field of the local avatar. The avatars that are not within the view field are disregarded and multimedia data for these avatars is not transmitted to the client associated with the local avatar.

At step a visibility culling technique is applied in which the server determines which avatars are beyond the visible range of the local avatar. The avatars that fail the visibility culling criterion as explained earlier are excluded.

At step a back face culling technique is applied. The avatars that fail the back face culling criterion as explained earlier are excluded.

At step an occlusion culling technique is applied. The avatars that fail the occlusion culling criterion as explained earlier are excluded.

At step a list of visible avatars is created. The visible avatars are the avatars that meet the pre determined criterion meaning the avatars that pass one or more of the data culling techniques explained earlier.

At step the server transmits multimedia data to the client corresponding to the local avatar for each avatars in the visible avatars list. At step the local client receives the data for the visible avatars and displays this data to an end user. As an optional extra step once the visible list of avatars is generated the server may divide the avatars up by distance from the local avatar. The local client may then receive multimedia data of the varying quality depending on the distance the avatars are from the local avatar within the virtual environment.

At step the server determines the motion vectors of the avatars in the virtual environment. At step a view field of at least one avatar is determined. At step a conservative view field of that avatar is determined based on the motion of the avatar and the relative motion of other avatars within the virtual environment. At step the central server may apply a view field culling technique in which the server determines which avatars are within the view field of at least one local avatar. The server may determine the avatars in the view field of the local avatar based on the view field constructed by the server. The avatars that are not within the view field are disregarded and multimedia data for these avatars is not transmitted to the client associated with the local avatar.

At step a visibility culling technique is applied. The avatars that do not meet the visibility culling criterion as explained earlier are excluded.

At step a back face culling technique is applied. The avatars that fail the back face culling criterion as explained earlier are excluded.

At step an occlusion culling technique is applied. The avatars that do not meet the occlusion culling criterion as explained earlier are excluded.

At step a list of visible avatars is created. The visible avatars are determined in relation to a local avatar. The visible avatars are avatars that meet the pre determined criterion meaning the avatars that pass the data one or more of the culling techniques explained earlier.

At step the central server transmits multimedia data relating to the visible avatars in the visible avatar list. At step the central server delivers the multimedia data of the clients that meet the predetermined criterion. As an optional extra step once the visible list of avatars is generated the central server may deliver or send multimedia data of varying quality depending on the distance of the visible avatars from the local avatar for the corresponding client.

It should be understood that in the method for managing multimedia data not all of the described data culling techniques are necessarily implemented. In alternate methods any one or any combination of data culling techniques may be utilised by the method. The server may receive and process the multimedia data from each client including determining what multimedia data each client receives or direct distribution of multimedia data directly between clients after determining how the multimedia data should be distributed based on the culling techniques . This may include the server simply generating a map of the virtual environment that identifies the current position orientation and movement vector of each avatar and distributing the map to each of the corresponding clients. The clients can then process the information contained in the map from the perspective of the corresponding local avatar and request multimedia as necessary from other clients without the multimedia having to be routed through the central server or media server .

A significant bandwidth saving is achieved by applying a view field culling technique and culling avatars that are not within the view field in addition to the visibility culling technique applied previously. The corresponding band width is demonstrated by the graph labelled DB view frustum culling in .

Addition of back face culling helps to save up to 86 bandwidth when compared to instances with no data culling techniques illustrated by the graph labelled no AOI by avoiding the transmission of the multimedia data of avatars that are located in the viewing frustum but facing away from the local avatar. This is shown by the graph labelled DB VFC Back face culling .

After adding the occlusion culling method the bandwidth saving reaches 90.61 when there are 60 avatars in the environment. This is shown by the final graph labelled DB VFC BFC Occlusion culling .

It is assumed that the avatars only move in the direction that they are orientated and that no sidestepping is possible. The simulated orientation and velocity of the avatars is completely random. The graph shows the reduction in bit rate after more data culling techniques are applied. The graph shows that the highest bit rate exists when no data culling technique are applied. The maximum reduction in bit rate occurs when view field culling visibility culling i.e. distance based culling back face culling and occlusion culling techniques are all applied in combination.

The graph in is a graph of a realistic scenario in which the avatars are in a clustered distribution the previous graphs were produced with the avatars arranged in a normal distribution . The graph in shows the reduction in bit rate when there is a clustered distribution of avatars and the translational and angular velocity components for all the avatars are introduced into the system. As can be seen the highest bit rate occurs when there is no data culling. The lowest bit rate occurs when all data culling techniques are applied.

It should be understood the methods and order of applying various data culling techniques described in this specification are exemplary embodiments. It is envisaged that any number of data culling techniques described could be applied in any order and the specification is not limited to a specific number or application order. It should be understood the applicant has devised a method and system for managing multimedia data in a virtual environment using predetermined criterion which is the application of data culling techniques.

Although not required the embodiments described with reference to the Figures can be implemented as an application programming interface API or as a series of libraries for use by a developer or can be included within another software application such as a terminal or personal computer operating system or a portable computing device operating system. Generally as program modules so include routines programs objects components and data files assisting in the performance of particular functions the skilled person will understand that the functionality of the software application may be distributed across a number of routines objects or is components to achieve the same functionality desired herein.

It will also be appreciated that where the methods and systems of the present invention are either wholly implemented by computing systems or partly implemented by computing systems then any appropriate computing system architecture may be utilised. This will include standalone computers network computers tablet computers mobile phones dedicated hardware devices and virtual machines. Where the terms computing system and computing device are used these terms are intended to cover any appropriate arrangement of computer hardware capable of implementing the function described.

