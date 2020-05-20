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
- Move gilesfor encryption into specifically designated folders flagged for encryption
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
    - Network discovery is the ability to view othernetwork computers and devices

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