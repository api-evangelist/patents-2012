---

title: Methods and devices for data retrieval
abstract: Methods and device are disclosed for data retrieval. At first images and reports are analyzed by respective parser units to detect both structures and text passages that are related to respective structures and text passages of a knowledge data-base. The detected structures and text passages are stored together with a unique resource located that identifies the respective structure and/or text passage at the knowledge database in a semantic annotation database. In addition a feature extraction can be performed to provide specific features of the images and/or regions of the images, whereby the features are stored in an image feature database. Finally an input query can ask questions that are used to provide a result to the query based on the semantic annotation database and the image feature database. The methods and devices may be used for data preparation and data retrieval of medical images and associated medical reports.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09575994&OS=09575994&RS=09575994
owner: Ludwig-Maxmilians-Universitat
number: 09575994
owner_city: Munich
owner_country: DE
publication_date: 20120210
---
The present application hereby claims priority under 35 U.S.C. 119 to European patent application number EP 11154185 filed Feb. 11 2011 the entire contents of which are hereby incorporated herein by reference.

At least one embodiment of the invention generally relates to methods and devices for data retrieval.

Diagnosis and treatment planning for patients can be significantly improved by comparing the patient s images with clinical images of other patients with similar anatomical and pathological characteristics where the similarity is based on the understanding of the image content. There are two kinds of search semantic search in patient records structured data and similarity search on images using low level image features.

The first requires semantically annotated images i.e. labeled image regions using a common vocabulary from a knowledge databases. This structured information is stored side by side with the images. For storing semantic information and background knowledge one often uses ontologies. The second search type uses similarity metrics based on pixel intensities.

With these two query methods the user can search the content of images texts and other clinical values acquired at the hospital for similar medical cases.

Current systems show weak search capabilities. Therefore the user must remember a similar medical case and search by the patient s name.

The inventors have discovered that presently there are no methods or devices available that enables combined use of two queries.

Hence at least one embodiment of the invention is directed to providing methods and or devices that enable combined use of queries based on semantic search in structured data and image similarity search comparing visual structures such as pixel intensities.

At least one embodiment of the invention relates to a method for data retrieval of a final result list comprising 

At least one embodiment of the invention relates to a device for data retrieval of a final result list comprising 

It should be noted that these Figures are intended to illustrate the general characteristics of methods structure and or materials utilized in certain example embodiments and to supplement the written description provided below. These drawings are not however to scale and may not precisely reflect the precise structural or performance characteristics of any given embodiment and should not be interpreted as defining or limiting the range of values or properties encompassed by example embodiments. For example the relative thicknesses and positioning of molecules layers regions and or structural elements may be reduced or exaggerated for clarity. The use of similar or identical reference numbers in the various drawings is intended to indicate the presence of a similar or identical element or feature.

Various example embodiments will now be described more fully with reference to the accompanying drawings in which only some example embodiments are shown. Specific structural and functional details disclosed herein are merely representative for purposes of describing example embodiments. The present invention however may be embodied in many alternate forms and should not be construed as limited to only the example embodiments set forth herein.

Accordingly while example embodiments of the invention are capable of various modifications and alternative forms embodiments thereof are shown by way of example in the drawings and will herein be described in detail. It should be understood however that there is no intent to limit example embodiments of the present invention to the particular forms disclosed. On the contrary example embodiments are to cover all modifications equivalents and alternatives falling within the scope of the invention. Like numbers refer to like elements throughout the description of the figures.

Before discussing example embodiments in more detail it is noted that some example embodiments are described as processes or methods depicted as flowcharts. Although the flowcharts describe the operations as sequential processes many of the operations may be performed in parallel concurrently or simultaneously. In addition the order of operations may be re arranged. The processes may be terminated when their operations are completed but may also have additional steps not included in the figure. The processes may correspond to methods functions procedures subroutines subprograms etc.

Methods discussed below some of which are illustrated by the flow charts may be implemented by hardware software firmware middleware microcode hardware description languages or any combination thereof. When implemented in software firmware middleware or microcode the program code or code segments to perform the necessary tasks will be stored in a machine or computer readable medium such as a storage medium or non transitory computer readable medium. A processor s will perform the necessary tasks.

Specific structural and functional details disclosed herein are merely representative for purposes of describing example embodiments of the present invention. This invention may however be embodied in many alternate forms and should not be construed as limited to only the embodiments set forth herein.

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are only used to distinguish one element from another. For example a first element could be termed a second element and similarly a second element could be termed a first element without departing from the scope of example embodiments of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion e.g. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of example embodiments of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. As used herein the terms and or and at least one of include any and all combinations of one or more of the associated listed items. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

It should also be noted that in some alternative implementations the functions acts noted may occur out of the order noted in the figures. For example two figures shown in succession may in fact be executed substantially concurrently or may sometimes be executed in the reverse order depending upon the functionality acts involved.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which example embodiments belong. It will be further understood that terms e.g. those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

Portions of the example embodiments and corresponding detailed description may be presented in terms of software or algorithms and symbolic representations of operation on data bits within a computer memory. These descriptions and representations are the ones by which those of ordinary skill in the art effectively convey the substance of their work to others of ordinary skill in the art. An algorithm as the term is used here and as it is used generally is conceived to be a self consistent sequence of steps leading to a desired result. The steps are those requiring physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of optical electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like.

In the following description illustrative embodiments may be described with reference to acts and symbolic representations of operations e.g. in the form of flowcharts that may be implemented as program modules or functional processes include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types and may be implemented using existing hardware at existing network elements. Such existing hardware may include one or more Central Processing Units CPUs digital signal processors DSPs application specific integrated circuits field programmable gate arrays FPGAs computers or the like.

Note also that the software implemented aspects of the example embodiments may be typically encoded on some form of program storage medium or implemented over some type of transmission medium. The program storage medium e.g. non transitory storage medium may be magnetic e.g. a floppy disk or a hard drive or optical e.g. a compact disk read only memory or CD ROM and may be read only or random access. Similarly the transmission medium may be twisted wire pairs coaxial cable optical fiber or some other suitable transmission medium known to the art. The example embodiments not limited by these aspects of any given implementation.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise or as is apparent from the discussion terms such as processing or computing or calculating or determining of displaying or the like refer to the action and processes of a computer system or similar electronic computing device hardware that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

Spatially relative terms such as beneath below lower above upper and the like may be used herein for ease of description to describe one element or feature s relationship to another element s or feature s as illustrated in the figures. It will be understood that the spatially relative terms are intended to encompass different orientations of the device in use or operation in addition to the orientation depicted in the figures. For example if the device in the figures is turned over elements described as below or beneath other elements or features would then be oriented above the other elements or features. Thus term such as below can encompass both an orientation of above and below. The device may be otherwise oriented rotated 90 degrees or at other orientations and the spatially relative descriptors used herein are interpreted accordingly.

Although the terms first second etc. may be used herein to describe various elements components regions layers and or sections it should be understood that these elements components regions layers and or sections should not be limited by these terms. These terms are used only to distinguish one element component region layer or section from another region layer or section. Thus a first element component region layer or section discussed below could be termed a second element component region layer or section without departing from the teachings of the present invention.

At least one embodiment of the invention generally relates to methods and devices for data retrieval. At first images and reports are analyzed by respective parser units to detect both structures and text passages that are related to respective structures and text passages of a knowledge database. The detected structures and text passages are stored together with a unique resource located that identifies the respective structure and or text passage at the knowledge database in a semantic annotation database. In addition a feature extraction can be performed to provide specific features of the images and or regions of the images whereby the features are stored in an image feature database. Finally an input query can ask visual and textual questions that are used to provide a result to the query based on the semantic annotation database and the image feature database. The methods and devices may be used for data preparation and data retrieval of medical images and associated medical reports.

In the following a term system is equivalent to the method or an associated device executing the method.

The respective text reports describe a content of the respective images. The reports are often generated by clinical staff to describe the respective images for documentation purpose.

In an embodiment of the invention the detection of structures in the at least one image includes segmenting anatomy and pathological structures. Herewith at least one embodiment of the invention can be used for improving the quality of diagnosis in the healthcare sector.

If the previous embodiment uses software detectors to perform the detection a cost effective and flexible realization of the detection is provided.

Hereby a quality of detecting structures based on known structures or similar structures stored in the knowledge database can be achieved.

In another embodiment the storing of the detected structure includes a storage of a reference information to the at least one image that is stored on an image database. Hereby storage space in the semantic annotation database can be reduced because the reference information requires less storage space than the entire image or a part of the image.

Further to the previous embodiment the storing of the detected structure includes a storage of a bounding box that defines a region of interest in the at least one image whereby the region of interest represents an image area that covers the detected structure. By using the bounding box a location of a relevant structure can be described in a more precise way compared to the case when a reference relates to an entire image.

Hereby a quality of detecting the text passage based on known text passages stored in the knowledge database can be achieved.

In another embodiment of the invention the storing of the detected text passage includes a storage of a reference information to the at least one report that is stored on a report database. Hereby storage space in the semantic annotation database can be reduced because the reference information requires less storage space than the entire report or a part of the report.

In another embodiment of the invention the first semantic annotation and the second semantic annotation are stored together at one place on the semantic annotation database. This will result in a boost of the available knowledge for the semantic search.

In another embodiment of the invention the computing of at least one feature includes a generation of a low level feature such as gradient or histogram features. Hereby a generation of classification of features can be provided in a low complex but very efficient way.

In an extension of the previous embodiment the generating of the low level feature includes a determination of a bounding box that defines a region of interest in the at least one image whereby the region of interest represents an image area that is used to generate the at least one feature. By using the bounding box a location of a relevant feature can be described in a more precise way compared to the case when a reference relates to an entire image.

In another embodiment of the invention the storing of the at least one computed feature includes a storage of

By using the bounding box a location of a relevant feature can be described in a more precise way compared to the case when a reference relates to an entire image. In addition by using the reference a storage space can be reduced as not the image itself by the sole reference has to be stored.

In another embodiment of the invention the forming of the first query includes the use of at least a first part of textual information from the input query whereby the first part of textual relates to a query of image information only. By this a specific textual query can be formed that allows retrieving a high quality result based on a content of the image.

In another embodiment of the invention the forming of a second query includes the use of a reference image provided by the input query. Therewith the query on specific content of the images can be performed with visual information. This improves the result of the query because a general textual description by be enhanced by the visual information.

In an enhancement of the previous embodiment the forming of a second query excludes the use of textual information provided by the input query. Herewith a clear guideline is provided to describe the forming of the second query that will result in a high quality query result.

By this third query results of the first and second query can be limited to a lower number of hints. This improves the quality of the final result list by eliminating not relevant hits.

In another embodiment of the invention the aggregating includes a ranking of the results of the first result list the second result list and the third result list such that the final result list shows the results in an order of importance. By this embodiment the most relevant hits can be shown first. Hence a time to review the hits by a user can be reduced.

In another embodiment of the invention the at least one image is a medical image. At least one embodiment of the invention can be used for medical images and associated medical reports in a very beneficial way.

At least one embodiment of the invention also relates to a device for data retrieval of a final result list comprising 

In an embodiment of the invention the device is further capable to implement and execute at least one of the method steps as claimed in one of the previous embodiments. The advantages are the same as for the respective method embodiments.

An embodiment of the invention describes a content based image retrieval method and device that use similarity search extended by a semantic model to increase the quality of the image search.

A data preparation unit starts procession images and texts on receiving a notification event NE from a report database or an image data base. The notification event NE indicates that new data such as medical images or report texts arrived on the respective database. The report database covers report texts and the image database PACS medical images.

For images IM the data preparation unit invokes in step S an image parser unit that loads in step S the new image and segments in step S the anatomy and pathological structures using software detectors see e.g. 1 and 2 . The image parser unit maps in step S detected structures to unique resource identifiers URI coming from a knowledge database and stores this information as first semantic annotations SAINFO in step S in a semantic annotation database . By using the semantic annotations SAINFO it is possible both to reference to a certain image area in the image IM that shows the detected structure and to locate this certain image area by a unique resource identifier.

Further on storing the detected structure includes a storage of a reference information to the at least one image that is stored on an image database. Additional a bounding box that defines a region of interest in the at least one image whereby the region of interest represents an image area that covers the detected structure can be stored.

The data preparation unit requests in step S from an indexing unit to compute features by use of a feature extraction unit . The data preparation unit requests in step S the image parser unit to detect in step S specific image regions that are portions of the image IM also called region of interest ROI . For example in the case of lesions or pathological lymph nodes the image parser unit detects the lesion or lymph node computes a bounding box and passes this as ROI in steps S to the feature extractor unit . For details on how the image parser unit is enabled to detect e.g. lymph nodes see 3 . The feature extractor unit computes in step S low level features e.g. gradient or histogram features from region of interest ROI . Finally the features are stored in step S in an image feature database and are indexed in step S for a fast retrieval.

If new reports are available in the report database a text parser unit is in step S invoked by the data preparation unit to parse in step S the next report text TEX for detecting a text passage PT and to generate second semantic annotations SAINFO i.e. mapping a unique resource identifier from the knowledge database identifying a content of a text. In step S the text parser unit stores a begin TPB and an end TPE of the detected text passage PT of the new text TEX together with the URI in the semantic annotation database. The second semantic annotations SAINFO are stored in step S together with the first semantic annotations SAINFO generated by the image parser unit . This will result in a boost of the available knowledge for the semantic search. The data preparation unit controls the text parser unit the image parser unit and the indexing unit . Both the text parser unit and the image parser unit use the knowledge database e.g. ontology database to find the correct URIs.

The storage of the detected text passage may include a storage of a reference information to the report whereby the report may be stored in the report database.

After processing the new data such as reports and images and storing the meta information as the semantic annotations SAINFO SAINFO in the respective semantic database and image feature database the system can be used e.g. by a user to do an image retrieval. With reference to in a step T a user can create a query QURY using a graphical user interface GUI . The GUI provides a form to describe the query in two ways directly using concepts RCT retrieved from the knowledge database or making use of the text parser unit to interpret free text.

Additionally the user can upload in a step T a reference image REFIMG that implicitly specifies the region of interest.

A query engine unit accepts the input query QURY from the user i.e. concept list CL and reference image REFIMG and prepares in a step T queries for the individual subsystems. In the example of these subsystems are the semantic inference unit a patient database and the indexing unit . In particular the indexing unit takes care of the part of the query relating to the reference image the semantic inference unit takes care of parts of the query relating to textual queries about image content and the patient database is contacted for parts of the query relating to non image textual queries such as gender or age of patients or laboratory values of patients whereby images and or image regions of the images used for search can be filtered on such patient s information.

In step T the query engine unit sends query terms QURYTERM also called a first query that are prepared in step T to a semantic inference unit . The semantic inference unit queries in step T the semantic annotation database with additional anatomic information retrieved from the knowledge database in step T. As an example if the user searches for lymph nodes in the thorax the semantic inference unit expands this query to specific names of the lymph nodes in the thorax such as pretracheal lymph node hilar lymph node axilliary lymph node and so forth.

Some constraints can be given by the user e.g. age or gender which the query engine unit queries in step T in the patient database to retrieve conventional patient data CPDR. The patient database is usually a hospital information system HIS in hospitals. The patient database covers laboratory values of patient general data.

The reference image REFIMG is sent in step T to the indexing unit to be used for search in the image feature database . This represents a second query. The indexing unit extracts in step T features of the reference image REFIMG by the use of the feature extractor unit and searches in step T an index to find matching features in the image feature database . Information REST also known as a first result list about belonging images and image regions are returned to the query engine unit in step T.

Finally the query engine unit takes in step T three result lists the first results list REST from the indexing unit a second result list REST from the semantic inference unit and a third result list RESTS from the patient database aggregates them in step T and presents in step T the results of the aggregation REST such as reference to image and image regions back to the user. The result can be a ranked list matching images and image regions from different patients.

In addition the device as described by the and may include for maintenance reasons a maintenance unit to configure the units and database used for data preparation and data search phases.

In practice a report is generated for one or several images such as in hospitals. Hence when analyzing images and associates reports the semantic annotations SAINFO and SAINFO relate to each other. Therefore it is beneficial to store both the first semantic annotation SAINFO and the second annotation SAINFO together in the semantic annotation database. This enhances the quality of information in the semantic annotation database.

The query is Find all patients with similar lesions in the liver and with thoracic lymph nodes enlarged . A radiologist specifies a scribble which is a GUI representation for a region of interest e.g. in step T the query is set by scribble e.g. of the reference image REFIMG shown. shows an enlarged view of the query interface also called GUI of . Subsequently the user fills the GUI based on a web based form to limit the search to patients also showing enlarged thoracic lymph nodes. In the following the term system is used as a synonym for method or device.

For the query by the scribble the system knows that the given lesion is within the liver this information is derived from the automatically generated semantic annotations. The subsystem returns a ranked result list REST e.g. a ranked lesion list to the query engine unit .

Analogously the semantic search is processed based on query terms QRYTERM based on query by concept and a ranked result list REST e.g. a ranked concept list is returned to the query engine.

Subsequently both ranked results lists REST REST are merged and a final ranked result list REST is presented to the user. For convenience this ranked list is hierarchically grouped by patients e.g. on a screen TV for the user such as

The image parser unit provides annotated images landmark and organ detection as shown by reference sign X.

In addition a filtered rank list FRL can be provided from the subsystem handling the semantic search to the subsystem handling the query by the scribble.

The benefit for the physician is that he can be sure that only lesions from patients with additional enlarged i.e. pathological thoracic lymph nodes are returned. With this the physician can infer that the given lesion is probably a tumor since it occurred together with pathological lymph nodes .

The patent claims filed with the application are formulation proposals without prejudice for obtaining more extensive patent protection. The applicant reserves the right to claim even further combinations of features previously disclosed only in the description and or drawings.

The example embodiment or each example embodiment should not be understood as a restriction of the invention. Rather numerous variations and modifications are possible in the context of the present disclosure in particular those variants and combinations which can be inferred by the person skilled in the art with regard to achieving the object for example by combination or modification of individual features or elements or method steps that are described in connection with the general or specific part of the description and are contained in the claims and or the drawings and by way of combinable features lead to a new subject matter or to new method steps or sequences of method steps including insofar as they concern production testing and operating methods.

References back that are used in dependent claims indicate the further embodiment of the subject matter of the main claim by way of the features of the respective dependent claim they should not be understood as dispensing with obtaining independent protection of the subject matter for the combinations of features in the referred back dependent claims. Furthermore with regard to interpreting the claims where a feature is concretized in more specific detail in a subordinate claim it should be assumed that such a restriction is not present in the respective preceding claims.

Since the subject matter of the dependent claims in relation to the prior art on the priority date may form separate and independent inventions the applicant reserves the right to make them the subject matter of independent claims or divisional declarations. They may furthermore also contain independent inventions which have a configuration that is independent of the subject matters of the preceding dependent claims.

Further elements and or features of different example embodiments may be combined with each other and or substituted for each other within the scope of this disclosure and appended claims.

Still further any one of the above described and other example features of the present invention may be embodied in the form of an apparatus method system computer program tangible computer readable medium and tangible computer program product. For example of the aforementioned methods may be embodied in the form of a system or device including but not limited to any of the structure for performing the methodology illustrated in the drawings.

Even further any of the aforementioned methods may be embodied in the form of a program. The program may be stored on a tangible computer readable medium and is adapted to perform any one of the aforementioned methods when run on a computer device a device including a processor . Thus the tangible storage medium or tangible computer readable medium is adapted to store information and is adapted to interact with a data processing facility or computer device to execute the program of any of the above mentioned embodiments and or to perform the method of any of the above mentioned embodiments.

The tangible computer readable medium or tangible storage medium may be a built in medium installed inside a computer device main body or a removable tangible medium arranged so that it can be separated from the computer device main body. Examples of the built in tangible medium include but are not limited to rewriteable non volatile memories such as ROMs and flash memories and hard disks. Examples of the removable tangible medium include but are not limited to optical storage media such as CD ROMs and DVDs magneto optical storage media such as MOs magnetism storage media including but not limited to floppy disks trademark cassette tapes and removable hard disks media with a built in rewriteable non volatile memory including but not limited to memory cards and media with a built in ROM including but not limited to ROM cassettes etc. Furthermore various information regarding stored images for example property information may be stored in any other form or it may be provided in other ways.

Example embodiments being thus described it will be obvious that the same may be varied in many ways. Such variations are not to be regarded as a departure from the spirit and scope of the present invention and all such modifications as would be obvious to one skilled in the art are intended to be included within the scope of the following claims.

