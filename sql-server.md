Install SQL Server unattended

  Setup.exe /q /ACTION=Install /FEATURES=SQL /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="NT AUTHORITY\Network Service" /SQLSYSADMINACCOUNTS="domain\username" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /AGTSVCSTARTUPTYPE=Automatic /SECURITYMODE=SQL /SAPWD="StrongPassword" /TCPENABLED=1 /NPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS