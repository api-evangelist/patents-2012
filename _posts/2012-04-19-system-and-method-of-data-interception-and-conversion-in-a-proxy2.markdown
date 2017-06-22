---

title: System and method of data interception and conversion in a proxy
abstract: An intercepting proxy server processes traffic between an enterprise user and a cloud application which provides Software as a Service (SaaS). The intercepting proxy server provides interception of real data elements in communications from the enterprise to the cloud and replacing them with obfuscating information by encrypting individual real data elements without disturbing the validity of the application protocol. To the processing cloud application real data are only visible as encrypted tokens. Tokens included in results returned from the cloud, are intercepted by the intercepting proxy server, and replaced with the corresponding sensitive real data. In this way, the enterprise is able to enjoy the benefits of the cloud application, while protecting the privacy of real data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09647989&OS=09647989&RS=09647989
owner: Symantec Corporation
number: 09647989
owner_city: Mountain View
owner_country: US
publication_date: 20120419
---
The present application claims benefit from the U.S. provisional application Ser. No. 61 479 634 filed on Apr. 27 2012 entire contents of which are incorporated herein by reference.

The present invention relates to network appliances specifically proxy servers mail transfer agents and file transfer agents and in particular to a system and method of data interception and conversion in a proxy.

Cloud computing has come to the forefront of information technology and is being adopted by organizations in all sectors and jurisdictions. Cloud computing itself can be segmented into three types Infrastructure as a Service IaaS Platform as a Service PaaS and Software as a Service SaaS .

In a SaaS model the enterprise no longer installs configures and manages the software application on their own premises and computing facilities instead the software is installed and managed by a 3rd party vendor the Cloud Vendor that amortizes the costs of the ongoing management and maintenance of the application across the plurality of customers using it. The enterprise itself merely needs to provide its users with web browser based workstations in order to access the software.

The challenges facing enterprise adoption of cloud SaaS is the loss of control and governance over the application and data itself. With the application and the underlying information customer records orders employee information etc. now residing In the cloud the enterprise may find itself unable to be compliant with jurisdictional regulatory requirements sector specific regulations and standards or their own internal security and data management guidelines. In a number of cases even encryption is not sufficient for obfuscating the data for persistence in the cloud.

One of the primary barriers to adoption of cloud based applications SaaS is the inability for an enterprise to place sensitive data into the cloud where it would be external to the enterprise environment and control. For example Swiss banks must adhere to stringent data protection laws wherein the customer information must not leave the Swiss jurisdiction. Similarly employee information must never leave the shores of Australia and personally identifying information must not leave mainland China in any format. As a result these potential Cloud application adopters are unable to adopt a solution providing for example CRM SFA Customer Relationship Management Sales Force Automation support available from salesforce.com because the data would be residing in the salesforce.com data centers in California.

Accordingly there is a need in the industry for developing improved computer methods and systems which would solve the above noted problems and avoid the shortcomings of the prior art.

There is an objective of the present invention to provide an improved system and method of data interception and conversion in a proxy.

According to one aspect of the invention there is provided a method of obfuscating data in a data object comprising 

The method further comprises transmitting the modified data object from the intercepting proxy server computer to the server computer in the cloud.

The replacing the token to be replaced further comprises formatting the real data element according to a context in the returned data object.

According to another aspect of the invention there is provided an intercepting proxy server computer comprising 

In the intercepting proxy server computer the computer readable instructions further cause the processor to transmit the modified data object from the intercepting proxy server computer to the server computer in the cloud.

In the intercepting proxy server computer the computer readable instructions further cause the processor to 

In the intercepting proxy server computer wherein the computer readable instructions for concatenating further cause the processor to add a predetermined suffix to the replacement value.

I the intercepting proxy server computer the computer readable instructions for identifying the real data element further cause the processor to 

In the intercepting proxy server computer the computer readable instructions to identify the token to be replaced further cause the processor to 

In the intercepting proxy server computer the computer readable instructions to replace the token to be replaced further cause the processor to 

In the intercepting proxy server computer the computer readable instructions to replace the token to be replaced further cause the processor to format the real data element according to a context in the returned data object.

A computer network is also provided comprising the intercepting proxy server computer described above.

According to yet another aspect of the invention there is provided an intercepting proxy server computer comprising 

In the intercepting proxy server computer the network input output TO system is further configured to transmit the modified data object from the intercepting proxy server computer to the server computer in the cloud.

In the intercepting proxy server computer the token packaging module is further configured to add a predetermined suffix to the replacement value.

In the intercepting proxy server computer the tooling module is further configured to map the data in the data object against a dictionary of attributes and identify the real data element using a corresponding attribute in the dictionary.

In the intercepting proxy server computer the tooling module is further configured to map data in the returned data object against a dictionary of attributes and identify the token to be replaced using a corresponding attribute of the returned data element of the returned data object.

In the intercepting proxy server computer the computer readable instructions further forming a decryption module configured to extract the token value from the token to be replaced and to generate the real data element by decrypting the token value.

In the intercepting proxy server computer the computer readable instructions further forming a context formatting module configured to format the real data element according to a context in the returned data object.

A computer network is also provided comprising the intercepting proxy server computer described above.

Thus the improved system and method of data interception and conversion in a proxy have been provided.

With the objective to overcome limitations of the prior art to protect sensitive data when using cloud applications a novel intercepting proxy server has been developed by PerspecSys corporation features and embodiments of which are described in the following. Disclosed are a system and methods for allowing an enterprise to utilize a cloud SaaS solution while ensuring that the sensitive data remain out of the cloud itself replaced only with obfuscated information. This allows the enterprise to remain compliant with their data management requirements as the data truly never leaves the enterprise in any format encrypted or otherwise. The proposed solution provides a means of allowing the data to be replaced with an obfuscated version of the data that is not computationally related to the original sensitive value. In this way the enterprise is able to enjoy the benefits of a cloud application such as salesforce.com while remaining compliant with any and all regulatory compliance requirements that preclude the sensitive data from leaving the enterprise in any format.

The enterprise includes one or more client devices also simply referred to as Client an Ultimate Obfuscation Solution comprising an Intercepting Proxy Server computer and a Local Persistent Storage layer and a conventional firewall .

The Ultimate Obfuscation Solution shown here inside an enterprise is shown as an example for deploying it. It is understood that there may be clients for example in the United Kingdom where a restriction exists only in that the data must not leave the country. In such a case the Ultimate Obfuscation Solution may be located in a datacenter i.e. a Hosted Ultimate Obfuscation Solution in a country with the client devices being located in one or more enterprises within the same country. The Hosted Obfuscation Solution is then capable of providing support for multiple enterprises.

The client device may be a personal computer a work station computer a laptop computer a smart device such as a mobile device or a tablet or any other computer device capable of including one or more of a web browser application also simply referred to as browser using for example standard Hypertext Transfer Protocol HTTP an electronic mail application also simply referred to as mail using for example Simple Mail Transfer Protocol SMTP and computer files also simply referred to as files which may be transferred for example using the File Transfer Protocol FTP for communicating with the Cloud by way of the Ultimate Obfuscation Solution .

The cloud application installation includes one or more Cloud Application servers and a Cloud Storage device .

The term computer is understood to mean a device that includes a processor and computer readable instructions stored in a computer readable memory for execution on the processor. Any of the computers used in the present invention may be a general purpose computer such as any of a number of commercially available computers. Alternatively each computer may be a specialized computer or a hardware device such as a programmable application specific device.

The operation of the Ultimate Obfuscating system is summarized as follows. The client communicates with the Cloud in transactions containing subject data for storing and or processing in the Cloud and receiving appropriate responses including data from the Cloud . Such transactions may involve any of the facilities in the Client including the web browser application the electronic mail application and file transfer of computer files . In such transactions the outbound subject data are intercepted and interpreted in the Intercepting Proxy Server computer where selected sensitive data elements of the outbound subject data are replaced with respective replacement values also referred to as tokens . In the following the terms sensitive data and sensitive data element will be used interchangeably with the terms real data and real data element respectively to distinguish the real data from the tokens which are their tokenized or obfuscated replacements. Each of the selected real data elements may be stored along with the corresponding replacement token in the Local Persistent Storage layer . Any tokens in the response from the Cloud are then identified by the Intercepting Proxy Server computer and the corresponding real data elements are retrieved and substituted for the tokens in the response. In this way the client interacts with the Cloud normally and transparently but any real data are hidden from the Cloud by sending tokens instead. The tokens will then be received and processed by the Cloud Application server and may be stored in the Cloud Storage device .

There are two types of obfuscating tokens resident tokens used in a Residency mode of operation and encrypted tokens used in a Privacy mode of operation. In the residency mode each real data element is stored locally i.e. resides in the Local Persistent Storage layer as described above. In the weaker privacy mode the real data element does not need to be stored locally but is encrypted into an encrypted token.

Each token is composed of a token prefix a token body and a token suffix. The token prefix and token suffix are used to delineate the token against the surrounding data in order to identify the tokens in the data stream. Token prefix and suffix are shown in bold in the examples of Table 1. The prefix may for example comprise three predetermined alpha characters followed by an underscore e.g. prs  or PJW . As this example shows the suffix may be an underscore followed by a single letter e.g. z or  Z. The length of both prefix and suffix are configurable. The requirement is that they be unique enough so as not to be part of the data itself. For example if the actual data contained ABC Z then ABC would not be a good choice for a prefix.

Table 1 shows five examples of tokenization 1 to 5 in three columns Type of Data Type of Token R for Resident Token E for Encrypted token and Example Token.

In example 1 a simple text data element such as a first name is replaced with a resident token R as prs ABDDK z.

In example 2 a simple text data element such as a first name is replaced with an encrypted token E with prefix PJW  token body which is a long string of random looking characters the result of encrypting the actual text data element and token suffix  Z.

In example 3 an email address is replaced with an obfuscation token R as prs DABCZRK z. This is followed with an email domain name such as dummymail.com in order for the combination to appear as a valid email address and so formally satisfy validation when the obfuscated data is received in the cloud.

In example 4 two text data elements are shown resulting in two type R tokens PJW DONdvcK Z and PJW DPScfpJ Z where each token is extended with a sort prefix code DO and DP respectively. As will be explained in more detail below the alphabetic sorting order of the original text data elements can be preserved in the corresponding replacement tokens by prefixing token values with the order preserving prefix code.

In example 5 an attached file is replaced by a type R token enclosed in square brackets and and separated from the prefix and the suffix by keywords ATTACH and ENDATTACH respectively.

The attachment example in 5 shows a format used for resident attachments. The format of tokens for attachments is different from other tokens in order to specifically identify them as attachments. In the example of a resident attachment shown here the value in the token is a relative path of where the file is stored. Although it is in clear text providing the location of the actual file in the Local Persistent Storage layer the file name or what is in the file is not discernible from the information in the token. The attachment example 5 of Table 1 is shown to indicate another technique of substituting tokens for real data e.g. attachments which may be performed in the Ultimate Obfuscation Solution .

The following description of embodiments of the invention however will be focused on cases of obfuscating tokens for general values i.e. text values.

The resident tokens for general values are generated by a random token generator in the Intercepting Proxy Server computer . It is noted that tokenization with randomly generated resident tokens is considered a more secure method than encryption. In tokenization the resident token contains no discoverable information related to the subject data. For example it is possible that a large amount of data including an entire attachment is represented by a relatively short resident token. For a resident token representing an attachment a reference pointer to a local directory location is used the implementation and format of which may vary depending on the cloud application requirements. On the other hand an encrypted token containing simple an encrypted version of the subject data is open to be decrypted by an Internet eaves dropper or by an adversary hacking into the Cloud Storage device as long as they have the decryption key.

The tokens variously referred to as resident token and encrypted token are also collectively referred to as index and the processes of tokenization and encrypting are similarly also referred to as indexing referring to the use of a token as a key index for storing and retrieving the corresponding real data element in a look up table or database of the Local Persistent Storage layer . The term index is used because the token for resident data is literally an index into the look up table value table . The term index is equivalent to token and the term indexing is equivalent to tokenizing .

In some cases complete obfuscation of a data element by replacement with a resident token may not be required. In this case it may be sufficient to use as replacement value an encrypted token in which the data element is merely encrypted.

With resident tokens the real data element is thus only stored locally inside of the firewall of the enterprise or the hosted environment i.e. in the Local Persistent Storage layer of the Ultimate Obfuscation Solution . The Local Persistent Storage layer may be implemented in a persistent storage device of any of a number of persistent storage technologies including but not limited to for example one or more hard disks or a solid state drive SSD . The type of data structure used in the Local Persistent Storage layer may include flat files or a database or an in memory cache within the Intercepting Proxy Server computer for example and may depend on the type of protocol and the type of data.

A simple example for tokenization may be a clear text string John Smith . The corresponding token value that may be sent to the Cloud instead could be a randomly generated token for which there is no computational method to reverse engineer it for example prs ABDEEFS z .

The primary purpose of the Ultimate Obfuscation Solution is to intercept clear text data that is outbound from the enterprise and substitute it with replacement values while preserving the application functionality. Likewise the replacement values that are now in the cloud application need to be converted back into the real values in any response data stream that is coming from the cloud application for example HTML pages XML files Spreadsheet reports etc.

The Ultimate Obfuscation Solution is designed to support interception of any data whether it is transported using the Transmission Control Protocol TCP or the User Datagram Protocol UDP or a file system for the purposes of substitution.

The Received Data Object may contain non changeable elements referred to as unmodified elements which are passed unchanged to the modified data object and one or more Element s to be replaced the Elements to be replaced being selected by a Tooling module described in more detail below.

The modified data object contains the unmodified elements of the Received Data Object and Replacement Values which are replacements for corresponding Elements to be replaced . The Replacement Value is generated by a Token Packaging function from a Token Value which is generated 

The Random Token Value generator function and the Encryption Function may be considered as alternative implementations of a token generator function.

Depending on the mode the Token Value is selected by a Mode Selector from either the output of the Encryption Function Privacy mode or the output of the Random Token Value generator function Residency mode .

In one embodiment of the invention the Token Packaging function assembles the Replacement Value by prefixing the random Token Value with a token prefix and appending a token suffix .

In the case of Residency mode a storage record including a copy of the Element to be replaced and a copy of the corresponding Replacement Value may be created. The storage record is then stored in the Local Persistent Storage layer thus preserving the value of the Element to be replaced in local storage while only the Replacement Value is forwarded to the Cloud .

In the case of Privacy mode it is not necessary to create the storage record or store it in the Local Persistent Storage layer .

What is to be intercepted is defined by a set of metadata that describes which data elements are to be extracted based upon a context and what obfuscation scheme is to be used.

The function of defining and selecting Elements to be replaced is performed in the Tooling module which includes pairs of metadata records. Each pair of metadata records corresponds to one or more Elements to be replaced and comprises a Data dictionary of Attributes and a Mapping part according to which elements are selected for intercepting. A separate set of metadata may be established for each cloud application.

The Data dictionary of Attributes includes a plurality n of individual Attributes . An Attribute is a data dictionary element that describes a data element such as for example a first name generically and comprises the following fields 

The Mapping part includes a plurality m of mappings each of which defines the mapping of a data stream element an element to be replaced to one of the Attributes . Each mapping is an association between a data element in an HTML form or XML Application Programming Interface API or other identified data element to an attribute and comprises the following fields 

Any data that is leaving the organization in the form of a web form of data an email or a file attached to a web page needs to be intercepted to replace the real data with tokens.

At the step Identify request type the type of request is identified by categorizing the Received Data Object for example in the case of an HTTP request any of the following categories may apply 

HTTP is provided as the most popular example since most cloud applications use HTTP based communications. But in general data may be any network transmitted data over TCP or UDP an example being the Simple Mail Transport Protocol SMPT and may be file system based or database based.

By categorizing the Received Data Object in the step the Intercepting Proxy Server computer is able to break up the Received Data Object into individual elements.

In the following step Identify data to be intercepted this categorization is the basis of identifying which elements remain unmodified ref and which are Elements to be replaced i.e. elements that need to be replaced with tokens or encrypted.

The metadata of the Tooling module is structured to identify by object referred to as the Record Type in the mappings which fields are to be intercepted. The Element Name of the mappings is the field name in the data structure i.e. in the Received Data Object that needs to be replaced based on its attribute .

In summary all elements comprising the data for example all fields in a HTML form are examined to determine which elements have corresponding tooling mappings.

At the step Mark data for indexing the tooling mappings are used to mark the object the Received Data Object and specific fields Elements to be replaced in the object as requiring interception.

At the step Determine Mode the Mode of the associated mapping is determined. Depending on the Mode of the associated mapping either tokenization Residency mode is invoked in the step Tokenize to generate Replacement Values for the intercepted elements or the data is encrypted Privacy mode in the step Encrypt .

The description of a preferred implementation of the look up table has been simplified for clarity. In practice the look up table may be implemented as any indexed data structure indexed by the token value e.g. as a number of flat files or a standard database or even as an in memory cache within the Intercepting Proxy Server computer instead of in the Local Persistent Storage layer .

The Returned Data Object may contain unmodified elements which are passed unchanged to the modified returned data object and one or more returned data elements which are identified as Token s to be replaced comprising Prefix Token Value and Suffix. The Token Value of each Token to be replaced is used as an index into the look up table in order to retrieve the specific key value pair record which contains the value of the Token Value as its key. In the example shown here the value of the Token Value of the Token to be replaced equals the value of the Token i . As a consequence the corresponding Value i in the Real Data column is retrieved and inserted into the data object as a Real Data Value .

As described in more detail below simply inserting the Real Data Value in place of the Token to be replaced may give rise to format errors in the modified returned data object . To avoid such problems a Context Formatting function is provided to take the context in which the token is found into account and format the Real Data Value accordingly.

Referring back to the storage records associated with the substitution of data elements to be replaced by replacement values tokens during processing of the interception request correspond to the key value pair records which are now retrieved in order to replace the tokens to be replaced with the corresponding original Real Data values which are of course equal to the original values of the respective data elements to be replaced . It is noted that the look up table may store entire storage records as described in indexing with tokens to retrieve corresponding real data values may be based solely on the stripped token values or alternatively may be based on the replacement token value including any prefix and suffix values.

As shown in real data i.e. elements to be replaced contained in a previous request by the Client for processing in the Cloud may as far as the Client can determine appear to be correctly contained in subsequent or later responses from the Cloud . In reality however the sensitive data i.e. the real data never physically left the enterprise but were kept in the Local Persistent Storage layer while the cloud application server only processed the tokens.

The Returned Data Object may contain unmodified elements which are passed unchanged to the modified returned data object and one or more Token s to be replaced . The Token to be replaced includes an encrypted Token Value which is extracted and decrypted into a Retrieved Real Data Value in a Decryption Function . The Retrieved Real Data is essentially the Real Data Value .

But as described above simply inserting the Retrieved Real Data in place of the Token to be replaced may give rise to format errors in the modified returned data object . To avoid such problems the Context Formatting function is provided to take the context in which the token is found into account and format the Retrieved Real Data into the Real Data Value accordingly.

As shown in real data i.e. elements to be replaced contained in a previous request by the Client for processing by the Cloud but encrypted by the Intercepting Proxy Server may as far as the Client can determine appear to be correctly contained in clear text in subsequent or later responses from the Cloud . In reality however the real data elements were encrypted before they physically left the enterprise and were decrypted and restored to clear text by the Intercepting Proxy Server in responses from the Cloud .

To summarize all data coming back from the cloud application is checked for obfuscating or encrypted tokens and those tokens are converted back into real data values.

At the step Identify content type the Returned Data Object received by the Intercepting Proxy Server in the data stream from the Cloud may contain different types of content. Depending on the content type the processing of the stream may vary. For example in the case of an attachment the whole data stream is only the attachment so processing can be optimized. In most cases the data stream is processed and obfuscated information is extracted for conversion to clear text.

At the step Identify Tokens by mode and pattern the tokens are stripped from the content by identifying the prefix and suffix. Resident Tokens representing locally stored real data values are processed differently from encrypted tokens.

At the step Security Mode the Mode of obfuscation is determined from the Attribute to which the token is mapped i.e. Residency mode using resident tokens or Privacy mode which uses encrypted tokens .

If the Mode is Privacy the token values are merely decrypted in the step Decrypt Tokens which yields the real data values and execution continues with the step . If the Mode is Residency the real data values are retrieved in the step Lookup Real Data Values by using the token values to index the lookup table in the Local Persistent Storage layer as described above . The token to value map i.e. the look up table may be partly cached in the memory of the Intercepting Proxy Server computer to speed up access.

The tokens are identified and their position and context in the data stream i.e. in the Returned Data Object are recorded.

At the step Format Real Data Values the retrieved or decrypted real data values see steps and above are formatted by the Context Formatting function according to the context of the data in the Returned Data Object which is the same as the context of the data in the modified returned data object .

At the step Insert Formatted Real Data values the formatted Real Data Values which are replacing the corresponding Tokens to be replaced are inserted into the result data stream i.e. into the modified returned data object .

One of the challenges when obfuscating data via tokenizing real data elements with obfuscating or encrypting tokens as described above is the loss of certain characteristics of the data one of which is the sort order. Depending on the context the obfuscated data may still require to be rendered by the Cloud via a report an ordered list a view on a web page etc. in the sorted order without revealing the original values. In another embodiment the present invention provides a technique that allows data to be obfuscated via whatever encoding method is required in order to preserve the security of the value being revealed while at the same time preserving the sort order to a configurable degree of accuracy so as to be usable in contexts that render ordered lists.

One of the characteristics of encryption is the inability of most encryption algorithms to preserve sort order. The manner in which encryption is performed typically renders the resulting encrypted value unusable for sort ordering. This means that in a data management context such as reporting list viewing or other human readable applications of the data the rendering of the list of data frequently must be performed using the real values. However there are a number of contexts and use cases that require the data to be ordered even if tokenized or encrypted.

While there are known techniques for preserving sort ordering while obfuscating the original data values there is a trade off of data security versus data ordering accuracy. For example one technique to preserve sort ordering while performing data obfuscation is to use a sort order preserving data compression algorithm such as described in U.S. Pat. No. 5 270 712 issued to Iyer et al. This compression algorithm utilizes a derivative of the Ziv Lempel compression technique involving a tree structure for data compression. The challenge with this technique is that while it renders the original data obfuscated and preserves the original data sort order it is not very secure because the encryption would be fairly easy to break. In a structured application context for example the list of data may be first names states provinces or cities. Knowledge of the domain of the data would enable an attacker to easily guess at a first couple of tree branches in the structure and then leave the rest of the decoding to a dictionary attack. The dictionary attack would provide the attacker with enough information to reconstruct the rest of the encoding tree allowing the attacker to then decode any other real values encoded using that tree structure.

The solution proposed here is a hybrid approach to the generation of a sort order preserving obfuscated value by prefixing the already obfuscated replacement value with a sort prefix code.

Essentially a Liv Zempel technique is used to generate a sort prefix code which may represent all or only the first few characters of the real data value. As described earlier each sensitive real data value may have been encoded using standard encryption yielding an encrypted token or may have been replaced entirely with a resident token. The resulting token value is encapsulated with Prefix and Suffix codes see and example 4 in Table 1. By extending or replacing the Prefix with the sort prefix the rendering of the data in a list report or other context based on the obfuscated value can be performed in an ordered fashion but the value is not as susceptible to the attack problems discussed earlier.

Preferably in order to enhance security not the entire real data value is encoded using the sortable compression algorithm but only the first few characters are used. Depending on the actual sort accuracy requirement this may be the first character alone the first few characters or a configurable number of characters.

The Sort Replacement Value is composed of a Sort Prefix concatenated with the Token Value and the token Suffix . The Token Value is generated by the Random Token Value generator function as described above. Similarly the value of the token Suffix is chosen for delineating the Sort Replacement Value as described earlier.

The Sort Prefix is generated by a Liv Zempel Compression function from a Front Portion of the Element to be replaced .

In this way any rendering of a list of the encoded values i.e. the sort replacement values would come arbitrarily close to the sort order of the original values depending on the chosen length of the Front Portion . This technique of combining the Liv Zempel Compression on a selected front portion of the data element with the random token value has the virtue of not being as susceptible to the attack described above. An attacker may still be able to determine the first character with some level of certainty but since they would no longer have all of the characters encoded within the Liv Zempel tree the token is no longer susceptible to a dictionary attack. Instead the remainder of the Sort Replacement Value is tokenized or may be encrypted neither of which is related to the Liv Zempel tree and hence not susceptible to a dictionary attack to determine the actual value.

The tradeoff is the degree of sort order accuracy. By only using the first few characters of the actual value as the sort characters it may not be perfectly sortable. However depending on the context a perfect sort may not be required. The first few characters may be more than sufficient for sorting a small set of data with a relatively even distribution of sorted data across the alphabet. The technique described is not only applicable to strings composed of single byte characters but also to multi byte character sets and even mixed characters within a UTF 8 or UTF 16 set of data.

As shown in already the Token Values are generated by a Random Token Value generator function in the Residency mode. In the Privacy mode the Token Values are simply generated by encrypting the Elements to be replaced in the standard Encryption Function . The appropriate Token Value as selected in the Mode Selector is then prefixed with the Sort Prefix and the Token Suffix is appended.

When an instance of a Sort Replacement Value is returned from the Cloud as the Token to be replaced in the Returned Data Object see the corresponding Real Data Value is recovered from the look up table as shown in which applies in Residency mode of operation. In the Privacy mode decrypting the encrypted token value returns the original clear text value. In either mode the sort prefix is merely for use by the Cloud in the rendering of the data to provide a specific degree of sorting accuracy.

The Intercepting Proxy Server computer is a computer equipped with software programs for enabling the features of the embodiments of the invention to be described below. Some or all of the functions of the Intercepting Proxy Server computer may also be implemented with an Application Specific Integrated Circuit ASIC or a number of ASICs.

The Processor may be any commercial processor capable of executing programs under an operating system such as but not limited to Linux Microsoft Windows or Mac Operating System 10 OSX for example comprising a Central Processing Unit CPU a Network Input Output I O system and a Command Interface .

The CPU may be any of a number of commercial processor implementations including a multi processor. The Network Input Output I O system provides an interface facility to the Internet via the optional Firewall and to the Client see . The Command Interface may include a keyboard mouse and visual interface as well as removable storage devices or any other hardware suitable for controlling a software configuration as well as the operations of the Intercepting Proxy Server computer .

The Processor is connected to the Computer Memory which is preferably a non transitory memory device such as dynamic memory DRAM capable of storing software programs and related data. Software modules which include computer executable instructions for execution by the Processor are stored in the Computer Memory comprise the Tooling module a Token Packaging module for performing the Token Packaging function a Random Token Value generator module for performing the Random Token Value generator function an Encryption Engine for performing the Encryption Function a Context Formatting module for performing the Context Formatting function and a Liv Zempel Compression Engine for performing the Liv Zempel Compression function .

In some embodiments of the invention the Random Token Value generator module and the Encryption Engine are combined into a Token Generator module .

The Computer Memory may also include a Cache for temporarily storing a full or partial copy of data such as the Look Up Table which is preferably more permanently stored in the Local Persistent Storage layer .

The Processor is also connected to the Local Persistent Storage layer which may be implemented in any of a number of persistent storage technologies including but not limited to for example a hard disk or a flash drive. Data stored in the Local Persistent Storage layer may also be stored simultaneously in the Computer Memory for periods while it is actively being used by the Processor .

The Local Persistent Storage layer is used for storing persistent information primarily configured information as well as information regarding cloud applications that are being used by the Client such as a set of the application specific metadata records for use by the Tooling module comprising the Data dictionaries of Attributes and the Mapping parts .

Methods and apparatus for intercepting transactions between a client and a cloud application have been described in a number of embodiments including encrypting real data into tokens Privacy mode replacing real data with token of random value Residency mode and combining the tokens with sort order preserving prefixes. These techniques can be used individually or in combination on the data elements of client to cloud traffic for the purpose of disguising or hiding sensitive data and for enhancing the usability of the obfuscated information by the cloud application in some instances.

It is also understood that the methods of obfuscating data of the embodiments of the invention can also be used in various other software applications i.e. other than cloud computing where obfuscating of data may be required.

Although embodiments of the invention have been described in detail it will be apparent to one skilled in the art that variations and modifications to the embodiments may be made within the scope of the following claims.

