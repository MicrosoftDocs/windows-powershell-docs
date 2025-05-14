---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Dism.PowerShell.dll-Help.xml
Module Name: System.Object[]
ms.date: 08/24/2021
online version: https://learn.microsoft.com/powershell/module/dism/add-windowscapability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WindowsCapability
---

# Add-WindowsCapability

## SYNOPSIS
Installs a Windows capability package on the specified operating system image.

## SYNTAX

### Online
```powershell
Add-WindowsCapability [-Name <String>] [-LimitAccess] [-Source <String[]>] [-Online]
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

### Offline
```powershell
Add-WindowsCapability [-Name <String>] [-LimitAccess] [-Source <String[]>] -Path <String>
 [-WindowsDirectory <String>] [-SystemDrive <String>] [-LogPath <String>] [-ScratchDirectory <String>]
 [-LogLevel <LogLevel>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WindowsCapability** cmdlet acquires a Windows capability package from a priority-ordered list of source locations, and then installs the package on the specified operating system image.

## EXAMPLES

### Example 1: Add a Windows capability package to the running OS via the Windows Update client
```powershell
PS C:\> Add-WindowsCapability -Online -Name "Msix.PackagingTool.Driver~~~~0.0.1.0"
```
This command adds a Windows capability package to the running operating system. Because no source is specified, the Windows Update client will download the necessary package. It requires either an active Internet connection or an active network connection to the local Windows Server Update Services (WSUS) server.

### Example 2: Add a Windows capability package to the running OS using a locally stored package file
```powershell
PS C:\> Add-WindowsCapability -Online -Name "Msix.PackagingTool.Driver~~~~0.0.1.0" -Source "E:\" -LimitAccess
```

This command adds a Windows capability package specified by the *Name* parameter, to the running operating system. The *Source* parameter specifies the location of required files. For instance, if the running OS is a copy of Windows 10 version 1809, the `Msix-PackagingTool-Driver-Package~31bf3856ad364e35~amd64~~.cab` file must be present at `E:\`.

If the package specified by the *Name* parameter is already installed, this command does not return an error message, regardless of whether the required files are present at `E:\`.

### Example 3: Add a Windows capability package to an image
```powershell
PS C:\> Add-WindowsCapability -Path "C:\mount\Windows" -Name "Msix.PackagingTool.Driver~~~~0.0.1.0" -Source "E:\"
```

This command adds a Windows capability package specified by the *Name* parameter,  to the operating system image at the path C:\mount\Windows. The *Source* parameter specifies the location of required files. For instance, if the mount point contains a copy of Windows 10 version 1809, the `Msix-PackagingTool-Driver-Package~31bf3856ad364e35~amd64~~.cab` file must present at `E:\`.

## PARAMETERS

### -LimitAccess
Indicates that this cmdlet does not query Windows Update for source packages when servicing a live OS. Only applies when the `-Online` switch is specified.

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
If not set, the default is `"$env:WINDIR\Logs\Dism\dism.log"`.
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

### -Name
Specifies the identity of the capability to add to an operating system image.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Online
Indicates that the cmdlet operates on a running operating system on the local host.

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
If not specified, the `"$env:Temp"` directory will be used, with a subdirectory name of a randomly generated hexadecimal value for each run of DISM.
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

### -Source
Specifies the location of the files that are required to add a Windows capability package to an image. If you specify multiple *Source* arguments, the files are gathered from the first location where they are found and the rest of the locations are ignored. Separate source locations with a comma.

If you do not specify a *Source*, the default location set by Group Policy is used. If that fails, Windows Update is also used for online images, unless *LimitAccess* is specified. When all fail, the cmdlet fails silently; no exceptions are thrown.

*Source* can only be used when servicing images that are running at least Windows 8 or Windows Server 2012.

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

## OUTPUTS

### Microsoft.Dism.Commands.ImageObject

## NOTES

As of Windows 10 version 1709, you cannot use Windows Server Update Services (WSUS) to host Features on Demand (FOD) and language packs for Windows 10 clients. Instead, you can enforce a Group Policy setting that tells the clients to download them directly from Windows Update. You can also host FOD and language packs on a network share, but starting with Windows 10 version 1809, FOD and language packs can only be installed from Windows Update. For more information, see [How to make Features on Demand and language packs available when you're using WSUS/Configuration Manager](/windows/deployment/update/fod-and-lang-packs).

## RELATED LINKS

[Get-WindowsCapability](./Get-WindowsCapability.md)
[Remove-WindowsCapability](./Remove-WindowsCapability.md)
