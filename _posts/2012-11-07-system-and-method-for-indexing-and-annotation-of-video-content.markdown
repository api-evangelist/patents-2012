---

title: System and method for indexing and annotation of video content
abstract: Embodiments in accordance with the present invention relate to methods and systems for the indexing and annotation of video content, the retrieval and display of such video content and its annotations, and the conversion and transmission of such video content and associated data. In certain embodiments, the system processes and cross-references video content with data associated with that content and with standard ontologies. Correlating these information sources produces a system of indexing and annotation of the content. In certain embodiments, this indexing and annotation may facilitate the discovery, retrieval, and management of video content, and may facilitate the integration of video content with other media and other systems.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09407942&OS=09407942&RS=09407942
owner: FINITIV CORPORATION
number: 09407942
owner_city: San Mateo
owner_country: US
publication_date: 20121107
---
The instant nonprovisional patent application is a continuation in part of U.S. patent application Ser. No. 12 569 632 filed Sep. 29 2009 which claims priority to U.S. Provisional Patent Application No. 61 102 699 filed Oct. 3 2008 both of which are incorporated by reference in their entireties herein for all purposes. The instant nonprovisional patent application also claims priority to U.S. Provisional Patent Application No. 61 556 702 filed Nov. 7 2011 which is incorporated by reference in its entirety herein for all purposes.

Any large volume of content in any given medium requires some approach by which it can be organized and managed. Readers of books employ indices glossaries tables of contents library card catalogs and Internet search engines to accurately locate specific content of interest.

Computer based systems have been used for the organization and management of content. This is true of the creators of content such as book publishers. It is also increasingly true for consumers of content who receive content through computer based systems such as the Internet. Computer based systems have proven especially effective in managing print based content since computer systems are particularly well suited to manage written language and numbers.

The effective organization and management of video content is more difficult than text based content due to the fact that digital video or analog video that has been converted into a digital form is not comprised of written language. Digital video may comprise a sequence of computer codes not based on human language that are used by a computer based system to display a video sequence. However computer based systems are unable to search for or identify the subject matter contained in these codes since the sequence of codes comprising the digital video content do not contain written language that can be meaningfully searched or indexed by computer programs. This inability to search or identify subject matter contained within a video sequence has rendered problematic the organization and management of large volumes of video content.

In the art metadata has been employed to address this issue. Metadata are descriptive fields of information that describe content. For example title author and publication date are three such fields used in book card catalogs. Similarly in order to manage video content more efficiently metadata fields are sometimes used in which descriptive information is entered into associated data fields to describe video content.

This approach has proven to limit efficacy however. One challenge is the lack of detailed descriptive information contained in this metadata. For example the entry of this descriptive information is often generated through a manual process limiting the amount and detail of the descriptions. Another challenge is the accuracy of such metadata resulting in an inaccurate description of the content.

In addition since video is a temporal medium it is desirable to not only create descriptive data but to associate that description with a specific point or duration of time within the video content. This temporal association is often not supportable with such a manual process. Consequently the descriptive information may typically fail to represent the subject matter of video content as it changes over time through the temporal sequence of the video.

Many computer based video editing systems so called non linear editing systems support the use of metadata fields and associate them with video content as described above. In addition some systems allow some portion of the audio containing speech to be transcribed into a text form and used as a basis for metadata. Such transcription varies considerably in terms of accuracy and therefore cannot be used as an unambiguous index. Also such speech transcriptions do not assist in the generation of metadata relating to content that is not reflected in speech.

Some Internet based services that allow users to share video content with one another allow contributors to enter descriptive words or tags . Videos can be located for example by searching the tags.

The efficacy of such tags may be limited however. First tags are manually generated limiting the level of description. Second tags do not typically associate subject descriptions with points of time in the video. Finally such tags are entered without restrictions or standards. This results in different users applying tags in conflicting ways significantly limiting the efficacy of such tagging as a tool for the organization of content from multiple users.

Accordingly there is a need in the art for improved computer based systems that provide indexing and annotation of video content that is descriptive detailed temporal automatically generated and unambiguous.

Embodiments in accordance with the present invention relate to methods and systems for the indexing and annotation of video content the retrieval and display of such video content and its annotations and the conversion and transmission of such video content and associated data. In certain embodiments the system processes and cross references video content with data associated with that content for example a written script. Correlating these information sources produces a system of indexing and annotation of the content. In certain embodiments this indexing and annotation may facilitate the identification retrieval and management of video content and may facilitate the integration of video content with other media and with other systems.

An indexing and annotation engine processes two input data types digital video content and a set of associated material. The associated material are digital files or other sources of data in machine readable form that are related to the digital video content that may be created during the production post production or distribution of the digital video content.

The indexing and annotation engine executes a series of steps comprising the indexing of the digital video and associated material by creating cross references between the digital video content and the associated material as well as cross references among the associated material. The indexing and annotation engine also creates annotations to digital video content with the use of information from the associated material and by the assignation of standard tags to the data in the associated material.

The system comprises an indexing and annotation engine . The indexing and annotation engine comprises executable software code present on a computer readable storage medium that is in electronic communication with a processor. When initiated by an operator the code will instruct the processor to execute one or more steps of a process.

As used herein an operator is any entity that invokes a process. In some embodiments of the present invention an operator will be a human interacting with the computer system. In some embodiments an operator may be another computer system capable of invoking a process.

In one embodiment code present on a computer readable storage medium may instruct a processor to receive digital video content . Code present in the computer readable storage medium may also instruct the processor to receive materials associated with the digital video content .

As shown in code may direct the processor to process the digital video content and the associated material to generate an annotated index . The annotated index may facilitate retrieval and display the video content information associated with the video content or both. The annotated index may also facilitate the integration of the video content and its associated information with other systems.

The indexing and annotation engine processes content in digital rather than analog form. An analog medium is one in which the images and audio in the content are modulated into a physical medium such as the silver emulsion on photographic film or the iron oxide surface of magnetic video tape. A digital medium such as digital video is one in which the physical properties of the event recorded such as the images and audio are recorded as a sequence of numbers.

Certain embodiments of the indexing and annotation system may index and process video content that may be entirely or partly in analog form such as analog film or analog video content . In such embodiments an analog to digital converter may convert the analog film video and into digital video content prior to submission to the indexing and annotation engine .

Some embodiments may operate with content that is already entirely or partly in digital video content form. For content that is already in digital video form no analog to digital converter is required.

Generally speaking digital video content is created though the conversion of analog signals such as analog media or real world phenomena into a sequence of numbers. This is conversion is done by a codec a contraction of the words compressor decompressor . A codec is software that operates in cameras computer systems or other devices capable of processing analog input and encoding it as a set of numbers. The numbers may then be saved on a data storage medium. A codec may also convert digital data into analog signals that can be displayed on display devices or recorded in analog form. Embodiments of the present invention are configured to receive digital video content created by a wide array of codecs including but not limited to 

Generally speaking digital video content such as that encoded with one or more of the codecs listed above is placed in a container file before it is saved to a computer readable storage medium. The container file is a digital file comprising the data created by one or more codecs and may also comprise other data types. The container file facilitates the management of the digital media data by computer systems.

For example certain embodiments of the present invention may accept digital video content present within a variety of container files that may include but are not limited to the following and their respective derivatives 

New digital container file formats may appear with some regularity. Accordingly embodiments of the indexing and annotation system may be modified so as to remain compatible with such formats as they emerge. The challenge of ongoing compatibility with evolving container file formats is mitigated somewhat by the fact that such file formats are required to be compliant with a standard codec which evolve with less regularity.

A time code is a sequence of numeric codes generated at regular intervals by a timing system. Such time codes are generally employed by digital video content to allow the synchronization of sound and images for referencing individual images or frames that comprise the moving picture of video content. Those elements of the indexing and annotation system that comprise time code information are so indicated time coded in the Figures.

In addition to the digital video content the indexing and annotation engine also receives as input and processes a set of associated material . Such associated material may comprise written documents and other forms of data that may be created during the pre production production post production or distribution of the video content.

An example of such associated material is a performance script stored in digital form and accessible to the processor. As used herein performance scripts are documents or other sources of data that are prepared prior to the creation or recording of the video content. Performance scripts specify the words to be spoken or actions to be taken by performers speakers actors spokespeople characters or other entities responsible for generating recordable action. Performance scripts may contain unique identifiers for different sections of the narrative work such as act numbers and scene numbers. Performance scripts may also contain scene descriptions and other directorial specifications. Embodiments of the present invention may operate with associated material that include full performance scripts or partial performance scripts for a single production or for multiple productions.

Performance scripts are used in the creation of both works of fictional video content such as narrative motion pictures and non fiction video content. Some embodiments may operate with digital video content and associated material of non fiction productions such as newscasts which may use scripts created prior to recording that are either memorized or read.

Embodiments of the invention may also process associated material comprising other types of information associated with the pre production production post production or distribution of the video content.

In certain embodiments the associated material may comprise breakdown scripts. As used herein a breakdown script is a document that comprises the production elements associated with the performance script to be executed in production and post production. Breakdown scripts may include detailed description of actions props vehicles or objects used lighting specification photographic specification sound effects special effects director s creative analysis. The breakdown script may be created and maintained by a member of the production staff such as the assistant director or producer.

Other examples of associated material are production boards or production strips which may contain drawings and other specifications about scenes in the script.

Still another example of an associated material is the shooting schedule. The shooting schedule may contain a timeline estimating tasks for each day of the production and may include the scenes to be shot the actors involved locations vehicles and props needed and special effects.

Yet another example of an associated material is the call sheet. The call sheet may specify details about a particular day s production activities which may such information as include actors needed scenes and script pages planned for production contact information schedule for the day and locations to be used.

Another example of an associated material is the daily editor log. The daily editor log may be created during production containing information useful for the editor or member of the post production staff relating to material produced during production. The daily editor log may be created and maintained by the script supervisor and used by the editor.

Another example of an associated material is the script supervisor notes. These notes may contain additional information pertaining to the production which may include changes made to the script script variations over multiple takes production elements that pertain to narrative continuity such as camera angles wardrobe makeup and hair and other observations made during production that would be valuable for guiding subsequent production or post production tasks.

Another example of an associated material is the daily progress report or daily production reports. These materials may be produced at the end of each shooting day and may contain a record of any production aspects that may have financial legal or logistical ramifications or be of interest to the producers of a production. These daily progress or daily production reports may contain information such as what scenes were shot that day the locations used the number of meals served the vehicles and equipment utilized or any other notable events or incidents.

Another example of an associated material is the film inventory report or daily raw stock log. These materials may contain information about how much raw film stock or tape was used that day what section of the script was used for specific units of stock the number of good and no good shots and the amount of film or video stock wasted. The clapper loader or a camera operator may create the film inventory report.

Another example of an associated material are sound reports. These may contain information about sound recording during production which may include details of each take recorded the DAT or DVD program number or time code or other commentary related to sound. This sound report may be created and maintained by the sound mixer or sound recorder and may enable subsequent production or post production tasks.

Another example of an associated material are production budgets. These may contain estimated detailed costs for a production.

Another example of an associated material are purchase orders. These may detail specific purchase orders executed for payment to vendors which may correspond to budget line items.

Another example of an associated material are cost reports. These may detail actual costs incurred for a production at a specific point in time subtotals of costs over specified durations of time estimates of the costs to complete the film and final costs for completed production.

Another example of an associated material are properties management files. These may detail information regarding objects props used for production.

Another example of an associated material are materials relating to special effects. These may detail information about special effects or computer generated effects.

Another example of an associated material are materials relating to make up and hair styling. These may contain specifications drawings notes and comments pertaining the make up and hairstyle treatments associated with the production.

Another example of an associated material are materials relating to photography and lighting. These may contain specifications drawing notes and observations pertaining to the photography of the production including camera and lens specification lighting specification and related data.

Another example of an associated material are financial documents. These may contain other financial information pertaining to the production such as accounts payable information and the general ledger for the production.

Another example of an associated material are documents or other sources of data comprising production credits. These may contain information about the individuals groups organizations companies associations and vendors associated with production or distribution of the content.

An associated material may be in a variety of digital formats stored on a computer readable storage medium that is accessible to the processor.

Some embodiments may receive as input associated material formatted as text files. Such text files may be created with a text mark up language including but not limited to the following and their derivatives 

Embodiments of the present invention may receive as input associated material which may comprise files created by word processing applications such as 

An embodiment of the present invention system may receive as input an associated material which may comprise files created or formatted by software or systems designed specifically for scriptwriting production or post production of video content. Examples of such software or systems include but are not limited to the following and their derivatives 

An embodiment of the present invention may receive as input associated material which may comprise data stored within a database including but not be limited to the following and their derivatives 

An embodiment of the present invention may receive as input associated material which may comprise files created or formatted by spreadsheet applications which may include one or more of the following formats and their derivatives 

A cross reference is a reference from one part of a document set of documents or other set of data to another part of the same or a different document or data containing related information. In some embodiments of the present invention the indexing and annotation engine is configured to receive as input the associated material and establish relationships among elements of the associated material in a process that may comprise cross referencing . After performing the cross referencing such embodiments will save the information generated by such cross referencing together with the associated material in a common data set the production script .

In some embodiments the files and other sources of data in the associated material contain related information. The indexing and annotation engine creates cross references among associated material based upon this related information. For example the associated material may include both a performance script and property management files that describe specific props used in specific scenes. The property management files will contain references to scene numbers which will also be found in the performance script. The indexing and annotation engine can then perform cross referencing among such data in the property management file and the performance script.

The degree of cross referencing that the indexing and annotation engine can perform among the elements of the associated material is in direct proportion to the granularity of information comprised by the elements. Associated material that comprise elements containing data with a high level of granularity may allow the indexing and annotation engine to create more cross references. For example some embodiments of the present invention may operate with digital video content from a dramatic video content production having associated material including not only a detailed performance script with uniquely numbered scenes but also including special effects materials with a large number of references to those numbered scenes. This may enable the indexing and annotation engine to create many cross references based upon scene numbers. Conversely some embodiments of the system may operate with associated material with less granularity of information such as in the case of non fiction or documentary video content. Such embodiments may produce fewer cross references.

In certain embodiments the production script is saved to a data storage device. Some embodiments of the system may save the production script to a database system or save the data in one or more text markup files.

Some embodiments of the present invention may use eXtensible Markup Language XML as a format for the production script . XML is a text based standard for the representation of data. XML is a non proprietary standard the specification of which is defined by World Wide Web Consortium MIT CSAIL World Wide Web Consortium Cambridge Mass. a technology standards organization. XML may be used in such embodiments as an alternative to other data formats such as the use of a relational data structure.

Relational data structures format data into two dimensional arrays or tables. A relational database may comprise of large number of tables each table containing two and only two dimensions. The dimensions of table are commonly referred to as rows and columns. Conversely XML formats data in nested hierarchies of elements rather than in two dimensional arrays.

The hierarchical nature of XML may be employed in such embodiments as a format for the production script . Some embodiments may store and manage XML formatted data such as the production script in one or more as text files on a data storage device. Some embodiments may store and manage XML formatted data such as the production script as data elements within an RDBMS which may require the hierarchical XML data to be mapped into the tabular structure of the RDBMS. Alternatively some embodiments may store and manage XML formatted data such as the production script in a Native XML Database which allows the XML formatted data to be maintained in its native hierarchical structure while providing the control and management capabilities of a database.

Native XML Databases include but are not limited to the following Berkeley DB XML Oracle Redwood Shores Calif. MarkLogic Server Mark Logic Corp. San Carlos Calif. DB2 pureXML International Business Machines Corp. Armonk N.Y. Tamino Software AG Darmstadt Germany Documentum xDB EMC Corporation Hopkinton Mass. Xindice Apache Software Foundation Lost Angeles Calif. 

The indexing and annotation engine processes the digital video content . In some embodiments of the current invention such processing may include the extraction of data contained in the digital video content . The extracted data may include but not be limited to a visual extraction an audio extraction and an embedded data extraction .

The visual extraction contains data that includes a copy transformation or representation of the visual frames in the digital video content . Some embodiments of the present invention may perform a visual extraction by copying frames of digital video content as images into a database or similar repository of binary data. Some embodiments of the present invention may perform a visual extraction through analysis of the frames of the video content such as detecting movement within the video content and subsequently storing data representing the analysis. Some embodiments of the present invention may perform a visual extraction with a combination of methods such as these or other methods.

The audio extraction comprises data that includes a copy transformation or representation of the sound data in the digital video content . Some embodiments of the present invention may perform an audio extraction by copying the sound data from the digital video content and storing these data as one or more digital audio files into a database or similar repository of binary data. Some embodiments of may perform analysis of the audio of the video content such as the detection of sound volume within the video content and subsequently may store the data representing the analysis. Some embodiments of the present invention may perform an audio extraction with a combination of methods such as these or other methods.

The embedded data extraction comprises the detection extraction and storage of any data from the digital video content other than that contained in the audio extraction and the visual extraction . The specifications for several container file formats provides for inserting or embedding data other than image and sound data in the digital video container file. Accordingly certain embodiments of the indexing and annotation engine may create an embedded data extraction by locating identifying and saving such embedded data.

The visual extraction audio extraction and the embedded data extraction all comprise time code data correlating to the time code data of the original digital video content from which they were extracted.

In certain embodiments the video extraction and audio extraction may contain a representation of each frame of video content. These numerical representations may comprise such visual information as average brightness contrast range or gamma of any given frame the RGB values for each pixel picture element or dot of the frame or some combination of data such as these. The numerical representations may include such audio parameters as the number of sound channels in the digital video content the number of distinct sound sources detected in each channel and for each sound source ratings for dominant pitch volume noise level and dynamic range.

In certain embodiments the visual extraction and or audio extraction are further processed to create a discontinuity profile . The discontinuity profile is a data set that indicates the degree of discontinuity of each frame of the digital video content . Discontinuity may be indicative of a change of scene camera angle take a single performance among many of the same performance script material or another point of segmentation of the digital video content . The discontinuity profile contains time code data correlating to the digital video content upon which the visual extraction and audio extraction are based.

Some embodiments of the indexing and annotation engine may create a discontinuity profile based on data in the visual extraction and audio extraction . Such an approach would produce one or more discontinuity ratings for each frame of video content by comparing the attributes of the frame to an extrapolation of the sequence of the frames that precede it. Such a discontinuity profile would represent the anomalousness of each frame of the digital video content sequence.

Since two frames of video content are rarely identical the discontinuity may not be based upon frame attributes of a single preceding frame but rather on the pattern established by a series of preceding frames. Discontinuity ratings can be calculated by comparing the value of any given frame attribute to the value that would be determined by an extrapolation of the sequence of values from the preceding frames.

For example a sequence of digital video content may represent a fade out sequence. A fade out is a sequence of comprising frames with brightness values less than the frame that precedes it. Some embodiments may comprise a visual extraction that would assign the frame in such as sequence a given brightness value N . Visual extraction would subsequently assign frame in the fade out a given brightness value N 1 and frame assigned N 2 . The extrapolation of this sequence would indicate that frame having a brightness value of N 3 . A brightness value for frame significantly divergent from the expected value N 3 would result in a higher discontinuity value for frame as pertaining to the attribute of brightness.

Some embodiments of the system may calculate a discontinuity profile for the digital video content structured as a two dimensional array with dimensions defined by the total number of frames and the total number of frame attributes contained in the video extraction and audio extraction . Some other embodiments of the system may produce a discontinuity profile on a subset of frame attributes or only produce discontinuity ratings above a threshold of significance.

In some embodiments of the system the visual extraction is also further processed by the indexing and annotation engine to produce an optical text transcription . Optical text transcription is a process comprising a series of steps that may include the identification of characters that visually appear in the video content and the subsequent storage of the identified text as data on a computer readable storage medium. As used herein the term character is the smallest unit of written human communication. Examples of characters may include letters numbers punctuation marks symbols and non English language characters.

Some embodiments of the indexing and annotation engine may employ OCR optical character recognition software which can identify and extract characters visually appearing in images or in video content. Such embodiments may use OCR software that is widely available including but not limited to 

In such embodiments the OCR software will identify any characters that appear on one or more frames of the digital video content as represented in the visual extraction . The indexing and annotation engine will then store the identified characters as text data in the optical text transcript and save the optical text transcript on a computer readable storage medium.

Some embodiments of the system may produce an optical text transcript comprising characters that may appear as titles or captions in the video content characters captured photographically during production of the video content such as background signage in a motion picture scene or characters that appear on a film production slate.

Speech recognition alternatively known as automatic speech recognition or computer speech recognition is a computer based process comprising the conversion of aural language to machine readable data. Speech recognition software detects patterns of sound representative of human speech and may convert these patterns in a computer readable format such as text data. Some embodiments of speech recognition software may identify words in speech. Some embodiments of speech recognition software may identify phonemes which are the smallest contrastive unit in the sound system of a language. Some embodiments of speech recognition software may identify both words and phonemes. As used herein speech or aural language will refer to spoken words phonemes or a combination of words and phonemes.

Speech recognition software may be used to detect speech patterns live with the use of a microphone or from a recording such as digital video content . Generally speaking speech recognition from digital video content is of variable accuracy. The degree of accuracy in speech transcription from digital video content may be dependent upon the clarity of the sound recording and speech delivery in the digital video the capabilities of the speech recognition software or other factors.

Some embodiments of the indexing and annotation engine will comprise speech recognition software that is widely available including but not limited to 

In such embodiments of the indexing and annotation engine speech recognition software will identify speech contained in the audio extraction of the digital video content . The indexing and annotation engine may then store the identified speech as machine readable data in the speech transcript and save the speech transcript on a computer readable storage medium. Some embodiments of the present invention may produce speech transcript containing time code data corresponding to the digital video content and the audio extraction upon which it is derived.

In some embodiments of the present invention the indexing and annotation engine is configured to establish cross references between elements of the production script and the digital video content . Such cross referencing may produce a temporal alignment of film or video content and the material with which it was created through the establishment of congruence between system generated speech transcription of the content and the script from which the content was recorded. This may be accomplished with script indexing a process comprising a number of steps which may include cross referencing data from the production script to data from the speech transcript or optical text transcript . The speech transcript and the optical text transcript both contain time code data that correspond to time code data of the digital video content from which they were derived. Script indexing will cross reference elements of the production script with specific time codes in the digital video content to which they correspond. The indexing and annotation engine may then store the information from the production script with the cross references to digital video content time code in a unified data set the indexed script . The indexing and annotation engine may then save the indexed script on a computer readable storage medium. As in the case of the production script in some embodiments the system may save the indexed script in a relational database RDBMS as one or more computer files or in a native XML database system.

Some embodiments of the indexing and annotation engine may establish cross references between the production script and the digital video content with the use of data contained in the speech transcript . Such an embodiment may for example cross reference text in the production script that indicates a line of actor s dialog with a corresponding section of text from the speech transcription corresponding to the video content clip of the actor delivering the line. Script indexing may then associate the text in the production script with the corresponding time code from the speech transcript and therefore with the time code from the digital video content upon which the speech transcript is based.

Some embodiments of the indexing and annotation engine may establish cross references between the production script and the digital video content with the use of by data contained in the optical text transcript . For example such an embodiment may produce an optical text transcript comprising the text of a title that appears in the digital video content . Correspondingly such an embodiment may also produce a production script comprising associated material that would comprise a breakdown script that includes the specification for the production of the text title. Script indexing may then associate the text in the production script with the corresponding time code from the optical text transcript and therefore with the time code from the digital video content upon which the optical text transcript is based.

Some embodiments of the indexing and annotation engine may establish cross references between the production script and the digital video content with the use the embedded data extraction . Such an embodiment may produce an embedded data extraction comprising copyright information pertaining to sections of the digital video content that may have been embedded into the digital video container file during post production. Correspondingly such an embodiment may also produce production script comprising information from a breakdown script that includes the copyright specification. Script indexing may then associate the text in the production script with the corresponding time code from the embedded data extraction and therefore with the time code from the digital video content upon which the embedded data extraction was derived.

Some embodiments of the indexing and annotation engine may establish cross references between the production script and the digital video content allowed by some combination of data from the optical text transcript the speech transcript the embedded data extraction or other sources of data.

In certain embodiments the indexing and annotation engine will receive as input digital video content which may comprise some amount of improvisational performance. As used herein improvisational performance is a segment of video content comprising a performance that diverges from the performance script. Improvisational performance may occur in video content for a number of reasons including but limited to artistic expression in a dramatic production or extemporaneous reportage in non fiction video content. In such embodiments processing improvisational performance the speech transcript may identify aural language for which there is no corresponding entry in the production script . In such embodiments the script indexing will produce a time coded improv transcript containing a text transcription of the divergent speech. The indexing and annotation engine incorporates the improv transcript with the indexed script .

In certain embodiments the indexing and annotation engine will receive as input digital video content from a dramatic production. In dramatic productions a single line of the performance script may be performed and recorded repeatedly. The repetition of performance is done for a variety of reasons for example to change camera angle to correct a performance to accomplish alternative dramatic effects or to correct a product flaw.

In such embodiments the indexing and annotation engine will receive as input digital video content comprising a plurality of digital video sequences corresponding to the same text in the performance script. Such embodiments may comprise script indexing that may create an indexed script with cross references between a single element of the production script and a number of discrete time code sequences in digital video .

In some embodiments script indexing may provide an index into the digital video in the form of the production script .

In some embodiments the production script may contain an array of descriptive text. The association of such descriptive text and time codes in the digital video content allows the descriptive text in the production script to serve as a source of annotations for the digital video . This level of annotation is so indicated in indexed script as annotation .

In some embodiments the indexing and annotation engine further processes the indexed script in a process of tagging . Tagging is a process comprising a number of steps which may include the assignation of standard tags to elements in the indexed script .

As used herein standard tags are standard labels terms subject headings or codes created or codified to be used by some group or community. The application of standard tags to content may be used to integrate the content with systems that use the same set of tags. Sets of standard tags are sometimes referred to as ontologies . Those familiar in the art will be aware of the technical standards upon which such standard tagging is done to digital content which includes but is not limited to XML RDF and OWL. Such standards are created by a number of standards groups such the World Wide Web Consortium http www.w3.org 2001 sw .

In some embodiments tagging may apply standard tags to the indexed script . In such embodiments text in the indexed script are tagged or associated with standard tags from one or more relevant standard ontologies . Some embodiments may perform such tagging by matching or approximate matching of the text in the indexed script to the appropriate standard tag. Some embodiments may perform such approximate matching with the associative tables that may enable the matching of many synonymous expressions to the same standard tag.

The digital video content is cross referenced to the indexed script . Therefore the application of standard tags to text in the indexed script will also associate the standard tag to the digital video. The standard tags thus act as second level of annotation as indicated by annotation in tagging .

In such embodiments following the tagging the indexing and annotation engine stores the information from the indexed script along with the applied standard tags in a unified data set the annotated indexed script . The indexing and annotation engine then stores the annotated indexed script on a computer readable storage medium. As in the case of the production script in some embodiments the system may save the annotated indexed script in a relational database RDBMS as one or more computer files or in a native XML database system.

As used herein the term clip is a discrete unit of video content containing one or more frames. A clip may be a scene of video content a discrete shot within video content one iteration among many of a performance of a line of a script or any other discrete video content sequence.

Some embodiments of the indexing and annotation engine may employ clip indexing . Clip indexing is a process containing a number of steps that include the analysis of data from a number of sources to determine the time codes from the digital video content at which each clip begins and ends. The indexing and annotation engine may then store the array of time codes representing each clip s beginning and end in the clip index and save the clip index on a computer readable storage medium. As in the case of the production script in some embodiments the system may save the clip index in a relational database RDBMS as one or more text files or in a native XML database system.

Some embodiments of the indexing and annotation engine may comprise clip indexing performed using data from the optical text transcript . The optical text transcript contains a variety of text elements that may indicate the beginning of a clip for example titles that appear in video content or text extracted from film production slates.

Frames in video content that represent a discontinuity with preceding frames may indicate the beginning of a clip. Some embodiments of the indexing and annotation engine may comprise clip indexing based upon data from the discontinuity profile which indicate the degree of each frame s discontinuity from the frames that precede it.

Some embodiments of the indexing and annotation system may receive as input digital video content for a dramatic production in which there are many clips corresponding to the same element in the production script . Such clips are referred to as takes. These takes may be recorded without the use of a production slate to demarcate the beginning of each take. Further these takes may be recorded with the same camera settings and lighting. In such embodiments the optical text transcript and discontinuity profile many be insufficient to determine the time codes at which to demarcate individual takes.

Thus some embodiments of the indexing and annotation engine may comprise clip indexing utilizing data from the indexed script . In such embodiments the indexed script may contain cross references between a single element in the production script and multiple time code sequences in the digital video content representing multiple takes. These data from the indexed script may be used in the clip indexing process to identify the beginning and end of these clips.

Some embodiments of the indexing and annotation engine may comprise a clip indexing process performed utilizing some combination of data from the optical text transcript discontinuity profile the indexed script or other data.

Some embodiments of the indexing and annotation engine store data from both the clip index and the annotated indexed script into a unified data format the annotated index . The indexing and annotation engine then saves the annotated index to a machine readable storage medium. Some embodiments of the system may store the annotated index in a database a text mark up language some alternative way of storing data or some combination thereof. As in the case of the production script in some embodiments the system may save the annotated index in a relational database RDBMS as one or more computer files or in a native XML database system.

In some embodiments digital video content is submitted for processing in the absence of an associated material . Without associated material the cross referencing process is not invoked nor is the production script produced.

However in such an embodiment the digital video can be processed to produce a visual extraction and subsequent optical text transcription audio extraction and subsequent speech transcript discontinuity profile and embedded data extraction . In such embodiments the optical text transcript speech transcript and embedded data extraction are all incorporated into the indexed script during script indexing as is the improv transcript generated by script indexing . In such embodiments clip indexing may be executed as well as tagging . Therefore it is possible in such embodiments to produce an annotated index .

The media display system comprises a retrieval and display engine . The retrieval and display engine comprises executable software code present on a computer readable storage medium that is in electronic communication with a processor. When initiated by an operator the code will instruct the processor to execute one or more steps of a process.

In one embodiment code present on a computer readable storage medium may instruct a processor to receive the annotated index allowing the operator to browse or search the annotated index .

Some embodiments of the retrieval and display engine may allow the operator to select a clip referenced in the annotated index .

After a clip is selected some embodiments may then allow the operator to retrieve video content by causing the retrieval and display engine to transmit digital video content from a computer readable medium and display the clip on a display device .

As discussed at length above the annotated index contains information elements related to the clip originating from the associated material and cross referenced to the clip. After the operator selects a clip some embodiments may allow the operator to request to view related information elements corresponding to the clip. This may cause the retrieval and display engine to present information elements related to the clip which the operator may then browse . Such instances may then allow the operator to select one of information elements .

Some embodiments may allow the operator to browse or search the annotated index and select an information element from the annotated index. Such embodiments may then allow the operator to display the information element on a display device or view clips related to that information element .

Some embodiments of the present invention may contain a plurality of clips related to an information element. For example a specific line of dialog may be cross referenced with many clips or takes. Some embodiments may allow the operator to view clips related to an information element after the selection of an information element. This may cause the retrieval and display engine to present an array of clips related to that information element that the operator may in turn browse or search . Such embodiments may then allow the operator to select one of the clips for retrieval and display .

Some embodiments of the retrieval and display engine may present comparative information related to clips. For example in some embodiments following the display of an information element representing a line of performance script the operator may elect to view related clips . The retrieval and display engine may then present a list of one or more related clips. The retrieval and display engine may also present a comparison of the clips derived from data in the annotated index which may include visual extraction data and speech transcript . These data could provide comparative information while the operator is browsing clips . Such comparative data may facilitate the browsing and selection of clips cross referenced with a single information element.

An embodiment of the transmission system may transmit video content and related data to external systems or services for integration with other media services or platforms. This may comprise of a number of steps which may include the selection of a range of content for transmission to recipients the identification of the recipients of the transmission the extraction and formatting of data from the annotated index for transmission and or the extraction and formatting of digital video content .

In the system contains a transmittal engine . The transmittal engine comprises executable software code present on a computer readable storage medium that is in electronic communication with a processor.

In some embodiments the transmittal engine allows an operator to browse or search the annotated index to identify the video content that is to be transmitted and its recipient or recipients. Such an embodiment may allow the operator to specify the range of content for transmittal and to specify the recipient or recipients of the transmission selected from the transmittal recipient index . Upon specification of the content range and specification of the recipient s such embodiments may extract data from the annotated index corresponding to the selected content range and may extract digital video content corresponding to the selected content range from the repository of digital video content .

Some embodiments of the transmittal engine may transmit video content and related information to media delivery services that may deliver video content via the Internet. Viewers may view the video content by accessing with their Internet browser a web site provided by the delivery service. From the delivery service s web site the viewer can select the video content of interest. Such delivery services seek to generate revenue with advertising. This advertising is sometimes displayed in association with the video content.

Generally speaking advertisers value contextual placement of their advertising messages. For example an automobile advertiser will place higher value on placement of their advertising message in association with specific segments of video that related to automobiles. For example the advertiser may value placement during a dramatic video content selection at a specific time code in the video content in which actors in the video are discussing automobiles or actors in the video are using automobiles. The specificity of placement of advertising based on the subject matter of content is sometimes referred to as contextual advertising. Advertisers will generally pay higher advertising rates for contextual placement of their advertising messages. The annotations created by the indexing and annotation engine are cross referenced to video content time code. Any given segment of video may have one or more annotations cross indexed to it. These annotations may provide contextual cues to advertising based online video delivery services as to the subject matter of each segment of video. These contextual cues can then be used by these delivery services to provide more contextual placement opportunities for advertisers.

While the previous discussion has focused on embodiments utilizing a browser to access video content this is not required by the present invention. Alternative embodiments may utilize software applications other than a browser and computing devices other than a traditional computer such as dedicated device for the access of video content through the internet. Examples of such dedicated devices include but are not limited to Apple iTV Apple Inc. Cupertino Calif. and Roku Roku Inc. Saratoga Calif. .

Some embodiments of the transmittal engine may transmit digital video content and related information to cable and or satellite television systems. Cable and satellite television is a system of providing video content transmitted to television sets or other display devices through fixed optical fibers coaxial cables telephone lines communications satellite signals or some combination of these.

The signal comprising the video content is delivered to via one or more the transmission methods listed above. Generally speaking the signals are received at the display location by a set top box STB and then sent to a television or other display device. An STB consists of a small device comprising computer processing components and software.

Two emerging aspects of cable and satellite television systems may be relevant to the present invention. First the United States federal law requires that all full power television broadcast stations stop broadcasting video in analog format and broadcast only in digital video format on or before Feb. 17 2009. Second the computing hardware and software of the STBs have comprised increasingly higher levels of functionality and computing power. These two developments may allow cable and satellite providers to provide new services and seek new revenue opportunities employing the capabilities of digital video signals and STBs with higher computing capacity.

Some embodiments of the transmittal engine may facilitate the creation of such new services through the transmission of digital video content and corresponding data from the annotated index . In such embodiments digital video content and corresponding data from the annotated index may be transmitted to the cable system provider for delivery and display. In such embodiments the annotated index data cross referenced with the time code from the digital video content may facilitate such capabilities as contextual advertising insertion.

Some embodiments of the transmittal engine may facilitate the editing of video content. Video content is edited in a process that may comprise the use of a computer based system sometimes referred to as a non linear editing system or NLE system. NLE systems comprise a computer readable storage device containing digital video content and software applications that allow for the manipulation of the digital video content. Such manipulation may comprise the selection of specific segments of digital video content and the assembly of such segments to create an edited version of the of the video content. Examples of NLE systems include but are not limited to FinalCut Apple Inc. Cupertino Calif. Avid Avid Technology Inc. Tewksbury Mass. and Premier Adobe San Jose Calif. . One of the tasks in the editing of video content with an NLE system may to transmit the video content created during production in digital form to the storage device associated with the NLE system. Following the transmission of the digital video content to the storage device the operator will perform a process with the NLE system which may comprise the review of the digital video content the identification of start and end points of video content segments and the annotation of such segments with text labels and other descriptive elements. The process of reviewing segmenting and annotating may sometimes be referred to as logging. In some embodiments of the transmittal engine the digital video content and corresponding data from the annotated index will be transmitted to an NLE system. The data from the annotated index cross referenced to the time code in the digital video content to which it applies may facilitate such logging.

Some embodiments may support transmission to a variety of recipient with a variety of formatting requirements for digital video content and its associated data. Such embodiments may produce a transmittal packet following the extraction of the annotated index data and digital video content in which both types of data are formatted specifically for the selected transmittal recipient s prior to transmission to the recipient. If a transmittal is sent to multiple recipients multiple transmittal packets may be produced.

In summary the capabilities of various embodiments of the invention can be grouped into three principal categories indexing and annotation of digital video content and associated material retrieval and display of digital video content and related data and extraction and transmittal of digital video content and related data. An embodiment may include 

Another embodiment may process materials from and produce indices on data storage devices that are not in the same physical location as the computer processing unit. Such embodiments may instead connect to data storage devices via secure internet connection. Such an embodiment may include 

A third embodiment may use a remote processing unit and all remote storage. The operator would therefore connect to all resources via secure Internet connection with the use of a thin client workstation. Such an embodiment may comprise 

As described in detail above embodiments of systems and methods for indexing and annotating digital video content according to embodiments of the present invention are particularly suited for implementation in conjunction with a computer. is a simplified diagram of a computing device for processing information according to an embodiment of the present invention. This diagram is merely an example which should not limit the scope of the claims herein. One of ordinary skill in the art would recognize many other variations modifications and alternatives. Embodiments according to the present invention can be implemented in a single application program such as a browser or can be implemented as multiple programs in a distributed computing environment such as a workstation personal computer or a remote terminal in a client server relationship.

As noted mouse can have one or more buttons such as buttons . Cabinet houses familiar computer components such as disk drives a processor storage device etc. Storage devices include but are not limited to disk drives magnetic tape solid state memory bubble memory etc. Cabinet can include additional hardware such as input output I O interface cards for connecting computer system to external devices external storage other computers or additional peripherals further described below.

In conclusion embodiments of methods and systems in accordance with the present invention may offer a number of functionalities. Various embodiments of the present invention may comprise a computer based system that is capable of one or more of the following 

As described above in some embodiments digital content may be submitted for processing to the indexing and annotation engine without associated material . Certain embodiments may allow the operator to submit associated material to the indexing and annotation engine without digital video content .

In the absence of the submission of digital video content to the indexing and annotation engine cross referencing of the associated material may take place to create a production script . Script indexing may subsequently correlate data of the production script .

In an absence of digital video content the indexed script created by script indexing may not align data in the production script with specific points within the digital content . However the indexed script may be tagged with standard ontologies to create the annotated indexed script and subsequently the annotated index may be produced.

In an absence of the submission of digital video content to the indexing and annotation engine the annotated index may not include specific references to the digital video content that may otherwise have been generated by the script indexing process. However the annotated index may still contain data from the associated material cross referenced by the cross referencing process which may be further tagged with standard ontologies in the tagging process .

Some embodiments may allow an operator to submit associated material to the indexing and annotation engine and to submit digital content that does not contain visual content. An example is where a digital video container file comprises only audio content referred to in the art as sound tracks and no visual content or comprises a container file specifically intended for audio content. Examples of such audio content container files include but are not limited to 

Other flexible containers can hold many types of audio as well as other media. Examples of such multi media containers include but are not limited to 

Digital audio content is created from a live or analog source with the use of a codec as in the case of digital video as discussed previously. Examples of audio codecs include but are not limited to 

In an absence of visual content within digital content submitted to the indexing and annotation engine visual extraction may not take place and optical text transcription may likewise not take place. However audio extraction may still take place as would embedded data extraction . Subsequently the speech transcript may be created. Embodiments may allow submission of associated material which may be cross referenced to produce the production script which may then be aligned with the speech transcript and extracted embedded data during script indexing .

In an absence of video content within the digital content submitted to the indexing and annotation engine some embodiments may employ a script indexing process that may align data contained in the production script with specific locations in the digital content as previously described. The indexed script in such embodiments may be tagged with standard ontologies to create the annotated index script and then merged with the clip index to create the Annotated Index .

A discontinuity profile may be created as described above. Clip indexing may be performed which may create a clip index . In an absence of visual content within the digital content submitted to the indexing and annotation engine the discontinuity profile and clip index may be based on data derived from the audio extraction and embedded data extraction processes. Following clip indexing such embodiments may also generate an improv transcript .

Certain embodiments may allow an operator to submit to the indexing and annotation engine a digital audio container file comprising a spoken word recording of materials from a book. These are often referred to as books on tape in reference to analog audiotape initially used by these products even though digital means of delivery is currently far more common e.g. via compact disc or MP3 download . Such spoken word content may correspond to all of the text contained in a book or abridged sections of the book. In such embodiments the indexing and annotation engine may align text from the associated material which may include the book upon which the performance was based with specific points in the digital content itself through the processes of audio extraction speech transcription and script indexing . In such embodiments the indexed script may indicate at which points the spoken word performance was abridged from the original text and the improv transcript may indicate at which points the spoken word recording in the digital content may have deviated from the original book text as submitted with the associated material .

Certain embodiments may allow an operator to submit digital content that does not contain audio content such as in the case of digital content comprising a digital video container file does not include audio sound tracks or in the case of digital content comprising a digital content container file for representations of graphical and or text content. Such representations may be delivered via printing on paper or display on a computer screens or mobile devices.

In an absence of audio content within the digital content submitted to the indexing and annotation engine audio extraction may not take place. Consequently speech transcription may likewise not take place.

However visual extraction may take place as would embedded data extraction . Subsequently the optical text transcript may be created. Such embodiments may allow submission of associated material which may then be cross referenced and may produce the production script .

A discontinuity profile may be created as described at length above and clip indexing may still be performed which may create a clip index . In the absence of audio content within the digital content submitted to the indexing and annotation engine the discontinuity profile and clip index can be based on data derived from the visual extraction and embedded data extraction processes. Following clip indexing such embodiments may also generate an improv transcript .

Some embodiments may allow an operator to submit associated material to the indexing and annotation engine and to submit digital content in a container file for representation of graphical and or text content to be delivered on a computer screen or printing device.

Container files for representations of graphic and or text content delivered with a printing device or computer display may be referred to herein as print content even though delivery may be made to a computer screen including a screen of a mobile device in which no actual printer is used. Generally speaking print content in digital form may be placed in one or more container files and saved to a computer readable storage medium.

Print publishers typically produce digital print container files which may be referred to as composition files . Such print container files may include the composition or representation of the content as printed on the page or display in digital form. Composition files are then transmitted to a printing device for paper output and or submitted to a mobile device for display delivery application or other delivery process.

The container files may comprise digital files including data associated with the textual and or graphical elements in the content. The container files may also comprise data to specify an appearance of the textual and or graphic elements on a page or screen and may also comprise other data types. The container files may facilitate the management of the digital textual content by computer systems including mobile devices and can be transmitted to a printing device to create printed output or output on a computer or mobile device screen.

Some embodiments may accept digital content in container files intended primarily for printing devices. Examples of such file formats include but are not limited to 

Certain embodiments may accept digital content in container files intended primarily for display on computer screens. Examples of such file formats include but are not limited to 

As previously described particular points within video content and or audio content may be specified with identifiers referred to herein as codes. Where these codes are based upon temporal designation they are referenced as time codes . In some embodiments digital content submitted to the indexing and annotation engine may comprise print content having codes that are based upon location which may be used to identify specific points within the content.

Container files may employ a variety of location codes to identify specific points within the content. Examples of location codes used in print content container files include but are not limited to 

According to particular embodiments of the present invention the indexing system may allow an operator to submit to an indexing and annotation engine digital content that may include codes such as time codes as in the case of video or audio content or location codes as in the case of print content . These codes may be used to align data of the associated material with specific points within the digital content and or to represent those associations in an indexed script in an annotated indexed script both shown in and or in an annotated index as output .

As indicated in the indexing and annotation engine may perform visual extraction if the submitted digital content includes visual data. Subsequently an optical transcript may be created.

The indexing and annotation engine may perform audio extraction if the submitted digital content contains audio data. Subsequently a speech transcript may be created.

Embedded data extraction may be attempted on submitted media. The optical transcript if created the speech transcript if created and embedded data which may extracted could then be used to index the associated material in the script indexing process . This may create the indexed script which may correlate the associated material with specific points within the digital content using codes such as time codes and or location codes .

In some embodiments the discontinuity profile and the optical transcript may subsequently be used to identify parts of video or audio content in clip indexing . This index could identify discrete sections of video or audio on the basis of a time code.

Similarly according to particular embodiments wherein digital content submitted to the indexing and annotation engine includes a container file for representation of graphical and or text content to be delivered on a computer screen or printing device sections of digital media content may be defined in clip indexing to generate the clip index . As used herein the term clip also refers to a portion or segment of print content. This index could thus define discrete segments of digital media content in a container file for representation of graphical and or text content to be delivered on a computer screen or printing device on the basis of location code.

In some embodiments digital media content in a container file for representation of graphical and or text content to be delivered on a computer screen or printing device may be submitted as digital media to the indexing and annotation engine . Visual extraction may extract graphic components such as illustrations along with their location codes. Visual extraction may generate a discontinuity profile which could be used to create the clip index through the clip indexing process .

Certain embodiments may extract the textual content from the digital media content in a container file for representation of graphical and or text content to be delivered on a computer screen or printing device through visual extraction and optical transcription and or from embedded data extraction .

According to some embodiments textual content extraction may create a comprehensive set of all text contained in the work whether within page copy or words that are present within images. Embodiments may also allow an operator to submit associated material to be cross referenced to create the production script . The production script may comprise a cross referenced set of data in the materials used to create the print content including but not limited to manuscripts descriptive catalog data image files output templates production metadata and or other data files created during the production process. The associated material in such embodiments may provide an array of metadata for subsequent incorporation into the annotated index . In such embodiments the indexed script could contain a comprehensive and aligned compilation of textual data derived from associated material such as manuscripts embedded data and textual data extracted from images through visual extraction and optical transcription .

The media display system comprises a retrieval and display engine . The retrieval and display engine comprises executable software code present on a computer readable storage medium that is in electronic communication with a processor. When initiated by an operator the code may instruct the processor to execute one or more steps of a process.

According to various embodiments code present on a computer readable storage medium may instruct a processor to receive the annotated index allowing the operator to browse or search the annotated index . After a clip has been selected some embodiments may then allow the operator to retrieve content by causing the retrieval and display engine to transmit digital content from a computer readable medium and display the clip on a display device .

The annotated index may include information elements related to the clip originating from the associated material and cross referenced to the clip. After the operator selects a clip some embodiments may allow the operator to request to view related information elements corresponding to the clip. This may cause the retrieval and display engine to present information elements related to the clip which the operator may then browse .

Certain embodiments may then allow the operator to then select one or more information elements . Some embodiments may allow the operator to browse or search the annotated index and or to select an information element from the annotated index . Such embodiments may allow the operator to display the information element on a display device and or view clips related to that information element .

Some embodiments may include one or more clips that are related to an information element. For example a specific section of a print manuscript may be cross referenced with many sections representing alternative versions of the finished printed work.

After selection of an information element some embodiments may allow the operator to view clips that are related to that information element. The retrieval and display engine may then present an array of clips related to the information element which the operator may in turn browse and or search . Embodiments may then allow the operator to select one of the clips for retrieval and or display .

In an embodiment of a system includes a transmittal engine . The transmittal engine comprises executable software code present on a computer readable storage medium that is in electronic communication with a processor.

The transmission system may allow an operator to select and transmit digital content that may or may not include audio data and or may or may not include visual data as described above. The transmission system may also allow an operator to select and transmit related information contained in the annotated index . Such selection and transmission may facilitate the transfer and integration of digital content and related information with other systems.

Some embodiments of the transmission system may transmit digital content and related data from the annotated index to transmittal recipients . Examples of transmittal recipients may include but are not limited to 

Embodiments according to the present invention may allow automated composition. For example production of print content may begin with the creation of a script document which may be referred to as a manuscript . A manuscript includes words of a print document as created by the author and or editor. The manuscript may not include the visual design of the work as printed on paper or displayed on screen figures and illustrations or a final revision of the text as displayed on screen.

Printed works may be created by placing the contents of the manuscript into a composition application. The composition application allows an operator to specify the final appearance of the print work as it will appear on paper or on a display device. Examples of composition applications include but are not limited to 

The composition application may allow an operator to define the final appearance of the content as it will appear on paper or a display device. The composition application may comprise processes including but not limited to 

The composition process may be manual semi automated or fully automated. Under certain circumstances the composition process may employ the use of a standard composition template including some of the display specifications. The manuscript content may be placed into the standard composition template.

Referring again to some embodiments may allow the operator to submit associated material to the indexing and annotation engine in the absence of digital content . An example is in the case of the associated material pertaining to digital print content.

In such an embodiment the manuscript may be included in the associated material which may be submitted by an operator to the indexing and annotation engine . Illustrations and or composition templates may likewise be submitted to the indexing and annotation engine as part of the associated material .

Certain embodiments may accept digital content in container files allowing display in connection with dedicated ebook display devices and or ebook playback software on computer screens. Examples of such file formats include but are not limited to 

Some embodiments may accept as part of the associated material production metadata for print content. Production metadata may refer to information used to manage or describe the product development process.

Production metadata may include technical descriptions of subject matter including but not limited to number of pages number of images found in the work cost estimates for production actual costs of production source information for images or text that may have been originated from third parties royalty details associated with images or text that may have originated from third parties scheduled dates estimated for key milestones of the product development process actual dates recorded for key milestones of the product development process names and contact information for individuals and organizations involved in the product development process e.g. authors agents editors designers and other parties internal to or external from the publishing organization and other information associated with either the planning or execution of the product development process.

Production metadata may be generated and managed by software applications originating from software providers. Examples include but are not limited to 

Particular embodiments may accept as part of the associated material distribution metadata for print content. Distribution metadata may comprise information used by publishers distributors and retailers of print content to describe print content and print products in order to facilitate its marketing distribution and sale.

Distribution metadata may include information that describes the product s contents such as title author subject matter tables of contents publisher information. Some of the distribution metadata may include information describing the product technically including but not limited to number of print pages book trim size number of images in product image file formats file sizes image data compression settings fonts uses. Some of the distribution meta may include terms regarding the products distribution and sale such as price regional distribution restrictions etc.

Distribution metadata may be formatted in XML in conformance to the ONIX standard. In particular ONIX is a set of data formatting specifications that includes standards for Books Serials and Licensing Terms Rights Information. ONIX standards may be used to support coordination among parties involved in creating distributing and licensing print content.

Distribution metadata may be generated and managed by software applications that originate from software providers. Examples of such software providers include but are not limited to 

Print media may be based upon a manuscript document. The manuscript may be created by an author editor and or production staff.

The manuscript typically undergoes a number of revisions by the parties involved before becoming complete. When complete the manuscript is then prepared for specific delivery formats such as for printing on paper via a composition file or one of the digital formats described above. Some embodiments may accept as part of the associated material one or more of the manuscript revisions created during the publishing process.

In certain embodiments an operator may use a Retrieval and Display Engine to Select a Clip from Digital Content to View Related Information from the Annotated Index that associated with that clip.

In some instances the Annotated Index may comprise multiple versions of the manuscript upon which the Digital Content was based. In such instances the Operator could Select a Clip and display the corresponding manuscript versions. The text in the manuscript versions in the Associated Materials would be aligned with the corresponding clips in the Digital Content through the process of Script Indexing as previously described at length above.

The indexing and annotation engine may then cross reference the associated material to create a production script . This production script may include the associated material cross referenced as previously described.

Cross referencing the associated material containing both the manuscript and the composition template may in some embodiments allow for the submission of the associated material to be submitted to a composition engine to automate the composition process. The annotated index may provide a mapping between elements in the manuscript to elements in the composition template which may allow a composition process to take place with greater levels of automation.

Embodiments of the present invention may allow updating of manuscripts. For example publishers may make changes to the textual content of digital print content after the manuscript has been placed in the composition file. When this occurs the textual content in the composition file submitted as digital content may no longer be equivalent to the textual content in the manuscript submitted as associated material .

Lack of equivalence between the text in the digital content and text in the associated material manuscript file may create operational inefficiencies. For example inefficiency may arise in the event that the manuscript file requires revision as in the case of subsequent editions. The manuscript file in such cases may not contain the most recent textual changes as reflected in the composition file.

Conventionally a current state of manuscript content may be maintained by extracting the text changes from the composition file and inserting these changes in the manuscript. Such an approach typically requires manual effort and is costly.

By contrast according to certain embodiments the improv transcript could identify discontinuities between the script or manuscript in the associated material and the final digital content . Such discontinuities could thereby indicate places in which such textual changes were performed from within the composition file which may facilitate manuscript revision.

According to certain embodiments discrepancies identified in the improv transcript may then be submitted to a manuscript updating engine shown as in . The manuscript updating engine in such embodiments may produce a listing of these discrepancies to the operator and or update the manuscript file to reflect the changes made during the composition stage. In some embodiments the manuscript updating engine could create a new manuscript version through the application of textual changes made during the composition process as identified by the improv transcript .

Embodiments of the present invention may allow the creation and distribution of electronic books. Currently digital content is often delivered to handheld mobile devices such as smart phones tablets and personal digital assistants. Such devices typically have a display and input mechanism via touchscreen or keyboard which may be connected to the internet and other remote services via WiFi 802.11 protocol TCP IP protocol connection CDMA or GSM mobile cellular network or some combination thereof. Examples of mobile devices include but are not limited to the iPhone and iPad Apple Inc. Cupertino Calif. Kindle Amazon.com Inc. Seattle Wash. Nook Barnes Noble Inc. New York N.Y. Galaxy Samsung Ridgefield Park N.J. . Certain devices may be primarily intended for representations text and or graphical content print content as defined above . Examples of such devices include but are not limited to the Nook Barnes and Noble New York N.Y. or Kindle Amazon.com Inc. Seattle Wash. .

An electronic book also known as an e book ebook electronic book digital book comprises a publication in digital form. An electronic book may comprise text images or both. An electronic book may be produced on published through and or readable on computers mobile devices or other electronic devices.

Electronic books may be electronic facsimiles of a printed book in which the e book as represented on the display devices closely reflects the appearance of the printed book. An electronic book may comprise a variation of a printed book and may be of a different visual appearance from the printed book. An electronic book may be a digital publication for which there is no printed antecedent or corresponding work.

An electronic book may be purchased through a digital bookstore. The data comprising the e book may be transmitted to the computer mobile device or other digital device for storage on that device and or subsequent display on that device.

The data comprising the e book may be included in a container file that is specifically formatted for e book delivery and display. Some examples of e book container files include but are not limited to 

Embodiments of the present invention may allow implementation of a conversion and formatting engine for e books and or video. E books may be created by the conversion of manuscript files such as may be a part of associated materials and or print composition files such may be a part of digital content through manual automated or semi automated processes.

Manuscript files may in some cases be used to create e books through automated or semi automated processes. As previously discussed manuscript files may not include 

In some embodiments including but not limited to that shown in the indexing and annotation engine could create an annotated index which would align and cross reference the digital content and associated material such as manuscript and print composition files . These cross referenced materials may then be submitted to a conversion and formatting engine which could extract data elements from both the digital content and associated material to create the final e book container file.

As in the case of electronic books digital video content may likewise be converted prior to transmission to a computer mobile device or other display device for storage and display. This conversion process may translate the digital content into a different video container file. This conversion process may re encode the digital content with the use of a codec or re encode the digital content with different settings of the same codec to facilitate its transmission to and storage on and display on a plurality of display devices such as web applications or mobile devices.

In some embodiments the annotated index may be submitted to a conversion and formatting engine for transmission storage and display on a variety of computers mobile devices and other storage and devices.

As previously described e books may be purchased from an ebook sales and delivery service such as Amazon Kindle or Barnes and Noble Nook. According to such transactions content is transmitted to a computer mobile device or other display device on which it can be persistently stored and viewed. In this way the e book data is downloaded and stored before viewing.

Audio and video content may be delivered and viewed in a similar manner through such software digital media stores such as iTunes Apple Inc. Cupertino Calif. . As in the case of e books audio or video content may be transmitted to the display device and stored in a digital storage medium on the display device prior to access by the user.

Some embodiments may allow an operator to display clips of digital content and or data contained in corresponding associated material to a computer or mobile device or other display device without downloading and storing the digital content. For example a clip of print content or video may be transmitted and displayed on a computer mobile device or other display device without first downloading the entire work through processes described in the retrieval and display engine in .

Certain embodiments may allow the request and delivery of clips and related associated materials through an application programming interface API . An API allows a first software application such as software resident on a computer mobile device or other device upon which the digital content is to be displayed to communicate with a second software application resident on the same or another computing device transmitting the digital content to display the content by the device on which the first application resides. An API could therefore allow requests for the delivery of clips or associated media initiated by the first application to be received by and delivered from the second application.

Direct interoperation between a first application resident on a computer that transmits content and a second application resident on a device that receives and displays content may allow alternative content delivery techniques to a range of devices. For example some embodiments may allow a first computer that transmits content to include and make available a broad collection of content. A second computer that receives and displays content could browse the content in the collection that resides on the first computer viewing specific clips of content without requiring the entire collection to be transmitted to and stored on the second computer prior to browsing.

As illustrated in the particular example of in some embodiments an API may allow an operator in a mobile device or remote application function to communicate with a retrieval and display engine . This allows the mobile device or remote application to select specific clips or selection specific information elements without requiring the content or annotated index data to be first stored on the mobile device or remote system.

Certain embodiments of the present invention may comprise a content server. shows a simplified block diagram of an embodiment of a system comprising an indexing and annotation engine and a content server . The content server may comprise data storage and processing capabilities to which data and digital content may be submitted for storage and which may also contain computer code capable of processing and transmitting data.

Certain embodiments may allow an operator to submit digital content and corresponding associated material to the indexing and annotation engine which may then produce the annotated index . Some embodiments may store the annotated index in a content server .

In addition to the annotated index some embodiments may also store on the content server the digital content and or the associated material used to produce the annotated index by the indexing and annotation engine .

Some embodiments may include a content server comprising computer code automating at least some of the data conversion processing and or transmission processes previously described. Such processes include but are not limited to automated or semi automated print composition processing e book conversion digital video content conversion digital audio content conversion manuscript updating as well as providing application interfaces for delivery to mobile devices and other online applications.

In some embodiments a content server may include a print composition engine performing print composition processes. The print composition engine may use the annotated index to align a manuscript with a composition template as described above.

According to certain embodiments the content server may comprise a manuscript updating engine that could aid in management of manuscript content. As an example the manuscript updating engine may identify discrepancies between the manuscript in the associated material and the textual content of the digital content as found in the improv script in a manner previously described.

Some embodiments may include a content server having a conversion and formatting engine . The conversion and formatting engine may allow an operator to translate digital media and associated material from one format to another.

For example some embodiments may include a conversion and formatting engine to assist in the process of e book creation. Certain embodiments may include a conversion and formatting engine for the conversion digital video or audio content as described above.

According to particular embodiments a content server may have an application programming interface or API for direct interoperation with mobile devices web applications and other remote processes as described above.

According to certain embodiments a Content Server may provide delivery of Digital Content or data contained in the Annotated Index to Mobile Applications or Web Applications collectively delivery applications .

In some embodiments production metadata and distribution metadata may be submitted as Associated Material to be included in the Annotated Index and stored on the Content Server . According to specific embodiments a Content Server that comprises an Application Program Interface API for interoperation with delivery applications may provide access to content based upon data contained in the Annotated Index .

In various embodiments the distribution metadata contained in the Annotated Index may contain specifications pertaining to the licensing restrictions of the content. For example according to some embodiments the distribution metadata may comprise specifications regarding which delivery applications the content may be delivered to and or may comprise specifications regarding which delivery applications the content may not be delivered to.

In some embodiments distribution metadata in the annotated index may include distribution restrictions for elements of the digital content. An example of such an element could be an illustration within print content. Such an illustration may be licensed by third parties under terms stipulating a manner of use for example permitting inclusion when the content is delivered on paper but not via a computer screen or vice versa. In some embodiments these licensing terms may be in the associated index and may be used by the content server to direct the delivery of content to mobile applications and web applications.

According to various embodiments the production metadata in the annotated index may include royalty terms for authors of the digital content or contributors of elements of the digital content e.g. illustrations within print content . Such terms may be based upon the frequency or manner of delivery of the content.

In some embodiments these royalty terms may be in the associated index . The terms may be used by the content server to calculate payments to authors and contributors based upon these terms.

Publishers typically monitor published reviews and refer to them in marketing materials. In some embodiments the distribution metadata may include the text of published reviews of the digital media such as a book review.

Published book reviews typically include quotations from the book. According to particular embodiments the book reviews could be aligned to the book via Script Indexing . This could be done by comparing quoted text from the review to the text in the digital content and the alignment reflected in the Indexed Script .

In some embodiments in which the Indexed Script includes the alignment between the Digital Content and the published reviews in the Associated Materials the Retrieval and Display engine could to Select a Clip from the book and display Related Information . That related information could comprise the published review that included that clip in the formal quotation in the published review.

According to particular embodiments the digital content submitted to the Indexing and Annotation Engine may comprise a plurality of digital products. An example includes a plurality of books and associated material for a plurality of print products. In some embodiments the associated materials could be aligned to corresponding products through the process of cross referencing and script indexing . This would be true whether the digital content contained a single product or book or multiple products.

As previously described the Associated Material for a narrative film may include the book upon which the film is based. In particular instances the Associated Material may include not only the book but also the Annotated Index of the book. For example in some embodiments the Digital Content may include video content of a narrative film and the Associated Materials may include the Annotated Index previously generated by the Annotation Engine from the book and its Associated Materials for the book or books upon which the film was based.

In some embodiments the Annotation Engine may create an Annotated Index for a film that may include one or more of 

In some embodiments the Annotated Index and the Digital Content for the film could be submitted to a Retrieval and Display Engine . An Operator could Select a Clip from the film and View Related Information which could include corresponding excerpts from the book upon which the film was based and or the Associated Materials of the books.

Similarly in certain embodiments the Digital Content may include content from a book. The Associated Materials may include not only the materials associated with the book but also the Annotated Indices previously generated by the Annotation Engine from a plurality of films based upon the book.

In particular embodiments the Annotation Engine may create an Annotated Index for a book that may include one or more of the following 

In some embodiments the Annotated Index and the Digital Content for the book could be submitted to a Retrieval and Display Engine . An Operator could Select a Clip from the book and View Related Information which could include corresponding clips from the films based upon the film and or Associated Materials of the films.

According to some embodiments a content server may have computer code capable of performing other functions relating to the conversion translation management and or transmission of digital content associated material and or the annotated index .

3a. The method of clause 2a wherein the defining of segments is further based upon an optical text transcript of the digital video data and the second index including the annotations.

4a. The method of clause 2a wherein the discontinuity profile is generated based on an analysis of sound and image attributes.

5a. The method of clause 1a wherein the aligning of elements of the associated data is based on a comparison of the associated data with a speech transcript of the digital video data.

6a. The method of clause 1a wherein the aligning of elements of the associated data is based on a comparison of the associated data with an optical text transcript of the digital video data.

7a. The method of clause 1a wherein the aligning of elements of the associated data is based on a comparison of the associated data with data embedded in a container file of the digital video data.

8a. The method of clause 1a further comprising tagging the second index according to a standard set of terms to create a second set of annotations wherein the combining includes the second set of annotations of the second index.

receiving from an operator an instruction identifying a portion of the digital video data and an intended recipient for the portion 

processing the annotated index according the instruction to produce a portion of the annotated index corresponding to the identified portion of the digital video data 

transmitting the portion of the digital video data and the portion of the annotated index to the recipient.

10a. The method of clause 9a wherein the portion of the digital video data and the portion of the annotated index are transmitted to the recipient according to a format previously specified for the recipient.

13a. The method of clause 1a further comprising prior to the aligning cross referencing components of the associated data to establish relationships between portions of the associated data wherein the relationships are included in the second index.

15a. The apparatus of clause 14a wherein the code is configured to define the segments according to a discontinuity profile.

16a. The apparatus of clause 15a wherein the code is further configured to define the segments based upon an optical text transcript of the digital video data and the second index including the annotations.

17a. The apparatus of clause 15a wherein the code is configured to generate the discontinuity profile based on an analysis of sound and image attributes.

18a. The apparatus of clause 14a wherein the code is configured to align elements of the associated data based on a comparison of the associated data with a speech transcript of the digital video data.

19a. The apparatus of clause 14a wherein the code is configured to align elements of the associated data based on a comparison of the associated data with an optical text transcript of the digital video data.

20a. The apparatus of clause 14a wherein the code is configured to align elements of the associated data based on a comparison of the associated data with data embedded in a container file of the digital video data.

21a. The apparatus of clause 14a wherein the code is further configured to tag the second index according to a standard set of terms to create a second set of annotations and wherein the code is configured to perform the combining including the second set of annotations of the second index.

23a. The apparatus of clause 22a wherein the code is configured to direct the processor to transmit the portion of the digital video data and the portion of the annotated index to the recipient in a format previously specified for the recipient.

26a. The apparatus of clause 14a further comprising code configured to direct the processor to prior to the aligning cross reference components of the associated data to establish relationships between portions of the associated data wherein the relationships are included in the second index.

aligning elements of the associated data to relevant codes of the digital media data to generate a second index of the digital media data including a set of annotations of the digital media data associated with the codes to which they apply and

combining the first index the second index including the set of annotations and the codes to which they are associated to produce an annotated index and

3b. The method of clause 1b wherein the defining of segments is further based upon an optical text transcript of the digital media data and the second index including the annotations.

5b. The method of clause 4b wherein the digital media data is configured to represent graphical and or text content.

7b. The method of clause 5b wherein the graphical and or text content is delivered via display on a computer screen.

11b. The method of clause 4b wherein the digital media container file is configured to be transmitted to a printer.

12b. The method of clause 4b wherein the digital media container file includes instructions to render the digital media data with a printer.

13b. The method of clause 4b wherein the digital media container file includes instructions to render the digital media data on a computer screen.

14b. The method of clause 4b wherein the digital media container file facilitates management of the digital media data.

15b. The method of clause 2b wherein the discontinuity profile is generated based on an analysis of sound and or image attributes.

16b. The method of clause 1b wherein the aligning of elements of the associated data is based on a comparison of the associated data with a speech transcript of the digital media data.

17b. The method of clause 1b wherein the aligning of elements of the associated data is based on a comparison of the associated data with an optical text transcript of the digital media data.

18b. The method of clause 1b wherein the aligning of elements of the associated data is based on a comparison of the associated data with data embedded in a container file of the digital media data.

22b. The method of clause 18b wherein the digital media container file is configured to be transmitted to a printer.

23b. The method of clause 18b wherein the digital media container file includes instructions to render the digital media data with a printer.

24b. The method of clause 18b wherein the digital media container file includes instructions to render the digital media data on a computer screen.

25b. The method of clause 18b wherein the digital media container file facilitates management of the digital media data.

26b. The method of clause 18b wherein the digital media data is configured to represent graphical and or text content.

27b. The method of clause 26b wherein the graphical and or text content is delivered via printing on paper.

28b. The method of clause 26b wherein the graphical and or text content is delivered via display on a computer screen.

29b. The method of clause 1b further comprising tagging the second index according to a standard set of terms to create a second set of annotations wherein the combining includes the second set of annotations of the second index.

receiving from an operator an instruction identifying a portion of the digital media data and an intended recipient for the portion 

processing the annotated index according the instruction to produce a portion of the annotated index corresponding to the identified portion of the digital media data 

transmitting the portion of the digital media data and the portion of the annotated index to the recipient.

31b. The method of clause 30b wherein the instruction is received via an application programming interface.

32b. The method of clause 30b wherein the portion of digital media data and the portion of the annotated index are transmitted the recipient via an application programming interface.

33b. The method of clause 30b wherein the portion of the digital media data and the portion of the annotated index are transmitted to the recipient according to a delivery format previously specified for the recipient.

converting data of the annotated index the digital media data and or the associated materials to the delivery format.

identifying misalignment between data embedded in the digital media container file and data in the associated material and

revising the associated material through comparison of data in the associated material and embedded data extracted from the digital media container file.

automatically merging of the composition template and the associated data to produce a composition file.

39b. The method of clause 1b further comprising prior to the aligning cross referencing components of the associated data to establish relationships between portions of the associated data wherein the relationships are included in the second index.

42b. The method of clause 1b wherein the annotated index includes a set of textual data derived from an optical text transcript of the digital media data textual data embedded in the digital media container file and textual data from associated data relating to the digital media.

a processor in electronic communication with a computer readable storage medium having stored thereon configured to instruct the processor to 

align elements of the associated data to relevant codes of the digital media data to generate a second index of the digital media data including a set of annotations of the digital video data associated with the codes to which they apply and

combine the first index the second index including the set of annotations and the codes to which they are associated to produce an annotated index and

44b. The apparatus of clause 43b wherein the code is configured to define the segments according to a discontinuity profile.

45b. The apparatus of clause 43b wherein the code is further configured to define the segments based upon an optical text transcript of the digital media data and the second index including the annotations.

46b. The apparatus of clause 45b wherein the digital media data comprises a digital media container file.

47b. The apparatus of clause 46b wherein the digital media data is configured to represent graphical and or text content.

48b. The apparatus of clause 47b wherein the graphical and or text content is delivered via printing.

49b. The apparatus of clause 47b wherein the graphical and or text content is delivered via display on a computer screen.

53b. The apparatus of clause 46b wherein the digital media container file is configured to be transmitted to a printer.

54b. The apparatus of clause 46b wherein the digital media container file includes instructions to render the digital media data with a printer.

55b. The apparatus of clause 46b wherein the digital media container file includes instructions to render the digital media data on a computer screen.

56b. The apparatus of clause 46b wherein the digital media container file facilitates management of the digital media data.

57b. The apparatus of clause 44b wherein the code is configured to generate the discontinuity profile based on an analysis of sound and image attributes.

58b. The apparatus of clause 43b wherein the code is configured to align elements of the associated data based on a comparison of the associated data with a speech transcript of the digital media data.

59b. The apparatus of clause 43b wherein the code is configured to align elements of the associated data based on a comparison of the associated data with an optical text transcript of the digital media data.

60b. The apparatus of clause 43b wherein the code is configured to align elements of the associated data based on a comparison of the associated data with data embedded in a container file of the digital media data.

64b. The apparatus of clause 60b wherein the digital media container file is configured to be transmitted to a printer.

65b. The apparatus of clause 60b wherein the digital media container file includes instructions to render the digital media data with a printer.

66b. The apparatus of clause 60b wherein the digital media container file includes instructions to render the digital media data on a computer screen.

67b. The apparatus of clause 60b wherein the digital media container file facilitates management of the digital media data.

68b. The apparatus of clause 60b wherein the digital media data is configured to represent graphical and or text content.

69b. The apparatus of clause 68b wherein the graphical and or text content is delivered via printing on paper.

70b. The apparatus of clause 68b wherein the graphical and or text content is delivered via display on a computer screen.

71b. The apparatus of clause 43b wherein the code is further configured to tag the second index according to a standard set of terms to create a second set of annotations and wherein the code is configured to perform the combining including the second set of annotations of the second index.

receive from an operator an instruction identifying a portion of the digital media data and an intended recipient for the portion 

process the annotated index according the instruction to produce a portion of the annotated index corresponding to the identified portion of the digital media data 

transmit the portion of the digital video data and the portion of the annotated index to the recipient.

73b. The apparatus of clause 72b wherein the instruction is received via an application programming interface.

74b. The apparatus of clause 72b wherein the portion of digital media data and the portion of the annotated index are transmitted the recipient via an application programming interface.

75b. The apparatus of clause 43b wherein the code is configured to direct the processor to transmit the portion of the digital media data and the portion of the annotated index to the recipient in a format previously specified for the recipient.

convert data of the annotated index the digital media data and or the associated materials to the delivery format

79b. The apparatus of clause 43b further comprising code configured to direct the processor to prior to the aligning cross reference components of the associated data to establish relationships between portions of the associated data wherein the relationships are included in the second index.

Embodiments may also relate to interactive content. As used herein interactive media may refer to products and services on digital computer based systems in which media in the form of text graphics animation audio or video is presented in response to the actions of the user or viewer. In particular users actions such as a clicking with a mouse typing on a keyboard or some other input to the computer system may have an effect on the behavior and presentation of the content.

Video games are one form of interactive media. The behaviors of the user playing the game will affect the manner and sequence of the media being displayed. Another example of interactive media is interactive learning software or instructional media to be displayed on a digital computer based system with an educational objective in which the user s actions can determine the sequence of instruction. In this way the learning sequence becomes individualized.

The computer systems used to display and operate interactive media can include but are not limited to personal computers handheld computers smartphones tablets game consoles personal gaming systems and gaming kiosks.

Interactive media experiences may be created by delivering interactive digital content on a computer system. Interactive content can comprise a collection of an array of digital media assets including text audio video animations and other forms of content that can be displayed on a computer. Interactive content can comprise computer software consisting instructions to a computer system to specify how the interactive media will respond to a range of anticipated user actions.

Interactive content can be created using a range of computer programming languages including but not limited to 

Interactive content can also be created with the use of a software application specifically intended for the creation of interactive content. Such software applications are often referred to as authoring systems and can be used by a range of user types including those without software engineering skills.

Thus in some embodiments the Indexing and Annotations Engine receives as one input Digital Content in the form interactive content and receives as a second input Associated Materials relating to the interactive content. In some embodiments the associated materials may comprise the media assets audio files video files image files scripts documents containing programming codes and other source material used to create the interactive content. In addition the associated materials could include budgets costs and production schedules used in production of the material or any of the other documents and associated materials described above.

Interactive media experiences may include a simulated three dimensional space in which the user can explore and interact. In some embodiments the Indexing and Annotation Engine could align the elements of the associated materials to the Digital Content through the use of location codes describing a point in the simulated three dimensional space and create alignment between elements at that location with data elements from the Associated Materials through the methods previously discussed.

According to embodiments interactive content may also include sequences of animation or video content that play in a linear fashion. Such animated sequences are sometimes referred to as cinemematics . In some embodiments the Indexing and Annotation Engine could align the elements of the associated materials to the Digital Content through the use of time codes that could describe any point in such linear sequences and create alignment between elements at that location with data elements from the Associated Materials through the methods previously discussed regarding video indexing.

In some embodiments the use of both time codes and three dimensional location codes could be used to align associated materials with interactive content. For the interactive content a user s actions may determine the manner or sequence of the content to be presented with a system responding to the user s actions by presenting content such as text graphics animation video audio games etc.

Various embodiments may be implemented in a social media context. As used herein social media refers to computer based systems in which individuals and or communities contribute and share user generated content. Some of the types of social media systems and services include but are not limited to 

A content matching system may comprise a real time software system that scans the contents of a web page mobile application or other application extract tokens or keywords from the scan of content and matches with external data sources based upon those tokens. A token may be a keyword text string image sound or any other identifiably data or media element.

Examples of content matching systems are advertising display systems that can insert an advertisement from a previously created advertising database selecting the advertisement for insertion based on the tokens identified from the content. In this way the advertisement selected is contextually relevant to the content on the page. ADSENSE Google Mountain View Calif. is one example of a content matching system used for contextual advertising insertion.

Thus according to an embodiment the Annotated Index may be used to insert within a social media service contextually relevant digital media. shows a simplified view of an embodiment of a social media application and a content matching system .

An operator submits digital content and associated material to an annotation and indexing system to create an annotated index . A content matching system inter operates with the annotated index and a social media application .

The content matching system extracts tokens such as keywords from the social media application as described above. After the social media content matching system extract tokens from the social media application it then compares extracted tokens to data in the annotated index .

When data elements are found in the annotated index corresponding to tokens extracted from the social media application a clip is then selected as previously discussed in reference to the Retrieval and Display Engine .

In an embodiment the Annotated Index may be used to insert within a web page contextually relevant digital media. shows a social media application and a content matching system according to an embodiment. An operator submits digital content and associated material to an annotation and indexing system to create an annotated index . A content matching system interoperates with the annotated index and a web page . The content matching system extracts tokens such as keywords from the web page as described above.

After the content matching system extract tokens from the web page it then compares extracted tokens to data in the annotated index . When data elements are found in the annotated index correspond to tokens extracted from the web page a clip is then selected as previously discussed in reference to the Retrieval and Display Engine .

In an embodiment the Annotated Index may be used to insert within a digital content delivery system that is not necessarily a web page contextually relevant digital media as described above.

Microblogs are another form of social media. Microblogs allow users to exchange very short messages in the form text strings images and web addresses. These short messages are sometimes referred to as microposts . The micropost is transmitted via a syndication platform to recipients on the service who have chosen to subscribe to the messages from the contributing user. Twitter San Francisco Calif. is a microblogging service.

Microblogs allow users to send and receive microposts. They also allow users to search for past microposts. Microposts frequently include text strings referred to as a hashtags comprising a sequence of characters with no spaces preceded by the hash character.

Hashtags are used to label or tag subject matter in the micropost to facilitate its retrieval by users who wish to search for a specific topic contained in past microposts. For example a user could search a microblogging service for all previous microposts containing the hashtag ELECTION. The search result could include previous microposts that are self identified as pertaining to the subject of ELECTION.

Micropost archives are a source of data representing interpersonal discourse. Microblogs such as Twitter license to third parties micropost live microblog data feeds and archives.

In some embodiments a micropost archive as obtained or licensed from a microblog service may be used an element of the associated material and input to an Indexing and Annotation Engine . Microposts may then be cross referenced to the production script and aligned to the digital content through the process of script indexing .

The Annotated Index in some embodiments may include contextually relevant microposts aligned with the other associated material and to the content itself . According to some embodiments in which micropost data is included in the associated material a content server may be employed to deliver to mobile applications and web applications not only clips of the digital content but also micro posts that have been aligned to these clips. In some such embodiments the recipients of the digital media would be able to receive discussions pertaining to it.

Embodiments may be employed in conjunction with location based information services and or with Global Positioning Systems GPS data. Location based information services are computer based services having the ability to determine the location of a device and provide information to that device based upon its location. For example a location based information service may provide a listing of the businesses nearest to the location of the device.

Location based information services may be based upon the Global Positioning System GPS a satellite based navigation system providing location and time information to devices equipped with a GPS receiver. Mobile phones tablets and many other portable devices commonly have GPS receivers.

In an embodiment the Annotated Index may be used to deliver to a mobile device contextually relevant digital media based upon the location of the device. This may be done using a content matching system that selects content elements based upon GPS coordinates.

In an embodiment a GPS content matching system obtains location information from the mobile device in the form of GPS coordinates. The GPS coordinates of the device location may then be compared to determine proximity to the GPS data from the annotated index annotated index . Based upon a comparison of values of the device location and GPS data from the annotated index the GPS content matching system selects clips of relevant content.

In an embodiment a GPS content matching system may be used with a mobile device to display clips of digital content that are associated with the location of the device.

It is understood that the examples and embodiments described herein are for illustrative purposes only and that various modifications or changes in light thereof will be suggested to persons skilled in the art and are to be included within the spirit and purview of this application and scope of the appended claims.

