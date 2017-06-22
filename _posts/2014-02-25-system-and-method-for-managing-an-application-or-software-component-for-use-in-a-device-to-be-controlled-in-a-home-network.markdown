---

title: System and method for managing an application or software component for use in a device to be controlled in a home network
abstract: The present invention relates to a system and method for managing an application wherein a function of a controlled device can be dynamically extended by continually updating the application for use in the controlled device. According to the present invention, a framework capable of providing integrated support to a variety of home network middleware is loaded on an application server corresponding to a control device, and Internet access services and middleware services for accessing various kinds of devices are bundled into the framework. Thus, application installation and management can be performed within a home network environment regardless of the hardware, network protocol and operating system used.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09038061&OS=09038061&RS=09038061
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09038061
owner_city: Suwon-si
owner_country: KR
publication_date: 20140225
---
The present application is a Continuation Application of U.S. patent application Ser. No. 12 551 656 now U.S. Pat. No. 8 677 350 filed on Sep. 1 2009 which is a Continuation Application of U.S. patent application Ser. No. 10 685 407 now U.S. Pat. No. 8 707 295 filed on Oct. 16 2003 which claims priority from Korean Patent Application No. 10 2003 0000058 filed on Jan. 2 2003. The above noted applications are incorporated herein by reference in their entireties.

The present invention relates to a system and a method for managing an application or software component for use in a device to be controlled in a home network environment and more particularly to a system and a method for managing an application wherein a function of a device to be controlled can be dynamically extended by continually updating the application for use in the appliance. The present application is based on Korean Patent Application No. 10 2003 0000058 which is incorporated herein by reference.

A home network system is a system for connecting and controlling PCs peripheral equipment mobile phones electric home appliances and the like through one network. A proposed method to configure the home network system is such that a common virtual computer environment called middleware is built into home appliances and applications are provided for the appliances. Here the middleware is capable of communicating between appliances in a home network. The currently available middleware includes home AV interoperability HAVi universal plug and play UPnP Jini home wide web HWW and the like.

However as functions of appliances improve and become more complicated the need to install the latest application in addition to the application already installed upon purchase thereof has increased. For example if a TV can support a high quality sound format e.g. surround sound stereo etc. but a poor tuner cannot support the high quality format the high quality format cannot be used.

According to such a trend technologies for providing new applications for use in controlled devices have developed. For example Korean Patent Application No. 2000 7007449 of which the title of invention is a method and system related an audio video network discloses a method capable of supporting a more superior performance through a device driver updated in such a manner that the device driver is updated when the appliance to be controlled is connected with the home network system.

Here the IEEE 1394 is a high speed serial bus interface for connecting several appliances in the home with one another and a device control module DCM is a software component for controlling the appliance to be controlled i.e. an application programming interface API needed when a user intends to use a function of a device. In particular the DCM is obtained by installing a bytecode of the DCM and should exist in the FAV in order to control the device. Further the bytecode of the DCM may reside in the BAV or exist at other locations e.g. at a file server on the Internet.

As shown in in a case where a bytecode of a DCM resides in a BAV an FAV causes the bytecode of the DCM to be loaded from a memory of the BAV and the loaded bytecode to be installed therein when the BAV is connected with the home network system. Alternatively as shown in in a case where a bytecode of a DCM resides in a file server an FAV causes a URL of the DCM to be read from a memory of a BAV and then causes the read bytecode to be loaded from the file server and the loaded bytecode to be installed therein when the BAV is connected with the home network system.

However such an application installation method is restrictively applied to the HAVi home network based on the IEEE 1394 technique because it can be executed only with the IEEE 1394 for supporting a hot plug and play. Further since it is determined that the FAV should install and manage the application there is a problem in that a large load is imposed on the FAV due to operations of installing and managing the applications for the several BAVs connected with the home network.

Furthermore since the FAV is configured to install the DCM only once upon initial connection of the BAVs with the home network there is another problem in that it is difficult to provide continual application update services.

Accordingly the present invention is contemplated to solve the above problems in the prior art. An object of the present invention is to provide a system and method for managing an application which can be independently operated in a home network environment.

Another object of the present invention is to provide a system and method for managing an application wherein a function of a controlled device can be dynamically extended by allowing a control device and the controlled device to control installation and management of the application and continually updating the application for use in the controlled device.

According to an aspect of the present invention for accomplishing the objects there is provided an application management system comprising a plurality of controlled devices and an application server wherein the application server performs the installation and management of applications for the controlled devices by using a framework capable of providing integrated support to a variety of home network middleware.

Further the application management system of the present invention may comprise an application server loaded with a framework capable of providing integrated support to a variety of home network middleware and the controlled devices which control the application server and perform installation and management of applications for the controlled devices.

Furthermore the home network middleware may be selected from a group consisting of HAVi UPnP Jini and HWW.

More preferably the framework provides Internet access services and home network middleware services.

Hereinafter preferred embodiments of the present invention will be described with reference to the accompanying drawings.

In the present invention the configuration of an application management system may vary according to which one of a control device and a controlled device can manage the application. More specifically the application management system of the present invention may be divided into two types a pull mode in which the application server control device becomes a subject of management and performs the application installation and management and a push mode in which the controlled device becomes a subject of management and performs the application installation and management.

First the application management system in the pull mode in which the application server becomes the subject of management and performs the application installation and management will be explained with reference to .

The application server includes a home network middleware module for communicating with the controlled device an application loader module for downloading an application file from the file server and an application management module for controlling operations of the home network middleware module and the application loader module . An open services gateway initiative OSGi framework is loaded on the application server and the home network middleware module and the application loader module are bundled into the OSGi framework .

Here the reason that the OSGi framework is loaded on the application server and the home network middleware module and the application loader module are bundled into the OSGi framework is that an independent home network system can be implemented into a middleware. Hereinafter for better understanding of the present invention the OSGi framework will be more specifically described.

The home network system for configuring a digital network in the home is based on a variety of application fields and living environments. Thus several limitations are accompanied when implementing the home network system.

That is in the home network system various electric home appliances including information appliances such as computer printer and fax machine AV appliances such as TV audio video and DVD and control devices such as light door lock air conditioner and washing machine are complexly connected with one another. Further the electric home appliances use different communication media such as power line communication PLC Ethernet Bluetooth and IEEE 1394. Thus in order to ensure reliability and stability of the home network system the home network system should be implemented in such a manner that it can be compatible with all the electric home appliances. In other words the home network system should be implemented independently of the middleware.

Accordingly in the present invention the OSGi framework into which middleware services for accessing various kinds of devices are bundled is loaded on the application server so that smooth communication can be made in the home network environment regardless of hardware network protocol operating system and the like whereby a home network system can be implemented independently of the middleware.

The OSGi is a specification for dynamic installation and execution of new services in home network appliances and provides interworkability between home network middleware such as UPnP Jini and LonTalk so that devices using different forms of middleware can be mutually controlled. Since such an OSGi technique is described in detail in a paper OSGi Service Platform release 2 announced on October of 2001 by the OSGi the detailed description thereof will be omitted.

Meanwhile the controlled device includes a home network middleware module for communicating with the application server and positional information on the application file to be installed. The application files for all the electric home appliances in the home are stored in the file server .

That is when the controlled device is connected with the home network the application server detects through the home network middleware module that the controlled device has been connected extracts the positional information on the application file to be installed from the controlled device through the application loader module and downloads an application file from the file server so as to install the relevant application in accordance with the extracted positional information on the downloaded application file.

The application server includes a UPnP control point CP bundle for controlling UPnP devices an hypertext transfer protocol HTTP web server bundle for downloading an application file from the file server and an application management module for controlling operations of the UPnP CP bundle and the HTTP web server bundle . The UPnP CP bundle and the HTTP web server bundle are bundled into an OSGi framework .

The controlled device includes a UPnP controlled device CD stack for notifying its presence to and receiving commands from the application server and a device description for driving the controlled device . Positional information e.g. uniform resource locator URL information on drivers is stored in the device description .

Here the UPnP corresponds to an extended version of the plug and play concept for connecting a conventional PC and peripheral equipment and is a software technology by which all devices as well as PC peripheral equipment can be configured into a single network without additional settings as soon as they are installed. The UPnP devices may be logically divided into a control point CP corresponding to a client that directly uses the services according to roles in the home network and a controlled device CD corresponding to a device or software capable of communicating with the CP. In such a case the party that first requested the service acts as the CP whereas the other party acts as the CD. The CP searches for UPnP devices on the UPnP network or receives event messages generated when the UPnP devices are newly connected with or disconnected from the network.

That is when the controlled device is connected with the home network the application management module of the application server extracts the positional information on the application file to be installed from the controlled device through the UPnP CP bundle and downloads the application file from the file server through the HTTP web server bundle so as to install the relevant application. A method of causing the application server to perform the application installation and management will be later described in detail with reference to .

In the meantime the application management system may be implemented in the controlled device push mode in addition to an application server pull mode. Hereinafter an application management system implemented in the controlled device push mode will be explained with reference to .

When the controlled device is connected with a home network the application management module of the controlled device controls the application platform service module of the application server and thus installs a new application or continuously manages the installed application. This process will be described in detail as follows.

In a case where it is necessary to install a new application the application management module determines the location where the relevant application will be downloaded and then requests the application platform service module to install the necessary application. In response to this request the application platform service module controls an application loader module to download an application file for the home appliance from a file server and then causes the application for the controlled device to be installed by executing the downloaded application file.

Further in a case where it is necessary to delete or update an already installed application the application management module requests the application platform service module to delete or update the application. In response to this request the application platform service module deletes or updates the relevant application from or in the application server and then notifies the controlled device of the execution result.

An application server includes a UPnP CD bundle for notifying its presence to and receiving commands from a controlled device an HTTP web server bundle for downloading an application file from a file server and an application platform service module for installing and managing the application under the control of the controlled device . Here the UPnP CD bundle and the HTTP web server bundle are bundled into an OSGi framework .

The controlled device includes a UPnP CP stack for transmitting control commands related to application management to the application server and an application management module for controlling a general operation related to application management. A method of managing the application in the controlled device push mode will be later described in detail with reference to .

Hereinafter the method of managing the application according to the present invention will be explained in detail with reference to the accompanying drawings.

First the method of managing the application in the pull mode in which the application server becomes the subject of management and performs the application installation and management will be explained with reference to .

When the controlled device is connected with the home network the UPnP CP bundle in the application server detects that the controlled device has been connected to the home network and then notifies the application management module of the presence of the controlled device through an event mechanism S .

Then the UPnP CP bundle analyzes the device description of the controlled device extracts the positional information e.g. the URL information on the drivers and transmits the extracted information to the application management module S .

Next the application management module controls the HTTP web server bundle and downloads the application file for the controlled device from the file server in accordance with the positional information on the application file input from the UPnP CP bundle S . After the download has been completed the application management module executes the downloaded application file to install the relevant application S .

Thereafter the application management module controls the controlled device in response to the installed application S . For example the application management module can perform operations of using a printout function or turning off an audio in a TV with an application platform service function.

Now the method of managing the application in the push mode in which the controlled device becomes the subject of management and performs the application installation and management will be explained with reference to .

When a controlled device is connected with the home network the UPnP CP stack of the controlled device searches through communication with the UPnP CD bundle of the application server to determine whether the application server with the application platform service module is connected with the home network S .

At this time if the application server with the application platform service module is connected with the home network the UPnP CP stack of the controlled device notifies the application management module of the presence of the application server through the event mechanism.

Then the application management module of the controlled device judges whether a new application should be installed S . If a new application should be installed the application management module determines the download location of the relevant application and requests the application platform service module to install the necessary application S .

Thereafter in response to the requested commands for installing the relevant application the application platform service module controls the HTTP web server bundle and downloads the application file from the file server S . After the download has been completed the application platform service module executes the downloaded application file to install the relevant application .

If the application is installed in the application server according to a control process of the controlled device the application management module of the controlled device controls the controlled device connected with the home network through the installed application S .

On the other hand in a case where it is necessary to delete or update an already installed application the application management module requests the application platform service module to delete or update the relevant application. In response to the request the application platform service module performs the operations of deleting or updating the relevant application and then notifies the controlled device of the execution result S and S .

As described above according to the present invention the application installation and management for the controlled device can be made regardless of the kinds of middleware within the home network environment. Thus the function of controlled device can be dynamically extended through the continual update of applications for the controlled device.

Further both the application server and the controlled device can perform the application installation and management. Thus the application management can be performed more efficiently by using either the application server pull mode to be used for electric home appliances that have poor operation capabilities or need no additional upgrade services or the controlled device push mode to be used for electric home appliances that have good operation capabilities and need various and continuous application upgrade services.

Although the present invention has been described in connection with the preferred embodiments shown in the drawings they are mere examples of the present invention. It will be understood by those skilled in the art that various modifications changes and equivalents thereof can be made within the scope and spirit of the present invention.

For example it has been described in the preferred embodiments that the file server is connected with the application server through the Internet network. However the location where the application files are stored may vary according to the services supported by the application loader module.

Further it has been described in the embodiments that the application for the controlled device is installed when the controlled device is connected. However it can be changed when the application is installed.

Furthermore it has been described in the embodiments that the UPnP is an example of the middleware for communicating between the devices. However the present invention is not limited thereto and middleware such as Jini a common object request broker architecture CORBA and a distributed component object model DCOM may be employed in the present invention.

Moreover in the embodiments of the present invention Java related platforms such as OSGi and JavaBeans and technologies for loading operating systems such as Microsoft Windows and Linux can be employed as the application installation technologies.

Accordingly the true technical scope and spirit of the present invention should be defined by the appended claims.

As described above according to the present invention there is an advantage in that the functions of the electric home appliances can be dynamically extended in the home network environment since an application management system operable independently of the home network middleware can be implemented.

Further according to the present invention the services for continuously updating the application or providing the application suitable to the characteristics of the home network can be provided and the controlled devices can also install new applications or manage already installed applications even though the controlling appliance has been implemented to provide simple functions. Therefore there is also another advantage in that resources can be efficiently utilized.

