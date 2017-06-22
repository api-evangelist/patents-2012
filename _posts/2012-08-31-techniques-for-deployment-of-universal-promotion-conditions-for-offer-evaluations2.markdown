---

title: Techniques for deployment of universal promotion conditions for offer evaluations
abstract: Techniques for universal promotion conditions for offer evaluations are provided. Promotions are comprised of promotion conditions. The conditions are defined as a key value, description, and data type. Defined operators for the data types are enumerated and the key values can be mixed and matched in custom defined conditional statements to expand promotional engines with universal promotion conditions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09646316&OS=09646316&RS=09646316
owner: NCR Corporation
number: 09646316
owner_city: Duluth
owner_country: US
publication_date: 20120831
---
Consumers are increasingly using kiosks to conduct business with enterprises. The kiosks come in a variety of sizes and are used for a variety of purposes. Some kiosks are drive through such as fast food establishments pharmacies banks and the like. Other kiosks are stationary located in gas stations airlines grocery stores department stores and the like.

In addition what is considered a kiosk is evolving with today s technology. For example digital signs now provide advertisements and mechanisms for users to interact with the displays to perform transactions. Such mechanisms include blue tooth communication Near Field Communication NFC Quick Response QR code scanning Wi Fi communication and the like.

In large part due to the advancement and use of technology coupled with the adoption of kiosks enterprises are trying to find new mechanisms to reach consumers with offers for their goods and services that use the current technology effectively and that are capable of being used by consumers via their own devices or kiosks.

Traditional offer management systems require modifications for deployment of new offer functionality. These modifications require extensive testing and affect numerous other existing components of the offer management systems since new functionality is tightly coupled to the existing infrastructure. Because of the tightly coupled environments making any modification to provide new offer functionality becomes a risky proposition when the enterprise wants to deploy the new offer functionality into live retail environments or into newer technology and platforms.

In various embodiments techniques for deployment of universal promotion conditions for offer evaluations are presented. According to an embodiment a method for deployment universal promotion conditions is provided.

Specifically a promotion engine is configured to accept unique pairs of information having a variable identifier and a data type. Operators for each data type are provided to the promotion engine. Finally the promotion engine is delivered to one or more devices for installation and dynamic evaluation of the unique pairs of information organized in custom statements to resolve enterprise offer decisions for consumers.

The condition deployment manager executes on one or more processors of over a network connection. The conditions once deployed interact over the network connection with a variety of devices such as a mobile device via an app may also be referred to as a mobile agent herein a checkout system self service kiosk or cashier manned station a website and the like.

In an embodiment the condition deployment manager is accessible via a cloud processing environment over the Internet. The cloud processing environment includes one or more processing environments configured to deploy and operate the condition deployment manager via an Internet connection having Application Programming Interfaces APIs to interact with a variety of point of sale POS devices customer s mobile device checkout station self service kiosk or cashier manned station website and the like.

Various embodiments of the invention provide a technique for expanding legacy promotion engines in a dynamic and on the fly manner by the deployment of universal promotion conditions.

Specifically the universal promotion conditions optionally allow the configuration and setup of testable reusable key value pairs called universal conditions in an enterprise offer management system.

An example of this is the following two configured Universal Conditions ExternalID Description DataType 

An unlimited number of testable universal conditions may be entered in an administrative section of an offer management tool. These universal conditions may then be leveraged as a condition for an offer setup.

An example offer condition leveraging the above values can be used to create an offer using the following values sent from the POS terminal during the transaction.

If Item Inventory Count of the purchased item is below 3 and the person checking out the merchandise is a seniority rank of manager distribute a reward of a cashier message to alert the manager that inventory of the item is nearly depleted.

The offer condition configuration screen allows the following configuration to test the combinations of universal conditions configured.

Any combination of any number of these universal conditions can be setup to evaluate as an offer condition in conjunction with any other pre existing offer conditions such as item cost item count point balance member identifier etc.

The universal promotion engine interface is capable of accepting these configured offer conditions and then processing the conditional test s based on the application of the values sent from the POS terminal in real time during the transaction.

An example payload of the universal conditions from the POS terminal as sent to the promotion engine can be as follows standard message header ItemLinkCode ItemInventory 2 CashierLevel 3 standard message trailer .

The ItemLinkCode can be interpreted to determine if the message being sent applies those values to an item in the transaction or to the transaction as a whole at the basket level.

IF an enterprise offer management system is not present these types of offer conditions may still be leveraged in the direct engine interface for offer configuration.

It is within this context that the processing of the condition deployment manager is discussed within reference to the .

At the condition deployment manager configures a promotion engine to accept unique pairs of information. Each pair of information having a variable identifier and a data type. This situation was described above.

According to an embodiment at the condition deployment manager configures the promotion engine to handle a custom description with each of the unique pairs of information. Again the description attribute of the information was presented above in detail.

Continuing with the embodiment of and at the condition deployment manager configures the promotion engine to present the custom description within user interfaces. This permits reporting and interactive evaluation of the unique pairs of information by resources such as administrators.

In an embodiment at the condition deployment manager configures the promotion engine to interactively accept the unique pairs of information from an administrative interface.

At the condition deployment manager provides to the promotion engine operators for each data type. Again some example data types and their operators were discussed above in the pre context to the discussion of the condition deployment manager.

According to an embodiment at the condition deployment manager permits the operators to be user defined.

In another case at the condition deployment manager enumerating a predefined list of operators as the operators.

At the condition deployment manager delivers the promotion engine to one or more devices for installation and dynamic evaluation of the unique pairs of information organized in custom statements to resolve enterprise offer devices for consumers. Installation of such a promotion engine is described below with reference to the .

In an embodiment at the condition deployment manager configures the promotion engine with a predefined set of statements defined by enterprise policy.

Continuing with the embodiment of and at the condition deployment manager periodically updates the predefined set of statements based on changes in the enterprise policy.

In another case at the condition deployment manager provides an interface with the promotion engine to define the custom statements.

Continuing with the embodiment of and at the condition deployment manager permits the interface to be used to define specific instances of the unique pairs of information.

Still continuing with the embodiment of and at the condition deployment manager enforces security against attempted changes to predefined instances of the unique pairs of information.

The promotion evaluation agent interacts with the universal promotion conditions described and deployed by the condition deployment manager discussed above with reference to the to provide novel techniques for processing universal promotion conditions in offer evaluations for consumers.

The promotion evaluation agent may be viewed as the promotion engine discussed above with reference to the .

At the promotion evaluation agent parses universal offer conditions defined in conditional statements. The universal offer conditions and the conditional statements custom defined. The universal offer conditions may be viewed as the unique pairs of information discussed above with reference to the .

According to an embodiment at the promotion evaluation agent separates each universal offer condition into a unique pair of information that includes a variable identifier and a data type.

Continuing with the embodiment of and at the promotion evaluation agent identifies a description with each variable identifier.

In another situation at the promotion evaluation agent identifies operators available for use with each universal offer condition.

At the promotion evaluation agent evaluates the universal offer conditions in the context of the conditional statements.

According to an embodiment at the promotion evaluation agent receives additional universal offer conditions periodically from an enterprise controller. The enterprise controller keeping enterprise offers in synchronization across channels and platforms.

In still another case at the promotion evaluation agent interactively receives additional statements having additional universal offer conditions from an administrative interface.

The universal promotion condition deployment system includes a condition deployment manager and a promotion evaluation agent . Each of these components and their interactions with one another will now be discussed in turn.

The universal promotion condition deployment system includes one or more processors of an enterprise retail based server the processors configured with the condition deployment manager which is implemented programmed and resides within a non transitory computer readable storage medium and executes on the one or more processors. Example processing associated with the condition deployment manager was presented in detail above with reference to the .

The condition deployment manager is configured to configure the promotion evaluation agent to process universal offer conditions defined in custom statements.

The universal promotion condition deployment system also includes one or more POS devices each of which are configured with an instance of the promotion evaluation agent which is implemented in a non transitory computer readable storage medium and that executes on one or more processors of the POS devices.

The promotion evaluation agent is configured to dynamically evaluate the custom statements with the universal offer conditions to make dynamic decisions on offers for the consumers.

Continuing with the previous embodiment the distributed promotion engine includes an administrative interface to custom define specific instances of the universal offer conditions and the custom statements on the POS device.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

