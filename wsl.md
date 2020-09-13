## Marking directory and sub-directories as case-sensitive in Windows
  
    (Get-ChildItem -Recurse -Directory).FullName | ForEach-Object {fsutil.exe file setCaseSensitiveInfo $_ enable}

This is useful for working with case-sensitive git repos in WSL.

Reference: https://stackoverflow.com/questions/51591091/apply-setcasesensitiveinfo-recursively-to-all-folders-and-subfolders
