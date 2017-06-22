---

title: Computing correlated aggregates over a data stream
abstract: Described herein are approaches for computing correlated aggregates. An aspect provides for receiving a stream of data elements at a device, each data element having at least one numerical attribute; maintaining in memory plurality of tree structures comprising a plurality of separate nodes for summarizing numerical attributes of the data elements with respect to a predicate value of a correlated aggregation query, said maintaining comprising: creating the plurality of tree structures in which each node implements one of: a probabilistic counter and a sketch, wherein said probabilistic counter and said sketch each act to estimate aggregated data element numerical attributes to form a summary of said numerical attributes; and responsive to a correlated aggregation query specifying said predicate value, using said plurality of tree structures as a summary of said data element numerical attributes to compute a response to said correlated aggregate query.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08868599&OS=08868599&RS=08868599
owner: International Business Machines Corporation
number: 08868599
owner_city: Armonk
owner_country: US
publication_date: 20120828
---
This application is a continuation of U.S. patent application Ser. No. 13 278 469 entitled COMPUTING CORRELATED AGGREGATES OVER A DATA STREAM filed on Oct. 21 2011 which is incorporated by reference in its entirety.

This invention was made with government support under grant numbers CNS0834743 and CNS0831903 awarded by the National Science Foundation. The government has certain rights in the invention.

The subject matter presented herein generally relates to efficiently computing correlated aggregates over a data stream.

Processing a massive data set presented as a large data stream is challenging. The data set may be for example network traffic data or streaming data from external memory. A difficulty encountered is that the data set is too large to store in cache for analysis. Because of the size of the data set processing requires fast update time use of very limited storage and possibly only a single pass over the data.

In computing statistics for certain types of data set analysis a problem is the correlated aggregate query problem. Here unlike in traditional data streams there is a stream of two dimensional data items i y where i is an item identifier and y is a numerical attribute. A correlated aggregate query requires first applying a selection predicate along the y dimension followed by an aggregation along the first dimension. An example of a correlated query is On a stream of IP packets compute the k th frequency moment of all the source IP address fields among packets whose length was more than 100 bytes . Answering such a query may for example allow a network administrator to identify IP addresses using an excessive amount of network bandwidth.

One aspect provides a method for summarizing attributes of data elements of a data set for computing correlated aggregates comprising receiving a stream of data elements at a device each data element having at least one numerical attribute maintaining in memory a plurality of tree structures comprising a plurality of separate nodes for summarizing numerical attributes of the data elements with respect to a predicate value of a correlated aggregation query said maintaining comprising creating the plurality of tree structures in which each node implements one of a probabilistic counter and a sketch wherein said probabilistic counter and said sketch each act to estimate aggregated data element numerical attributes to form a summary of said numerical attributes and responsive to a correlated aggregation query specifying said predicate value using said plurality of tree structures as a summary of said data element numerical attributes to compute a response to said correlated aggregate query.

The foregoing is a summary and thus may contain simplifications generalizations and omissions of detail consequently those skilled in the art will appreciate that the summary is illustrative only and is not intended to be in any way limiting.

For a better understanding of the embodiments together with other and further features and advantages thereof reference is made to the following description taken in conjunction with the accompanying drawings. The scope of the invention will be pointed out in the appended claims.

It will be readily understood that the components of the embodiments as generally described and illustrated in the figures herein may be arranged and designed in a wide variety of different configurations in addition to the described example embodiments. Thus the following more detailed description of the example embodiments as represented in the figures is not intended to limit the scope of the claims but is merely representative of those embodiments.

Reference throughout this specification to embodiment s or the like means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment. Thus appearances of the phrases according to embodiments or an embodiment or the like in various places throughout this specification are not necessarily all referring to the same embodiment.

Furthermore the described features structures or characteristics may be combined in any suitable manner in different embodiments. In the following description numerous specific details are provided to give a thorough understanding of example embodiments. One skilled in the relevant art will recognize however that aspects can be practiced without certain specific details or with other methods components materials et cetera. In other instances well known structures materials or operations are not shown or described in detail to avoid obfuscation.

On a stream of two dimensional data items i y where i is an item identifier and y is a numerical attribute a correlated aggregate query requires applying a selection predicate first along the second dimension y followed by an aggregation along the first dimension. For selection predicates of the form yc where parameter c is provided at query time embodiments provide streaming processing and lower bounds for estimating statistics of the resulting substream of elements that satisfy the predicate.

For example an embodiment can answer the following query On a stream of IP packets compute the k th frequency moment F k 0 1 2 or greater of all the source IP address fields among packets whose length was more than 100 bytes . A process according to an embodiment for F basic count improves previous approaches by roughly a logarithmic factor and is near optimal. An approach provided according to embodiments for k 1 provides the first sub linear space algorithms in this model for these problems. Embodiments also estimate heavy hitters rarity and similarity in this model. The memory requirements are significantly smaller than existing linear storage schemes for large data sets and embodiments simultaneously achieve last per record processing time.

The description now turns to the figures. The illustrated example embodiments will be best understood by reference to the figures. The following description is intended only by way of example and simply illustrates certain example embodiments representative of the invention as claimed.

Referring to consider a data stream data set stream are used interchangeably herein of tuples S x y i 1 . . . n where xis an item identifier and ya numerical attribute. A correlated aggregate query C AGG S specifies two functions a selection predicate along the y dimension. It requires that the selection be applied first on stream S followed by the aggregation. More formally is true

Importantly the selection predicate need only be completely specified at query time and may not be known when the stream is being observed. For example on a stream of IP packets with x denoting the source IP address and y denoting the number of bytes in the packet on an observed packet stream a network administrator may ask the query What is the second frequency moment F of all IP addresses for those packets that are less than 1000 bytes The selection predicate y

A traditional data stream summary provides an accurate answer to an aggregate query such as frequency moments quantities and heavy hitters over the entire data stream. In contrast a summary for correlated aggregate provides accurate answers to a family of queries that can he posed on the stream where different queries in the family specify the same aggregation function but over different subsets of the input stream. These subsets are selected by the predicate along the primary dimension. Correlated aggregates arise naturally in analytics on multi dimensional streaming data and space efficient methods for implementing such aggregates are useful in streaming analytics systems such as in IBM SYSTEM S.

The summaries for correlated aggregates provided by embodiments allow for more flexible interrogation of the data stream than is possible with a traditional stream summary. For example consider a data stream of IP flow records such as those output by network routers equipped with CISCO netflow. Suppose that one is interested in only two attributes per flow record the destination address of the flow and the size number of bytes of the flow. Using a summary for correlated aggregate AGG along with a quantile summary for the y dimension any well known stream quantity summaries may be used it is possible for a network administrator to execute the following sequence queries on the stream 

 1 First the quantile summary can be queried to find the median size of the flow. 2 Next using the summary for correlated aggregates the network administrator can query the aggregate AGG of all those flow records whose flow size was more than the median flow size. 3 If the answer to query 2 was abnormal in the network administrator s opinion and the network administrator needed to find properties of the very high volume flows this may be accomplished by querying for the aggregate of all those flow records whose flow size is in for example the 95 percent quantile or above the 95 percent quantile may be found using the quantile summary .

Thus a summary that allows for such queries can be used for deeper investigation of larger data streams. Important to this is the flexibility that the parameter for the selection predicate can be specified at query time which allows the user to iteratively adapt his or her query based on the results of previous queries. For data intensive analytics systems such as network management systems and sensor data management this can be a very powerful tool.

In this description both processing and lower bounds for summarizing data streams for correlated aggregate queries are provided. Embodiments consider selection predicates of the form y y or y y where yis specified at query time.

For estimating the basic count the x values of the stream elements x y do not matter hence only considered is the stream Y y y . . . y. The y s may not be distinct and do not necessarily arrive in increasing order. The problem is to design a summary that can answer the following query given a parameter y provided at query time how many y s are less than or equal to y In other words estimate COUNT y y Y y

The starting point for a solution is the splittable histogram data structure of prior work. This data structure stores histograms at multiple levels i 0 1 2 . . . such that the error due to using a data structure at level i is proportional to 2 but as i increases the set of possible queries that can be answered by the data structure at level i also become larger. The rough intuition here is that if a data structure is used at a large level a large value of i though the error is large proportional to 2 the answer must also be large hence the relative error is controlled.

It is noted that that the data structures in prior work use many counters that may need to hold very large values. Observe that these counts need not be exact and hence an embodiment uses probabilistic counters which provide approximate counts of large numbers using significantly smaller space than exact counters. The error in the counters and the error in the data structures combine to give the total error in the estimate.

There is a technical difficulty in getting the above idea to work which is that the states of the counters are used to trigger certain actions of the data structures such as the formation of new nodes in the data structure. Replacing these counters with probabilistic counters leads to dealing with random variables and events that are not all independent of each other and this dependency has to be handled carefully. Presented herein are further details of the process for doing this and the analysis.

A probabilistic counter is a data structure for approximate counting that supports two operations increment and query. For positive integer M and 0 let PC M denote a probabilistic counter with base 1 that counts until a maximum estimated value of M. Let Cdenote the state of the counter after n increment operations. Using C it is possible to return an estimate circumflex over n of n. If circumflex over n M the counter cannot be incremented any further and the counter is said to be closed . If circumflex over n 

Theorem 1 Let circumflex over n denote the estimated count returned by the counter PC M after n increments. Then E circumflex over n n and

The above theorem concerns the estimates returned by the probabilistic counter. The number of increments needed for the counter to reach its maximum value need to be analyzed so a slightly different type of guarantee is required.

Lemma 1 For C PC M let I C denote the number of insertions into C that causes it to be closed. Then E I C M 1 and

The data structure consists of histograms S S . . . S where l log 2 U where U is an upper bound on the value of COUNT y for any value of y. Each histogram Sconsists of no more than

Every bucket is responsible for a range of y values which is represented implicitly by the position of the bucket in the tree. The span of a bucket b is the range of timestamps that the bucket b is responsible for. The span of the root of the tree is 0 y . If the span of node v is y y then the span of its left child is y y y 1 2 and the span of its right child is y y 1 2 y . In a given level l the span of all buckets at the same depth in the tree are disjoint but the span of buckets at different depth may overlap with each other. If they do overlap then the span of one of the buckets must be a proper subset of the span of the other overlapping bucket. Each bucket has a probabilistic counter associated with it.

For bucket b let span b denote the span of the bucket. Let left b denote the leftmost endpoint of span b and right b denote the rightmost endpoint of span b . Let PC b to denote the counter associated with the bucket. The process for COUNT is illustrated in .

Proof The space complexity is the space taken to store O l buckets. Each bucket b consists of a probabilistic counter PC M where the value of M is no more than U. The space complexity of the data structure follows from Theorem 1.

For bucket b let A b denote the number of stream items that were inserted into this bucket. Let EST b denote the current estimate of the number of items that were inserted into the bucket. This notation is extended to sets of buckets too. For any set of buckets B all in the same level let

For the leaves after the actual counts A b s have been assigned the random variables EST b s are all independent. Hence 

Lemma 6 The estimate returned for COUNT y by process 3 has a relative error of less than 7 with probability at least 1 4 .

Proof Suppose the process uses level l for its estimate. Let BS denote the set of all nodes b Ssuch that the span of b is a subset of 0 y . The estimator uses the sum of the estimated counts of all nodes in B. Let BBdenote the internal nodes in B and BBdenote the leaves in B. Let CO NT y denote the estimate returned by the process. Let BSdenote the set of all buckets b Ssuch that the span of b intersects 0 y but is not a subset of 0 y . COUcircumflex over N T COUNT 1 

First consider E. Bounding A B each bucket in Bmust span y. There can be no more than log ybuckets in Sthat can span y and each such bucket except for the smallest bucket must be an internal node of S. Let fdenote the leaf bucket in B if it exists note that fmay not exist . Let B denote the internal buckets in B. If fdoes not exist then A f is defined to be 0. f 

Next it is shown that A f is small with high probability. If fdoes not exist then A f 0 so it can be assumed that fexists. In such a case fcannot be a singleton bucket since then its span would have been completely contained within 0 y . Consider I f which is the number of stream items that need to be inserted into fto close the counter. From Lemma 3 Pr Y f 2 2 . Thus with probability at least 1 it must be true that Y f 1 2 3 

This proves that the estimate is within a 7 relative error of COUNT. The other direction is proved similarly by noting the following.

Proof The space complexity and correctness follow from Lemma 2 and Lemma 6 respectively. In prior work it was shown that any data structure for basic counting for a synchronous sliding window with an relative error needs

A general scheme for constructing a summary for correlated aggregation for any aggregation function that satisfies a certain set of properties is described. For any such aggregation function it is described how to reduce the construction of a sketch for correlated aggregation to the construction of a sketch for aggregation over the entire stream. This reduction allows the use of previously known stream summaries for aggregation over streams in constructing summaries for correlated aggregation.

An embodiment employs this scheme to construct small space summaries for estimating correlated frequency moments over a data stream. For k 0 the k th frequency moment of a stream of identifiers each assumed to be an integer from 1 . . . m is defined as F f where fis the number of occurrences of the i th item. The estimation of the frequency moments over a data stream has been the subject of much study however embodiments provide processing for estimating the correlated frequency moments with provable guarantees on the relative error. The memory requirements are optimal up to small factors namely factors that are logarithmic in m and the error probability and factors that are polynomial in the relative error parameter .

The technique for general correlated aggregation described herein builds on prior work for the correlated estimation of the basic count. While the basic data structure used in prior work is an exact counter embodiments rather employ a sketch which can accurately estimate an aggregate on a stream and provide a possibly probabilistic guarantee on the correctness. The error due to the randomized sketches employed by embodiments is analyzed as well as the combination of different sketches. A central new issue is that of dependency between random variables.

Also presented in detail are approaches for the first space efficient processing for correlated aggregates of the number of distinct elements F and other aggregates related to frequency moments such as the F heavy hitters and rarity. A technique for achieving lower amortized update time is provided. For correlated F the update time is log n per stream update.

The case of streams where items can have an associated positive or negative integer weight is described. Allowing negative weights is useful for analyzing the symmetric difference of two data sets since the items in the first data set can be inserted into the stream with positive weights while the items from the second data set can be inserted into the stream with negative weights.

In this model each stream element is a 3 tuple x y z where zspecifies the weight of the item. It is shown that even if z 1 1 for all i then for a general class of functions that includes the frequency moments any summary that can estimate correlated aggregates accurately and that is constructed in a single pass must use memory that is linear in the size of the stream. This is to be contrasted with the estimation of frequency moments over a stream in the non correlated case where it is known how to estimate these aggregates in sublinear space even in the presence of positive and negative weights.

Also described is a model with arbitrary positive and negative weights in which multiple passes over the stream are allowed. This more general model allows the processing to make a small but more than one number of passes over the stream and store a small summary of what is seen. At a later time a query is made and must be answered using only the summary. Such a setting arises if data is collected and stored from previous days for the purpose of creating a summary but is then deleted or archived while only the summary is retained.

In this case a smooth pass space tradeoff is obtained for these problems in that with a logarithmic number of passes there are space efficient algorithms for a large class of correlated aggregates even with negative weights but with fewer passes no such space efficient algorithms can exist.

A closely related problem is that of computing aggregates over a sliding window on an asynchronous stream. In this scenario a stream of v t tuples where v is a data item and t is the timestamp at which it was generated. Due to asynchrony in the transmission medium it is possible that the stream elements do not arrive in the order of the time stamps. In other words it is possible that t

Embodiments provide for the estimation of correlated aggregates for any aggregation function that satisfies a set of properties. Consider an aggregation function that takes as input a multi set of real numbers R and returns a real number R . In the following the term set of real numbers is used to mean a multi set of real numbers . Also union of sets implies a multi set union when the context is clear.

For any set of tuples of real numbers T x y 1 i n and real number y let T c denote the correlated aggregate x x y T y c . For any function satisfying the following properties it is shown herein how a reduction from the problem of space efficient estimation of correlated aggregate T c to the problem of space efficient estimation of in an uncorrected manner on the entire set R.

In the following description the term sketching function denotes a compression of the input set with certain properties. More precisely has a sketching function sk v R if 

Many functions have sketching functions. For instance the second frequency moment Fand the k th frequency moment Fhave sketches due to prior work. In these two examples the sketching function is obtained by taking random linear combinations of the input.

Embodiments require the following conditions from in order to construct a sketch for estimating correlated aggregates. These conditions intuitively correspond to smoothness conditions of the function bounding how much can change when new elements are inserted or deleted from the input multi set. Informally the less the function value is sensitive to small changes the easier it is to apply to estimating correlated aggregates.

For any function with a sketch sk with the above properties it is shown herein how to construct a sketch sk T for estimating the correlated aggregate T c with the following properties 

Referring to let denote an upper bound on the value of over all input streams considered. The process uses a set of levels l 0 1 2 . . . l where lis such that 2 for input stream T and real number c. From Property 1 it follows that lis logarithmic in the stream size.

Without loss of generality assume that yis of the form 2 1 for some integer . The dyadic intervals within 0 y are defined inductively as follows 

Within each level l from 0 to l there is a bucket for each dyadic interval within 0 y . Thus there are 2y 1 buckets in a single level. Each bucket b is a triple k b l b r b where l b r b is a dyadic interval that corresponds to a range of y values that this bucket is responsible for and k b is defined below.

When a stream element x y arrives it is inserted into each level l 0 . . . l. Within level l it is inserted into exactly one bucket as described in Process 5. For a bucket b in level l let S b denote the multi set of stream items that were inserted into b. Then k b sk v S b is a sketch of S b .

Within each level no more than of the 2y 1 buckets are actually stored. In the process Sdenotes the buckets that are stored in level l. The level Sis a special level that just consists of singletons. Among the buckets that are not stored there are two types of buckets those that were discarded in Process 5 see the Check for overflow comment in Process 5 and those that were never used by the process. The above three types of buckets are termed stored discarded and empty respectively. Note that S b is defined for each of these three types of buckets if b is an empty bucket then S b is defined as the null set .

The buckets in Sare organized into a tree induced by the relation between the dyadic intervals that these buckets correspond to.

The initialization for the process for a general function is described in Process 4 illustrated in . The update and query processing are described in Processes 5 and 6 illustrated in and respectively.

Proof There are no more than 2 log flevels and in each level l Sstores no more than buckets. Each bucket b contains sk v S b . The space complexity is 2 log times the space complexity of sketch sk. Here it is assumed that the space taken by sk is larger than the space required to store l b and r b .

Let S denote the stream of tuples observed up to a given point. Suppose the required correlated aggregate is S c . Let A be the set .

For level l 0 l l Band Bare defined as follows. Let Bdenote the set of buckets b in level l such that span b 0 c . Let Bdenote the set of buckets b in level l such that span b 0 c but span b has a non empty intersection with 0 c .

Note that for each level l Band Bare uniquely determined once the query S c is fixed. These do not depend on the actions of the process. This is an important property used which allows the choice of which buckets to use during estimation to be independent of the randomness in the data structures. Further note that only a subset of Band Bis actually stored in S.

Consider any level l 0 l l. For bucket b recall that S b denotes the set of stream items inserted into the bucket until the time of the query. For bucket b S let f b denote f S b . Let estdenote the estimate of f b obtained using the sketch k b . If S b then f b 0 and est b 0. Thus note that f b and est b are defined no matter whether b is a stored discarded or an empty bucket. Further for a set of buckets B in the same level let S B S b and let f B f S B . Let est B be the estimate for f B obtained through the composition of all sketches in k b by property V sketches can be composed with each other .

Definition 3 Bucket b is defined to be good if 1 v f b est b 1 v f b . Otherwise b is defined to be bad .

Proof For each bucket b note that est b is a v estimator for f b . Thus the probability that b is bad is no more than . Noting that there are less than 2ybuckets in each level and l 1 levels in total and applying a union bound yields 

Proof Every bucket b Bmust satisfy span b 0 c . Thus every element inserted into Bmust belong in A. Hence S B A. Each element in A has been inserted into some bucket in level l it is possible that some of these buckets have been discarded . By the definitions of B an element in A cannot be inserted into any bucket outside of B B. Thus AS B B .

Proof Consider l. Y c if event G occurs. Observe that Yis initialized to in Process 4. Its value can only change if the root b of Scloses. For this to happen there must be est k b 2. But 2 which means that est k b does not provide a 1 approximation. This contradicts the occurrence of event G. Hence Y c and so Process 6 does not output FAIL in step 1.

Proof First note that there can be no singleton buckets in Bby definition of Bfor a level l. Thus for each bucket b B est b 2. Because G is true for every bucket b B b is good so that

Next note that there are no more than log ybuckets in B since there can be only one dyadic interval of a given size that intersects 0 c but is not completely contained within 0 c .

Proof Since the process used level l for answering the query it must be the case that there are buckets in Sthat had an intersection with 0 c but were discarded from the data structure. It follows that there are at most log ybuckets b Ssuch that span b 0 c . For the remaining buckets b S it must be true that span b 0 c . If Sis viewed as a binary tree with nodes according to the ordering between the different dyadic intervals then Smust have 1 2 internal nodes. Suppose I denoted the set of buckets in b Ssuch that b is an internal node and span b 0 c . Thus I 1 2 log y. Since G is true for any bucket

Theorem 4 When presented with a query for f S c let est denote the estimate returned by the process. Then with probability at least 1 1 f 1 f .

Proof If l 0 then all elements x y S such that y c are stored in S. In this case the theorem follows by the definition of event G and Lemma 1. Otherwise est est B and f S c f A . First note that in level l none of the buckets in Bhave been discarded. Thus each bucket b Bis either empty or is stored. Thus it is possible to execute line 7 in Process 6 correctly to construct a sketch of S B . From property b of sketching functions yields a sketch sk v S B .

This proves that conditioned on G and the estimate returned is never too small. For the other direction note that conditioned on being true 1 v 1 v 1 where B A has been used and v

The general technique presented herein can yield a data structure for the correlated estimation of the frequency moments F k 2.

Proof Fact 1 j dimensional vectors a and b implies that a b a b . Setting B 1 1 . . . 1 it follows that a . . . a j a . . . a . Hence it follows that

Proof Suppose A and B have support on 1 2 . . . n. Let a and b be the characteristic vectors of sets A and B respectively. Using Fact 1 yields 

Proof It is know that for any two sets A and B F A B 2 F A F B . 2 which leads to 2 9 1 3 . Thus 3 . Applying Lemma 7 yields 1 . Thus 1 1 .

Proof From Lemma 12 c j j. From Lemma 8 c 9k . Using these in Theorem 3 yields c log y log y and c 2 18k . Using the sketches for Fand F k 2 from prior work the above result is obtained.

The space can be improved to rpoly log n where r is the number of distinct x values in the stream. In the worst case though r could be n . The dependence is made more explicit for the case of F.

Proof The space taken by a sketch for an estimator for Fon a stream is O log 1 log 1 bits. From the proof of Theorem 5 c j j and c 18 .

To get O log log 1 log y amortized processing time observe that there are O log data structures S each containing O logy buckets each holding a sketch of O log log 1 log y bits. A batch of O logy updates is processed at once. The batch is first sorted in order of non decreasing y coordinate. This can be done in O logy log 1 log log y time. Then the following processing is done for each S. A pre order traversal of the buckets in Sis conducted and the appropriate buckets are updated. Importantly each bucket maintains an update efficient AMS sketch shown in prior work which can be updated in time O log 1 log y . Since the updates are sorted in increasing y value and the list is represented as a pre order traversal the total time to update Sis O logy log 1 log y . The time to update all the Sis O log times this. So the amortized time is O log log 1 log y .

While many aggregation functions satisfy the properties described above some important ones do not. However in many important remaining cases these aggregation functions are related to aggregation functions that do satisfy these properties and the mere fact that they are related in the appropriate way enables efficient estimation of the corresponding correlated aggregate.

The correlated F heavy hitters can be computed as well as the rarity defined below by relating these quantities to Fand F respectively.

In the rarity problem the problem is to estimate the fraction of distinct items that occur exactly once in the multi set. The ideas for estimating rarity are similar where the same data structures Sare maintained for estimating the correlated aggregate F but in each bucket maintain data structures for estimating the rarity of items inserted into that bucket.

The number of distinct elements in a stream also known as the zenith frequency moment F is a fundamental and widely studied statistic of the stream. Here the correlated estimation of the number of distinct elements in a stream is described. Consider a stream of x y tuples where x 1 . . . m and y 1 y. The process employed by an embodiment is an adaptation of the process for estimating the number of distinct elements within a sliding window of a data stream due to prior work. Similar to prior work the process for correlated estimation of Fis based on distinct sampling or sampling based on the hash values of the item identifiers. Multiple samples S S . . . S are maintained where k log m. Suppose that for simplicity there is a hash function h that maps elements in 1 . . . m to the real interval 0 1 . This assumption of needing such a powerful hash function can be removed as shown in prior work.

The process of prior work proceeds as follows. Stream items are placed in these samples Sin the following manner. A Each item x y is placed in S. B For i 0 an item x y is placed in level i if

Since each level has a limited space budget say a way to discard elements from each level is needed. The process according to an embodiment differs from prior work in the following aspect of how to discard elements from each level. For correlated aggregates maintained in Sare only those items x y that 1 have an x value that is sampled into S and 2 have the smallest values of y among all the elements sampled into S. In other words it is a priority queue using the y values as the weights whereas in prior work each level was a simple FIFO first in first out queue.

It can be shown that the above scheme of retaining those elements with a smaller value of y when combined with the sampling scheme in prior work yields an estimator for the correlated distinct counts.

An example process for correlated Festimation was implemented in Python. The following four data sets were used for example evaluations. 1 Packet traces of Ethernet traffic on a LAN and a WAN. The relevant data here is the number of bytes in the packet and the timestamp on the packet in milliseconds . This data set is referred to as the Ethernet data set. This data set has 2 million packets and was constructed by taking two packet traces and combining them by interleaving. 2 The Uniform data set which is a sequence of tuples x y where x is generated uniformly at random from the set 0 . . . 10000 and y is generated uniformly at random from the set 0 . . . 2 1. This maximum size of this data set is 10. 3 The Zipfian data set with 1. Here the x values are generated according to the Zipfian distribution with 1 from the domain 0 . . . 10000 and the y values are generated uniformly at random from the set 0 . . . 2 1. The maximum size of this dataset is 10. 4 The Zipfian data set as described above with set to 2.

For the sketch for F the implementation used a variant of a process developed in prior work. An observation was that for all cases tested the relative error of the process was almost always within the desired approximation error for 

The space consumption of the process was studied. The space depends on a number of factors including the values of and . The space also depends on since determines the maximum size of the data structure at each level. But the most obvious dependence is on and this dependence is explored further.

In the space taken for the summary for Fis plotted as a function of . This is illustrated for all the data sets described above with each dataset of size 2 million tuples. It is noted that the space taken by the sketch increases rapidly with decreasing and the rate of the growth is similar for all four datasets. For smaller values of 0.1 the summary data structure took even more space than the input stream itself. This is not surprising since the space increases as the fourth power of

It can be observed that the space taken for the Ethernet dataset is greater than the space for the Uniform and Zipfian datasets. The reason for this is that the range of the y values in the Ethernet dataset was much larger 0 to 3200000 than in the Uniform and the Zipfian datasets where the y values ranged from 0 to 8191. The larger range of y values meant that the number of nodes at each level is larger. In addition a larger value of yalso leads to a larger value of for the Ethernet dataset than for the other datasets and hence also to a larger number of levels of data structures. However note that the rate of growth of the space with respect to remains similar for all data sets. For smaller values of 0.15 the summary data structure often took even more space than the input stream itself. This is not surprising since the space increases as the fourth power of

Example results are illustrated in for 0.15 for 0.2 and for 0.25 . In all cases as predicted by theory the space taken by the sketch does not change much and increases only slightly as the stream size increases. This shows that the space savings of the process is much larger with streams that are larger in size.

The time required for processing the stream of 2 million elements was nearly the same about 5 minutes for the Uniform Zipfian as well as Ethernet datasets. The processing rate can be improved by using the C C language and by using a more optimized implementation.

These example results illustrate that a reasonable processing rate can be achieved for the data structure for F and that correlated query processing is indeed practical and provides significant space savings especially for large data streams of the order of 10 million tuples or larger .

An example of the process for Fin Python and four data sets as described in the case of F was also implemented. The only difference was that in the Uniform and Zipfian datasets the range of x values was much larger 0 . . . 1000000 than in the case of F where the range of x values was 0 . . . 10000. The reason for this change is that there are much simpler approaches for correlated Festimation when the domain size is small simply maintain the list of all distinct elements seen so far along the x dimension along with the smallest value associated with it in the y dimension. Note that such a simplification is not easily possible for the case of F.

The variation of the sketch size with is shown in . Note that while the sketch size decreases with increasing the rate of decrease was not as fast as in the case of F. Further note that the sketch size for comparable values of was much smaller than the sketch for correlated F. Another point is that the space taken by the sketch for the Ethernet dataset was significantly smaller than the sketch for the other datasets. This is due to the fact that the range of x values in the Ethernet dataset was much smaller 0 . . . 2000 than for the other datasets 0 . . . 1000000 . The number of levels in the data structure is proportional to the logarithm of the number of possible values along the x dimension. Note that as explained above the process of choice for correlated Festimation for the Ethernet type datasets where the x range is small will be different as explained herein. Thus the process is particularly useful for datasets where the x range is much larger.

The size of the sketch as a function of the stream size is shown in for 1. It can be seen that the sketch size hardly changed with the stream size. Note however that for much smaller streams the sketch will be smaller since some of the data structures at different levels have not reached their maximum size yet. The results for other values of are similar and are not shown here.

Accordingly embodiments provide for computing correlated aggregates over a data stream. Referring to it will be readily understood that embodiments may be implemented using any of a wide variety of devices or combinations of devices. An example device that may be used in implementing embodiments includes a computing device in the form of a computer . In this regard the computer may execute program instructions configured to compute correlated aggregates over a data stream and perform other functionality of the embodiments as described herein.

Components of computer may include but are not limited to at least one processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit s . The computer may include or have access to a variety of computer readable media. The system memory may include computer readable storage media in the form of volatile and or nonvolatile memory such as read only memory ROM and or random access memory RAM . By way of example and not limitation system memory may also include an operating system application programs other program modules and program data.

A user can interface with for example enter commands and information the computer through input devices . A monitor or other type of device can also be connected to the system bus via an interface such as an output interface . In addition to a monitor computers may also include other peripheral output devices. The computer may operate in a networked or distributed environment using logical connections network interface to other remote computers or databases remote device s . The logical connections may include a network such local area network LAN or a wide area network WAN but may also include other networks buses.

As will be appreciated by one skilled in the art aspects may be embodied as a system method or computer program product. Accordingly aspects of the present invention may take the form of an entirely hardware embodiment an entirely software embodiment including firmware resident software micro code et cetera or an embodiment combining software and hardware aspects that may all generally be referred to herein as a circuit module or system. Furthermore aspects of the present invention may take the form of a computer program product embodied in at least one computer readable medium s having computer readable program code embodied thereon.

Any combination of at least one computer readable medium s may be utilized. A computer readable storage medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus or device or any suitable combination of the foregoing. More specific examples a non exhaustive list of the computer readable storage medium would include the following an electrical connection having at least one wire a portable computer diskette a hard disk a random access memory RAM a read only memory ROM an erasable programmable read only memory EPROM or Flash memory an optical fiber a portable compact disc read only memory CD ROM an optical storage device a magnetic storage device or any suitable combination of the foregoing. In the context of this document a computer readable storage medium may be any tangible or non signal medium that can contain or store a program for use by or in connection with an instruction execution system apparatus or device.

Program code embodied on a computer readable medium may be transmitted using any appropriate medium including but not limited to wireless wireline optical fiber cable RF etc. or any suitable combination of the foregoing.

Computer program code for carrying out operations for embodiments may be written in any combination of at least one programming language including an object oriented programming language such as Java Smalltalk C or the like and conventional procedural programming languages such as the C programming language or similar programming languages. The program code may execute entirely on the user s computer partly on the user s computer as a stand alone software package partly on the user s computer and partly on a remote computer or entirely on the remote computer or server. In the latter scenario the remote computer may be connected to the user s computer through any type of network including a local area network LAN or a wide area network WAN or the connection may be made to an external computer for example through the Internet using an Internet Service Provider .

Embodiments are described with reference to figures of methods apparatus systems and computer program products according to embodiments. It will be understood that portions of the figures can be implemented by computer program instructions. These computer program instructions may be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified.

These computer program instructions may also be stored in a computer readable medium that can direct a computer other programmable data processing apparatus or other devices to function in a particular manner such that the instructions stored in the computer readable medium produce an article of manufacture including instructions which implement the function act specified. The computer program instructions may also be loaded onto a computer other programmable data processing apparatus or other devices to cause a series of operational steps to be performed on the computer other programmable apparatus or other devices to produce a computer implemented process such that the instructions which execute on the computer or other programmable apparatus provide processes for implementing the functions acts specified.

This disclosure has been presented for purposes of illustration and description but is not intended to be exhaustive or limiting. Many modifications and variations will be apparent to those of ordinary skill in the art. The example embodiments were chosen and described in order to explain principles and practical application and to enable others of ordinary skill in the art to understand the disclosure for various embodiments with various modifications as are suited to the particular use contemplated.

Although illustrated example embodiments have been described herein with reference to the accompanying drawings it is to be understood that embodiments are not limited to those precise example embodiments and that various other changes and modifications may be affected therein by one skilled in the art without departing from the scope or spirit of the disclosure.

