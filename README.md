# Notes-for-SMW
- ```++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++.>+++++.<<++.>>++++.++++++++++++.<<.>>-----------.-------------.++++++++++++.--------.<<.>>++++.++++++++++.<<.>+++++++++++.>--------------.----.+++++++++++++.<<+.-.>------------------.>.----------.<<.>>++++++++++++++++.------------.---.++++++++++++++.--------------.<<.>>----.+++++++++++++++++.-------------.<<.>++++++++++++++++++.------.++++++++++.<.>>+++++++++.+.+++++.<++++++++++++++.>-.```

# Topic 1


# Introduction to windows server 2016

- Safer computing requires:
    - Change in the bhavior of managment, programmers and users
    - Will have to make secure computing a priority
    - Will have to write secure operating systems and application but it should not compromise on productivity
    - Companies will have to train users to always keep security in mind

## Different areas of security that microsoft has decided to make signigicant investment on:
- Isolation and resiliency
    - The idea is to separate and split a computer system into smaller pieces and make sure that each piece is separated from the others so that if in the case that one of the system is compromised or is malfunctioning the other surrounding systems may not be affected.
    - Inclusion of better file attachment handling in outlook express and windows messenger instant messaging 
    - Compilation of core windows components with the most recent version of compiler technology
    - Introduction of exchange edge services
        - These are designed for e-mail protections, enhanced security and management of junk email for exchange
    - To create and produce an integrated set of protection technologies
        - E.g mirosoft security essentials (MSE)
            - Windows defender
    - To have smart screening technologies
        - An intelligent spam-filtering solution
- Updating 
    - Updating is the primary way to protect against security vulnerabilites
    - Microsoft's monthly release of software updates
    - Various products incorporated by microsoft to make the ipdates seamless include:
        - System center configuration manager(SCCm)
    - Microsoft Baseline security analyzer(MBSA)
    - Windows software update services  (WSUS)
- Quality
    - Microsoft's commitment towards quality:
    - Use of best practices in all phases of software developments
    - Developments of new interenal tools that automatically check code for common errors
    - Thorough testing of software before its release
- Access control and authentication
    - The areas in which microsoft has made changes to improve access control and authentication:
        - Passwords
        - Smart cards
        - Public key infrastructure (PKI)
        - Internet Protocol Security (IPSec)
        - Active directory Rights Management Services (AD RMS)

# Trustworthy computing
- Microsoft Trustworthy computing memo
    - Development Emphasis: Security over features
    - Strategy to compete against others companies
- A way to ensure safe and reliable computing
- Some requirements of trustworthy computing includes:
    - Computers itself need to be reliable
    - The software that operates those machines must be equally reliable
    - The service components that are included in the machine and the software need to be dependable



- The Dimensions on which microsoft objective of a trustworthy computing relies on the Goals:
    - Security
    - Privacy
    - Business Integrity
- Means:
    - Security by design, by default and by deployment
    - Privacy/fair information principles
    - Availability, manageability and accuracy
    - Usability, responsiveness and transparency

- Trustworthy Computing is a long term initiative
- It is currently expanding to the cloud
- trusted cloud initiative are based on the four foundational principles
    - Security
    - Privacy
    - Compliance
    - Transparency


# Microsoft steps to implement and maintain security
- The plan to train windows engineers in:
    - Writing secure code
    - Specialized testing techniques
    - Threat modeling
    - To write documentation with security in mind

# Common language runtime

- Runtime environment for the .NET Framework
- manages the running of .NET programs regardless of the programming language they were written in

- There are goals for the design of the common language runtime:
    - Some of these include:
        - to simplify the development environment
        - To get a simpler and safer deployment 
        - To get rid of the concept of registry( Using XML configuration files instead )
        - To use zero-impact installation


# Windows server 2016 Essentials edition:
- It supports a maximun of :
    - 25 users
    - 16.8 million connections for file sharing through server message block(SMB) services
    - 2 central processor sockets
    - 50 Remote desktop connections
    - 50 Routing and remote access connections
    - This addition cannot join a domain, other than to migrate files and data from one server to another
    - It provides the user with most but not all server roles
        - It does not provide a role for hosting virtual machines and cannot provide cloud services
        
 # Topic 2 
 
 ## Purpose of server manager
- It consolidates administrative functions to make a server easier to manage

### Two common roles for a windows server 2016
- File and storage services role
    - Focuses on sharing files from the server or using the server to coordinate and simplify sharing through Distributed File system( DFS )
- Print and Document Services role
    - Used to manage network printing services and it can offer one or more network printers connected to the network through the server itself

### Best practice analyzer
- you can run the BPA to determine if one of more roles are installed and configured to follow the guidelines recommended by Microsoft
- When problems are found, the analysis of each role yields a report htat shows threee levels of severity:
    - Information 
    - Warning
    - Error

### How to run General steps for running BPA:
- Open Server Manager
- Click local server in the left pane
- In the right pane, scroll to best practices analyzer
- Click the down arrow for TASKS
- Click the start BPA scan and wait for the scan to complete
- Read the results for the scan


## Using Sigverif to verify system and critical files
- Sigverif verifies the system and critical files to determine if they have a signature
    - Only scan files and does not overwirte inappropriate filles, enabling you to use the tool while users are logged on
- After the scan is complete, the resilts are written to a log file, called sigverif.txt
- If the tool finds a file without a signature that you believe needs to be replaced
    - You can replace the file when users are off the system

## Understanding the Window Server 2016 registry
- Precautions when working with the registry
    - Establish a specific group of administrators who have privileges to openand modify the registry
    - Only make changes to the registry as a last resort
    - Regularly back up the registry as part of backing up the windows server window folder
    - Never copy the resgistry from one windows-based system over the registry of a different system

# Registry Contents
- The registry is hierarchical in structure
    - Its made up of keys, subkeys, and entries
- Registry key
    - A Category or division of information within the Registry
- Registry subkeys
    - A single key may contain one or more lower-level keys
- Registry entry
    - A data parameter associated with a software or hardware characteristic under a key or subkey
- Root Key
    - A primary or highest level category of data contained in the registry
    - Total of 5 root keys

## HKEY_LOCAL_MACHINE
- HKEY_LOCAL_MACHINE root key
    - Contain information on every hardware component in the server
    - It inclides information about what drivers are loaded and their versioin levels, what IRQ lines ae used, setup configurations, the BIOS version and more
- A few subkeys are stored as a set, called hives, cuz they hold related info


## HKEY_CURRENT_USER root key
- Contains informations about the desktop setip for the account presently signed in to the server console
- is an alias for HKEY_USERS logged-on user's hive
- It contains profile info for each user who has logged onto the computer before
- Each profile is listed under this root key
- Within each user profile is info identical to that viewed within the KEY_CREENT_USER root key
    - The profile used when you are signed in is one of the profiles stored under HKEY_USERS

## HKEY_CLASSES_ROOT
- HKEY_CLASSES_ROOT key
    - It holds data to associate file extensions with programs
    - is an alias for HKEY_LOCAL_MACHINE\software\Classes
- Assosciations exist for executable files,text files, graphic files, clipbard files and audio

## HKEY_CURRENT_CONFIG root key
- Has information about the current hardware profile

# Active Directory Basics

- What is an active directory?
    - It is a service that houses information about all network resources and devices such as servers and printers or even user accounts.
- Directory service
    - Responsible for providing a central listing of resources and ways to quickly find and access specific resources.
- ``` Domain Controllers ```
    - These are servers that have the 'active directory directory sevices' server roles installed
- ``` Memberservers```
    - Servers on a network managed by Active directory that do not have active directory installed
- ``` Domain ```
    - They are container that holds information about all network resources that are grouped within it 
    - Every resource is called an object

- Multimaster replication
    - Each domain controller is equal to every other one in the same active directory

## The three general concepts important for understanding active directory
- Schema
    - It is a componenet of the Active Directory which contains rules for object creation within an active directory forest. It is a list of definitions about active directory objects and information about those objects that are stored in active Directory
    ### Example of object classes
        - User accounts
        - Computers
        - Groups
    ### Caveat
        - Replication between Domain Controllers require the involved parties to be having an identical active directory schema
- Global catalog
    - Stores information about every object within a forest
    - The first DC configured in a forest becomes the global catalog server
    - Global catalog server
        - Store a full replica of every object within its own domain in the forest 
    - The global catalog server enables forest-wide searches of data
    ### Purpose of global catalog serves the following purposes:
        - Serving as the central storehouse of key object information in a forest that has multiple domains
        - Providing lookup and access to all resources in all domains
        - Providing replication of key active directory elements
        - Keeping a copy of most used attributes for each object for  quick access
    ### By default, the first DC in the forst is automatically designated as the global catalog server
        - You have the option of configuring another DC to be a global catalog server as well as designating multiple DCs as global catalog servers
- Namespace
    - There must be a DNS server on the network that Active directory can access
    - A namespace is a logical area on a network that contains directory services and named objects and it has the ability to perform name resolution
    
# Containers in Active Directory
- Active Directory has a treelike structure 
- The hierarchical elements, or containers, of Active Directory includes:
    - Forests
    - Trees 
    - Domains
    - Organizational Units 
    - Sites


# Interim Recap
- Active Directory enables
    - Providing an information repository and lookupservice for users and applications. 
    - Implementing an authentication and authorization strategy for resource sharing across a network reousrce.
    - Organizaing objects of a network into a non-physical hierarchical structure
        - To support a more well-structured management approach for security, performance and resource sharing


## active directory structure
- Active directory logical structure
    - Forests 
        - Consists of one or more Active Directory trees that are in a common relationship
        ### They have the following characteristics:
            - The trees can use a disjointed namespace
            - All trees use the same schema
            - All trees use the same global catalog
            - Domains enable administrator of commonly associated objects, such as accounts and other resources, within a forest
            - Two-way transitive trusts are automatically confugred between domains within single forest
            - A forest provides a means to relate trees that use a contigous namespace in domains within each tree.
            - The advantage of joining trees into one forest is that all domains will share the same schema and global catalog
    - Trees 
        - Contains one or more domains that are in a common relationship
        - Domains are represented in a contiguous namespace and can be in a hierarchy
        - Two-way trust relationships exist between parent domaains and child domains
        - All domains in a single tree use the same schema for all types of common objects
        - The domains within a tree are in what is called a kerberos transitive trust relationship
            - Which is basically a mutual trust between parent domains and child domains
        - Domain functional levels refers to the windows server operating systems on domain controllers and the domain-specific functions they support
    - Domains 
        - All domains use the same global catalog
        - A domain is a grouping of objects that typically exists as a primary container within active directory
    - Organizational unit 
        - Offers a way to achieve more flexibility in managing resources than through domain administration alone
        - An OU is a grouping of 
    - Site Objects
- Active Directory physical structure
    - Domain Controller
    - Sites ( actual physical network )
        - A site is a TCP/IP based concept within the active directory that is linked to IP subnets
        - It reflecs one or more interconnected subnets
        - It reflects the physical aspect of the network
        - Is used for DC replication
        - Is used to enable a client to access the DC that is physically closest
        - Is composed of only two types of objects,servers and congfiguration objects
        ### Reasons to define a site
            - It connects to the network server more efficiently
            - DC replcation is more efficient when AD knows where the DC's locations are


# Active Directory Guidelines
- Keep AD as simple as possible (plan first)
- Implement least number of domains (1 is ideal)
- Use OUs to reflect organization's structure
- Create only necessary OUs
- Dont build AD with more than 10 levels of OUs
- Use domains as partitions in forests
- Implement multiple trees and forests only as necessary
- Use sites in situations where there are multiple IP subnets and multiple geographic locations


# Using the security configuration wizard
- Through the SCW, you can:
    - Disable unnecessary services and software
    - Close network communication ports and resources that aren't in use
    - Examine Share files and folders to manage networks access via protocols
    - Confiure audit policy
- The security configuration database is a group of XML files that establish a security policy



# Topic 3

# User account management
- Default accounts:
    - Administrator and Guest accounts
- Accounts can be set up in two general environments:
    - Accounts that are set up through a stand-alone server that does not have active directory installed( Local users account )
    - Accounts that are set up in a domain when Active directory is installed ( Domain user accounts )
- When accounts are created in the domain through Active Directory
    - Those accounts can be used to access any server or resource in the domain
    - Hackers can actually used the default guest accounts left by the user to enter the system. 

- Wen a user takes a leave of absence
    - you have the option to disable his or her account
- Organizations might also have the practice of disabling accounts when someone leaves and enabling the account for that person's replaccement
- When an account is deleted, the files owned by the user will automatically handover the ownership of the files to the system administrator.
- When an account is deleted, It's GUID is also lost therefore in the events logs there will be logs that will show the GUID of the deleted account, causing confusion

### Moving an account 
- When an employee moves from one department to another
    - you might need to move that person's account form one container to another

### Resetting a password
- Administrator does not have the option to look up a password
    - But an administrato can reset the passwords for users
- For organizations that have accounts that manage sensitive information
    - It is advisable to have sepcific guidelines that govern the circumstances under which an account password is reset

### Deleting an account
- It is a good practice to delete accounts that are no longer in use
- Failure to do so could expose youre company to security risks
- WHen an account is deleted an account
    - Its GUID is also deleted and will not be reused even if you create another account using the same name 

### Is recovery of a deleted account possible?
- Actve directory recycle bin by default is off
- From windows server 2008 there is a recycle feature but recovering a deleted account is not reccomended


## Security group Management
- For resource permissions management, one of the best ways to manage accounts is by grouping accounts that have similar characteristcs
- Scope of influence
    -The reach of a group for gaining accesss to resources in actve directory
- Types of groups:
    - local ( Also know as machine local/ It only exsist in the machine itself )
    - domain local
    - Global
    - universal

- All of these groups can be used for security or distribution groups
- Secruity groups
    - Used to enable access to resources on a stand-alone server or in active directory
    - The resources access permission is simply implemented via group membership

### Properties of groups
- You can configure the properties of a specific group
    - Through local users and groups tool for local groups
    - Or in the active directory users adnd computer tools for damins groups
    - Properties are configured using the following tabs:
        - general 
        - Mambers
        - Member of
        - managed by

## OU vs Security membership
- What is the difference between security groups and organizational units 
    - Group policies are apploed to OUs( eg. password policies ) Delegation of authority are also applied to OUs
    - Security groups are used to assign file and folder permissions, shared folder permissions, and any type of resources permissions


# Implementing local groups
- Local secruity group
    - Used to manage  resources on stand- alone computer that is not part of a domain and on member servers in a domain

# Implementing domain local gorups
- Domain local security groups
    - Used when actve directory is deployed
    - Typically used to manage resources in a domain and to give global groups from the same and other domains access to those resources
- The scope of a domain local group is the domain whic the group exsist
- The typical purpose of a domain local group is to provide access to resources
    - You grant access to server folders shared folders and printers to a domain local group
- You should put domain local groups an access control list only
    - The members of domain local groups should be mainly global groups

## Global secruity group
- Intended to contain user accounts from a single domain
- Can also be set up as a member of a domain local group in the same or another domain

- A global group can contain user accounts and other global groups from the domain in which it wan created
- A global groups can be converted to a universal group
    - As long as it is not nested in another global group or in universal group

- A typical use for a global group is to uild it with accoutns that need access to resouces in the same or in another domain
    - And then to make the global group in one domain a member of a domain local group in the same of another domain
- This model enables you to manage user accounts and their access to resources thorugh one or more global groups
    - Whule reducing the complexity of managing accounts


# Implementing universal secruity groups
- Universal security groups
    - Provide a means to span domains and trees
- Universal group membership can include user account from any domain, global groups from any domain, and other universal groups from any domain
- Universal groups are offered to provide an easy means to access any resource in a tree
    - Or among trees in a forest
- Guidelines to help simplify how you plan to use groups:
    - Use global groups to hold accounts as members
    - Use domain local groups to provude access to resources in a specific domain
    - Use universal groups to provide extensive access to resources

# Implementing secruity groups and resources permission
- Best practices:
    - AGDLP
    - AGUDLP
``` 
A = account
U = Universal
G = Global 
DL = Domain Local
P = Permissions
```

- There are many groups or resources permission approaches
    - AP
    - AGP
    - AUP
    - AGUP
- The shorter of the A to P distance implies 
    - Easier to create
    - More difficult to maintain ( Error Prone )


# Managing folder and file secruity
- Creating accounts and groups are the initial steps for sharing resources 
    - The next steps are to create access controll lists to secure thee objects and then to set them up for sharing
- Discretionary ACL (DACL)
    - An ACL that is configured by a server administrator or owner of an object
    - This is the list that tells the system who can operate what things
- System ACL (SACL)
    - Contains information used to audit the access to an object
    - This is to control how many type of audit events for a particular file
- DACL and SACL controls for folders and files:
    - Attributes
    - Permissions 
    - Auditing 
    - Ownership

- attribute are stored as header information with each folder and file
    - Along with other characteristics including volume label, designation as a subfolder, datae of creation, and time of creation
- Two basic attributes remain in NTFS that are still compatible with FAT
    - Read-only and hidden
    - On the general tab in an NTFS folder's or file's properties dialog box
- The advanced properties are archive index compress, encrypt

- Archive attribute
    - For system backup to use
    - Indicates that the folder or file needs to be backed up because it is new or changed
    - File server backup systems can be set to detect files with the archive attribute to ensure those files are backed up
- Index attribute vs windows search service
    - The NTFS index attribute is used to index the folder and file contrents so that file properties can be quickly searched in windows server 2016 through the indexing service
    - Windows server 2016 offers and newer faster search service called the windows search service
    - To use the windows search service, uou must install the file and storage service role via server manager
- Compress attribute ( can be manually set by user )
    - A folder and its contents can be stored on the disk in compressed format
    - Cmpression saves space and you can work on compressed files in the same way as on uncompressed files
    - Compressed files increase CPU overhead to open the files and to copy them
- Encrypt attribute
    - Protects folders and files so that 
    - an encrypted folder or file uses the microsoft encrypting file system
        - Which sets up a unique , private encryption key associated with the user account that encrypted the folder or file
    - EFS uses both symmetric and asymmetric encryption technique
    - When you move an encrypted file to another folder on the same computer, that file remains encrypted, even if you rename it
## Best practices for using EFS:
- Move files for encryption into specifically designated folders flagged for encryption
- It is safer for an application to work on a file is an encrypted folder rather than to work on a file that is individually encrypted
- Workstation users and server administrators should consider encrypting the My documents or Documents folders on their systems
- Users and server administrators should frequently exports certificates and private keys to portable media and store the media in a secure place


## Permissions
- COntrol access to an object, such as a folder or file
- When you configure a folder so that a doomain local group has access to only read the contents fo that folder
    - you are configuring permissions

- Auditing
    - Enables you to track activity on a folder or file
- WIth permissions and auditing set ip, you might want to verify the ownership of a folder
- Folders are first owned by the account that creates them
- Folder owners have the ability to chance permissions for the folders they create
- Ownership can be transferred only by having the take ownership advanced permission
    - Or fill control permission
- A folder can be set up as a shared folder for users to access over the network
- Configuring a shared folder includess features so that the person configuring a share is more aware of security options
- Sharing a folder or file consists of first enabling sharing

### Enabling sharing
- First step for sharing a folder or file over the network
    - Is to make sure folder and printer sharing is turned on
- Network discovery can be turned on
    - Network discovery is the ability to view other network computers and devices

### Configuring Folder sharing through the folder properties
- Share permissions for folder or files
    - Can be set by configuring sharing using the file sharing windows and a folder's or file's sharing tab in its properties dialog box
- When you configure sharing using the advanced sharing options
    - The share permissions also include Full control and change
    - Configured using advanced sharing button on the sharing tab of properties
- Share Permissions
    - ``` Read ``` ( for shared user )
    - ``` Write ```( for shared user )
    - ``` Change or Contribute ```
    - ``` Custom ``` 
    - ``` Full Control ``` ( only in advanced )
    - ``` Owner ```

## Configuring sharing through server manager
- Sever message block protocol
    - Enable an OS to offer shared files on a network
- Network File system protocol
    - Used for file and folder sharing on UNIX and linux systems

## publishing a shared folder in AD
- To publish an object means to make it available and easier to find for users that view the active directory.


# Troubleshooting a secruity conflict
- When a file or folder is created, copid or moved the file permissions can be affected in the following ways:

</br>
</br>
</br>

|Situation   |Permission   |
|:-:|:-:|
|Newly created file   |inherit permissions set in the destination folder   |
|Copied on the same volume   |inherit permissions set in the destination folder   | 
|Move on the same volume   |Retains permissions of the original folder   |
|Move or copied on a different volume   |inherits permissions set in destination folder   |



## Important features in windows server 2016 AD
- Five importants or new features deserve particular mention:
    - restart capability
    - ```Read-only Domain Controller```
    - Cloning domain controllers
    - ```Fine-grained password policy enhancements```
    - ```Protected users global group```
