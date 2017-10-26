Fix domain trust relationship
-----------------------------

    Reset-ComputerMachinePassword [-Credential <PSCredential>] [-Server <String>]

Find a domain controller
------------------------

Run nslookup

    set type=all
    _ldap._tcp.dc._msdcs.DOMAIN_NAME
