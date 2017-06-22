---

title: System and method for adjusting the amount of data bandwidth provided to a mobile device
abstract: The invention is conveniently suited for use in telecommunications system and does not require modifications to be made to existing telecommunications system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08874073&OS=08874073&RS=08874073
owner: Chikka Pte Ltd.
number: 08874073
owner_city: Singapore
owner_country: SG
publication_date: 20120629
---
The present invention relates to a system and method for adjusting the amount of data bandwidth provided to a mobile device. The system and method are particularly suited but not limited to adjust data bandwidth for a mobile device having a pre paid subscriber account with a telecommunications carrier and will be described in this context.

The following discussion of the background to the invention is intended to facilitate an understanding of the present invention only. It should be appreciated that the discussion is not an acknowledgement or admission that any of the material referred to was published known or part of the common general knowledge of the person skilled in the art in any jurisdiction as at the priority date of the invention.

Mobile devices such as smartphones have recently surpassed the conventional desktop or laptop PCs as a popular means for people to connect to the internet to connect with one another and or play online games. This in part is fueled by social networks and mobile software applications. The main advantage of mobile phones is in their ability to be Always On or connected to the Internet wherever the user is. Mobile phone users may receive and or respond to Instant messaging messages Facebook tags Tweets instantly in real time wherever the users are as long as data cellular connection GSM GPRS 3G LTE 4G etc. can be established.

The above advantage of mobile phone complements markets where majority of telecommunication carrier subscribers prefer mobile data post paid plans. Subscribers of these post paid plans generally do not mind paying more per month to have unlimited Internet data access or a data usage capped at a relatively larger size for example 12 Gigabytes GB .

However providing always on Internet or data connection has remained a challenge for telecommunications carriers in markets dominated by users who prefer prepaid plans or pay as you go plans . In these markets users are less willing to pay a relatively larger subscription fee for internet access. A typical prepaid plan is based on a pay per specified time model such as 10 pesos for 30 minutes of fast Internet connection. Another variation to the pay per specified time model may be a daily always on access to only social networking sites such as Facebook or Twitter for 20 pesos per day.

As cost is generally an important concern for prepaid plan users a challenge for telecommunications carriers is to deliver Internet connection at relatively lower sachet price points such as below 20 pesos daily yet still providing prepaid plan users an always on experience i.e. internet on demand. While this may be possible for certain phones which are efficient in terms of consuming data bandwidth it is typically difficult to implement such sachet price points for more recent smartphones models which require relatively higher data bandwidth. There is thus a need to capture the market of these smartphone users by providing them with certain flexibility in controlling and adjusting their data bandwidth usage so as to implement such sachet price points.

Although it is possible for prepaid plan users to control data bandwidth and monitor their bandwidth usage known control mechanisms in place are all or nothing approaches i.e. data access may only be switched from either all maximum data bandwidth or nothing no data bandwidth. The user does not have the flexibility in controlling different levels of data bandwidth as and when he she desires depending on his her usage.

The present invention seeks to provide a system and method that alleviates the above mentioned drawbacks at least in part.

In accordance with a first aspect of the present invention there is provided a system for adjusting the amount of data bandwidth provided to a mobile device comprising a bandwidth adjustment facilitator arranged to receive a request from the mobile device for adjusting the amount of data bandwidth a bandwidth throttler in communication with the bandwidth adjustment facilitator the bandwidth throttler adapted to cap or allocate excess available data bandwidth to the mobile device wherein on receipt of the request the bandwidth adjustment facilitator process the request and if the request is successfully processed adjusts the data bandwidth provided to the mobile device via the bandwidth throttler.

Preferably the request for adjusting the amount of data bandwidth is in the form of one of the following Short Messaging Service SMS message electronic text message Unstructured Supplementary Service Data USSD message.

Preferably the data bandwidth is adjustable between two modes comprising a trickle mode where data bandwidth is 9.6 kbps and lower and a boost mode where data bandwidth is at least 2 Mbps.

Preferably the system further comprises a subscriber database arranged to maintain details of a plurality of subscribers and an accounting database arranged to be in data communication with the subscriber database for the settlement and checking of available funds for each subscriber and maintaining a history of transaction of each subscriber.

Preferably the mobile device is arranged to send the request automatically to the bandwidth adjustment facilitator based on the usage profile of the mobile device.

Where the bandwidth adjustment facilitator is arranged to monitor the usage profile of the mobile device the bandwidth adjustment facilitator is adapted to send a prompt to the mobile device prompting the user of the mobile device if he would wish to adjust the data bandwidth according to the usage profile.

The usage profile used to determine if the data bandwidth should be adjusted to boost mode is based on one or more of the following detection that the mobile device has consumed the maximum data bandwidth of the trickle mode for a predetermined period of time detecting that an active connection is established with a URL IP address that is known to deliver video images or large files for a predetermined period of time detecting that a file of a certain type and size is being accessed or downloaded and detecting that the mobile device uses progressive http download.

Preferably the bandwidth adjustment facilitator is arranged to check the access point name APN of the mobile device prior to processing the request.

Preferably the bandwidth usage is charged or billed based on either a pay per specific time model or pay per action model.

More preferably the pay per specific time model or pay per action model is activated by sending a request from the mobile device to the bandwidth adjustment facilitator the bandwidth adjustment facilitator operable to upon receiving the request toggle between an existing billing infrastructure implementing the pay per specific time model and an independent billing module implementing the pay per action model. In this case the toggling from the existing billing infrastructure to the independent billing module may be achieved either by switching off the existing billing infrastructure or defining the data bandwidth connection as a zero tariff.

In accordance with a second aspect of the present invention there is provided a method for adjusting the amount of data bandwidth provided to a mobile device comprising the following steps a. receiving at a bandwidth adjustment facilitator from the mobile device a request to adjust bandwidth b. processing the request to adjust bandwidth and c. adjusting the data bandwidth to the mobile device via a bandwidth throttler upon successful processing of the request.

Preferably the request for adjusting the amount of data bandwidth is in the form of one of the following Short Messaging Service SMS message electronic text message Unstructured Supplementary Service Data USSD message.

Preferably the bandwidth is adjustable between two modes comprising a trickle mode where data bandwidth is 9.6 kbps and lower and a boost mode where data bandwidth is at least 2 Mbps.

Preferably the processing step includes checking a subscriber database to determine if the mobile device has a subscriber account and the subscriber type pre paid or post paid and checking an accounting database for available of funds to make the adjustment of bandwidth.

Preferably the request is sent automatically to the bandwidth adjustment facilitator based on the usage profile of the mobile device.

Preferably the bandwidth adjustment facilitator is arranged to monitor the usage profile of the mobile device and sends a prompt to the mobile device to adjust the data bandwidth to boost mode according to the usage profile.

The usage profile used to determine if the data bandwidth should be adjusted to boost mode is based on one or more of the following whether the mobile device consumed the maximum data bandwidth of the trickle mode for a predetermined period of time detecting that an active connection is established with a URL IP address that is known to deliver video images or large files for a predetermined period of time detecting that a file of a certain type and size is being accessed or downloaded and detecting that the mobile device uses progressive http download.

Preferably the method includes a step of checking the access point name APN of the mobile device prior to processing the request.

Preferably the method comprising an additional step of billing for the bandwidth consumed based on either a pay per specific time model or pay per action model.

More preferably the pay per specific time model or pay per action model is activated by sending a request from the mobile device to the bandwidth adjustment facilitator the bandwidth adjustment facilitator operable to upon receiving the request toggle between an existing billing infrastructure implementing the pay per specific time model and an independent billing module implementing the pay per action model. In this case the toggling from the existing billing infrastructure to the independent billing module may be achieved either by switching off the existing billing infrastructure or defining the data bandwidth connection as a zero tariff.

In accordance with a third aspect of the present invention there is a mobile device containing software instructions wherein upon execution of the software instructions performs the any of the method of the second aspect to adjust the data bandwidth.

In accordance with a fourth aspect of the present invention there is a mobile device containing software instructions to send a request for selection of either the pay per specific time model or the pay per action model.

Other arrangements of the invention are possible and consequently the accompanying drawings are not to be understood as superseding the generality of the preceding description of the invention.

In accordance with an embodiment of the present invention there is a system for adjusting the amount of data bandwidth provided to a mobile device . The system comprises a bandwidth adjustment facilitator in communication with a bandwidth throttler a subscriber database and an accounting database . In the embodiment data bandwidth is provided to the mobile device via a host such as telecommunications carrier .

The mobile device is a smartphone capable of the installation of mobile software application or apps . The mobile device is connectable to the mobile data Internet via various mobile data services such as GPRS Enhanced Data rates for GSM Evolution EDGE 3G LTE 4G etc.

The bandwidth adjustment facilitator is adapted to process requests from the user of mobile device to the telecommunications network for the adjustment of data bandwidth. In this sense the bandwidth adjustment facilitator is within a proxy gateway server for connecting to the Internet. The requests are in the form of simple text or Short Messaging Service SMS Unstructured Supplementary Service Data USSD messages or any other form of an electronic signal message wherein a software application is installed on the mobile device for such a purpose.

The subscriber database maintains details of the subscribers of telecommunications network such as the Mobile Subscriber Integrated Services Digital Network Number MSISDN of each subscriber mobile phone. The subscriber database is in data communication with the accounting database for the settlement and checking of available funds for the subscriber of mobile device . The accounting database further maintains a history of transaction of each subscriber.

For the case where the mobile Internet service is a GPRS service the bandwidth adjustment facilitator and the bandwidth throttler are typically located between the Gateway GPRS Support Node GGSN and the Service Aware Support Node SASN of the GPRS core network.

The mobile device is installed with a dedicated mobile software application depending on the particular model of the mobile device . For a typical smartphone such as an iPhone or Android this may be an app as colloquially known. For ease of reference the dedicated mobile software application will be interchangeably known as Boost Apps .

Prior to use the mobile device is checked if it has been registered as a subscriber of the system via checks on the MSISDN of the mobile device or other methods as well known to a skilled person. If the mobile device is a not a subscriber the user of mobile device is prompted a message by the software application to change the Access Point Name APN of the mobile device. An example of the message is as follows To use the ABC Boost Apps please change the APN of your smartphone to internet.abc.com .

If the mobile device is already registered as a subscriber for the system then there is no prompt to change the APN.

Alternatively the telecommunications carrier may have dedicated APNs for the purpose of carrying out the present invention and requires the user of the mobile device to change the APN accordingly.

Any change in APN effectively changes the proxy internet gateway of the telecommunications carrier thus directing internet data communication to be routed via the system .

The installed software application may be manually activated by the user of mobile device wherein the application opens a user interface see providing the option to adjust the bandwidth as desired or may include a detecting algorithm for detecting the data usage profile of the subscriber for mobile device . The detecting algorithm will be discussed subsequently.

The mobile software application next provides the user interface for the user of mobile device to toggle control of his data speed between a trickle mode i.e. 9.6 kbps to 14.4 kbps and a boost mode 2 Mbps onwards if on 3G for example on demand. For the subscriber having a pre paid contract or plan the default mode for the data speed is the trickle mode.

Upon clicking the button Boost on the user interface the request to change the data speed from trickle to 3G or higher depending on the limitation of the network is sent to the bandwidth adjustment facilitator . The bandwidth adjustment facilitator proceeds to process the request by verifying if the MSISDN of the mobile device is in the subscriber database . Further steps such as password authentication SMS verification may also be performed as known to a person skilled in the art to authenticate the subscriber.

Once the request is successfully verified the bandwidth adjustment facilitator checks the accounting database to make sure that the subscriber has enough funds to pay for the boost .

Upon determining that there are enough funds in the subscriber pre paid account or pre paid card the bandwidth adjustment facilitator proceeds to adjust the bandwidth settings for the subscriber of mobile device . This is done via the bandwidth throttler which either caps the data speed of connection between the mobile device to the internet or allows any excess available data bandwidth to the mobile device .

As mentioned earlier instead of manually activating the dedicated software application the dedicated software application installed on the mobile device may include a detection algorithm for detecting the usage profile of the subscriber for mobile device . The detecting algorithm may also be installed on the bandwidth adjustment facilitator .

Upon inferring from the detecting algorithm that the subscriber is likely to be downloading an image watching a video or accessing any large file including websites which are for example image graphic intensive thus requiring more data bandwidth the bandwidth adjustment facilitator activates the dedicated software application to prompt an alert to the user of mobile device as shown in . The corresponding rules for prompting an alert to the user of mobile device based on the results of the detecting algorithm may be one or more of the following 

Where the Internet gateway servers will be able to detect how large a file is being downloaded or the type of file thereby activating the dedicated software application to trigger an alert to boost the internet data bandwidth.

Where the dedicated software application is installed on the mobile device the request is sent automatically to the bandwidth adjustment facilitator to adjust the bandwidth once it is determined that one or more of the above rules are satisfied.

In each of these instances the telecommunication carrier informs the dedicated software application for a possible upsell to BOOST alert or notification.

The described system and method further allows the user to stop or pause the boost as and when desired and thus better able to control the part of his remaining credit of the pre paid plan.

In accordance with another embodiment of the present invention as illustrated in wherein like numerals reference like parts there is a system for adjusting the amount of data bandwidth provided to a mobile device . The system comprises a bandwidth adjustment facilitator in communication with a bandwidth throttler a subscriber database and an accounting database . Additionally the system further comprises a pay per action based independent billing module . In this embodiment the bandwidth adjustment facilitator further maintains a list of different charging rates or plans and has a toggling mechanism to toggle from the existing billing structure to the pay per action independent billing module .

Independent billing module is operable to be in data communication with the subscriber database and accounting database . Independent billing module is arranged to provide a per action charging mechanism for charging billing a subscriber for his Internet bandwidth usage. The independent billing module is advantageous because it does not require modifications to the existing billing charging structure database and may be implemented as a convenient add on to the existing resources.

 Per action charging is a charging model based on an action taken by the subscriber. Examples of such action s are defined as follows 

ii. Viewing an up to 10 minute video or flick on Youtube In this regard billing or charging occurs once for a full download and viewing i.e. the bill charge is the same regardless of how long the video takes to download or begins to stream. This is to be contrasted from the conventional pay per specified time charging where the subscriber end user is charged based on time taken for download 

iii. Uploading images videos in social networking sites Similar to the Youtube viewing example the bill charge to the user is the same regardless of how long it takes for a photo to upload or how big a file the upload entails. and or 

iv. Any other actions which the user the application developer or the telecommunications network service provider may define. This may include toll free downloads of mobile applications apps but usage of these apps to perform subsequent functions including i to iii above may be chargeable on a per action basis.

In the context of the embodiment other actions which may fall within the definition of per action charging may include per click within dedicated smartphone App per click within web browser etc.

 Per action charging offer additional choice for a pre paid subscriber as it allows the pre paid subscriber to choose from the conventional pay per specified time model pay per specified time mode such as 10 pesos for 30 minutes of Internet connection and or the daily always on access to only social networking sites such as Facebook or Twitter for 20 pesos daily to the per action charging model depending on his preference such as time location and or usage.

In this embodiment the previously discussed Boost App may include an additional function which allows a subscriber of mobile device to toggle between the pay per specified action charging billing model to the per action charging charging billing model. Alternatively the toggling function may be implemented as another dedicated software application or App.

The request for switching to per action charging is in the form of simple text or Short Messaging Service SMS Unstructured Supplementary Service Data USSD messages or any other form of an electronic signal message wherein a software application is installed on the mobile device for such a purpose.

The embodiment with emphasis on the usage of the billing module for charging billing a subscriber s data bandwidth usage will next be described in the context of its use.

Upon detection that per action charging is to be adopted via a request from the user of mobile device the bandwidth adjustment facilitator switches from the existing billing infrastructure of the telecommunications carrier to the billing module . This may be achieved by either 

b. defining the Internet connection as a zero tariff equivalent to no charge on existing billing infrastructure .

The billing module then takes over the billing charging based on per action charging depending on the adjustment of bandwidth between the trickle mode and boost mode as previously discussed.

The billing module is complementary with the flexible adjustment of data bandwidth. In particular when a request is sent to the bandwidth adjustment facilitator to adjust the bandwidth from trickle to boost mode in conjunction with the request to bill based on per action charging the subscriber of mobile device enjoys faster speed of accessing videos files at almost the same charges using the per action charging model in comparison with the trickle mode billed based on the per action charging model.

The system may be suited to incorporate other permutations and combinations of usage. In particular the billing module may include differential pricing for accessing certain websites URLs Application Programming Interfaces APIs and IP addresses. Access to these mobile services will not incur any mobile data charges to the subscriber or will be at a discounted rate.

It is to be understood that the above embodiments have been provided only by way of exemplification of this invention and that further modifications and improvements thereto as would be apparent to persons skilled in the relevant art are deemed to fall within the broad scope and ambit of the present invention described herein. In particular 

