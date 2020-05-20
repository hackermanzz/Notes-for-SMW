# Notes-for-SMW
- ``` ++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++.>+++++.<<++.>>++++.++++++++++++.<<.>>-----------.-------------.++++++++++++.--------.<<.>>++++.++++++++++.<<.>+++++++++++.>--------------.----.+++++++++++++.<<+. ```


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



- The Dimensions on which microsoft objective of a trustworthy computin relies on the Goals:
    - Security
    - Privacy
    - Buisness Integrity
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
