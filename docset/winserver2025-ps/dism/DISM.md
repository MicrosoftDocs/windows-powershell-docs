---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
Download Help Link: https://aka.ms/winsvr-2025-pshelp
Help Version: 5.0.1.1
Locale: en-US
Module Guid: 389c464d-8b8d-48e9-aafe-6d8a590d6798
Module Name: Dism
ms.date: 10/07/2021
title: Dism Module
---

# Dism Module

## Description

The Deployment Image Servicing and Management (DISM) platform is used to mount and service Windows
images before deployment. A subset of DISM commands can be used on online Windows images. You can
use DISM tools to mount, and get information about, Windows image (`.wim`) files or virtual hard
disks (`.vhd` or `.vhdx`). You can also use it to install, uninstall, configure, and update Windows
features, packages, and drivers in a Windows image or to change the edition of a Windows image.

The DISM platform also includes a command-line tool, `dism.exe`, and the
[DISM API](https://go.microsoft.com/fwlink/?LinkID=237611). The command-line tool is available in the
[Windows Assessment and Deployment Kit (Windows ADK)](https://go.microsoft.com/fwlink/?LinkId=206587)
and includes additional functionality that supports servicing commands for international settings.

You can check for errors when running Dism cmdlets by checking if the `$?`. If set to True, the last
operation succeeded. If False, the last operation failed. The `$LASTEXITCODE` contains the exit code
of the last Win32 executable run. For example, to check that the `Get-WindowsImage` cmdlet fails to
get information about the Windows image contained in the file, `E:\images\c.wim`, type the
following:

```powershell
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

For more information about error handling, see the
[about_Try_Catch_Finally](https://go.microsoft.com/fwlink/p/?LinkID=317390).

## Dism Cmdlets
### [Add-AppxProvisionedPackage](./Add-AppxProvisionedPackage.md)
Adds an app package (.appx) that will install for each new user to a Windows image.

### [Add-WindowsCapability](./Add-WindowsCapability.md)
Installs a Windows capability package on the specified operating system image.

### [Add-WindowsDriver](./Add-WindowsDriver.md)
Adds a driver to an offline Windows image.

### [Add-WindowsImage](./Add-WindowsImage.md)
Adds an additional image to an existing image (.wim) file.

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

### [Expand-WindowsCustomDataImage](./Expand-WindowsCustomDataImage.md)
Expands a custom data image.

### [Expand-WindowsImage](./Expand-WindowsImage.md)
Applies an image to a specified location.

### [Export-WindowsCapabilitySource](Export-WindowsCapabilitySource.md)
Creates a custom FOD repository that includes packages that support the installation of the specified capabilities.

### [Export-WindowsDriver](Export-WindowsDriver.md)
Exports all third-party drivers from a Windows image to a destination folder.

### [Export-WindowsImage](./Export-WindowsImage.md)
Exports a copy of the specified image to another image file.

### [Get-AppxProvisionedPackage](./Get-AppxProvisionedPackage.md)
Gets information about app packages (.appx) in an image that will be installed for each new user.

### [Get-NonRemovableAppsPolicy](Get-NonRemovableAppsPolicy.md)
Returns a list of the app packages that are installed and configured as non-removable apps.

### [Get-WIMBootEntry](Get-WIMBootEntry.md)
Displays the Windows image file boot (WIMBoot) configuration entries for a specified disk volume.

### [Get-WindowsCapability](./Get-WindowsCapability.md)
Gets Windows capabilities for an image or a running operating system.

### [Get-WindowsDriver](./Get-WindowsDriver.md)
Displays information about drivers in a Windows image.

### [Get-WindowsEdition](./Get-WindowsEdition.md)
Gets edition information about a Windows image.

### [Get-WindowsImage](./Get-WindowsImage.md)
Gets information about a Windows image in a WIM or VHD file.

### [Get-WindowsImageContent](./Get-WindowsImageContent.md)
Displays a list of the files and folders in a specified image.

### [Get-WindowsOptionalFeature](./Get-WindowsOptionalFeature.md)
Gets information about optional features in a Windows image.

### [Get-WindowsPackage](./Get-WindowsPackage.md)
Gets information about packages in a Windows image.

### [Get-WindowsReservedStorageState](./Get-WindowsReservedStorageState.md)
Gets the reserved storage state of the image.

### [Mount-WindowsImage](./Mount-WindowsImage.md)
Mounts a Windows image in a WIM or VHD file to a directory on the local computer.

### [New-WindowsCustomImage](./New-WindowsCustomImage.md)
Captures an image of customized or serviced Windows components on a Windows Image File Boot (WIMBoot) configured device.

### [New-WindowsImage](./New-WindowsImage.md)
Captures an image of a drive to a new WIM file.

### [Optimize-AppXProvisionedPackages](Optimize-AppXProvisionedPackages.md)
Optimizes the total file size of provisioned packages on the image by replacing identical files with
hard links.

### [Optimize-WindowsImage](Optimize-WindowsImage.md)
Configures a Windows image with specified optimizations.

### [Remove-AppxProvisionedPackage](./Remove-AppxProvisionedPackage.md)
Removes an app package (.appx) from a Windows image.

### [Remove-WindowsCapability](./Remove-WindowsCapability.md)
Uninstalls a Windows capability package from an image.

### [Remove-WindowsDriver](./Remove-WindowsDriver.md)
Removes a driver from an offline Windows image.

### [Remove-WindowsImage](./Remove-WindowsImage.md)
Deletes the specified volume image from a WIM file that has multiple volume images.

### [Remove-WindowsPackage](./Remove-WindowsPackage.md)
Removes a package from a Windows image.

### [Repair-WindowsImage](./Repair-WindowsImage.md)
Repairs a Windows image in a WIM or VHD file.

### [Save-WindowsImage](./Save-WindowsImage.md)
Applies changes made to a mounted image to its WIM or VHD file.

### [Set-AppXProvisionedDataFile](./Set-AppXProvisionedDataFile.md)
Adds custom data into the specified app (.appx) package that has been provisioned in a Windows image.

### [Set-NonRemovableAppsPolicy](Set-NonRemovableAppsPolicy.md)
Sets an app package as non-removable (can not be uninstalled).

### [Set-WindowsEdition](Set-WindowsEdition.md)
Changes a Windows image to a higher edition.

### [Set-WindowsProductKey](./Set-WindowsProductKey.md)
Sets the product key for the Windows image.

### [Set-WindowsReservedStorageState](./Set-WindowsReservedStorageState.md)
Sets the reserved storage state of the image.

### [Split-WindowsImage](./Split-WindowsImage.md)
Splits an existing .wim file into multiple read-only split .wim files.

### [Start-OSUninstall](Start-OSUninstall.md)
Windows gives a user the ability to uninstall and roll back to a previous version of Windows. You
can use DISM to initiate an uninstall.

### [Update-WIMBootEntry](Update-WIMBootEntry.md)
Updates the Windows image file boot (WIMBoot) configuration entry, associated with either the specified data source ID, the renamed image file path or the moved image file path.

### [Use-WindowsUnattend](./Use-WindowsUnattend.md)
Applies an unattended answer file to a Windows image.
