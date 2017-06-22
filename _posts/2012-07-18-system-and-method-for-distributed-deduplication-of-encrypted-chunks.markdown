---

title: System and method for distributed deduplication of encrypted chunks
abstract: The present disclosure relates to an advantageous system and related methods for distributed deduplication of encrypted chunks. One embodiment relates to a method for storing encrypted chunks in which an encryption key is generated independently from a chunk payload. With this method, two encrypted chunks are identifiable as having identical chunk payloads even when the chunk payloads are encrypted with different encryption keys. Other embodiments, aspects and features are also disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09037856&OS=09037856&RS=09037856
owner: Nexenta Systems, Inc.
number: 09037856
owner_city: Santa Clara
owner_country: US
publication_date: 20120718
---
The present disclosure relates generally to data storage systems. More particularly the present disclosure relates to data storage systems supporting cloud storage system protocols and providing inline distributed deduplication services.

With the increasing amount of data is being created there is increasing demand for data storage solutions. Storing data using a cloud storage service is a solution that is growing in popularity. A cloud storage service may be publicly available or private to a particular enterprise or organization. Popular public cloud storage services include Amazon S3 the Google File System and the OpenStack Object Storage Swift System .

Cloud storage systems may provide get and put access to objects where an object includes a payload of data being stored. The payload of an object may be stored in parts referred to as chunks . Using chunks enables the parallel transfer of the payload and allows the payload of a single large object to be spread over multiple storage servers.

With the increasing need for archival data storage it is highly desirable for a cloud storage system to be efficient in storing large data sets. Deduplication is one technique for substantially improving the efficiency of a cloud storage system. Deduplication identifies identical data chunks in a storage system so as to avoid storing duplicative copies of the same chunk. Distributed Deduplication is a more advanced form of deduplication that also avoids transferring duplicative copies of the same chunk over the network.

For reasons of data security and privacy for users it is also highly desirable provide end to end encryption of data chunks in a cloud storage system. End to end encryption requires chunks to be stored and transmitted only when they are encrypted.

However it is challenging to only store and transmit encrypted chunks in a distributed system while at the same time retaining the ability to determine whether two chunks are identical for data deduplication. The present disclosure provides an advantageous solution to this challenge.

The present disclosure relates to an advantageous system and related methods for distributed deduplication of encrypted chunks.

One embodiment relates to a method for storing encrypted chunks in which an encryption key is generated independently from a chunk payload. With this method two encrypted chunks are identifiable as having identical chunk payloads even when the chunk payloads are encrypted with different encryption keys.

Another embodiment relates to a method for retrieving chunks of data from a distributed deduplication storage system. In this method in response to a request for a chunk from a client an encrypted chunk payload and an encrypted chunk key are retrieved. The encrypted chunk key is decrypted and then re encrypted specifically for the client that sent the request. The encrypted chunk payload and the re encrypted chunk key are then returned to that client.

Another embodiment relates to a storage system that includes a client which generates an encryption key independently from the chunk payload. In this system two encrypted chunks are identifiable as having identical chunk payloads even when the chunk payloads are encrypted with different encryption keys.

Another embodiment relates to a storage system that includes a storage server that in response to a request for a chunk from a client retrieves an encrypted chunk payload and an encrypted chunk key. The storage server decrypts the encrypted chunk key and then re encrypts the chunk key specifically for the client that sent the request. The encrypted chunk payload and the re encrypted chunk key are then returned by the storage server to that client.

The present disclosure relates to the distributed deduplication of encrypted chunks. The method and system described herein allows for encryption of the stored chunk payload both in transit and as stored on disk. This is done to provide end to end storage encryption where the stored content is encrypted before it is transmitted to the storage server is stored in that encrypted format and is decrypted after it is retrieved. End to end storage encryption contrasts with in flight encryption which only encrypts the stored payload while it is in flight over the network and at rest encryption which only encrypts the stored payload when it is stored on non volatile media at the storage server.

A storage system that employs distributed deduplication relies on distributed components typically co located with or at least near the storage clients to use a cryptographic hash algorithm to generate an identifying fingerprint of each chunk to be stored. When a given fingerprint chunk identifier is already known by the chunk storage system it does not need to accept a duplicate copy over the network. A given chunk only needs to be accepted by the object storage system once.

End to end encryption of stored chunks is desirable to provide unified protection for data both in transit and as when it is stored. However end to end encryption is also distributed encryption. The goals of identifying common content and protecting it are in conflict. Prior efforts have either concluded that the goals were incompatible or have tailored the encryption system such that any two clients encrypting the same chunk would use the same encryption key while making that encryption key unpredictable to any not in possession of the chunk payload.

The weakness of such a solution is that deriving an encryption key from the payload creates a potentially exploitable pattern that may allow for a successful attack at less cost than a brute force linear attack. While there is no known algorithm to exploit the correlation between the chunk payload and the encryption key a storage system that relied on this method would be unable to recover should such as an attack algorithm be developed. This is because the distributed deduplication algorithm in this case is dependent on the encryption key being consistent for all clients referencing the same payload.

As described in detail below the present disclosure avoids this weakness and provides an advantageous system which uses a client generated effectively random encryption key for each chunk rather than relying on an algorithmically derived key. Although the encryption keys are randomly generated the system nevertheless enables the identification of each chunk based on a cryptographic hash of the unencrypted chunk payload. When optional compression is allowed the fingerprinting may be done either before or after compression as long as one method is selected consistently. In a preferred embodiment fingerprinting is done after compression. This will be slightly more efficient unless the fingerprint is calculated as a byproduct of the compression algorithm a requirement that would make re use of existing compression libraries difficult. The payload is only transferred or stored while encrypted with the client generated random chunk key while the chunk key is only transferred when encrypted for the target machine or user.

While the chunk servers in the presently disclosed system never store the unencrypted chunk payload the techniques described herein allow them to verify that the client supplied chunk identifier is correct. This provides a further advantage of preventing a rogue client from corrupting the distributed de duplicated chunk storage system by submitting an incorrect payload for a fingerprint for content anticipated to be uploaded by other users.

A prior system is described in Secure Data Deduplication by Mark W. Stoner Kevin Greenan Darrell D. E. Long and Ethan L. Miller 08 2008 . This prior system uses convergent encryption for distributed deduplication of encrypted chunks. Select aspects of this prior system are described below in relation to the method depicted in .

As shown after a chunk to be stored is obtained per step a chunk key may be generated per step . The generation of the chunk key is performed by applying a first hash function f1 to the payload of the chunk. This may be expressed in equation form as chunk key hash payload .

Subsequently per step the payload is encrypted using the chunk key. In equation form encrypt payload encrypt payload chunk key . The identifier for the chunk is then generated per step by applying a second hash function f2 to the encrypted payload. In equation form chunk identifier hash encrypted payload .

In addition per step the chunk key is encrypted for the client by using a client password such that the client may decrypt it. Expressed as an equation encrypt key encrypt chunk key client password . Finally per step the encrypted payload chunk identifier and encrypted key are stored in the system.

While the above discussed convergent encryption system does provide some level of data security applicants have identified certain inherent weaknesses of such a system. First because the chunk key is based on the payload such that the same content is encrypted in the same way the chunk key has a predictability that may be exploited. Second once the chunk encryption is cracked it is cracked for the entire system from that time forward. It would then be necessary for example to place all new chunks in a different system which utilizes alternate encryption.

The presently disclosed system is a new system which avoids the above discussed weaknesses of the prior convergent encryption system. First because the chunk key is effectively random in its generation the potentially exploitable predictability of the chunk key generation is avoided. Second if the encryption of one chunk is cracked the rest of the system remains secure because the chunks are encrypted with different randomly generated chunk keys. Significantly deduplication is enabled despite the fact that identical chunks are potentially encrypted with different chunk keys.

Table 1 below compares and contrasts a few aspects of the prior convergent encryption system and the presently disclosed system.

In the following discussion a chunk generally refers to a sequence of bytes found in one or more objects. If compressed which is optional the chunk may also have the attributes identifying the compression algorithm used and the resulting compressed length stored in metadata for the chunk. A chunk image refers to a persistent image of a chunk which may be maintained by a specific storage server chunk server . The specific storage server may encode the chunk payload and metadata of the chunk. A chunk identifier refers to a unique identifier of a chunk. The chunk identifier may be generated by applying a cryptographic hash algorithm to take the fingerprint of the optionally compressed payload of the chunk.

Per step a cryptographic hash is applied the optionally compressed plaintext payload so as to generate the chunk identifier. This may expressed in equation form as chunk identifier hash payload .

In addition a chunk key may be effectively randomly generated per step . If a true random number generator is not available the chunk key should be salted with as many sources as are available to the process. There are many well known techniques for generating effectively random numbers in lieu of access to a truly random input stream.

Subsequently per step the optionally compressed plaintext payload is encrypted using the chunk key. In equation form encrypt payload encrypt payload chunk key .

In addition per step the chunk key is encrypted for the target chunk server. Expressed as an equation encrypt key encrypt chunk key target server key .

Finally per step the chunk identifier encrypted payload and encrypted key are stored. Note that as shown above in Table 1 the chunk identifier and chunk key in the method of are very different from the chunk identifier and chunk key in the method of .

In one implementation of the system a client proxy may initiate an object put transaction with a manifest server . Subsequently the client proxy may perform zero or more chunk puts with chunk servers before completing the transaction with the manifest server .

The manifest servers collect information about objects as collections of chunks. The metadata stored about an object at a manifest server may include an indication as to whether or not the chunks for the object are encrypted.

The chunk servers store chunks and retrieve chunks. The chunk servers may also validate the chunk identifiers fingerprints of chunks put to them.

Note that each component of the storage system need not be on a separate computer system. For example a manifest server and a chunk server may be implemented on a same computer system i.e. the same machine and that computer system may be connected to the network . In another implementation a client proxy may also be on the same computer system .

As shown a compressed chunk payload and a chunk key to be put to the distributed deduplication system may be stored in plaintext unencrypted at the originating client proxy . The chunk payload may be compressed by the originating client proxy so as to form the compressed chunk payload and the chunk key may be generated by the originating client proxy in an effectively random manner.

The originating client proxy may send the chunk for storage in the distributed deduplication system. Before the chunk is sent an encrypted compressed chunk payload is generated by the originating client proxy . This may be accomplished by the originating client proxy encrypting the compressed chunk payload using the chunk key . Also before the chunk is sent an encrypted key may be generated by the originating client proxy encrypting the chunk key specifically for the first chunk server to be able to decrypt it. The first chunk server stores the encrypted compressed chunk payload and the encrypted key as encrypted specifically for the first chunk server .

The first chunk server may replicate the chunk for redundant storage at the second chunk server . Before the chunk is sent the chunk key is decrypted by the first chunk server and then re encrypted by the first chunk server specifically for the second server to be able to decrypt it. The encrypted compressed chunk payload and the re encrypted chunk key are then sent from the first chunk server to the second chunk server . Note that while the encryption of the payload remains the same between the first and second chunk servers the encryption of the chunk key is changed before the first chunk server sends it to the second chunk server. The second chunk server stores the encrypted compressed chunk payload and the encrypted key as encrypted specifically for the second chunk server .

As further shown the other client proxy may retrieve the chunk from the first chunk server . Before the chunk is retrieved the chunk key is decrypted by the first chunk server and then re encrypted by the first chunk server specifically for the client proxy to be able to decrypt it. The encrypted compressed chunk payload and the re encrypted chunk key are then sent from the first chunk server to the client proxy . The other client proxy stores the encrypted compressed chunk payload and the encrypted key as encrypted specifically for the client proxy .

As depicted in the Client Proxy has three inputs available when it begins to put a chunk a transaction identifier ID chunk metadata and optionally compressed chunk payload .

The transaction ID identifies the transaction that this chunk put is part of. The transaction ID may encode the object being put or modified the class of storage requested an indicator that the chunks for this object should be encrypted and a signature covering the entire transaction ID validating that it was created by an authorized manifest server . The Transaction ID may be obtained from the manifest server in an initial manifest pre put operation.

The chunk metadata includes information about the chunk. In one implementation the chunk metadata may include the compression algorithm used if any the chunk logical length and the compressed length of the chunk.

The chunk payload may be optionally compressed. Note that the list of compression algorithms that may be applied should include None so as to allow already compressed content to be effectively stored.

In step an effectively random chunk key may be generated. If a true random number generator is not available this key should be salted with as many sources as are available to the process. There are many well known techniques for generating effectively random numbers in lieu of access to a truly random input stream.

In step a single pass may be taken over the chunk payload to produce both a fingerprint chunk identifier and an encrypted chunk payload . The fingerprint may be generated by applying a cryptographic hash to the unencrypted optionally compressed chunk payload . The encrypted optionally compressed chunk payload may be encrypted using the chunk key .

The Chunk Put operation may then be initiated with a packet that is sent from the Client Proxy to the Chunk Server. The initiating chunk put packet may include the fingerprint and also request modifier which include the transaction ID and the chunk metadata . The fingerprint identifies the chunk that is being put. In a preferred embodiment the fingerprint is the target specified in an HTTP REST Manifest Put request.

The Chunk Server upon receiving the initiating packet determines in step whether it or any of its federated chunk servers already has a chunk stored with the fingerprint .

If a chunk with that fingerprint is already stored then the Chunk Server will return an acknowledgement for the Chunk Put operation to the Client Proxy. The acknowledgement packet may indicate that the chunk already exists and therefore the client need take no further action. The chunk server may then add a back reference for the fingerprint identified chunk.

In a preferred embodiment the back reference may be derived from the transaction ID . Note that the use of back references is the method chosen in the preferred embodiment to track chunk usage and to prevent wasting storage on chunks that are no longer referenced in any manifest. There are other techniques that could be applied such as a reference counter. The mechanism selected does not impact the encryption or decryption of chunks.

On the other hand if the chunk is not already stored on the Chunk Server or a federated chunk server then the Chunk Server may perform steps and . In step the Chunk Server returns a packet to the Client Proxy which prompts the client proxy to provide the encrypted chunk payload and the encrypted chunk key . The encrypted chunk key is encrypted specifically for the Chunk Server. In addition in step various data fields may be saved in association with the encrypted chunk payload once received by the chunk server. The various data fields may include the fingerprint the transaction ID the user ID and the chunk metadata .

When the Client Proxy provides the chunk payload packets which deliver the encrypted chunk payload it will also include the encrypted chunk key . The encrypted chunk key is encrypted by the Client Proxy specifically for the target Chunk Server to decrypt.

The Chunk Server performs the following operations per step to accept validate and store the new chunk and also re encrypt the chunk key for local storage. The Chunk Server decrypts the encrypted chunk key to obtain the unencrypted chunk key . The Chunk Server also decrypts the encrypted chunk payload to obtain the unencrypted chunk payload but it does not save the unencrypted chunk payload .

In addition the Chunk Server may validate the fingerprint by applying the cryptographic hash algorithm to the unencrypted chunk payload . If the Client Proxy supplied fingerprint and the Chunk Server calculated fingerprint do not match then an error response indicating a presumed transmission error may be generated and returned to the Client Proxy. Otherwise if the supplied and calculated fingerprints do match then the Chunk Server may proceed to i save the encrypted chunk payload as received ii save an encrypted chunk key which is generated by re encrypting the chunk key with a private key known only to the Chunk Server and iii save the transaction ID as the back reference for the newly stored chunk.

In accordance with an embodiment of the invention the Client Proxy may also elect to put chunks that are not encrypted. To do so the Client Proxy may vary its steps as follows. The Client Proxy does not request that the object be encrypted in the manifest pre put operation. The Client Proxy also does not generate a chunk key and does not generate the encrypted chunk payload. Finally the Client Proxy does not include the chunk key modifier in the Chunk Put operation.

If both encrypted and non encrypted chunk puts are supported then the chunk servers must maintain two sets of chunks a first set including those chunks that were received with a chunk key and a second set including those chunks that were received in plain text without a chunk key. The encrypted chunks may be stored in a manner that invokes data integrity protection from the local file system of the chunk servers. For example a cryptographic hash from the set of SHA 2 cryptographic hashes may be used. The cryptographic has may be preferably at least the equivalent of SHA 256 in terms of security. The non encrypted chunks do not require the local file system to provide this protection because the Chunk Get operation may readily validate the unencrypted chunk payload against the fingerprint chunk ID .

The Client Proxy may generate a Chunk Get Request and send it to the Chunk Server. As depicted the Chunk Get Request may include a user ID a transaction ID and the fingerprint of the chunk being requested.

Per step the Chunk Server may validate the transaction ID by checking whether it includes an authenticating signature of an authorized manifest server . If the transaction ID is determined to be not valid because it lakes the authenticating signature then an error message indicating an invalid transaction ID may be returned via a Chunk Get Response .

Per step the Chunk Server may validate the requested chunk by checking whether it has a back reference to the object referenced within named in the transaction ID . If requested chunk is determined to be invalid because it lacks a back reference to the object named in the transaction ID then an error message indicating that the chunk is not referenced may be returned via a Chunk Get Response .

If both the transaction ID and the requested chunk are validated then per step the Chunk Server may return the encrypted chunk payload and the encrypted chunk key which is encrypted for the requesting user as identified by the user ID . The encrypted chunk key may be generated by decrypting the encrypted chunk key using the private key of the Chunk Server and then re encrypting the chunk key for the requesting user such that the user will be able to decrypt it . A Chunk Get Response which is a valid response and includes the encrypted chunk payload and the encrypted chunk key may then be sent to the Client Proxy.

The Client Proxy may receive the valid response. Assuming the chunk key modifier is present such that chunk encryption is indicated the Client Proxy may decrypt the chunk key per step . The chunk key may then be used to decrypt the chunk payload per step . Lastly the decrypted chunk payload may be validated per step . The payload validation may be performed by generating a fingerprint from the decrypted payload and comparing the generated fingerprint with the fingerprint that was sent in the Chunk Get Request .

In one embodiment the system may include a process for client triggered repair of a chunk. When the Chunk Server delivers the encrypted optionally compressed chunk payload to a Client Proxy the Chunk Server includes a metadata indicator that will allow it to identify which copy of the stored chunk it referenced to fulfill this chunk get request.

Should the Client Proxy s validation of the decrypted optionally compressed chunk payload fail the Client Proxy will return a invalid chunk get notification to the chunk server identifying the chunk that failed the validation and including the metadata field indicating which copy of the chunk image had been read.

The Chunk Server will then determine whether the suspect image is in fact bad and if it is then the Chunk Server will repair or replace the bad replica using local or network copies and or RAID error correction.

In one embodiment the transaction ID obtained from the manifest server encodes whether or not the chunk for a requested object are encrypted. The transaction ID is passed with the Chunk Get Request from the Client Proxy to the Chunk Server. In one implementation the Chunk Server may determine from the transaction ID whether an encrypted chunk directory or a non encrypted chunk direction is to be used to get the chunk.

Consider the case where the Source Chunk Server is replicating an encrypted chunk to the Target Chunk Server. Both the Source Chunk Server and the Target Chunk Server are members of a group of federated chunk servers. The Source Chunk Server obtains the encrypted chunk payload and the encrypted chunk key for the chunk to be replicated. As described above the encrypted chunk payload is encrypted with the chunk key and the encrypted chunk key is encrypted with a private key of the Source Chunk Server.

In step the Source Chunk Server obtains the encrypted chunk key decrypts it and then re encrypts it for the Target Chunk Server. The result is the encrypted chunk key that is encrypted such that it may be decrypted by the Target Chunk Server.

The Source Chunk Server then sends a Chunk Replicate Request to the Target Chunk Server. The Chunk Replicate Request includes both the encrypted chunk payload and the encrypted chunk key .

Target Chunk Server receives the Chunk Replicate Request . In step the encrypted chunk key is decrypted and then re encrypted with a private key of the Target Chunk Server. The resultant encrypted chunk key encrypted with the private key of the Target Chunk Server is stored along with the encrypted chunk payload in local storage at the Target Chunk Server.

Replication of non encrypted chunks is straightforward. To replicate an unencrypted chunk merely requires performing a chunk replicate of the unencrypted chunk payload without a chunk key modifier such that there is no need to decrypt and re encrypt a chunk key .

Scrubbing of stored data requires a Chunk Server to i obtain the chunk key and decrypt it ii read the encrypted compressed chunk payload iii calculate the cryptographic hash fingerprint of the payload data iv validate the calculated fingerprint by matching it against the chunk identifier and v if they do not match then the chunk is invalid and may be for example quarantined so that the chunk will no longer be retrievable.

As shown the computer apparatus may include a processor such as those from the Intel Corporation of Santa Clara Calif. for example. The computer apparatus may have one or more buses communicatively interconnecting its various components. The computer apparatus may include one or more user input devices e.g. keyboard mouse etc. a display monitor e.g. liquid crystal display flat panel monitor etc. a computer network interface e.g. network adapter modem and a data storage system that may include one or more data storage devices which may store data on a hard drive semiconductor based memory optical disk or other tangible non transitory computer readable storage media and a main memory which may be implemented using random access memory for example.

In the example shown in this figure the main memory includes instruction code and data . The instruction code may comprise computer readable program code i.e. software components which may be loaded from the tangible non transitory computer readable medium of the data storage device to the main memory for execution by the processor . In particular the instruction code may be programmed to cause the computer apparatus to perform the methods described herein.

A method of putting an encrypted chunk to an object storage system supporting distributed deduplication the method comprising 

calculating a cryptographic hash to fingerprint an unencrypted payload by a client proxy a client or proxy acting on behalf of the client after optional compression has been applied at the client proxy 

sending a chunk put request to a chunk server that identifies the chunk to be put by a fingerprint wherein the chunk server was selected either because it is co located with the client proxy or by a consistent hashing algorithm.

determining by the chunk server whether a specified chunk identifier is already stored within a federated set of chunk servers by checking local storage of the chunk server and at least one of the chunk servers designated to store the specified chunk identifier by the consistent hashing algorithm.

indicating by the chunk server to the client proxy whether the chunk was already stored or whether a chunk payload is to be provided.

when the chunk payload is to be provided the client proxy performs steps including generating an effectively random chunk key that is not correlated with the chunk payload encrypting the chunk payload with the generated chunk key sending the encrypted chunk payload to the chunk server encrypting the chunk key for the chunk server and sending encrypted chunk key to the chunk server.

validating the encrypted chunk payload by the chunk server wherein the validating is performed by decrypting the encrypted chunk key decrypting the received payload with the decrypted chunk key calculating the cryptographic hash fingerprint of the decrypted chunk payload comparing the calculated fingerprint with the fingerprint identifying the chunk and declaring the chunk to be invalid if said fingerprints do not match.

receiving a chunk get request from a client proxy to get a chunk from a chunk server of a chunk storage system 

using a chunk identifier to determine if the chunk is already stored locally as a local chunk image at the chunk server 

if the chunk is already stored locally at the chunk server then performing a first procedure to use the local chunk image 

if the chunk is not already stored locally at the chunk server and the chunk server is not designated to store the chunk identifier by a consistent hashing algorithm then performing a second procedure to obtain a copy of a chunk image from a designated chunk server of the chunk storage system and

if the chunk is not stored in the chunk storage system then returning an error message from the chunk server to the client proxy.

re encrypting the unencrypted chunk key for the requesting client proxy or user to obtain a re encrypted chunk key 

appending a metadata field to the chunk metadata the metadata field identifying the local chunk image and

sending the re encrypted chunk key in the chunk metadata in further response to the chunk get request.

forwarding a chunk payload of the chunk image to the client proxy in response to the chunk get request 

appending a metadata field to the chunk image wherein the metadata field identifies the chunk image as being a copy of the chunk image at the designated chunk server and

sending the re encrypted chunk key to the client proxy as metadata in further response to the chunk get request.

decrypting the encrypted chunk payload at the client proxy using the chunk key to obtain a chunk payload.

validating the chunk payload at the client proxy by generating a fingerprint of the chunk payload and comparing the fingerprint against the chunk identifier 

if validation fails because the fingerprint does not match the chunk identifier then sending an invalid payload notification to the chunk server and re sending the chunk get request to the chunk server.

The method of additional embodiment 11 wherein if the invalid payload notification is received by the chunk server the chunk server responds by

if the chunk payload was obtained from the designated chunk server then relaying the invalid payload notification to the designated chunk server and erasing all local copies of the chunk and

if the chunk payload is from a local chunk image then validating the local chunk image and if the local chunk image is invalid then reparing or replacing the local chunk image using other local and or network replicas of the chunk.

In the above description numerous specific details are given to provide a thorough understanding of embodiments of the invention. However the above description of illustrated embodiments of the invention is not intended to be exhaustive or to limit the invention to the precise forms disclosed. One skilled in the relevant art will recognize that the invention can be practiced without one or more of the specific details or with other methods components etc.

In other instances well known structures or operations are not shown or described in detail to avoid obscuring aspects of the invention. While specific embodiments of and examples for the invention are described herein for illustrative purposes various equivalent modifications are possible within the scope of the invention as those skilled in the relevant art will recognize. These modifications may be made to the invention in light of the above detailed description.

