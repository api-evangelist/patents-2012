---

title: System for the discovery and provisioning of artifacts and composites
abstract: The present invention relates to software development in a networked environment, and in particular to a method for automatically assisted generation of composite applications which are composed of instantiable components. The method includes a) dynamically accessing a data source comprising one or more components being potentially suitable for being used within said composite application, b) parsing said data source for a predetermined searched component according to a predetermined functionality specification standard, c) ranking found components according to predetermined ranking criteria, d) defining a list of selected usable components from said ranking, e) storing at least a subset of said selected components locally, f) automatically deploying said composite application from said selected components.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09354848&OS=09354848&RS=09354848
owner: International Business Machines Corporation
number: 09354848
owner_city: Armonk
owner_country: US
publication_date: 20120304
---
This application claims priority to U.S. patent application Ser. No. 12 142 952 currently pending filed Jun. 20 2008 which claims priority under 35 U.S.C. 119 a to European Patent Application Serial Number 07111107.4 filed Jun. 27 2007 the entirety of which are incorporated herein by reference.

The present invention relates to software development in a networked environment. In particular it relates to a method and system for automatically assisted generation of composite applications which are composed of a plurality of components and in which method a template means defines the requirements and specifications of the components of the composite application and wherein the template serves as an input for instantiating the composite application.

In this field the term composite application defines an application hosted on a web portal platform which is built by combining and connecting multiple components such as portlets wikis document libraries or web services for a particular purpose such as a shop or a virtual teamroom application. A single portal platform may host multiple instances of the same composite application for example different teamrooms for different associated user communities. Composite applications are built from a template describing the contained components and their set up and interconnection.

The templating application infrastructure TAI component manages the templates in the system which contain references to instantiable components in a local list of components . As an example a template for shopping applications could consist of a reference to a document library component which is used to hold the available goods and their descriptions a shop portlet that lets clients process actual shopping transactions an invoice business component that handles the payment process and a blogging component that allows clients to comment on their satisfaction.

The TAI component also creates application instances from the templates via an instantiation component which creates separate instances of the referenced business components typically by creating or copying individual configurations for these components such that multiple application instances can be created from the same template without interfering with each other.

For the above mentioned sample template the instantiation would among other things create an individual storage compartment in the document library an individual configuration of the invoice component referring to the bank account and an individual configuration for the shop portlet that is set up to display goods from the created document library and to delegate payment processing to the created invoice component instance.

In particular the instantiation needs to create the necessary portal artifacts like pages that allow to interact with the created composite application which is typically done by employing a specific handler that creates those portal artifacts and links them with the business components of the application.

The created composite application instances hold a context that lists the component instances that make up the composite application

In prior art composite applications and their components which are also referred herein as artifacts have to be individually developed or supplied by a vendor. Specifically when different composite applications or artifacts are offered by different vendors a decision which composite application or artifact to use for building up a new own composite application requires significant knowledge about the properties of the artifacts offered by the various vendors. These properties comprise the scope of functions an artifact is able to deliver compliant of input data and output data in order to build in an artifact into the planned own composite application as well as precise descriptions of APIs to other artifacts or components cooperating with. This is the reason why such artifacts need to be manually observed analyzed and finally deployed. Further a planned composite application needs then to be manually assembled by using the artifact mentioned above. The assembly can then be stored as a template.

Alternatively composite applications can also be created based on templates that contain the list of components that build up the composite application. If any of the respective components is not available in the system the creation of the composite application will fail. So always some manual work is necessary for creating a composite application.

Disadvantageously this manual work requires much skills and experience. Further in case of updates for certain artifacts which have been used for building up the composite applications it is a difficult work to observe and analyze if such new update is suitable for being build in an existing composite application in order to replace an older version thereof. Again the functional scope must be analyzed the interfaces must be observed in order to comply with those being used in the actually existing composite application and potentially a decision has to be taken if or if not to extend the composite application in order to integrate some new function offered by such new update of an artifact as mentioned above.

Disadvantageously the assembly and keeping up to date of such composite applications is to much time consuming.

It is thus the objective of the present invention to provide a method for automatically assisted generation of composite applications which is more flexible and requires less skill and time for building a composite application or for keeping it up to date.

In short words the inventional method discloses two processing parts A first part for implementing a dynamic discovery and deployment of components referenced by a template and a second part for performing an automated assembly of components based on meta data e.g. a component to store documents and a component to handle mail.

The above objective of the invention is achieved by the features stated in enclosed independent claims. Further advantageous arrangements and embodiments of the invention are set forth in the respective subclaims. Reference should now be made to the appended claims.

According to its basic aspect the present invention discloses a method for automatically assisted generation of composite applications preferably implemented in an application server or specifically in a portal server which composite applications are composed of a plurality of instantiable components wherein a composite application infrastructure CAI component handles application instances during runtime and manages connections and data flow between said components of a composite application and wherein a templating application infrastructure TAI component manages templates which contain references to said instantiable components. This method is characterised by an automatic component discovery comprising the steps of 

a dynamically accessing a data source such as e.g. a template catalog an artifact registry or some libraries located locally or remote in a network which data source comprises one or more components being potentially suitable for being used within the composite application b parsing the data source for a predetermined searched component according to a predetermined functionality specification standard as exemplarily given in c ranking found components according to predetermined ranking criteria d defining a list of selected usable components from the ranking e storing at least a subset of the selected components locally preferably at the application server f automatically deploying the composite application using at least one of said selected components.

The step of discovering components may include the access of data sources located local or remote relative to the server which generates the composite application.

Further the process of installing a discovered component into said composite application may be done advantageously in an automated way without major human interference.

Further advantageously an automatic versioning management may be included by enriching the inventional method wherein a component is used for an instantiation of a composite application is automatically monitored for updates thereof and wherein in case a new update is discovered the step is performed of checking if its requirements comply with those of the composite application and if it complies to perform the step of automatically binding the new updated component into the composite application.

In the portal system left part of a new component is implemented An instantiation component . This instantiation component has appropriate interfaces to the portal to the runtime container the deployment component as well as to input output and send receive functionalities in order to communicate across the internet or another network with an artifact registry service which is in turn also new and provided by the present invention.

In the artifact registry service a further discovery component is provided as well as a registry component and a notification component . Further the before mentioned components have appropriate APIs in order to communicate with each other and with a template catalogue as well as with an artifact registry . Further send and receive functionality is provided and not explicitly depicted in order to communicate with either the portal or any independent software vendor ISV depicted in the right hand portion of .

The independent software vendor may be represented for example by a portal or by any other suited data source which includes one or a plurality of artifact which are collected in the artifact registry of the respective service . It should be noted that a plurality of independent software vendors register their respective artifact in this artifact registry such that there is built up a considerable collection of such artifacts. In a preferred embodiment of the present invention the artifacts are ordered by incorporating them into a given taxonomy which is preinstalled at the artifact registry .

In a similar way a template catalogue is provided at the artifact registry service which comprises a collection of templates also preferably ordered by a given taxonomy wherein each template is usable by the inventional method in order to generate a composite application by using one or more of such templates as a base for the structure and function of such composite application.

The discovery component is preferably invoked by the instantiation component as the components are needed for instantiating the composite application and searches artifacts and templates based on meta data supplied with the invocation. A further example illustrating a more detailed description of the discovery component and its cooperation with the registry component and the notification and subscription component is given further below.

The registry component allows Independent Software Vendors to deploy their templates and artifacts into the Artifact Registry Service . This component is responsible to store the templates artifacts and their metadata in the Template Catalog and Artifact Registry .

The notification and subscription component implements some logic which alerts about available artifact updates which can then be provided automatically to the instantiation component of the portal . Alternatively or in combination specific versions of artifacts or composite applications can be selected manually after being offered for instantiation by this component .

With further reference to the template is enhanced by a meta data collection to contain meta data about components instead of directly listing the components that shall be used.

When a template is instantiated the lookup component interprets the component description and searches for suitable components in the local list of components and by using the discovery component .

The independent software vendor is assumed now to upload store and register the templates and artifacts he is offering for purchase and use by others. The storage location in this example is the template catalogue and the artifact registry see .

With further reference to as well as some control flow diagrams A and interaction charts B are discussed which illustrate important steps of the inventional method.

With reference to respectively after invocation in a step the discovery component searches for a template via a dedicated template discovery service. This is done in order to build up a new composite application as it was mentioned further above according to the objective of the present invention. More details are given further below describing according to which preferred aspects such search step is implemented.

Once a template has been found by the search step this template will be downloaded to the portal to the instantiation component thereof in a step . Of course more than only one template can be downloaded in particular in a situation in which several templates are stored in the template catalogue which fulfill basically the same technical functionality. It should be mentioned that preferably also further business meta information such as apprise to use such template may be recorded at the template catalogue. Of course this additional information will be also downloaded to the instantiation component .

At the portal site the instantiation component first stores the downloaded templates in a local template registry as it is known from the template catalogue in .

With further reference to the instantiation of a template and the query of artifacts are described in more detail 

In a first step one of the templates which were downloaded in step or which have been stored in the local template registry is selected for instantiation.

In order to make a good selection a plurality of criteria may be set up and offered to be controlled by an administration user or by a business user which may use a man machine interface which is smart enough to hide technical details and to stress business details which may be understood by such business user the composite application is deemed to cover. Examples for criteria are the following Scope of functionality price quality of service availability of service etc.

In a further step the artifact registry is queried by the instantiation component by using meta data from the selected template. The meta data includes version compatibility and dependency information to determine a matching set of compatible artifacts. Examples for such meta data are given and described in later below. An example is 

The result of step is a set of artifacts which all fulfill more or less well the requirement of the query. The skilled reader will understand that the evaluation of the query result is implemented in an application driven way in order to give more or less freedom to tailor the composite application according to any specific business requirements.

Then in a further step the one or more missing artifacts are downloaded to the instantiation component of the portal . There they are preferably stored locally in the local component registry or alternatively in a separate registry step .

Then all components required to build up a new composite application should be available local at the portal and ready to be accessed by the instantiation component . According to the present invention the composite application is now automatically deployed from the selected components. Similar to the selection of templates also the selection of artifacts may be performed preferably according to any given ranking criteria which are predetermined in any way and adjusted to a respective individual composite application. Similar criteria as mentioned above can be taken also here. So in the end a new composite application has been generated and can be instantiated by the instantiation component . So this new composite application may be used for the real business of a respective enterprise.

In the course of time however some of the components or templates which are used for one or more composite applications are no more up to date because there may be a newer version of such component or artifact offered by its producer.

According to a further preferred feature of the present invention which may be used to enrich the inventional method such update components may be either automatically incorporated into an existing composite application or may at least the automatically offered for manual inclusion into such composite application. In the letter case a business user or a business user accompanied by a programmer may decide on this.

In a first step the independent software vendor updates any given predetermined component which is assumed now to be in use in a certain composite application. Thus as indicated in step such updated component is sent to the artifact registry service and will be stored in the artifact registry . Here a trigger is fired in order to invoke the notification component . The notification component identifies the artifact new version number and optionally a catalogue of new functions which the new update artifact offers to the business user. The notification component further stores in a dedicated mapping list an association between each artifact its version number and each composite application which makes use of such artifact. In order to do that preferably a database is used which stores respective IDs for the composite application and a respective artifact. In this database also a subscription tag is stored which is checked in order to be sure to be obliged or not to notify the composite application about the newly updated artifact. Here it can be assumed that if the subscription tag is set then such obligation exists and a respective notification will be send from component to the instantiation component of portal . In this notification method the necessary IDs are used by the notification method.

Then in a step a business user or a portal administration user can decide whether or not to adopt the new artifact. In case they do adopt the new one the new version of the artifact is downloaded step from the artifact registry to the instantiation component and will be stored in the artifact registry .

In a first step a certain template denoted as template X is instantiated according to prior art in a sequence of steps to .

In a first step of the instantiation the lookup component is invoked from the template. Then in a step the different components which are comprised of the template X are identified. A sample component may for example be the IBM portal WIKI BLOG component version 1.0. Next in a further step all identified components are looked up in the local list of components. This is done according to prior art. Then every component identified in the template which is decided in a decision not being stored in the local component list is looked up in a step in the remote list of components. Further the binary code for each required component is requested and received from this remote list of components and is deployed locally in a step .

Thus in a further step an instance of the composite application is created based on the results and data obtained by the preceding steps. Then the created instance is registered in the context of the portal i.e. in appropriate context storage. In particular the number of created instances their initialization values and other information are registered.

A skilled reader will appreciate that all steps to can be performed fully automatically without human intervention. This is a significant advantage over prior art.

However in a step the meta data stored in the template X are identified and are abstracted according to a predetermined taxonomy. So in step a component is analyzed to be required which provides a certain functionality instead of an exact specification of the component as it was described with reference to . So in this further modification any component which provides BLOG functionality is accepted.

As a result of more search hits the look up component looks up all components that have a pre specified functionality and preferably performs a selection in order to obtain one or more special components which fit best the functionality requirement. It should be remarked that in this context prior art methods to instantiate a composite application fail if the component specified in step does not exist in the local component storage. Here in contrast according to this special embodiment the choice of components is significantly enlarged and the components can be selected according to their scope of functionality instead to be constrained to satisfy the request with the exact component specified by name and version number possibly vendor name etc.

With further reference now to further details are given telling a skilled reader how to manage the selection of artifacts and templates. This includes how to perform a parsing of the data source for a predetermined searched component according to a predetermined functionality specification.

The input and output parameters of components are described preferably via portal property broker WSDL fragments.

The properties of the components are defined via domain specific XML fragments. A domain may be defined via the XML namespace. The properties depend on a respective domain see the samples given in .

According to a mail component having the business functionality of standard business mail uses a http server is compliant to protocols SMTP and POP3 and offers LDAP functions.

Further a calendar component uses a http server uses a protocol iCal and has also LDAP functionality.

Further a document library component uses again a http server stores a minimum document size of 10 arbitrarily defined units and a maximum capacity of 100 units and uses a folder structure of the depth of at least 100.

With respect to identification of appropriate component functionality preferably Xpath queries are used to lookup components with the required meta data. The query service called by the portal can be implemented as a Web service or a REST service.

Of course different syntax can be used as long as a different syntax is pre defined by a respective standard.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers.

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.

The circuit as described above is part of the design for an integrated circuit chip. The chip design is created in a graphical computer programming language and stored in a computer storage medium such as a disk tape physical hard drive or virtual hard drive such as in a storage access network . If the designer does not fabricate chips or the photolithographic masks used to fabricate chips the designer transmits the resulting design by physical means e.g. by providing a copy of the storage medium storing the design or electronically e.g. through the Internet to such entities directly or indirectly. The stored design is then converted into the appropriate format e.g. GDSII for the fabrication of photolithographic masks which typically include multiple copies of the chip design in question that are to be formed on a wafer. The photolithographic masks are utilized to define areas of the wafer and or the layers thereon to be etched or otherwise processed.

