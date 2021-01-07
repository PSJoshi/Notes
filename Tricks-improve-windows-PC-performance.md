## Some tips to improve Windows PC Performance

### High CPU or Disk usage caused by ntoskrnl.exe process in Windows 10

Windows NT kernel is responsible for managing various services like memory management, process management, hardware resoure management etc.Sometimes, it is seen that this process utilizes too much of CPU/Disk and cause the slowdown of computer especially at startup.
A minor registry tweak will solve the high CPU/Disk utilization issue. For this, you have to open registry editor ( Open "Run"->"Regedit") and modify the following registry setting:

1. Go to section - HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management
2. Change/modify key value of  "ClearPageFileAtShutdown" from 0 to 1.

### System File Checker (SFC)
System File Checker (SFC) is a utility in Windows that allows users to scan for corruptions in Windows system files and restore corrupted files. To run, open command prompt  "run"->"cmd " and type
```
C:\Windows\system32> sfc /scannow
```
Note - sfc program should be run in administrative mode.

### Deployment Image servicing and management (DISM)
A DISM scan can be used to repair and prepare Windows images, including the Windows Recovery Environment, Windows Setup, and Windows PE. To run a DISM scan, open Command Prompt as administrator and type this command: "DISM /Online /Cleanup-Image /RestoreHealth". Press Enter on the keyboard to execute it.
```
C:\Windows\system32>  DISM /Online /Cleanup-Image/RestoreHealth
```

* Ref - https://blog.pcrisk.com/windows/12536-ntoskrnlexe-process-is-causing-high-cpu-or-disk-usage-how-to-fix-it

