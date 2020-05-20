## Purpose of server manager
- It consolidates administrative functions to make a server easier to manage

### Two common toles for a windows server 2016
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