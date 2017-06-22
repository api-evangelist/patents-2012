---

title: Method and system for provisioning software
abstract: The present invention provides a unified provisioning environment, which comprehensively manages the tasks related to software provisioning. In particular, the present invention manages software provisioning using a hierarchy of commands. The lowest level in the hierarchy comprises distribution commands, which primarily handle base operating system specific tasks of provisioning. The second level comprises profile commands, which associate a configuration file, such as a Linux kickstart file, with a distribution and optionally allow for customization. The third level comprises system commands, which associate remote systems that are involved with the provisioning of the software. The fourth level comprises repository commands, which address configurations and tasks related to updating the software, remote installation procedures, and optionally customizing the software.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08271975&OS=08271975&RS=08271975
owner: Red Hat, Inc.
number: 08271975
owner_city: Raleigh
owner_country: US
publication_date: 20120217
---
This patent application is a continuation of U.S. Non Provisional application Ser. No. 11 763 315 filed Jun. 14 2007 which claims the benefit under 35 U.S.C. 119 e of U.S. Provisional Application No. 60 917 917 filed May 14 2007 both of which are herein incorporated by reference.

Software provisioning is the process of selecting a target machine such as a server loading the appropriate software operating system device drivers middleware and applications and customizing and configuring the system and the software to make it ready for operation. Software provisioning can entail a variety of tasks such as creating or changing a boot image specifying parameters e.g. IP address IP gateway to find associated network and storage resources and then starting the machine and its newly loaded software. Typically a system administrator will perform these tasks using various tools because of the complexity of these tasks. Unfortunately there is a lack of provisioning control tools that can adequately integrate and automate these tasks.

Furthermore none of the known provisioning control tools provide virtualization installation support unified with other provisioning types on a target machine. Virtualization install support requires knowledge of additional parameters and to date cannot be automated for software rollouts with the current available tools.

Ideally provisioning control tools would be able to handle the various types of provisioning. For example many system administrators in data centers utilize Preboot Execution Environment PXE installations. However other forms of provisioning such as virtualization installations and re installations are also common. Accordingly it would be desirable to provide provisioning control tools that can handle different types of installations.

The present invention provides a unified provisioning environment which comprehensively manages the tasks related to software provisioning. In particular the present invention manages software provisioning using a hierarchy of commands. The lowest level in the hierarchy comprises distribution commands which primarily handle base operating system specific tasks of provisioning. The second level comprises profile commands which associate a configuration file such as a Linux kickstart file with a distribution and optionally allow for customization. The third level comprises system commands which associate remote systems that are involved with the provisioning of the software. The fourth level comprises repository commands which address configurations and tasks related to updating the software remote installation procedures and optionally customizing the software.

The unified provisioning environment provides several capabilities and advantages over the known provisioning solutions. For example the present invention is capable of handling a variety of forms of installations such as PXE virtualization and re installations.

The present invention enables integrating virtualization into a PXE provisioning infrastructure and provides several options to reinstall running machines as well. The present invention can integrate mirroring of package repositories with the provisioning process so that a provisioning server may serve as a central mirror point of contract for all of an organization s software needs. In the present invention mirrored repositories can automatically be used by provisioned systems without additional setup.

Reference will now be made in detail to the exemplary embodiments of the invention. The present invention may be applied to provisioning any form of software such as Windows systems UNIX systems and Linux systems. For purposes of illustration the present invention will now be explained with reference to implementation to Linux systems such as Fedora and Red Hat Enterprise Linux by Red Hat Inc.

Accordingly the description will first provide some general information about Linux installations. Next is presented to explain an exemplary Linux type system of the present invention. Several examples of the hierarchy of commands will then be explained. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts

Turning now to the provisioning of Linux systems many system administrators use what is known as the kickstart installation method. Kickstart files are files that specify the intended configuration of the software being provisioned. Kickstart files can be kept on a server and can be read by individual computers during the installation. This installation method allows the use a single or relatively few standard kickstart files to install Linux on multiple machines making it ideal for network and system administrators.

The kickstart file is a simple text file containing a list of items each identified by a keyword. In general a kickstart file can be edited with any text editor or word processor that can save files as ASCII text. One skilled in the art will recognize that the present invention may be applied to non kickstart files in Linux provisioning. For example configuration files such as AutoYAST Answer files used in Novell SuSe Linux and Sun Solaris Jumpstart files may also be used by the present invention.

Typically a kickstart file is copied to the boot disk or made available on the network. The network based approach is most commonly used as most kickstart installations for Linux systems tend to be performed via a network using NFS FTP or HTTP on networked computers. Administrators also find it desirable that kickstart installations can be performed using a local CD ROM or a local hard drive.

Using kickstart files a system administrator can create a single file containing the parameters that are needed to complete a typical Linux installation. For example kickstart files specify parameters related to language selection mouse configuration keyboard selection boot loader installation disk partitioning network configuration NIS LDAP Kerberos Hesiod and Samba authentication firewall configuration and package selection.

Referring now to an exemplary system that is consistent with the present invention is shown. The system may comprise a provisioning server a code repository which provides access to distributions and a set of installation templates a set of exception plugins a helper client running on target machines a scheduler a provisioning database which comprises a distribution tree list and template list . Each of these components will now be further described.

Provisioning server from herein referred to as a cobbler is responsible for serving as a extensible markup language remote procedure call XMLRPC handler linking to or mirroring install distribution trees and a configuration database hosting kickstart templates and hosting plugins. Cobbler server may be implemented as software such as Python code installed on a boot server machine and provides a command line interface for configuration of the boot server. In addition cobbler server may make itself available as a Python application programming interface API for use by higher level management software not shown . Cobbler server supports provisioning via PXE virtualization and re provisioning. As will be described later the last two modes are performed with the assistance of a helper client .

Code repository is responsible for hosting distributions and . Code repository may be implemented using well known components of hardware and software.

Distributions and are bundles of software that is already compiled and configured. Distributions and may be in the form of either rpm deb tgz msi exe etc. formats. As Linux distributions distributions and are bundles of software that comprise the Linux kernel the non kernel parts of the operating system and assorted other software. Distributions and may take a variety of forms from fully featured desktop and server operating systems to minimal environments.

Installation templates are any data structure or processing element that can be combined with a set of installation configurations and processed to produce a resulting configuration file such as a kickstart file.

Exception plugins is software that interacts with cobbler server to customize the provisioning of software. In general exceptions plugins are intended to address infrequent customization needs.

Helper client known as koan which stands for kickstart over a network may assist cobbler server . Koan allows for both network provisioning of new virtualized guests and destructive provisioning of any existing system. When invoked koan requests profile information from a remote boot server that has been configured with cobbler server . In some embodiments what koan does with the profile data depends on whether it was invoked with virt or replace self.

In addition koan enables replacing running systems as well as installing virtualized profiles. Koan may also be pushed out to systems automatically from the boot server. In some embodiments helper client is also written in Python code to accommodate a variety of operating systems machine architectures etc.

Target machines represent the particular machines to which software provisioning is directed. Target machines may represent a wide variety of devices.

Although shows relatively few number of target machines the present invention is capable of managing a wide range environments such as datacenters with thousands of machines or server pools with just a few machines.

Provisioning database serves as a data storage location for holding data used by cobbler server . For example as shown provisioning database will typically comprise distribution tree list and template list .

Distribution tree list provides an inventory of distributions and that are hosted or mirrored by cobbler server . Template list provides an inventory of templates that are hosted by cobbler server .

Now that an exemplary system for the present invention has been described some of the commands and provisioning processes supported by the present invention will now be described. As noted above cobbler server manages provisioning using a hierarchical concept of distribution commands profile commands system commands and repository commands. This framework enables cobbler server to abstract the differences between multiple provisioning types installation reinstallation and virtualization and allows installation of all three from a common platform. This hierarchy of commands also permits cobbler server to integrate software repositories with the provisioning process thus allowing systems to be configured as a mirror for software updates and third party content as well as distribution content. The present disclosure will now explain the hierarchy of commands further.

Distributions contain information about base operating system tasks such as what kernel and initrd are used in the provisioning along with other information such as required kernel parameters. Profiles associate one of distributions and with a kickstart file and optionally customize it further for example using plugins . Systems commands associate a hostname IP or MAC with a distribution and optionally customize the profile further. Repositories contain update information such as yum mirror information that cobbler server uses to mirror repository . Cobbler server can also manage generate DHCP configuration files using templates .

Of note cobbler server uses a provisioning environment that is fully templated allowing for kickstarts and PXE files to be customized by the user. Cobbler server uses the concept of profiles as an intermediate step between the operating system and the installed system. A profile is a description of what a system does rather than what it is installed with. For instance a profile might describe a virtual web server with X amount of RAM Y amounts of disk space running a Linux distribution Z and with an answer file W.

Cobbler server provides a command line interface to configure a boot server in which it is installed. The format of the cobbler server commands is generally in the format of cobbler command subcommand arg1 arg2 . An exemplary process flow will now be described in which a user may provision software via this command line interface.

In phase 1 a user may use various commands of the present invention to specify distributions and install trees hosted by code repository such as a distribution from distributions or . A user may add or import a distribution or import it from installation media or an external network location.

In some embodiments the user may use a manual add command generally of the form cobbler distro add name string kernel path initrd path kopts string ksmeta string arch x86 x8664 ia64 breed redhat suse where

 Kopts is an optional parameter that sets kernel command line arguments that the distro and profiles systems dependent on it will use. For example kopts foo bar baz 3 asdf is an example of a kopts parameter.

 Ksmeta is an optional parameter that sets kickstart variables to substitute thus enabling kickstart files to be treated as templates. For example ksmeta foo bar baz 3 asdf is example of a ksmeta parameter. Templating is further described below.

 Breed specifies a general type of the Linux system distribution such as Red Hat or Novell SuSE. In some embodiments the default for breed is redhat which may be a suitable value for Fedora and Centos as well. Specifying suse allows the kickstart file parameters to be treated instead like AutoYaST answer files such that the proper parameters for SuSE answer files are put on the kernel command line. Support for other types of distributions is also possible. The file used for the answer file regardless of distro breed is the value used for kickstart when creating the profile.

In order to import a distribution cobbler server can auto add distributions and profiles from remote sources whether this is an installation media such as a DVD an NFS path or an rsync mirror. When importing a rsync mirror cobbler server will try to detect the distribution type and automatically assign kickstarts. By default in some embodiments it will provision by erasing the hard drive setting up eth0 for DHCP and using a default password. If this is undesirable an administrator may edit the kickstart files in etc cobbler to do something else or change the kickstart setting after cobbler server creates the profile.

In phase 2 a user may map profiles to the distributions and map systems to the profiles using profile commands and systems commands of the present invention. As noted above a profile associates a distribution to additional specialized options such as a kickstart automation file. In cobbler server profiles are the unit of provisioning and at least one profile exists for every distribution to be provisioned. A profile might represent for instance a web server or desktop configuration.

In general the command for adding a profile may be of the form cobbler profile add name string distro string kickstart url kopts string ksmeta string virt file size gigabytes virt ram megabytes where 

 Kickstart is the local filesystem path to a kickstart file. If this parameter is not provided the kickstart file will default to etc cobbler default.ks or whatever is set in var lib cobbler settings . If this file is initially blank default kickstarts are not automated. However an administrator can change the default.ks for an automated installation.

 Repos is an optional parameter that sets a space delimited list of all the repos created with the cobbler repo add and cobbler reposync commands that this profile can make use of during kickstart installation. For example repos fc6i386updates fc6i386extras is one example of a repos parameter.

Next a user may map systems to profiles using system commands of the present invention. In general systems commands assign a piece of hardware with cobbler server to a profile. Systems can be defined by hostname Internet Protocol IP address or MAC address. When available use of the MAC address to assign systems may be preferred.

The general format for specifying Systems commands to cobbler server may be of the form cobbler system add name ip mac hostname profile string kopts string pxe address string ksmeta string where 

 Name is the name that is either a currently resolvable hostname an IP address or a MAC address. When defining Virtualized systems using a MAC address causes the Virt MAC address to be used for creation. In some embodiments the name may be default . In this situation the PXE will use the specific profile set for unconfigured systems otherwise it will fall through to local boot.

 Pxe address is a feature that may be used to generate the dhcpd.conf file. This setting sets a certain hostname or IP to a given MAC address. This corresponds to the fixed address field in dhcpd.conf.

In phase 3 the user may map repositories and profiles using repository commands of the present invention. In general repository commands address configurations and tasks related to updating the software remote installation procedures and optionally customizing the software. These repository commands may also specify mirroring of the provisioned software. Repository mirroring allows cobbler server to mirror not only install trees and but also optional packages third party content and updates. Mirroring may be useful for faster more up to date installations and faster updates or providing software on restricted networks.

The command for specifying a Repository is generally of the form cobbler repo add mirror url name string local filename string where 

 Mirror is the address of the yum mirror. This can be an rsync URL an ssh location or a http or ftp mirror location. For example rsync yourmirror.example.com fedora linux core updates 6 i386 for rsync protocol http mirrors.kernel.org fedora extras 6 i386 for http user yourmirror.example.com fedora linux core updates 6 i386 for SSH .

 Name is the save location for the mirror. This name corresponds with values given to the repos parameter of cobbler profile add . If a profile has a repos value that matches the name here that repo can be automatically set up during provisioning. This means that if supported the repo can be used during kickstart install and either way it can be automatically configured on the clients.

 Local filename specifies for kickstarts containing the template parameter yum config stanza what files to populate on provisioned clients in etc yum.repos.d. In other words if this value is foo the repo would be installed on provisioned clients as etc yum.repos.d foo.repo .

Cobbler server may also include other administrative features such as allowing the user to view their provisioning configuration or information tracking the status of a requested software installation. For example the cobbler sync can be used to repair or rebuild the contents tftpboot or var www cobbler when something has changed. The command brings the filesystem up to date with the configuration as understood by cobbler server . The cobbler sync function may be run whenever files in var www cobbler are manually edited or when making changes to kickstart files.

The following example shows a sequence of commands to create a provisioning infrastructure from a distribution mirror. Then a default PXE configuration is created so that by default systems will PXE boot into a fully automated install process for that distribution. A network rsync mirror or a mounted DVD location. Accordingly the sequence of commands may be 

In this next example the administrator uses a local kernel and initrd file already downloaded and shows how profiles would be created using two different kickstarts one for a web server configuration and one for a database server. Then a machine is assigned to each profile. Accordingly the sequence of commands may be 

cobbler profile add name fc5webservers distro fc5 i386 kickstart dir4 kick.ks kopts something to make my gfx card work 42 some other parameter foo 

The following example shows how to set up a repo mirror for two repositories and create a profile that will auto install those repository configurations on provisioned systems using that profile. Accordingly the sequence of commands would be 

cobbler profile add name p1 distro existing distro name kickstart etc cobbler kickstart fc6.ks repos fc6i386updates fc6i386extras 

In addition to normal provisioning cobbler server may support yet another option called enchant . Enchant takes a configuration that has already been defined and applies it to a remote system that might not have the remote helper program installed. Users might want to use this command to replace a server that is being repurposed or when no PXE environment can be created. Thus the enchant option allows the remote helper client to be executed remotely from cobbler server .

If cobbler server is configured to mirror certain repositories it can then be used to associate profiles with those repositories. Systems installed under those profiles will be auto configured to use these repository mirrors in etc yum.repos.d and if supported these repositories can be leveraged. This can be useful for a large install base fast installation and upgrades for systems are desired or software not in a standard repository exists and provisioned systems are desired to know about that repository.

Cobbler server may also keep track of the status of kickstarting machines. For example the cobbler status will show when cobbler server thinks a machine started kickstarting and when it last requested a file. This may be a desirable way to track machines that may have gone inactive during kickstarts. Cobbler server may also make a special request in the post section of the kickstart to signal when a machine is finished kickstarting.

For virt cobbler server will create new virtualized guests on a machine in accordance to the orders from cobbler server . Once finished an administrator may use virsh and xm commands on the guest or other operations. Cobbler server automatically names domains based on their MAC addresses. For re kickstarting replace self cobbler server will reprovision the system deleting any current data and replacing it with the results of a network install.

Referring now back to in phase 4 cobbler server configures boot methods for the provisioning requested by the user. For example cobbler server may configure a PXE environment such as a network card BIOS. Alternatively cobbler server may compile and configure information for koan client . Cobbler server may also optionally configured DHCP and DNS configuration information.

In phase 5 cobbler server serves the request of koan client . Koan client may acknowledge the service of information of cobbler server and then may initiate installation of the software being provisioned. Processing now flows to phase 6 in which koan client may either install the requested software e.g. replace the existing operating system or install a virtual machine.

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. For example the cobbler may contain a templating feature that allows a single kickstart file to be customized on a per system basis. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. For example the cobbler may contain a templating feature that allows a single kickstart file to be customized on a per system basis. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

