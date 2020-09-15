# WSL2 install guide

This guide assumes that you have installed any of the following windows 10 updates:
 - Windows 10 May 2020 (2004)
 - Windows 10 May 2019 (1903)
 - Windows 10 November 2019 (1909)

Make sure you have one of them installed before proceeding.

The whole process will eat away around 16 GB. Make sure you have enough space.

## Setup
 1. Run Powershell as administrator
 2. Run the following commands: (~14GB)

        dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    
    Then:

    On Windows update 2004, use:

        dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    On Windows update 1903/1909, use:

        Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -NoRestart

 3. Restart the PC
 4. Download and install [Linux kernel](https://aka.ms/wsl2kernel) (size < 15MB)  for Windows 10
 5. Download and install [Ubuntu](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6) (size < 450MB) distribution from Microsoft Store
 6. Download and install [Windows Terminal](https://www.microsoft.com/en-gb/p/windows-terminal/9n0dx20hk701) from Microsoft Store
 7. Run Powershell as administrator
 8. Run `wsl --set-default-version 2`

 9. Now Open the Ubuntu app by searching on the start menu. It will show:

        Installing, this may take a few minutes...

 10. Input username and password.
     The following message will show:

         Installation successful!
         ...
         Welcome to Ubuntu 20.04.1 LTS (GNU/Linux 4.19.128-microsoft-standard x86_64)
         ...
         ...
     Then you are good to go

 12. Test running `sudo -i` and check that you have root access!
 13. Run command `uname -a`, and you will get a similar output as follows:

         Linux <computer-name> 4.19.128-microsoft-standard #1 SMP Tue Jun 23 12:58:10 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux

     We confirm that the kernel is _4.19.128-microsoft-standard_ running on _x86_64_ architecture. And the operating system is Linux.

---
## Sources
 - https://www.omgubuntu.co.uk/how-to-install-wsl2-on-windows-10
 - https://docs.microsoft.com/en-us/windows/wsl/install-win10