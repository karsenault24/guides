Windows Subsystem for Linux
====================================


WSL allows you to run a Linux environment on your Windows machine, without the need for a separate virtual machine or dual booting. 

It is designed to provide a seamless and productive experience for developers who want to use both Windows and Linux at the same time.

WSL can be used in conjunction with VS Code, Git, Docker, databases, and other applications for user accessibility and ease.

Find the individual tutorials here:
https://learn.microsoft.com/en-us/windows/wsl/setup/environment 


WSL Workflow with Docker
-------------------------

User can enable WSL to locally work on their project using the Linux Ubuntu instance with the Bash commands and tools they prefer. 

Once the development is complete, they can push it to the cloud of their choice by making it into a docker container.

For more information on using Docker in combination with WSL, please visit: 
https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers 


WSL1 vs WSL2 
-------------

WSL comes in two versions, find the differences and what is best fit for your needs here:
https://learn.microsoft.com/en-us/windows/wsl/compare-versions 	



Installation
-------------

Install Windows Subsystem for Linux here:
https://learn.microsoft.com/en-us/windows/wsl/install 

Install the first version of WSL here:
https://learn.microsoft.com/en-us/windows/wsl/install-manual 

YouTube follow along installation video (15 min):
https://www.youtube.com/watch?v=av0UQy6g2FA 


Upgrade Windows
----------------

.. image:: /_static/sphinx/wsl/wsl1.png 
   :width: 600px
   :align: center

Check your windows to make sure you’re running the latest version
You must be running Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11


Find your Windows specs in the “about” page


Enable WSL
----------

To enable WSL:

1. Open powershell as administrator 

2. Allow admin access 

3. Paste ```dism.exe /online /enable-feature /featurename:MicrosoftWindows-Subsystem-Linux /all /norestart``` in the command line window to enable and install WSL.

4. Then paste ```dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart``` to enable Virtual Machine Platform.


Install WSL and Linux 
----------------------

To auto install a Linux distribution with WSL installation use: ```wsl –install```

To change the distribution from the default linux use ```wsl –install –d <Distribution Name>``` with replacing ```<Distribution Name>``` with your choice of distrubtion.

Update and set WSL
-------------------

While still using Powershell as administrator, set WSL to its version by

Checking your version by running: ```wsl -l -v```

To change your WSL to version 2 use: ```wsl --set-default-version 2```


Install Linux
---------------

If Linux was not automatically downloaded during the WSL download, search your app store to find “Ubuntu 20.40 LTS” 


.. image:: /_static/sphinx/wsl/wsl2.png 
   :width: 600px
   :align: center


Launch from Start Menu 


.. image:: /_static/sphinx/wsl/wsl3.png 
   :width: 600px
   :align: center

Linux 
-------
The first launch of Ubuntu Linux console will prompt you to enter a UNIX username and password. The password will be needed for sudo commands.

Once completed, the distribution is ready for use.



Troubleshooting
----------------
- If you are having issues with WSL, try these commands to update and reboot wsl.

    1. run ```wsl --update```
    2. ```dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart```
    3. ```dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart```
    4. reboot
    5. ```wsl --set-default-version 2```
    6. install ubuntu from Microsoft Store
    7. open up ubuntu 
    8. run ```sudo apt update``` if you get a Failed to fetch error run the following (obtained from [here](https://askubuntu.com/questions/1450120/windows-subsystem-for-linux-2-temporary-failure-resolving-archive-ubuntu-com)):
        1. ```sudo rm /etc/resolv.conf```
        2. ```sudo bash -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'```
        3. ```sudo bash -c 'echo "[network]" > /etc/wsl.conf'```
        4. ```sudo bash -c 'echo "generateResolvConf = false" >> /etc/wsl.conf'```
        5. ```sudo chattr +i /etc/resolv.conf````

For troubleshooting information please visit:
https://learn.microsoft.com/en-us/windows/wsl/troubleshooting 

For WSL frequently asked questions, please visit:
https://learn.microsoft.com/en-us/windows/wsl/faq 




Windows Sandboxing
======================

A disposable, lightweight, isolated virtual machine (VM) desktop environment for safely running applications. 

- Ideal for:

    - Testing

    - Debugging

    - Exploring unknown files

    - Experimenting with tools

Applications installed within the sandbox remain isolated from the host machine using hypervisor-based virtualization. 

WSB ensures reboot persistence, quick launch times, and a lower memory footprint compared to full VMs. 


Installation 
-------------

Directions for installation:
https://learn.microsoft.com/en-us/windows/security/application-security/application-isolation/windows-sandbox/windows-sandbox-install 

.. dropdown:: Prerequisites

    - Arm64 (for Windows 11, version 22H2 and later) or AMD64 architecture

    - Virtualization capabilities enabled in BIOS

    - At least 4 GB of RAM (8 GB recommended)

    - At least 1 GB of free disk space (SSD recommended)

    - At least two CPU cores (four cores with hyper-threading recommended) 


Short video tutorial and example:
https://www.youtube.com/watch?v=UywHb0rOHVI 

For written Microsoft documentation please visit:
https://learn.microsoft.com/en-us/windows/security/application-security/application-isolation/windows-sandbox/ 


Troubleshooting 
----------------

For troubleshooting solutions, please visit:
https://learn.microsoft.com/en-us/windows/security/application-security/application-isolation/windows-sandbox/windows-sandbox-troubleshoot

For WSB frequently asked questions, please visit:
https://learn.microsoft.com/en-us/windows/security/application-security/application-isolation/windows-sandbox/windows-sandbox-faq 
