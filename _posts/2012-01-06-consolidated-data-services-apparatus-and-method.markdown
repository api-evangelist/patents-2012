---

title: Consolidated data services apparatus and method
abstract: An apparatus for consolidated data services comprising a plurality of devices, a plurality of data services and a content application programming interface (API). A user API provides user identification for each of the plurality of devices using one or more of a plurality of user API methods. A feedback API configured to receive data from each of the plurality of devices that identifies media content that was delivered to the plurality of devices using one or more of a plurality of feedback API methods. A device API configured to provide a client system to one or more of the plurality of devices using one or more of a plurality of device API methods. A web service consolidator coupled to the content API, the user API, the feedback API, the device API, the update API, a plurality of data services and the plurality of devices through the communications media.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08572685&OS=08572685&RS=08572685
owner: 
number: 08572685
owner_city: 
owner_country: 
publication_date: 20120106
---
The present disclosure relates to data services and more particularly to a web services apparatus and method that allows diverse web services to be consolidated through a common web services platform.

The Internet is commonly used to provide access to data services providers. The ease for establishing a connection with a data service provider over the Internet has resulted in data service providers having dedicated service portals. However because of the large number of different data service providers data service users have to become proficient in using the interface for each different data service provider which leads to mistakes and errors. In addition peripherals and equipment must be configured to interface with different data services which also leads to mistakes and errors.

An apparatus for consolidated data services comprising a plurality of devices a plurality of data services and a content application programming interface API . A user API provides user identification for each of the plurality of devices using one or more of a plurality of user API methods wherein each of the user API methods includes a required signature parameter. A feedback API configured to receive data from each of the plurality of devices that identifies media content that was delivered to the plurality of devices using one or more of a plurality of feedback API methods. A device API configured to provide a client system to one or more of the plurality of devices using one or more of a plurality of device API methods. An update API configured to provide an updated client system to one or more of the plurality of devices using one more of a plurality of update API methods. A web service consolidator coupled to the content API the user API the feedback API the device API the update API a plurality of data services and the plurality of devices through the communications media the web service consolidator configured to control interactions between the content API the user API the feedback API the device API the update API a plurality of data services and the plurality of devices.

Other systems methods features and advantages of the present disclosure will be or become apparent to one with skill in the art upon examination of the following drawings and detailed description. It is intended that all such additional systems methods features and advantages be included within this description be within the scope of the present disclosure and be protected by the accompanying claims.

In the description that follows like parts are marked throughout the specification and drawings with the same reference numerals. The drawing figures might not be to scale and certain components can be shown in generalized or schematic form and identified by commercial designations in the interest of clarity and conciseness.

As used herein hardware can include a combination of discrete components an integrated circuit an application specific integrated circuit a field programmable gate array or other suitable hardware. As used herein software can include one or more objects agents threads lines of code subroutines separate software applications two or more lines of code or other suitable software structures operating in two or more software applications or on two or more processors or other suitable software structures. In one exemplary embodiment software can include one or more lines of code or other suitable software structures operating in a general purpose software application such as an operating system and one or more lines of code or other suitable software structures operating in a specific purpose software application. As used herein the term coupled and its cognate terms such as couples or couple can include a physical connection such as a wire optical fiber or a telecommunications medium a virtual connection such as through randomly assigned memory locations of a data memory device or a hypertext transfer protocol HTTP link a logical connection such as through one or more semiconductor devices in an integrated circuit or other suitable connections. In one exemplary embodiment a communications medium can be a network or other suitable communications media.

System includes consolidated web service which coordinates user API content API feedback API update API and device API and which interfaces with devices through through communications media and with data services through through communications media . Communications media and can separate communications media such as dedicated high speed data connections or can the same communications media or combinations of communications media and can be a wire line communications medium or media such as the public switched telephone system or Internet a wireless communications medium or media an optical communications medium or media a digital or analog communications medium or media or a suitable combination of these or other communications media.

Consolidated web service can include a request handler an interface manager a database abstraction layer a database such as for service data user data history data update data device data or other suitable data content service mapping and other suitable functionality. In one exemplary embodiment the request handler can receive requests from user devices and can manage responses to the requests such as to track individual requests and addresses associated with the device that generated the requests . The interface manager can control access to user API content API feedback API update API and device API that may be required to respond to request received from the user devices. The database abstraction layer can control access to the database such as to prevent user data from being accessed by unauthorized personnel.

Content API can interface with devices through and data services through through consolidated web service or can also or alternatively be implemented as a plurality of dedicated content APIs that each interface with consolidated web service devices through and one or more of data services through This architecture minimizes the need for data services through to have customized software or algorithms for operation within system .

In one exemplary embodiment a device can interface with any of data services through through consolidated web service user API content API feedback API and update API . In this exemplary embodiment a device having a user interface such as a tablet computer can access a data service such as an audio data service provider or video data service provider using a single interface. As described in greater detail herein a user can log onto an account hosted by consolidated web service using their tablet computer can receive a user interface that is optimized for the tablet computer can select a type of data for delivery to the tablet computer and can receive that data in a format that can be displayed on the tablet computer.

Devices through can include a client application that provides a client controller API a consolidated web services controller interface a consolidated web services query library and other suitable client functionality. In one exemplary embodiment the client application can be obtained from a website for a personal computer from a smart phone or tablet application store or from other suitable locations. In another exemplary embodiment the consolidated web services query library can be a C library to consume the web services communication layer and the consolidated web services controller interface can be the data abstraction of the consolidated web services controller responses for the client controller API.

In another exemplary embodiment a user can log onto an account hosted by web service provider using a smart phone and can receive a user interface that allows the user to select a different device such as stand alone speakers or a television set to receive the selected data from the selected data service. In this exemplary embodiment the user can select a sound recording to be delivered to a stand alone speakers a video recording to be delivered to a television set or other suitable data text images to be delivered to other suitable devices printers copiers fax machines . In this manner system allows a device such as a smart phone personal computer or tablet computer to operate as a universal remote control device for a plurality of diverse devices such as speakers stereo systems televisions printers fax machines or copiers.

Algorithm begins at where a method call is received. As discussed in greater detail herein the method call can include data in a predetermined data format having required data fields and optional data fields. By utilizing the architecture of system the different APIs can utilize method calls that have common data fields that can be readily translated for use by other APIs and other method calls so as to provide the disclosed interoperability. The algorithm then proceeds to .

At it is determined whether required data fields for the method call are present. As disclosed in greater detail herein each method call can have one or more predetermined required data fields such that if a required data field is not present then the method call is incomplete. The required data fields for a method call can be determined by looking up an associated data table or other suitable data structures associated with the identifier for the method call which can be included in a predetermined location within the method call data format. If it is determined at that a required parameter is not present the algorithm proceeds to where a suitable error message is generated. In one exemplary embodiment the error message can generate a user display that requests additional information a selection such as a device selection or a data service selection or other suitable information. In another exemplary embodiment the error message can be a query to consolidated web service user API content API feedback API update API or other suitable systems or devices where the response to the query can provide the missing parameter or other suitable processes can also or alternatively be used.

If it is determined at that all required parameters are present the algorithm proceeds to where a call to a data service is formatted such as using content API . In another exemplary embodiment a call to user API content API feedback API update API or other suitable systems or devices can be generated such as where a user is configuring their system or selection choices or other suitable functions can also or alternatively be implemented. The algorithm then proceeds to .

At a call is transmitted to the data service and the response to the call is received. In one exemplary embodiment the call can include a request for a specific type of data audio program video program a list of content a list of artists or programs or other suitable data. The algorithm then proceeds to where it is determined whether the response included an error message. In one exemplary embodiment the error message can indicate that the data service is unavailable that the user does not have authorization for the requested content or other suitable error messages. If it is determined that an error message has been received the algorithm proceeds to where a suitable error message is generated. In one exemplary embodiment the error message can generate a user display that requests additional information a selection such as a new program selection or a new device destination or other suitable information. In another exemplary embodiment the error message can be a query to consolidated web service user API content API feedback API update API or other suitable systems or devices where the response to the query can provide the missing parameter or other suitable processes can also or alternatively be used. Otherwise the algorithm proceeds to .

At data is formatted for delivery to a device. In one exemplary embodiment the data can include a user interface where the data is formatted to be used in a user interface template. In another exemplary embodiment the data can include audio data video data image data text data or other suitable data that is formatted for delivery to a speaker a television the display of a personal computer or tablet computer or other suitable device. The algorithm then proceeds to where the data is delivered to the device.

In operation algorithm allows diverse data services and devices to interface through a common platform that includes consolidated web service user API content API feedback API and update API . Algorithm can also or alternatively be implemented using object oriented programming where the different states disclosed above and in further detail below are related based on object oriented principles. The various APIs and associated methods described below can be used within the architecture of system and with algorithm to provide the functionality discussed herein. In that regard the discussion of the APIs and associated methods that follows can be applied to system and algorithm as well as to other suitable systems and algorithms.

Algorithm begins at where a consolidated web service is access from a user device. In one exemplary embodiment the user device may have an installed client system that operates to provide access to the consolidated web service. In another exemplary embodiment the user device can access a web site or other resource and can receive initial configuration for accessing the consolidated web service. Other suitable processes can also or alternatively be used such as those described in greater detail herein. The algorithm then proceeds to .

At the device is determined. In one exemplary embodiment the device can be determined using a suitable method as disclosed herein from a machine id such as where the device has an existing client system. In another exemplary embodiment the device can be determined by querying the device or user for device type data. In yet another exemplary embodiment the device can be determined for a peripheral that is accessed from a user interface device. Other suitable methods or processes can also or alternatively be used. The algorithm then proceeds to .

At a device API is accessed. In one exemplary embodiment the device API can be device API or other suitable device APIs. The algorithm then proceeds to .

At it is determined whether an update for the device is available needs to be installed has been requested or otherwise needs to be accessed. In one exemplary embodiment device API methods can be executed. If it is determined that an update for the device exists the algorithm proceeds to where the update is installed. In one exemplary embodiment an update API method can be used to update the device or to perform other suitable functions as disclosed herein. The algorithm then proceeds to . Likewise if it is determined at that no device update is available or required the algorithm proceeds to .

At a use API is accessed. In one exemplary embodiment user API can be accessed such as to authenticate a user or to perform other suitable user API methods as disclosed herein. The algorithm then proceeds to .

At the user logs on to the consolidated web service. In one exemplary embodiment a user authentication or logon method of user API can be implemented as disclosed herein. The algorithm then proceeds to .

At a content API is accessed. In one exemplary embodiment the content API can be content API or other suitable content APIs and one or more content API methods as disclosed herein can be implemented. The algorithm then proceeds to .

At a user selection is received. In one exemplary embodiment the user selection can be a content selection such as by using one or more of the content API methods as disclosed herein or other suitable user selections. The algorithm then proceeds to .

At it is determined whether an error has been generated. In one exemplary embodiment the error can be one of the errors disclosed herein that are generated in response to the content selection such as by the content service the content API or other suitable systems. If it is determined that an error has been generated the algorithm proceeds to where an error message is generated. In one exemplary embodiment the error message can be generated for display on the user device for review by an operator of system or other suitable error messages can be generated. The algorithm then returns to terminates or other suitable methods as disclosed herein or procedures can be used.

If it is determined at that no error has been generated the algorithm proceeds to where data is formatted for the device. In one exemplary embodiment content data can be formatted for delivery to the user device such as by the content service. In other exemplary embodiments content data can be formatted for delivery to a peripheral device data for a user interface display can be generated or other suitable data can be formatted that is responsive to the user selection. The algorithm then proceeds to .

At data is delivered to the device. In one exemplary embodiment the data can include audio or video content such as sound recordings movies television shows or other suitable audio or video content. In another exemplary embodiment the data can include text data image data telephone message facsimile transmissions print jobs or other suitable data. The algorithm then proceeds to .

At it is determined whether feedback is required or has been generated. In one exemplary embodiment feedback can include information about audio or video content that has been delivered. In another exemplary embodiment feedback can include user entered feedback or other suitable data. If it is determined that feedback is required or has been generated the algorithm proceeds to where a feedback API is accessed. In one exemplary embodiment feedback API can be used to implement an associated method as disclosed herein or other suitable feedback API methods or processes can be implemented. The algorithm then proceeds to . Likewise if it is determined at that feedback has not been generated or is not required the algorithm proceeds to .

At it is determined whether the user has logged off such as by selecting a logoff command or control by timing out or in other suitable manners. If the user has logged off the algorithm proceeds to otherwise the algorithm returns to or other suitable states.

In operation algorithm allows diverse data services and devices to interface through a common platform that includes consolidated web service user API content API feedback API and update API . Algorithm can also or alternatively be implemented using object oriented programming where the different states disclosed above and in further detail below are related based on object oriented principles. The various APIs and associated methods described below can be used within the architecture of system and with algorithm to provide the functionality discussed herein. In that regard the discussion of the APIs and associated methods that follows can be applied to system and algorithm as well as to other suitable systems and algorithms.

Content providers have varying functions parameters return types and processes for communicating with other systems such as Simple Object Access Protocol SOAP eXtensible Markup Language Remote Procedure Call XML RPC and JavaScript Object Notation Remote Procedure Call JSON RPC and Relative Expression Software Tool REST . In addition content providers have varying methods of authenticating users that further complicate web service implementation. Content API provides a uniform interface to these different protocols.

In one exemplary embodiment content API can allow a call to be executed across different data services through in a uniform fashion by using proxy calls through a content API REST Interface. REST is an architectural style developed alongside HTTP and can be utilized for client server communication rather than building a layer on top of client server communications such as SOAP or XML RPC. Other suitable interfaces can also or alternatively be utilized.

Web service calls can vary between content providers and a call from one web service may have no basis for a call in another or simply may not exist. For example a web service call to retrieve a list of top tracks would not make sense for a content provider that specializes in photos. For this reason such a call would result in a mapping error that could be handled appropriately. In situations where content providers offer similar services the mapping error might not be apparent. The error system employed by content API allows non existent calls to be properly handled in addition to providing a means for investigating a content provider s web service.

CONTENT API METHODS. The following sections describe content API methods and parameters. Due to the open ended nature of content API the responses from calls depend more on parameters passed than on the method invoked. Below is a description of methods for content API and each method s available parameters. While some parameters are always required such as partner key the intention of the request will determine which parameters are used and will vary from call to call.

USER API METHODS. User API allows a partner developer to create and manage profiles on behalf of the user. In addition to storing general information about the user the user profile manages multiple content provider credentials by employing a keychain model. User API is used for accessing content provider user data such as a user s music library playlists favorites friends or other suitable data.

Sharing and bookmarking can also be provided by User API . Users can be allowed to create bookmarks and playlists to access relevant content quickly and to share content. Unlike content API which can be open ended to accommodate various content providers user API can expose methods and parameters more like a traditional web service.

Signatures can be used for user API calls and calls that use a session key. A signature can be created without a session key e.g. SHA1 method ordered parameters partner secret or with a session key e.g. SHA1 method ordered parameters partner secret session key . The SHA1 output can be converted to hexadecimal format. The method used can be the call method for example get from content API or login from user API . Ordered parameters can be a concatenation of each parameter ordered by parameter key name followed by the parameter value.

The partner secret can be the private token given to a partner when the partner key is received. The session key can be the token returned from a user authentication call such as register login get session and create session. The session key can be added to the signature when it is needed to perform a call. The query library can automatically create and add a signature to the query.

In one exemplary embodiment four user API methods can be used to return a session 1 register 2 login 3 session 4 session add. The session key can be a unique token that identifies the user when making calls to the web service. The session key can expire after a predetermined amount of time. In addition to the session key a coordinated universal time UTC timestamp can be returned that marks the session expiration. When the session has expired it will no longer be valid and a call must be made to retrieve a new session. This call can be performed without prompting the user to login again assuming the application has properly stored the user s web service username and authorization token. The authorization token can be a SHA1 hash of the user s web service password which can be captured when the user performs a login. The application does not need to store a plaintext password as none of the functions require it apart from registration.

Below are descriptions of exemplary user API methods. Some user API methods require https in this exemplary embodiment and will result in an error response if not secure. Other suitable embodiments that do not require https can also or alternatively be used.

The register method registers a user. On success a new user will be returned with a new session. Otherwise an appropriate error is returned. The HTTP Method for register is POST and register requires https. POST is a request method supported by the HTTP protocol used by the World Wide Web and can be used when the client needs to send data to the server as part of the request such as when uploading a file or submitting a completed form. In contrast to the GET request method where only a URL and headers are sent to the server POST requests also include a message body. This allows for arbitrary length data of any type to be sent to the server. The parameters are 

The login method is used to login a user. On success login can return a user with the current valid session or a new session if the user s current session has expired. Otherwise login can return an appropriate error. All pertinent user data can be returned by this call. The HTTP method for login is GET and login requires https. The parameters are 

The logout method is used to logout a user and removes the user s current session. The HTTP method for the logout method is GET and the parameters are 

The update method updates a user s profile information. On success update will return a user. Otherwise update will return the appropriate error. The HTTP Method for update is POST and update requires https. The parameters are 

The password update method can update a user s password. On success returns status OK. On fail returns status FAIL. The HTTP Method is POST and the password update method can require https. The parameters are 

The password reset method resets a user s password. An email message can be sent with a temporary password. The HTTP method is POST and it requires https. The associated parameters are 

The exists method checks to determine whether a username is already in use. The associated HTTP Method is GET and the parameters are 

The session method can retrieve a user session. On success this method will return the current valid session or a new session if the user s current session has expired. Otherwise the method will return the appropriate error. This method does not return user data. The HTTP Method used is GET https is required and the parameters are 

The session add method creates a new user session. On success this method will return a user with a new session. Otherwise the method will return the appropriate error. This will overwrite the current session for this user even if the current session is valid. The HTTP Method is GET https is required and the parameters are 

The services method retrieves a user s content services. The HTTP Method used is GET and the parameters are 

The service add method adds a content provider service. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. This method can be used where user authentication is specified by username and password. The HTTP Method is POST https is required and the parameters are 

The service add method adds a content provider service. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. This method can be used where user authentication is specified. The HTTP Method is POST https is required and the parameters are 

The service remove method removes a content provider service. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. The HTTP Method is GET and the parameters are 

Users can share resources using a web service sharing mechanism. The share method can get bookmark share with another user the HTTP Method is GET and the parameters are 

The shares method gets user s bookmark shares based on different criteria. The HTTP Method is GET and the parameters are 

The share add method can add bookmark share with another user. The HTTP Method can be POST and the parameters are 

The shares remove method removes bookmark shares based on different criteria. The HTTP Method used is GET and the parameters are 

The bookmark method can get a bookmark that is specified by id. The HTTP Method is GET and the parameters are 

The bookmark remove method is used to remove a bookmark specified by the id. The HTTP Method is GET and the parameters are 

The bookmarks remove method removes all user s bookmarks. The HTTP Method is GET and the parameters are 

The playlist method is used to get a user s playlist specified by playlist id. The HTTP Method is GET and the parameters are 

The playlists remove method removes all playlists for a user. The HTTP Method is GET and the parameters are 

The playlist resources or playlist tracks methods are used to update a user playlist. The HTTP Method is POST and the parameters are 

The playlist resource add or playlist track add methods are used to add a track resource to a playlist. The resource can be of type track . The HTTP Method is POST and the parameters are 

The playlist resource remove or playlist track remove methods can be used to remove a track resource from a playlist. The HTTP Method is GET and the parameters are 

The device method is used to get required information for a user s device such as a model. The parameters are 

The queue all method is used to obtain a list of queues which the current user owns. The HTTP Method is GET and the associated parameters are 

The queue get method is used to obtain queue metadata such as for registered users and queue owner to see the metadata. The HTTP Method is GET and the associated parameters are 

The queue add method registers a queue to the current user who becomes the queue owner. The HTTP Method is GET and the associated parameters are 

The queue update method updates queue metadata. Either the name or description can be set. The HTTP Method is GET and the associated parameters are 

The queue remove method unregisters queue ownership for the current user. The HTTP Method is GET and the associated parameters are 

The queue users method provides a list of users registered to the queue such as where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue user add method registers users to the queue such as where the queue owner is registered when the queue is registered where the queue owner is permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue user update method updates the queue user status such as where the queue owner is permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue user remove method removes the user registration with this queue such as where the queue owner is permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue items method is used to list items in the queue such as when the parameter username is passed to return items in the queue for this user where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue items history method is used to list items in the queue history such as when the parameter username is passed to return items in the queue history for this user where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue items waiting method provides a list of items in waiting queue such as where every user has a separate waiting queue and when the parameter username is passed it returns items in the waiting queue for this user where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue items remove method removes items in the queue for the current user. The HTTP Method is GET and the associated parameters are 

The queue items waiting remove method removes items in the waiting queue for the current user. The HTTP Method is GET and the associated parameters are 

The queue items all remove method removes all items associated with the queue for the current user. The HTTP Method is GET and the associated parameters are 

The queue item head method is used to obtain the head item of the queue such as where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue item head update method updates the head item of the queue such as where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue item head rate method rates the head item of the queue such as where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue item enqueue tries to add item to the queue. If the queue is full it enqueues the item to the waiting queue such as where registered users are permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue item dequeue method dequeues the head item from the queue such as where the queue owner is permitted to make this call. The HTTP Method is GET and the associated parameters are 

The queue item remove method removes an item specified by queue item id such as where the user who submitted the item or the queue owner makes the call. The HTTP Method is GET and the associated parameters are 

FEEDBACK API METHODS. Feedback API tracks user actions. In addition to providing data for user analytics it also provides the basis for user history and charts. The track method tracks a user action. If no user is passed the action is tracked anonymously and the associated parameters include 

The history method retrieves a user s history. Filters can be passed to focus the results. The parameters include 

DEVICE API METHODS. Device API provides an interface for managing data related to devices such as a speaker cell phone iPod or iPad. The model add method adds a device model and includes the following parameters 

The model remove method is used to remove a device specified by an id and has the following parameters 

UPDATE API METHODS. Update API provides methods for checking if an update exists for any device or application including the download URL to the update if one exists. For example iOS application updates would likely be downloaded via the Apple App Store but Update API can still be used to check if the update is available and provide the iTunes URL. It also provides a method for adding an update for a device or application. The check method is used to check for an update for a device or application. The HTTP Method used is GET and the associated parameters are 

In addition to the web service APIs service specific APIs can also be used to provide optimized interface capability to specific services. Several exemplary service specific APIs are described below.

The Service Alpha Service content get method tracks metadata specified by name and the associated parameters include 

The Service Alpha Service content get method tracks metadata specified by id and the associated parameters include 

The Service Alpha Service content get track method obtains a list of all tracks and the associated parameters include 

The Service Alpha Service content get album track method obtains a list of tracks specified by album name and the associated parameters include 

The Service Alpha Service content get artist track method obtains a list of tracks specified by artist name and the associated parameters include 

The Service Alpha Service get genre track method lists tracks specified by genre name and the associated parameters include 

The Service Alpha Service get album method obtains album metadata specified by name and the associated parameters include 

The Service Alpha Service get album track id method obtains album metadata specified by track id and the associated parameters include 

The Service Alpha Service get album track name method obtains a list of albums specified by track name and the associated parameters include 

The Service Alpha Service get artist albums method obtains a list of albums specified by artist name and the associated parameters include 

The Service Alpha Service get genre albums method obtains a list of albums specified by genre name and the associated parameters include 

The Service Alpha Service get artist method obtains a list of artists and the associated parameters include 

The Service Alpha Service get genre method obtains a list of all genres and the associated parameters include 

In addition to these exemplary methods other suitable methods can also or alternatively be used by applying the user API methods the content API methods the feedback API methods the update API methods and the device API methods described herein.

Service Beta methods include the add Service Beta service method uses the service username and service password parameters to add an existing account or anonymous account and returns an updated user services list. The HTTP Method is POST https is required and the associated parameters include 

The Service Beta get featured artists method obtains a list of featured artists and the associated parameters include 

The Service Beta get artist station tracks method obtains a list of station tracks specified by artist and the associated parameters include 

The Service Beta get current user station tracks method obtains a list of station tracks specified by user such as where user stations play similar tracks selected mostly from favorite tracks and artists and other personal data and the associated parameters include 

The Service Beta get personal station tracks method obtains a list of personal station tracks specified by user such as where the personal station is a station composed almost entirely of the user s favorite tracks and the associated parameters include 

The Service Beta get picked station tracks method obtains a list of picked station tracks specified by station such as where the picked station contains selected tracks and the associated parameters include 

In addition to these exemplary methods other suitable methods can also or alternatively be used by applying the user API methods the content API methods the feedback API methods the update API methods and the device API methods described herein and as shown above for other services.

Service Prime Content API methods include the add Service Prime service method which adds a Service Prime service. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. The HTTP Method is POST https is required and the associated parameters include 

In addition to these exemplary methods other suitable methods can also or alternatively be used by applying the user API methods the content API methods the feedback API methods the update API methods and the device API methods described herein and as shown above for other services.

Service Gamma Content API methods include add Service Gamma service which adds a Service Gamma service. On success a URL is returned. Otherwise an appropriate error is returned. The HTTP Method is POST https is required and the associated parameters include 

The Service Gamma get artist method obtains a list of artists by id. The associated parameters include 

In addition to these exemplary methods other suitable methods can also or alternatively be used by applying the user API methods the content API methods the feedback API methods the update API methods and the device API methods described herein and as shown above for other services.

Service Delta Content API methods include the add Service Delta service method which is used to add a Service Delta service. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. The HTTP Method is POST https is required and the associated parameters include 

The Service Delta get artist by id method obtains artist metadata specified by id and the associated parameters include 

In addition to these exemplary methods other suitable methods can also or alternatively be used by applying the user API methods the content API methods the feedback API methods the update API methods and the device API methods described herein and as shown above for other services.

The Service Sigma Content API includes the add Service Sigma service method. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. The HTTP Method is POST https is required and the associated parameters include 

The Service Sigma get artist method obtains artist metadata with list of albums and the associated parameters include 

In addition to these exemplary methods other suitable methods can also or alternatively be used by applying the user API methods the content API methods the feedback API methods the update API methods and the device API methods described herein and as shown above for other services.

The Service Tau Content API includes the add Service Tau service method which adds a Service Tau service. On success a user is returned with an updated user services list. Otherwise an appropriate error is returned. The HTTP Method is POST https is required and the associated parameters include 

The Service Tau get root links method is used to generate a user interface front end. It returns list of links which can be later used for other methods to browse down the tree retrieving links stations and shows and the associated parameters include 

It should be emphasized that the above described embodiments are merely examples of possible implementations. Many variations and modifications may be made to the above described embodiments without departing from the principles of the present disclosure. All such modifications and variations are intended to be included herein within the scope of this disclosure and protected by the following claims.

