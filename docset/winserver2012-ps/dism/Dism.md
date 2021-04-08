---
author: andreabarr
Download Help Link: https://aka.ms/winsvr-2012-pshelp
Help Version: 3.0.2.0
Locale: en-US
manager: dansimp
Module Guid: 389c464d-8b8d-48e9-aafe-6d8a590d6798
Module Name: System.Object[]
ms.author: v-anbarr
ms.reviewer: 
---

# Dism Module
## Description
The Deployment Image Servicing and Management (DISM) platform is used to mount and service Windows images before deployment. A subset of DISM commands can be used on online Windows images. You can use DISM tools to mount, and get information about, Windows image (.wim) files or virtual hard disks (.vhd or .vhdx). You can also use it to install, uninstall, configure, and update Windows features, packages, and drivers in a Windows image or to change the edition of a Windows image.

This topic introduces the DISM cmdlets available in the DISM PowerShell module. This module is available in Windows 8.1 and Windows Server 2012 R2. On other supported operating systems, you can install the DISM module from the [Windows Assessment and Deployment Kit (Windows ADK)](https://go.microsoft.com/fwlink/?LinkId=206587). For more information about how to use the DISM PowerShell module installed with the ADK, see [How to Use DISM in Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=239927).

For Windows 8.1 and Windows Server 2012 R2, Windows PowerShell 4.0 is included in the installation. For other supported versions of Windows and Windows Server, (including Windows 8, Windows 7 SP1, Windows Server 2012, and Windows Server 2008 R2 SP1), you must install Windows Management Framework 4.0. You can download and install [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=293881) from the Microsoft Download Center.

The DISM platform also includes a command-line tool, DISM.exe, and the [DISM API](https://go.microsoft.com/fwlink/?LinkID=237611). The command-line tool is available in the [Windows Assessment and Deployment Kit (Windows ADK)](https://go.microsoft.com/fwlink/?LinkId=206587) and includes additional functionality that supports servicing commands for international settings.

You can check for errors when running DISM cmdlets by checking if the $?. If set to True the last operation succeeded. If False the last operation failed. The $LASTEXITCODE contains the exit code of the last Win32 executable run. For example, to check that the **Get-WindowsImage** cmdlet fails to get information about the Windows image contained in the file, E:\images\c.wim, type the following: 

```
try
{
       
    Get-WindowsImage -ImagePath E:\images\c.wim
}
catch
{
    $message = "TRAPPED: {0}: '{1}'" -f ($_.Exception.GetType().FullName), ($_.Exception.Message)
    Write-host $message
}

```

For more information about error handling, see the [about_Try_Catch_Finally](https://go.microsoft.com/fwlink/p/?LinkID=317390).

## Dism Cmdlets
### [Add-AppxProvisionedPackage](./Add-AppxProvisionedPackage.md)
Adds an app package (.appx) that will install for each new user to a Windows image.

### [Add-WindowsDriver](./Add-WindowsDriver.md)
Adds a driver to an offline Windows image.

### [Add-WindowsPackage](./Add-WindowsPackage.md)
Adds a single .cab or .msu file to a Windows image.

### [Clear-WindowsCorruptMountPoint](./Clear-WindowsCorruptMountPoint.md)
Deletes all of the resources associated with a mounted image that has been corrupted.

### [Disable-WindowsOptionalFeature](./Disable-WindowsOptionalFeature.md)
Disables a feature in a Windows image.

### [Dismount-WindowsImage](./Dismount-WindowsImage.md)
Dismounts a Windows image from the directory it is mapped to.

### [Enable-WindowsOptionalFeature](./Enable-WindowsOptionalFeature.md)
Enables a feature in a Windows image.

### [Get-AppxProvisionedPackage](./Get-AppxProvisionedPackage.md)
Gets information about app packages (.appx) in an image that will be installed for each new user.

### [Get-WindowsDriver](./Get-WindowsDriver.md)
Displays information about drivers in a Windows image.

### [Get-WindowsEdition](./Get-WindowsEdition.md)
Gets edition information about a Windows image.

### [Get-WindowsImage](./Get-WindowsImage.md)
Gets information about a Windows image in a WIM or VHD file.

### [Get-WindowsOptionalFeature](./Get-WindowsOptionalFeature.md)
Gets information about optional features in a Windows image.

### [Get-WindowsPackage](./Get-WindowsPackage.md)
Gets information about packages in a Windows image.

### [Mount-WindowsImage](./Mount-WindowsImage.md)
Mounts a Windows image in a WIM or VHD file to a directory on the local computer.

### [Remove-AppxProvisionedPackage](./Remove-AppxProvisionedPackage.md)
Removes an app package (.appx) from a Windows image.

### [Remove-WindowsDriver](./Remove-WindowsDriver.md)
Removes a driver from an offline Windows image.

### [Remove-WindowsPackage](./Remove-WindowsPackage.md)
Removes a package from a Windows image.

### [Repair-WindowsImage](./Repair-WindowsImage.md)
Repairs a Windows image in a WIM or VHD file.

### [Save-WindowsImage](./Save-WindowsImage.md)
Applies changes made to a mounted image to its WIM or VHD file.

### [Set-WindowsEdition](./Set-WindowsEdition.md)
Changes a Windows image to a higher edition.

### [Set-WindowsProductKey](./Set-WindowsProductKey.md)
Sets the product key for the Windows image.

### [Use-WindowsUnattend](./Use-WindowsUnattend.md)
Applies an unattended answer file to a Windows image.

