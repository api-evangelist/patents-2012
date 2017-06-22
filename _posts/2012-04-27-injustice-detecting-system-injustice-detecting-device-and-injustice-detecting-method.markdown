---

title: Injustice detecting system, injustice detecting device and injustice detecting method
abstract: The present invention provides an injustice detecting system enabling detection of an injustice that is performed through an operation that cannot be distinguished from normal operation. This injustice detecting system is provided with: a history recording unit for recording operation history information of a monitored device; an audit information disclosure unit for disclosing audit information including at least information indicating that an audit for detecting an injustice is to be implemented; and an injustice detecting unit for detecting the injustice on the basis of pre-disclosure operation history information which is operation history information generated before the audit information is disclosed, and post-disclosure operation history information, which is operation history information generated after the audit information is disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09183388&OS=09183388&RS=09183388
owner: NEC CORPORATION
number: 09183388
owner_city: Tokyo
owner_country: JP
publication_date: 20120427
---
This application is a national stage application of International Application No. PCT JP2012 061799 entitled Injustice Detecting System Injustice Detecting Device and Injustice Detecting Method filed on Apr. 27 2012 which claims the benefit of the priority of Japanese patent application No. 2011 107300 filed on May 12 2011 the disclosures of each of which are hereby incorporated by reference in their entirety.

The present invention relates to an injustice detecting system an injustice detecting device and an injustice detecting method.

With respect to detecting an injustice access to an information system which is carried out by a handler who has an access right various related techniques are known. Here the handler includes a person a computer or another apparatus. Hereinafter the handler is called a person having access right.

A patent document 1 discloses a log analyzing server which detects a specific user who carries out a peculiar operation in a group including a plurality of users in comparison with another user in the group.

First the log analyzing server collects a log of a computer operation or the like carried out by users belonging to the same group.

Next the log analyzing server generates a model of operation which a specific user who belongs to the group carries out as a specific time elapses on the basis of a log of the operation carried out by the specific user. At the same time the log analyzing server generates models of operations which a plurality of general users carry out as the specific time same as the specific time corresponding the model of operation carried out by the specific use elapse on the basis of logs of the operations carried out by a plurality of the general users. Here the general users are different from the specific user who belongs to the group but belongs to the same group.

Next the log analyzing server carries out analysis by comparing a general tendency of the models of operations carried out by the general users and the model of operation carried out by the specific users.

The log analyzing server which is disclosed in the patent document 1 operates as mentioned above and consequently detects the specific user who carries out the peculiar operation in the group in comparison with the general user.

A patent document 2 discloses an abnormal operation detecting device which detects an abnormal operation on the basis of a regular operation which can be judged to be an usual operation and a current operation.

The abnormal operation detecting device includes a log collecting means a current operation defining means a regular operation database and an operation comparing means.

The current operation defining means defines operation contents which the log collecting means acquires and which are carried out during a short time in a specific user terminal as the current operation.

The regular operation database stores contents corresponding to the regular operation which can be judged to be the usual operation in advance.

The operation comparing means finds a ratio of number of the regular operations to number of the current operations which are different from the regular operation as a degree of abnormal operation and judges that the current operation is abnormal if the degree of abnormal operation is larger than a predetermined threshold value.

The abnormal operation detecting device disclosed in the patent document 2 detects the current operation which is abnormal in comparison with the regular operations by having the above mentioned configuration.

However the technique which is disclosed in the patent document mentioned above has a problem that it is impossible to detect an injustice carried out by an operation which can not be distinguished from a normal operation.

A reason why there is a case that the injustice can not be detected will be described in the following.

In the case that the injustice is carried out by an operation corresponding to regular operations the log analyzing server described in the patent document 1 can not detect the injustice. Specifically in the case that a specific user carries out the injustice by carrying out an operation which is similar to the operations carried out by a plurality of the general users who belong to the same group the log analyzing server can not detect the injustice.

Moreover the log analyzing server can not be applied to a transaction system which can not define a group whose members carry out the same operation at the same time. Specifically in the case of for example a sales department of a general company each member of the sales department carries out a job according to a situation of a customer of each member. Accordingly operations which are carried out to an information system by the members do not synchronize. That is the log analyzing server can be applied to only the case that a transaction system using an information system which is an object for analysis is corresponding to a transaction system which can define the group whose members carry out the same operation at the same time.

In the case that the injustice is carried out by an operation corresponding to the regular operation the abnormal operation detecting device disclosed in the patent document 2 can not detect the injustice. Specifically in the case that the injustice is carried out by a specific operation the abnormal operation detecting device can not detect the injustice. Here the specific operation means an operation whose operation contents exist in a range where the operation contents are not used by the abnormal operation detecting device when comparing a difference between the current operation and the regular operation.

An object of the present invention is to provide an injustice detecting system an injustice detecting device and an injustice detecting method which solve the problem mentioned above.

an audit information disclosing means for disclosing audit information including at least information which indicates that an audit for detecting an injustice and

an injustice detecting means for detecting an injustice on the basis of pre disclosure operation history information corresponding to said operation history information before a time when said audit information is disclosed and post disclosure operation history information corresponding to said operation history information after the time when said audit information is disclosed.

an audit information disclosing means for disclosing audit information including at least information which indicates that an audit for detecting an injustice and

an injustice detecting means for detecting an injustice on the basis of pre disclosure operation history information corresponding to said operation history information before a time when said audit information is disclosed and post disclosure operation history information corresponding to said operation history information after the time when said audit information is disclosed.

An injustice detecting method which an injustice detecting device executes according to a fourth aspect of the present invention includes 

disclosing audit information including at least information which indicates that an audit for detecting an injustice and

detecting an injustice on the basis on pre disclosure operation history information corresponding to said operation history information before a time when said audit information is disclosed and post disclosure operation history information corresponding to said operation history information after the time when said audit information is disclosed.

A non transitory medium according to a fourth aspect of the present invention records a program which makes a computer which includes a means to store operation history information of a monitored device execute 

a process of disclosing audit information including at least information which indicates that an audit for detecting an injustice and

a process of detecting an injustice on the basis on pre disclosure operation history information corresponding to said operation history information before a time when said audit information is disclosed and post disclosure operation history information corresponding to said operation history information after the time when said audit information is disclosed.

The present invention has an effect that it is possible to detect the injustice carried out by the operation which can not be distinguished from the normal operation.

Next an exemplary embodiment of the present invention will be described in detail with reference to a drawing.

Referring to an injustice detecting system according to the exemplary embodiment includes an injustice detecting device and a monitored device .

The injustice detecting device includes an audit information disclosing unit a history storing unit and an injustice detecting unit . The injustice detecting device may be for example a server PC a terminal or another information processing device.

The monitored device includes an audit information displaying unit a history acquiring unit and a control unit . The monitored device may be for example a server PC a terminal or another information processing device.

The audit information disclosing unit of the injustice detecting device discloses audit information which includes at least audit execution information. Here the audit execution information means information which indicates that an audit for detecting the injustice is executed. For example the audit information disclosing unit discloses the audit information by sending the audit information to the monitored device .

Moreover the audit information disclosing unit outputs a time hereinafter referred to as audit information disclosure time at which the audit information is disclosed to the injustice detecting unit at a time when making the injustice detecting unit start working. Here the time when making the injustice detecting unit start working means a time when a predetermined predicted period of time elapses since the audit information is disclosed. Moreover the predetermined predicted period of time means a period of time which is given in advance by for example a means not shown in the figure and which indicates that it is predicted that an injustice concealing operation will be carried out when the prediction period of time elapses. Here the injustice concealing operation means an operation in which the injustice is concealed by a trigger which is post disclosure audit information being disclosed.

Moreover the audit information disclosing unit may output for example the time of disclosing the audit information to the injustice detecting unit in advance. In this case the injustice detecting unit may start working at a time when the predetermined predicted period of time mentioned above elapses since the received time of disclosing the audit information.

The history storing unit stores operation history information which the history acquiring unit of the monitored device acquires.

The operation history information whose operation contents is delete file is also called file deletion history information.

The operation contents means information which indicates contents of an operation carried out by an handler of the monitored device . Specifically the operation contents indicate for example delete file which means an operation of deleting a file. The operation contents may indicate send mail meaning an operation in which the monitored device sends an e mail. The operation contents may indicate receive mail meaning an operation in which the monitored device receives an e mail. Furthermore the operation contents may indicate browse web browse web page meaning an operation in which the monitored accesses the Internet.

Here the file is for example a text file a document file a numerical value data file a database data file an image data file a voice data file an e mail data file a binary file like a program and another data file.

The operation time means information which indicates a time when an operation indicated in the operating contents is carried out. The operation time indicates a date and time for example like month date hour minute .

The deletion method classification indicates for example move to trash box meaning to move a file to a folder which is named a trash box by carrying out an operation of deleting the file or erase file which means erasing a file from a storage means not shown in the figure of the monitored device by carrying out an operation of erasing the file. Here for example also in the case that the file in the trash box is erased by carrying out an operation of clearing the trash box the deletion method classification indicates erase file .

The deleted file generation time means information which indicates a time when a file deleted by the operation of deleting the file is generated first.

The deleted file name means a file name of the file which is deleted by the operation of deleting the file.

The deleted file contents means contents of the file which is deleted by the operation of deleting the file. The deleted file contents may include all of or a part of the contents of the file. Here N A described in the figure is an abbreviation of not available and indicates impossible to be used . That is a case that the deleted file contents indicates N A indicates that the deleted file contents do not include contents of the file.

The injustice detecting unit detects the injustice on the basis of pre disclosure operation history information and post disclosure operation history information. Here the pre disclosure operation history information means the operation history information which is stored in the history storing unit before the audit information is disclosed. Moreover the post disclosure operation history information means the operation history information which is stored in the history storing unit after the audit information is disclosed. Here specifically the injustice detecting unit according to the exemplary embodiment detects the injustice as a result of detecting the injustice concealing operation. Next in the case that the injustice detecting unit detects the injustice injustice concealing operation the injustice detecting unit outputs information which is corresponding to the detected injustice concealing operation to an outside by use of a means not shown in the figure. Here the information corresponding to the detected injustice concealing operation means information related to the injustice.

The injustice detecting unit starts working by a trigger which is the audit information disclosure time being received from the audit information disclosing unit . Here the injustice detecting unit may start working after the predetermined predicted time mentioned above elapses since receiving the audit information disclosure time from the audit information disclosing unit .

For example the injustice detecting unit detects an injustice concealing operation on the basis of number of pieces of file deletion history information which are included in each of pre disclosure operation history information and post disclosure operation history information.

As a more specific example the injustice detecting unit counts number of the pieces of the file deletion history information which are included in the pre disclosure history information per a predetermined unit time for example one day . Hereinafter the number of the pieces of the file deletion history information which are included in the pre disclosure operation history information per the predetermined unit time is referred to as an usual deletion number. At the same time the injustice detecting unit counts number of the pieces of the file deletion history information which are included in the post disclosure history information per an unit time. Hereinafter the number of the pieces of the file deletion history information which are included in the post disclosure operation history information per the predetermined unit time is referred to as a checked deletion number.

Next the injustice detecting unit makes the usual deletion number which is larger than 1 approximate to the normal distribution and calculates a T score of the checked deletion number according to the normal distribution.

Next the injustice detecting unit makes the usual deletion number which is larger than 1 approximate to the normal distribution and calculates a T score or a Z score of the checked deletion number according to the normal distribution. Here each of a T score and a Z score is calculated from standard scores.

In this case the operation history information may include only the operation contents and the operation time out of the operation history information .

Moreover for example the audit information disclosing unit of the injustice detecting device may disclose audit information including at least scheduled time information which indicates a scheduled time for executing the audit in addition to audit execution information.

In this case according to the first specific example mentioned above for example the injustice detecting unit may count number of the pieces of file deletion history information which are included in post disclosure pre execution operation history information per an unit time as checked deletion number. Here the post disclosure pre execution operation history information means the operation history information whose operation time indicates any time in a period of time from the time of disclosing the audit information until the time indicated by the scheduled time information.

Moreover for example the injustice detecting unit may detect injustice concealing operations on the basis of the deletion method which is indicated by file deletion history information included in post disclosure operation history information.

As a more specific example the injustice detecting unit calculates a ratio of the number of the pieces of the file deletion history information whose deletion method classification indicates erase file to the number of the pieces of the file deletion history information included in the post disclosure operation history information. Next the injustice detecting unit detects the injustice concealing operation on the basis of a judgment whether the calculated ratio is larger than a predetermined value for example 50 percent or not.

In this case the operation history information may include only the operation contents the operation time and the deletion method classification out of the operation history information .

Moreover for example the injustice detecting unit may detect injustice concealing operations on the basis of date and time at which a deletion object file is generated and which is indicated by file deletion history information included in post disclosure operation history information.

As a more specific example the injustice detecting unit calculates a ratio of number of the pieces of the file deletion history information whose deleted file generation time indicates before a predetermined time out of the file deletion history information included in the post disclosure operation history information. Here the predetermined time is for example one year before the current time. But the predetermined time may be any time.

Next the injustice detecting unit may detect the injustice concealing operation on the basis of a judgment whether the calculated ratio is larger than a predetermined value for example 50 percent or not.

In this case the operation history information may include only the operation contents the operation time and the deleted file generation time out of the operation history information .

Moreover for example the injustice detecting unit may detect injustice concealing operations on the basis of file deletion history information included in post disclosure operation history information of the plural monitored devices .

As a more specific example the injustice detecting unit counts a usual deletion number on the basis of the pre disclosure operation history information of each monitored device out of the plural monitored device . Next the injustice detecting unit adds the usual deletion number which is counted per the monitored device to find a total of the usual deletion numbers.

At the same time the injustice detecting unit counts a checked deletion number on the basis of the post disclosure operation history information of each monitored device out of the plural monitored devices . Next the injustice detecting unit adds the checked deletion number of each monitored device to find a total of the checked deletion numbers.

Next the injustice detecting unit calculates a T score of the total of the checked deletion numbers according to the normal distribution which is generated from the total of the usual deletion numbers.

Next the injustice detecting unit detects the injustice concealing operation on the basis of a judgment whether the calculated T score of the total of the checked deletion numbers is larger than a predetermined value for example 70 or not.

In this case the operation history information may include only the operation contents and the operation time out of the operation history information .

Moreover for example the injustice detecting unit may detect injustice concealing operation on the basis of in particular the deleted file name of file deletion history information included in post disclosure operation history information of the plural monitored devices .

As a more specific example the injustice detecting unit extracts the file deletion history information which includes the same deleted file name out of the post disclosure operation history information of the plural monitored devices .

Next the injustice detecting unit counts number of kinds of the deleted file name which are included in the extracted file deletion history information. Hereinafter the number of the kinds of the deleted file name which is included in the extracted file deletion history information is called number of kinds of cooperative deletion.

Next the injustice detecting unit may detect the injustice concealing operation on the basis of a judgment whether the counted number of kinds of cooperative deletion is larger than a predetermined value for example 1 or not.

In this case the operation history information may include only the operation contents the operation time and the deleted file name out of the operation history information .

Moreover for example the injustice detecting unit may detect the injustice concealing operation by combining any specific examples out of the first to the sixth specific examples.

As a more specific example the following may be used by combining the first specific example and the third specific example. The injustice detecting unit element counts number of the pieces of the file deletion history information whose checked deletion number has a T score larger than a predetermined value and whose deletion method classification indicates erase file . Next the injustice detecting unit detects the injustice concealing operation on the basis of a judgment whether the ratio of the counted number is larger than a predetermined value or not.

Moreover for example the following may be used by combining the first specific example and the third specific example. The injustice detecting unit selects only the file deletion history information whose deletion method classification indicates erase file as objects and calculates a T score of the checked deletion number of the objects.

Moreover for example the following may be used by combining the first specific example and the fourth specific example. The injustice detecting unit selects only the file deletion history information whose deleted file generation time indicates that the deleted file is generated before a predetermined time as objects and calculates a T score of the checked deletion number of the objects.

Moreover for example the following may be used by combining the fifth specific example and the fourth specific example. The injustice detecting unit selects only the file deletion history information whose deleted file generation time indicates that the deleted file is generated before a predetermined time as objects and calculates a T score of the total of the checked deletion numbers of the objects.

Moreover for example the following may be used by combining the first specific example and the sixth specific example. The injustice detecting unit generates a normal distribution related to the number of kinds of cooperative deletion which is calculated on the basis of the pre disclosure operation history information. Then the injustice detecting unit calculates a T score of the number of kinds of cooperative deletion which is calculated on the basis of the post disclosure operation history information according to the normal distribution.

Moreover for example in the third to the sixth specific examples the injustice detecting unit may correspond to audit information including at least a scheduled time information which indicates a scheduled time for executing the audit in addition to audit execution information similarly to a relation of the second specific example with the first specific example.

Moreover in addition to the specific example mentioned above for example file deletion history information may include a distinction between a file deletion carried out by an user s instruction and a file deletion carried out automatically by a system or an application. The file deletion carried out by the user s instruction is corresponding to for example moving a file to a trash box by drag and drop with handling a mouse and deleting a file by selecting deletion from the menu bar. Then the injustice detecting unit may select the file deletion history information which indicates deletion carried out by the user s instruction as an object and may detect the injustice concealing operation out of the object.

The above is the description of the specific example of the operation of the injustice detecting unit .

The audit information displaying unit of the monitored device makes a display means of the monitored device which is not shown in the figure display the audit information on the basis of the received audit information.

In the case that the history acquiring unit which monitors an operation carried out by the control unit detects any one of one or more than one predetermined operations for example file deletion the history acquiring unit acquires and outputs the operation history information related to the detected operation.

Here the history acquiring unit may acquire the deleted file contents out of the operation history information only in a period of time from a time when the audit information displaying unit displays the audit information until a time when a predetermined predicted period of time elapses and output the acquired deleted file contents . Here the history acquiring unit may acquire a period of time which means that it is predicted that during the period of time the injustice concealing operation is carried out at a trigger time when the audit information is disclosed as mentioned above. Then the history acquiring unit may use the period of time as the predicted period of time.

The history acquiring unit detects the operation of deleting the file for example by monitoring that the control unit which will be described later calls API Application Programming Interface for deleting the file. Since the technique related to detecting the operation is well known detailed description is omitted.

The control unit controls an original operation of the monitored device . For example in the case that the monitored device is a server a personal computer or a terminal the control unit controls an operation which is carried out as the server the personal computer or the terminal respectively.

Next an operation according to the exemplary embodiment will be described in detail with reference to a drawing.

First an operation of disclosing audit information and an operation of detecting injustice concealing operations will be described.

The audit information disclosing unit of the injustice detecting device sends audit information to the audit information displaying unit of the monitored device Step S .

Next the audit information disclosing unit outputs a audit information disclosure time time when the audit information is sent to the audit information displaying unit of the monitored device to the injustice detecting unit after a predetermined time elapses Step S .

Next the injustice detecting unit acquires pre disclosure operation history information and post disclosure operation history information from the history storing unit on the basis of the received audit information disclosure time Step S .

Next the injustice detecting unit detects an injustice concealing operation on the basis of the acquired pre disclosure operation history information and the acquired post disclosure operation history information Step S .

Next in the case that the injustice detecting unit detects the injustice the injustice concealing operation the injustice detecting unit outputs information corresponding to the detected injustice concealing operation that is information related to the injustice Step S .

Next an operation of acquiring the operation history information and an operation of storing the acquired operation history information will be described.

In the case that the history acquiring unit of the monitored device which monitor an operation carried out by the control unit detects any one of one or more than one predetermined operations the history acquiring unit acquires the operation history information related to the detected operation Step S .

Next the history acquiring unit outputs the acquired operation history information to the history storing unit of the injustice detecting device Step S .

The injustice detecting unit refers to the history storing unit and acquires a list of deletion number corresponding to pre disclosure operation history information Step S .

Next the injustice detecting unit makes the usual deletion number which is included in the deletion number list approximate to the normal distribution Step S . The example in shows the normal distribution whose average mu is 1.36 and whose deviation rho times rho is 0.60 .

Next the injustice detecting unit refers to the history storing unit and acquires a checked deletion number for example assumed to be 5 corresponding to post disclosure operation history information Step S . Here the checked deletion number which the injustice detecting unit acquires is the maximum checked deletion number out of plural checked deletion numbers per the unit time which are corresponding to the post disclosure operation history information. Moreover as the checked deletion number the injustice detecting element may acquire an average value of the plural checked deletion numbers per the unit time which are corresponding to the post disclosure operation history information.

Next the injustice detecting unit acquires the T score of the checked deletion number 5 according to the normal distribution related to the usual deletion number Step S . In the case of the example shown in the T score is 75.59 .

Next the injustice detecting unit detects the injustice concealing operation on the basis of a judgment whether the calculated T score is larger than a predetermined value for example 70 Step S .

Next the injustice detecting unit outputs information related to the detected injustice concealing operation for example the deleted file name and the deleted file contents which are included in the post disclosure operation history information whose operation contents indicates erase file Step S .

While it is described to delete the file in the above mentioned exemplary embodiment to count rewriting the file may be used instead of deleting the file. Moreover to count both of deleting the file and rewriting the file may be used.

While the operation of detecting the injustice is described with exemplifying deletion of the file and rewriting of the file which are handled by OS Operating System in the above mentioned exemplary embodiment the injustice may be detected by carrying out the above mentioned operation to deletion of an e mail which is handled by electronic mail software.

A first effect in the exemplary embodiment mentioned above exists in a point that it is possible to detect the injustice carried out by the operation which can not be distinguished from the normal operation.

The reason is that the exemplary embodiment includes the following configuration. That is firstly the audit information disclosing unit discloses the audit information. Secondly on the basis of the pre disclosure operation history information and the post disclosure operation history information with reference to the history storing unit the injustice detecting unit detects the injustice concealing operation that is the operation which indicates that the injustice is carried out previously.

A second effect in the exemplary embodiment mentioned above exists in a point that it is possible to make it unnecessary to prepare a specific rule for example the whitelist and the blacklist which is used for specifying the injustice.

A third effect in the exemplary embodiment mentioned above exists in a point that it is possible to acquire efficiently the appropriate operation history information which is used for detecting the injustice concealing operation.

The reason is that the audit information includes the scheduled time information and the injustice detecting unit uses the post disclosure pre execution operation history information as the post disclosure operation history information.

A fourth effect in the exemplary embodiment mentioned above exists in a point that it is possible to execute the audit efficiently.

The reason is that the file deletion history information which is included in the post disclosure operation history information stored in the history storing unit includes the contents of the deleted file.

A fifth effect in the exemplary embodiment mentioned above exists in a point that it is possible to record the contents of the deleted file efficiently and to save a capacity of the history storing unit .

The reason is that the history acquiring unit acquires the deleted file contents out of the operation history information only in the period of time from the time when the audit information displaying unit displays the audit information until the time when the predetermined predicted period of time elapses and outputs the acquired deleted file contents .

A sixth effect in the exemplary embodiment mentioned above exists in a point that it is possible to detect the injustice which is carried out by a plurality of injustice persons in conspiracy.

The reason is that the injustice detecting unit detects the injustice concealing operation on the basis of the total of the usual deletion numbers and the total of the checked deletion numbers of the plural monitored devices .

A seventh effect in the exemplary embodiment mentioned above exists in a point that it is possible to improve accuracy more in detecting the injustice.

The reason is that the file deletion history information includes information which indicates whether the file deletion is carried out by the user s instruction or not and the injustice detecting unit selects the file deletion history information which indicates that the file deletion is carried out by the user s instruction as objects and detects the injustice concealing operation in the objects.

Next a second exemplary embodiment of the present invention will be described in detail with reference to a drawing. Hereinafter description contents which overlap with the above mentioned description contents are omitted in a range where description of the exemplary embodiment does not become unclear.

The second exemplary embodiment according to the present invention is different from the first exemplary embodiment in the operations of the audit information disclosing unit and the history acquiring unit .

The audit information disclosing unit according to the exemplary embodiment instructs the history acquiring unit of the monitored to start and to stop acquisition of the operation history information .

For example the audit information disclosing unit outputs an acquisition start time and an acquisition stop time to the history acquiring unit . Moreover for example the audit information disclosing unit may output an instruction which indicates to start acquisition at the acquisition start time to the history acquiring unit and may output an instruction which indicates to stop acquisition at the acquisition stop time to the history acquiring unit .

Here the audit information disclosing unit determines the acquisition start time and the acquisition stop time for example on the basis of the predetermined period of time when the operation history information is acquired before disclosure of audit information and a time when the audit information is disclosed. The acquisition start time and the acquisition stop time mean a start time and a stop time of the period of time when the operation history information is acquired before disclosure of the audit information respectively.

Moreover the audit information disclosing unit determines the acquisition start time and the acquisition stop time for example on the basis of the predetermined period of time when the operation history information is acquired after disclosure of audit information and a time when the audit information is disclosed. The acquisition start time and the acquisition stop time mean a start time and a stop time of the period of time when the operation history information is acquired after disclosure of the audit information.

Moreover the audit information disclosing unit determines the acquisition start time and the acquisition stop time for example on the basis of the predetermined period of time when the operation history information is acquired after disclosure of audit information scheduled time information included in the audit information and a time when the audit information is disclosed. The acquisition start time and the acquisition stop time mean a start time and a stop time of a period of time from the time when the audit information is disclosed until the time indicated by the scheduled time information respectively.

The history acquiring unit acquires the operation history information on the basis of the instructions to start and to stop acquisition of the operation history information which are issued by the audit information disclosing unit .

A first effect in the exemplary embodiment mentioned above which includes the effect of the first exemplary embodiment exists furthermore in a point that it is possible to prevent an erroneous detection.

The reason is that the audit information disclosing unit instructs the history acquiring unit to start and to stop acquisition of the operation history information and the history acquiring unit acquires the operation history only in a required period of time on the basis of the instructions.

A second effect in the exemplary embodiment mentioned above exists in a point that it is possible to make a load of the monitored device light.

Next a third exemplary embodiment of the present invention will be described in detail with reference to a drawing. Hereinafter description contents which overlap with the above mentioned description contents are omitted in a range where description of the exemplary embodiment does not become unclear.

The third exemplary embodiment of the present invention is different from the first exemplary embodiment in the operation of the injustice detecting unit . Moreover the exemplary embodiment is different from the first exemplary embodiment in operation history information which the history string unit stores.

The address is an address of the other party of communication. For example in the case that the operation contents indicates receive mail or send mail the address means a mail address of the other party who sends or receives the mail respectively. Moreover for example in the case that the operation contents indicate browse web the address means an address of a web page indicated by URL Uniform Resource Locator .

The communication data contents means data contents of communication with the other party indicated by the address . The communication data contents may include all of or a part of the data contents of the communication. For example in the case that the operation contents indicate receive mail or send mail the communication data contents mean header information a main body data or an attached file of the mail which is sent or received respectively. Moreover for example in the case that the operation contents indicate browse web the communication data contents means received display data for example hypertext and sent input data for example form data .

The injustice detecting unit according to the exemplary embodiment detects injustice on the basis of pre disclosure operation history information and post disclosure operation history information like the injustice detecting unit according to the first exemplary embodiment. Here the injustice detecting unit according to the exemplary embodiment detects an injustice which is carried out previously as a result of detecting that operation which carries out an injustice is not carried out any more.

Next in the case that the injustice detecting unit detects the injustice detect that the operation which carries out the injustice is not carried out any more the injustice detecting unit outputs information corresponding to the operation which is not carried out any more that is information related to the injustice to an outside by use of a means which is not shown in the figure.

Next a specific example of the operation of the injustice detecting unit according to the exemplary embodiment will be described.

For example on the basis of the address of the operation history information which is included in each of pre disclosure operation history information and post disclosure operation history information and which includes the specific operation contents for example send mail the injustice detecting unit detects that the operation which carries out an injustice is not carried out any more.

As a more specific example the injustice detecting unit counts number of pieces of the operation history information which is included in the pre disclosure operation history information and is not included in the post disclosure operation history information and which includes specific operation contents and the specific address .

Next on the basis of a judgment whether the counted number of the pieces of the operation history information is larger than a predetermined value for example 3 or not the injustice detecting unit detects that the operation which carries out the injustice is not carried out any more. That is in the case that the counted number of the pieces of the operation history information is larger than the predetermined value the injustice detecting unit detects the operation history information as the history of the injustice operation which is carried out previously.

In this case the operation history information may include only the operation contents the operation time and the address out of the operation history information .

In the case that the operation contents indicate receive mail or browse web an operation of the injustice detecting unit according to the exemplary embodiment mentioned above is similar to the operation which is carried out in the case of send mail .

An effect in the exemplary embodiment mentioned above which includes the effect according to the first exemplary embodiment exists furthermore in a point that it is possible to detect that an injustice is carried out even in the case that an active operation for example injustice concealing operation is not carried out.

The reason is that on the basis of the pre disclosure operation history information and the post disclosure operation history information the injustice detecting unit can detect that a specific operation is not carried out any more.

Next a fourth exemplary embodiment of the present invention will be described in detail with reference to a drawing. Hereinafter description contents which overlap with the above mentioned description contents are omitted in a range where description of the exemplary embodiment does not become unclear.

The audit information disclosing unit is different from the audit information disclosing unit according to the first exemplary embodiment in a point of notifying an outside of audit information by use of a mail or the like. The audit information disclosing unit may make for example a display unit not shown in the figure display the audit information.

Similarly to the effect in the first exemplary embodiment an effect in the exemplary embodiment mentioned above exists in a point that it is possible to detect an injustice carried out by the operation which can not be distinguished from the normal operation.

The reason is that the audit information disclosing unit discloses the audit information and the injustice detecting unit detects the injustice with reference to the history storing unit on the basis of the pre disclosure operation history information and the post disclosure operation history information.

Next a fifth exemplary embodiment according to the present invention will be described in detail with reference to a drawing. Hereinafter description contents which overlap with the above mentioned description contents are omitted in a range where description of the exemplary embodiment does not become unclear.

The fifth exemplary embodiment according to the present invention is corresponding to an exemplary embodiment which makes a computer execute a predetermined process according to the fourth exemplary embodiment by use of a program.

Similarly the injustice detecting device according to the first to the third exemplary embodiments may be the injustice detecting device which includes a general purpose computer as shown in .

The audit information disclosing unit and the injustice detecting unit of the injustice detecting device shown in are corresponding to CPU the disk and the storage unit . Moreover the history storing unit of the injustice detecting device is corresponding to the storage unit .

CPU makes an operating system not shown in the figure work to control a whole operation of the injustice detecting device . Moreover CPU reads a program for example program to make the injustice detecting device carry out the operation of the injustice detecting device which is defined by the flowcharts shown in and data for example from the recording medium mounted on the disk . Then CPU makes the read program and data stored in the storage unit . Then CPU executes various processes as the audit information disclosing unit and the injustice detecting unit shown in according to the read program and on the basis of the read data. Similarly CPU executes various processes as the audit information disclosing unit and the injustice detecting unit shown in .

Here CPU may download the program and the data into the storage unit from an external computer not shown in the figure which is connected with a communication network not shown in the figure .

CPU transfers the program which is stored in the disk for example to the storage unit and executes the same process as the audit information disclosing unit and the injustice detecting unit carry out on the basis of the transferred program.

The disk may be for example an optical disk a flexible disk a magnetic optical disk an external hard disk and a semiconductor memory and may include the recording medium . The disk records the program so that the program may be computer readable. Moreover the disk may record data so that the data may be computer readable. The disk may include the history storing unit .

The storage unit stores the transferred program. Moreover the storage unit stores the operation history information like the history storing unit .

The communication unit is included in each of the audit information disclosing unit and the injustice detecting unit .

As described above function blocks of the injustice detecting device shown in and the injustice detecting device shown in are realized by the injustice detection device which has a hardware configuration shown in . However a means to realize each unit of the injustice detecting device is not limited to the above. That is the injustice detecting device may be realized by one device which has a configuration combined physically or may be realized by a plurality of devices which are separated physically each other and are connected each other through a wire line or a wireless line.

Here the recording medium which records a code of the above mentioned program may be supplied to the injustice detecting device and CPU may read the code of the program which is stored in the recording medium and carry out the program. Or CPU may store the code of the program which is stored in the recording medium in the storage unit and or the disk . That is the present exemplary embodiment includes an exemplary embodiment of the recording medium which stores temporarily or non temporarily the program software executed by the injustice detecting device CPU .

An effect in the exemplary embodiment mentioned above is the same as one in the first to the fourth exemplary embodiments.

The reason is that the general purpose computer executes the same process as each element of each exemplary embodiment carries out.

Here it is described in each exemplary embodiment mentioned above that the monitored device is for example the server PC the terminal or another information processing device. However the monitored device may be a management device for entering and leaving a room or a facility management device. These devices may detect the injustice on the basis of the pre disclosure operation history information and the post disclosure operation history information as described in each exemplary embodiment.

The injustice detecting device according to each exemplary embodiment mentioned above may be mounted on the monitored device or may be included in the monitored device. is a block diagram showing an example of the monitored device including the injustice detecting device.

While the invention of the present application has been described with reference to the exemplary embodiment as mentioned above the invention of the present application is not limited to the above mentioned exemplary embodiment. Various changes which a person skilled in the art can understand can be added to the composition and the detail of the invention of the present application in the scope of the present invention.

This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2011 107300 filed on May 12 2011 the disclosure of which is incorporated in its entirety by reference.

