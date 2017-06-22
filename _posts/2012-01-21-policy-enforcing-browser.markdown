---

title: Policy enforcing browser
abstract: A web browser that includes a network policy enforcement unit, a storage policy enforcement unit, and an ancillary policy enforcement unit is disclosed. The network policy enforcement unit controls communications between application logic of a web application and data communication APIs. The storage policy enforcement unit controls access between the web application logic and persistent storage APIs. The ancillary policy enforcement unit controls user authentication of the web application logic.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09043863&OS=09043863&RS=09043863
owner: Symantec Corporation
number: 09043863
owner_city: Mountain View
owner_country: US
publication_date: 20120121
---
This application claims priority to U.S. Provisional Application 61 461 710 filed Jan. 22 2011 and titled SYSTEM FOR THE DISTRIBUTION AND DEPLOYMENT OF APPLICATIONS WITH PROVISIONS FOR SECURITY AND POLICY CONFORMANCE which application is incorporated by reference in its entirety into the present application.

This application claims the benefit of U.S. application Ser. No. 13 226 351 filed on Sep. 6 2011 and titled SYSTEM FOR THE DISTRIBUTION AND DEPLOYMENT OF APPLICATIONS WITH PROVISIONS FOR SECURITY AND POLICY CONFORMANCE which application is incorporated by reference in its entirety into the present application. U.S. application Ser. No. 13 226 351 filed on Sep. 6 2011 claims priority to U.S. Provisional Application 61 402 934 filed on Sep. 7 2010.

The present invention relates generally to browsers and more particularly to browsers that enforce policies relating to a web application.

Presently browsers only perform core functions such as interpreting a document markup language and possibly a scripting language. However in an environment in which Web applications are delivered to client devices many of which are mobile and operated by employees in carrying out functions of the business that employes them such browsers are not sufficient. Browsers in the above mentioned environment need additional functions to aid in the secure operation of such client devices.

One embodiment of the present invention is a web browser that includes a web browser core unit a network policy enforcement unit a storage policy enforcement unit and an ancillary policy enforcement unit. The web browser core unit is operable if enabled to interpret at least a document markup language contained in a web application where the web application includes web application logic that uses a data communication facility to communicate over a network and a persistent storage facility to save or retrieve web application data. The network policy enforcement unit acquires a network enforcement policy wherein the unit constrains use by the web application logic of the data communication facility according to the network enforcement policy. The storage policy enforcement unit acquires a storage enforcement policy wherein the unit constrains use by the web application logic of the persistent storage facility according to the storage enforcement policy. The ancillary policy enforcement unit acquires an ancillary enforcement policy wherein the unit constrains application logic according to said ancillary policy. One such constraint is authentication of a user prior to use of the web application logic.

Another embodiment of the present invention is a method of enforcing a data communication policy in a computer system. The method includes obtaining a web application where the web application is operable on the computer system and includes web application logic that requires use of a data communication facility of the computer system acquiring a network enforcement policy and constraining use by the web application logic of the data communication facility according to the network enforcement policy.

Yet another embodiment is a method of enforcing a persistent storage policy in a computer system. The method includes obtaining a web application where the web application is operable on the computer system and includes web application logic that uses a persistent storage facility of the computer system acquiring a persistent storage policy and constraining use by the web application logic of the persistent storage facility according to the persistent storage enforcement policy.

A typical embodiment of the invention consists of a web browser core coupled with authentication security and policy enforcement logic the means to store and receive policy from an authoritative source and the means to communicate with an identity or authentication service. An embodiment may also contain the means to communicate encryption key values with a key management or key storing system. In a preferred embodiment of the invention the embodiment works in conjunction with the application gateway as it is described in patent application 61 402 934 which is incorporated by reference into the present application in its entirety.

A web application is typically comprised of but not limited to HTML HTML5 JavaScript code VBScript code Java code CSS XML Plug ins or Helper applications or any combination thereof served from a web application server to a client browser by communicating across a data network . In some cases the web application may be stored locally on the device hosting the web browser rather than being served across a data network.

The invention allows for a web application to be run within the context of a browser in such a way that policies related to user authentication device authentication data storage data encryption and data communication are enforced independent of the behavior of the aforementioned web application and independent of traditional web browser policy enforcement.

In a typical embodiment the invention is deployed on a user facing endpoint such as a mobile phone tablet personal computer laptop or kiosk.

Although the invention is titled a browser in an embodiment browsing may not be enabled at all the embodiment may be simply acting as an execution platform for a single web application or an execution platform for multiple web applications.

In an alternate embodiment the invention may be employed as a means to affect the aforementioned policy controls on a dynamic application execution environment. The invention requires neither HTML nor Javascript in an alternate embodiment the invention can be applied to other computer languages.

In a typical embodiment the invention is based on a conventional web browser core . In a typical embodiment the web browser core includes the logic and data structures needed to receive HTML parse HTML and translate HTML into data structures . In a typical embodiment the web browser core additionally includes the logic and data structures needed to receive HTML5 parse HTML5 and translate HTML5 into data structures . In a typical embodiment the web browser core further includes the logic and data structures needed to receive JavaScript parse JavaScript translate JavaScript into data structures execute JavaScript and generate JavaScript . In some embodiments the logic and data structures needed to perform the same or similar functions with alternative markup or programming languages may be substituted or added.

In a typical embodiment the invention runs under the control of an operating system OS on a computing platform. An embodiment of the invention that does not require an OS is an alternative. In a typical embodiment the computing platform comprises at a minimum random access memory RAM and a central processing unit CPU . In a typical embodiment the computing platform has access to a data network access to persistent storage or both. A data network supports the communication of data between two entities often at a distance. Persistent storage allows for the storage of data often locally such that the data survives events that would harm the data if the data were otherwise stored in RAM. In an embodiment where the OS and computing platform support access to a data network typically the OS presents data communication APIs application programming interfaces . In an embodiment where the OS and computing platform supports access to persistent storage typically the OS presents persistent storage APIs .

In a possible embodiment of the invention web browser plug ins may also be bound to the web browser core . In a possible embodiment plug ins may have access to browser data structures OS system calls libraries or data resident on the computing platform. In such an embodiment all policy enforcement described below is extended to any such plug ins that is plug ins are constrained to policy.

In a typical embodiment policy is communicated from an application gateway through a data network and stored in RAM and in persistent policy storage PPS by the invention. PPS is simply the storage of relevant policy in persistent storage. In a preferred embodiment the stored policy is secured such that authenticity and integrity are preserved. In an alternate embodiment confidentiality may be required as well. In an alternate embodiment policy may be loaded into invention by alternate means possibly including manual configuration . In a preferred embodiment of the invention policy may be attached as a partial or complete PPS at the time that the invention is linked or otherwise programmatically transformed into the state in which it is to be distributed preferentially using the invention described in provisional patent application 61 402 934 which application is incorporated by reference into the instant application.

In the preferred embodiment of the invention the storage policy enforcement unit SPE network policy enforcement unit NPE and ancillary policy enforcement unit APE draw policy to be enforced from the PPS RAM or both.

As shown in the SPE NPE and APE are receivers of policy and the reception of policy is a policy event . In the preferred embodiment they receive policy as policy becomes available in real time. They may however receive policy only based on push events where multiple policies are sent simultaneously. In an alternative embodiment they may compel or ask for policy updates. An embodiment that supports the dynamic update of policy may use but is not limited to all three types of policy events.

In the preferred embodiment the NPE enforces all policy related to the web application s communication over any data network . Any attempt by the web application to communicate over or access the network is allowed blocked or logged depending on policy. Note that the invention is not limited to the three actions of allowing blocking or logging an access or communication rather these are the policy actions available in the preferred embodiment. In a typical embodiment the NPE logically stands as a gatekeeper between the web application logic and the OS provided data communication APIs .

In the preferred embodiment the SPE enforces all policy related to the web application s storage of data to persistent storage. Any attempt by the web application to write to or read from persistent storage is allowed blocked or logged depending on policy. Note that the invention is not limited to the three actions of allowing blocking or logging an access to storage rather these are the policy actions available in the preferred embodiment. In a typical embodiment the SPE logically stands as a gatekeeper between the web application logic and the OS provided persistent storage APIs .

In the preferred embodiment the APE performs user authentication by use of UI controls . In doing so the APE is able to affect the enforcement of policy related to user authentication. In the preferred embodiment the APE is also responsible for any device authentication aspects including but not limited to marshalling i.e. collecting device credentials or responding to challenges related to device authentication.

In the preferred embodiment the APE performs all policy enforcement related to plug ins. This includes both the acceptance for launch or allowed use of specific plug ins as well as the accesses to network storage OS aspects or compute platform aspects by specific plug ins.

In the preferred embodiment the APE performs all policy enforcement related to the web application s access to web browser cookies or any other browser specific stored data such is stored in HTML5.

In the preferred embodiment the APE performs all policy enforcement related to shared memory RAM access as well as all policy enforcement related to interprocess communication IPC mechanisms or communication between threads. The availability of IPC or communication between threads to a web application would typically be a function of the OS and of the web browser core .

In the preferred embodiment where the invention is used to run more than a single web application the APE enforces all policy related to the interaction between the web applications .

In the preferred embodiment the logic of the web browser core is also subject to policy enforcement by the SPE NPE and APE . In such an embodiment the policy conformance of the aggregate web application and web browser can be assured.

In the preferred embodiment the invention leverages all substitution linking or binding capabilities described in patent application 61 402 934. In practice the method of integration with the web browser core typically depends on the OS and the actual web browser core utilized.

In some embodiments the integration is accomplished by editing the browser core source code such that the affected source code changes cause the policy enforcement and other related logic to be directly or indirectly invoked.

In some embodiments the integration is accomplished by link time insertion of the policy enforcement and other related logic or by other automated re writing of source or object code or symbols.

In some embodiments the integration is accomplished by augmenting the OS rather than the browser itself. In such an embodiment the invention spans the boundary between application web browser and OS.

In some embodiments more than one of the above methods of integration may be employed in implementing the invention. In some embodiments methods of integration not listed above may be employed.

Although the present invention has been described in considerable detail with reference to certain preferred versions thereof other versions are possible. Therefore the spirit and scope of the appended claims should not be limited to the description of the preferred versions contained herein.

