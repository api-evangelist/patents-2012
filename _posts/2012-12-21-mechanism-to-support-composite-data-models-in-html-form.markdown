---

title: Mechanism to support composite data models in HTML form
abstract: Techniques to process a form are disclosed. An attribute associated with a child data model is recognized in a first set of form data associated with a form an attribute associated with a child data model. A data value associated with the attribute is used to obtain a second set of form data associated with the child data model. The second set of form data is associated with the form.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09424243&OS=09424243&RS=09424243
owner: EMC Corporation
number: 09424243
owner_city: Hopkinton
owner_country: US
publication_date: 20121221
---
In web 2.0 applications JSON is one of the supported data exchange formats between the client and server e.g. REST services . The server serializes complex data models e.g. Java object into the JSON data. In the client e.g. Web Browser the JSON data gets transformed into client data model objects e.g. JavaScript objects .

Typically the client model objects are used to display the data in the HTML page. The data may be displayed as read only or may be populated into an editable HTML form.

In the classical mechanism HTML form fields are associated to a single level data model e.g. JavaScript object . Changes made to form fields at the client can be submitted which results in the data model changes being sent back to the server. However currently there is no known mechanism for HTML form fields to be associated to composite data models. The composite data model groups multiple data models in a parent child relationship. Additionally there is no known mechanism to submit i.e. to a server a composite data model associated with a single HTML form.

The invention can be implemented in numerous ways including as a process an apparatus a system a composition of matter a computer program product embodied on a computer readable storage medium and or a processor such as a processor configured to execute instructions stored on and or provided by a memory coupled to the processor. In this specification these implementations or any other form that the invention may take may be referred to as techniques. In general the order of the steps of disclosed processes may be altered within the scope of the invention. Unless stated otherwise a component such as a processor or a memory described as being configured to perform a task may be implemented as a general component that is temporarily configured to perform the task at a given time or a specific component that is manufactured to perform the task. As used herein the term processor refers to one or more devices circuits and or processing cores configured to process data such as computer program instructions.

A detailed description of one or more embodiments of the invention is provided below along with accompanying figures that illustrate the principles of the invention. The invention is described in connection with such embodiments but the invention is not limited to any embodiment. The scope of the invention is limited only by the claims and the invention encompasses numerous alternatives modifications and equivalents. Numerous specific details are set forth in the following description in order to provide a thorough understanding of the invention. These details are provided for the purpose of example and the invention may be practiced according to the claims without some or all of these specific details. For the purpose of clarity technical material that is known in the technical fields related to the invention has not been described in detail so that the invention is not unnecessarily obscured.

Techniques to provide composite data model support for HTML forms are disclosed. In various embodiments N level nesting of parent child relationships is supported. The parent child relationship is established using a field attribute in the parent data model. This field is of a custom type that identifies the field as one that defines and represents a parent child relationship. In various embodiments a dotted notation is used to express and or communicate the parent child relationship s that define an attributes place within a hierarchical composite data model. In some embodiments dynamic and or lazy loading of child objects of a composite data model is provided.

In some embodiments the parent model in the example shown in the LoanApproval model references the customer model as field customer . Consider the following payload from the server for the loan approval data 

The customer field which refers to customer model has the custId attribute which in this example can be used to fetch the customer data from the server. In some embodiments the server may return the following payload for the customer model 

The customer model above in various embodiments would be instantiated and inserted into the loan approval model. In some embodiments the loading of a child object of the customer model such as the mail address model in the example shown in would happen only when the address model fields were referred by the HTML form. As a result the mail address model or any other child model would only be loaded if and or when needed to render the HTML form.

In various embodiments a dotted notation is used to refer to form fields by name in a manner that expresses applicable parent child relationships. For example the HTML form field may be associated to the composite data models as follows using ExtJs configuration 

In the above example the name attribute of the form field is used to express the binding of that field to the composite data model. Specifically the expression loan approval.customer.name is used to identify the name attribute as a field of the customer child data model of the loan approval parent data model.

In various embodiments data model fields values can be set or obtained using the dotted notation e.g. as follows 

In various embodiments as the child model data gets loaded it gets merged into the parent data model. Thus all the user inputs to the form are recorded into the parent model which gets submitted on form submission. At the server the dotted notation is interpreted to associate submitted data values to corresponding attributes in the composite data model.

Using techniques disclosed herein inherent support of composite data models is provided for HTML forms. Seamless binding of composite data model attributes to form fields is provided. Dynamic and or lazy loading of client data models is supported. Transparent data exchange between the client and server is provided.

Although the foregoing embodiments have been described in some detail for purposes of clarity of understanding the invention is not limited to the details provided. There are many alternative ways of implementing the invention. The disclosed embodiments are illustrative and not restrictive.

