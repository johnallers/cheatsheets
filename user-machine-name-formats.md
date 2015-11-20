**Legacy Windows**

    NetBIOS Domain Name \ SAM (Security Account Manager) account name
    NetBIOS Name: 16-byte address ending with 0x20. Names are 15 characters, padded with spaces; 16th character is 0x20.
    
    Sample: MYDOMAIN\JOHN

**User Principal Name (UPN)**

    User Logon Name (not the legacy sAMAccountName) @ UPN Suffix
    
    Sample: john@mydomain.com
    
**Distinguished Name**

    CN=john,OU=Users,DC=mydomain,DC=com
