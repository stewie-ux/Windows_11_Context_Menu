\# Restore the Classic Windows 10 Context Menu on Windows 11



This guide explains how to show the full, classic-style right-click

context menu directly in Windows 11.



\## Tested setup



\-   Windows 11 26H2

\-   OS build: `26300.10075`



\## Enable the classic context menu



1\.  Open \*\*Start\*\* and search for \*\*Command Prompt\*\*.



2\.  Open Command Prompt normally (do not select \*\*Run as

&#x20;   administrator\*\*).



3\.  Run these commands one at a time:



&#x20;   ``` cmd

&#x20;   reg add "HKCU\\Software\\Classes\\CLSID\\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\\InprocServer32" /ve /f

&#x20;   ```



&#x20;   ``` cmd

&#x20;   reg add "HKCU\\Software\\Classes\\CLSID\\{51668040-5e31-4023-bbe3-149163bd80f1}\\InprocServer32" /ve /f

&#x20;   ```



4\.  Restart \*\*Windows Explorer\*\* from Task Manager, or restart your PC.



5\.  Right-click a file or folder to check that the classic menu appears.



\## Restore the default Windows 11 context menu



To undo the change, open Command Prompt normally and run:



``` cmd

reg delete "HKCU\\Software\\Classes\\CLSID\\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f

```



``` cmd

reg delete "HKCU\\Software\\Classes\\CLSID\\{51668040-5e31-4023-bbe3-149163bd80f1}" /f

```



Restart Windows Explorer or restart your PC.



\## Notes



\-   These commands modify the current user's registry (`HKCU`).

\-   Run the commands exactly as shown.

\-   Registry changes can affect Windows behavior. If you are unsure,

&#x20;   create a restore point before making changes.

\-   The method was confirmed working on the setup listed above; behavior

&#x20;   may differ on other Windows builds.



