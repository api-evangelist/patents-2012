---

title: System and method for simplified representation of geographic addresses
abstract: Computerized methods and system of shortening representations of geographical coordinates (Latitude, Longitude) by replacing the leading significant latitude and longitude digits in a given locality with an optional and often user friendly context hint. The locality context can be indicated either explicitly by a human factors appropriate name, or implicitly by the center of a map or current location of the client computerized device. The invention also discloses a reverse method to recover these eliminated digits by using the approximate center of locality and proximity to provide the missing context information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08612147&OS=08612147&RS=08612147
owner: 
number: 08612147
owner_city: 
owner_country: 
publication_date: 20120706
---
This application claims the priority benefit of U.S. provisional application 61 505 527 entitled Methods and system of local address based on removal of leading significant digits from global coordinates inventor Anup Som filed Jul. 7 2011 the contents of which are incorporated herein by reference.

This invention is in the field of computerized location identifiers digital and non digital maps mapping and navigation applications.

In developed countries such as the US most geographic addresses at least in settled areas have traditionally been reported by standard postal addresses such as street addresses. In addition to street addresses alternative mapping schemes such as city defined local map grid systems have also been used. These latter schemes tend to be both non standardized and either proprietary or poorly publicized which tends to limit their use.

In developing countries such as India where geographic address methods e.g. postal addresses are not standardized the process of locating specific geographic addresses is often even more complex and difficult.

In recent years the Global Positioning System GPS of GPS satellites and receivers has simplified the task of determining precise latitude and longitude of geographic locations of interest. Additionally GPS equipped mobile computerized devices such as smartphones tablet computers and the like have also proliferated along with wireless communications methods. As a result direct reporting of latitude and longitude coordinates has now become a viable alternative to reporting geographic addresses.

Although latitude and longitude can be unambiguously expressed using such methods to find local street addresses can be inconvenient and is not at all user friendly . Particularly when mobile computerized devices are used users often find the process of entering in lengthy street addresses and or long latitude and longitude coordinates to be both complex and error prone. This problem tends to severely hinder the usability of prior art computerized mapping and GPS systems.

Prior art in this field includes Natural Area Code or NAC www.nacgeo.com which employs base 30 alpha numeric encoding of latitude and longitude to generate global addresses which are shorter than their decimal degree equivalents for equivalent precision. NAC is similar to Beatty U.S. Pat. No. 7 302 343 assigned to Microsoft Corporation who taught a method of compact text encoding of latitude and longitude coordinates.

Other work includes the work of Ueda U.S. Pat. No. 7 903 005 who taught a method of transforming geographic coordinates.

Prior art also includes www.glocode.com which uses an encoding scheme overridden with customized prefixes in certain metro areas.

All these methods suffer from human factors usability issues however which render their widespread use at least for geographic coordinate problems that require human input rather problematic. Thus improved methods for dealing with geographic coordinate information that are better optimized from a human factors standpoint are needed.

The general process of determining geographic coordinates e.g. latitude and longitude from other data such as street addresses postal codes and the like is called geocoding. The reverse process finding street addresses and the like from geographic coordinates is called reverse geocoding. Geocoding software designed to implement either geocoding or reverse geocoding methods on various types of microprocessor equipped computerized devices is often referred to as a geocoder .

The invention s methods and coordinate output results will often be described in the alternative herein as Glocal methods and coordinates. The term Glocal is a bit of a play on the words Global and Local and is occasionally used because it helps to express a purpose of the invention which is to generate Local addresses based on Global coordinates.

The invention s methods are based in part on the removal of the leading significant digits and sign from geo coordinate latitude and longitude information and replacing this data with a context reference here often designated as simply context or context hint .

The invention s implementation of context is in turn primarily based on a reference location. This reference location can be either implicit e.g. a center or focus of an interactive digital map or the user s current location or it can be explicit. Typically explicit context data would be a text based location hint that is easily searchable by conventional means. Examples of explicit context data include city names e.g. San Francisco or Delhi Airport codes e.g. SFO DEL and the like. In some embodiments optional custom context can also be selected from a database repository of for example non rectangular asymmetric polygons.

Recovering the removed leading significant latitude and longitude digits and sign To interpret the invention s Glocal coordinates the removed digits and sign can be recovered from the context information context hint by using either a nearest to reference location method often the default method or alternatively a custom asymmetric proximity method.

By using the invention s context methods the local address data can be made of minimal length because it will generally be stripped of unnecessary i.e. redundant information. To further improve robustness and usability the context definition method can be flexible and generally multiple alternative contexts can be used without losing accuracy.

In some embodiments the invention may make use of latitude and longitude coordinates in decimal degrees format and may additionally make use of the World Geodetic System standards such as the WGS 84 standard to allow for compatibility with various legacy GPS based systems including major online maps.

In some embodiments the lower significant digits portion of the location data will often have a latitude and longitude granularity in the 0.1 to 4 range often around 1 . The 1 range is useful and will often be used as a specific example in this disclosure because it covers an area of approximately 100 100 kilometers at a latitude of approximately 20 40 degrees north or south and will often report location to a precision of about 0.0001 e.g. approximately 10 meters which is generally acceptable for navigation purposes. Other granularity values such as 3 are also useful however. 3 granularity for example covers an approximate area of about 300 300 kilometers which is large enough for most metropolitan areas of the world while still giving reasonable accuracy.

In some embodiments base 30 encoding may be used to further reduce the number of characters needed to represent the same decimal value.

Thus in some embodiments the invention may be a computerized system and method of generating an encoded version of at least the lower significant digits of a geographic addresses latitude and longitude values. Here the method will generally operate by obtaining e.g. often entering into a computerized device a geographic address determining the latitude and longitude of the geographic address and determining or obtaining a granularity value. The method will then further use a computerized device e.g. comprising at least one processor memory and software to use the granularity value to truncate the higher significant digits of the latitude and longitude of the geographic address producing lower significant digits of the latitude and longitude of the geographic address. The method will then encode the lower significant digits of the latitude and longitude of the geographic address according to various techniques to be discussed.

The inventions system and method may optionally also further provide a context hint by searching a geo search database on an external server or a context repository for a human recognizable place location with a latitude and longitude with higher significant digits that correspond to the higher significant digits of the truncated higher significant digits of the latitude and longitude of the geographic address and outputting the human recognizable place location as a context hint.

Additionally in some embodiments the invention may further be a computerized system or method of determining the complete latitude and longitude values of a geographic address based on input data pertaining to the addresses lower significant digit latitude and longitude values and at least one context hint pertaining to the addresses higher significant digit latitude and longitude values. This method will generally comprise obtaining an encoded version of the addresses lower significant digit latitude and longitude values and also obtaining or determining a latitude and longitude granularity value. The method will additionally comprise obtaining at least one context hint that is related to the higher significant digit latitude and longitude values of the address at least within the error limits defined by this granularity value.

The method will then use at least one computerized device e.g. a device with at least one processor memory and software and the context hint to determine the higher significant digits of the latitude and longitude associated with the context hint. The method will also use the computerized device to parse or decode the encoded lower significant digit latitude and longitude values thereby producing decoded lower significant digit latitude and longitude values. The method will then combine the decoded lower significant digit latitude and longitude values with the higher significant digit latitude and longitude values associated with the context hint thereby determining a complete address with both higher significant and lower significant latitude and longitude values.

As will be discussed the present invention is a computerized system and method that generate short local addresses and enables the human user to pinpoint locations with the accuracy and precision of geographical coordinates Latitude Longitude but in a user friendly manner. As such it is intended to provide an alternative to local search for businesses prior art coordinate based addresses and Geocoding based methods for determining location.

The basic idea is to reduce the long series of digits presently used to express high precision latitude and longitude information down to a combination of a context hint for the digits of high significance and the remaining digits of low significance trimmed to appropriate precision. One of several context hint choices may be selected ideally based on non cryptic references to generally known locations for the higher significant digits of the geographic coordinates. This enables a relatively short and human manageable string of data such as two to four symbols for the latitude and two to four symbols for the longitude to be used for the lower significant digits of the geographic coordinates. The net result is to produce detailed and accurate geographic location data that is also easy for human users to remember and enter into various computerized devices. Because for local use the context may be available by other means such as GPS this enables users to enter in extremely short length location data information. For non local use the context hint itself will give the non local user an often human readable idea of the gross location of the location of interest. An additional benefit of this approach is that although usually intended for use with GPS equipped computerized devices the method can also be made compatible with non computerized and or non GPS systems even including paper and printed maps.

When used within a locality the local address field may be all that is needed i.e. sufficient for many uses such as for human users who don t need the full global coordinates. Thus computing devices that are aware of the relevant context such as with the center or focus of an interactive digital map FIG. to be discussed or the current location FIG. also to be discussed may also utilize the local address directly without the need to use additional information.

However for remote use according to the invention the local address field needs to be associated with a context field to fully resolve the more complete latitude and longitude coordinate values. In general the conversion is Remote Address Context Hint Scaled Offsets Local Address

The context hint field can refer to at least two types of contexts. One is a reference locations point type context or a context repository entry typically region polygon type context. Often the context hint can be any text likely to be found in a prior art or conventional geo search system or custom context repository that is representative of a desired context for the Target Location to be discussed .

In situations where the target location is too far e.g. greater than about 0.5 the desired latitude or longitude granularity setting which is often 1 from a reference location the scaled offset field may also be applied to the reference location. Such offsets may also be useful because the reference location coordinates can occasionally vary significantly depending on which conventional geo search system is used to determine the latitude and longitude of the context. The offset field may be scaled such that integer increments are equivalent to 0.5 the desired latitude or longitude granularity setting which again is often 1 .

The parser software directs the device s processor to split an input address into the various address fields or parts and as previously described in above. In some embodiments the data granularity may be derived from the local address .

One or more optional context repositories may be used to augment customize or override entries in conventional geo search systems . Here for example a minimal embodiment of an entry can have a Name or Code and Center Location the default region of applicability being 0.5 Granularity neighborhood of Center .

Another alternative minimal embodiment of such an entry can use an asymmetric polygon to customize interpretation of the local address within the polygon region.

The coordinates calculator is a main element of the Glocal system. This software module calculates and fills in the missing parts of the global coordinate values in an input local address.

The invention may also use a software module to run conventional geo searches i.e. a conventional geo search delegator can be used to communicate with one or more conventional geo search systems .

The results presenter may often return a single location result possibly with additional related information. Alternatively the results presenter may return multiple candidate location results. This can often happen when there is some ambiguity. In this case multiple results may be sorted using a software implemented heuristic algorithm that for example checks if a candidate location is in water and if so will discard or deweight that option.

The system may also optionally provide a Glocal application programming interface API . This API can be used by other applications to interact with or utilize the Glocal system on the server . Additionally other client applications may also interact with or utilize the Glocal system via this Glocal API.

By way of reference this example location is in a parking lot just outside the oldest winery in California 18000 Old Winery Road Sonoma Calif. . Many visitors to San Francisco like to visit wineries in the famous Napa valley. The city of Sonoma is nearby but it is not as well known.

To get to this location often visitors fly into San Francisco International Airport airport code SFO and may need to plan their trips from SFO. According to the invention various different Glocal Addresses can be created with respect to all these reference locations and this is shown in .

According to the invention both San Francisco and SFO can be used for the context data but note that San Francisco and SFO are more than 0.5 away from the given target location and thus require coordinate offsets here represented by N . Note also that Sonoma being a small city fits within 0.1 latitude and longitude granularity. It thus provides superior or at least more local context data. As a result according to the invention when Sonoma is used as the location context and because 3 digits for each latitude and longitude are sufficient to unambiguously represent the target location within 0.05 of Sonoma then by using Sonoma as the context the target location coordinates of 38.297813 122.425126 can be expressed by three latitude and three longitude digits rather than with the four latitude and four longitude digits as would be required if the more distant SFO or Napa context hint was used.

As an alternative to all numbers some form of encoding may be used for the Local Address. Encoding is covered in .

By contrast the solid non rectangular custom context San Francisco Bay region SFBay illustrates the invention s alternative asymmetric proximity methods. These alternative methods allow encompassing much of the San Francisco Bay area into a single context without changing granularity.

The architecture in also includes the Glocal system of within the client. In this embodiment the conventional geo search delegator component of the Glocal system may communicate often through a network such as the internet and often using a wireless connection with a server e.g. internet server that provides the results of a conventional geo search System . Examples of such a conventional geo search system include Google Maps and the like.

In alternative embodiments parts of the Glocal system s may simultaneously operate in one or both of the client and or server devices. Here for example a cached subset of the context repository may operate on the client for quick access and or offline operation.

Depending on the embodiment there may be multiple context repositories one context repository or even no context repository. An example of multiple context repositories would be a first repository with custom large contexts and a second repository that stored Airport Codes with locations. These multiple context repositories could exist on one server or multiple servers.

Similarly there also may be multiple servers e.g. each performing Glocal functions and or GeoCoding for different regions of the world.

Examples of various client computerized devices that can be used by a human user to interact with the invention s Glocal system include personal computers often through internet browsers mobile phones smartphones tablet computers and the like often through native apps or internet browsers . All will generally also have at least one microprocessor memory and various input and output devices such as graphical user interfaces often with bit mapped display screen s touch screen or mouse input and optional keyboard input. Some may make use of other input output schemes such as audio e.g. speech input and output.

In general any computerized device or application that deals with communication or storage of location location representations maps navigation addresses contact information and the like can take advantage of the invention s Glocal methods.

Step Select a representation of the target s latitude longitude coordinate angles. Generally a preferred representation is Decimal Degrees.

Step Select a desired precision for the coordinates. Generally a preferred precision of 0.0001 is often used which corresponds to approx 10 meters.

Step Optionally round off or trim the latitude and longitude coordinates to a selected precision and pad with zeroes if necessary.

Step Remove digits of Granularity and higher significance. Also remove the sign. In rare cases such when the target is on the equator or prime meridians e.g. London UK the sign can change within a locality. In such cases the sign can be replaced with a special context hint or offset such as E for East to resolve this ambiguity

Step After the previous steps what remains is essentially the Glocal local address FIG. A which can then be formatted for output or storage in several different ways. For remote users additionally a context hint FIG. A and Offsets FIG. A can be used. See .

Step Simple number type local address format. A simple number format is a pure numbers pair that is optionally separated with a comma e.g. 1234 5678 or other separation symbol. This number pair may be formatted in many alternative ways and is often the preferred format.

Step Simple alphanumeric latitude or longitude encoding format. One simple encoding that may be applied to one of latitude or longitude is to use alphanumeric characters such as A 1 B 2 C 3 D 4 E 5 F 6 G 7 H 8 I 9 and Z 0. This format has the advantage that the distinction between latitude and longitude is immediately obvious to human observers i.e. numeric versus letters and thus a separator symbol is not needed e.g. ABCD5678 .

Step Interleaved type Glocal local format. Optionally the alpha numeric local address may be interleaved e.g. AB56 CD78 to represent progressively reducing tiles i.e. AB56 representing a 0.01 by 0.01 region and CD78 a 0.0001 by 0.0001 region within it . Such interleaving may be preferred for some map tile labeling applications.

Step Other formats to express Glocal local addresses are also possible. In general any combination of local address digits can be used including with or without encoding for latitude and or longitude with or without separators forward or reverse interleaved or not with or without additional text symbols based on local preferences or not. Here if the implied granularity units or precision cannot be determined easily from the input data the user s previously established preferences like miles vs. km can often be used to help disambiguate local addresses.

Decimal Granularity Based Encoding In the Interleaved Local Format Step if a user enters AB12 it is not clear whether AB12 or AB12 is intended. To avoid ambiguity additional clues may be introduced by using different latitude encodings for the former and latter parts such as in Table 1. The new address would then be AB12 QR12 or AB12QR12. Further this can be extended to two additional orders of magnitude of granularity by not encoding Latitude digits at all. When used with country code as context hint this scheme can give a fixed width global address that looks like CC 1234. AB12 QR12 where CC is a 2 letter country code such as ISO Country Code.

This scheme removes ambiguity about granularity when parts of a Glocal address are used without separators. For example the location of Shanti Guest House at 2 20 2 Nishi Kasai Edogawa ku Tokyo Japan with coordinates 35.666569 139.854093 would have a remote Glocal address JP 3539.FF85 VU41 using this scheme. Parts of this Glocal address can be used in different combinations as shown in the Table 2 below 

Although most examples in this disclosure are based on the base 10 numeric system alternative schemes are also possible. As an example an alternative Glocal base 30 encoding scheme such as below can be used to subdivide 1 latitude and longitude measurements into smaller increments in a manner that is similar to a geographic latitude and longitude minute and second approach. Here base 30 can be mapped onto the standard 1 10 and A F alphanumeric symbols by a scheme such as shown in the Table 3 below 

In this alternative scheme the first character or symbol can represent degree 30 the second character or symbol can represent degree 30 the third character or symbol can represent Degree 30 and so on. This scheme is very efficient because with only three symbols it can represent geographic locations with a precision of 00A 1 27000 3.7e 5 approximately 4 meters. Thus using base 30 Glocal nomenclature the geographic location 17 52.067 25 30.367 can be encoded as H8A LVR 6 characters 0.000037 precision . By contrast if more common base 10 decimal encoding is used this would require two extra symbols e.g. 2978 4251 8 characters 0.0001 precision . Thus base 30 encoded Glocal address parameters can be both more compact than decimal parameters and also slightly more precise. In situations where compactness is paramount to users then use of such base 30 methods may be preferable. Other base encoding methods may also be used although normally base encoding methods between about base 10 and base 128 inclusive will be used.

The base 30 encoding of Table 3 can be enhanced by introducing a separator such as the colon character to indicate granularity. This is useful when the Glocal local address is used partially. Additionally if granularity is 3 degree the resulting lowest three levels of precision may correspond approximately to the size of a typical town 3 30 0.1 degree approx. 10 km neighborhood 3 30 0.003 degree approx. 300 m and building 3 30 0.00011 degree approx. 10 m . For example Tokyo ZR SP9G represents Shanti Guest House from above. The first part of the local address ZR represents a town sized region centered at Edogawa and SP approximates a neighborhood centered at Nishikasai. The colon symbol disambiguates which granularity is intended.

Step The selection of a reference location often involves selecting the nearest well known place. This can be assisted by using the previously obtained reverse GeoCoding results

Step Calculate Glocal offsets difference between the reference location coordinates and the target location coordinates 

Step Scale each component of the Glocal offsets by 2 Granularity. The resulting components may individually be ignored if they are less than 1 in magnitude preferably well below 1 e.g. 

Step Round off and format the scaled offsets. Here a simple format may be used such as N for 1 0 W for 0 1 and for larger offsets 3S2E for 3 2 may be used. In general many types of convenient separator symbols such as dash symbol may be used as a prefix here.

Step Additional reference locations may also be chosen from other well known places nearby the target location. To allow this type of flexibility the invention also allows multiple alternative reference locations to be used depending on the characteristics of the Glocal address recipient. For example in the case where a Glocal address is being calculated for a house address in Cupertino Calif. and the Glocal recipient is an individual who is not familiar with San Francisco bay area then a context based on San Francisco or San Francisco International Airport airport code SFO may be more appropriate. Alternatively if the recipient is someone who is more familiar with the San Francisco Bay area then Cupertino may be more appropriate to use as the reference or context location.

Step Optionally in case of multiple reference locations are feasible the system can present the user with a list of these various possible reference location and even sort these reference locations according to various criteria such as importance distance to the target location FIG. A convenience preference and so on.

Step the system looks for any available context repository FIG. B entry that geometrically includes the target location .

Step Optionally in the case that multiple suitable context repository entries are found the system can present them in a sorted order based on previously discussed criteria such as importance distance to the target Location convenience preference and so on.

Step The name or text based code representing any of the reference locations Step or context repository entries Step may also be used as a context hint FIG. A along with corresponding formatted Scaled Offsets FIG. A 

Input Name nickname code and or aliases. Generally it is best here for the user to enter short convenient familiar or memorable text

Input Location and or shape details. In some embodiments the system may be set to use a default shape such as 0.5 Granularity around Location. This may comprise a centroid location or alternatively any other type of shape definition such as rectangular bounding box i.e. min max of Coordinates . Here the idea is that the polygon should preferably be defined such that the included local addresses inside the polygon are unique . Alternatively a circle with a center and radius may be used.

Input Optional context granularity. Here it is often convenient to set the system to use a preferred default value such as 1 . In some cases however this may also be inferred from the shape definition .

Input Optional importance level or weight. These parameters can be used to sort or determine the preference of an entry in the case where a particular target location is included or found within multiple context repository entries. Alternatively the granularity parameter itself may be used in some cases usually with higher Granularity carrying more weight.

Step The system parses the input looking for the context hint scaled offsets and local address parameters. This can be done in the parser software code or module 

Step Extract granularity from local address. In a preferred embodiment the system algorithm logic assumes or has a preference for decimal degrees input. The system will generally assume that the number of symbols in the local address latitude parameter is the same as the number of symbols in the local address longitude parameter. In some embodiments the system may further assume when the parameter is characters long and that this further represents a default granularity of 1 and when the parameter is 3 characters long this represents a default granularity 0.1 . These default values may be modified by the system settings and user preferences however to further identify units input format and Granularity as needed.

Step The system may be configured so that that if the context hint is not provided then the system will assume a reference location see step . If a context hint is found then the system will follow one or both paths shown in the steps starting at step and step below.

Step The system will search for context names matching the hint and granularity in the context repository 

Step The system will collect matching contexts in some embodiments using their centroids as reference Locations R and then jump Go To step .

Step The system will search for a context hint in one or more conventional Geo Search systems FIG. . This can be done by the conventional Geo Search delegator FIG. B .

Step The system may be configured to assume that the reference location is the center or focus of an interactive digital map FIG. current Location FIG. or any other location based on the system settings user preferences such as Home City .

Step Optionally such as when there are no coordinate offsets the system may also consider the proximate context repository entries with their centroids as being the reference locations R and then jump Go To step .

Step The system will then multiply the scaled offsets by 0.5 Granularity to get the unscaled offsets thus ensuring the proper interpretation of positive and negative signed location data here North and East are assumed to be positive South and West are assumed to be negative .

Step The system will apply the unscaled offsets to each reference location i.e. apply an R R Offset transformation.

Step The system will then continue to part 2 of this process shown in to deduce the latitude and longitude coordinate values.

Step Given one or more reference locations from Step and the Glocal local address from step the invention s software implemented methods will then proceed as follows 

Step The system will parse and decode the input data to extract the local digits of latitude and longitude. As previously discussed the system may use its previously determined settings and user preference parameters to disambiguate any ambiguous units and input formats.

Step The system will estimate the missing leading significant digits of the latitude and longitude coordinates. This step can be done in the coordinates calculator software code or module FIG. B . Assume use of decimal system data one way to do this is as follows 

Based on granularity the system will determine and appropriately place the decimal points on the local digits of each component

The system will then multiply this result by the sign of the reference location coordinate subtract result the result from the reference location coordinate and then round off the results to the nearest Granularity. Thus for example if the granularity 1 the longitude of the reference location 114.9 and the local digits of the longitude are 1257 then we can determine that the reference longitude is reference longitude is 114.9 sign 114.9 0.1257 114.7743 which when rounded to the nearest integer is 114.7743 115

This methodology tends to give the closest estimate but other methods can also be used. Here for example alternate methods can include simply truncating or rounding off the reference Location coordinate such that granularity is maintained.

Step Fill in the trailing significant digits with the Glocal local digits to get a latitude longitude pair C .

Step In some cases the result C of step may not always be the intended location e.g. the reference location may not be close enough . In this case we may optionally consider as additional candidates all adjacent combinations of latitude longitude C Granularity

Step The method will sort these candidates based on the distance to the reference location R with offset applied . Here the method will give additional priority to those candidates that are located within the proximate context repository entries from Step or .

Step The method will then present the nearest candidate as single result and or present a filtered subset of the candidates based on heuristic algorithms. Here an important consideration for asymmetric contexts is whether a candidate location falls inside the context s polygon region. Here step and step can be done in the results presenter software module FIG. B .

Example 1b uses an alternative setting. Here using degree decimal minutes input format DDD MM.MMM with Granularity 10minutes precision 0.001 minutes.

With regards to the 310 Washington St Boston example this address can be challenging for conventional geocoder software methods as there are several such locations in the Boston area. Here however by using the invention s Glocal method each different location can have a separate local address within the Boston area.

With regards to the National Air and Space Museum Washington D.C. area example here there are actually two such museums. In this situation Glocal can be helpful in two ways 

With regards to the Ajanta Caves India example these caves contain famous frescos and are a popular tourist attraction in a remote location in western India. The nearest town is Aurangabad Maharashtra 104 km away and the nearest major metro is Mumbai formerly Bombay airport code BOM . The invention s Glocal address approach is particularly useful because it gives a quick idea of the distance between the caves and these reference locations as well as the relative direction of the caves.

Other examples in illustrate use of the invention s Glocal methods in all of the continents of the world.

Additional uses of the invention s Glocal address representation methods can include use with more traditional printed maps artificial landmarks such as billboards electronic messages eMarketing and even verbal communications.

Here for example static maps e.g. static digital maps or non digital printed maps can be annotated with Glocal local addresses or part thereof and with optional simple Glocal latitude encoding. Thus city or metro area maps can have Glocal encoded grid rows labeled AA AB AC etc. along with Glocal encoded columns labeled and the like. The map grid tiles may be labeled with Glocal encoded labels such as A B . . . C and so on.

Further artificial Landmarks e.g. temporary displays such as banners or more permanent displays such as billboards or structures can also be annotated with Glocal address or parts of Glocal addresses. These displays can additionally include business information such as local business advertisements promotions and so on.

Glocal position encoding methods can also be used in any electronic digital data storage or communication such as SMS Instant Text message email chat status update blog web page wiki hyperlink semantic web information URL query Contact List Address Book Calendar Business Card Blu Ray disk DVD CD wireless communication wired communication and the like. Here the Glocal addresses may be used for searching storing transferring data with intent to represent location and other activities.

Glocal position encoding methods can additionally be used in any human communication verbal written and the like to communicate location and related information.

Although as previously discussed almost any geodetic system can be used with Glocal in a preferred embodiment the latest revision of the World Geodetic System currently WGS 84 will be used. It is also useful to combine the WGS 84 system with other easy to use Glocal parameters such as unencoded simple latitude number longitude number local format and with easy to convert granularity parameters such as Granularity 1 . These settings enable Glocal address values to be better compatible with legacy maps applications devices and other systems which may not be Glocal enabled.

This is possible because the Glocal address is generally compatible with the lower significant digits of the legacy latitude longitude system but with the higher significant digits missing. Although the system will be generally used with computerized devices as needed the missing integers can also be manually determined as well. Here for example a traveler can get these higher significant digits from a GPS system or alternatively ask a local resident for the digits and insert them as a prefix to the other Glocal local address components. Here errors are easy to detect because mistaken higher order address prefix values will cause addresses to be off by at least 1 approx 100 km which should generally be quite apparent.

The invention s Glocal system can also provide addresses with extra precision as needed as long as the Glocal parser software knows how this extra precision data is to be delimited. Here one convenient scheme is to use a decimal point plus one extra digit for 0.00001 1 meter precision. Thus higher precision Glocal addresses can look like using San Francisco International Airport SFO symbol as an example SFO 1234.1 5678.9 or SFO AB56 CD78. A9.

As previously discussed the as long as a commonly understood convention is followed the specific sequence of Glocal address components separators or delimiter symbols e.g. space comma prefixes before scaled offsets used herein in the various examples are not critical. Many convenient alternative symbols may also be used. Here however it is generally prudent to choose symbols that avoid or minimize ambiguity and confusion.

In any electronic communication e.g. emails SMS Text messages or in web pages by using the invention s methods implemented in the form of software a host system or computing device can automatically convert a Glocal Address to a hyperlink to a map thus saving the user time and effort and reducing chance of error. This also provides an alternative to more tedious copy pasting methods or forcing the user to enter numbers into map application.

Thus for example the message Let s meet at 5678 1234 can be presented to the recipient as Let s meet at 5678 1234 .

Here it may be useful to use a leading delimiter such as or other distinguishing symbol to indicate a Glocal address. This delimiter would be particularly helpful with multi word Context hints such as The meeting is Bangalore India ZZ58 ED09 tomorrow morning . Such a delimiter also could help third party parsers to identify Glocal addresses in documents e.g. to recast as a link or to extract Glocal addresses for other purposes e.g. location information mining .

In a preferred embodiment the symbols used in the Glocal addresses may be chosen to be amenable to URL addresses as well as URL Shortening services. The default space delimiter can to URL encoded as usual to a plus character in URLs e.g. http x.x SFO AB12 CD34. This results in non cryptic URLs with human friendly context hints. In alternative embodiments however a broader range of symbols such as the entire printable ASCII character set may also be used.

The invention s Glocal address methods and processes may also be exposed as web services and used in conjunction with other input strings such as restaurants near SFO AB12 CD34 

As another application the sub part of a Glocal local address may be used to indicate region. Here for example restaurants in SFO AB12 would search for restaurants in the corresponding 0.01 square geographical region.

In other embodiments the Glocal software may perform the Glocal conversion process dynamically while the user is entering in the input. This embodiment has the advantage that it both serves as a visual cue to enhance the user experience and it also helps the user to detect typographical errors as the user enters the input data.

The Glocal system can also provide data mapping from Glocal address es to postal address es and or business resident names either with or without existing reverse geocoding. This may be provided either as web service or as offline data.

The Glocal system can also provide data mapping from Glocal address es to other information such as user contact information e.g. email postal address phone numbers and the like . This may also be provided as a web service or as offline data.

Glocal Addresses may be stored and further integrated into operating systems such as iPhone OS iOS Android Windows Phone Windows MacOS Linux for seamless interaction with applications such as native mapping navigation apps contact manager calendar email SMS Text messaging browser as well as third party Location Based Services.

If there is sufficient information in the Glocal context repository FIG. B the Glocal system may also operate on a stand alone basis without using information provided by a server FIG. hosting a conventional geo search system FIG. .

The Glocal system software or parts thereof can be located on many types of computerized devices including client devices server devices and or any intermediary computing device or network element.

Use for waypoints GPS receiver assigned waypoints and other waypoints can also take advantage of the Invention s Glocal methods often by using earlier assigned waypoints as a Glocal reference for later Glocal assigned waypoints.

Here for example assume N 1 waypoints are being assigned. Here using the invention s Glocal methods the previous Nth waypoint location can be used by the Glocal software as a reference location for the next N 1 th waypoint Glocal local address. Thus the successive waypoint locations in Glocal address format can be of the type Chicago 1111 2222 3333 4444 5555 6666 or alternatively Chicago 1111 2222 3333 4444 5555 6666.

This type of method can be handy for multi part directions such as proceed first to the main entrance of a large complex and then to the appropriate parking lot or building entrance . In this Glocal format this might be of the type Napa 5101 4787 Napa 5115 4808 which in turn may be written as any of the following Napa 5101 4787 5115 4808 or Napa 5101 4787 115 808 or Napa 5101 4787 15 08 because latter location is within 0.005 of former i.e. approx 0.5 km .

Alternatively using interleaved local format encoding previously discussed in FIG. A this might be Napa EA47 ZA87 AE08.

This encoding scheme may also be enhanced chosen or altered to prevent occurrence of offensive words by replacing vowels by numbers such as AEIOU 12345. This replacement may be done partially only to I and O to avoid confusion with the numbers 1 and 0 thus IO 34.

An alternative variation to this approach is to use this encoding to start from 360 divide longitude coordinates into 10 parts using 0 through 9 and then further divide this into 30 parts 0 through 29 resulting in 1.2 segments. Subsequently logic similar to above for 1 can be used for 30 30 30 sub divisions finally resulting in 0.00004 precision which is also generally quite acceptable accuracy for location and navigation.

The general concept of removing leading digits and using contexts with Asymmetric Proximity can also be useful in many other computing applications such as to reduce data allocation and storage requirements. The quantities represented need not be just angles or coordinates. Indeed this general concept can also be useful for altitude coordinates as well as other dimensions such as time mass weight and so on.

The following example shows how the invention s Glocal methods can also be used to designate a time quantity using mixed base 10 and non base 10 values. Here BC Year Month Day Hour Minute Second.Milliseconds the input can be Input 2011 May 6 12 34 56.287 the granularity can be set to Granularity Year and the precision can be set to Precision Minute. The output would then be of the form Output May 6 12 35

In an alternative embodiment an alternative Step algorithm may be used to deduce Latitude and Longitude and thereby achieve the same user experience. In this alternative embodiment the Glocal Addresses are pre calculated in part or full and then saved in storage. These pre calculated addresses can then be retrieved by a String Text search.

For example if the location 28.5859 77.0679 has a TEXT value 28.5859 77.0679 associated with it in computer memory storage similar to conventional place name then if a user searches for 5859 0679 the system can search for 0.5859 0.0679 representing wildcard near the reference location or context as conventional geo searches may already do and get the coordinates 28.5859 77.0679 as a result. With a different encoding scheme say if a global address is abcdefgh and input is efgh then the system can search using string operation endswith and further select a result based on proximity to the reference location or context.

An alternative user interface and method which reduces the need for a user to enter in the higher significant digits of an address of interest may also be used. This alternative interface and method can automatically pre fill parts of the address input field based on the system s knowledge of the user s current location or context e.g. SFO . This is useful if an explicit context hint is desired for any reason.

This approach is superior to alternative approaches such as simply pre filling the field with the higher digits of latitude and longitude e.g. 37. 122. because the intended location may have digits of Latitude or Longitude that are one degree higher or lower than the pre filled value thus making the results unreliable in many cases. By contrast the invention s Glocal methods are more robust in this regard.

An alternative to Steps and is to use the following formula for each of Latitude and Longitude Initial Candidate sign Reference Location Granularity round abs Reference Location frac Granularity frac where frac represents the fractional value of Latitude or Longitude based on Granularity of input Local Address.

The Glocal Address parser can also be configured to support a comment or general payload which is passed through to results. This feature can be used for postal purposes with the payload comprising information such as apartment number suite number floor number person or business name or the entire postal address. Further reverse geocoding if available can be used to match the postal address.

Screen shots in illustrate common steps in a typical use case. In this use case the previously discussed Tokyo Shanti Guest House address is again used as the example.

To begin with the Glocal address for this Shanti Guest House location needs to be generated. Here a user may use the computerized system to zoom in and center the map at the desired Shanti Guest House location. The Glocal system in turn generates the location local address corresponding to the center of screen marked by cross hair and in this example presents the results in two alternative formats. These are 

Additionally several context hint options with appropriate scaled offsets are provided for each local address format. In this example the context hints are represented by the IATA Airport codes followed by the UN Locodes United Nations Code for Trade and Transport Locations and these in turn are sorted by a combination of distance importance and other heuristics.

In this example different users are involved. For example a first user such as the manager of the manager of the Shanti Guest House hotel may do a Glocal lookup on a one time basis and then publish the Local Address provided by the system e.g. ZR SP9G on the Shanti Guest House hotel website contact info business card etc. for later use by hotel customers . This short local address would be sufficient for use all over the Tokyo metro area. Additionally for non local visitors one or more context hints provided by the system such as TYO the airport code for Tokyo or JP.EGA the UN Locode for Edogawa Japan may also be recommended. Of course many visitors may prefer the more natural choice of Tokyo as a context hint.

Next a smartphone user who may be a potential Shanti Guest House hotel guest and who is also located somewhere in Tokyo metro area will try to find the Shanti Guest House hotel. She can find the hotel by entering a 6 character Glocal Local Address Base 30 encoded with colon separator ZR SP9G into her smart phone. This is shown in which shows the smartphone screen both before the search and also successfully pinpointing the Shanti Guest House hotel target location after the search. Here assuming that the smartphone is configured with its GPS location feature enabled the system software can then automatically insert the context hint based in part on the smartphone s present GPS location.

As another example consider another smartphone user who may be a local Edogawa Tokyo resident or local businessman who wants to meet our guest from the previous example. Here the user may be located within Edogawa approximately 2 miles from the Shanti Guest House hotel. At this distance this local businessman need only enter the last 4 characters of the 6 character version of Local Address Base 30 encoded with colon separator here SP9G . Here again assuming that the smartphone s GPS location feature is enabled the system software may be programmed to recognize that when only four characters are loaded the granularity is smaller and thus the software should automatically insert the higher order location values based in part on the smartphone s present GPS location. This is shown in which shows the smartphone screen before the 4 character SP9G address search and again successfully pinpointing the Shanti Guest House hotel target location after the search . The system thus allows users to generally enter in the minimum amount of data as appropriate to the user s particular circumstance and thus minimizes user typing and the chance of inadvertently generating typographical errors.

An alternative way to avoid ambiguity due to sign change near the equator and prime meridian is to transform Latitude and Longitude values to a range from 0 to 180 degrees and 0 to 360 degrees respectively.

Closer to the poles a unit difference in Latitude and Longitude does not correspond to the same distance. To adjust for this or for any other reason Latitude and or Longitude values may optionally be transformed by various linear or non linear functions.

The inventions Glocal concepts may be also be applied with encodings that combine latitude and longitude e.g. a one character per resolution of coordinates instead of 2 characters e.g. twenty five letters of the English alphabet can be used to define a 5 5 grid as in the Table 4 below 

Since an important object of the invention is to increase the human usability of latitude and longitude determinations market input can be an important factor at determining which of various schemes may be implemented. These market preferences which may vary from region to region may be used to determine which specific embodiments of the system may be implemented in a particular region.

