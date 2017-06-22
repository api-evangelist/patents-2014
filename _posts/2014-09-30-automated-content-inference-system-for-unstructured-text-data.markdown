---

title: Automated content inference system for unstructured text data
abstract: An apparatus comprises a processing platform configured to implement an automated content inference system for unstructured text data. The automated content inference system comprises a data indexer, a dictionary generator, a topic model generator, and a visualization generator. The data indexer is configured to process the unstructured text data to construct a term index for a given document. The dictionary generator is configured to process the term index to construct an in-domain dictionary. The topic model generator is configured to process the in-domain dictionary to construct a topic model. The visualization generator is configured to provide an output display showing assignment of one or more topics to the given document based on the topic model. The unstructured text data illustratively comprises unstructured service request summaries from a service events database. The unstructured service request summaries may comprise problem summaries and corresponding solution summaries relating to respective service events.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09378200&OS=09378200&RS=09378200
owner: EMC Corporation
number: 09378200
owner_city: Hopkinton
owner_country: US
publication_date: 20140930
---
The field relates generally to information processing systems and more particularly to processing of unstructured text data.

In many information processing systems service event analysis relies heavily on inefficient manual activities. For example it is common in some systems for service personnel to be required to complete forms describing problems experienced by customers and the manner in which these problems were resolved. These forms often utilize static sets of predetermined problem and resolution codes that in the interest of convenience to the service personnel tend to be overly general and vague.

Supplementary unstructured text data added to such forms is often ignored as it requires special treatment. For example the unstructured text data may require manual screening in which a corpus of unstructured text data is reviewed and sampled by service personnel. Alternatively the unstructured text data may require manual customization and maintenance of a large set of rules that can be used to determine correspondence with predefined themes of interest. Such processing is unduly tedious and time consuming particularly for large volumes of unstructured text data.

Illustrative embodiments of the present invention provide automated content inference systems that can process unstructured text data from a service events database in a particularly efficient manner.

In one embodiment an apparatus comprises a processing platform configured to implement an automated content inference system for unstructured text data of one or more documents obtained from a service events database.

The automated content inference system comprises a data indexer a dictionary generator a topic model generator and a visualization generator. The data indexer is configured to process the unstructured text data to construct a term index for a given document. The dictionary generator is configured to process the term index to construct an in domain dictionary. The topic model generator is configured to process the in domain dictionary to construct a topic model. The visualization generator is configured to provide an output display showing assignment of one or more topics to the given document based on the topic model.

The unstructured text data in some embodiments illustratively comprises unstructured service request summaries from a service events database. For example the unstructured service request summaries may comprise problem summaries and corresponding solution summaries relating to respective service events.

The illustrative embodiments provide a number of significant advantages relative to the conventional arrangements described previously. For example these embodiments avoid the need for manual screening in which a corpus of unstructured text data is reviewed and sampled by service personnel.

Moreover the automated content inference systems in the illustrative embodiments are data driven in that relevant topics are elevated automatically from the actual unstructured text data itself rather than determined by attempting to impose a limited set of predefined themes on the unstructured text data. As a result there is no need for manual customization and maintenance of a large set of rules that can be used to determine correspondence with predefined themes of interest. For example the illustrative embodiments do not require rule updates to accommodate previously unseen terms appearing in unstructured text data.

In addition automated content inference systems as disclosed herein can provide significant insights into unstructured text data in a very short period of time. Particular studies can be configured and executed quickly with large quantities of analysis output being available almost immediately. Also such studies can be easily reconfigured and repeated as needed using different sets of parameters.

Embodiments of the invention include without limitation apparatus systems methods and articles of manufacture comprising processor readable storage media.

Illustrative embodiments of the present invention will be described herein with reference to exemplary information processing systems and associated processing platforms each comprising one or more processing devices. It is to be appreciated however that the invention is not restricted to use with the particular illustrative system platform and device configurations shown. Accordingly the term information processing system as used herein is intended to be broadly construed so as to encompass for example processing systems comprising private or public cloud computing or storage systems as well as other types of processing systems comprising physical or virtual processing resources in any combination.

The information processing system in this embodiment illustratively comprises a plurality of servers . . . S and an automated content inference system all of which are coupled to and communicate over a network . The content inference system is separated into a plurality of functional modules including a preprocessing module a clustering module and a visualization module .

The content inference system is coupled to a service events database . The service events database stores unstructured text data in the form of multiple documents each relating to one or more service events arising within the system or within associated systems not explicitly shown. The service events database illustratively comprises one or more storage disks storage arrays electronic memories or other types of memory in any combination. Although shown as separate from the content inference system in the service events database in other embodiments can be at least partially incorporated within the content inference system or within one or more other system components.

The documents stored in the service events database need not be in any particular format or formats but generally comprise unstructured text data possibly in combination with other types of data such as structured text data. Moreover a given set of documents subject to processing in embodiments of the invention can illustratively include documents of a variety of different formats. The term document as used herein is therefore intended to be broadly construed.

In the present embodiment the content inference system and the service events database are associated with a data management system . The content inference system can communicate directly with the service events database and the data management system and additionally or alternatively can communicate with these system components via the network .

The content inference system more particularly comprises a data indexer and a dictionary generator both implemented in the preprocessing module a topic model generator implemented in the clustering module and a visualization generator implemented in the visualization module .

The data indexer is configured to process unstructured text data of one or more documents obtained from the service events database in order to construct a term index for a given document. The unstructured text data illustratively comprises unstructured service request summaries such as problem summaries and corresponding solution summaries relating to service events. In some embodiments the unstructured text data has structured data associated therewith in the service events database and the term index is based on both the unstructured text data and the associated structured data. Examples of structured data include indications of region team etc.

The dictionary generator is configured to process the term index generated by the data indexer in order to construct an in domain dictionary. In this context the term in domain refers to a domain comprising specified unstructured text data of one or more documents although other types of domains can be used in other embodiments. The dictionary generator in the present embodiment is illustratively configured to implement automatic lemmatization and synonym extraction but in other embodiments different types of dictionary generators may be used.

Additional details regarding exemplary dictionary generation techniques that may be utilized in embodiments of the present invention can be found in R. Cohen Towards Understanding of Medical Hebrew Dissertation Ben Gurion University of the Negev 2012 P. F. Brown et al. Class based n gram models of natural language Computational Linguistics 18.4 1992 467 479 and S. Banerjee et al. The design implementation and use of the ngram statistics package Computational Linguistics and Intelligent Text Processing 2003 370 381 which are incorporated by reference herein.

The topic model generator is configured to process the in domain dictionary in order to construct a topic model. In the present embodiment it is assumed that the topic model generator in generating the topic model utilizes latent Dirichlet allocation LDA with asymmetric priors although other techniques can be used including for example probabilistic latent semantic analysis pLSA canonical correlation analysis CCA or combinations of these and other topic modeling algorithms. As will be described in more detail below in conjunction with the user interface of the topic model generator provides lists of topics at least a subset of which are elevated as respective sets of related terms from the unstructured text data.

Examples of topic modeling algorithms suitable for use in embodiments of the present invention are disclosed in for example R. Cohen et al. Redundancy in electronic health record corpora analysis impact on text mining performance and mitigation strategies BMC Bioinformatics 2013 14 10 D. M. Blei et al. Latent dirichlet allocation The Journal of Machine Learning Research 2003 3 993 1022 A. K. McCallum Mallet A machine learning for language toolkit 2002 and H. Wallach et al. Rethinking LDA Why priors matter Advances in Neural Information Processing Systems 2009 22 1973 1981 which are incorporated by reference herein.

The visualization generator is configured to provide an output display showing assignment of one or more topics to the given document based on the topic model. The output display illustratively comprises one of a plurality of user interface displays that are generated under the control of the visualization module and presented on a display screen of a user device not explicitly shown in . For example such a user device may comprise a computer mobile telephone or other type of processing device adapted for communication with the content inference system over the network .

The service events database may be updated to indicate the assignment of one or more topics to the given document. Such a topic assignment is an example of what is more generally referred to herein as a content inference. 

The automated content inference system is advantageously data driven in that relevant topics are elevated automatically from the actual unstructured text data itself rather than determined by attempting to impose a limited set of predefined themes on the unstructured text data. This provides significant improvements in unstructured text data analysis and visualization relative to the conventional approaches previously described. For example resulting topic distributions and associated visualizations can be used to identify sets of documents sharing semantic similarity.

The content inference system considerably facilitates text data exploration in large volumes of unstructured text data and in particular the problem and resolution summaries that are common to service requests. It enables analysts to quickly obtain content inferences from multiple sets of unstructured text data.

The content inference system in the illustrative embodiments does not characterize individual system users but instead models unstructured text data of one or more documents from the service events database . By way of example such an arrangement allows particularly efficient analysis and visualization of overall customer interactions with a corporate or enterprise support organization.

The content inference system in some embodiments is implemented as part of an analysis and visualization tool for unstructured text data analysis and visualization. Such a tool can be associated with the service events database the data management system or another system component. By way of example the user interface of can be generated by a tool of this type.

It is to be appreciated that the particular arrangement of system components illustrated in is exemplary only and that numerous other arrangements of components may be used in other embodiments. For example in other embodiments functionality described herein as being associated with one or more of the data indexer dictionary generator topic model generator and visualization generator may be implemented at least in part using additional or alternative components of the system .

The content inference system and possibly other related components of system such as the service events database are assumed in the present embodiment to be implemented on a given processing platform using at least one processing device comprising a processor coupled to a memory.

The processor may comprise a microprocessor a microcontroller an application specific integrated circuit ASIC a field programmable gate array FPGA or other type of processing circuitry as well as portions or combinations of such circuitry elements.

The memory may comprise random access memory RAM read only memory ROM or other types of memory in any combination. These and other memories disclosed herein may be viewed as examples of what are more generally referred to as processor readable storage media storing executable computer program code or other types of software programs.

Articles of manufacture comprising such processor readable storage media are considered embodiments of the present invention. A given such article of manufacture may comprise for example a storage device such as a storage disk a storage array or an integrated circuit containing electronic memory. The term article of manufacture as used herein should be understood to exclude transitory propagating signals.

The one or more processing devices implementing the content inference system and possibly other components of system may each further include a network interface that allows such components to communicate with one another over one or more networks. For example a given such network interface illustratively comprises network interface circuitry that allows at least one of the data indexer dictionary generator topic model generator and visualization generator to communicate over a network with other components of the system such as servers service events database and data management system . Such network interface circuitry may comprise for example one or more conventional transceivers.

The above noted network may comprise for example a global computer network such as the Internet a wide area network WAN a local area network LAN a satellite network a telephone or cable network a cellular network a wireless network such as a WiFi network or a WiMAX network or various portions or combinations of these and other types of networks.

At least a portion of the content inference system and possibly other system components may comprise software that is stored in a memory and executed by a processor of at least one processing device.

Processing devices comprising processors memories and network interfaces as described above are illustratively part of a processing platform comprising physical and virtual resources in any combination. Additional examples of such processing platforms that may be used to implement at least portions of the system will be described in more detail below in conjunction with .

Again it should be understood that the particular sets of components implemented in the information processing system as illustrated in are presented by way of example only. In other embodiments only subsets of these components or additional or alternative sets of components may be used and such components may exhibit alternative functionality and configurations.

The operation of the information processing system will now be further described with reference to the flow diagram of which illustrates an exemplary process carried out by the system in one embodiment. The process as shown includes steps through . Steps through are assumed to be performed by the content inference system but one or more of these steps may be performed at least in part by or in conjunction with other system components in other embodiments. Moreover automated content inference functionality as disclosed herein should not be viewed as being limited in any way to this particular illustrative arrangement of process steps.

In step unstructured text data of one or more documents is obtained by the content inference system from the service events database .

In step a term index is constructed for a given document based on the unstructured text data. The term index may be in the form of a document term matrix or in another suitable format. As noted above associated structured data may also be taken into account in generating the term index.

In step an in domain dictionary is constructed based on the term index. As mentioned previously the in domain dictionary is assumed to be constructed using automatic lemmatization and synonym extraction.

Steps and in the present embodiment are considered examples of preprocessing steps performed by the respective data indexer and dictionary generator of the preprocessing module .

In step a topic model is constructed based on the in domain dictionary using LDA with asymmetric priors. Additionally or alternatively one or more other topic modeling algorithms such as pLSA or CCA may be used.

Steps and in the present embodiment are considered examples of clustering steps performed by the clustering module . The topic model referred to in step is constructed by the topic model generator of the clustering module .

In step the service events database is updated to indicate the one or more topics assigned to the given document.

Steps through can be repeated periodically or as needed to process additional documents comprising unstructured text data from the service events database .

Also labels can be assigned to respective clusters of documents possibly utilizing a cluster labeling system incorporated in or otherwise associated with the content inference system . Furthermore additional analysis or other processing can be performed on labeled clusters of documents.

The particular processing operations and other system functionality described in conjunction with the flow diagram of are presented by way of illustrative example only and should not be construed as limiting the scope of the invention in any way. Alternative embodiments can use other types of processing operations for implementing an automated content inference system or portions thereof. For example the ordering of the process steps may be varied in other embodiments or certain steps may be performed concurrently with one another rather than serially.

It is to be appreciated that automated content inference functionality such as that described in conjunction with the flow diagram of can be implemented at least in part in the form of one or more software programs stored in memory and executed by a processor of a processing device such as a computer or a virtual machine. As mentioned previously a memory or other storage device having such program code embodied therein is an example of what is more generally referred to herein as a processor readable storage medium. 

As mentioned previously the configuration of information processing system is exemplary only and numerous other system configurations can be used in implementing an automated content inference system as disclosed herein.

The application portion comprises a set of Linux based servers illustratively implemented using virtual machines. These include a Linux based server that performs language processing using Java Python Natural Language Toolkit NLTK and Mallet. The server interacts with the analytics system via Java DataBase Connectivity JDBC and receives data subsets therefrom as illustrated.

The front end portion comprises a web server also illustratively implemented using one or more virtual machines and includes a user interface providing visualizations of the type described elsewhere herein. The web server communicates with the server via Flask and a RESTful API as illustrated and may additionally or alternatively communicate with one or more other servers of the application portion via additional connections shown by a dashed arrow in the figure.

The various portions of system are adapted in the present embodiment to implement the functionality of the content inference system as previously described. This particular system configuration is only an example and numerous other arrangements of system components can be used to provide that functionality.

Referring now to an exemplary user interface display generated by the content inference system is shown. The same user interface display is shown in each of these figures but features of different portions of the user interface display are highlighted in . The user interface display is assumed to be one of a plurality of different user interface displays that are generated by the content inference system possibly in conjunction with an associated analysis and visualization tool.

As illustrated in the user interface display includes a control panel a console log and a data exploration panel .

It should be understood that the particular user interface displays and other output displays illustrated in are presented by way of example only and should not be construed as limiting the scope or functionality of the content inference system in any way.

The illustrative embodiments provide a number of significant advantages relative to the conventional arrangements described above. For example these embodiments provide automated content inference systems for unstructured text data.

As indicated previously the automated content inference systems in the illustrative embodiments are data driven in that relevant topics are elevated automatically from the actual unstructured text data itself rather than determined by attempting to impose a limited set of predefined themes on the unstructured text data.

The illustrative embodiments therefore advantageously avoid the need for manual screening in which a corpus of unstructured text data is reviewed and sampled by service personnel.

Furthermore there is no need for manual customization and maintenance of a large set of rules that can be used to determine correspondence with predefined themes of interest. For example the illustrative embodiments do not require rule updates to accommodate previously unseen terms appearing in unstructured text data.

In addition automated content inference systems as disclosed herein can provide significant insights into unstructured text data in a very short period of time. Particular studies can be configured and executed quickly with large quantities of analysis output being available almost immediately. Also such studies can be easily reconfigured and repeated as needed using different sets of parameters.

It is to be appreciated that the foregoing advantages are illustrative of advantages provided in certain embodiments and need not be present in other embodiments.

It was noted above that portions of the information processing system may be implemented using one or more processing platforms. Illustrative embodiments of such platforms will now be described in greater detail. Although described in the context of system these processing platforms may also be used to implement at least portions of other information processing systems in other embodiments of the invention such as the information processing system of .

As shown in portions of the information processing system may comprise cloud infrastructure . The cloud infrastructure comprises virtual machines VMs . . . M implemented using a hypervisor . The hypervisor runs on physical infrastructure . The cloud infrastructure further comprises sets of applications . . . M running on respective ones of the virtual machines . . . M under the control of the hypervisor .

Although only a single hypervisor is shown in the embodiment of the system may of course include multiple hypervisors each providing a set of virtual machines using at least one underlying physical machine. For example different sets of virtual machines provided by respective ones of multiple hypervisors may be utilized in configuring multiple instances of preprocessing module clustering module visualization module or other components of the system .

An example of a commercially available hypervisor platform that may be used to implement hypervisor and possibly other portions of the information processing system in one or more embodiments of the invention is the VMware vSphere which may have an associated virtual infrastructure management system such as the VMware vCenter . The underlying physical machines may comprise one or more distributed processing platforms that include storage products such as VNX and Symmetrix VMAX both commercially available from EMC Corporation of Hopkinton Mass. A variety of other storage products may be utilized to implement at least a portion of the system .

One or more of the processing modules or other components of system may therefore each run on a computer server storage device or other processing platform element. A given such element may be viewed as an example of what is more generally referred to herein as a processing device. The cloud infrastructure shown in may represent at least a portion of one processing platform. Another example of such a processing platform is processing platform shown in .

The processing platform in this embodiment comprises a portion of system and includes a plurality of processing devices denoted . . . N which communicate with one another over a network .

The network may comprise any type of network including by way of example a global computer network such as the Internet a WAN a LAN a satellite network a telephone or cable network a cellular network a wireless network such as a WiFi or WiMAX network or various portions or combinations of these and other types of networks.

The processor may comprise a microprocessor a microcontroller an ASIC an FPGA or other type of processing circuitry as well as portions or combinations of such circuitry elements.

The memory may comprise RAM ROM or other types of memory in any combination. As mentioned previously the memory and other memories disclosed herein should be viewed as illustrative examples of what are more generally referred to as processor readable storage media storing executable program code of one or more software programs and articles of manufacture comprising such processor readable storage media are considered embodiments of the present invention.

Also included in the processing device is network interface circuitry which is used to interface the processing device with the network and other system components and may comprise conventional transceivers.

The other processing devices of the processing platform are assumed to be configured in a manner similar to that shown for processing device in the figure.

Again the particular processing platform shown in the figure is presented by way of example only and system may include additional or alternative processing platforms as well as numerous distinct processing platforms in any combination with each such platform comprising one or more computers servers storage devices or other processing devices.

It should therefore be understood that in other embodiments different arrangements of additional or alternative elements may be used. At least a subset of these elements may be collectively implemented on a common processing platform or each such element may be implemented on a separate processing platform.

Also numerous other arrangements of computers servers storage devices or other components are possible in the information processing system . Such components can communicate with other elements of the information processing system over any type of network or other communication media.

It should again be emphasized that the above described embodiments of the invention are presented for purposes of illustration only. Many variations may be made in the particular arrangements shown and described. For example although described in the context of particular system and device configurations the techniques are applicable to a wide variety of other types of information processing systems processing devices and other components. In addition the particular modules processing operations and other exemplary features of the illustrative embodiments may be varied to meet the needs of other implementations. Moreover it should be understood that the various assumptions made above in describing illustrative embodiments need not apply in other embodiments. Numerous other embodiments within the scope of the appended claims will be readily apparent to those skilled in the art.

