---

title: CDN scale down
abstract: In one embodiment, a system component in a content delivery network (CDN), the CDN including a request router and edge caches, the request router being operable to determine which edge cache should serve content to a client, the system component including a processor, and a memory to store data used by the processor, wherein the processor is operative to receive a request for content from the client, and based on a decision to shut down a first edge cache after the client has already downloaded some of the content from the first edge cache, participate in a process to transfer the client from downloading the content from the first edge cache to downloading the content from a second edge cache in the middle of the client downloading the content so that the client continues downloading the content from the second edge cache. Related apparatus and methods are also described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09602630&OS=09602630&RS=09602630
owner: Cisco Technology, Inc.
number: 09602630
owner_city: San Jose
owner_country: US
publication_date: 20140708
---
The present disclosure relates to content delivery networks and in particular but not exclusively to controlled shut down of an edge cache in a content delivery network.

A content delivery network or content distribution network CDN is a large distributed system typically deployed in multiple data centers across the Internet. The goal of a CDN is to serve content to end users with high availability and high performance. CDNs serve a large fraction of the Internet content including web objects text graphics and scripts downloadable objects media files software documents applications e commerce portals live streaming media on demand streaming media and social networks.

There is provided in accordance with an embodiment of the present invention a system component in a content delivery network CDN the CDN including a request router and a plurality of edge caches the request router being operable to determine which one of the edge caches should serve content to a client the system component including a processor and a memory to store data used by the processor wherein the processor is operative to receive a request for content from the client and based on a decision to shut down a first edge cache after the client has already downloaded some of the content from the first edge cache participate in a process to transfer the client from downloading the content from the first edge cache to downloading the content from a second edge cache in the middle of the client downloading the content so that the client continues downloading the content from the second edge cache.

There is also provided in accordance with an embodiment of the present invention a client device including a processor and a memory to store data used by the processor wherein the processor is operative to request content from a first edge cache in a content delivery network CDN including a plurality of edge caches download at least some of the content from the first edge cache while the first edge cache is still operational receive data including an identification of a second edge cache in the CDN redirecting downloading the content from the first edge cache to downloading the content from the second edge cache based on a decision to shut down the first edge cache and continue downloading the content from the second edge cache based on the identification of second edge cache.

By way of introduction a CDN typically comprises a Distribution Delivery component a Service Routing component and a Management System. The Distribution Delivery component typically comprises caches capable of acquiring the content requested by the end user locally storing caching the content and delivering the content to the end user. The caches may be organized in a flat or in arbitrary hierarchical structures to maximize the cache efficiency. The Service Routing component is typically responsible for processing the end user s initial content request for example in the form of a hypertext transfer protocol HTTP content request a domain name system DNS request for the content hostname or an application programming interface API request from some external request handling system selecting the cache from the Distribution Delivery component that is best suited to serve the request and redirecting the end user request towards the selected cache.

With HTTP Adaptive Bit Rate ABR which is becoming the dominant content delivery format a video content item is segmented in to many segments and the end user client first requests a manifest file providing information about the segments comprised in the content item and then continuously requests the next segments of interest. When served by a CDN the initial HTTP ABR manifest file request is redirected to the best edge cache at the time and then the end user typically continues requesting all segments from that same cache. The best edge cache may be defined by one or more factors including proximity of the client to the edge cache the network delay between the edge cache and the client the current spare capacity of the edge cache by way of example only. This approach works particularly well with hardware based CDNs where the edge caches are long lasting resources.

If it is desired for a CDN to be virtualized and elastic edge caches may be dynamically added CDN scale up or removed CDN scale down at a high frequency to closely adapt the allocated resources CPU memory storage network to the current load thereby minimizing the overall content delivery cost.

It may be problematic to scale down the CDN by shutting down an edge cache as the ABR sessions that had been redirected to that edge cache will continue to request subsequent content segments from that same cache until the video session is over which could be of the order of hours particularly in the case of live content thereby significantly postponing the actual removal of the virtualized edge cache which typically needs to be performed in a hitless manner from the end user viewpoint. This may unnecessarily retain resources that could otherwise be freed up very fast for example but not limited to in the order of seconds using virtualization and orchestration technologies and consequently seriously limiting the economical benefits of elastic virtualized CDNs.

Reference is now made to which is a partly pictorial partly block diagram view of a CDN system constructed and operative in accordance with an embodiment of the present invention.

It will be appreciated that only certain elements of the CDN system have been shown in the figures for the sake of simplicity.

Although the CDN system has been described below with reference to an ABR system it will be appreciated by those of ordinary skill in the art that the CDN system may be implemented with non ABR content download systems for example progressive download.

The CDN system typically includes a CDN orchestration function system a CDN request router and a plurality of edge caches including edge cache and edge cache .

The CDN orchestration function typically includes a processor and a memory . The processor of the CDN orchestration function is generally operative to monitor the edge caches to determine whether the CDN system should be scaled up or down by adding or removing an instance or instances of the edge caches respectively. Monitoring of the edge caches may be implemented by sending queries to the edge caches and or the CDN request router regarding how many clients are being served by each edge cache by way of example only. The processors of the edge caches and or the processor of the CDN request router are operative to send data to the CDN orchestration function about the clients being served by each one of the edge caches in response to the monitoring query queries. It will be appreciated that the functionality of the CDN orchestration function could be implemented partially or totally in the CDN request router .

The processor of the client client is typically operative to send a request to the CDN request router for a manifest file of the content .

The CDN request router typically includes a processor and a memory . The memory is operative to store data used by the processor . The processor of the CDN request router is typically operative to receive the content request for example typically an HTTP get request for the manifest file of the content from the client client in . In response to receiving the request for the manifest file of the content from the client the processor of the CDN request router is typically operative to determine which one of the edge caches should serve the manifest file of the content to the client client and send an identification of the selected edge cache edge cache to the client client in order for the client client to retrieve the manifest file and the content from the edge cache edge cache . It will be appreciated that the identification of the selected edge cache may be conveyed inside a Uniform Resource Locator URL included in a HTTP redirection response.

The processor of the client client is typically operative to receive the identification from the CDN request router and send a request for the manifest file to the edge cache edge cache .

Each edge cache typically includes a processor a memory and a cache memory . The memory is generally operative to store data used by the processor . The cache memory is generally operative to store the content therein and optionally the manifest file .

The processor of the edge cache edge cache is operative to receive the request for the manifest file from the client client . The processor is operative to send serve the manifest file to the client client . The processor of the client is operative to receive the manifest file .

The content typically includes a plurality of segments . The manifest file includes location data for each of the segments . The location data points to the first edge cache where the segments are stored.

The processor of the client client is operative to request each of the segments of interest of the content via a request from the edge cache edge cache based on the location data stored in the manifest file .

The processor of edge cache is operative to receive each content request for the relevant segments of the content from the client client and serve each of the requested segments of the content stored in the cache memory to the client client .

The processor of the client client is operative to download the requested segments representing at least some of the content from the edge cache edge cache .

Manifest files used to locate segments of the content may include relative or absolute locators as will be described in more detail with reference to .

Reference is now made to which is a partly pictorial partly block diagram view of a manifest file with relative locators for use in the CDN system of .

The manifest file is typically stored by one or more of the edge caches for download to the clients . The manifest file is located by a locator not shown for example but not limited to a URL. The manifest file references segments of the content using one of the relative locators for each of the segments. To retrieve any one of the segments the locator of the manifest file is prepended to the relative locator of that segment yielding a compounded locator for example a URL of that segment. The compounded locator is used by the clients to download that segment. The relative locators are described with reference to in more detail including an example of how the relative locators are used.

Instead of including multiple locators the manifest file may include a rule or rules including a partial relative locator from which location of the segments can be determined.

Reference is now made to which is a partly pictorial partly block diagram view of a manifest file with absolute locators for use in the CDN system of . The manifest file may be stored in one of the edge caches or in the CDN request router or in another suitable location. The manifest file references segments of the content using one of the absolute locators . To retrieve any one of the segments the absolute locator is used by the clients to download that segment.

Instead of including multiple locators the manifest file may include a rule or rules including a partial absolute locator from which location of the segments can be determined.

Reference is now made to which is a partly pictorial partly block diagram view of one of the edge caches edge cache being shut down in the CDN system of .

If the processor of the CDN orchestration function determines that the CDN system should be scaled down the processor of the CDN orchestration function is operative to determine which edge cache s should be removed shut down. The CDN orchestration function notifies the CDN request router that new requests should not be redirected to the cache s being removed shut down. In the example of edge cache has been selected by the CDN orchestration function for shut down.

The CDN orchestration function typically notifies edge cache and or the CDN request router to trigger a fast session offloading .

The fast session off loading is performed by the CDN request router and edge cache using a suitable offloading method. Alternative offloading methods are described with reference to .

In general the processor of edge cache and or the processor of the CDN request router are operative based on a decision to shut down edge cache after client has already downloaded some of the content from edge cache to participate in a process to transfer client from downloading the content from edge cache to downloading the content from another edge cache edge cache in the middle of client downloading the content so that client continues downloading the content from edge cache . The example of also shows that client has been transferred to edge cache .

In each of the offloading methods described in more detail with reference to the processor of the CDN request router is operative to select the edge cache from which the client s will continue downloading the content . It should be noted that the CDN request router may select the same edge cache or different edge caches for different clients .

The processor of client is operative while edge cache is still operational that is prior to edge cache being terminated by the CDN orchestration function or another element to receive data including an identification of edge cache selected by the CDN request router redirecting downloading the content from edge cache to downloading the content from edge cache based on a decision to shut down edge cache . The re directing process is described in more detail with reference to below. Then the processor of client is operative to continue downloading the content from edge cache based on the identification of edge cache .

When edge cache no longer serves any sessions or a number below some threshold the processor of edge cache sends a notification to the CDN orchestration function that edge cache is no longer serving content to any client or the number of clients being served is below a threshold. Alternatively the CDN orchestration function will assume that fast session offloading has been completed after a certain timeout without needing a notification from edge cache .

Therefore the processor of the CDN orchestration function is then typically operative to trigger termination of edge cache i on receipt of a notification from edge cache that edge cache is no longer serving content to any client or a number of clients below a threshold number of clients or ii after a certain timeout.

It should be noted that the CDN Management System component not shown may be involved as an intermediary agent in some of the steps above.

It should also be noted that the CDN system may use any appropriate CDN request redirection to redirect the client to the edge cache for example but not limited to hypertext transfer protocol HTTP domain name system DNS and application programming interface API .

Reference is now made to which is a partly pictorial partly block diagram view of a first client being transferred from one edge cache to another in the CDN system of .

The transfer method described with reference to may be implemented in any suitable environment but may be particularly useful when the CDN request redirection method that initially pointed the ABR session client to edge cache is HTTP and the CDN technology is Cisco Video Distribution Suite for Internet Streaming VDS IS .

When the manifest file of with the relative locators is used the initial HTTP redirection may be performed by prepending the locator of the manifest file to the relative locator as described above with reference to . To perform the fast session offloading edge cache may perform reverse domain name manipulation in order to redirect the content request back to the CDN request router which then performs edge cache selection and redirection towards another edge cache e.g. edge cache .

For example if the content domain name is video.my cdn.net the client HTTP ABR session may initially be redirected to the edge cache using the paris streamer.se.video.my cdn.net hostname. The client pulls the HTTP ABR manifest file and segments using the paris streamer.se.video.my cdn.net hostname. If it is decided that the Paris edge cache should be scaled down the Paris edge cache can redirect the next segment request s from the client s towards video.my cdn.net which will direct the request to the CDN request router . The CDN request router selects the best edge cache for each client excluding the edge cache under scale down because it has been flagged as such and issues a redirect to the newly selected edge cache for example using brussels streamer.se.video.my cdn.net .

Typically after receiving a shut down notification from the CDN orchestration function the processor of the edge cache is operative to redirect the client to the CDN request router block typically using an HTTP redirect to the CDN request router so that the client can receive an identification of a newly selected edge cache edge cache selected by the CDN request router for the client to continue downloading of the content therefrom.

The processor of the client is operative to send a content request to the CDN request router based on the redirect from the edge cache .

The processor of the CDN request router is typically operative to receive the request from the client related to receiving the content . The processor is operative to select a new one of the edge caches edge cache for the client to continue downloading the content therefrom block . The processor of the CDN request router is typically operative to send the identification of the selected edge cache edge cache to the client typically as part of a redirect command in order for the client to continue downloading the content from edge cache . The identification of edge cache typically includes a locator for example but not limited to a URL of edge cache .

The processor of the client is typically operative to prepend the locator of edge cache to at least some of the locators listed in the manifest file of the segments of the content yielding a plurality of new locators not shown and request segments based on the new locators block . The processor of the client is operative to continue downloading the content from edge cache based on the new locators of the segments of the content .

Reference is now made to which is a partly pictorial partly block diagram view of a second client being transferred from one edge cache to another in the CDN system of .

In the example of edge cache first queries the CDN request router to obtain the identification such as a locator for example but not limited to a URL of the newly selected edge cache so that edge cache can directly redirect the client towards the newly selected edge cache typically using an HTTP redirect which includes the identification of the newly selected edge cache.

The processor of edge cache is operative to send a request to the request router to select one of the edge caches from which the client will continue downloading of the content . The request sent by edge cache may be via any suitable interaction for example but not limited to via a suitable application programming interface API . The processor of the CDN request router is operative to receive the request from edge cache select the new edge cache edge cache block and send the identification of the selected edge cache edge cache to edge cache .

The processor of edge cache is operative to receive the identification of the selected edge cache edge cache from the request router and send the identification of edge cache to the client typically as part of a redirect command.

The processor of the client is operative to prepend the locator of edge cache to at least some of the locators listed in the manifest file of a plurality of segments of the content yielding a plurality of new locators not shown and to request segments based on the new locators block . The processor of the client is operative to continue downloading the content from edge cache based on the new locators of the segments of the content .

Reference is now made to which is a partly pictorial partly block diagram view of a third client being transferred from one edge cache to another in the CDN system of .

In some implementations it may be advantageous to first trigger the client to request a new manifest from edge cache and then once the manifest request is received to redirect the client to edge cache as described in more detail below.

In the example of edge cache triggers the client to request a new manifest from edge cache and continue to download the content from edge cache based on the manifest . It will be appreciated that the data included in the manifest of edge cache may be the same as or very similar to the data included in the manifest of edge cache especially when the locators included in the manifests are relative locators.

The processor of edge cache is typically operative to send request to the request router to select one of the edge caches from which the client will continue downloading of the content .

The processor of the CDN request router is typically operative to receive the request from edge cache and select the new edge cache edge cache block .

The processor of the CDN request router is typically operative to send the identification of the selected edge cache edge cache to edge cache .

The processor of edge cache is typically operative to receive the identification of the selected edge cache edge cache from the request router .

The processor of edge cache is typically operative to send data to the client to trigger the client to re request a manifest file block .

The processor of the client is generally operative to receive the trigger from the edge cache to re request a manifest file.

The processor of the client is typically operative to re request a manifest file from edge cache block .

The processor of edge cache is operative to receive the manifest file request from the client and then send to the client a redirect to edge cache block .

The processor of the client is typically operative to receive the redirect from edge cache . The processor of the client is generally operative to request a manifest file for at least part of the content from edge cache block based on receiving from edge cache the redirect which included the identification of edge cache selected by the request router for the client to continue downloading of the content therefrom.

The processor of the client is generally operative to receive a manifest file from edge cache and continue downloading segments of the content from edge cache based on sending requests to edge cache based on the locators not shown in the manifest file . The locators in the manifest file may either be relative or absolute locators.

Reference is now made to which is a partly pictorial partly block diagram view of a fourth client being transferred from one edge cache to another in the CDN system of .

In some implementations it may be advantageous to first trigger the client to request a new manifest from edge cache and then once the manifest request is received by edge cache to redirect the client to the CDN request router as described in more detail below.

The processor of edge cache is operative to send data to the client to trigger the client to re request a manifest file block . The processor of the client is typically operative to receive the trigger from edge cache to re request a manifest file and then send a request for a manifest file to edge cache based on receiving the trigger.

On receipt of the re request of the manifest file the processor of edge cache is operative to send data to the client to redirect the client to the CDN request router block . The processor of the client is typically operative to receive from edge cache the redirect to the CDN request router .

Based on the redirect the processor of the client is then operative to request a manifest file from the CDN request router block .

The processor of the CDN request router is operative to receive the manifest file request related to receiving the content from the client select a new one of the edge caches edge cache block and send the identification of the selected edge cache edge cache to the client typically as part of a redirect command in order for the client to continue downloading the content from edge cache .

The processor of the client is then operative to receive the identification of edge cache from the CDN request router typically as part of a redirect command.

The processor of the client is then typically operative to request a manifest file block for at least part of the content from edge cache based on receiving the identification of edge cache selected by the CDN request router for the client to continue downloading of the content therefrom.

The processor of the client is then operative to receive the manifest file from edge cache and continue downloading the segments of the content from edge cache based on sending requests to edge cache based on the locators not shown in the manifest file .

It will be appreciated that the data included in the manifest of edge cache may be the same as or very similar to the data included in the manifest of edge cache especially when the locators included in the manifests are relative locators.

Reference is now made to which is a partly pictorial partly block diagram view of a fifth client being transferred from one edge cache to another in the CDN system of .

The fast session offloading may be performed by edge cache and the CDN request router using a process based on manifest file manipulation instead of using HTTP redirection. This is particularly useful in environments where the client pulls a fresher manifest file at regular intervals as is the case with some HTTP ABR protocols for Live content delivery or where the client can be triggered to pull the fresher manifest file . The manifest file is typically manipulated by the CDN request router where the manifest file is stored for download by the client .

It may be possible for the processor of edge cache to manipulate the manifest file . In such a case edge cache queries the CDN request router to determine which of the edge caches will continue to serve the client with the segments of the content .

The processor of the edge cache is typically operative to send data to the client to trigger the client to re request the manifest file block . The data sent to the client typically includes a locator of the CDN request router or a locator for the location where the manifest file is stored. Triggering the client to re request the manifest file or any of the other triggering events described above may be specified by an ABR protocol or performed using any suitable mechanism.

The processor of the client is operative to receive the trigger from edge cache and re request the manifest file from where it is red for example on the CDN request router block or edge cache or some other suitable location. The description below assumes that the manifest file is stored at the location of the CDN request router .

Then the processor of the CDN request router is operative to receive the re request of the manifest file and select a new one of the edge caches edge cache block and edit the manifest file so that location data of the segments of the content which are still to be downloaded is amended from pointing to edge cache to pointing to edge cache block and serve the manifest file to the client .

The processor of the client is operative to receive the manifest file which has been amended to point to edge cache instead of pointing to edge cache then continue downloading the segments of the content from edge cache based on sending requests to edge cache based on the amended locators not shown in the manifest file

The CDN system has been described above based on a non hierarchical manifest file structure for example where a single manifest file includes rules and or locators to the segments of all the available bitrates. However it will be appreciated that the CDN system may be implemented using a hierarchical manifest file structure as will be described in more detail below.

In some ABR schemes a hierarchical manifest file structure is employed. In one such scheme a top level manifest includes pointers to several lower level manifest files. Each of the lower manifest files is provided for the segments of each available video bitrate. Each of the lower level manifest files includes rules and or pointers to build the locator e.g. URL for each segment of the bitrate of that lower level manifest file.

When the CDN system is implemented with a multi level manifest file structure and as in the examples of where the manifest file request from the client or the client is re directed to edge cache the client is typically triggered to re request the highest level manifest file from edge cache and follow the links in the highest level manifest file to the lower level manifest files as necessary in order to request the relevant segments of the content from edge cache .

When the CDN system is implement with a multi level manifest file structure and as in the example of the manifest file request from the client is not re directed to edge cache the client is typically triggered to re request the highest manifest file from the same location that the highest level manifest file was previously retrieved from for example from the CDN request router or some other suitable location and follow the links in the highest level manifest file to the lower level manifest files as necessary in order to request the relevant segments of the content from edge cache .

In practice some or all of these functions may be combined in a single physical component or alternatively implemented using multiple physical components. These physical components may comprise hard wired or programmable devices or a combination of the two. In some embodiments at least some of the functions of the processing circuitry may be carried out by a programmable processor under the control of suitable software. This software may be downloaded to a device in electronic form over a network for example. Alternatively or additionally the software may be stored in tangible non transitory computer readable storage media such as optical magnetic or electronic memory.

It is appreciated that software components may if desired be implemented in ROM read only memory form. The software components may generally be implemented in hardware if desired using conventional techniques. It is further appreciated that the software components may be instantiated for example as a computer program product or on a tangible medium. In some cases it may be possible to instantiate the software components as a signal interpretable by an appropriate computer although such an instantiation may be excluded in certain embodiments of the present invention.

It will be appreciated that various features of the invention which are for clarity described in the contexts of separate embodiments may also be provided in combination in a single embodiment. Conversely various features of the invention which are for brevity described in the context of a single embodiment may also be provided separately or in any suitable sub combination.

It will be appreciated by persons skilled in the art that the present invention is not limited by what has been particularly shown and described hereinabove. Rather the scope of the invention is defined by the appended claims and equivalents thereof.

