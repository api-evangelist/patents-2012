---

title: System and method for provisioning internet access to a computing device
abstract: A system and method for provisioning Internet access to a computing device comprising an Internet access adjustment facilitator arranged to receive a request from the computing device for adjusting Internet access from a paid Internet access mode to a toll-free Internet access mode; and a whitelist in communication with the Internet access adjustment facilitator, the whitelist maintaining a list of web resources available for toll free access by the computing device; wherein upon successful processing of the request, the list of web resources are toll free for access by the computing device. The system may further be adapted for billing/charging based on either pay-per-specified-time model or pay per action model.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08874074&OS=08874074&RS=08874074
owner: Smart Communications, Inc.
number: 08874074
owner_city: Makati
owner_country: PH
publication_date: 20120824
---
This application claims the benefit of U.S. Provisional Patent Application Ser. No. 61 527 145 filed on Aug. 25 2011 and Singapore Provisional Patent Application Serial No. 201108719 4 filed on Nov. 24 2011 both applications are incorporated herein by reference in their entirety.

The present invention relates to a system and method for provisioning Internet access to a computing device. The system and method are particularly suited but not limited to providing internet access to a mobile device and personal computers enabled with USB dongles and will be described in this context.

The following discussion of the background to the invention is intended to facilitate an understanding of the present invention only. It should be appreciated that the discussion is not an acknowledgement or admission that any of the material referred to was published known or part of the common general knowledge of the person skilled in the art in any jurisdiction as at the priority date of the invention.

Mobile phones have recently surpassed the conventional desktop or laptop PCs as a popular means for people to connect to the internet. This in part has been fueled by social networks and mobile software applications. The main advantage of mobile phones is in their ability to be connected to the Internet wherever the user is. Mobile phone users may receive and or respond to Instant messaging messages Facebook tags Tweets surf the Internet via a mobile web browser instantly wherever the users are as long as data connection GSM GPRS 3G Wi Fi etc. can be established.

The above advantages complement markets where a majority of telecommunication carrier subscribers prefer mobile data post paid plans. Subscribers of these post paid plans generally do not mind paying more per month to have unlimited Internet data access or a data usage capped at a relatively larger size for example 12 Gigabytes GB .

Another recent phenomenon is the use of broadband dongles USB powered devices that allow computing devices such as Personal Computers laptops to connect to the Internet using the mobile network operator MNO networks 3G 4G etc. 

However providing always on Internet or data connection for smartphones and dongle powered PCs has remained a challenge for telecommunications carriers in markets dominated by users who prefer prepaid plans or pay as you go plans . Users under these prepaid plans are less willing to pay a relatively larger subscription fee for full unlimited internet access. A typical prepaid plan is based on a pay per specified time model such as for example 10 pesos for 30 minutes of fast Internet connection i.e. at maximum bandwidth as provided by the mobile network carrier . Another variation to the pay per specified time model may be a daily always on access to only social networking sites such as Facebook or Twitter for 20 pesos per day.

The above mentioned prepaid pay per specified time plans do not offer enough flexibility to subscribers. For example many users may be interested in visiting certain websites or URLs but not others. Further certain telecommunications carriers may be able to provide certain services such as URLs or APIs free of charge to their subscribers without the need to pay for Internet access or providing free of charge certain mobile applications or apps without the need to pay for downloading such mobile applications. Subscribers to such telecommunications carriers may be only interested in these specific mobile applications URLs or APIs without the need for general Internet access but at present there is no system or mechanism to allow flexibility to toggle between a paid and free Internet access service.

As prepaid plan subscribers are sensitive to cost another challenge for telecommunications carriers is to deliver Internet connection at relatively lower sachet price points such as below 20 pesos daily while still providing prepaid plan users with always on experience. While this may be possible for certain phones which are efficient in terms of consuming data bandwidth such as feature phones or a Blackberry for example it is typically difficult to implement such sachet price points for more recent smartphones models which require relatively higher data bandwidth because to do so may be unprofitable for mobile network operators MNOs or telecommunications carrier. MNOs typically have relatively limited Internet bandwidth as compared to full Internet service providers. From the perspective of the MNOs the relevant question for implementing sachet price points for smartphone models would be What kind of Internet service can be offered profitably at 5 peso or approximately US 10 cents per day to capture the markets of these smartphone users 

Along the same line of cost consideration for prepaid plan subscribers a fixed cost per unit time e.g. 10 pesos per 30 minutes plan may be deemed relatively more expensive for a user with Internet access outside an area with high network coverage e.g. metro areas compared to a user within the metro area. A prepaid plan subscriber outside the metro area requires more time to download a file or carry out certain actions such as video streaming compared to a subscriber within the metro area. This is due to the relative less dense network coverage in non metro areas. In such cases a user may be unduly penalized with a pay per specified time plan.

In light of the above there also exists a need for different charging plans and billing mechanisms that caters to pre paid subscribers depending on the location of the subscriber.

The present invention seeks to address the above mentioned concerns and provide a system and method that alleviates the above mentioned drawbacks at least in part.

It is to be appreciated that free access in the context of access to web resources including URLs APIs or other websites IP addresses refer to toll free always on data access i.e. access to these URLs APIs websites IP addresses would be free to the user as provided by a telecommunications carrier. Such always on data access is to be distinguished from any subsequent actions to retrieve input or manipulate data including downloading of videos audio files for example. Actions to retrieve input or manipulate data may be chargeable although the access to the data itself may be toll free.

In addition free access in the context of access to mobile applications apps refers to downloading such apps but usage of such apps to download view stream or perform other functions may be chargeable.

It is further to be appreciated that Internet access in the context of the description generally refers to mobile data Internet service such as GPRS Enhanced Data rates for GSM Evolution EDGE 3G LTE 4G network Wi Fi tethering etc. unless otherwise stated.

In accordance with a first aspect of the present invention there is provided a system for provisioning Internet access to a computing device comprising an Internet access adjustment facilitator arranged to receive a request from the computing device for adjusting Internet access from a paid Internet access mode to a toll free Internet access mode and a whitelist in communication with the Internet access adjustment facilitator the white list maintaining a list of web resources available for toll free access by the computing device wherein upon successful processing of the request the list of web resources are toll free for access by the computing device.

Preferably any subsequent action to retrieve input or manipulate data in the toll free Internet access mode is chargeable. Ideally each subsequent action to retrieve input or manipulate data is charged or billed based on a pay per action model. Alternatively each subsequent action to retrieve input or manipulate data is charged or billed based on a flat fee for a defined set of subsequent actions.

Preferably in the toll free Internet access mode the comprising device is not allowed to access any web resources not within the whitelist.

Preferably the request for adjusting Internet access is a Short Messaging Service SMS message electronic text message or Unstructured Supplementary Service Data USSD message.

Preferably the system further comprises a subscriber database arranged to maintain details of a plurality of subscribers and an accounting database arranged to be in data communication with the subscriber database for settlement and checking of available funds for each subscriber and maintaining a history of transaction of each subscriber.

Preferably the mobile device is arranged to send the request automatically to the Internet access adjustment facilitator based on a priority based algorithm that typically ranks higher quality or more open plan or faster user subscriber plan higher in priority. More preferably the pay per action model is activated by sending a request from the mobile device to the Internet access adjustment facilitator the Internet access adjustment facilitator operable to upon receiving the request toggle between an existing billing infrastructure which implements a pay per specific time model and an independent billing module implementing the pay per action model.

Preferably the toggle from the existing billing infrastructure to the independent billing module is achieved either by switching off the existing billing infrastructure or defining the data bandwidth connection as a zero tariff.

In accordance with a second aspect of the present invention there is provided a method for provisioning internet access to a computing device comprising the following steps receiving at an Internet access adjustment facilitator from the computing device a request to adjust Internet access from a paid Internet access mode to a toll free Internet access mode processing the request to adjust Internet access and upon successful processing adjusting the Internet access to the computing device wherein in the toll free Internet access mode web resources within a whitelist are toll free for access by the computing device.

Preferably any subsequent action to retrieve input or manipulate data in the toll free Internet access mode is chargeable. More preferably the each subsequent action to retrieve input or manipulate data is charged or billed based on a pay per action model. Alternatively the each subsequent action to retrieve input or manipulate data is charged or billed based on a flat fee for a defined set of subsequent actions.

Preferably in the toll free Internet access mode the computing device is not allowed to access any web resources not within the whitelist.

Preferably the request for adjusting Internet access is a Short Messaging Service SMS message electronic text message or Unstructured Supplementary Service Data USSD message.

Preferably the Internet access adjustment facilitator is in data communication with a subscriber database arranged to maintain details of a plurality of subscribers and an accounting database arranged to be in data communication with the subscriber database for settlement and checking of available funds for each subscriber and maintaining a history of transaction of each subscriber.

Preferably the computing device is arranged to send the request automatically to the Internet access adjustment facilitator based on a priority based algorithm that typically ranks higher quality or more open plan or faster user subscriber plan higher in priority.

Preferably the pay per action model is activated by sending a request from the computing device to the Internet access adjustment facilitator the Internet access adjustment facilitator operable to upon receiving the request toggle between an existing billing infrastructure which implements pay per specific time model and an independent billing module implementing the pay per action model. More preferably the toggling from the existing billing infrastructure to the independent billing module is achieved either by switching off the existing billing infrastructure or defining the data bandwidth connection as a zero tariff.

In accordance with a third aspect of the present invention there is a mobile device containing software instructions wherein upon execution of the software instructions performs the method according to any of the second aspect of the invention toad just the Internet access from a paid Internet access mode to a toll free Internet access mode.

Preferably where the method comprises an additional step of billing for the bandwidth consumed based on either a pay per specific time model or pay per action model wherein the pay per specific time model or pay per action model is activated by sending a request from the mobile device to the Internet access adjustment facilitator the Internet access adjustment facilitator operable to upon receiving the request toggle between an existing billing infrastructure implementing the pay per specific time model and an independent billing module implementing the pay per action model.

Other arrangements of the invention are possible and consequently the accompanying drawings are not to be understood as superseding the generality of the preceding description of the invention.

In accordance with an embodiment of the present invention there is a system for provisioning Internet access from a host to at least one computing device . The system comprises an Internet access adjustment facilitator and a whitelist in data communication with the Internet access adjustment facilitator .

The computing device may preferably be a mobile phone. More preferably the computing device is a smartphone capable of the installation of mobile software application or app . The computing device is connectable to the Internet via various mobile data services such as GPRS Enhanced Data rates for GSM Evolution EDGE 3G Wi Fi LTE 4G network etc.

Alternatively the computing device may be a personal computer laptop comprising a USB wireless adapter such as a dongle for plugging into a personal computer desktop or laptop to access the system and the Internet adjustment facilitator . Such an arrangement allows the personal computer laptop to access the telecommunications network s GPRS Enhanced Data rates for GSM Evolution EDGE 3G Wi Fi LTE 4G network etc.

The Internet access adjustment facilitator is adapted to process requests from the user of computing device to the telecommunications network for the control of Internet access. In this sense the Internet access adjustment facilitator is within a proxy server for connecting to the Internet. The requests are typically in the form of an electronic signal message wherein a software application is installed on the mobile device or personal computer PC for such a purpose. Other means of communicating with the adjustment facilitator may be in the form of a simple text or Short Messaging Service SMS Unstructured Supplementary Service Data USSD messages or other similar messaging service.

The system optionally comprises a subscriber database . The subscriber database maintains details of the subscribers of telecommunications network such as the Mobile Subscriber Integrated Services Digital Network Number MSISDN of each subscriber mobile phone and whether the subscriber is on any prepaid post paid plans as well as the details of the plans such as the expiry of the prepaid plan if applicable . The subscriber database is in data communication with an accounting database for the settlement and checking of available funds for the subscriber for computing device . The accounting database further maintains a history of transaction of each subscriber.

In the case where the mobile Internet service is a GPRS service for example the Internet access adjustment facilitator is typically located between the Gateway GPRS Support Node GGSN and the Service Aware Support Node SASN of the GPRS core network.

The whitelist is in data communication with Internet access adjustment facilitator. The whitelist maintains a list of web resources comprising URLs and APIs and other web services as approved by telecommunications carrier . These approved URLs and APIs are considered toll free i.e. available for free access by the computing device or free to be accessed by a user as far as charging billing based on the data network of the telecommunications network is concerned. Whitelist is in data communication with Internet access adjustment facilitator.

The computing device is preferably installed with a dedicated mobile software application depending on the particular model of the computing device . For a typical smartphone such as an iPhone or Android this may be an app as colloquially known. For ease of reference the dedicated mobile software application will be interchangeably known as Safe Browsing App .

Prior to use the computing device is checked if it is registered as a subscriber of the system via checks on the MSISDN of the computing device or other methods as well known to a skilled person. For the case where the computing device is a personal computer or laptop that connects to the Internet via a dongle the dongle typically comprise a subscriber identity module SIM card within the same the SIM card having a MSISDN. If the computing device is not a subscriber the user of a computing device may optionally be prompted a message through the Safe Browsing App to register or choose from any set of services or the telecommunications network operator or mobile network operator MNO may have dedicated APNs for the purpose of carrying out the present invention and requires the user of the computing device to change the Access Point Name APN of the mobile device. The user may for example get a text message or a notification on his app asking him to make this change.

Alternatively the subscriber does not have to be prompted to change the APN explicitly. The MNO may employ an intelligent APN provisioning system that enables automatic connection in the background to the Internet.

The installed software application Safe Browsing Apps may be manually activated by the user of computing device wherein the installed application opens a user interface providing the option to adjust internet access type as desired or may include detecting the data usage profile of the subscriber for computing device . The data usage profile details any existing data plan package which the subscriber is currently on.

The Safe Browsing Application also provides the user interface for the user of computing device to toggle control of his internet access between a paid Internet access and a toll free Internet access. Examples of these two Internet access are as described in the two modes as follows 

a full access mode Paid Internet access mode full access to the Internet provided by MNO telecommunications carrier at maximum speeds available. For example 3G 4G networks at 10 peso for 30 minutes or a discounted rate for slower speeds such as EDGE or GPRS.

a limited access mode Toll free Internet access mode restricted to certain mobile data services including certain websites URLs Application Programming Interfaces APIs and IP addresses as maintained by the whitelist Access to these services as listed in whitelist will not incur any mobile data charges to the subscriber. Sites URLs APIs and or services outside of this whitelist are however non accessible to the user in this mode.

A third default mode upon detection by the system to be on an existing data plan such as a 10 pesos for 30 minutes fast internet access the default mode overrides any other modes until the expiration of the data plan.

The Safe Browsing App may be pre installed or downloadable. The App may be a software widget which includes an graphical representation of an on off switch on the user interface of computing device allowing the user of computing device to toggle between the full access ON mode and the limited access OFF mode. Upon clicking sliding the On toggle the user sends a request for full access and the clicking sliding of the off toggle sends a request for limited access mode. The default mode is typically not presented as an option to the user of computing device and will automatically kick once detected that an existing data plan is available.

Further details on the user adjustable full access and limited access modes and their functionality as well as its operation under various computing devices including smartphones and legacy non smartphones are described as follows 

There are a number of possible ways for subscribers to switch between the full access and limited access modes. For example the user may download the safe browsing app widget send a SMS to the Internet access adjustment facilitator or via access of a mobile web browser WebConnect .

Users who subscribe to a data plan data Package activates the default mode automatically to override whatever mode he is currently at.

If the user has downloaded the safe browsing app widget a set of console rules governs the interaction between the user subscriber and the widget depending on the type of computing device .

If the computing device is a smartphone specifically developed for the telecommunications carrier hereinafter known as a netphone after the initial user registration process the widget will be set to the limited access OFF mode which is the default setting.

Interaction with the Safe Browsing App via for example tapping or sliding the User interface provided on the App widget will toggle the OFF mode to the unlimited access ON mode. A prompt will appear and inform the user that by switching modes mobile Internet will be activated and the subscriber will be charged the prevailing rate e.g. P10 for 30 minutes . If the subscriber wishes to switch to the OFF mode he may simply interact with the widget again as mentioned above. The subscriber may be prompted a message along the lines of 

If the computing device is any other smartphone which is not specifically developed for the telecommunications carrier upon installation of the safe browsing app widget the widget will by default be set to the full access ON mode instead of the OFF mode as described above. Interaction with the Widget will toggle from the ON mode to OFF mode and vice versa.

If the computing device is any other legacy phones i.e. non Smartphones capable of accessing the internet and installing the widget the default setting is the ON mode. The installed widget is capable of detecting the current state of the computing device data and APN setting. If detected that the mobile device s data internet setting is disabled the installed widget will display the status of the computing device as disabled. If the subscriber interacts with the widget for example via tapping the screen of the mobile device to enable the Device s Data access and prompts the subscriber that the device Data access is enabled. The widget will then send a request to the Internet access adjustment facilitator to switch to limited access MODE. Upon tapping the widget again will send another request to switch to the full access mode and enable all Mobile Data to pass through the Network.

As an alternative to installing the software widget the subscriber may choose to switch between the full access and limited access modes via SMS. Switching via SMS may be performed by any phone via console rules as follows 

The subscriber sends an SMS comprising an Access Code password and the desired mode. The Internet access adjustment facilitator responds with an SMS stating the current mode and a confirmation to proceed with the change. The subscriber then sends a confirmation SMS. Upon switching mode the Internet access adjustment facilitator will send a confirmation of the switch in mode.

The subscriber may switch mode on a mobile internet browser. The console rules governing the switch mode via web connect is as follows.

The subscriber of mobile device accesses web connect and logs in for example using his user ID and password. Upon logging in the web browser displays the current mode of the computing device . In the absence of any subscriber plan the default mode is the unlimited access mode. The subscriber is then allowed to change the mode. An SMS will be sent to the subscriber on first use of the switch mode service.

For roaming subscribers in the absence of any data package plan the full access mode is applicable so as not to disrupt any data service. However a prompt SMS may be sent to the roaming subscriber to advise him to disable data roaming on his mobile device so as not to incur additional roaming cost.

Should a user subscriber wish to buy a data subscription plan package the console rules are defined as follows 

For a Netphone the subscriber accesses the Subscription application available to netphone selects a Package and taps on BUY option. Upon confirmation the Internet Widget will automatically toggle to ON full access mode without further input required from the subscriber. A prompt will be displayed to the subscriber indicating that the Widget has been set to ON and that all Mobile Data use is ACTIVE.

On other Smartphone the subscriber may be availed a Package via SMS or mobile web browser. Upon confirmation the Internet Widget will automatically toggle to the ON MODE. A prompt will be displayed to the subscriber indicating that the Widget has been set to ON and that all Mobile Data use is ACTIVE.

For other legacy Phones the subscriber may be availed of a Package via SMS or mobile web browser. The Internet ON OFF service will automatically toggle to ON MODE. An SMS will then be sent to the subscriber confirming the Package and indicating that the Internet ON OFF service has been set to ON and that all Mobile Data use is now ACTIVE.

It is to be appreciated that the Internet access adjustment facilitator may further include steps to verify the MSISDN of the computing device is in the subscriber database . Further steps such as password authentication SMS verification or other forms of authentication may also be performed as known to a person skilled in the art to authenticate the subscriber.

It is further appreciated that once any request to switch mode is successfully verified the Internet access adjustment facilitator proceeds to adjust the internet access for the subscriber of computing device . This is based on the whitelist as maintained by the telecommunications carrier .

The described system and method further allows the user to stop or pause the limited access as and when desired and thus better able to control the part of his remaining credit of the pre paid plan.

In the case where the computing device is a personal computer laptop having a dongle the user interface may be an Internet browser that is able to be connected to the whitelist for accessing the toll free services. In the case where the Internet browser is for example Google chrome accessed to Google chrome based applications are typically whitelisted for toll free connection. Another user interface can be a program downloaded and installed on a personal computer laptop as has been the typical case.

In accordance with another embodiment of the present invention as illustrated in wherein like numerals reference like parts there is a system for provisioning Internet access from a telecommunications carrier to at least one computing device . The system comprises an Internet access adjustment facilitator a subscriber database and a whitelist in data communication with the Internet access adjustment facilitator . The system further comprises an independent billing charging module . The billing module is an independent separate value added billing module based on the mechanism of per action charging .

Independent billing module is operable to be in data communication with the subscriber database and accounting database . Independent billing module is arranged to provide a per action charging mechanism for charging billing a subscriber for his Internet bandwidth usage. The independent billing module is advantageous because it does not require modifications to the existing billing charging structure database and may be implemented as a convenient add on to the existing resources.

 Per action charging is a charging model based on an action taken by the subscriber. Examples of such action s are defined as follows 

In the context of the embodiment other actions which may fall within the definition of per action charging may include per click within dedicated smartphone App per click within web browser etc.

 Per action charging offer additional choice for a pre paid subscriber as it allows the pre paid subscriber to choose from the conventional pay per specified time model pay per specified time mode such as 10 pesos for 30 minutes of Internet connection and or the daily always on access to only social networking sites such as Facebook or Twitter for 20 pesos daily to the per action charging model depending on his preference such as time location and or usage.

In this embodiment the previously discussed Safe Browse App may include an additional function which allows a subscriber of computing device to toggle between the pay per specified action charging billing models to the per action charging charging billing model. Alternatively the billing charging function may be implemented as another dedicated software application or App known as the Flexible Billing App.

The request for switching to per action charging is in the form of simple text or Short Messaging Service SMS Unstructured Supplementary Service Data USSD messages or any other form of an electronic signal message wherein a software application is installed on the mobile device for such a purpose.

The embodiment with emphasis on the usage of the billing module for charging billing a subscriber s data bandwidth usage will next be described in the context of its use.

Upon detection that per action charging is to be adopted via a request from the user of computing device the Internet access adjustment facilitator switches from the existing billing infrastructure of the telecommunications carrier to the billing module . This may be achieved by either 

The billing module then takes over the billing charging based on per action charging once detected that the computing device is in the limited access mode as previously discussed in the previous embodiment. In particular for the limited access mode as discussed the following charging methods shall apply charge per action on a specific App or a browser within the whitelist 

A flat charge for a continuous Internet connection for specific Apps or set of web resources URLs or IP addresses for subsequent actions for the APIs URLs within the whitelist i.e. initial access to these web resources within the whitelist is free but subsequent actions are billable .

If the user chooses to exercise the option of charge per action mode while on Limited Access a simplified flat nominal charge per action tariff may be charged. Such action includes updating one s Facebook s status downloading and streaming a YouTube video etc. If the user chooses the FLAT CHARGE for continuous streaming while on Limited Access that charge will be applied turning on Internet connection only for the specified apps URLs IP addresses and overriding Full Access mode if the user has been on the limited access mode.

The billing module is complementary with the flexible provision of Internet access. In particular when a request is sent to the Internet access adjustment facilitator to adjust the from the full access mode to limited access mode in conjunction with the request to bill based on per action charging the subscriber of computing device gains more control of the type of charging billing applicable depending on where he she may be at. For example at a non metro area with less dense network coverage the user has the flexibility to turn on the limited access mode and make use of the whitelist to access web resources at no charges and be charged at per action charging for any subsequent actions taken.

The system may be suited to incorporate other permutations and combinations of usage. In particular the billing module may include differential pricing for accessing certain websites URLs Application Programming Interfaces APIs and IP addresses. Access to these mobile services will not incur any mobile data charges to the subscriber or will be at a discounted rate.

For the full access mode the operational speeds may be detected via a speed monitoring application installed on the computing device . This is preferably integrated with the Flexible Billing App. By using test data packets similar to concept of a PING the operational speed of the computing device may be estimated and charged based on the 3G 4G high speed or possibly at a discounted rate for lower speed.

For the limited access mode in addition to the charge per action billing method a flat fee for a defined set of apps method or some combination of both may be adopted.

As an alternative to manual switching by a user subscriber an automatic method for switching from one mode to another may be provided. The automatic method is a priority based algorithm that typically ranks higher quality or more open plan or faster plan higher in priority unless otherwise switched manually by the user. For example if the user is subscribed to a data plan that translates to a full Access mode as described any limited access mode purchased is override.

The priority based algorithm of the automatic method means that once the Full Access mode subscription has expired say the full 30 minutes in a 10 peso for 30 minutes plan the user will be automatically switched to Limited Access mode.

In the case where the computing device is a personal computer laptop these modes may be presented as a form of notification anywhere within a relatively larger desktop laptop screen area. Clicking on such notification will take the subscriber to a Settings Area. The Settings indicate among others the mode that the user is currently on and the remaining balance information. The remaining balance would be either shown in terms of currently e.g. Pesos or time elapsed and time remaining. In the Settings section the subscriber may also choose to switch manually from one mode of connection to another.

The Flexible Billing App may be a feature which may be integrated as an integral module with the Safe Browsing App or any other Apps. In the case of it being a separate App it may take the form of a software widget which includes an graphical representation of an on off switch such that when in the on position it indicates which mode of connection is active balance information and a graphical lever that allows the subscriber to switch manually to a specific modes. Upon selecting a particular mode of connection the Flexible Billing App sends a request to the Internet access adjustment facilitator for instructions to adjust the same.

It is to be appreciated that charge per action may include the following Per click within app or per click within web browser and per click within program Per app running always on for specified period and or per set of apps running always on for specified period .

Alternatively the request may be sent as an SMS access code required USSD command or via the world wide web www .

The Internet access adjustment facilitator may further comprise a bandwidth throttler not shown to process requests from the user of computing device to the telecommunications network for the adjustment of data bandwidth between a trickle mode i.e. 9.6 kbps to 14.4 kbps and a boost mode 2 Mbps onwards if on 3G for example on demand. The Boost mode provides the user interface via the Safe Browse and or Flexible billing app for the user of computing device to toggle control of his data speed between the trickle mode i.e. 9.6 kbps to 14.4 kbps and the boost mode 2 Mbps onwards if on 3G for example on demand. For the subscriber having a pre paid contract or plan the default mode for the data speed is the trickle mode.

In such an instance a boost mode may be included in the system and the charge bill per action plan may be applied to the boost mode.

Upon selecting the option Boost on the user interface the request to change the data speed from trickle to 3G 4G is sent to the Internet access adjustment facilitator . The Internet access adjustment facilitator proceeds to verify if the MSISDN of the computing device is in the subscriber database . Further steps such as password authentication SMS verification may also be performed as known to a person skilled in the art to authenticate the subscriber.

Once the request is successfully verified the Internet access adjustment facilitator checks the accounting database to make sure that the subscriber has enough funds to pay for the boost .

Upon determining that there are enough funds in the subscriber pre paid account or pre paid card the Internet access adjustment facilitator proceeds to adjust the bandwidth settings for the subscriber of computing device . This is done via a bandwidth throttler which either caps the data speed of connection between the computing device to the internet or allows any excess available data bandwidth to the computing device by the Internet access adjustment facilitator .

The Internet access adjustment facilitator may include a detecting algorithm for detecting the usage profile of the subscriber for computing device .

It is to be appreciated that while the full access and Limited access modes are mutually exclusive the Limited access mode can operate simultaneously while on the Boost mode.

As an example in the combination of Boost with Limited access mode fast Internet access may advantageously be achieved for the selected whitelisted services at no cost for the user while slower for all others not on the White List. If Facebook is on the whitelist this means that the subscriber could enjoy a full fast Facebook experience this will not be the case for non whitelisted Apps. These non whitelisted apps will operate at trickle speeds. Nonetheless for notifications or when a new email is received or an IM message is sent the Boost mode running on trickling mode for non whitelisted Apps may be adequate.

It is to be understood that the above embodiments have been provided only by way of exemplification of this invention and that further modifications and improvements thereto as would be apparent to persons skilled in the relevant art are deemed to fall within the broad scope and ambit of the present invention described herein. In particular features from one or more embodiments may be combined to form further embodiments.

