---

title: System and method for supporting named operations in a distributed data grid
abstract: A system and method can support one or more named operations in a distributed data grid. The distributed data grid includes one or more cluster nodes that can provide the one or more named operations associated with one or more resources in the distributed data grid. The distributed data grid can publish the one or more named operations to a client. Furthermore, the distributed data grid can perform the one or more named operations in the distributed data grid upon receiving a request from a client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08930409&OS=08930409&RS=08930409
owner: Oracle International Corporation
number: 08930409
owner_city: Redwood Shores
owner_country: US
publication_date: 20121107
---
This application claims priority on U.S. Provisional Patent Application No. 61 714 100 entitled SYSTEM AND METHOD FOR SUPPORTING A DISTRIBUTED DATA GRID IN A MIDDLEWARE ENVIRONMENT by inventors Robert H. Lee Gene Gleyzer Charlie Helin Mark Falco Ballav Bihani and Jason Howes filed Oct. 15 2012 which application is herein incorporated by reference.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention is generally related to computer systems and is particularly related to a distributed data grid.

Modern computing systems particularly those employed by larger organizations and enterprises continue to increase in size and complexity. Particularly in areas such as Internet applications there is an expectation that millions of users should be able to simultaneously access that application which effectively leads to an exponential increase in the amount of content generated and consumed by users and transactions involving that content. Such activity also results in a corresponding increase in the number of transaction calls to databases and metadata stores which have a limited capacity to accommodate that demand.

Described herein is a system and method that can support one or more named operations in a distributed data grid. The distributed data grid includes one or more cluster nodes that can provide the one or more named operations associated with one or more resources in the distributed data grid. The distributed data grid can publish the one or more named operations to a client. Furthermore the distributed data grid can perform the one or more named operations in the distributed data grid upon receiving a request from a client.

Described herein is a system and method that can support one or more named operations in a distributed data grid.

In accordance with an embodiment as referred to herein a distributed data grid data grid cluster or data grid is a system comprising a plurality of computer servers which work together to manage information and related operations such as computations within a distributed or clustered environment. The data grid cluster can be used to manage application objects and data that are shared across the servers. Preferably a data grid cluster should have low response time high throughput predictable scalability continuous availability and information reliability. As a result of these capabilities data grid clusters are well suited for use in computational intensive stateful middle tier applications. Some examples of data grid clusters e.g. the Oracle Coherence data grid cluster can store the information in memory to achieve higher performance and can employ redundancy in keeping copies of that information synchronized across multiple servers thus ensuring resiliency of the system and the availability of the data in the event of server failure. For example Coherence provides replicated and distributed partitioned data management and caching services on top of a reliable highly scalable peer to peer clustering protocol.

An in memory data grid can provide the data storage and management capabilities by distributing data over a number of servers working together. The data grid can be middleware that runs in the same tier as an application server or within an application server. It can provide management and processing of data and can also push the processing to where the data is located in the grid. In addition the in memory data grid can eliminate single points of failure by automatically and transparently failing over and redistributing its clustered data management services when a server becomes inoperative or is disconnected from the network. When a new server is added or when a failed server is restarted it can automatically join the cluster and services can be failed back over to it transparently redistributing the cluster load. The data grid can also include network level fault tolerance features and transparent soft re start capability.

In accordance with an embodiment the functionality of a data grid cluster is based on using different cluster services. The cluster services can include root cluster services partitioned cache services and proxy services. Within the data grid cluster each cluster node can participate in a number of cluster services both in terms of providing and consuming the cluster services. Each cluster service has a service name that uniquely identifies the service within the data grid cluster and a service type which defines what the cluster service can do. Other than the root cluster service running on each cluster node in the data grid cluster there may be multiple named instances of each service type. The services can be either configured by the user or provided by the data grid cluster as a default set of services.

In accordance with an embodiment of the invention different named operations can be supported in order to improve performance and ensure security in the distributed data grid. Such named operations can be performed e.g. using named queries named entry aggregator and named entry processors.

A resource A B in the distributed data grid can be configured for a client in a client server environment to perform one or more data grid operations. These data grid operations can include one or more named operations e.g. named operations A C . For example resource A supports a named operation A while resource B supports a named operation B and a named operation C .

Furthermore a configuration file e.g. a cache configuration file in XML format can be used to define each resource A B in the distributed data grid . The configuration file can include definitions of the named operations A C for the different resources A B in the distributed data grid and each named operation A C can be configured with a unique name.

The distributed data grid can publish the one or more named operations A C to the client e.g. using Web Application Description Language WADL and allows the client to request the performance of the available named operations e.g. by name.

Additionally the client can access the distributed data grid via a proxy service . The proxy service can trigger the requested named operations e.g. named operation A on resource A or named operation B on resource B on behalf of the client after receiving a request from the client . Thus the proxy service can address security concerns and help isolate the distributed data grid from potentially untrusted clients.

The distributed data grid can provide a response to the client after performing the named operations. For example when the request from the client is a Hypertext Transfer Protocol HTTP request the distributed data grid can provide a HTTP response back to the client .

In accordance with an embodiment of the invention the client can be a REpresentational State Transfer REST client that supports accessing a distributed data grid via a REST API. The REST API can include support for performing GET PUT and DELETE operations on a single object in a resource e.g. a cache for a REST client. On the other hand the distributed data grid can provide a REST service that implements the REST API in order to support the REST clients.

Furthermore the REST services in the distributed data grid such as the Coherence REST services may require metadata about the cache that they expose. The metadata can include the key and value types for each cache entry in addition to key converters and value marshallers. The distributed data grid can use built in converters and marshallers with both XML and JSON supported based on the associated key and value types.

For example in Coherence a user can edit the coherence rest config.xml file to define the key and value types for a cache entry. The user can include the and the elements within the element respectively. The following example defines a string key class and a value class for a Person user type 

In Coherence the named query is a query expression that can be configured for a resource in the coherence rest config.xml file. The query expression can be specified as a Coherence Query Language CohQL expression e.g. in the predicate part of CohQL. This expression can be configured in an XML file e.g. all special characters such as and must be escaped using the corresponding entity .

A user can add any number of elements within a element in order to specify named queries. Each of the elements can contain a query expression and name binding. The following example defines a named query for a cache 

The following is an exemplary syntax for a named query . The named queries can include context values as they may be required.

For example a user can enter the name of the query within the REST URL in order to use a named query . The following example uses the named query minors that is defined in the above example.

The parameters can provide flexibility by allowing context values to be replaced in the query expression. The following example uses the name parameter that is defined in the name query query expression above to only query entries whose name property is Mark.

Additionally the parameter names can be prefixed by a colon character paramName in the query parameter definition. A user can specify type hints as part of a query parameter definition paramName int in the case when parameter bindings do not have access to type information.

In accordance with an embodiment of the invention the distributed data grid allows a client to use direct queries in addition to the named queries. In Coherence direct queries are query expressions that can be submitted as the value of the parameter q in a REST URL. The query expression can be specified as a URL encoded CohQL expression the predicate part of CohQL . Direct queries which may be disabled by default as a security measure can be enabled by adding a element for each resource to be queried and setting the enabled attribute to true in the coherence rest config.xml file.

Furthermore the distributed data grid can use a query engine to execute queries for both direct and named queries. This query engine can be either a default query engine or a custom query engine. In Coherence a default query engine can execute queries that are expressed using a CohQL syntax the predicate part of CohQL . Additionally a custom query engine can be used to perform the named query operation on the distributed data grid .

The custom query engine allows the use of different query expression syntaxes or the ability to execute queries against data source other than Coherence for example to query a database for entries that are not present in a cache . Custom query engines can implement a query interface such as the com.tangosol.coherence.rest.query.QueryEngine and com.tangosol.coherence.rest.query.Query interfaces In Coherence. Additionally custom implementations can also extend the com.tangosol.coherence.rest.query.AbstractQueryEngine base class which provides convenient methods for parsing query expression and handling parameter bindings. The base class supports parameter replacement at execution time and type hints that can be submitted as part of the query parameter value. Both parameter names and type hints follow the CohQL specification and can be used for other query engine implementations.

Custom query engines can be enabled in the coherence rest config.xml file. The following example defines a custom query engine.

As shown in the above a user can register the custom query engine implementation by adding an element within the element in the coherence rest config.xml file to enable a custom query engine . The element can include a name for the query engine and the fully qualified name of the implementation class.

Furthermore a user can use DEFAULT as the registered name to make a query engine the default custom query engine. Additionally a user can add the engine attribute within a element or a element that refers to the custom query engine s registered name in order to explicitly specify a custom query engine for a named query or a direct query.

A named entry aggregator can aggregate all entries in the cache query results e.g. specified as a URL encoded CohQL expression or specified entries. For example Coherence REST can provide a set of pre defined entry aggregators and also can allow custom entry aggregators to be created as required.

If the entry aggregation succeeds a OK status code can be returned with the aggregation result as an entity.

In accordance with an embodiment of the invention the distributed data grid can provide a simple strategy for entry aggregator creation e.g. based on entry aggregator related URL segments. Coherence REST can resolve any registered either built in or user registered entry aggregator with a constructor that accepts a single parameter of type com.tangosol.util.ValueExtractor e.g. LongMax and DoubleMax . If an entry aggregator call within a URL does not contain any parameters the entry aggregator can be created using com.tangosol.util.extractor.IdentityExtractor. If an entry aggregator segment within the URL does not contain any parameters nor a constructor accepting a single ValueExtractor exists Coherence REST can instantiate the entry aggregator using a default constructor which is the desired behavior for some built in aggregators such as count .

Furthermore custom entry aggregator types can be defined by specifying a name to be used in the REST URL and a class implementing a special interface e.g. either the com.tangosol.util.InvocableMap. EntryAggregator interface or the com.tangosol.coherence.rest.util.aggregator.AggregatorFactoryinterface.

Here an EntryAggregator implementation can be used for simple scenarios when entry aggregation is either performed on single property or on a cache value itself. An AggregatorFactory interface can be used when a more complex creation strategy is required. The implementation can resolve the URL segment containing entry aggregator parameters and use the parameters to create the appropriate entry aggregator.

The custom entry aggregators can be configured in the coherence rest config.xml file within the elements.

The following example configures both a Custom EntryAggregator implementation and a Custom AggregatorFactory implementation 

A named entry processor can process all entries in the cache query results or specified entries. For example Coherence REST includes a set of pre defined entry processors and custom entry processors can be created as required.

In order to define an entry processor a user can specify the name of the entry processor class directly in the configuration in a fashion similar to defining entry aggregators. Additionally the entry processor definition can be based on a factory approach.

For example a ProcessorFactory interface can be used to handle an input string from a URL section and instantiate the processor instance since the entry processors can have more diverse creation patterns than the entry aggregators . For example Coherence REST can provide two such factories for NumberIncrementor and NumberMultiplier each of which can be an implementation of a special interface e.g. the com.tangosol.coherence.restutil.processor.ProcessorFactory interface. Additionally custom entry processors can be defined by specifying a name to be used in a REST URL and a class that implements the com.tangosol.coherence.rest.util.processor.ProcessorFactory interface.

The custom entry processors can be configured in the coherence rest config.xml file within the elements. The following example configures a custom ProcesorFactory implementation 

The present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

In some embodiments the present invention includes a computer program product which is a storage medium or computer readable medium media having instructions stored thereon in which can be used to program a computer to perform any of the processes of the present invention. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many modifications and variations will be apparent to the practitioner skilled in the art. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

