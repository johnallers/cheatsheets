ldp.exe
-------
Included as part of the Remote Server Administration Tools (RSAT).
In Windows 10, this can be installed through **Add an optional feature**
For specifics, see: https://social.technet.microsoft.com/wiki/contents/articles/2202.remote-server-administration-tools-rsat-for-windows-client-and-windows-server-dsforum2wiki.aspx#Download_locations_for_RSAT

Fix domain trust relationship
-----------------------------
1. Ensure that the computer object exists on the domain controller. If it doesn't, create it.

2. On the client machine, open PowerShell as administrator and run:

       Reset-ComputerMachinePassword [-Credential <Domain Account>] [-Server <DCName>]
       
       Example:
       Reset-ComputerMachinePassword -Credential FooBarCorp\Admin -Server dc.foobarcorp.com

Find a domain controller
------------------------

Run nslookup

    set type=all
    _ldap._tcp.dc._msdcs.DOMAIN_NAME
