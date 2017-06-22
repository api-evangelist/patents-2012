---

title: Encrypting files within a cloud computing environment
abstract: A system, computer readable medium and a method for encrypting a file, the method may include retrieving the file from a storage service; segmenting the file into multiple file segments; calculating a file segment signature for each of the multiple file segments to provide multiple file segment signatures; encrypting each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that are in response to the multiple file segment signatures; wherein the multiple encrypted file segments form an encrypted file; and sending the multiple encrypted file segments to the storage service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09262643&OS=09262643&RS=09262643
owner: SOOKASA INC.
number: 09262643
owner_city: Mountain View
owner_country: US
publication_date: 20121226
---
This application claims priority from U.S. provisional patent Ser. No. 61 603 910 filing date Feb. 27 2012 this application is a continuation in part of U.S. patent application Ser. No. 13 031 628 filing date Feb. 22 2011 which in turn claims priority from U.S. provisional patent Ser. No. 61 306 578 filing date Feb. 22 2010 all patent applications are incorporated herein by reference.

The advances and reduced costs of network connected mobile devices in recent years have brought a dramatic change in user behavior. The typical user owns multiple personal devices ranging from desktop and laptop computers notebooks tablets smart phones and electronic books. Consequently there is a growing need to share data among devices as well as to guarantee its availability despite the fact that devices may be turned off disconnected and replaced. The penetration of such technology is rapidly increasing in organizations of all sizes. As a result users are mixing enterprise files documents and applications together with their personal media.

To this end the use of cloud based storage for sharing information between different devices and also among group of users has become a standard. Many consumer commercial offerings such as Dropbox Box iCloud Google Drive and Sugarsync have gained widespread user popularity.

These services offer cloud based storage that is connected to the devices through apps or through a browser interface. The apps present to the user a directory structure of files organized in folders similar to the appearance of native application such as MS Explorer. In certain operating systems Windows Apple OS X the folder are accessed via the native file browser application. The folders on the device are synchronized with the storage on the cloud and therefore maintain a coherent file and directory state and view across all devices. In certain cases e.g. Sugarsync the files are uploaded to the cloud but are not necessarily automatically synchronized to all devices.

In addition to the web storage services there is a parallel trend of uploading unstructured data in particular company documents to SaaS Software as a Service services. New cloud based enterprise application such as Salesforce.com Success Factors and Box and consumer based applications such as Google Docs and Gmail are essentially independent document repositories. These new services have caused a major migration of documents from the corporate storage to web based SaaS.

According to an embodiment of the invention there may be provided a method for encrypting a file the method may include retrieving the file from a storage service segmenting the file into multiple file segments calculating a file segment signature for each of the multiple file segments to provide multiple file segment signatures encrypting each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that are in response to the multiple file segment signatures wherein the multiple encrypted file segments form an encrypted file and sending the multiple encrypted file segments to the storage service.

The method may include calculating each encryption key in response to a file segment signature associated with a file segment that is encrypted by the encryption key.

The method may include associating with the multiple encrypted file segments the multiple file segment signatures.

The method may include flagging the encrypted file as being encrypted by altering a file type of the encrypted file.

The method may include exposing the encrypted file to a user of the management server through an interface of the storage service.

The method may include preventing the segmenting the calculating and the encrypting of the file if the file has been modified by a user of the storage service during a predetermined period from a moment of the retrieving of the file by the management server.

The method may include preventing the deletion of the file if the file has been modified by a user of the storage service during a predetermined period from a moment of the retrieving of the file.

The segmenting may include finding initial file segments by applying a first segmentation process and defining each file segment as may include multiple initial file segments.

The finding of the initial file segments may include applying at least one process out of Rabin fingerprint process and cyclic redundancy code CRC process.

The segmenting of the file into multiple file segments is executed independent of a file segmentation scheme applied on the file by the storage service.

The segmenting of the file to multiple file segments is executed independent of a file segmentation scheme applied on the file by the storage service for de duplication purposes.

The file is associated with a certain user wherein the method may include using different segmentation parameters for segmenting another file that is associated with another user that differs from the certain user.

The file is associated with a certain user wherein the method may include using different encryption parameters for encrypting another file that is associated with another user that differs from the certain user.

The file is associated with a user of certain group of users wherein the method may include using different segmentation parameters for segmenting another file that is associated with another user that belongs to another group of users.

The file is associated with a user of certain group of user wherein the method may include using different encryption parameters for segmenting another file that is associated with another user that belongs to another group of users.

The method may include adding a user identifier to each file segment wherein the user identifier identifies a user associated with the file.

The method may include retrieving the file from the storage service wherein the file is stored in a storage entity in an encrypted form and is decrypted by the storage service to be provided in a decrypted form to the management server wherein the encrypting by the management server is executed independent of a decryption applied by the storage service.

The method may include retrieving the file from the storage service wherein the storage service applies a first de duplication policy wherein the segmenting of the file by the file management server is executed while a applying a second de duplication policy that is defined independent of the first de duplication policy.

The method may include retrieving the file from the storage service wherein the storage service applies a first de duplication policy wherein the segmenting of the file by the file management server is executed while a applying a second de duplication policy that is in response to the first de duplication policy.

The method may include retrieving the file from the storage service wherein the storage service applies a first de duplication policy wherein the segmenting of the file by the file management server is executed while a applying a second de duplication policy that differs from the first de duplication policy.

The method wherein at least one of the management server and the storage service belong to a cloud computing environment.

The method may include retrieving the file from a dedicated folder that is allocated for files to be encrypted.

The method may include creating a new folder for files to be encrypted wherein the folder is exposed to the user.

The method may include retrieving the file from a dedicated folder that is allocated to files to be encrypted.

The method may include changing a type of a file to a type that is indicative of the encryption of the file.

The method may include sending the file to a cache memory before starting the segmenting the calculating and the encrypting actions.

There may be provided a method for decrypting an encrypted file the method may include receiving a request by a management server to provide at least one encryption key for decrypting at least one encrypted file segment of the encrypted file by a user device after the management server generated the encrypted file to be of a specific file type and after a storage service stored the encrypted file wherein the request may include a file segment signature determining by the management server whether the user device is authorized to decrypt the at least one encrypted file segment and sending the at least one encryption key to the user device if it is determined that the user device is authorized to decrypt the at least one encrypted file segment.

The at least one encryption key may be generated in response to a content of at the least one encrypted file segment.

The method may include receiving the request from an application that is regarded by the operating system hosted by the user device to be associated with files of the certain file type.

The method wherein at least one of the management server and the storage service belong to a cloud computing environment.

There may be provided a method for decrypting an encrypted file the method may include retrieving by a user device of one or more file segment signatures associated with one or more encrypted file segments of an encrypted file wherein each file segment signature is mapped to a decryption key that facilitates a decryption of the encrypted file segment comparing the multiple file segment signatures to a data structure of file segment signatures that may be mapped to decryption keys that may be stored at the user device to find at least zero decryption keys not stored in the user device requesting from a management server at least zero decryption keys that are not stored in the user device receiving by the user device at least one zero encryption keys that are not stored in the user device and decrypting the multiple encrypted file segments wherein each encrypted file segment is decrypted using a decryption key that facilitates the decryption of the encrypted file segment.

The decryption key to be used for decrypting a certain file segment may be calculated based upon a file segment signature and its metadata field associated with the certain file segment.

Additional embodiments of the invention include a non transitory computer readable medium that may stores instructions that may cause a system to execute any or all of the methods described above including any stages and any combinations of same.

The non transitory computer readable medium may store instructions for retrieving the file from a storage service segmenting the file into multiple file segments calculating a file segment signature for each of the multiple file segments to provide multiple file segment signatures encrypting each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that may be in response to the multiple file segment signatures wherein the multiple encrypted file segments form an encrypted file and sending the multiple encrypted file segments to the storage service.

The non transitory computer readable medium may store instructions for receiving a request by a management server to provide at least one decryption key for decrypting at least one encrypted file segment of the encrypted file by a user device after the management server generated the encrypted file to be of a certain file type and after a storage service stored the encrypted file wherein the request may include a file segment signature determining by the management server whether the user device is authorized to decrypt the at least one encrypted file segment and sending the at least one decryption key to the user device if it is determined that the user device is authorized to decrypt the at least one encrypted file segment.

The non transitory computer readable medium may store instructions for retrieving by a user device of multiple file segment signatures associated with multiple encrypted file segments of an encrypted file wherein each file segment signature is mapped to an encryption and decryption key that facilitates a decryption of an encrypted file segment associated with the file segment signature comparing the multiple file segment signatures to a data structure of file segment signatures that may be mapped to decryption keys that may be stored at the user device to find at least zero decryption keys not stored in the user device requesting from a management server the at least zero decryption keys that are not stored in the user device receiving by the user device the at least one zero decryption keys that are not stored in the user device and decrypting the multiple encrypted file segments wherein each encrypted file segment is decrypted using an decryption key that facilitates the decryption of the encrypted file segment.

The non transitory computer readable medium may store instructions for retrieving the file from a storage service segmenting the file into multiple file segments calculating a file segment signature for each of the multiple file segments to provide multiple file segment signatures encrypting each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that may be in response to the multiple file segment signatures wherein the multiple encrypted file segments form an encrypted file and sending the multiple encrypted file segments to the storage service.

The non transitory computer readable medium may store instructions for receiving a request by a management server to provide at least one decryption key for decrypting at least one encrypted file segment of the encrypted file by a user device after the management server generated the encrypted file to be of a certain file type and after a storage service stored the encrypted file wherein the request may include a file segment signature determining by the management server whether the user device is authorized to decrypt the at least one encrypted file segment and sending the at least one decryption key to the user device if it is determined that the user device is authorized to decrypt the at least one encrypted file segment.

The non transitory computer readable medium may store instructions for retrieving by a user device of multiple file segment signatures associated with multiple encrypted file segments of an encrypted file wherein each file segment signature is mapped to an encryption and decryption key that facilitates a decryption of an encrypted file segment associated with the file segment signature comparing the multiple file segment signatures to a data structure of file segment signatures that may be mapped to decryption keys that may be stored at the user device to find at least zero decryption keys not stored in the user device requesting from a management server the at least zero decryption keys that are not stored in the user device receiving by the user device the at least one zero decryption keys that are not stored in the user device and decrypting the multiple encrypted file segments wherein each encrypted file segment is decrypted using an decryption key that facilitates the decryption of the encrypted file segment.

Additional embodiments of the invention include a system arranged to execute any or all of the methods described above including any stages and any combinations of same. For example the system may include a management server that may be arranged to retrieve the file from a storage service segmenting the file into multiple file segments calculate a file segment signature for each of the multiple file segments to provide multiple file segment signatures encrypt each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that may be in response to the multiple file segment signatures wherein the multiple encrypted file segments form an encrypted file and send the multiple encrypted file segments to the storage service.

Additional embodiments of the invention include a system arranged to execute any or all of the methods described above including any stages and any combinations of same. For example the system may include a management server that may be arranged to receive a request by a management server to provide at least one decryption key for decrypting at least one encrypted file segment of the encrypted file by a user device after the management server generated the encrypted file to be of a certain file type and after a storage service stored the encrypted file wherein the request may include a file segment signature determine by the management server whether the user device is authorized to decrypt the at least one encrypted file segment and sending the at least one decryption key to the user device if it is determined that the user device is authorized to decrypt the at least one encrypted file segment.

Additional embodiments of the invention include a system arranged to execute any or all of the methods described above including any stages and any combinations of same. For example the system may include a user device that may be arranged to retrieve multiple file segment signatures associated with multiple encrypted file segments of an encrypted file wherein each file segment signature is mapped to an encryption and decryption key that facilitates a decryption of an encrypted file segment associated with the file segment signature compare the multiple file segment signatures to a data structure of file segment signatures that may be mapped to decryption keys that may be stored at the user device to find at least zero decryption keys not stored in the user device request from a management server the at least zero decryption keys that are not stored in the user device receive the at least one zero decryption keys that are not stored in the user device and decrypt the multiple encrypted file segments wherein each encrypted file segment is decrypted using an decryption key that facilitates the decryption of the encrypted file segment.

Additional embodiments of the invention include a system arranged to execute any or all of the methods described above including any stages and any combinations of same. For example the system be arranged to retrieve the file from a storage service segment the file into multiple file segments calculate a file segment signature for each of the multiple file segments to provide multiple file segment signatures encrypt each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that may be in response to the multiple file segment signatures wherein the multiple encrypted file segments form an encrypted file and sending the multiple encrypted file segments to the storage service.

Additional embodiments of the invention include a system arranged to execute any or all of the methods described above including any stages and any combinations of same. For example the system may include a management server that may be arranged to receive a request to provide at least one decryption key for decrypting at least one encrypted file segment of the encrypted file by a user device after the management server generated the encrypted file to be of a certain file type and after a storage service stored the encrypted file wherein the request may include a file segment signature determine whether the user device is authorized to decrypt the at least one encrypted file segment and send the at least one decryption key to the user device if it is determined that the user device is authorized to decrypt the at least one encrypted file segment.

Additional embodiments of the invention include a system arranged to execute any or all of the methods described above including any stages and any combinations of same. For example the system may include a user device that may be arranged to retrieve multiple file segment signatures associated with multiple encrypted file segments of an encrypted file wherein each file segment signature is mapped to an encryption and decryption key that facilitates a decryption of an encrypted file segment associated with the file segment signature compare the multiple file segment signatures to a data structure of file segment signatures that may be mapped to decryption keys that may be stored at the user device to find at least zero decryption keys not stored in the user device request from a management server the at least zero decryption keys that are not stored in the user device receive by the user device the at least one zero decryption keys that are not stored in the user device and decrypt the multiple encrypted file segments wherein each encrypted file segment is decrypted using an decryption key that facilitates the decryption of the encrypted file segment.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numerals may be repeated among the figures to indicate corresponding or analogous elements.

In the following detailed description numerous specific details may be set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

The subject matter regarded as the invention is particularly pointed out and distinctly claimed in the concluding portion of the specification. The invention however both as to organization and method of operation together with objects features and advantages thereof may best be understood by reference to the following detailed description when read with the accompanying drawings.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numerals may be repeated among the figures to indicate corresponding or analogous elements.

Because the illustrated embodiments of the present invention may for the most part be implemented using electronic components and circuits known to those skilled in the art details will not be explained in any greater extent than that considered necessary as illustrated above for the understanding and appreciation of the underlying concepts of the present invention and in order not to obfuscate or distract from the teachings of the present invention.

Any reference in the specification to a method should be applied mutatis mutandis to a system capable of executing the method and should be applied mutatis mutandis to a non transitory computer readable medium that stores instructions that once executed by a computer result in the execution of the method.

Any reference in the specification to a system should be applied mutatis mutandis to a method that may be executed by the system and should be applied mutatis mutandis to a non transitory computer readable medium that stores instructions that may be executed by the system.

Any reference in the specification to a non transitory computer readable medium should be applied mutatis mutandis to a system capable of executing the instructions stored in the non transitory computer readable medium and should be applied mutatis mutandis to method that may be executed by a computer that reads the instructions stored in the non transitory computer readable medium.

According to various embodiments of the invention methods computer readable media and systems are provided for extending existing third party cloud storage services without changing their basic architecture. The methods computer readable media and systems may support all the services of the cloud based virtual file system described in U.S. patent application Ser. No. 13 031 628 filling date Feb. 22 2011 as well as several new features.

Similarly the new set of features may assist the administration of the organization termed IT as well as the users in gaining new management and security functions. This should be done across multiple services in a seamless way.

We assume that according to an embodiment of the invention there is provided a system that may support a cloud storage service such as Dropbox Box Sugarsync or a web based storage system such the one offered by Amazon S3 or EMC. It can also support document repositories included in SaaS services such as Salesforce Success Factors and Jive. Without loss of generality we can also utilize systems which are not traditional storage depositories. For example Google Docs Office 365 Evernote and even cloud based email accounts such as Gmail have the ability to create draft documents create folders and filters and send mail to another email account. While there are many different user interfaces and APIs provided by the different cloud storage services we assume that there is a clear way in each of these services to upload a file erase a file and upload control information using the writing and reading of standard files e.g. text or binary files .

The Management server can communicate with user devices and that host management applications such as management applications. The management server is illustrated as having a file system metadata module an IT policy enforcement module a data manager and login module and an encryption key manager .

The management server can be regarded as a broad term to describe the complete software system which is responsible for encrypting files in the cloud and enforcing secure access to these cloud files by providing the right decryption keys to the right users. It may include various software and or hardware components that may include or may be arranged to i provide connectors to various consumer file repositories ii store information about these file repositories iii analyze and encryption of files iv secure storage and retrieval of encryption keys v provide access policy configuration for secure file access vi enforce access policy for secure file access and vii report on file access usage and devices being used for access.

The management server itself can be run on the cloud and implemented in various programming languages for example Python code running on Heroku or Java based servers running on Amazon EC2. For storing the data such as file metadata keys access tables and user profiles a data a persistent store can be used example Postgres Relational Database and or Redis Key Value Store 

The figure also illustrates a file System metadata module . The Sookasa service fetches information about all the files residing in consumer file repositories. In addition to the file name the service also discovers a lot of information about the file which is commonly called metadata.

The metadata module can be implemented by a combination of application code and a persistent store e.g. Python code and a relational database and an in memory store Memcache Redis for enhanced performance.

IT Policy Enforcement Module . The Sookasa service encrypts files in consumer file repositories. Different IT departments will want different policies for access to these secure files. Users in a company may be organized in further groups and each group may have different policies. Each user may use multiple devices to access these file repositories e.g. Dropbox accessed by an iPhone iPad App or a Windows Laptop. The admin interface allows for an administrator to define access policies. This is done through a web browser interface to the module. Once this policy is defined it will be enforced through application interfaces API . A HTTP based API will be available which can be used by a Sookasa client application or any third party application to request access to a secure file. The module will check the credentials of the requesting application user and the file to determine if access is to be granted.

Data Manager and Login Module . An application interface API will be provided so an application can request access to the secure file on behalf of the user. For example on the iPhone a Sookasa application can handle a request to open a secure file. On invocation the Sookasa application will authenticate the user with the login module and then request access to the secure file.

Encryption Key Manager . The encryption key manager generates stores and retrieves encryption keys. An encryption key is used to encrypt a cloud file or chunks in case of very large files . For example an AES 256 byte key can be used to encrypt a file. This AES key needs to be stored so it can later be retrieved to decrypt the file. The key is stored in a secure manner in a persistent storage. For example Sookasa will store the key in an encrypted form in a relational database.

The management server may provide a SaaS solution layered on top of one or more cloud storage solutions to monitor track log and secure unstructured business content in the cloud stored at different file repositories operated by many vendors. The management server and the management application may also enables cross vendor file tracking comparison and movement as well as user access to files from one of the vendors user interfaces UIs to other vendors.

The management server provides user management API access as well as API feed to cloud storage services such as Dropbox and Box metadata for all the files folders contained in these services and device APIs for the management application on user s devices to communicate with the server. The management server may also provide file and folder encryption services to the user. It serves as the secure key server and provides file decryption keys and permissions to the Management Apps on devices. It also allows the extraction of file Metadata from files including their cryptographic signature.

The management application or a management web application may allow users to register for management services to login and manage their account to create manage collaboration teams for secure file and folder sharing. It also allows for a full view of the user files and folders across all services.

The management web application may also provide a hierarchical administrative dashboard to a hierarchy of team administrators to manage team policies and permissions and to track team members usage of the cloud storage services.

Management applications on desktops and mobile devices are invoked when the file types for which they are registered are opened by the user locally or from cloud storage applications. These applications then seamlessly access the management server to fetch the encryption keys from the server as needed to decrypt the secure file before opening the file for the user.

Other file types are used to create pointers to files which can be stored in cloud storage services and are uploaded by the Management applications through a request to the Management server or directly from the cloud service.

The management server may have the following functions user management cloud service API metadata device API and key management.

The management server may use the Django Python Django 1.4 and Python 2.7 web application framework on top of which each of the components are instantiated. A database such as a PostgreSQL database may be used for the user and team information with an optional cache layer based on Redis or Memcache to optimize database accesses.

Redis may be used for implementing a key value store for keeping the file folder metadata. This allows the management server to handle authorize the key requests from the devices very rapidly. Redis also provides the mechanism to create message queues for inter module communication. Celery and Celerybeat components may provide facility for scheduling and managing multiple threads.

The management server may use standard REST APIs provided by cloud storage services e.g. Dropbox and Box to periodically discover new and changed user files in the cloud. Additional metadata e.g. file signature is extracted from these files and stored in the Redis key value store. Any new files that need encryption are serviced and stored back in the cloud via the appropriate APIs. The management server may also need to access additional file folder sharing information using the user s cloud account. The management server may provide a similar REST API for third party services in order to upload metadata to the management server.

The management server may provide a REST API for the device apps to communicate with the server as needed to fetch or push appropriate file encryption keys to the device.

The management server may be implemented as a multi tenant SaaS application hosted in the cloud. The management server components may be instantiated as modules on top of the Heroku Platform as a Service PaaS platform which in turn is hosted on Amazon Web Services .

The management server may be implemented in a modular way with well defined interfaces between components which allows scaling and hosting different modules independently and outside Heroku as well e.g. the PostgreSQL DB can be run elsewhere e.g. on AWS to optimize performance. In addition a caching layer can be added on top of the database backend to increase performance.

Heroku allows the application to scale appropriately by instantiating more dyno instances for any of the server component as required. Additional Heroku application modules are also instantiated as needed e.g. mailgun for smtp stripe for payments new relic for monitoring.

Management web application handling may be implemented using the Django Web Model View Template Framework on a standard web server e.g. Apache with a Python backend server which hosts the database model for the users team owners and teams. The frontend is further enhanced by Jquery JavaScript and Ajax calls to the server. The data between the server and client app is serialized using JSON JavaScript Object Notation format.

Users may sign up for the management service using the web application and from the device application in the future . Users can create collaboration teams to share secure folders and invite other enterprise users to these teams. The team administrators have a tracking monitoring dashboard view of all the sharing activity within and outside the team. The team administrator can be configured to approve or deny requests for members outside her team to access secure files inside the team members secure folder.

The management server may be integrated with Open ID and Microsoft Active Directory to facilitate and simplify provisioning of enterprise users.

The management applications are installed by the users on their desktop computer or their mobile devices. The OS requirements for desktop clients are Windows 7 or Mac OS X 10.6.8 Linux desktop support will be added in the future and these can be downloaded from the management server by the user. The OS requirements for mobile clients are IOS 5 for iPhones and iPads and Android 2.3 for Android phones and tablets. These apps are downloaded by the user from the App Store and Android Marketplace respectively. Updating the installed applications to newer revisions is also supported.

The management application may be registered with the underlying OS to open the encrypted documents with the .sooksasa file extension and other file extensions designated for encrypted files and virtual files. These files may be opened from the MS Explorer OS X Finder or similar file browsers as well as from the cloud service application file browser. When opening an encrypted file from the local file browser the management application seamlessly hands over the decrypted file to the native application for the file type of the original unencrypted file. When opening an encrypted file from a web based file browser the management application seamlessly fetches the file over the network from the management server or from another cloud service over its native API and hands over the file to its native application.

As part of the OS registration the application also registers management type icons to display encrypted files visually to the user and to show encryption progress for any files or folders that are added to the secure folder of the user. Similarly virtual files are displayed to show if they are remote or in the process of being fetching.

The Management server imports information regarding the files and folders from the various repositories. It can be gathered through browsing the typically tree structure of the folders and processing file and folder data or by directly importing metadata that resides within these repositories. The information is captured into a normalized metadata description. Examples are described in U.S. patent application Ser. No. 13 031 628.

In addition other systems can export their file repository information by pushing this information to the Management server via a published API. The API specifies how the folder directory structure is described and how the file information is described as well as extracted. The API may also describe commands that can be invoked against the files or folders from the Management server. This enables new SaaS providers to be managed via the management server.

In addition to the information that describes the folders and files there may be additional information captured as metadata that describes the policy and ownership of the folders and files and how they should be handled. This additional information can be gathered from other sources e.g. Microsoft Active Directory LDAP can be configured and defined on top of the tree and files by both users and administrators and can be created by the system itself by learning user and administrator behavior. This metadata may include for sub trees folders and files 

The management server is kept updated about access changes and modification to files and folders. These updates are logged at the management server and can be accessed and exported by the administrators. Examples of information parameters that can be tracked and logged 

The management server may allow the administrator not only access to its metadata and logs but may also create a federated physical file system by allowing users and administrators access to the files in variety of ways. A very simple example is exposing to the IT and the user a standard file system network interface such as WebDAV FTP SFTP that enables download upload move and discard operations as well as file folder name or other property changes. When a request for a specific file operation is invoked the management server acts as a middle box or man in the middle between the user and the repositories and translates the load upload change operations to the API used by the management server against the specified repository. The management server may also perform value added services in the path such as encryption decryption traffic de duplication and compression. It can also serve as a cache to facilitate large information transfers.

As folder structure and file metadata is extracted and maintained by the management server newly discovered files are uploaded to the management server for additional metadata extraction. As metadata should be kept small in compared to the original file size there are several important use cases for the metadata being kept at the management server for the operation and management of the federated virtual file system FVFS .

In this invention we will focus on a set of metadata types that will be termed file DNA. These information items can be file type specific or totally type agnostic. A file DNA may include file segment signature each file segment signature may be associated with a single segment of the file. A file segment signature of a specific file segment can be calculated based upon the content of the file segment.

The file DNA can be extracted by the storage service and reported to the management server. Alternatively this is done by the management server looking for new files in the storage services fetching each new file from the corresponding service to the management server performing the DNA extraction and erasing the fetched copy after the DNA extraction is completed. In order to save communication and storage a single fetch operation of a new file from the storage service to the management server can be used not only for DNA extraction but also for other services such as encryption analytics virus and malware filtering archiving and backup to other storage services and file synchronization between services.

There are several papers that describe different ways to discover and measure similarities between files. These papers may include 

Article j describes the first implementation of file de duplication using the segmenting techniques described in article a. We will use some of the segmenting techniques described in these documents that are based on the application of Rabin Fingerprints see articles h and i and A. Z. Broder Some applications of Rabin Sequence II 1993 or Cyclic Redundancy Code CRC over a sliding window along the file and the creation of anchors segments boundaries along these files see .

Segments are then identified by a cryptographic signature such as SHA 2 or a fingerprint function such as Rabin Fingerprint. Other techniques described in articles b g show how to dissect the file into shingles which can overlap unlike the segmenting algorithm of articles a and j . If Sand Sare the set of segments or shingles of files A and B respectively the similarity between the two files is defined as 

It is clear that this metric takes the value 1 when the files are identical and 0 when they have no common segment. The set relationship also defines inclusion and exclusion relationships.

As each file is identified by a sequence of segments each with a unique ID we can assign a threshold to identify file similarity. Two files are declared similar if the similarity metric is more than a predefined value H.

In addition to file similarities it may be very useful to identify file ancestry or lineage. We define file ancestry as a tree of files where the oldest file is at the top of the tree. Another file B will be defined as a direct child of another file A if 

Since a parent file A may have multiple children this creates a tree structure rooted at the first version of a file termed the ancestry tree . Note that such files in a single ancestry tree may belong to different repositories and different users and is not related to the folder tree structure.

Note that while context free similarities based on segments or shingles is a very useful notion there are many obstacles to applying such metrics and there is a strong motivation to further refine the notion of file similarities.

Files may also include images which occupy a much larger space than text. Thus it may be sufficient to replace a single large image or picture to make the two files not similar while in reality they are almost identical. Examples can be a single picture a logo or a presentation background.

Many modern applications create files that are compressed e.g. PDF MS Office 2007 and later . If two files A and B are similar their compressed versions are usually not similar using the segmenting or shingles metric.

Policies can be defined on documents which are ancestors of other documents. For example inheritance rules can be defined which imply that a policy that is defined on a document that is rooted at an ancestry sub tree by its file metadata or its folder metadata can be extended to its sub tree.

Placement policies violations can be detected. The actions taken upon detecting a policy violation can be one or more of 

As consumer storage services like Dropbox and Sugarsync have security problems in terms of password strength possible attacks on client apps and mobile devices exposure of content to the service employees and file folder sharing mistakes it may be required to apply a user based encryption on sensitive documents and corporate folders.

The rest of this subsection assumes that the second option is selected and that the management server is the entity that encrypts files on the user Dropbox accounts we use Dropbox as a generic example and the same method can be followed for other web storage services . We also assume that a special management application is uploaded to every device that is needed to decrypt the files and there is also a way to interact with the encryption and decryption facility from the user s web browser interface.

The encrypted files are stored in the web storage service under a new file type. This file type will have a new icon either installed at the web service e.g. Dropbox or when the management application is installed on the device. In order to permit different icons such as various Office icons with a lock symbol representing encryption there may be multiple new types defined such as docx sks pptx sks. One type .sks serves as a default for the case where the original type is not known or the system supports only a 3 letter type.

A right click selection of the temporary decryption action of a file or folder will cause the server to decrypt the file temporarily if the user has a permission to access the file. It will be re encrypted after a time out as described before in the encryption functions.

A file may be stored in at a storage entity managed by a storage service of a cloud computing environment such as a Dropbox service .

The management server may perform a de duplication friendly encryption process to provide a modified file also referred to as an encrypted file . The encryption process is de duplication friendly because it is performed on segments of the file in a manner that preserves or induces minimal penalty on the storage system de duplication capabilities. As will be illustrated in the FIG. changes of a file may require transmitting only file segments that were actually affected by the changes in the file and allow the storage system to prevent the re transmission de duplication of file segments that are already stored at the user device.

The storage service may expose after performing a sync process the encrypted file to a user device . Thus the encrypted file can be viewed as belonging to a virtual folder that is displayed to a user of user device . If the user requests to decrypt the encrypted file the management application can determined if it already has all the required keys for decrypting the encrypted file and if it is so the user device can decrypt the encrypted file. If one or more encryption keys are missing they are requested from the management server . The management server may apply an access control mechanism permission and may or may not allow the management application to obtain the encryption keys. If it is determined that the user and user device have the requisite permissions for the file then the encryption keys are provided key upload and pre fetch to the management application.

The decryption process may require the retrieval of the file or at least of file segments from the storage service and the storage service can apply a de duplication process that involves sending only encrypted file segments that are not already stored in the user device .

Now every time a file transfer or storage is required it is first checked if each of its segments already resides in the target system. For the segments which are already known only the segment signatures need to be sent or stored. This technique is used in many commercial systems that apply storage de duplication e.g. DataDomain and traffic redundancy elimination e.g. Riverbed Cisco WAAS . If the system uses compression this will be performed on each segment separately and not the original file.

Assuming that file is already stored in a user device then the de duplication mechanism will have to send only file segments C of file .

Assuming that file is already stored in a user device then the de duplication mechanism will have to send only file segments C and C of file .

Assuming that file is already stored in a user device then the de duplication mechanism will have to send only file segment C of file .

This de duplication mechanisms breaks when encryption and compression is introduced at a full file level. Both functions practically randomize the data map the file bit vector to a pseudo randomly selected bit vector of an identical encryption or shorter length . Both create completely different files even if the original files were only different in a single bit. Thus similarity between files as defined above is completely destroyed with these features. This is demonstrated in .

These segments differ from each other and virtually eliminate any benefit that can be obtained from the de duplication process.

There is provided a user level encryption methodology separate from possible internal service encryption such as the one applied by Dropbox at the Amazon S3 service in which the native de duplication in systems like Dropbox Box or any other storage service will be able to use segmenting based de duplication for elimination of redundancy in their storage and communication with remote agent file synchronization with mobile client cache .

The idea is that instead of encrypting the entire file we use a user level segmenting algorithm termed segmentation algorithm split the files into user level segments that are independent of the native de duplication used by the cloud storage system.

Segments are potentially compressed signed using a hash function and then encrypted using a key that is a function of the segment signature. In other words identical segments use identical encryption keys. Encrypted segments are combined together to form a full file. In order to be able to decompose segments these may be preceded by a size field signature field or signature ID field and then the data itself.

Another way is to describe the segments lengths and IDs before the first segment starts. The file itself starts with the file signature or the file signature ID which is the key to the access permission process. Note that this technique increases the number of keys used to encrypt decrypt a large file composed of several segments. This is necessary as the content of identical segments must remain identical also after the encryption. This procedure is detailed in .

Method starts by stage of receiving a file if the file is compressed then decompressing it and compute a file signature for example by applying a SHA 2 process . Stage is followed by stage of checking if the file signature already exists in the database of the application server if so stage is followed by stage else stage is followed by stage .

Stage may include retrieving file segment sizes from the database to segment the file into file segments compress and encrypt each file segment using encryption keys calculated based upon the file segment signatures and appending segment size and key ID to the beginning of each encrypted file segment. Stage is followed by END stage .

Stage may include adding a file signature to the file database and assigning a new file identifier. Stage is followed by stage of appending the file ID to the beginning of the encrypted file and applying a file segmenting algorithm using for example Rabin fingerprinting.

Stage is followed by stage of determining if there are more file segments to process if so then stage is followed by stage . If there are no file segments to process then stage is followed by stage .

Stage is followed by stage of checking if the file segment signature is already in a file segment signature database and if so stage is followed by stage of retrieving an encryption key or an encryption key identifier associated with the file segment signature. Otherwise stage is followed by stage of assigning a new encryption key and a new encryption key identifier ID . Stage and are followed by stage of adding the file segment signature a segment size indicator and the encryption key to a database compressing and encrypting the file segment using the encryption key and appending the file segment size indicator and the encryption key identifier to the beginning of the encrypted file segment.

Stage includes retrieving file segment sizes from the database to segment the file into file segments add unique company identifier to each file segment compress and encrypt each file segment using encryption keys calculated based upon the file segment signatures and appending segment size and key ID to the beginning of each encrypted file segment.

Stage includes adding a unique company ID to the file segment adding the file segment signature a segment size indicator and the encryption key to a database compressing and encrypting the file segment using the encryption key and appending the file segment size indicator and the encryption key identifier to the beginning of the encrypted file segment.

File includes segment segment segment and segment and . In comparison to file segment differs from segment as a result from adding information to segment.

File includes segment segment segment and segment and . In comparison to file segment differs from segment as a result from removing information from segment.

Encrypted file includes segment a segment b segment c segment d and segment e and . In comparison to encrypted file segment b differs from segment b .

Encrypted file includes segment a segment b segment c segment d and segment e and . In comparison to encrypted file segment b differs from segment b .

File segments and were generated by the management system. The segmentation performed by the management system is independent of the storage service segmentation performed by the storage service. also illustrates storage service segments and storage service anchors. The storage service segments are illustrated as being smaller than the file segments defined by the management server but they may be bigger than or even equal to the storage service segments.

Encrypted file is segmented by the storage service to fourteen storage file segments and . Storage service segments differ from storage service segments as they include data from file segment .

Encrypted file is segmented by the storage service to thirteen storage file segments and . Storage service segments differ from storage service segments as they include data from file segment .

According to various embodiments of the invention and in order to lower the overhead associated with a large number of keys a practical selection of the segmentation algorithm may be the following 

The management application on a device is called each time the user clicks on a file in the Dropbox folder as well as other cloud storage file browser email attachment etc. whose type is unique and the management application has registered for this file type. This methodology was described for the decryption of files that were encrypted by the management server directly on the Dropbox account.

Such methodology allows the management server to use the cloud storage application for accessing files that are located outside this service while still placing them within the desired folders of the same cloud service e.g. certain files within the Dropbox tree will be located outside Dropbox . Instead of the real files the management server may place short files with a new type that only include pointers to files so each time the user clicks on a pointer type file filename.doc elsewhere of type doc elsewhere with an icon that match exactly a doc file the management application gets called. This file contains a short pointer to the real file which is stored in another file repository or on the management server. It may be also an encrypted repository that belongs to the enterprise. The management application then fetches this file from the other repository. Access control can be controlled by the server side including the following file features 

The file is processed by a first process that includes decompression signature computation such as SHA2 signature computation denoted in segmentation and segment signature computation to provide three file segments SEGMENT of SIZE and SEGMENT SIGNATURE SEGMENT of SIZE and SEGMENT SIGNATURE . The file segments are processed by a second process that includes assigning file identifier assigning file segment identifiers and assigning key cryptography to provide encrypted file segments . Each encrypted file segment includes an encrypted content size information and segment identifier . These encrypted file segments and the encrypted file identifier form encrypted file represented in database by record .

The database may include the name of the original file NOTES.COM the size of the original file KB a file identifier XYZ . . . the name of the encrypted file also referred to as secure file NOTES.DOC.SOOKASA time of creation of the encrypted file 5 01 PM 10 OCT 2012 and encrypted file segment information such as encrypted file segment identifier size signature cryptographic key SEGMENT ID SIZE SIGNATURE CRYPTO KEY per encrypted file segment.

The invention may also be implemented in a computer program for running on a computer system at least including code portions for performing steps of a method according to the invention when run on a programmable apparatus such as a computer system or enabling a programmable apparatus to perform functions of a device or system according to the invention.

Method may include retrieving the file from a storage service segmenting the file into multiple file segments calculating a file segment signature for each of the file segments to provide multiple file segment signatures encrypting each of the multiple file segments to provide multiple encrypted file segments by using encryption keys that are responsive to the multiple file segment signatures wherein the multiple encrypted file segments form an encrypted file and sending the multiple encrypted file segments to the storage service .

The segmenting of the file into multiple file segments may be executed regardless of a file segmentation scheme applied on the file by the storage service such as a file segmentation scheme applied on the file by the storage service for de duplication purposes.

Stage may include sending at least one encryption key that is responsive to a content of the at the least one encrypted file segment.

Stage may include receiving the request from an application that is regarded by the operating system hosted by the user device to be associated with files of the certain file type.

At least one of the management server and the storage service belong to a cloud computing environment.

The decrypting of a certain file segment can be done by using a decryption key that is calculated based upon a file segment signature and its metadata field associated with the certain file segment.

The determining action may be executed without any intervention from the user of the device may be triggered by the user of the device may be triggered by a determination to modify another file that is similar to the file may be in response to a content of the file or to metadata associated with this file.

The determining action may be in response to a placement of the file within a folder that is defined as including files that should be modified or may be in response to a lapse of at least a predetermined time period during which the file is not altered the predetermined time period starts from a moment that the file is stored in a folder that is defined as including files that should be modified.

The modifying action may include changing a content of the file encrypting the file encrypting the file if it determined that a security level of the file is not adequate generating the modified file to comprise access information to another location in which the modified file is to be stored and storing the modified file at the other location flagging the file by altering the file type of the file to a predefined file type to be handled by the management application.

The providing action may include scanning multiple storage entities that are managed by different storage services in the cloud computing environment to find files that are candidates for modification.

The modified file may consist essentially of access information to the file and flagging information that indicates to the agent that the modified file is to be handled by the agent.

The method may also include retrieving by the agent the modified file and requesting of the file by the agent from the management server in response to the retrieval of the modified file wherein the file and the modified file are stored at different locations. The user device that hosts the agent may be prevented from directly accessing the first storage device.

The method may include repeating the retrieving the modifying and providing actions for each file of a first folder of the first storage device to provide a second folder of modified files wherein the first and second folders have substantially a same structure.

The method may include repeating the retrieving the modifying and providing actions for each file of a first group of files stored by the first storage device to provide a second group of modified files wherein the first and second groups of files have substantially a same structure.

The compressed file signatures may be at least fifty percent smaller than the unique file segment signatures.

The compressed file signatures may be at least eighty percent smaller than the unique file segment signatures.

The compressed file signatures may be at least ninety percent smaller than the unique file segment signatures.

The segmenting action may maintain a separation between image content of the file and text content of the file.

A computer program is a list of instructions such as a particular application program and or an operating system. The computer program may for instance include one or more of a subroutine a function a procedure an object method an object implementation an executable application an applet a servlet a source code an object code a shared library dynamic load library and or other sequence of instructions designed for execution on a computer system.

The computer program may be stored internally on a non transitory computer readable medium. All or some of the computer program may be provided on computer readable media that is permanent removable or remotely coupled to an information processing system. The computer readable media may include for example and without limitation any number of the following magnetic storage media including disk and tape storage media optical storage media such as compact disk media e.g. CD ROM CD R etc. and digital video disk storage media nonvolatile memory storage media including semiconductor based memory units such as FLASH memory EEPROM EPROM ROM ferromagnetic digital memories MRAM volatile storage media including registers buffers or caches main memory RAM etc.

A computer process typically includes an executing running program or portion of a program current program values and state information and the resources used by the operating system to manage the execution of the process. An operating system OS is the software that manages the sharing of the resources of a computer and provides programmers with an interface used to access those resources. An operating system processes system data and user input and responds by allocating and managing tasks and internal system resources as a service to users and programs of the system.

The computer system may for instance include at least one processing unit associated memory and a number of input output I O devices. When executing the computer program the computer system processes information according to the computer program and produces resultant output information via I O devices.

In the foregoing specification the invention has been described with reference to specific examples of embodiments of the invention. It will however be evident that various modifications and changes may be made therein without departing from the broader spirit and scope of the invention as set forth in the appended claims.

Moreover the terms front back top bottom over under and the like in the description and in the claims if any are used for descriptive purposes and not necessarily for describing permanent relative positions. It is understood that the terms so used are interchangeable under appropriate circumstances such that the embodiments of the invention described herein are for example capable of operation in other orientations than those illustrated or otherwise described herein.

The connections as discussed herein may be any type of connection suitable to transfer signals from or to the respective nodes units or devices for example via intermediate devices. Accordingly unless implied or stated otherwise the connections may for example be direct connections or indirect connections. The connections may be illustrated or described in reference to being a single connection a plurality of connections unidirectional connections or bidirectional connections. However different embodiments may vary the implementation of the connections. For example separate unidirectional connections may be used rather than bidirectional connections and vice versa. Also plurality of connections may be replaced with a single connection that transfers multiple signals serially or in a time multiplexed manner. Likewise single connections carrying multiple signals may be separated out into various different connections carrying subsets of these signals. Therefore many options exist for transferring signals.

Those skilled in the art will recognize that the boundaries between logic blocks are merely illustrative and that alternative embodiments may merge logic blocks or circuit elements or impose an alternate decomposition of functionality upon various logic blocks or circuit elements. Thus it is to be understood that the architectures depicted herein are merely exemplary and that in fact many other architectures can be implemented which achieve the same functionality.

Any arrangement of components to achieve the same functionality is effectively associated such that the desired functionality is achieved. Hence any two components herein combined to achieve a particular functionality can be seen as associated with each other such that the desired functionality is achieved irrespective of architectures or intermediate components. Likewise any two components so associated can also be viewed as being operably connected or operably coupled to each other to achieve the desired functionality.

Furthermore those skilled in the art will recognize that boundaries between the above described operations are merely illustrative. The multiple operations may be combined into a single operation a single operation may be divided into additional operations and operations may be executed at least partially overlapping in time. Moreover alternative embodiments may include multiple instances of a particular operation and the order of operations may be altered in various other embodiments.

Also for example in one embodiment the illustrated examples may be implemented as circuitry located on a single integrated circuit or within a same device. Alternatively the examples may be implemented as any number of separate integrated circuits or separate devices interconnected with each other in a suitable manner.

Also for example the examples or portions thereof may be implemented as software or code representations of physical circuitry or of logical representations convertible into physical circuitry such as in a hardware description language of any appropriate type.

Also the invention is not limited to physical devices or units implemented in non programmable hardware but can also be applied in programmable devices or units able to perform the desired device functions by operating in accordance with suitable program code such as mainframes minicomputers servers workstations personal computers notepads personal digital assistants electronic games automotive and other embedded systems cell phones and various other wireless devices commonly denoted in this application as computer systems .

However other modifications variations and alternatives are also possible. The specifications and drawings are accordingly to be regarded in an illustrative rather than in a restrictive sense.

In the claims any reference signs placed between parentheses shall not be construed as limiting the claim. The word comprising does not exclude the presence of other elements or steps than those listed in a claim. Furthermore the terms a or an as used herein are defined as one or more than one. Also the use of introductory phrases such as at least one and one or more in the claims should not be construed to imply that the introduction of another claim element by the indefinite articles a or an limits any particular claim containing such introduced claim element to inventions containing only one such element even when the same claim includes the introductory phrases one or more or at least one and indefinite articles such as a or an. The same holds true for the use of definite articles. Unless stated otherwise terms such as first and second are used to arbitrarily distinguish between the elements such terms describe. Thus these terms are not necessarily intended to indicate temporal or other prioritization of such elements. The mere fact that certain measures are recited in mutually different claims does not indicate that a combination of these measures cannot be used to advantage.

While certain features of the invention have been illustrated and described herein many modifications substitutions changes and equivalents will now occur to those of ordinary skill in the art. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes as fall within the true spirit of the invention.

