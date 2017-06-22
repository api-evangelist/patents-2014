---

title: Distributed fragments file system
abstract: The present invention relates to a distributed storage scheme, wherein every file is optionally encrypted, optionally interleaved, fragmented, and the various fragments stored on different constituent storage systems commensurate with the storage mechanisms supported by those storage providers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09436842&OS=09436842&RS=09436842
owner: 
number: 09436842
owner_city: 
owner_country: 
publication_date: 20140818
---
Conventional distributed computer file systems are known for allowing different subsets of a file system to be on different computer file systems. A given file or a specific replicated instance is stored in its entirety on a single underlying disk or file system.

A conventional file system accessed from a personal computer or a workstation has files that are typically stored entirely on a single hard disk drive or on a cluster of drives in a scheme called Redundant Array of Independent Disks RAID . Both types of file systems are prone to data loss and security vulnerabilities due to the following reasons 

Similarly conventional systems that utilize cloud services for storage tend to store related application data with a single cloud service provider. This approach suffers from the same security vulnerability because a potential intruder only needs to be able to breach the information security barriers of that cloud provider.

Use of a single cloud service provider for storage of all data also heightens the risk of loss of access whenever there s an outage at that provider and a commonly used approach against a single provider outage involves replicating data across multiple cloud providers. Replication not only increases storage costs but also increases the number of attack vectors by allowing a potential intruder access to data by breaching any one of the providers.

Considering the limitations described above it is desirable to provide an improved storage scheme having reduced storage requirements as well as improved security and fault tolerance.

The present invention relates to a distributed storage scheme for computer data referred to as Distributed Fragments Storage System DFSS . DFSS uses N N 1 potentially heterogeneous storage systems which may be a combination of file systems or cloud storage providers for creating a unified and if desired physically distributed file system. In one embodiment of this invention every file is encrypted interleaved and broken into N fragments and the respective fragments are stored on different constituent storage systems. This is in contrast to conventional distributed file systems where different groups of files may be on different file systems but a given file or its replicated instance is stored in its entirety on a single underlying disk or file system. The creation and distribution of file fragments of each file in the present invention as opposed to distribution of entire files provides the following advantages 

1. Intrinsic security DFSS improves security as a given file is not found in its entirety on any specific storage system but is optionally encrypted optionally interleaved fragmented and dispersed across one or more N potentially heterogeneous storage systems such as file systems or cloud storage providers .

2. Fault tolerance The distributed storage scheme supports storage redundancy that tolerates one or more faults in the constituent storage systems. Redundancy is achieved without replicating file data but through use of suitable block FEC codes. File access remains uninterrupted and potential failures of one or more constituent storage systems are transparent to the users of DFSS.

3. Reduced storage requirements Instead of full replication of files that are distributed across N storage systems implying a storage expansion factor of N DFSS employs a scheme with an N N 1 storage expansion factor where N is the number of constituent storage systems. Storage redundancy overhead necessary to tolerate for example loss of a single storage system decreases as the number of storage systems increases. For example when N is 3 the storage expansion factor is 1.5. When N is 4 the storage expansion factor is only 1.33. Both those cases compare very favorably with the respective expansion factors of 3 and 4 for conventional storage schemes.

4. Use of heterogeneous storage systems with no stringent timing synchronization requirements or similarity of lower level parameters such as block sizes allows these systems to be geographically distributed.

DFSS is broadly applicable but is especially useful when storing data at facilities such as cloud storage providers that are not controlled or maintained by the creator or owner of the data. Users of DFSS in one embodiment can purposely utilize multiple heterogeneous cloud storage providers to create a customized and virtualized cloud storage system with the following security advantages 

In one embodiment the interleaving and fragmentation are performed after encrypting the file. In another embodiment interleaving and fragmentation are done first while encryption is applied to the resulting fragments. In either embodiment when N 1 security is enhanced because theft of a data fragment from any of the constituent storage systems does not result in the loss of any information because access to other fragments residing at other cloud providers or constituent file systems is essential for reconstructing the original file. Any potential service interruptions at a cloud service provider are transparent and non disruptive as well.

DFSS does not require replication of data for tolerating failures of the constituent storage systems. This translates into lower expenses compared to traditional replication based storage systems.

Reference will now be made in greater detail to a preferred embodiment of the invention an example of which is illustrated in the accompanying drawings. Wherever possible the same reference numerals will be used throughout the drawings and the description to refer to the same or like parts.

1. N is the number of constituent file systems each capable of hosting a conventional file system structure comprised of directories and files. A subset of PFSthrough PFSmay also be possibly heterogeneous cloud service providers that are based on Object Storage instead of file storage.

3. A file in VFS is denoted as F and it is fragmented and respective fragments are stored as file fragments F F. . . Fin the underlying file systems designated PFS PFS. . . PFS respectively. Under this scheme fragment Fis a valid file under physical file system PFS fragment Fis a valid file stored at PFS and so on. If object storage is used the respective fragments are stored as objects.

4. A virtual file system controller VFC is a master controller which maintains and controls the virtual file system VFS .

5. End user PCs and workstations communicate with the virtual file system controller VFC and mount virtual file system VFS using conventional protocols such as Network File System NFS or CIFS. The VFC in turn uses protocols specific to each of the file systems or cloud service providers in a manner transparent to the end user PCs and workstations. PFS PFS . . . PFScan each employ one of a myriad of different file system protocols such as NFS iSCSI SMB or HTTP HTTPS REST based cloud object storage or other protocol and storage mechanisms known in the art in accordance with the teachings of the present invention.

6. The virtual file system controller VFC supports conventional file operations such as open close read write delete and stat .

7. The virtual file system controller VFC also supports directory operations such as mkdir list and rmdir .

8. The virtual file system controller VFC uses local dedicated storage for its own operations and optionally for caching of frequently used files. It relies primarily on PFS. . . PFSfor actual storage of data.

PFS PFS and virtual file controller VFC are on Local Area Network LAN . PFS . . . PFS 1 are in possibly geographically dispersed areas connected via network . Network can be the internet or a private IP network. PFS and PFS are used as examples to show flexibility of placement of file systems. It will be appreciated that PFS and PFS do not need to be local.

Virtual file system VFS in this embodiment is shown hosting a directory structure comprised of the root directory sub directories D and D and files F . . . F . The example directory structure is not intended to imply limitations in the number of files directory structure depth or file sizes. DFSS scales to support extremely large file systems with directory depth levels and the number of files only limited by the amount of storage available across the constituent file systems.

Personal computer PC mounts Virtual File System VFS from virtual file system controller VFC using a drive mapping Y for e.g. and protocol . For example Virtual File Controller VFC can use one of the standard protocols such as NFS or CIFS for the drive mapping. Workstation mounts virtual file system VFS from virtual file system controller VFC using protocol . For example workstation can be a UNIX workstation. Personal computer PC and workstation mount root directory structure .

Virtual file system controller VFC includes local cache which optionally utilizes a Least Recently Used LRU scheme for management of the overall cache. It will be appreciated that other cache management schemes known in the art can be used in accordance with the teachings of the present invention. Subdirectories and files are available to both personal computer PC and workstation . Subdirectories and files shown for this embodiment have paths D F D F D F and D F.

In block encrypted bytes of file F are interleaved and optionally subject to Forward Error Correction FEC coding as described below to create N fragments denoted F F . . . F which may not necessarily be equal sized but preferred embodiment assumes are equal sized. In block each file fragment is optionally encrypted with a separate key.

In block each file fragment is transmitted to its corresponding storage system PFS for storage using its respective storage protocol. File fragment Fis stored on PFSin the directory specified by the full pathname of the file if file system based or using a globally unique identifier if object based. In block virtual file system controller VFC optionally also stores an encrypted version of the original file in local cache for fast response to future read requests from other clients. If the cache is full the LRU scheme is used for freeing up storage in the cache.

In block file fragment meta information about file F is stored in local cache of virtual file system controller VFC . For example file fragment meta information can include information about the file system PFS instances that store the fragments of the file the order of distribution of fragments across storage systems whether FEC was used access permissions creation modification times of the original file and creation times of the respective fragments. File fragment meta information can also include the size of the file and the key K used for the encryption of the overall file. Storage of other types of information in the meta headers is not precluded.

In another embodiment no VFC is required and meta information itself is stored as fragments using a recursive application of the present invention across the same or different set of storage systems.

In block each file fragment F F. . . F is separately decrypted if encrypted during the storage process. In block each file fragment F F . . . F is processed through a de interleaver and optionally decoded using FEC techniques as described below. The result is file F . In block file F is decrypted using the inverse of the encryption function used during the storage process. The decryption key K is obtained from the meta file associated with file F . The virtual file system controller VFC responds to the requesting client with the decrypted contents of file F.

An example interleaver is shown in . Byte interleaver array of R rows and C columns . Wherein R is a fixed number of the form 2 1 where m is typically 4 7 but higher values are not precluded. C is max N S R 1 R where S is the size of the file. If FEC support is desired for fault tolerance against failures of one or more constituent file systems then the last K rows of the interleaver array contain encoded bytes that are computed using block FEC encoders. Otherwise the last K rows contain normal file data. The FEC encoding and decoding process along with calculation of K are described later.

During interleaving the bytes of the file are stored column first in byte interleaver array . Bytes are stored in column 0 starting at row 0 and all rows except the last K rows if FEC is enabled are filled. If FEC is not used last K rows contain regular data. Once column 0 is filled the process is repeated for the remaining C 1 columns. Zero padding is used to fill out a partially filled array.

It will be appreciated that other interleaving and de interleaving processes known in the art can be used in accordance with the teachings of the present invention. Rows of interleaver array are assigned to N different file fragments in a round robin fashion. Row q is assigned to fragment number q mod N and so on. Thus row 0 maps to fragment 0 row N 1 to fragment N 1 row N to fragment 0 row N 1 to fragment 1 and so on. All fragments that map to the same PFS instance are stored in a single file on that instance.

If N is small the number of rows can be increased to be a multiple m of N resulting in m N rows. Each storage system PFS receives m rows from the interleaver table.

For the de interleaving process file bytes received in file fragments are stored row wise and read out column wise. A file fragment received from a file system PFSi is unpacked and consecutive sets of C the number of columns in the de interleaver array bytes are stored at row indices i i N i 2 N . . . respectively. It will be appreciated that other fragmenting and unpacking of file fragment processes known in the art can be used in accordance with the teachings of the present invention.

In an alternate embodiment file interleaving can be performed when error correction support is enabled for tolerating failures or loss of access to one of the underlying constituent physical file systems PFS . When storing the original bytes of the file in interleaver array only K rows of each column are filled. The remainder R K rows of each column are filled with the parity bytes computed using a suitable erasure code such as for example Reed Solomon.

Erasure encoding is done column wise. The first K rows of every column contain actual file data and provide input of information bytes to the erasure encoding process which generates R K parity bytes for every column.

All R rows of interleaver array act as the source of data put into fragments stored on a plurality of storage systems PFS . It will be appreciated that other erasure processes known in the art can be used in accordance with the teachings of the present invention.

File de interleaving can be performed when error correction support is enabled. File fragments received from various file systems PFS are unpacked and bytes written to de interleaver array as described above. In addition all R rows corresponding to a file fragment that is not received from a physical file system PFS are marked for erasure. Once all R rows are filled erasure decoding is done column wise using the converse of the erasure encoding process described above. A row marked for erasure results in a single erasure byte in every column. Use of sufficient parity bytes R K per column ensures missing bytes such as from a fragment not received from a storage system are recreated. Only the first K rows of de interleaver array are used for recreating the original file i.e. the parity bytes are discarded once the erasure decoding process is run on each column.

It is to be understood that the above described embodiments are illustrative of only a few of the many possible specific embodiments which can represent applications of the principles of the invention. Numerous and varied other arrangements can be readily devised in accordance with these principles by those skilled in the art without departing from the spirit and scope of the invention.

