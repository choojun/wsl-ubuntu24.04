<img width="160" height="80" alt="wsl" src="https://github.com/user-attachments/assets/cf564094-1d59-4f66-a5b2-4300213bf6f3" />

# A. Remove/Setup WSL

A Microsoft Windows component that allows users to run Linux command-line tools, scripts, and GUI applications natively on Windows 10 and Windows 11. 

1. Hardware requirement: recommended **16GB RAM (or more)** and **CPU virtualization enabled** with **constant internet access** during exercises.
Suppose that your Windows has updated to the latest patches too (tested Windows 10 Pro with version 22H2)!  
Software reqirement:
   - Find Settings --> Apps --> Apps & features --> Related Settings --> Programs and Features --> Turn Windows features on or off, **or**
   - Find Settings --> System -->  Optional features --> Related Settings --> More Windows features --> Turn Windows features on or off.

3. Click (for setup) or unclick (for remove) the following items (if any available)
    - Hyper-V
    - Virtual Machine Platform
    - Windows Hypervisor Platform
    - Windows Subsystem for Linux.

4. Restart PC

5. Suppose that your PC accessible to the Internet (for huge files downloading), perform the search of required keyword, e.g., Ubuntu, in the Microsoft Store. Click on the Get button to download and intall the required distro, e.g., UBuntu-xx.xx, and laumch the installed distro via the created link in the Windows Start. A sudoer user will be created during the initial launching.

> To set up the required Ubuntu distro (same version), run the following commands in PowerShell as administrator.
>
> ~~~bash
> wsl --update
> (restart PC)
>
> wsl –-list --online
>
> wsl --install -d UBuntu-xx.xx
> (restart PC)
> ~~~
>
> You may install a specific version of distro under the PowerShell as Administrator, e.g., the adopted version as PC either in lab or your course mate. Then, locate your administrator username and password, after reboot and before first use.
>
> ![wsl_setup](https://github.com/user-attachments/assets/fae87c59-097a-43f4-bea1-1febbaf5e16a)
>



