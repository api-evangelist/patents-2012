---

title: Method and system for migration of multi-tier virtual application across different clouds hypervisor platforms
abstract: A method and system for migration of multi-tier virtual application across different clouds hypervisor platforms. The principal object of the embodiment is to provide migration of multi-tier virtual application from one vendor to another vendor cloud platforms. Another object of the embodiment is to convert entire multi-tier virtual application of a source vendor cloud platforms, along with the virtual machines, configuration and properties into a format suitable for a destination vendor cloud platforms. Another object of the embodiment is to verify the migrated application after completion of conversion and migration.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09183032&OS=09183032&RS=09183032
owner: HCL Technologies Limited
number: 09183032
owner_city: Chennai, Tamil Nadu
owner_country: IN
publication_date: 20121018
---
The present application is based on and claims priority from IN Application Number 2853 CHE 2012 filed on Jul. 13 2012 the disclosure of which is hereby incorporated by reference herein.

This application relates to multi tier application migration across different cloud computing hypervisor platforms.

With advances in hardware virtualization and computing along with availability of high capacity networks cloud computing is emerging as the future of computing technology. Cloud computing provides access to third party software and services on web and generally has a pay as per usage basis system. End users access the cloud applications using appropriate application programming interfaces.

There are several vendors providing cloud platforms. Even though cloud computing provides end users with a lot of advantages the lack of interoperability between different cloud vendors restricts end users from using services of other cloud vendors. Each vendor currently in the fray have their own formats and data model for the application deployment and management in cloud leading to vendor locking and prohibits user from using cloud services of other vendors. Also due to lack of standardization in cloud computing each vendor cloud operates and stores applications and data in different manner. The technology used in each vendor cloud platform is also different. Users find it difficult to process migrate share applications between two clouds. Although migration tools are available for migrating virtual machines from one hypervisor or cloud to a destination hypervisor or cloud complex multi tier applications may not migrate completely as completely different formats may be used in the destination hypervisor or cloud and applications may be running on multiple virtual machine with different properties and configurations.

The principal object of the embodiment is to provide migration of multi tier virtual application from source cloud platform along with the Application configuration and properties into a format suitable for a destination vendor cloud platform.

Another object of the embodiment is to verify the migrated application after completion of conversion and migration.

Accordingly the embodiment provides a method for migrating at least one application from a source cloud to a target cloud using a migration server the method comprising of creating a source application package by the source cloud wherein the source application package comprises of all virtual machines and configurations associated with the migrating application exporting the source application package by the source cloud to the migration server converting the source package application into a target application package compatible with target cloud by the migration server sending the target application package to the target cloud by the migration server and launching and verifying the migrated application by the migration server.

Also disclosed herein is a migration server for migrating at least one application from a source cloud to a target cloud the migration server comprising of a virtual machine migration tool for migrating virtual machines a mapping table for finding equivalence of Application Properties and Configurations format elements between source and target clouds and conversion tool for constructing the source applications package into a target application package compatible with target cloud.

These and other aspects of the embodiments herein will be better appreciated and understood when considered in conjunction with the following description and the accompanying drawings. It should be understood however that the following descriptions while indicating preferred embodiments and numerous specific details thereof are given by way of illustration and not of limitation. Many changes and modifications may be made within the scope of the embodiments herein without departing from the spirit thereof and the embodiments herein include all such modifications.

The embodiments herein the various features and advantageous details thereof are explained more fully with reference to the non limiting embodiments that are illustrated in the accompanying drawings and detailed in the following description. Descriptions of well known components and processing techniques are omitted to not unnecessarily obscure the embodiments herein. The examples used herein are intended merely to facilitate an understanding of ways in which the embodiments herein may be practiced and to further enable those of skill in the art to practice the embodiments herein. Accordingly the examples should not be construed as limiting the scope of the embodiments herein.

The overall computing environment can be composed of multiple homogeneous and or heterogeneous cores multiple CPUs of different kinds special media and other accelerators. The processing unit is responsible for processing the instructions of the algorithm. Further the plurality of process units may be located on a single chip or over multiple chips.

The algorithm comprising of instructions and codes required for the implementation are stored in either the memory unit or the storage or both. At the time of execution the instructions may be fetched from the corresponding memory and or storage and executed by the processing unit .

In case of any hardware implementations various networking devices or external I O devices may be connected to the computing environment to support the implementation through the networking unit and the I O device unit .

The embodiments disclosed herein can be implemented through at least one software program running on at least one hardware device and performing network management functions to control the elements. The elements shown in include modules which can be at least one of a hardware device or a combination of hardware device and software module.

The foregoing description of the specific embodiments will so fully reveal the general nature of the embodiments herein that others can by applying current knowledge readily modify and or adapt for various applications such specific embodiments without departing from the generic concept and therefore such adaptations and modifications should and are intended to be comprehended within the meaning and range of equivalents of the disclosed embodiments. It is to be understood that the phraseology or terminology employed herein is for the purpose of description and not of limitation. Therefore while the embodiments herein have been described in terms of preferred embodiments those skilled in the art will recognize that the embodiments herein can be practiced with modification within the spirit and scope of the embodiments as described herein.

