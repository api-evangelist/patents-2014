---

title: System and method of leveraging GPU resources to increase performance of an interact-able content browsing service
abstract: A system and a corresponding method of leveraging GPU resources to enhance performance of the interact-able content browsing (ICB) service are to utilize the computation capacity of the GPU of the graphics card to share the computation load originally taken by the CPU. The raw images depicted by the browser application program executed in the server can be directly retrieved from the VRAM of the graphics card by the encoder inside the GPU to be further encoded and streamed before being forwarded directly to distant clients. Thereby, work load and bus bandwidth occupation on the CPU can be greatly reduced, the number of clients that can be served simultaneously by a single server can be increased, and the related power consumption can be substantially reduced.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09483996&OS=09483996&RS=09483996
owner: ubitus, Inc.
number: 09483996
owner_city: 
owner_country: VG
publication_date: 20140320
---
This invention relates to a system and a method of leveraging GPU Graphics processing unit resources to enhance performance of an interact able content browsing ICB service and more particularly to the system and the method for enhancing the performance of an interact able content browsing service that can introduce the GPUs to directly capture encode and stream raw images in memory of a display card so as to save the operational bandwidth of the central processing unit CPU .

In a cloud based service system for example but not limited to a system for providing a cloud based web browsing and or application service a typical job of a server therein is to deliver web based content or other kinds of contents to clients at far ends. When the content to be delivered contains video data raw images related to the content shall be encoded in advance at the server end into a video stream before such content can be transmitted to specific clients and can be presents at displayers of the clients in a web form or other formats. Particularly in the case while more than one client intends to capture the video content from a single cloud based service system at the same time jobs of encoding the raw images and stream transferring the encoded data between the GPU and the CPU would occupy huge workable bandwidths of the system resources and the CPU which can be originally applicable to application programs. Such an arrangement would inevitably limit the cloud based service and also the number of clients accessing the system simultaneously. Further for those cloud based services with almost the same capacity the power consumption will also be an issue.

Referring to a typical cloud based service system is illustrated in a block form. The cloud based service system can perform the cloud based network application and web browsing service to provide data to a data center in accordance with the following structuring.

1. Display to display a plurality of raw images at display peripherals by executing the browser application program at the server ends of the cloud based service system through performing the application programming interface API of the operating system OS 

2. Encode to capture the raw images displayed at the display peripherals and to transfer the captured raw images to a hardware or software encoder for further encoding and streaming 

3. Stream to capture the streamed data from the encoder for being further distributed to the distant client ends through the network facilities .

As shown in the browser application program performed individually by the servers or of the cloud based service system can only provide service to a single client or once at a time. If a need to enlarge the service capacity of the system cost hike in increasing the number of the servers would be too high to be accepted.

Referring to another typical cloud based service system is shown in a block form. The system performs the following operations to provide the cloud based network application and browsing services.

1. Program a server of the cloud based service can execute a plurality of application programs and . Each of the programs or can individually form a respective program executing environment to provide the distant client or to obtain the service of the server through the network facilities .

2. Memory the browser application program executed by the server of the cloud based service system can depict a plurality of raw images displayed at the display peripherals through the application program interface of the operation system. The raw images are further stored in the system memory of the server controlled by the operation system.

3. Encode to capture the raw images in the system memory controlled by the operation system and further to forward these raw images to a hardware or software encoders for further encoding and streaming.

4. Stream to capture the streamed data from the encoder and to forward the streamed data to the respective distant client through the network facilities .

As shown in each of the servers and of the cloud based service system can provide services simultaneously to plural clients and . However for storing the raw image into the system memory and encoding the raw images need to consume the work capacity of the CPU of the respective server and also for the transmission of the raw images between the system memory and the video RAM VRAM will occupy a considerable range of bus bandwidths huge operation loads would be inevitable to the servers and and to limit the number of the clients that can be served at the same time by a single server. Also tremendous power consumption therein can be expected.

Accordingly it is the primary object of the present invention to provide a system and a corresponding method that can enhance performance of an interact able content browsing ICB service by leveraging GPU resources. Thereby the number of clients that can be served simultaneously by a single server can be increased and also energy consumption of the system can be substantially reduced.

According to the present invention the system and the method of leveraging GPU resources to enhance performance of the interact able content browsing service are to utilize the computation capacity of the GPU of the graphics card to share the computation load originally taken by the CPU. Thereby the raw images depicted by the browser application program executed in the server can be directly retrieved from the VRAM of the graphics card by the encoder inside the GPU to be further encoded and streamed before being forwarded to distant clients. Upon such an arrangement work load and bus bandwidth occupation on the CPU can be greatly reduced the number of clients that can be served simultaneously by a single server can be increased and the related power consumption can be substantially reduced.

In a preferable embodiment of the present invention the system of leveraging GPU resources to enhance performance of the interact able content browsing service can include at least a network facilities and at least a server. At least one client can use a network environment to capture a specific content of the system. The network facilities are to wirely or wirelessly connect with the network environment. The server is connected wirely or wirelessly to the network facilities. The network facilities can use the network environment to establish connection between the client and the server. In this embodiment each server includes a CPU module and at least a graphics card.

The CPU module can further include a CPU to performing an OS and to execute at least an application program under the OS. Each of the application programs can form a respective application runtime environment for the corresponding one client to establish network connection and to make a capture request through the application runtime environment.

The graphics card can include individually a VRAM and at least a GPU based encoder. Each of the GPU based encoders is correspondence to an application runtime environment. The application runtime environment can generate at least a raw image to be stored into the VRAM. According to the capture request from the client the corresponding GPU based encoder is to retrieve the corresponding raw image from the VRAM and to encode and stream the raw image for further forwarding to the respective client.

In one embodiment of the present invention the capture request can be the request of the connected client to obtain the raw image generated by the application runtime environment for a further browsing purpose at the client end. The application runtime environment can accordingly to generate an application program interface API redirecting event. The respective GPU based encoder can accord to the API redirecting event to retrieve the correspondent raw image from the VRAM for further encoding streaming and computing.

In one embodiment of the present invention the content of the request can be a content of the interact able content browsing service ICB and can be a webpage shown at the client end. The webpage definitely includes the raw image.

In one embodiment of the present invention the OS can be one of the following Windows XP Windows Vista and Windows 7.

In one embodiment of the present invention the network environment can be one of the following an internet environment a telephone communication network environment and a cable television network environment.

In one embodiment of the present invention the client end capable of network connection can be one of the following a computer a PDA a mobile phone a game station and a set top box.

All these objects are achieved by the system and the method of leveraging GPU resources to enhance performance of an interact able content browsing service described below.

The invention disclosed herein is directed to a system and a method of leveraging GPU resources to enhance performance of an interact able content browsing service. In the following description numerous details are set forth in order to provide a thorough understanding of the present invention. It will be appreciated by one skilled in the art that variations of these specific details are possible while still achieving the results of the present invention. In other instance well known components are not described in detail in order not to unnecessarily obscure the present invention.

In the present invention the system and the method of leveraging GPU resources to enhance performance of the interact able content browsing service are to utilize the computation capacity of the GPUs of the graphics card to share the computation load originally taken by the CPU. Thereby the raw images depicted by the browser application program executed in the server can be directly retrieved from the VRAM of the graphics card by the encoder inside the GPU to be further encoded and streamed before being forwarded directly to distant clients. Upon such an arrangement work load and bus bandwidth occupation on the CPU can be greatly reduced the number of clients that can be served simultaneously by a single server can be increased and the related power consumption can be substantially reduced.

Referring now to and shows a structure of an embodiment of the system of leveraging GPU resources to enhance performance of an interact able content browsing service in accordance with the present invention and shows details of a server in .

As shown in the system of leveraging GPU resources to enhance performance of the interact able content browsing service in accordance with the present invention can provide at least a client plural clients and in to utilize a network environment for establishing connection with the system and for further obtaining services from the system . For example but not limited to the example a content of the system can be captured and displayed at correspondent displayers at client ends and . The network environment can be one of the following an internet environment a cable television network environment and a telephone communication network environment in which the telephone communication network environment can be but not limited to a global system for mobile communication GSM a general packet radio service GPRS a code division multiple access CDMA or any the like. In the present invention the clients can be broadly explained as any electronic device that can connect with the network environment any of the internet environment the cable television network environment and the telephone communication network environment . The electronic device can be one of the following a computer a PDA a mobile phone a game station and a set top box.

In one embodiment of the present invention the system of leveraging GPU resources to enhance performance of the interact able content browsing service can include at least a network facilities and at least a server plural clients in general . The network facilities are to wirely or wirelessly connect with the network environment . The network facilities can use the network environment to establish connection between the distant client or and the server or so as to have the clients accessible to the cloud based service provided by the system . In the present invention following descriptions elucidate how the servers of the system is to provide the cloud based network applications and browsing service of a database center to the individual clients and .

1. Problem located in the server for example to perform individually a plurality of application problems these problems are not limited to browser application problem . Each of the problems can form a correspondent application runtime environment to be used by the distant clients to obtain the service of the same server through the network facilities . Such services are not limited download of web pages and the browsing service.

2. VRAM to use the application runtime environments formed by performing the corresponding application programs to sketch visional a series of raw image contents that can be displayed in a display peripheral and further to store the raw images into the VRAM of the graphics card. In this operation every element of the first raw image would be written into the VRAM . Thereafter for the following raw images only those elements that are different to those of the previous raw image would be written into the VRAM .

3. Encode to utilize the GPU based encoder or GPU encoder on the graphics card to retrieve the raw images from the VRAM controlled by the graphics card and to further encode and stream the retrieved raw images.

4. Stream to capture the data stream from the VRAM and to transfer these data stream to the distant clients via the network facilities such that these raw images can be shown to the displays of the clients in a webpage form. In the present invention the webpage formed raw images are not limited to be displayed by a browser such like Internet Explorer developed by Microsoft but also can be displayed by any other means which are capable of showing visual contents such as raw images retrieved from Internet onto the display device of the client .

For the sketching or reforming of the raw images can be triggered by instant changes in the states or arrangements of specific elements therefore in the serial operation of reforming the raw images only the new matters shall be updated to the original images it is not required to retrieve the total raw images from the system memory of the server to the VRAM . Upon such an arrangement the data volume written to the memory can be reduced the need or importance of the CPU of the server can be reduced and the processing efficiency can be increased. When there is a need to encode the raw images the GPU encoder would capture the stored raw images from the VRAM and then the raw images are encoded and forwarded in a stream form. Obviously such an operation won t occupy additional bus bandwidths in the server and also won t increase the work load on the CPU of the server . Hence by compared to the prior art the system and the method of leveraging GPU resources to enhance performance of an interact able content service in accordance with the present invention has the following advantages.

1. Every server or can execute more applications and at the same time without sacrificing the service efficiency for the method of the present invention won t forward the output of the display peripherals to the software or hardware encoder controlled by the OS of the server and .

2. Every server or can provide quality service capacity to more clients and at the same time. Thus the consumption in the bus bandwidths can be greatly reduced.

3. A higher work efficiency can be achieved by using the GPU encoder inside the graphics card to encode the raw images.

4. Energy consumption of the server and for the comparable levels of jobs can be substantially decreased.

As shown in the server the same structure as the server of can include at least a CPU module and at least a graphics card .

The CPU module can further include a CPU to performing an OS and to execute at least an application program preferably to be plural programs under the OS . The CPU controls the OS and the application programs to work together in performing the processing of the video images and audio data. Each of the application programs can form a respective application runtime environment or for the corresponding one distant client to establish network connection and to make a capture request through the application runtime environment. The connected client can use the application runtime environment or to make a capture request for capturing a content from the server . Each of the graphics cards can include individually a VRAM and at least a GPU based encoder or say GPU encoder and preferably to be plural . Each of the application runtime environments and is respective to one of the GPU encoders and . Each of the application runtime environments and can generate at least one respective raw image or to be stored into the VRAM . According to the capture request from the client the corresponding GPU encoder is to retrieve the corresponding raw image from the VRAM and to encode in a predetermined format and stream the raw image for further forwarding to the respective client.

In the embodiment the OS can be preferably but not limited to a native OS such a Windows XP a Windows Vista and a Windows 7. Further the captured content of the client from the server can be a content of an interact able content browsing service ICB in which the content can be shown to the browser of the client in a webpage form and the webpage includes the raw image . In the present invention services provided by the ICB system are not merely to allow clients to retrieve video files or image streams from the servers and to display the same on the clients. Contrary users of the clients can control and change the ICB contents interactively. Taking on line game as an example the game program executed in the client end does not draw nor generate the raw images by itself in stead the game program monitors the signals coming from the input peripherals such as mouse arrow or control keys or touch panel and then transform these operational signals into control messages and then sends these control messages to the server remotely located in the ICB system. The server then draws and generates those raw images based on the control messages encodes the raw images into streams and then sends back to the client for display. Therefore the raw images shown on the display device of the client actually will change according to the operation signals coming from the input peripheral of client. Such that although the user of client might feel these raw images are generated by the client but in fact they are generated by the ICB system remotely and thus the loading of the client can be significantly reduced.

In this embodiment the capture request can be the request of the connected client to obtain the raw image generated by the application runtime environment for a further browsing purpose at the client end. The application runtime environment can accord to the capture request to generate an application program interface API redirecting event . The respective GPU encoder can accord to the API redirecting event to retrieve the correspondent raw image from the VRAM for further encoding and streaming before being forwarded to the client. In this operation no encoding and streaming upon the raw image by the CPU is needed and also there is no need to transfer the raw image between the system memory and the VRAM so that the occupation problem in bus bandwidths can be resolved.

In the following listing an example shows a program listing or source codes for details of how the present invention at a moment of locating an API redirecting event can react to introduce GPU encoder to retrieve raw images from the VRAM and to further encode and stream the raw images. Please note that although the following codes are coded based on nVidia CUDA but they are not limited to this example for the following commands of the source codes can be understood to the skill person in the art details of the codes would be omitted herein.

Referring now to a flowchart of an embodiment showing operations at server end of the ICB under a performing environment in accordance with the present invention is illustrated. The operations include the following steps.

Step The ICB service of the present invention is to operate under an environment of executing the OS not limited to Window systems of a server and an ICB application program is executed to form an ICB runtime environment for providing the distant clients to establish network connection and to capture the ICB content service. Then go to Step

Step Check if the ICB content to be captured by the client has video or audio output If including the video output go to Step . If including the audio output go to Step . If including none of the video and audio output go back to Step for waiting a next capture request of the ICB content.

Step The ICB content uses the visualized output API of the native OS according to the type of the ICB content in which the type of the ICB content is determined in Step .

Step Determine the type of the ICB content. If the ICB content is a video of Windows GDI go to Step . If the ICB content is a video of DirectX go to Step . If the ICB content is a video for web browsing go to Step .

Step The ICB content queries to redirect the audio output API of the native OS to the corresponding audio driver under the current ICB runtime environment.

Referring now to a flowchart is provided to show an embodiment of the method of leveraging GPU resources to enhance performance of an interact able content browsing service at system end in accordance with the present invention. The method includes the following steps.

Step The system of leveraging GPU resources to enhance performance of an interact able content browsing service in accordance with the present invention receives an ICB service request from a client end. Go to Step .

Step Check if the ICB content has video or audio output If including the video output go to Step . If including the audio output go to Step . If including none of the video and audio output go back to Step .

Step According to an interactive streaming protocol the ICB content is encoded and streamed and encrypt the coded bitstream the encoded stream to the client end.

Step An audio live encoder extracts the auditable content from the ICB runtime environment. Go to Step .

Referring now to a flowchart is provided to show an embodiment showing operations at client end in accordance with the present invention. The flowchart includes the following steps.

Step Session ongoing. The client continuously executes a client application program in order to allow the client to connect to the ICB system connect and use the runtime environment generated by one of the ICB application programs executed in one of the servers in the system and retrieve the raw images encoded and streamed by one of the video cards inside the used server.

Step The client that is connected to the ICB system waits for operation signals from its native input peripheral such like but not limited to mouse arrow or functional keys or touch panel and transforms these operation signals into corresponding control messages.

Step The server inside the ICB system checks if the control messages can be recognized If NO then the server drops the control messages and then go back to step . If YES then proceed step .

Step The server of ICB system processes corresponding control messages and send these control messages to the corresponding application runtime environment generated by the application program executed by that server.

Step The application runtime environment generated in the server of ICB system generates corresponding visualized content such as raw image based on the control messages.

Referring now to which is a flowchart of an embodiment of the playback procedures at client end of the ICB system in accordance with the present invention. The flowchart includes the following steps.

Step The client receives the encoded streams of raw images from the server remotely located inside the ICB system.

Step To detect if an End of Session EoS signal is existing If NO then go back to step . If YES then proceed step in order to finish the playback session.

While the present invention has been particularly shown and described with reference to a preferred embodiment it will be understood by those skilled in the art that various changes in form and detail may be without departing from the spirit and scope of the present invention.

