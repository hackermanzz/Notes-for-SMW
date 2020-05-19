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