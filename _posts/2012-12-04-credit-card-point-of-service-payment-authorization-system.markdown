---

title: Credit card point of service payment authorization system
abstract: The risk of fraud in point of sale credit card transactions is reduced by providing independently-routed verification by communication between the authorized user of the credit card and the issuer of the credit card through a trusted intermediary.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09043224&OS=09043224&RS=09043224
owner: Securus, LLC
number: 09043224
owner_city: Annapolis
owner_country: US
publication_date: 20121204
---
This application claims priority to U.S. Provisional Application Ser. No. 61 630 125 filed Dec. 5 2011 and entitled Credit Card Point of Service Payment Authorization System the entirety of which is incorporated by reference herein.

The present invention relates in general to the problem of user verification and in particular to the problem of unauthorized credit card use and the reduction of the risk of fraud in point of sale credit card transactions.

The invention described and claimed herein comprises a novel approach to reducing the risk of fraud in point of sale credit card transactions by providing independently routed verification of the user s authorization by communication between the authorized user of record of the credit card and the issuer of the credit card through a trusted intermediary.

The term credit card is used to refer to any instrument by which an individual authorizes the request for an extension of credit or transfer of funds. It encompasses not only actual cards which are commonly referred to as credit cards but also debit cards and electronic wands and other tokens which are used to establish authority to extend credit or transfer funds.

The term user refers to the individual presenting the credit card the term user of record refers to the individual who is authorized to request credit or the transfer of funds according to the records of the party extending credit or transferring funds pursuant to said request.

Credit Cards are increasingly becoming popular with an increasing customer base year on year because of the convenient and rewarding experience. Credit Card issuers offer frequent flier miles reward points and other rewarding perks to attract users for regular usage and to maintain their interest in using the credit card services.

The U.S. Census Bureau estimates that there are 181 million credit card holders in the United States. This represents approximately 77 percent of the adult population of the U.S.

According to Census Bureau estimates there are more than 1.4 billion credit cards currently in circulation in the U.S. whose 2010 population is roughly 308.8 million.

These figures mean that there are about 4.5 credit cards for every man woman and child in the United States or an average of 7.7 credit cards for each of the 181 million people who actually hold credit cards.

The Federal Reserve reports that credit cards are used more than 20 billion times a year in the U.S. with the total value of these transactions at about 1.9 trillion.

Based on the number of transactions and the number of credit card holders the average card holder uses a credit card 119 times a year for transactions averaging 88 apiece.

There are many players in the credit card market but there are a handful of clear market share leaders. Based on projections from the Nilson Report based on the data collected by the U.S. Census Bureau here is how the credit card market looked in 2010 

Three companies command 86 percent of all U.S. credit card purchase volume. Visa is the clear front runner with an estimated 38.5 percent of annual purchase volume followed by a close race for second and third place with MasterCard at 24.3 percent and American Express at 23.2 percent.

Other significant players in the credit card market include Discover various store issued credit cards and various oil company credit cards.

American Express has a much lower number of card holders but compensates for it with an up market focus. At 44 million U.S. cardholders American Express not only trails

Visa and MasterCard but is edged out by Discover at 45 million. However in terms of average annual purchase volume American Express transactions total roughly 11 300 per card holder compared with Visa at 7 300 MasterCard at 5 250 and Discover at 2 500.

Relative to their shares of purchase volume Visa and MasterCard each have a disproportionate share of the debt outstanding with Visa at 41.8 percent and MasterCard at 30.6 percent. In dollar terms these portions of debt outstanding represent 388 billion and 284 billion respectively.

The Mercator report estimates U.S. card issuers total losses from credit and debit card fraud at 2.4 billion. That figure does not include losses that are borne by merchants which probably run into tens of billions of dollars a year. These credit card fraud costs cardholders and credit card issuers as much as 500 million a year.

Counterfeit Credit Card Fraud This fraud accounts for 37 of all funds lost through credit card frauds. The fake card criminals use latest technology to skim information contained on credit cards.

Lost or Stolen Credit Card Fraud Cards stolen from their cardholders or lost by them account for 23 of all card frauds. Often cards are stolen from the workplace gym and unattended vehicles.

Identity Theft Identity Theft has been on the rise in the recent years and can happen when criminals apply for credit card using someone else s credentials and personal information.

A 10 year low has been observed in the overall losses due to credit card frauds. According to an annual study by Javelin Strategy Research the number of fraud victims decreased 28 percent in 2010 from 11 million to 8.1 million. The total value of fraudulent losses also fell from 56 bn in 2009 to 37 bn in 2010. This has primarily happened because of the initiatives taken by the stakeholders of the banking industry to increase consumer awareness and hence prevent fraud.

However billions of dollars of frauds are still happening at Point of Sale terminals because of non involvement of the Card Holder.

Attempts to address this problem include Smart Chip solutions which use a card with an embedded microchip that requires the consumer to enter a unique PIN through a reader to make payment and Near Field Communication Solutions which involve short distance wireless communication technology which allows communication between two devices that either touch or are momentarily held close together.

The infrastructure required to enable these solutions is high and even using these solutions fraud remains as demonstrated by the above statistics.

The foregoing problems are overcome and other advantages are provided by an independently routed verification of authority through communication between an authorized user and an issuer of a credit card through a trusted intermediary in accordance with the invention. It should be noted that while the preferred embodiment is illustrated with respect to a credit card transaction the problem and the solution disclosed herein are not limited to credit cards and the invention may also be used in general to verify that a transaction is being authorized by a user of record.

The fundamental weakness of the current system is that the system does not require that the card holder be involved anywhere in the payment process the system only requires that the person claiming to have authority produce the credit card to the POS Merchant. The solution proposed in this disclosure is to involve the Authorized User and require an approval or rejection of any payment authorizations.

It is an object of the invention to provide a means by which an Authorized User is notified of a proposed transaction and authorizes or denies authorization of the transaction via an independent communications channel.

A principal feature of the invention is the independent communications channel controlled by a trusted intermediary.

Another principal feature of the invention is the design of the independent communications channel so that there is no direct communication between any of the parties to the transaction all communications go to a third party trusted intermediary.

Note that in the preferred embodiment a merchant is involved only at POS the merchant does not interact with the Bank System and a communication module runs backend around the clock without involvement of the User or Merchant.

These and other objects features and advantages which will be apparent from the discussion which follows are achieved in accordance with the invention by providing a novel tool for use in point of sale credit card transactions for reducing the risk of fraud by providing independently routed verification by communication between the authorized user of the credit card and the issuer of the credit card through a trusted intermediary.

The various features of novelty which characterize the invention are pointed out with particularity in the claims annexed to and forming a part of this disclosure. For a better understanding of the invention its advantages and objects reference is made to the accompanying drawings and descriptive matter in which a preferred embodiment of the invention is illustrated.

The invention is illustrated through an embodiment using an Apple iPhone . Conceptually there are two broad approaches a pre authorization approach and an at POS authorization approach.

The starting point is the current system for authorizing credit card payments illustrated in . The key stakeholders in this process are Point of Sale Merchants a Merchant Bank Card Service Provider the Card Holder s Bank and a Network Provider. The stakeholder best positioned to prevent fraud is the Credit Card Holder yet under the current system shown in the card holder is not involved except for the moment when card holder hands over the credit card to the POS Merchant and therefore there is no assurance that the actual authorized user of record is actually involved in the authentication process of the credit card payment.

Involving the user of record in the process to authorize the payment will add a level of security and enable reduction in credit card fraud. The approach is illustrated in . The fundamental approach of the invention is to supply the Bank the Credit Card Network Provider or a trusted intermediary with a user s registered mobile telephone number and to download the application described below to the user s mobile telephone. Optionally the user may choose a pin for the application residing on their device thereby providing an additional level of security.

Since the user s mobile number is registered with the Bank or the Network Provider or the intermediary whenever the pre authorization request is sent by the card holder to the bank the user s authentication is verified.

The card holder needs to have data connectivity to use the application on their mobile device and communicate with the Bank system. In case there is no data connectivity the user will have an option to utilize IVR.

This At Authorization approach can be implemented at both Card Service Network and Banking Network level. The POC implements the At Authorization at Banking Network level.

The diagram shows the key stakeholders and flow of information between these stakeholders for the At Authorization approach.

iPhone POC. This application is used by the credit card user for pre authorization At authorization and view transactions and includes the following screens

This simulated model shall be responsible to simulate the card transaction and shall hold the information like card number amount date and status

CNS is a non UI service that acts as an bridge between POS and BS to transfer the information since this is POC CNS does not have any major responsibility associated with it except to transfer the transaction data between POS and BS

BS is responsible to show the information received from POS and act on the transaction and return the response back to credit card user. BS involves itself in following type of requests

This type of request is sent by credit card user prior to the transaction typically a card swipe at POS. As soon as transaction is done by credit card user BS shall compare the Pre Authorization data and the original transaction data to authorize or decline the transaction and send the response back to iPhone application.

At Authorization is similar to Pre Authorization except that BS shall not have any prior information of transaction. In order to simulate the At Authorization effectively a server check shall be sent from iPhone application and BS responds back with At authorization information. iPhone application shall ping the BS every minute once the user launches the application in order to get the appropriate response back to the client.

a. User shall launch the app and successfully pre authorize the transaction for specific amount and credit card

b. User sends a pre authorization for specific amount range however in case bank receives payment exceeding or less than the amount range mentioned in pre authorization then bank sends an At authorization request to user for authorizing the payment

This class shall have a slider to select the credit range and a picker field to select the available credit cards. User shall be provided Authorize and Reset buttons.

This class shall be representing Transaction Authorization pop up for the transaction. Using which user can accept or decline the transaction.

This class shall be the entry point of BS application and shall be responsible for validating the supplied credentials. On successful validation gives access to BS screen.

This class shall be the entry point for POS terminal which captures card number transaction amount and validates the data for transaction process.

Following are the internal interface present in Simtech POC application. This interface holds the static data for application like images html contents if any and information about application.

This interface provides the GUI Graphical User Interface for the application. Through this interface user can interact with the application. It shall also provide the navigation between different features of the application.

iPhone app shall communicate with BS server with the help of SOAP web services for pre and at authorizations.

2.1.1 This screen shall be shown on each and every launch of application and after 3 seconds login screen shall be displayed automatically.

2.1.2 Login screen shall appear at every launch of application prompting user to input username and password to log in to the application. For proof of concept Since POC does not have the registration concept a hard coded username Simtech and password Hadrian combination shall be maintained for authentication. iPhone shall receives the credit card numbers associated with logged in user from BS which shall be displayed in Authorization screen for Pre Authorization process.

2.1.3. Home screen shall be the main screen of the application shall contain 4 different options IVR Authorization My Transactions and About.

2.1.4. IVR shall simulate a call process along with edit field to enter the credit card number and amount. Call pop up shall stay on screen for 10 seconds. There shall be a end call button on the call pop up. If user clicks on end call button before 10 seconds the request process shall be terminated and a failure message shall be shown otherwise a successful message shall be shown.

This screen shall take care of the main concept of iPhone application user shall be able to select the amount range and select the credit card from the picker control for sending a pre authorization request to BS.

This screen shall show all the transactions that have been done by user in form of list once user selects particular transaction from the list all the details shall be shown in a pop up related to selected transaction like

8.1.2. History pop up shall take care of showing the selected transaction details of user and authorization pop up shall allow the user to authorize or decline particular transaction especially At Authorization pulled from BS.

8.2.1. This screen shall be a log in point for BS screen. Once user logs in successfully shall be shown a BS grid user interface with transaction information.

8.2.2. This screen shall contain two parts once shall show an animation image representing a POS terminal where the card transaction happens along with an on screen key pad to enter the amount and execute the transaction. Once the transaction is executed user shall be shown a grid UI with information like credit card number amount date and status.

8.2.3. BS system shall be a grid UI reflecting all the information sent from POS and additional components like user name. All the transaction authorizations shall be automated process showing the animated status accordingly.

8.2.4. This header shall be representing where the request is currently residing in form of a status bar so that user can easily get to know the flow of the request.

A preferred embodiment was tested using the following components iPhone 4 Dedicated Windows server and hosting space for Simulation model .Net framework 2.0 Ajax extension 1.0 IrS 5.0 or above and included the following 

Hadrian app an IPhone 4 application which communicated with the BS and allows a user to raise Pre authorization for a specific amount for all the credit cards associated with specific user name and also receive authorization request from BS for the actual transactions happening at the POS. Based on user authorize or declining response the transaction shall be processed by the BS and update to POS.

The i phone application had the following screens Splash screen an example is shown in Login screen an example is shown in Home screen an example is shown in bank Support screen an example is shown in authorization screen and card selection an example is shown in pre authorization popup an example is shown in Actual Transaction authorization popup an example is shown in APNS popup an example is shown in and My transactions screen and transaction details an example is shown in .

The system was tested using a simulated POS terminal to simulate a typical POS terminal where the billing happens and a transaction request sent to respective eNS and BS once the credit card is swiped and a Simulated eNS which is a non UI simulated eNS which simply shall act as a bridge between POS and BS and a Simulated BS to simulate a bank system to show all the transactions and their status.

The capabilities and functioning of the invention are further illustrated in the following scenarios which were tested 

3. Home screen is shown with available options based on user validation and credit cards associated with user

10. If actual transaction is with in the limits of pre Auth request 50 bank shall check and authorize the request directly

3. Home screen is shown with available options based on user validation and credit cards associated with user

to. r f actual transaction is more than the limit of pre auth request S50 then the transaction shall be cancelled by BS and new AT request is sent to user

3. Home screen is shown with available options based on user validation and credit cards associated with user

10. If actual transaction is with in the limits of pre Auth request 50 bank shall check and initiate APNS notification

11. User receives the notification when clicked on View app launches and user inputs proper user name and password

3. Home screen is shown with available options based on user validation and credit cards associated with user

10. If actual transaction is above the limit of pre Auth request S50 BS shall cancel the transaction initiate AT request and sends APNS notitication

11. User receives the APNS notification with View and Close buttons when clicked on View app launches and user inputs proper user name and password. If clicked on Close nothing happens and BS shall wait for specified time and cancel the transaction

3. Home screen is shown with available options based on user validation and credit cards associated with user

5. When clicked on View application launches and user types proper username and password. If clicked on Close button nothing happens and after some time transaction shall be cancelled by BS and updates to POS

3. Home screen is shown with available options based on user validation and credit cards associated with user

10. If actual transaction is more than the limit of pre auth request 50 then the transaction shall be cancelled by BS and new AT request is sent to user

11. User enters a dead zone where there is no internet available or does not respond to the transaction request sent by BS

12. BS shall wait for 2 minutes for user response and if not received shall send a pass code request to POS terminal

3. Home screen is shown with available options based on user validation and credit cards associated with user

8. If insufficient funds on the card then BS shall send back appropriate response and cancels the request placed

3. Home screen is shown with available options based on user validation and credit cards associated with user

10. If actual transaction is more than the available credit limit on the card then BS shall cancel the transaction

Thus there has been described a novel solution for reducing the risk of fraud in point of sale credit card transactions by providing independently routed verification by communication between the authorized user of the credit card and the issuer of the credit card through a trusted intermediary that has a number of novel features and a manner of making and using the invention.

While a specific embodiment of the invention has been shown and described in detail to illustrate the application of the principles of the invention it will be understood that the invention may be embodied otherwise without departing from such principles and that various modifications alternate constructions and equivalents will occur to those skilled in the art given the benefit of this disclosure. Thus the invention is not limited to the specific embodiment described herein.

