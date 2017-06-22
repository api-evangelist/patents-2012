---

title: Ordering method and system for restaurants
abstract: A method of ordering menu items for delivery to a station at a premises, such as a table at a restaurant, includes the steps: Launch App; Scan QR code or NFC tag on table; Identify location. The location is identified using the restaurant and table identifier(s) extracted from the QR code. This location is used to identify the correct restaurant menu from the central platform database; Download menu; Add menu items to order; Confirm order; Pay order; Route order. The restaurant identifier is used to determine the appropriate EPOS adaptor based on the EPOS system in use by the specific restaurant; Transmit to restaurant. The correct communication protocol and authentication details are then used in order to route the order to the restaurant EPOS system or printer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09117231&OS=09117231&RS=09117231
owner: QIKSERVE LIMITED
number: 09117231
owner_city: 
owner_country: GB
publication_date: 20120913
---
The present application claims priority to U.S. Provisional Application No. 61 590 496 filed on Jan. 25 2012 which is incorporated herein by reference in its entirety.

The present disclosure relates to methods and systems for ordering menu items for delivery to stations at premises such as tables at restaurants and relates to tags such as with QR codes for use in such methods.

Fast casual restaurants traditionally have not benefited from customer self service efficiencies that other industries have achieved. Fast casual restaurants operate a number of service models including waited service counter service and semi counter service. Waited service means that waiters provide service to customers at their table. This is convenient for the customer but labour costs are typically 30 of the restaurant overheads. Counter service is where a customer orders from a counter and waits to collect the food and drink. This is cost effective to run but inconvenient for the customer. Semi counter service where a customer selects a table chooses from a menu and then places an order at the counter or bar giving the table number are almost as cost effective to run but are inconvenient for the customer. The customer must leave the table and queue at the bar to place an order. This can be very difficult when supervising young children or with valuables such as a handbag or laptop computer etc. It may be necessary to take the children or valuables to the bar and risk losing the table to other diners. In group situations it is also necessary to remember a large order and it causes social disruption when someone has to leave the group to go to the bar.

Mobile Apps applications currently exist for placing orders with takeaway restaurants for delivery or collection. These typically use the GPS Global Positioning System on the mobile device to identify the user s location and present a list of local takeaway restaurants. Orders are then sent electronically to the restaurant for collection or delivery.

This solution is not suitable for an in restaurant ordering system as GPS does not work indoors and so an alternative approach is desirable for locating the customer.

These takeaway ordering systems also transmit the order to the restaurant in a standardized way and there is a problem of routing the order to the appropriate restaurant EPOS system using the required protocol and network.

QR Quick Response codes are commonly used to store web page URLs Uniform Resource Locators which direct the mobile phone browser to a pre determined web page. However this is a fixed URL and does not allow for the identification of a particular location.

According to a first aspect of the present disclosure there is provided a method of ordering menu items for delivery to a station at a premises using a processor the method comprising the steps 

 a receiving a station input the station input comprising a station identifier and a premises identifier together identifying the station at the premises 

 d receiving an order input the order input indicating a selection of at least one of the output menu items and

 e the processor causing transmission of an order to the premises identified by the input premises identifier the order including the station identifier and the selection of the output menu items.

The station input may be received by a processor reading a QR code comprising the encoded station and premises identifiers.

The station input may be received by a processor reading a transmission from an electronic tag at the station.

The transmission from the electronic tag may comprise the station identifier and the premises identifier.

The method may further comprise the step of receiving a third input the third input indicating placing the order for the selection of the output menu items.

The method may further comprise the step of selecting an EPOS adapter based on the premises identifier and wherein the processor causes transmission of the order to the premises using the selected EPOS adapter.

The method may further comprise the step of selecting a communication protocol based on the premises identifier and wherein the processor causes transmission of the order to the premises using the selected communication protocol.

The method may further comprise the step of selecting a communication network based on the premises identifier and the processor causes transmission of the order to the premises using the selected communication network.

According to a second aspect of the present disclosure there is provided a method of delivering products to a station at a premises the method comprising ordering menu items in accordance with the method of the first aspect and delivering to the station at the premises at least one product corresponding to the selection of the output menu items.

According to a third aspect of the present disclosure there is provided a computer program product one or more sequences of machine readable instructions for use in ordering menu items for delivery to a station at a premises the instructions being adapted to 

first computer readable program code for causing at least one computer to receive a station input the station input comprising a station identifier and a premises identifier together identifying the station at the premises 

cause at least one computer to receive an order input the order input indicating a selection of at least one of the output menu items and

cause at least one computer to cause transmission of an order to the premises identified by the input premises identifier the order including the station identifier and the selection of the output menu items.

According to a fourth aspect of the present disclosure there is provided a tag for use in ordering menu items for delivery to a station at a premises using a processor the tag comprising a station identifier and a premises identifier identifying the station at the premises.

The tag such as a label may comprise a barcode encoding the station identifier and the premises identifier.

The tag may comprise an electronic tag operable to transmit the station identifier and the premises identifier.

According to a fifth aspect of the present disclosure there is provided a substrate patterned with a QR code comprising a patterned region comprising QR encoded station and premises identifiers.

According to a sixth aspect of the present disclosure there is provided a system for ordering menu items for delivery to a station at a premises the system comprising 

 a receive a station input the station input comprising a station identifier and a premises identifier together identifying the station at the premises 

 d receive an order input the order input indicating a selection of at least one of the output menu items 

and the system further comprising a server remote from the premises operable to cause transmission of an order to the premises identified by the input premises identifier the order including the station identifier and the selection of the output menu items.

According to a seventh aspect of the present disclosure there is provided a computer program product comprising one or more sequences of machine readable instructions for use in accordance with the method of the first aspect the instructions being adapted to cause at least one computer to cause transmission of the order to the premises identified by the input premises identifier the order including the station identifier and the selection of the output menu items.

Embodiments enable a customer to order using their mobile phone. In an embodiment the customer uses a downloaded smartphone application App and checks in by using the App to scan a QR Quick Response code on the table using the smartphone camera.

The QR code contains the table location information namely the restaurant identifier and table number identifier.

In an embodiment the appropriate menu for that particular restaurant and time of day is automatically identified and downloaded to the smartphone. For example a breakfast menu may be presented between the hours of 6 am and 11 am. Individual restaurants may also have particular specials on offer.

In an embodiment the user can choose individual categories such as Starters Mains Desserts Drinks etc. Within the category the relevant individual menu items are shown. The user can then add items to the order along with special instructions etc.

In an embodiment the user can review the order before paying with one of the normal methods such as a credit card. The payment details may be stored for convenience during subsequent use of the App.

In an embodiment the order is automatically sent to the restaurant kitchen. This can be done in a number of ways such as printing to a remote printer or via integration with the existing restaurant EPOS Electronic Point of Sale system.

Along with the QR code other information including the restaurant and table identifiers may be printed in human readable form.

Scanning a QR code is much more convenient and accurate than keying in restaurant and table identifiers. Consumers are now becoming more familiar with scanning QR codes to access online information. A QR code is commonly used on advertising material such as in magazines to access further information on the product. These QR codes contain the URL to access the relevant online web page.

The user can be identified using a unique identifier from the mobile device itself or through storing login credentials.

The App may be conveniently available for major smartphone operating systems including Apple iOS Android Blackberry and Windows Phone . The App may be installed on the smartphone by downloading from one of the App stores such as the Apple Appstore Google Play etc.

Installing a dedicated system in every restaurant would be a simple approach as the issue of identifying the restaurant menu and EPOS system is not a problem. The App would however need to connect to the local system perhaps over a WiFi network. This would require setting up the appropriate authentication and security information and would be difficult for a typical end user to achieve. Installing a dedicated system for each restaurant would also be costly to install and maintain.

In order to address these issues an embodiment is provided as a hosted service where the smartphone App connects to a platform over the internet and the order is delivered by the system to the appropriate restaurant s EPOS system or kitchen printer. This enables a scalable solution where it is not necessary to install a dedicated system for every restaurant.

In an embodiment a database stores the restaurant customer order and payment information. The remote EPOS system or printer connection and authentication information may also be stored.

The restaurant identifier together with the time of day is used to extract the appropriate menu from the database. Payment is achieved by submitting the user s payment card details to a payment gateway. The order is then routed via the appropriate protocol to the appropriate EPOS system.

There are many EPOS system providers including companies such as Radiant Systems Micros Zonal etc. EPOS providers support varying types of protocols for connection to those systems. The communication protocols are proprietary and interface methods used range from web service interfaces down to TTY protocols. Web service interfaces may use SOAP Simple Object Access Protocol or REST Representative State Transfer technologies and use http over internet protocol IP as the underlying communication method.

Remote connection to an EPOS system uses a secure wide area network WAN . The WAN type may be a dedicated line dial up modem or broadband connection. For security over the internet a VPN Virtual Private Network connection is often used.

In an embodiment the restaurant identifier is used to determine the appropriate EPOS adaptor based on the EPOS system in use by the specific restaurant. The correct communication protocol and authentication details are then used in order to route the order to the restaurant EPOS system or printer.

An item selection screen is also shown schematically in this case for appetizers as displayed on the display of the smartphone by the App. The item selection screen has a navigation area and an item selection area with pairs of item display fields for description and price each pair accompanied by a quantity control for the user to input a quantity of each item for the order. In this example the items are soup of the day cheesy nachos stuffed mushrooms or Caesar salad. A back to menu button is also provided by the App to allow the user to return to the category selection screen . A message area is again provided for example for a message and or logo of the restaurant.

The smartphone App is launched to begin the process. The App may previously have been downloaded and installed from one of the App stores such as Apple Android etc. A unique identifier for the customer may be provided by the device.

The App may use an embedded QR code scanner to control the camera and scan the QR code on the table. The restaurant and table identifiers are extracted from the QR code. Alternatively the restaurant id and table id can be keyed in manually.

An alternative to the QR code and QR code scanner is to use an NFC Near Field Communication tag on the table and NFC reader where present in the smartphone. In this case the location data is extracted by swiping the phone over the tag.

The location is identified using the restaurant and table identifier s extracted from the QR code. This location is used to identify the correct restaurant menu from the central platform database. The platform is accessed from the App on the smartphone by calling web services over the mobile data network. The mobile data network can be delivered using various over the air technologies including GPRS General Packet Radio Service 3G 3rd generation mobile telecommunications LTE Long Term Evolution 4G 4th generation mobile telecommunications WiFi.

The appropriate menu is downloaded over the air to the smartphone and the menu items are output to the smartphone display. The menu may be dependent on the restaurant location and the time of day.

The user interacts with the digital menu in the App to select items from the menu. Items selected are added to the order. This step may be repeated as indicated by the dashed line.

The user may pay the waiter directly. The user can use a pre stored credit or debit card to pay for the order. Additional cards can be added. Payment card information may be stored in encrypted form in a local database on the device or in a mobile wallet. Alternatively the payment card information can be stored centrally and accessed using the unique customer identifier. Where payment details are stored in other accounts such as social network accounts including Facebook Twitter Google etc. the existing payment information can be accessed by signing in to the account. Payment systems such as Paypal may also be used.

The restaurant identifier is used to determine and select the appropriate EPOS adaptor based on the EPOS system in use by the specific restaurant. The restaurant identifier is used to determine and select the appropriate communication protocol and communication network.

The correct communication protocol and authentication details are then used in order to route the order to the restaurant EPOS system or printer.

The user has the ability to sign in to their existing social network accounts and record a review of the service.

In some embodiments the menu may be retrieved before the station e.g. table is known for example while the customer is waiting to be seated or before the customer arrives at the premises. In such a case steps and of downloading and adding menu items to the order may be initiated by for example scanning a QR code encoding or otherwise associated with the restaurant identifier or for example clicking on a web link associated with the restaurant identifier. When the QR code on the table is subsequently scanned and a matching restaurant identifier is obtained the pre assembled order has the table number from the scanned QR code added to it and step of confirming the order may be performed.

With reference to the Smartphone has an App stored in its memory. The App may be downloaded and installed on the smartphone . When the one or more sequences of machine readable program instructions of the App are loaded into the CPU Central Processing Unit of the smartphone the CPU executes the program instructions of the App. This causes the processor to execute the steps to of . The QR code reader may be an embedded component within the App which accesses the camera . The App accesses the database . The App accesses the central platform via web services over a mobile data network for example using Hypertext Transfer Protocol Secure HTTPS .

The App may also be implemented as a mobile web application rather than an application downloaded and running on the device.

The database on the smartphone stores information such as the payment card details. Such information can be stored securely using techniques such as data encryption. Menu information downloaded from the platform database may be cached locally on the smartphone for performance reasons. In this case a check may be made when the application starts up to see if there is more recent menu data to download.

The platform may be hosted centrally and accessed over the internet. There may be a number of components within the platform and these are described below.

The platform implements web services for access by the smartphone App using a web services module . When the one or more sequences of machine readable program instructions of the web services module are loaded into the CPU of the platform the CPU executes the program instructions of the web services module . Web service interfaces may use SOAP or REST technologies and use HTTP over internet protocol IP as the underlying communication method.

The central database stores the restaurant customer order and payment information. The remote EPOS system or printer connection and authentication information is also stored.

The location information extracted from the read QR code may be used to retrieve the relevant EPOS and connection information for the restaurant.

The restaurant identifier may be used by the router module to determine the appropriate EPOS adaptor based on the EPOS system in use by the specific restaurant. The correct communication protocol and authentication details are then determined by the router module and or CPU and used in order to route the order to the restaurant EPOS system or printer. When the program instructions of the router module are loaded into the CPU of the platform the CPU executes the program instructions of the router module . This causes the processor to execute the steps to of .

EPOS providers support varying types of protocols for connection to those systems. The communication protocols are proprietary and interface methods used range from web service interfaces down to TTY protocols. Specific EPOS adaptors may be implemented to support each individual type of EPOS system. The router module identifies the EPOS adaptor to use to deliver the order to a specific restaurant.

With respect to the communication protocol remote connection to an EPOS system may use a secure wide area network WAN . The WAN type may be a dedicated line dial up modem or broadband connection. For security over the internet a VPN Virtual Private Network connection is suitable.

The EPOS System Printer is the instance of an EPOS system deployed in a particular restaurant. As an alternative to integrating with a specific type of EPOS system the order may be sent directly over the internet to a remote printer.

Table 1 shows the table visits V indicates a table visit by a waiter in each of the dining formats full counter service semi counter service and waiter service. Some of these visits can be eliminated through the use of embodiments of the present disclosure denoted by columns headed Embodiment A and Embodiment B. Embodiment B differs from Embodiment A by the customer paying the serving staff waiter directly rather than using the App. The efficiency improvements and therefore cost savings provided by embodiments of the present disclosure may be calculated based on the reduction in table visits or ordering time.

Embodiments provide a process of scanning a QR code to identify the physical location automatically selecting the menu and subsequently routing the order to the correct EPOS system.

Embodiments provide a system which selects the appropriate menu and subsequently routes the order to the EPOS system in the appropriate restaurant using the correct communications protocol all based on the physical location from the QR code.

Scanning a QR code from the App. The QR code contains the physical location restaurant and table identifier .

Rather than a table a station may be another sub location of a premises such as a seat or a location such as a pillar or corner or a point or region defined by coordinate data.

Embodiments of the present disclosure may be used at other fixed point locations such as hotel rooms and stadia e.g. baseball .

QR code can be a URL with encoded identifiers or encode the restaurant and table identifiers directly.

As well as EPOS system or a remote printer the orders could be accessed from a web browser in the kitchen or even sent via email.

The system can also be implemented on other mobile devices such as tablet computers like the Apple iPad or Android tablets.

The mobile device may be provided by the proprietor of the premises such as the restaurant owner with appropriate security measures to prevent or deter theft.

