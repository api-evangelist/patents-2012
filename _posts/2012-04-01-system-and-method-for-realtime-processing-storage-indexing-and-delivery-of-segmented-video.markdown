---

title: System and method for real-time processing, storage, indexing, and delivery of segmented video
abstract: Disclosed embodiment providing for the capture of video content. The video content is segmented in real-time into clips by topic, and those clips are delivered as customized queues of video items relevant to the consumer according to their interests as aggregated from their social graph data and manual entry.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08769576&OS=08769576&RS=08769576
owner: Mixaroo, Inc.
number: 08769576
owner_city: Palo Alto
owner_country: US
publication_date: 20120401
---
This application claims priority to U.S. Provisional Application No. 61 470 818 filed on Apr. 1 2011 entitled Real Time Delivery of Segmented Video which is incorporated herein by reference in its entirety.

The present disclosure relates generally to systems and methods that provide for indexing storage and access to video broadcasts.

Broadcast television is a constantly changing medium with linear programming schedules. Multiple forms of recording devices exist to satisfy a consumer s need to record selected programming at their own convenience but these require consumers to know in advance what programming they want to record. Programming that has not been recorded cannot be viewed later.

Broadcast television is localized by satellite cable or antenna coverage. Even though content partnership between networks is common the delivery is still regional.

Internet Protocol television IPTV solutions are emerging to deliver content on demand by exploiting the internet as a global delivery medium but the large cost of bandwidth and streaming services for long form content delivery coupled with licensing costs and restrictions hampers wide scale distribution.

There is also an infrastructure and development cost to create such a delivery platform. These costs mean that a company must have either large scale user numbers or premium content must be introduced to attract this audience and achieve a viable income.

User generated content sites such as YouTube have begun to attract the attention of content producers as a medium for delivery in particular time sensitive content such as news broadcasts. These sites go some way to providing content to the user in a timely manner but indexing is driven by manually generated program titles descriptions tags and other processes that cause delays. For news information in particular the absence of video content within a search engine s real time results is an indication of a problem in this process in particular when the story has already been aired but a user must wait for someone else to manually add a news story in order for them to watch it later.

Video advertising remains largely rooted in its broadcast television foundations. Advertising is based largely on broad channel or program demographics rather than explicit information about a program s content. On the internet text based advertising such as Google Adwords has proven to have much more value with context sensitive advertising.

While the increasing use of mobile devices delivers an emerging base of consumers traditional long play program formats are poorly suited to these users and their devices. Several formats have been defined and deployed for delivery of television streams to mobile devices. These formats such as Digital Video Broadcasting Handheld or DVB H are focused on replicating the television experience on a mobile device but do not address the more common use cases for mobile devices which favor short form content.

The systems and methods disclosed in this specification capture video content segment the content in real time can sort the video content into clips by topic and can delivers those clips as a customized queue of video items relevant to users according to their interests as determined by their social graph data and or their manual interest profile configurations.

The disclosed systems and methods can segment long form video content into smaller clips based on the topic of the content. This enables the generation of a searchable index of short highly relevant video results. The created index is not only useful to the user but also provides advertisers a deeper context against which relevant advertising can be selected.

In addition to enabling directed search results for keyword lookups in the index the disclosed systems and methods enables providing recommendations in the form of a custom video queue or other organization means. These recommendations may be based on users interests. The catalogue of user interests is built by aggregating user input social network graph information and usage feedback.

Video processing may be performed in real time so that live or currently broadcasting video content is indexed as it airs. This enables the System to immediately notify users through push mechanisms when relevant content is available and where the client supports it deliver the related video. This real time processing also means that the content can be delivered to search engine indexes to enable real time results with rich video content.

The index offers a rich data source for analysis and reputation management applications. As a whole the combination of user interests demographic information and behaviors against sentiment aware content forms a valuable asset for brands and advertisers.

Although similar reference numbers may be used to refer to similar elements for convenience it can be appreciated that each of the various example embodiments may be considered to be distinct variations.

The present embodiments will now be described hereinafter with reference to the accompanying drawings which form a part hereof and which illustrate example embodiments which may be practiced. As used in the disclosures and the appended claims the terms embodiment and example embodiment do not necessarily refer to a single embodiment although it may and various example embodiments may be readily combined and interchanged without departing from the scope or spirit of the present embodiments. Furthermore the terminology as used herein is for the purpose of describing example embodiments only and are not intended to be limitations. In this respect as used herein the term in may include in and on and the terms a an and the may include singular and plural references. Furthermore as used herein the term by may also mean from depending on the context. Furthermore as used herein the term if may also mean when or upon depending on the context. Furthermore as used herein the words and or may refer to and encompass any and all possible combinations of one or more of the associated listed items.

Shown in is a system overview illustrating an exemplary embodiment in which the System is illustrated in the context of a number of architecturally distinct units. This exemplary system will be shown in further detail in the other more detailed figures and description that follows. Illustrated in is a Capture Platform which captures source data received from incoming video broadcasts and converts the source data into a standardized format.

Also shown in the figure is the Search Platform which as will be further described herein extracts topics from source video metadata and manages user taste graphs the searchable index and the Application Programming Interface API layer for client interaction.

Further illustrated in is the Media Storage and Delivery Platform . The Media Storage and Delivery Platform is the backend for storage and delivery of video content to Client Devices . The Media Storage and Delivery Platform receives the converted incoming video broadcasts and stores it in storage within the platform . This platform is further accessible through the search platform to present source data that is found through user searches.

Still further illustrated in is the Front End Client which is a Client Device as shown in through which users interact with the System . Through the Front End Client users will input searches and receive search results. Users will also be able to establish their customized profiles searches watch lists and perform other types of personalizations.

With further reference to and the architectural platforms introduced above are now further described.

The Capture Platform collects incoming source media and converts the content into a standardized format for use by the Search Platform and Storage Delivery Platform . Because television content is localized as shown in Capture Servers are deployed to local geographic regions when a data feed is not available for remote collection as in the case of analog signals or when the cost of locally processing raw data is less than that of receiving raw data remotely such as when delivery of raw data to a distant server will cost more in bandwidth than setting up a Capture Platform locally. As shown in the capture server which is drawn in the form of a known server implementation of a computing machine that includes a user display a user input device and memory for storing computer readable instructions on a computer readable medium. Thus as functionality for the Capture Server is described below the functionality performed by the Capture Server would be provided and performed by the Capture Server running computer instructions that are stored on the Capture Server s computer readable medium or computer memory or it could be based on computer readable instructions that are stored in an external or other computer memory.

Still referring to and with further reference to the Capture Platform which includes the Capture Server illustrated in provides a number of functions 

The Capture Platform may be divided between processing elements in cloud infrastructure and regionally physically deployed Capture Servers. The regionally deployed servers convert analog streams into digital transport streams and convert multiplexed transport streams into separated video and data. All of this data is then delivered to the Storage Platform.

Video is sent to the Media Storage and Delivery Platform and the EPG and subtitle encoded Transport Streams are delivered to the Cloud portion of the Capture Platform for further processing.

The purpose of the search platform is to process incoming data and requests for information. It does this by processing and then indexing incoming information doing search functions when a user requests a specific video clip and analyzing trends and user usage in order to fine tune the System as a whole.

Results are pushed to the user according to their registered interests. Results are also sent in real time to search engines for public indexing.

In addition to returning an indexed result to a search query the System is also engaged in the ongoing analysis of the index. It preforms this process by analyzing the following pieces of information 

The sentiment of content this can be processed in the form of an overall report for sentiment or sub divided by topic source time location category etc.

In disclosed embodiments of the Media Storage and Delivery Platform incoming video audio streams are marked with time data and stored according to source information. The incoming video audio streams need not be physically divided. Rather the System can use Start End data in order to determine when a relevant clip is needed and can accordingly wrap that chunk of video audio stream in a single topic wrapper to be sent to the user.

The Media Storage and Delivery Platform can use cloud based data storage such as Amazon s Web Services S3 storage product. Other such cloud based data storage approaches such as Microsoft s Windows Azure platform may be used. Further a non third party or in house storage system can be used. In any case in disclosed embodiments content would be pushed to this storage infrastructure using HTTP mechanisms.

A Front End Client is ultimately any program that a user uses to interact with the System and retrieve data from it. API interactions with the platform APIs may be provided as a component of the Search platform specification.

Client Devices are defined as any mobile website IPTV devices smart televisions set top boxes gaming platforms in car entertainment systems or any other web capable device. A client could equally be integrated with a content agency or broadcast network s existing platforms or platform families such as Microsoft s Mediaroom.

Data flows of the system are enabled to take certain paths as the data is being collected processed stored and retrieved. These paths are described in the following section as a series of steps that span multiple platforms and cross multiple components of the System .

Incoming data is gathered by the Capture Platform . This data can come in the form of at least two distinct types of input over the air data and IPTV data . Over the air data is captured using physical capture methods such as collecting satellite signals with a satellite receiver collecting local channels using antennas and plugging into a cable network in order to capture cable signals. IPTV data may be streamed through the internet as opposed to more traditional methods of broadcasting television data and usually includes more information about the content itself.

The Capture Platform separates the video audio stream from Text Metadata assigns a unique source and time code to it and sends it to the Media Storage and Delivery Platform . This unique source and time code is later used by the index to reference the video s topic after the Text Metadata is processed. In the case of IPTV data the video audio stream and Text Metadata are already separated so the Capture Platform simply has to send this data along to the appropriate storage locations.

Text Metadata is sent to the storage platform where it is processed. This incoming metadata is divided into small stories called topics. These topics contain specific keywords that can be used to index the Text Metadata and to assign context to the video audio stream that is associated with it.

Video audio streams passes through the search platform in order to be segmented and assigned more specific source and time codes. Once this is done the video audio streams are sent to the Media Storage and Delivery Platform .

Once information about the Text Metadata has been fully extracted it is stored in the index under a unique topic that can later be used by a Front End Client in order to retrieve a specific video clip. Video audio data is stored in the Media Storage and Delivery Platform in segmented chunks that can easily be retrieved when a request for the specific clip is made.

A user queries a specific video clip using a Front End Client device. Or a user with social graph data logs into a Front End Client and the System can populate the user s custom video query with videos relevant to their interests.

The Front End Client sends a request to the Index of TV for the source and time code of the specific video clip that the user queried or the video clip that they system deems appropriate to display on the custom video query.

The Media Storage and Delivery Platform filters through its stored data streams for the specific section of data that the user requested.

Upon locating the requested video clip the System wraps the clip along with its start end time data and source information in a content wrapper and sends the combined files to the Front End Client .

Incoming data is gathered by Capture Servers . This data comes in the form of two distinct types of input 

Over the air data is captured using physical capture methods such as collecting satellite signals with a satellite receiver collecting local channels using antennas and plugging into a cable network in order to capture cable signals. Because these physical capture methods are regional Capture Servers may be placed in a specific region to gather local TV signals within that region. For example if a user living in Liverpool UK is taking a trip to the United States and wishes to know what is currently happening in that country a regional Capture Server would mean that television streams from the United States could be made available to that user.

Internet Protocol data is in some respects easier to collect. Because it is streamed through the internet as opposed to more traditional methods of broadcasting television data it usually includes more information about the content itself. IP data is available where ever an internet connection is available and because the internet is almost universally accessible physical servers aren t necessarily. Rather all that is needed it to connect a Capture Server to the internet and deliver the incoming content to the Initial Processing Server .

This data is preprocessed in the Capture Servers according to type. Over the air data usually comes as a massive data stream and oftentimes needs to be demultiplexed broken up into individual channel streams and Text Metadata in order to be transported to the initial processing step. In certain described embodiments herein preprocessing is not necessary. The IPTV data for example generally comes pre split and ready for initial processing. The Capture Server may further be operable to place the captured video streams into a regular format that can be recognized and processed by the Initial Processing Server below. The formatted video streams may then be sent from the Capture Servers to the Initial Processing Server .

Once data is captured and converted into a format that can be more easily transported the Capture Server sends this data through the internet to the Initial Processing Server . Initial processing is done primarily to separate the incoming preprocessed data and sort it into its according processing and storage divisions. As illustrates once the Initial Processing Server has completed sorting it sends the sorted data to the Text Decoding Server the Video Server and the Image Server .

Video and Audio Streams are sent to the Video Processing Server from the Initial Processing Server where they are divided up and a unique time stamp and source code is assigned to the incoming data. The video stream may not actually be physically divided up but rather a time stamp may be assigned to every second or so of video. Video may for example be stored in hour long chunks but this is simply for storage purposes and has nothing to do with the length of a video viewed by a user. When a user makes a query for a specific video clip which could be any of size the System does not need to reassemble chunks of divided video. Instead all it really has to do is look for the start and end time of the video the user requested find the source of that same video and pluck that specific chunk of video from the stored stream. If a user requests a clip that spans multiple hour long segments the System has the capability to retrieve the two separate pieces of information and reassemble them before delivering the requested video to the user. Once the streams have been assigned source and start end time data they can be delivered to Video Storage .

As illustrated in the Text Decoding Server receives incoming text data from the Initial Processing Server and extracts individual words from the incoming Text Metadata . The Text Decoding Server does this through the use of Voice Recognition and OCR or Optical Character Recognition applied to Subtitle data. In this way analog information can be converted into a digital format that algorithms can be applied to. This process is explained in further detail later in this document.

As pictured in the Image Server receives images from the Initial Processing Server and divides them up into individual thumbnail components. The purpose of the Image Server component is to take individual frames from the video stream and uses them as thumbnails. These thumbnails are used in Front End Clients in order to give the user a preview of any given clip. Images taken by the Image Server are stored in the Image Storage .

As shown in once the Image Server has finished extracting thumbnail images from a video clip these thumbnails are sent to the Image Storage to be stored. When a user opens a Front End Client a series of thumbnails are displaced as representative of the video audio clips they represent.

As illustrates additional data from a video clip s EPG and Neilson Data can be used to add more context to a clip to make it more easily categorized.

As further illustrates once text subtitle and OCR data has been processed in the Text Coding Server it is sent to Topic Extraction and Segmentation . This is where the bulk of processing is performed using semantic and grammar processing key term searches input from EPG and Neilson Data information from the Contextual Database and other sources of information that can provide Entry Extraction with information as to the contents of the text data. Once Entry Extraction has collected enough information about a collection of Text Metadata to assign the data a Topic the Text Metadata is delivered to the Database Archive the Index of TV and the Trending Metrics component. This process is further described later in this document.

The Contextual Database is composed of a number of dictionaries that aid in applying a topic to a given video clip based on the translated Text Metadata . As displays Topic Extraction makes use of these contexts when assigning topics to video clips.

Once topics have been assigned to the processed text data in the Topic Extraction Segmentation component the text data is delivered to the Database Archive .

The Database Archive substantially serves as storage for all topic information. This archive is described in the present embodiment as a static index such that once information is sent to the Database Archive it does not change. In this embodiment this insures that all information that the System processes has a solid backup copy.

If an indexed topic is categorized incorrectly the Database Archive provides a means for correcting these problems if the topic is too wildly incorrect to be easily fixed. Because the System is dealing with imprecise information in the form of TV content it is advantageous to provide a method and means for making such corrections.

Also if a user needs a particular clip from a particular time on a particular channel the Index of TV is not well suited for searching for information according to these parameters. In the instance that this data does need to be found the Database Archive is better equipped to handle requests of this nature.

After Text data has been assigned topics in the Entry Extraction component it is delivered to the Index of TV .

The Index of TV is a dynamic index that continually changes and updates itself as more information is received. This component of the System contains all current updates of all topics and is referenced by the Front End Client of the System when looking for user requested content. When user requests are combined in the Custom TV they pass through the Index of TV on their way out to the Front End Client .

Client Devices represent the basis of user interfaces. A client device is defined as anything that an average user can use to connect to the System . The basic form of a client device is a website with a Graphic User Interface or GUI. However this is by no means the only client device the System could connect with. Anything with an internet connection such as gaming systems mobile phones tablets laptops and vehicle media systems could easily have an application adapted to access the System and retrieve videos for users.

There are two distinct processes through which a Front End Client request and receive video content to display to users. They are user specific search queries and system recommendations.

User specific search queries are things users specifically request such as a specific clip President Obama s inauguration speech or a parameter of things the user wants to see such as President Obama the economy CNN. The latter example may return several results. As far as the Front End Client is concerned user specific searches are begun when a user types a list of parameters or a specific clip title into a search box and clicks send.

System recommendations are a little more complex than user specific searches and pull information from a lot more places than a simple direct search. A system recommendation is activated when a user logs into a client with a pre established account. When the GUI uploads part of it can include a recommendations box. This box might display for instance several thumbnails of videos that the System has reasoned the user might like based on past searches information gathered from social graphs behavior during different clips such as pausing or skipping certain clips and other factors that the System can use to aggregate a user s interests.

It is also worth noting that whenever a user makes a request or clicks on a recommend video clip the Client Device reports to the Web Server that a video has received some sort of feedback. The Web Server then sends this information to the Metrics and Trends component for further processing.

The webserver may act as a gateway to and from the System . It acts in this regard to direct requests from Client Devices to the system components and to push requested content from the Index of TV back to the Client Devices .

The Metrics and Trends Processing component is where information about a specific clip can be found. This information isn t necessarily what a clip is about. Rather it is information about how popular a clip is how users behave while watching it pausing skipping etc. and also how frequently a clip is searched for ignored or viewed.

The purpose of compiling all this information is to place higher quality more universally liked clips at the top of user access and to place damaged bad quality or irrelevant clips closer to the bottom so that users rarely if ever have to view a bad clip.

As illustrates once the Metrics and Trends Processing component has finished extracting information the data is sent to the Metrics and Trends Archive where it can later be accessed.

Social Media such as Facebook Twitter LinkedIn and other Social Media websites are a valuable source of data when determining a specific user s interests. Because these sites actively gather information about not only a single user but the network of other users any one user is associated with a massive quantity of information can be gathered about what the user likes and also what the user is likely to become interested in based on their friends and connections interests.

When a user first sets up an account with a Front End Client they are given the option to connect their Social Media to the client it is at this point that the System sends a request for information to these Social Media outlets. However the System can update itself when a change is made to one of these Social Media outlets. These Social Media outlets return the request with a Social Graph that the Social Graph Processing component can extract information from.

When the System receives a social graph it sends the graph to the Social Graph Processing component in order to extract a user s interests and arrange them in a way that trending topics can be related to.

The System can also make use of social graph information to add context when a user makes a search query. For example if a user searches for Apple that search query may turn up results involving apple the company or apple the fruit. However if that user has mentioned Apple the company or likes Apple the company in one or more Social Media outlets the System can infer that this user is requesting video clips about Apple the company.

Once the Social Graph Processing component component has extracted the necessary information from a given social graph it deposits the graph in the Graph Database . The Graph Database is a general storage space used to house processed graphs in a form that the System can use to compile custom video line ups for individual users.

The Custom TV component assembles a group of videos that the System assumes a user will be interested in. It first collects social graph data from the Graph Database in order to determine a user s interests. It then requests relevant Video clips from the Index of TV and sends them to the Web Server which delivers the recommended videos to the user s Client Devices .

Over the air content such as Satellite Cable or Antenna delivered broadcast content can be captured and converted into a digital IPTV stream for processing using video capture hardware . This content can have several channels multiplexed together.

IPTV streams can be captured and processed. Because these streams come directly over the internet no physical capture device such as a satellite dish or a cable box is necessary to collect them. Like their analog equivalents these streams can contain a number of channels multiplexed together. The capture system demultiplexes the signal into individual Transport Streams including 

Which is usually in DVB or Line 21 format EIA 608 CEA 708 and ETS 300 74. The DVB format in particular poses a problem because it is image based and therefore requires an additional step of Optical Character Recognition OCR processing to Decode text data from the subtitle images to decode text data from the subtitle images. These images are pictures of the sentences that is displayed on screen as subtitles commonly white text on a black background.

Captured IPTV streams can contain encoded EPG data which is decoded for delivery alongside the subtitle metadata. When EPG data is not included in the initial bundle of Multiplexed data it can be collected from commercially available internet distributed feeds.

Content Providers expose a variety of proprietary APIs for content delivery these are generally HTTP and XML protocol driven APIs.

Content Providers expose a variety of proprietary API s for content delivery generally HTTP and XML protocol driven. Rather than physical servers the Capture Platform servers for these APIs are deployed to Cloud infrastructure. Content from these sources are preprocessed so when they are delivered to the Capture Platform the only processing necessary is to split the information into Text Metadata and video audio streams which are delivered directly to the Search Platform and the Media Storage and Delivery Platform respectively.

The Capture System is broken into a number of system elements based on location and need. The first of these system elements is the Capture Server which is operable to collect raw data preprocess it demultiplex it and stream it into the System . The second of these system elements may exist in a cloud infrastructure . Its purpose is to begin the process of splitting data up by extracting Text Metadata applying a format the Search Platform can understand and delivering it to the search platform for the Topic Extraction Segmentation component . The cloud infrastructure component of the Capture Platform may also receives Content API data splits it into Video Audio Streams and Text Metadata and delivers it to its respective platforms.

Text Metadata is sent to the Search platform . Metadata is sent as a JavaScript Object Notation JSON formatted object but any extensible data format can be used XML BSON etc. This data can include 

At the Topic Extraction Segmentation Block the incoming data stream is divided into Topics small story segments extracted from a continuous source. These Topics contain not only specific keywords but also the related ontologies sentiment and confidence data.

At the Video Segmentation Block the continuous video stream is divided into smaller more easily managed chunks of data.

The Real Time Updates Block delivers results in real time to Client Devices . These results are produced by combining data as it is received in real time with users taste graph information.

This Block delivers these results according to users personalized profiles is operable to receive topics and match them to registered user profiles so that the topics can be delivered to the users Client Devices as for example as Breaking News alerts or Now on Channel X . . . .

This component manages the pairing of the topics to users and in addition management of the users volume settings which define how often they expect to be notified of events on their Client Devices .

The System defines multiple indexes with multiple purposes however the Index Block within the Search Platform s functionality is primarily responsible for tracking information related to the content and topic information concerning specific chunks of video data. Once Topic Extraction has completed extracting the topic from a given set if text data it delivers that same text data to the index to be filed. The Index Block is also responsible for housing user taste information once it has been extracted from user behavior. As also displays the index is also responsible for returning information to the Directed Search functionality block when a user makes a direct search request.

A taste graph as provided in the Taste Graph Block is the categorization and management of user taste graph data so that it may later be applied to the index to produce relevant video results. This taste graph is a combination of information gathered from Social Media and information gathered from the Feedback Block . Process

By combining users tastes graphs and received topics a set of suitable users and relevance confidence weights is produced.

Each user has a volume setting for their registered Client Devices that specifies the frequency which notifications appear. This can learn user behavior according to whether notifications are viewed or dismissed.

To prevent never ending processing of inactive users an overriding setting automatically tapers out alerts exponential back off as time passes without user activity.

The PubSubHubbub protocol is used to publish real time results to Search engines for indexing e.g. Google etc. 

Directed searches include query processing for directed search and the necessary interaction with the search index to produce a search result.

The query delivers custom result sets generated by combining user taste graph data with the search index. The queue offers options to client implementations to choose different options for ordering a result list 

Relevance is determined by topic and interest confidence matching and is driven by Lucene or an alternative search engine s native relevancy mechanisms.

Feedback includes the processing of explicit and implicit user behavior data to manage the index relevance rankings and user graph data.

Usage feedback forms are an important aspect of managing the index and tuning the relevancy algorithms within the System .

Frequent negative ratings indicate a problem with the active video item either in terms of content quality or relevance. Negative ratings are applied to the index as a whole in order to suppress poor quality content from the core index s base.

Additionally the taste graph of the user who negatively rated the item is updated because a negative rating towards content within a certain topic context may indicate that the user is less interested in the topic. Positive ratings boost overall index rating for individual topic items and within that users taste graph the assumed interest in the associated topic for the user.

Reporting is required for user behavior analysis and overall product performance. This includes the number of active users video items consumed and other indicators as a high level product overview. Deeper reporting may also be provided in parallel with the Feedback analysis to indicate algorithm performance.

Along with paid subscription agreements advertising can be a basis for revenue generation. Where advertising is used the topic and related ontologies of individual items can be leveraged to provide more context relevant advertising results. Advertising models also require additional reporting to define performance and potentially to execute revenue sharing agreements.

Because the System recognizes the words within the program and the result is in response to a user s directly or indirectly indicated interests we can provide highly relevant advertising around the content and therefore highly specific advertising for individual users. For example where traditional advertising might recognize that certain demographic watches Piers Morgan on CNN the disclosed System can recognize that Piers Morgan is on CNN talking with or about Lady Gaga a celebrity pop musician who in turn is talking about her new shoes in New York. While the applications of this context awareness in delivering content have been described this context awareness can also be combined with advertising inventory to provide highly relevant and targeted advertising results.

Because advertising is based on the topic context some clips will have a higher monetary value than others. These high value clips can be exploited within the algorithms to play advertising more often than those clips with less contextual value although care is taken so that the introduction of advertising is not damaging to the user experience and does not cause an unnecessary increase in negative feedback.

To gather more direct user feedback client implementations include functionality to prompt the user for specific reasons when negative feedback occurs. These reasons may include asking whether the rejection was related to relevance video quality timing segmentation issues etc. This provides a tool during testing and ongoing usage as to an alternative option to client advertising and subscription fees.

Monitoring services are required to track the status of the platform as a whole the throughput performance of its subsystems and any errors that may be occurring. Within the cloud environment this monitoring can be used to manage the number of available server instances and automatically scale capacity to meet user demand.

After processing the engine is left with the topic information and the user to send it to. The details of specific client API s for real time messaging can include 

The Search Platform Outputs information about a specific clip that users have requested. This information is not the clip itself instead it is used by the Media Storage and Delivery Platform in order to call up specific clips requested by users.

Video content is stored in a scalable data store with streaming servers to support delivery to clients.

The Media Storage and Delivery Platform receives Video Audio streams from the Capture Platform and stores them with a unique time stamp and source data. It is this time stamp and source data that the platform references when a request is processed.

Cloud based storage provides advantages by reducing initial infrastructure costs and by removing ongoing infrastructure management costs while at the same time providing the benefits of local and geographic redundancy. In addition cloud storage providers include a set of supporting services e.g. Contest Distribution Network or CDN delivery .

Video files from live content may for example be divided into 1 hour long blocks. This 1 hour duration is purely a mechanism to divide the content and make management easier the actual length of content stored will be varied and can be adjusted within the Storage Platform.

The storage server is also responsible for storage and delivery of video thumbnails. These are generated as the stream is delivered through the Capture Platform and stored as static files for delivery via CDN. These thumbnails are organized in a folder hierarchy incorporating the source and date information.

As discussed in the segmentation process topics generate segmented lists of videos only if absolutely necessary. The majority of the time the delivery server extracts stream segments and wraps them in file wrappers on demand. Where on demand transcoding is not possible baseline profile files are created for example in different output dimensions.

The Media Storage and Delivery Platform outputs video segments to the Front End Client to be viewed by users.

The System uses taste graph information to generate custom video recommendations to users. To simplify generation of a user s taste graph the clients exploit social APIs.

Merely by submitting taste graph information the System can build a picture of global user interests and popular terms. This information serves as a basis for relevancy calculations.

Because the System algorithms feed from such a broad set of inputs traditional Information Retrieval test strategies are employed to build confidence in various algorithms.

Users are able to generate augment and modify their compiled taste graph. However this should be managed using the server generated compiled and processed view of their profile data rather than the original social graph data enabling the platform to reimport this source data and apply the same corrections.

The Infrastructure of this platform is largely vague. In general a Front End Client can be defined as anything that has access to the System so creating a specific description may limit the scope of the System s capability at a later date.

As a user interacts with a client device usage feedback is delivered to the Search platform services as an aid to tuning search and indexing algorithms. This feedback is described as part of the Search platform outline.

Client Devices are defined as any mobile website IPTV devices smart televisions set top boxes gaming platforms in car entertainment systems or other web capable device.

The majority of client user interfaces include a list of videos generally displayed as a thumbnail and Text Metadata that includes program title topic video source and duration.

Users are able to generate augment and modify their compiled taste graph. However this should be managed using the server generated compiled and processed view of their profile data rather than the original social graph data enabling the platform to reimport this source data and apply the same corrections.

As a user interacts with a client device usage feedback is delivered to the Search platform services as an aid to tuning search and indexing algorithms. This feedback is described as part of the Search platform outline.

Push mechanisms are used on various devices to support immediate alerts when relevant content appears. The mechanisms to support this are described in the Media Storage and Delivery section.

Note there is a client use case scenario where users are alerted that content is currently being broadcast without actually delivering the video Lady Gaga is now on Channel X .

For mobile devices the type of connectivity can be determined using device specific APIs to determine whether the data network connection is via Wi Fi or mobile network 3G GPRS Edge etc. . The client tracks this connectivity so that when a push notification arrives the client can automatically chose to delay presenting the notification to the user if the client is likely to connect to Wi Fi before a timeout period.

The predication of Wi Fi availability may be based on data collected on the device of historic behavior with consideration of the days of the week and public holidays. This mechanism helps to reduce mobile network data consumption and the possible associated data charges. The higher bandwidth connection speeds of Wi Fi also enable delivery of higher quality video than might be possible over mobile network data connections.

A REST based API handles client interactions. Which because of its client facing nature is cached and distributed. Video Queues are delivered in a format based on a MediaRSS protocol in multiple output formats e.g. RSS ATOM XML JSON etc. Although there are elements that require extension of the protocol its use provides a base for the data format design.

Hand picked Featured items analytics and any other web supporting services are left to the client implementation.

As delivered from the Trending Topics engine. The small pin icon beside the Trending title text in this example is described as a location pin suggesting that the results are local to the user rather than the being a global trending topic. This is implemented using the location segmentation as described in the Trending Topics section of this document.

The Users Custom Video Queue is displayed as a series of thumbnails at the bottom of the page. This is custom to the logged in user so it would be replaced with a login button if no user is currently signed in.

Discover replaces the custom video queue with a series of featured items drawing these results from the Custom Queue block of the platform optionally filtering results to match a user s location .

 Shared provides a similar queue format to discover with the number of times an item has been shared on social networks Twitter Facebook etc. as the result order.

The transcript of the active video is displayed. This can be delivered from the data store based on the topic source channel and time.

The IPTV interface example offers a little less functionality than the web example but displays an App Selection at the bottom of the page and above that the custom queue of video items to select from.

The video thumbnails show the view after the user has connected to their social account to configure their interests or like the web based Discover list featured top ranked items for users who are not connected.

The Connect button in at the top of the example image enables the user to connect using Facebook s Open Graph API as a source for taste graph interests.

A Refine button at the center of the bottom tab panel is provided leading to a list of taste graph interests that the user can modify.

For the purposes of explaining the System design subtitles will be used as the example data source because they provide chunks of text with associated timestamps. Data can also be supplied by a content provider s API or through voice recognition software in which case the System follows the same methodology except that it considers the complete body of text as a text chunk .

The timestamp for subtitle data is not the time that the Capture Platform receives the text but the timestamp that the source defines. For subtitles the Coordinated Universal Time is used to identify when the word or words appeared on screen.

In addition to the text data subtitles also provide encoded data by using color to represent different speakers and text markers for non text actions such as APPLAUSE LAUGHTER TRANSLATION etc.

Subtitle text in particular is prone to errors in the initial translations as are Optical Character Recognition OCR and voice recognition processing. Or if delivered Over the air original signal corruption can cause errors in initial translation.

Although each text chunk is associated with a number of parameters e.g. source channel location etc. the implementation does not require that this information be explicitly passed from the Capture Platform to the search platform .

The System can use source IDs and timing data combined to reduce the amount of data encoded directly alongside each text chunk that is passed to the search platform . And therefore reduce processing needs and resource consumption.

This process outputs segmented topics that contain the complete text of the topic a start and end time and additional classification information. This additional classification data can include the primary topic and weighted categorization data such as location people organizations and keywords related to the topic.

As illustrated and previously discussed with respect to Incoming text is processed in a series of queues or buffers for semantic analysis and processing. The sections that follow describe these processes with further reference to and . In the context of the below describing word tokenization step 1 categorization step 2 and sentence extraction step 3 are generally performed in the Text Decoding Server whereas the remaining steps are generally performed in the Topic Extraction Segmentation component in conjunction with its reference to the contextual database. The application of this methods to system elements described here can be implemented according to system design techniques with knowledge of the relevant design needs in a particular implementation.

Where applicable stemming algorithms are applied to the source words. The basic function of a stemming algorithm is to enable matching of words based on their root for example a stemming algorithm extracts the root word connect from the words connected connecting or connection. Numerous algorithms are available across a broad language base.

Phonetic stemming can also be applied to compensate for errors in the text in particular when the text is derived from a voice recognition mechanism. Phonetic stemming compensates for language irregularities by providing word alternatives based on the source word s phonetic structure. For example it will match see with sea and through with threw. 

These are words which should not be indexed such as in English for of at a and the etc. These words are not removed from the buffer as they form part of the semantic analysis for categorization later in the process but they are not considered when determining a sentence s context. Instead these words are flagged as stop words and are ignored when looking for context.

The incoming text is processed and words are marked with their assumed part of speech such as noun verb adjective etc. Detected nouns are of particular interest to the System later in processing as potential sources of context information such as locations people and organizations. These words are usually the best indicators of a text stream s context.

Dictionary look ups are performed to create an extended graph of associated topics with source tokens 

The basic description of this process is that words are matched against a database of morphologically related words. For example airplane is related to aircraft fly flying passenger pilot airport etc.

In addition to the more explicitly defined relationships in the Morphologic dictionaries a database of more loosely coupled relationships is maintained and updated as text is received. This dictionary provides a further source of related data for each of the word tokens.

This dictionary is generated by storing relationships between nouns identified in the parts of speech tagging process. For example the English sentence In Brazil the famous carnival has begun in Rio leads to associations where Brazil is related to Carnival Rio Carnival is related to Brazil Rio and Rio is related to Brazil Carnival . In this way important information containing multiple words is not discarded or sectioned into unrelated topics.

This helps the System to recognize that the context of a topic has not changed between one sentence discussing Rio and the next that mentions Brazil .

For example in location based lookups London can be expanded to Location London England United Kingdom Europe .

A good example is a location based lookup where London can be expanded to Location London England United Kingdom Europe . Rather than pure nouns keywords such as scored can also be used.

Dictionaries are assumed not to be complete and only serve to help the categorization process. These dictionaries are generated by analyzing taste graphs as described later for popular terms and by gathering information from available sources. Online resources and search tools such as DMOZ Yahoo BOSS Amazon Alexa API and others are used as data sources for dictionary generation.

As we categorize tokens with associated topics we assign weight or confidence values that define how important we believe a word to be.

The base of this weight or score is the count of historic mentions of an expression on a channel. For example if CNN mentions Obama a thousand times a day and President Karzai 30 times then given the sentence Obama met with President Karzai today we would assume President Karzai to be the dominant topic of the sentence and as the sentences are combined the discussion as a whole.

The weighting algorithms are also driven by dictionary source. For example a location dictionary result is weighted higher than a result from context relationships dictionaries such that we can say the sentence In London David Cameron met political leaders for talks is strongly weighted almost certainly about London and the UK and probably related to David Cameron and by association politics. In addition to this dynamic collection of previous mentions we also draw on the related metadata

As each sentence is processed sequentially as they arrive these confidence values are aggregated to provide a dynamic set of keywords and related contexts that define what we believe the most important keywords are and the current context of the conversation. In addition to the identified entities we also gather context from.

Where available inbound data may also be tagged with context such as News Sport Entertainment etc. Such is the case for much of the API provided content. For broadcast content over the air or commercially supplied EPG data can be used to provide categorization and context information.

In particular broadcast content uses Nielsen data as an additional source for categorization. Commercial EPG data feeds are also available some even define advertising break schedules.

For example a text stream with mentions of goal and football would lead to a strong weighting towards a context of sport . As additional tokens are processed a dictionary lookup for Liverpool is more weighted towards Liverpool the football club as opposed to Liverpool the city.

As data is received and categories assigned the context of the stream is identified. This context is gathered from 

Where available inbound data may also be tagged with context such as News Sport Entertainment etc. Such is the case for much of the API provided content. For broadcast content Over the air or commercially supplied EPG data can be used to provide categorization and context information.

In particular broadcast content uses Nielsen data as an additional source for categorization. Commercial EPG data feeds are also available some even define advertising break schedules.

For example a text stream with mentions of goal and football would lead to a strong weighting towards a context of sport . As additional tokens are processed a dictionary lookup for Liverpool is more weighted towards Liverpool the football club as opposed to Liverpool the city.

Each of the dictionary lookups described includes support for multiple word associations. For example if the word European in the token buffer is followed by Union a stronger weight is applied to the complete results as opposed to either word individual word.

Unlike a filtering process weighing is applied so that a result of Middle East Politics does not nullify results for Middle East . When a query is made against the index for Middle East Politics the higher match ensures a higher ranking for the more complete match in the results.

According to individual language rules the dictionary is structured to support passing preceding word types to assist in distinguishing between Beatles and The Beatles . Although correct capitalization cannot be assumed capitalized nouns also play a role in result weight. For example organizations and places are capitalized Apple and apple middle east Middle East .

The next stage of processing is to divide the token stream into sentence blocks. This is performed by using a separate segmentation process. The function of this segmentation process is to provide the best match for sentence or topic start end times.

Similar to the token stream at the core of the segmentation process is a buffer of time values and confidence values. These confidence values are weights are further illustrated in .

Many languages define a period e.g. Modern Latin derivatives English Japanese Chinese etc. to denote the end of a sentence structure. In English capitals commonly indicate the beginning of a sentence. Care should be taken towards exceptions such as periods after abbreviations.

In the case of subtitle information pauses in the source text timestamps indicate pauses in original spoken words. This information is vital to determining the source chunk length of a subtitle source.

The System recognizes that the 3 second gap between riots and protestors is more significant than 4 second gap between were and riots simply because the combined chunk sentence in London today there were would have taken longer to say.

Many television sources can be assumed to follow a programming pattern. Content is traditionally delivered in 15 30 or 60 minute blocks so that the 0 15 30 and 45 minute markers of every hour are weighted as possible indicators of context change.

Historic data and language is analyzed to provide an expected phrase length generated for each source. This is a weighted value stacked to prevent obvious failures like 60 word sentences and does not assume speakers will follow a strict speech pattern.

Some data such as that provided by Content API 408 Providers such as Reuters and Associated Press is delivered as a segmented block with a single published time which acts as the start end and content time. In these instances sentence extraction is not required the article acts as a single already defined topic.

Expressions are defined on a per channel basis to mark start and end expressions. Expressions beginning with Now on . . . Hello . . . Next . . . Welcome to . . . The Headlines etc. are a good indicator of a segment beginning while expressions such as . . . back later . . . Goodnight etc. are a good indicator that a segment has come to a close.

Algorithms to process video scene change are available as part of key frame generation routines in many video encoding implementations. Audio analysis is cheaper in terms of processing power and a sudden change in volume can be used to indicate a change in context. Sudden audio adjustment is a particularly common feature of broadcast advertising and can be used to guess when a television program has ended and commercials have begun.

Using this data buffer the System can divide the incoming text into sentences. An example is given in the table below 

 Now we w AS so double the killer delete select all. . Sentences that contain unrecognized tokens containing non alphanumeric characters as flagged with a below average grammar confidence score that lowers the weight value of the related contexts and topic in the index so that this entry is less likely to appear as a result.

Lost data may make end of sentence detection difficult e.g. missing period characters within the sentence structure. By examining historic channel data we define average and expected maximum sentence lengths for channel content. As this expected length is reached and exceeded we increasingly aggressively identify potential sentence break points using timing data a pause between expressions capitalized words and parts of speech tagging e.g. definite article The followed by noun to detect a potential sentence break.

This step is performed using available libraries although the effect of the grammar score on the overall topic ranking is related to the confidence in these algorithms. A channel known to adhere less to conventional grammar rules will weigh this category less than a channel known to adhere more frequently to conventional grammar rules. For example CNN evening news cast will weight this category as more important than say MTV.

It is expected that many valid spoken text streams will contain colloquialisms and grammatical irregularities so over all these checks should not greatly impact the topic relevance weight.

Sentences are examined to produce positive or negative sentiment values. Dictionaries are provided to weigh individual words with individual values with care taken towards modifiers like not good super bad very happy and broader analysis of overall semantic context I cannot say I am happy. 

The dictionaries that serve the source weight are balanced by context such that for example superlative heavy sports content does not overly dominate the resultant weight win score fantastic goal .

When a topic has been extracted this sentiment information is aggregated and stored with the topic as the overall sentiment.

At this point in processing the buffer can be said to consist of a series of sentences each with weighted primary related keywords and context associated with it.

When a new sentence arrives it is assigned a unique Topic ID. The sentence is compared to recent historic sentences and related keywords. The System then determines if the sentence is a match for recent or historic topics. If a sentence is a strong match it is assigned to a recent or historic sentence Topic ID. If a match cannot be made the sentence retains its unique Topic ID.

While new sentences are being assigned topics on a sentence level the buffer contains a series of sentences and Topic IDs that are waiting for a change in context. The end Topic ID of the buffer is generated algorithmically using a number of parameters 

Depending on the data source and time topics can be expected to be a certain duration. For example a news channel might be expected in general to create several 30 second topics at the start of every hour followed by 10 minute topics for the remainder of that hour. An entertainment program might be expected to produce four 15 minute topic blocks such as interviews over the course of an hour.

After a period of time passes during which no mention of the original topic or related keywords is made the System assumes that the discussion of that topic has ended.

If a topic has a strong confidence in relationship to a particular category and new sentences arrive strongly connected to an unrelated category this is an indication that the topic has changed to an unrelated subject.

If a series of sentences mention sport football goal Liverpool the System has a confidence in Sport as the current context with Liverpool UK as a location. Should the sentence that follows include Libya government and protests a change in context to news politics is assumed.

Sentence extraction will supply heavily weighted hard stop actions. In the news a sentence beginning with The Headlines is a good indication that the previous topic has ended. Similarly EPG program start and end timing indicates a topic change. represents the processes by which a clip s Start and End time data is generated.

Once a topic end has been identified this completes the process of Topic Extraction Segmentation . The category and related keyword confidence of the topic as a whole is analyzed and combined alongside the aggregated text and start end times.

Video files are not necessarily physically broken into topic segments in this process. Along with the source channel the start and end time is sufficient for the Media Storage and Delivery Platform to retrieve and play requested topics. This enables the System to reprocess and redefine topic start and end times without the overhead of cutting and or merging video files.

The start and end time for the video. In combination with the source location and channel this is used to form the content request to the Media Storage and Delivery Platform .

This data is passed on to a number of processes including the index for storage the trending engine and the real time updates component.

As completed topics are detected their related keywords are pushed to the trending topics engine which maintains sets of trending topics. The concept of trending topics or trending stories is one that is widely used with many active examples online Breaking News Twitter etc. .

Each topic generated carries with it not just the active keyword text but also a confidence score and the accompanying metadata all of which is aggregated within this engine.

This enables the System to generate rich trending topics lists as sets of query objects for example in the pseudo JSON format below 

By using this format when trending keywords such as Apple are queried only the results relevant to the organization are returned.

Allows the Front End Client Admin Users to temporarily or permanently ban words from the trending topics lists in case a word slips past the frequency analysis algorithm. In this way the System eliminates words that users would otherwise not be interested in querying.

Ranking determines the likelihood of an given topic appearing as the result of a user queried search or of a user seeing a topic in a client s user recommendations. Ranking of a given topic is based on 

Trends are computed across all sources. Those with broad coverage across multiple sources are ranked higher than those trends discovered on a single source or a limited number of sources.

Where Terms of Service allow external sources are mined and ranking are boosted where matches are found for example comparing television trend stories with those on internet news sites. 

Direct searches and specific user topic selection clicking on a Topic combined with algorithm balancing serve as valuable indicators that a topic is popular. These algorithms may be carefully balanced to ensure that prominently placed keywords do not become self fulfilling.

Directed search is the process of providing search results for user queries. These queries can come from text box entrees or by trending topics requests as opposed to the taste graph search for multiple entries . These queries can be defined as 

Which simply means that a user has entered a query for a specific topic such as Lady Gaga. Processing can include query tokens such as AND OR etc.

Searches that contain context information or filters. For example location London returns only results from London and in the case of a combination riots location Libya will return only results related to riots in Libya.

One index implementation uses ElasticSearch a scalable derivative of Apache Lucene or its web enabled sister product Solr . This provides scalability and query processing but another implementation could be chosen to provide equivalent functionality.

The result of a search query is a response document containing an array of results. This result format is based on MediaRSS structure and is provided in multiple formats so that the client device can choose the best suited structure for example JSON .

This component receives a user s taste graph data and stores it for comparison against video topics. This comparison matches the user with topics first with topics from the existing topic index and second with the real time stream of newly created topics as they are received. The user s taste graph combines profile information such as gender age and location with other user information such as the user s interests.

Just as categorization is applied to the incoming data for Topic Extraction and video segmentation the user s interests are also processed to provide equivalent ontological data for search matching.

Users are offered the option to connect the application to external networks to import existing taste graph information. Depending on the client program a user can input profile information as well as their specific interests. Facebook s Open Graph formerly Facebook Connect is the most prevalent example of this but other available graphs such as Twitter LinkedIn and others can be used to gather user information.

Unique information such as User ID values is valuable as part of a user s profile but may be ignored in the process of topic relevance. Email addresses however are considered a factor when determining a user s interest simply because their sources can be used to determine what kinds of data a user may be looking for. For example a .edu address may be less likely to be looking for current culture and more likely to be looking for factual information.

Discreet data can be organized into individual sets such as Age Location Gender and Religion to form an applicable basis for topic matching. Discreet data may require less preprocessing by comparison than abstract data does.

User profiles may contain interests in the form text keywords such as band names books sports and film titles. Depending on the data source this information can be supplied with context. Interests such as Books Television and Film interests may be separated into specific categories or they may be grouped together.

The System automatically attempts to categorize this abstract data so that user profiles better match an index.

API specific data is data specific to the source of the social graph for example Facebook User Name Twitter User Name etc. This information is not highly value on it own but it opens a path to yet more information.

Tokenization for interest graphs does not occur in the same way as it does for inbound text. An interest like Kings of Leon is taken as a complete expression rather than being divided into individual words. However in languages where appropriate definite articles can be stripped for the purposes of the dictionary lookup however their presence is still noted. For example an interest in The Beatles is queried against the index as Beatles but an additional parameter notes the inclusion of the definite article the so that a result for the band rather than the insect is identified.

The dictionaries used are the same as those used to categorize inbound text from the Capture Platform . Sets of common terms from taste graph profiles form a valuable data source in determining popular out of dictionary expressions. The System define the dictionary as providing the following 

For example in a location based lookup London can be expanded to Location London England United Kingdom Europe .

Once these lookups have completed we are left with basic profile information alongside and an expanded graph of user information.

As with the inbound data categorization can yield multiple results for individual keywords. Confidence values are applied to each. Because of the scale of data available processing is assisted by determining a broad demographic for the user. If the System is given the basic information that a user is a 24 year old US male with an interest in sports the System can quickly provide a set of related topics.

In order to expedite lookup of users from inbound topics for real time push profile data is stored in an inverted index with topics forming the key to weighted user lists. Instead of serving as the primary data store this data source is simply used to provide an optimized lookup.

In addition to the interests explicitly defined for a user data relating to the user s social graph of friends or connections is also processed when available. While this data is not the primary indicator of a user s interests it does form a lower weighted component to be used in determining a user s potential interests. In simple terms if your friends all like rock music the System extrapolates that you may like rock music too.

Used exclusively a user s friends interests and broader demographic data can be used to generate a subset of recommended topic items that fall outside a user s core interest graph. By representing these items and monitoring the users explicit and implicit feedback to them views ratings etc. the System can expand the user s set of interests and broaden the media they are exposed to.

The taste graph is paired with the index to create a list of relevant results. These results may be from the index database as a whole or returned according to context relevant in news relevant in sport relevant in music relevant in a location etc. .

When a user first defines their interests a large quantity of information is processed to quickly return a relevant list of results. Because of this the infrastructure is optimized to efficiently deliver results using big data database and server tuning techniques. Rather than implementing any platform logic this sectioning is more a matter of server configuration and is largely invisible to the platform processing.

At the lowest level disk usage can be segmented in a Redundant Array of Independent Disks RAID configuration to increase performance.

The data may also be split across severs to increase performance and redundancy. For the search index ElasticSearch can be configured in a multiple server configuration so that queries are processed across a number of servers in parallel.

For the database a vast majority of database solutions provide support for server clusters and data replication for high volume high performance data processing. The nature of the data means that it is best suited to a non relational database structure which allows for less complex replication processes compared to RDBMS solutions . As an example MongoDB provides relatively easily configured replication and storage capabilities suitable for the platform service but many alternative options are available that may be employed Cassandra HBase etc. 

In order to provide context relevant results the System uses a search index which provides support for faceted search . This means that the search keyword s can be supplemented with additional data to filter results.

There is a connection between this and the context of topics described earlier. For example a standard search for Beatles may return results for both the band or the animal in equal parts depending on what has more references in the index. In a facet assisted search with music as the facet context only results for the band will be returned.

As described in Topic Extraction additional information provided from various dictionary lookups is added to the index with each topic brought in from the Capture Platform . Additionally taste graph data the query is given context in the same way. This provides the index and query facets with additional information for search lookups.

Many search index technologies provide support for faceted search such as Lucene and many if its derivatives ElasticSearch Solr etc. .

Caching occurs on several levels thus exploiting the relatively cheap cost of storage over the less efficient use of processing power.

API outputs provide cached output data as appropriate following standard web caching methodologies e.g. content expiry dates etags server side rendered HTML output caching database lookup caches etc. .

Both the index and database contain internal transparent memory management caching to optimize disk IO in the case of Solr ElasticSearch MongoDB and many alternatives. 

By extracting the topic and preforming processing before adding data to the index the system enables the Search platform to provide more logic driven caching options by creating separated indexes specific to search query types. For example by knowing the source of content and context of queries the System can apply different caching rules accordingly a search for a personality would likely require an up to date immediate result from un cached indexes of news content whereas a search for Polar Bears could draw from a cached result.

As topics are extracted they are queried against an inverted index of user interests. Topics are then sent to individual user queues to be drawn upon for relevant results the next time a query is made.

To prevent this preprocessing task from growing indefinitely lists are only maintained for users who have connected to the system within the past 30 days. With this segmentation an active user s search is passed through their personalized index and filtered according to query terms and facets.

Faceted searches provide some efficiency within the index for context based queries these can be divided at processing time to provide a single endpoint to client requests for example to only return results relevant to sports business news music etc.

These examples describe isolated indexes that duplicate data also stored in the core index. The core index is a single index of all topics that is queried when a suitable smaller pre cached index is not available. In essence the core index is a master index of all information stored in the system while isolated indexes are smaller more specific indexes based in trending topics.

When a user is reviewing a video they may wish to view related items for that clip. In this case the topic and context of each video can be used in place of the user s taste graph to retrieve and deliver related results.

In effect the custom queue itself can be said to be a list of recommendations based on the users interests. This concept is extended to include the interests of their friends which may not overlap with the users core interests but is assumed to be loosely relevant.

The queue offers options to client implementations to choose different options for ordering a result list 

Relevance is determined by topic and interest confidence matching and is driven by Lucene or an alternative search engine s native relevancy mechanisms.

In general physical segmentation of video clips is avoided to allow modification of the clip timings at a later date segmentation is logical and does not produce physical file changes. Topic start and end times are stored and delivered to the client with the topic data which then sends them to the Media Storage and Delivery Platform where long form files are read and the appropriate wrapper placed around the Text Topic Data and Video Data.

Incoming video is delivered to the Media Storage and Delivery Platform in continuous chunks such as 24 1 hour videos each day. These videos are stored in a way that enables lookup based on the content source and timing information.

At the same time the Search platform extracts Topic IDs and stores them in the Index of TV along with their timing information. This timing information is encoded to the UTC time so regional time zone variations do not need to be considered. Topics returned to the client such as search results or matches to a user s taste graph contain start and end time information for the topic which is passed to the Media Storage and Delivery Platform when the user requests playback.

Additionally the channel name should be considered as a token so where the channel name might be CNN in practice the actual disk structure may follow a wider pattern to differentiate between CNN International CNN HD and or provide character formatting to compensate for file system restrictions on non ASCII characters.

For example if the client needs to access a video item such as a specific interview with Barak Obama the Media Storage and Delivery Platform is delivered the topic source the topic start time and the topic end time 

Using this information the Media Storage and Delivery Platform understands that the required video file is at the location 

The platform also understands to start playback 12 minutes and 22 seconds into the video block and end after playing for the video 1 minute and 32 seconds. This is a good example of the process. In practice the actual processing is slightly more complex as multiple video files may be involved if a request spans more than one file in which case the streaming server compensates by combining two files into an output.

There is another exception to this process where the delivery server cannot provide dynamic streaming for example Wowza Media Server delivers H.263 encoded 3gp videos the Search platform can queue a Delivery Platform API request to pre encode content to the required format so that the Media Storage and Delivery Platform will deliver a specific pre encoded video file continuing the example above uk cnn 2011 01 01 17 12 33.3gp .

An API is a source code based specification intended to be used as an interface by software components to communicate with each other. An API may include specifications for routines data structures object classes and variables.

A Content Delivery Network is a system of computers containing copies of data placed at various nodes of a network. When properly designed and implemented a CDN can improve access to the data it caches by increasing access bandwidth and redundancy and reducing access latency.

Redundancy within a computer network means that multiple versions of a single piece of data exist in multiple places across a network. This is useful because it means that a program searching for this information is more likely to find it needs less bandwidth to continue its search and in the case of damage to a physical server the data isn t truly gone because other copies of that data exist elsewhere.

Client at least in the context of this document is meant to indicate a program that interacts with the main Real time Delivery of Segmented Video but is not a part of it. A client can be can be anything from a mobile phone app to a web based user interface. For the most part clients are used by users to access the database and retrieve data.

A Client Device is any device that runs a client program such as an Apple Iphone an Android capable phone or a TV with IPTV capabilities.

Cloud infrastructure or simply the cloud is a system of data organization in which pieces of data are scattered across a network of physical servers. These servers can be pretty much anywhere in regards to their physical location but are all linked by a common cloud network. Cloud infrastructure has many benefits including a massive capability for redundancy a capability to store and efficiently use local and regional data and a network that will lose little data in the case that a physical server is damaged.

DVB is a suite of internationally accepted open standards for digital television. DVB standards are maintained by the DVB Project an international industry consortium with more than 270 members and they are published by a Joint Technical Committee JTC of European Telecommunications Standards Institute ETSI European Committee for Electrotechnical Standardization CENELEC and European Broadcasting Union EBU .

EPG provides users of television radio and other media applications with continuously updated menus displaying broadcast programming or scheduling information for current and upcoming programming.

Function at least in regards to the context of this document is used to describe any task that a program or a component of a program is designed to do. For example The Capture Platform provides a number of functions simply means that the Capture Platform has the capability of performing a number of tasks.

IPTV is a system in which television services are delivered using the Internet or a similar wide scale network instead of using traditional terrestrial satellite signal and cable television formats.

Line 21 or EIA 608 is the standard for closed captioning in the United States and Canada. It also defines Extended Data Service a means for including information such as program name in a television transmission.

Long Form video at least within the context of this document simply refers to video data before it has been processed. The actual length of the video may vary but in most cases it can be assumed to be about the length of a television show or movie.

RSS originally called RDF site summary is a family of web feed formats used to publish frequently updated works. Media RSS simply refers to an RSS feed that is used for media.

Optical character recognition or OCR is the mechanical or electronic translation of scanned images of handwritten typewritten or printed text into machine encoded text. This conversion is used by the System to translate close captioned text into a form that the Search Platform is capable of reading.

RAID is a storage technology that combines multiple Physical storage servers so that they function as a single unit. This single unit known as a Logical unit doesn t require that the servers be physically close only that they are linked by a network. Data is distributed across the drives in one of several ways called RAID levels depending on what level of redundancy and performance via parallel communication is required.

RDBMS is a Database Management System in which data is stored in tables and the relationships between the data are also stored in tables. The data can be accessed or reassembled in many different ways without requiring that the tables be changed.

REST is a form of software architecture for distributed hypermedia systems such as the World Wide Web. REST style architectures consist of clients and servers. Clients send requests to servers servers process requests and return appropriate responses.

A social graph is a collection of data points that represent a person s interests and how those interests interact. Social graphs can be expanded to include information about a group of people or about a group of interests shared by multiple people.

A topic according to this system is a basic description of a chunk of video. The topic can be broad such as Sports or News or specific such as Lady Gaga or Bill Gates. A chunk of video can have as many topics as is required to describe it. These topics are what the search platform looks for when it attempts to find relevant videos to a search query.

While various embodiments have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of a preferred embodiment should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the claims and their equivalents for any patent that issues claiming priority from the present provisional patent application.

For example as referred to herein a machine or engine may be a virtual machine computer node instance host or machine in a networked computing environment. Also as referred to herein a networked computing environment is a collection of machines connected by communication channels that facilitate communications between machines and allow for machines to share resources. Network may also refer to a communication medium between processes on the same machine. Also as referred to herein a server is a machine deployed to execute a program operating as a socket listener and may include software instances.

In all descriptions of servers or other computing devices herein whether or not the illustrations of those servers or other computing devices similarly show a server like illustration in the figures it should be understood that any such described servers or computing devices will similarly perform their described functions in accordance with computer readable instructions stored on a computer readable media that are connected thereto.

Resources may encompass any types of resources for running instances including hardware such as servers clients mainframe computers networks network storage data sources memory central processing unit time scientific instruments and other computing devices as well as software software licenses available network services and other non hardware resources or a combination thereof.

A networked computing environment may include but is not limited to computing grid systems distributed computing environments cloud computing environment etc. Such networked computing environments include hardware and software infrastructures configured to form a virtual organization comprised of multiple resources which may be in geographically disperse locations.

Various terms used herein have special meanings within the present technical field. Whether a particular term should be construed as such a term of art depends on the context in which that term is used. Connected to in communication with or other similar terms should generally be construed broadly to include situations both where communications and connections are direct between referenced elements or through one or more intermediaries between the referenced elements including through the Internet or some other communicating network. Network system environment and other similar terms generally refer to networked computing systems that embody one or more aspects of the present disclosure. These and other terms are to be construed in light of the context in which they are used in the present disclosure and as those terms would be understood by one of ordinary skill in the art would understand those terms in the disclosed context. The above definitions are not exclusive of other meanings that might be imparted to those terms based on the disclosed context.

Words of comparison measurement and timing such as at the time equivalent during complete and the like should be understood to mean substantially at the time substantially equivalent substantially during substantially complete etc. where substantially means that such comparisons measurements and timings are practicable to accomplish the implicitly or expressly stated desired result.

Additionally the section headings herein are provided for consistency with the suggestions under 37 CFR 1.77 or otherwise to provide organizational cues. These headings shall not limit or characterize the invention s set out in any claims that may issue from this disclosure. Specifically and by way of example although the headings refer to a Technical Field such claims should not be limited by the language chosen under this heading to describe the so called technical field. Further a description of a technology in the Background is not to be construed as an admission that technology is prior art to any invention s in this disclosure. Neither is the Brief Summary to be considered as a characterization of the invention s set forth in issued claims. Furthermore any reference in this disclosure to invention in the singular should not be used to argue that there is only a single point of novelty in this disclosure. Multiple inventions may be set forth according to the limitations of the multiple claims issuing from this disclosure and such claims accordingly define the invention s and their equivalents that are protected thereby. In all instances the scope of such claims shall be considered on their own merits in light of this disclosure but should not be constrained by the headings set forth herein.

