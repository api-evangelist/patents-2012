---

title: Techniques for achieving tenant data confidentiality from cloud service provider administrators
abstract: Techniques for achieving tenant data confidentiality in a cloud environment are presented. A daemon process within a Tenant Storage Machine (TSM) manages a key store for a particular tenant of a cloud storage environment having multiple other tenants. Just TSM storage processes are given access to the key store. Data is decrypted for the particular tenant when access is needed and data is encrypted using encryption keys of the key store when written in the cloud storage environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09270459&OS=09270459&RS=09270459
owner: CloudByte, Inc.
number: 09270459
owner_city: Cupertino
owner_country: US
publication_date: 20120912
---
The present application is co pending with and claims foreign priority to Indian Provisional Patent Application No. 3233 CHE 2011 entitled A Method for Protecting Tenant Data from a Service Provider in a Cloud Storage Environment filed with the Indian Patent Office on Sep. 20 2011 the disclosure of which is incorporated by reference herein in its entirety.

Cloud computing is rapidly changing the Internet into a collection of clouds which provide a variety of computing resources storage resources and in the future a variety of resources that are currently unimagined.

Specifically cloud computing is a technology infrastructure that facilitates supplementing consuming and delivering Information Technology IT services. The cloud environment provides elastic provisioning of dynamically scalable virtual services.

A tenant is considered as a subscriber of some amount of storage in the cloud or an application who owns part of the shared storage environment. Multi tenancy is an architecture where a single instance of software runs on a server which is serving multiple tenants. In a multi tenant environment all tenants and their users consume the service from a same technology platform sharing all components in the technology stack including the data model servers and database layers. Further in a multi tenant architecture the data and configuration is virtually partitioned and each tenant works with a customized virtual application instance.

In a Cloud Service Provider s environment multiple customers tenants applications share a common storage infrastructure. The shared storage infrastructure includes storage controllers and raw storage disks. It is often a common scenario that some enterprise customers or users have a stringent requirement that their data is stored in an encrypted manner so that no one else can read their data.

Specifically today whenever data needs to be encrypted for confidentiality several encryption algorithms are used with a key being stored at the tenant or client or at the server storage controller .

So tenant or client can manage the storage keys or the storage controller can manage the storage keys.

The problem with the key being stored at tenant or client is that in the case of key being lost by the tenant or client the encrypted data on the server becomes useless. This results in a complete loss of data.

The problem with the key being stored on the server or the storage controller is that the administrator of the storage controller who knows the root password can use the key to decrypt the data. So true confidentiality is never achieved this way.

Various embodiments of the invention provide techniques for achieving tenant data confidentiality. Specifically and in one embodiment a method for tenant data confidentiality in a cloud environment is presented.

More particularly and in an embodiment a tenant storage machine TSM is established in a cloud storage environment for an authenticated tenant. Next a tenant key store is managed within the TSM for the tenant the tenant key store including encryption keys for encrypting data of the authenticated tenant within the cloud storage environment. Finally assurances are made so that just TSM storage processes are given access to the tenant key store.

A resource includes a user service system device directory data store groups of users a file a file system combinations and or collections of these things etc. A principal is a specific type of resource such as an automated service or user that acquires an identity. As used herein a principal may be used synonymously and interchangeably with the term tenant. 

A processing environment defines a set of cooperating computing resources such as machines processor and memory enabled devices storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X and be logically combined with another computing resource at network site Y to form a logical processing environment.

The phrases processing environment cloud processing environment cloud environment and the term cloud may be used interchangeably and synonymously herein.

Moreover it is noted that a cloud refers to a logical and or physical processing environment as discussed above.

The techniques presented herein are implemented in machines such as processor or processor enabled devices hardware processors . These machines are configured and programmed to specifically perform the processing of the methods and systems presented herein. Moreover the methods and systems are implemented and reside within a non transitory computer readable storage media or machine readable storage medium and are processed on the machines configured to perform the methods.

It is within this context that embodiments of the invention are now discussed within the context of the .

The techniques herein prescribe unique mechanisms for storing a tenant s data in such a way that only the tenant can read it and it is kept completely confidential even from the cloud service provider s administrator. This means that the tenant s data cannot be viewed by the cloud service provider.

As will be demonstrated more completely herein and below the embodiments herein provide the following unique techniques mechanisms to solve the above referenced problems 

In other words the approaches herein provide tenant data confidentiality in a multi tenant storage environment where a particular tenant s data can be decrypted by only that tenant and the server administrator is be able to read any of the tenant data either through the storage controller or by directly accessing the hard disk.

As shown is the the architecture includes a key store per each tenant. The run time environment of a tenant is called a Tenant Storage Machine or TSM. The techniques herein prescribe one key store or key container per TSM. The key store includes the keys of the tenant s data. In the two blocks of tenant data is encrypted with two dynamically generated strong keys k and k. These keys k and k are stored in a key store. The key store is managed by a key daemon. The key daemon allows only the tenant storage processes running inside the TSM to access keys k and k. In other words it is impossible to get the keys k and k anywhere outside the TSM.

When a TSM is started the tenant data is decrypted by the tenant storage processes and mount points are arranged. The decrypted tenant data can be accessed only by a process running inside the TSM.

When the administrator intentionally wants to read the confidential tenant data there are two ways he she can try. The first is to run a process inside the TSM and read through the mount points. The second is to directly ready the data on the hard disk accessible to him.

In the first method when the process owned by the root user outside the TSM tries to run a process inside the TSM the TSM architecture disallows it. TSM exposes an interface though which few sets of standard messages can be sent to TSM from outside the TSM. The architecture allows only the application management process to follow a secure protocol and communicate through the above interface. So it is impossible for the administrator to get access to the mount points inside the TSM.

In the second approach the administrator has access to the hard disk which has the encrypted data but not the keys with which the data is encrypted. So the encrypted data is worthless to the snooping administrator.

As shown below the techniques prescribe a mechanism in which there is a master key per tenant. This master key MK is used to encrypt the data encryption key DEK . Both MK and DEK are stored along with the data on the hard disk. The DEK is obfuscated with a static algorithm which is kept in a secret manner. The DEK is continually changing whenever the data is being written to disk.

This technique uses a randomly generated DEK for each block of data. For example a text file of 1 MB is stored on a disk where the Block size is 128K. Which means 1 MB text file is stored in 8 blocks on the disk. This technique uses 8 randomly generated DEKs that are encrypted with MK.

If the cloud service provider needs to read this data by stealing the hard disk he she has to crack the 8 DEKs.

As part of the data management the cloud service provider may store multiple copies of data for backup or disaster recovery purpose . Because the MK and DEK are stored alongside and with the data the replication happens both to the encrypted data and corresponding keys.

In an embodiment the key manager is deployed and utilizes the architecture presented above with respect to the and uses the sequence presented above with respect to the .

At the key manager establishes a tenant storage machine TSM in a cloud storage environment for an authenticated tenant. The cloud storage environment services multiple other storage tenants. Any authentication mechanism can ensure that the tenant is authenticated.

According to an embodiment at the key manager creates the TSM as a VM and processing environment within the cloud storage environment for the authenticated tenant to access the data of the authenticated tenant. So each time a particular tenant authenticates to the cloud storage environment a VM in a TSM for that tenant is created to manage the storage session between the tenant and the cloud storage environment via the TSM.

At the key manager manages a tenant key store within the TSM for the authenticated tenant. The tenant key store includes encryption keys for encrypting data of the authenticated tenant within the cloud storage environment. Other tenant specific keys may be housed here as well and managed on behalf of the tenant.

In an embodiment at the key manager ensures that the TSM includes just one key storage which belongs to the tenant as the tenant key store. In other words there is a one to one mapping of the a key store to a TSM and a one to one mapping between authenticated tenant and a TSM.

In another case at the key manager creates the tenant key store as a container within the TSM for the authenticated tenant. In other words the tenant key store is a logical data structure created and managed by the key manager.

According to an embodiment at the key manager delegates management and any access to the tenant key store to a key daemon that processes within the TSM. This was discussed at length above with reference to the A and B.

In an embodiment at the key manager restricts root processes from accessing the tenant key store. That is only tenant storage processes described at can access the tenant key store so not even root processes initiated by the administrator can access the tenant key store.

Continuing with the embodiment of and at the key manager limits Application Programming Interface API calls that can be initiated outside the processing context of the TSM and ensures that all such calls have no access rights to the tenant key store.

At the key manager ensures that just TSM storage processes are given access to the tenant key store. This was discussed at length above with reference to the .

In an embodiment at the tenant storage processes use the encryption keys to encrypt changed data written in the cloud storage environment before that changed data is stored in the cloud storage environment. So no data is written to the cloud storage environment disks without being encrypted.

According to an embodiment at the key manager decrypts the data for the tenant using the tenant storage processes at startup for a storage session between the authenticated tenant and the TSM.

Continuing with the embodiment of and at the tenant storage processes use a master key housed with the data to decrypt the encryption keys from the tenant key store.

Still continuing with the embodiment of and at the key manager uses the master key to decrypt the data within the TSM for the storage session.

The key controller presents another and in some cases enhanced perspective of the key manager represented by the method of the . Moreover the key controller is implemented or deployed within the architecture of the and utilizes the sequencing discussed with the .

At the key controller acquires a master key for a tenant when a TSM is initiated to the tenant in a cloud storage environment. Again the cloud storage environment services multiple tenants each tenant when connecting to the cloud storage environment having a TSM instantiated to service the storage of the tenant in a secure manner from the cloud storage environment.

At the key controller decrypts encryption keys using the master key when data is being read within the TSM.

At the key controller generates random additional encrypting keys and encrypts those random additional encryption keys with the master key and the encrypting additional data being written in the cloud storage environment with the random additional encryption keys.

According to an embodiment at the key controller uses a specific encryption key for each block of data being written in the cloud storage environment. Each block of data being written having a different encryption key from the other blocks. So encryption is block based and not based on the entirety of the data.

In another case at the key controller generates a new random encryption key each time any new additional data is written to the cloud storage environment.

In an embodiment at the key controller provides the encrypted random additional keys to a key daemon processing within the TSM.

Continuing with the embodiment of and at the key controller stores the master key encrypted versions of the encrypted keys and encrypted versions of the random additional keys within the cloud storage environment when the TSM is terminated.

Still continuing with the embodiment of and at the key controller uses a predefined algorithm to hide the encrypted versions of the encrypted keys and the encrypted versions of the random additional keys within the cloud storage environment.

In an embodiment the tenant data confidentiality system implements inter alia the processing associated with the methods and of the respectively using the architecture provided by the and the sequencing provided by .

The tenant data confidentiality system includes a cloud storage environment that has one or more processors memory and storage.

The memory of the cloud storage environment is configured with the key manager 501 which is implemented as executable instructions that process on one or more processors of the cloud storage environment. Example processing associated with the key manager 501 was presented above in detail with reference to the B and .

The key manager 501 is configured to maintain a key storage for a particular tenant using a particular TSM within the cloud storage environment shared by multiple other tenants. The key storage includes a master key and a plurality of encrypted encryption keys the key manager 501 only allows TSM storage processes to access the key storage.

According to an embodiment the TSM is a VM and processing environment established dynamically for the particular tenant when a storage session with the cloud storage environment is initiated.

Continuing with the prior embodiment and in some instances the key storage is hidden and stored in the cloud storage environment.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

