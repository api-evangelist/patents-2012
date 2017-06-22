---

title: Efficient, high volume digital signature system for medical and business applications
abstract: The system relates to a method for collecting signatures from pre-validated signers. In one aspect of the method, a pre-validated signer's signature is affixed to an electronic document in an appropriate location after the pre-validated signer authorizes the use of his or her signature.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08667290&OS=08667290&RS=08667290
owner: 
number: 08667290
owner_city: 
owner_country: 
publication_date: 20120727
---
This application claims priority to provisional application 61 513 506 filed Jul. 29 2011 the entire contents of which are incorporated herein by reference.

This invention relates to methods and systems for obtaining efficient high volume certified digital signatures which may be suited for use in business medical legal engineering and other applications.

Presently authorizing signatures are a necessary part of the work environment. Timed and dated authorizations or orders a clear sequence of responsibility are needed in engineering legal business financial and medical operations. Often obtaining these signatures is an efficiency limiting factor in these processes be it for a purchase order authorization to begin an engineering procedure singing a contract or medical orders.

One of these work environments is the medical environment where large numbers of timely secure physician authorizations are necessary for patient care billing procedures medicolegal protection and reviews by certifying agencies. Often dozens or even more than provider physician signatures are needed per day per medical facility. One problem that may arise is that often the signer is in a remote location. Obtaining these signatures reliably is time consuming for the provider and troublesome for the administrations of medical facilities.

Timely confirmation of medical orders is considered an important patient safety measure by The Joint Commission of Accreditation of Healthcare Organizations JCAHO and the Center for Medicaid and Medicare Services CMS . Similarly in the business legal engineering and financial environments obtaining timely legally verifiable signatures is often a procedural rate limiting step be it for a purchase order a contract to be signed or an engineering procedure to be authorized.

Current commercially available internet based digital signature systems such as DocuSign Echosign and AgreenSign are not intended for efficient high volume authorizations. These services may be slow and somewhat complex to use for the casual user. Security certificates of digital signatures may be weak. They do not use two factor user identification and generally rely on insecure means such as unencrypted email for transmission of important documents. Furthermore these services are not optimized for efficient smartphone or other mobile device use. While Xyzmo.com is oriented to smartphones its usage may be cumbersome and document security and verifiability is suboptimal. None of these services are properly sequenced for efficiency security and ease of use. Rather these solutions are intended for episodic use by specifically trained clerical personnel.

The majority of skilled nursing facilities assisted living facilities and many long term acute care hospitals still use paper systems and will not be converted to fully electronic medical records for years if ever. Freestanding medical service centers such as physical therapy surgicenters and outpatient rehabilitation centers need physician signatures for billing and documentation purposes. Homecare agencies infusion pharmacies durable medical equipment agencies also often use electronic systems for tracking billing and medical documentation. All of these agencies or facilities generate thousands even multiples of tens of thousands of signature requests of providers per year. Most commonly these remote signatures include telephone orders related to direct patient care review of critical new patient information such as laboratory data or radiology data confirming plans of care and certifying patients needing hospitalization transfer or placement in a facility. Obtaining these authentications is troublesome and time consuming process for both the medical organization and for the provider.

Efforts to fax paper copies of these important documents for signature to a physician s office or emailing the documents to the physician have not successfully addressed the problem. Often days or weeks go by before the provider signs the document. He she often doesn t time and date the signature. Time shuffling papers and faxing is required of the provider s office personnel and of the personnel of the requesting facility. A simple efficient method to accomplish this task is needed.

Patient safety organizations such as JCAHO recommend that telephone orders and critical labs be reviewed within 48 hours but that simple goal has not been achieved often and is widely considered impractical. Clearly 48 hour delays for review of potentially harmful orders and urgent patent information is not adequate either. What is needed is a near real time review by the provider no matter where the provider is.

Medical informatics has special security requirements to guard and keep confidential personal health information PHI . The Health Insurance Portability and Accountabilty Act of 1996 HIPAA has strict requirements as to how PHI can be safely and securely handled for the patient. Any instrument used to review patient data or orders must comply with these requirements.

Electronic Medical Record systems EMR are rapidly coming into use in acute care hospitals because the HITECH Act actually requires them to adopt EMR and actually pays them to do so. Many of these systems are admirably secure and comprehensive but they do not address the need for remote rapid efficient high volume digital signatures. They may require the provider to sign in via a remote terminal. During most of the day physicians are not sitting in front of a computer and therefore the need is unmet. However most North American physicians now use mobile devices with internet access which are with them all day. A method that allows them to promptly review and sign from these mobile device is needed.

The High Volume Digital Signature System HVDSS described here is a novel solution to the problems described above both in the medical environment and in the other cooperative activities such as engineering projects corporate executive procedures and business contracts and communications. The solutions described here exist in both a paper to digital form as well as a fully electronic form.

Therefore it is an object of this invention to provide an improvement which overcomes the aforementioned inadequacies of the prior art devices and provides an improvement which is a significant contribution to the advancement of the electronic or digital signature art.

Another object of this invention is to provide a high volume digital signature system which improves the efficiency and workflow of obtaining digital signatures.

The foregoing has outlined some of the pertinent objects of the invention. These objects should be construed to be merely illustrative of some of the more prominent features and applications of the intended invention. Many other beneficial results can be attained by applying the disclosed invention in a different manner or modifying the invention within the scope of the disclosure. Accordingly other objects and a fuller understanding of the invention may be had by referring to the summary of the invention and the detailed description of the preferred embodiment in addition to the scope of the invention defined by the claims taken in conjunction with the accompanying drawings.

For the purpose of summarizing this invention the invention comprises a High Volume Digital Signature System which improves the efficiency and workflow of obtaining digital signatures in the business engineering legal or medical environment in which large numbers or especially rapid digital signatures are required. The prototype is the medical environment in which nursing homes hospitals homecare services or free standing medical service centers need a high volume of prompt secure signatures from medical providers.

The HVDSS works in part via a pre validated closed network of designated signers which allows an efficient and secure routing. The system may also allow convenient viewing and rapid signing of documents.

The foregoing has outlined rather broadly the more pertinent and important features of the present invention in order that the detailed description of the invention that follows may be better understood so that the present contribution to the art can be more fully appreciated. Additional features of the invention will be described hereinafter which form the subject of the claims of the invention. It should be appreciated by those skilled in the art that the conception and the specific embodiment disclosed may be readily utilized as a basis for modifying or designing other structures for carrying out the same purposes of the present invention. It should also be realized by those skilled in the art that such equivalent constructions do not depart from the spirit and scope of the invention as set forth in the appended claims.

The label is preferably affixed to a paper document which requires a signature. Preferably the label is affixed on the document in the location in which a signature is desired. The unique identifier may be stored in a datastore such as a database. The unique identifier may be used to uniquely identify the respective document to which the label has been affixed.

The machine readable identifier may be any machine readable indicia such as a barcode 2D Matrix barcode as illustrated a datamatrix code a QR code or the like. The machine readable identifier is used when the document is scanned to assist in determining the appropriate routing of the document to gather the necessary signature s .

The label may also include priority information . The priority information may be used to indicate to the signer that the document to be signed requires immediate attention or some other priority related information.

Once the label is affixed to the document the document may be submitted to a device of a pre validated signer by operation of a method in accordance with the present disclosure. In one embodiment the document may be scanned into a computing system. The scanning operation may review the label and determine from the machine readable identifier the appropriate routing for the document.

In a preferred embodiment a datastore stores a mapping between the document identifier and the pre validated signer. When the document is scanned the machine readable identifier is analyzed by the computing process which looks up the unique identifier indicated on the label . In another embodiment the machine readable identifier contains the same information as the unique identifier in a machine readable format. In yet another embodiment the scanning process scans the unique identifier and performs character recognition such as Optical Character Recognition to determine the unique identifier .

Once the unique identifier is determined the system may lookup the appropriate signer to direct the document to in accordance with the present disclosure.

In another embodiment documents to be signed need not be scanned. Instead such documents may be generated electronically for instance from a computer workstation. In one example of such an operation a specialized print driver is configured on the work station so that when a user prints the desired document to the specialized print driver the document is automatically routed in the system in accordance with the present disclosure. In such an embodiment the user may also optionally be presented an opportunity to define where in the document the electronic signature should be placed.

In another example of such an operation a user may drag and drop electronic files for instance PDFs word processing documents etc. into the system. depicts an illustrative example of an interface to permit a user to add additional electronic documents into a system in accordance with the present disclosure. Through this interface after a document is loaded a user may designate where the signature is to appear on the final signed electronic document.

Once a document is in the system to be signed it must be routed to one or more pre validated signers. through depict illustrative interfaces that may be displayed to a pre validated signer enabling the pre validated signer to review the respective document and either sign it or reject it.

When a document is ready to be signed a notification is preferably sent to the signer. The notification may be sent instantly or may be scheduled for some later delivery period. For instance notifications may be sent only once a day hourly or other preconfigured time period. Additionally a signer may be permitted to specify any desired schedule during which she or he wishes to receive signature requests.

In one embodiment the priority associated with a document may be used in determining an appropriate notification timing sequence. For example the system may be configured to enable high priority documents to be delivered immediately while leaving routine documents for a later delivery schedule.

As mentioned earlier when a signer registers with the system the signer indicates a device through which the signer is willing to utilize the system. The device may be any device which can be communicatively coupled with the system. Preferably the device is a smartphone. The device may also be a computer a fax machine an IP address or the like. Each device the signer wishes to utilize with the system should be pre registered with the system.

Clicking on the link in may present the signer with an interface as depicted in . As shown in the signer is given an opportunity to log into the system by providing appropriate credentials.

Once authenticated the signer is presented with pending signature requests as depicted in . In one embodiment the signer may also review archived signatures and configure other preferences.

If the signer approves of the signature she or he may click the appropriate approval button. Optionally the system may present a confirmation screen as depicted in . If the user confirms the authorization an image of the signer s actual physical signature is affixed to the electronic document. In a preferred embodiment as shown in a time and date stamp is also affixed.

If the signer rejects the signature by clicking the appropriate button a confirmation screen as depicted in may be presented. In a preferred embodiment a list may be provided to the signer of common reasons for rejection such as the signer not being an appropriate person to sign the document. In one embodiment rejected documents may store a notation such as a hash mark in the signature region.

The interface depicted in may allow the signer to cycle through a number of documents very quickly thus enabling efficient and high speed review of documents and collection of necessary signatures.

Once a signer has authorized his or her signature the signer s electronic signature is stored within the document as shown in

When adding a new user certain user information may be collected as shown in . Next as shown in a registration form may be printed. The registration form as shown in will be provided to the user and may be used to collect the user s signature in the signature region . The signature collected in the signature region is preferably stored in a datastore. This signature is then affixed to documents signed in accordance with the present disclosure.

The datastore may be any system capable of storing electronic information but is preferably a database. In one preferred embodiment a noSQL database system is utilized. In another preferred embodiment a sparse distributed persistent multidimensional sorted map is utilized. In another preferred embodiment a relational database system is utilized. In other embodiments the datastore may be a flat file an XML file or a filesystem.

Once the executed registration form has been received an account verification process may take place as shown in . These screens help to insure the device to be registered actually belongs to the signer intending to register the device.

Users of the system other than pre validated signers gain benefit from its features. For instance depict some other capabilities which may be presented in a separate mode of operation for instance Clerical Mode as described in

In one embodiment the Clerical Mode does not require a user to authenticate himself or herself. Instead only certain pre registered machines may be permitted to operate in such a mode. For instance only network verified machines may be permitted to operate in such a mode. Such machines may be for example those machines on an internal network at a medical facility that are known to be protected.

Through this limited operational Clerical Mode a user may be able to print reports search the status of specific documents or print new labels for paper systems. Clerical Mode may not permit viewing of the actual documents so as to protect privacy.

Returning to a user may use a number of criteria to generate various reports. For example the user may search for all documents sent to a particular device such as a particular fax machine.

The user may also create additional labels as shown in and . The user may enter appropriate information and the system will generate the proper type and number of labels .

The system may also permit the user advanced design capabilities for designing the labels ads depicted in . Here a user may customize paper or electronic labels to fit the particular needs. Once any device has been registered and validated with the system that device may be used to generate new labels.

Additionally a user may create more advanced routing directives. For example a user may require that once a first person has signed a document the document must be routed to a second person. This information is preferably stored in the datastore. Thus when the system or method in accordance with the present disclosure receives the first signer s authorization it may pass the document along to the next signer required to sign the document.

Communication between the faxing service provider and the application servers may be via any reasonable communication capability including a network intranet local network WIFI Bluetooth or other communication capability. Preferably the communication is encrypted to protect the information in transit and SSL is preferred.

The application servers are configured to execute steps in accordance with the present disclosure. The system and method may be implemented on one or more computing systems which can include a personal computer a workstation a network computer a hand held computer or any other computer system. Further the system can be written as a software program in any appropriate computer language.

The system may preferably include a processing device which can be any computer processing unit and could be a central processing unit or a number of processing units configured to operate either in sequence or in parallel. The processing device may be configured to execute software processes which implemented the steps disclosed herein. The system may also include a memory capable of storing the steps necessary for a processing device to implement the steps disclosed herein. This memory could be in the form of memory resident within the processing device or in the form of standalone memory coupled to the processing unit via a communication path such as a bus or a network.

Application servers communicate with the pre validated signers through the devices previously registered. Preferably this communication is also encrypted with SSL being preferred.

At step the system must determine how to send the authorization request to the signing individual thus the system looks up this information. Preferably the information is stored in the datastore . At step the system notifies the signing individual that there are documents requiring signature.

At steps and upon receipt of the notification the signing individual the doctor authenticates himself or herself with the system and is then presented a list of documents to be signed.

The signing individual may then authorize or reject the pending documents at steps and . When the signing individual approves the document step the information is recorded preferably in the datastore and then the signed document may be sent back to the original facility at step . In a preferred embodiment the signed document that is sent back includes a copy of the signing individuals signature as previously recorded when the signing individual registered with the system.

The datastore may be a single universal datastore or each facility may have its own datastore . Additionally the datastore may be implemented on a single machine or may be implemented on a number of machines.

Application servers at in combination with Application Programming Interfaces may be utilized to combine the functionality of the present disclosure with the customer s specific needs. In such a configuration the customer may store its data privately and separate from the datastore required to manage the signature process in accordance with the present disclosure.

In another embodiment a user may track a paper document utilize a scanning device. The scanning device may preferably be a smartphone configured to scan a label on the paper document but could be any sufficient scanning device. The scanning device may first preferably require the user authenticate himself or herself with the system. The scanning device would then interface with the datastore to gather information related to the respective label . Through this embodiment users may track the progress of document signatures using either the administrative control panel or by way of a handheld scanning device.

In one embodiment upon scanning a paper document with the scanning device a lookup is performed in the datastore returning whether or not the signature was approved rejected or not found. The lookup may also return time and date information associated with the signature process for instance when the signature was approved or rejected. If the document is found a link may also be provided permitting the user of the scanning device to view an electronic version of the document.

In another embodiment the label may include a radio frequency identifier RFID . In such an embodiment the RFID may be utilized by the scanning device to scan a plurality of documents at once. The scanning device in such an embodiment would be capable of reading the RFIDs to gather the necessary information.

The present disclosure includes that contained in the appended claims as well as that of the foregoing description. Although this invention has been described in its preferred form with a certain degree of particularity it is understood that the present disclosure of the preferred form has been made only by way of example and that numerous changes in the details of construction and the combination and arrangement of parts may be resorted to without departing from the spirit and scope of the invention.

