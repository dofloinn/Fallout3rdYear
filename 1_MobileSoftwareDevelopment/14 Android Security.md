### <mark style="background: #AD21D9;">Android Security:</mark>

Like any operating system of application platform Android has paid significant focus to the security of the system.

An insecure system is unlikely to be adopted by users.

<mark style="background: #AD21D9;">Measures include:</mark>
- Sandboxing 
- Permissions 
- Use of the kernel etc

### <mark style="background: #AD21D9;">Multiple Layer:</mark>

![](https://i.imgur.com/Po5a9sQ.png)

### <mark style="background: #AD21D9;">Android is a Linux based system:</mark>  

The first major decision was to base Android on the Linux kernel  

In existence and use since 1991  

<mark style="background: #AD21D9;">Open Source:</mark> anyone can observe the code and suggest patches  

As a result Android adopts a lot of Linux style security measures by default

### <mark style="background: #AD21D9;">Android is a Linux based system:</mark>  

OS nature of the kernel leads to increased security of the system (?)  

Code & patches are more visible  

Patches analysed & if they show suspicious behaviour or introduce bugs, then are rejected.  

Patches that are accepted should be of sufficient quality to remove bugs or security issues - will go through a checking process by the main development team  

Approved patches will be brought mainline in next release.

### <mark style="background: #AD21D9;">User IDs (UIDs) and group IDs (GIDs)</mark> 

Linux imposes an ID on every user and group  

Users considered individuals while groups are a collection of related users, Any user outside a group is “other”  

File access permissions (read, write, and execute) are managed by a set of permissions on each file  

Permission list like ``rwxr-xr–`` would state that the user has read, write, and execute permissions the group only has read, and execute, while others can only read

### <mark style="background: #AD21D9;">Sandboxing:</mark> 

All applications sandboxed in Android  

Container that stores application’s code and data. Android - single directory  

Applications are permitted to make any modifications to their own sandbox

Android sets the UID and GID for everything in that directory to be the UID & GID of application. Will also set permissions to ``rwx——``  . Each application is isolated from each other and OS.

An application cannot modify or interact with the data of another application

All other files on the system are either owned by another application in a separate directory  

Or files not owned by any application are owned by the root user  

Applications have limited access to touch or modify those files.  

However to complicate matters, the filesystem is divided into two sections

### <mark style="background: #AD21D9;">File system structure:</mark>  

<mark style="background: #AD21D9;">Internal Storage:</mark> private data belonging to an application and holds android OS.  

<mark style="background: #AD21D9;">External Storage:</mark> public shared data that can be accessed by the OS and all applications.  

Please check the latest security changes.

![](https://i.imgur.com/l6CAaHK.png)

### <mark style="background: #AD21D9;">Permissions:</mark>

Forces applications to declare resources that they require in order to function

At install time android must be informed what permissions the app requires to function

This is to stringently control permissions from app to app

Also informs users what the app has access to on the device.

### <mark style="background: #AD21D9;">Permissions: Manifest file:</mark>  

<mark style="background: #AD21D9;">Manifest file</mark> is where all requested permissions must be declared  

Every required permission must be listed here. If the user accepts the required permissions - application will be installed and given those permissions by the OS  

If app tries to access permissions it does not have, OS will immediately kill it as considered a security risk

### <mark style="background: #AD21D9;">Permissions:</mark> 

<mark style="background: #AD21D9;">Whitelisting:</mark> Applications are given no permissions to begin and are only allocated the minimum set of permissions needed  

<mark style="background: #AD21D9;">Blacklisting:</mark> Gives all permissions by default and only removes permissions as needed  

Whitelisting is used to encourage developers to use the minimum set of required permissions  
- Apps with a long list of permissions will be viewed sceptically by users  
- Particularly when sensitive data is involved  

These permissions will be shown to the user before install such that they can read through and spot anything suspicious

### <mark style="background: #AD21D9;">Permissions - Default:</mark>  

Every application will get a default set of basic permissions  

<mark style="background: #AD21D9;">This includes:</mark>  
- Update the screen  
- Interact with user input 
- Generate sound and vibrations  
- Read/Write to sandbox in internal storage

### <mark style="background: #AD21D9;">Permissions - Advice:</mark> 

Always use the absolute min. amount of permissions  

If you don’t need a permission, then get rid of it. 

If you do require a permission, give the user clear and concise information about <mark style="background: #AD21D9;">why</mark> you need it  
- Especially if user data is involved (data - protection law)  
- GDPR

### <mark style="background: #AD21D9;">Permissions - The Human:</mark>

Weakest link in the security chain - Human  

Measures will be useless if the human does not take care when installing apps  

Users are becoming more aware and recognize potential threats to their devices  

There are a number of tricks that unscrupulous developers and apps will try to use to gain access to permissions

### <mark style="background: #AD21D9;">Permissions - Social Engineering:</mark> 

Trick user to either give access to all permissions or ask for more over time  

User effectively invites malware in!  

If you can circumvent the user you also circumvent the entire security system  

There is no patch for human stupidity

### <mark style="background: #AD21D9;">Security Measures - Application level:</mark> 

Mechanisms developer should use to try to make apps secure  

Learning about secure programming (input validation, buffer overflows, etc)  

Will vastly reduce the number of potential security issues in code.

### <mark style="background: #AD21D9;">Security Measures - Network:</mark>

If your application uses any form of networking you should consider using secure forms of transport  

Particularly login/logout & transmission of sensitive data  

HTTPS and SSL sockets are available in API, Provides a level of encryption & protection against attacks  

<mark style="background: #AD21D9;">Network Security Configuration:</mark>
![](https://i.imgur.com/P8Frl89.png)

### <mark style="background: #AD21D9;">Security Measures - Credentials:</mark>  

With regards to credentials try to ask as little as possible  

Avoid storing username/password combinations  

Use authorisation tokens where possible  

The less a user provides username/password combinations the less likely it will be transmitted over the network  

Less likely that it will be captured as well.

### <mark style="background: #AD21D9;">Security Measures - Cryptography:</mark>  

When storing user sensitive information, encrypt it 
- API provides a number of ciphers use them where possible  
- A secure random number generator is also provided.  

Most random number generators are pseudorandom and predictable  

Don’t implement your own encryption mechanism -likely be weaker than whatever is already there.  

<mark style="background: #AD21D9;">Android Encryption – Various levels:</mark>  
- Full Disk  
- File  
- Metadata

### <mark style="background: #AD21D9;">Security Measures: Input Validation:</mark>  

Common mechanism used - Inject code / cause errors with forms that are not properly validated  

Particularly if SQL or JavaScript  

Any input that received should be stringently validated to ensure it adheres to the format expected  

If it looks suspicious, then reject immediately.

![](https://i.imgur.com/bBnM33m.png)
