ldp.exe
-------
Download RSAT (Remote Server Administration Tools): https://social.technet.microsoft.com/wiki/contents/articles/2202.remote-server-administration-tools-rsat-for-windows-client-and-windows-server-dsforum2wiki.aspx#Download_locations_for_RSAT

Fix domain trust relationship
-----------------------------

    Reset-ComputerMachinePassword [-Credential <PSCredential>] [-Server <String>]

Find a domain controller
------------------------

Run nslookup

    set type=all
    _ldap._tcp.dc._msdcs.DOMAIN_NAME
