**Fix Windows 10 Menu Search Issue**

    REG ADD HKCU\Software\Microsoft\Windows\CurrentVersion\Search /v BingSearchEnabled /t REG_DWORD /d 0
    REG ADD HKCU\Software\Microsoft\Windows\CurrentVersion\Search /v CortanaConsent /t REG_DWORD /d 0
    tskill searchui
