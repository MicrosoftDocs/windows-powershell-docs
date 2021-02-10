---
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: Dism
online version: 
schema: 2.0.0
title: Add-AppxProvisionedPackage
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C32BA440-73EB-4D09-9C3C-68C2239B013B
---

# Add-AppxProvisionedPackage

## SYNOPSIS
Adds an app package (.appx) that will install for each new user to a Windows image.

## SYNTAX

### Offline
```
Add-AppxProvisionedPackage [-FolderPath <String>] [-PackagePath <String>] [-DependencyPackagePath <String[]>]
 [-LicensePath <String>] [-SkipLicense] [-CustomDataPath <String>] -Path <String> [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

### Online
```
Add-AppxProvisionedPackage [-FolderPath <String>] [-PackagePath <String>] [-DependencyPackagePath <String[]>]
 [-LicensePath <String>] [-SkipLicense] [-CustomDataPath <String>] [-Online] [-WindowsDirectory <String>]
 [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>] [-LogLevel <LogLevel>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AppxProvisionedPackage** cmdlet adds an app package (.appx) that will install for each new user to a Windows image.
If the package has dependencies that are architecture-specific, you must install the applicable architectures for the dependency on the target image.
For example, you must install the x86 dependency on the x86 image.

You cannot install an app package (.appx) on an operating system that does not support Windows 8 apps.
Apps are not supported on Server Core installations of Windows Server 2012, Windows Preinstallation Environment (Windows PE) 4.0, or on any versions of Windows older than Windows 8 and Windows Server 2012.

To install and run apps on Windows Server 2012 R2, you must install the [Desktop Experience Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn609826(v=ws.11)).

Use the *Online* parameter to specify the running operating system on your local computer, or use the *Path* parameter to specify the location of a mounted Windows image.

Use the *PackagePath*, *DependencyPackagePath*, and *LicensePath* parameters to specify the location of all the files that are needed to add the provisioned app package (.appx).
Use these parameters to provision line-of-business apps.

Use the *FolderPath* parameter to specify the location of a folder of unpacked app package (.appx) files that includes any dependency packages and a license file.

To add an app package (.appx) for a particular user, or to test a package while developing your app, use the **Add-AppxPackage** cmdlet instead.

For more information, including requirements for app package provisioning, see [Sideload Apps with DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/sideload-apps-with-dism-s14) and [How to develop an OEM app that uses a custom file](https://docs.microsoft.com/windows/win32/appxpkg/how-to-develop-oem-app-with-custom-file) in MicrosoftDocs.

## EXAMPLES

### Example 1: Add an app package to the running operating system
```powershell
PS C:\> Add-AppxProvisionedPackage -Online -FolderPath "c:\Appx"
```

This command adds the app package, dependency packages, and license file from the c:\Appx folder to the running Windows operating system.
The package will be installed for the current user and any new user account created on the computer.

### Example 2: Add an app package an operating system image
```powershell
PS C:\> Add-AppxProvisionedPackage -Path c:\offline -PackagePath c:\Appx\myPackage.appx -DependencyPackagePath c:\Appx\dependency1\dependencyPackage.appx -LicensePath c:\Appx\myLicense.xml
```

This command adds the app package, myPackage.appx, to the Windows image mounted to c:\offline.

## PARAMETERS

### -CustomDataPath
Specifies the location of a custom data file.
The custom data file will be renamed custom.data and saved in the app data store.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DependencyPackagePath
Specifies the location of a dependency package.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FolderPath
Specifies a folder of unpacked app package files containing a main package and any dependency packages.
This folder must also contain your application license.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LicensePath
Specifies the location of the .xml file containing your application license.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogLevel
Specifies the maximum output level shown in the logs.

```yaml
Type: LogLevel
Parameter Sets: (All)
Aliases: LL
Accepted values: Errors, Warnings, WarningsInfo

Required: False
Position: Named
Default value: WarningsInfo
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogPath
Specifies the full path and file name to log to.
If not set, the default is `%WINDIR%\Logs\Dism\dism.log`.
In Windows PE, the default directory is the RAMDISK scratch space which can be as low as 32 MB.
The log file will automatically be archived.
The archived log file will be saved with .bak appended to the file name and a new log file will be generated.
Each time the log file is archived the .bak file will be overwritten. 
When using a network share that is not joined to a domain, use the net use command together with domain credentials to set access permissions before you set the log path for the DISM log.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Online
Specifies that the action is to be taken on the operating system that is currently running on the local computer.

```yaml
Type: SwitchParameter
Parameter Sets: Online
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PackagePath
Specifies the location of the app package (.appx) to add to the Windows image.
This package will be added for every new user account.
To add an app package (.appx) for a particular user or to test a package while developing your app, use the **Add-AppxPackage** cmdlet instead.

The *PackagePath* parameter is only supported for offline servicing when the technician computer is running a version of Windows that supports Windows 8 apps.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the full path to the root directory of the offline Windows image that you will service.
If the directory named Windows is not a subdirectory of the root directory, *WindowsDirectory* must be specified.

```yaml
Type: String
Parameter Sets: Offline
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScratchDirectory
Specifies a temporary directory that will be used when extracting files for use during servicing.
The directory must exist locally.
If not specified, the `\Windows\%Temp%` directory will be used, with a subdirectory name of a randomly generated hexadecimal value for each run of DISM.
Items in the scratch directory are deleted after each operation. 
You should not use a network share location as a scratch directory to expand a package (.cab or .msu file) for installation.
The directory used for extracting files for temporary usage during servicing should be a local directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipLicense
Adds an app package without a license file.

Only use *SkipLicense* with apps that do not require a license on Enterprise or Server versions of the operating system.
Using *SkipLicense* in other scenarios can compromise an image.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SystemDrive
Specifies the path to the location of the BootMgr files.
This is necessary only when the BootMgr files are located on a partition other than the one that you are running the command from.
Use -SystemDrive to service an installed Windows image from a Windows PE environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsDirectory
Specifies the path to the Windows directory relative to the image path.
This cannot be the full path to the Windows directory; it should be a relative path.
If not specified, the default is the Windows directory in the root of the offline image directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.Dism.Commands.ImageObject

### Microsoft.Dism.Commands.AppxPackageObject

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

## RELATED LINKS

[Add-AppxPackage](../appx/Add-AppxPackage.md)

[Get-AppxProvisionedPackage](./Get-AppxProvisionedPackage.md)

[Remove-AppxProvisionedPackage](./Remove-AppxProvisionedPackage.md)

[Set-AppXProvisionedDataFile](./Set-AppXProvisionedDataFile.md)
