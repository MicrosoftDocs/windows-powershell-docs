---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
Module Name: AppvClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/appvclient/mount-appvclientpackage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-AppvClientPackage
---

# Mount-AppvClientPackage

## SYNOPSIS
Loads a package into the App-V cache.

## SYNTAX

### ByGuid (Default)
```
Mount-AppvClientPackage [-Cancel] [-PackageId] <Guid> [-VersionId] <Guid> [<CommonParameters>]
```

### ByPackage
```
Mount-AppvClientPackage [-Cancel] [-Package] <AppvClientPackage> [<CommonParameters>]
```

### ByName
```
Mount-AppvClientPackage [-Name] <String> [[-Version] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Mount-AppvClientPackage** cmdlet initiates or resumes the loading of a Microsoft Application Virtualization (App-V) package into the cache.

## EXAMPLES

### Example 1: Get a specific version of a package
```
PS C:\> Mount-AppvClientPackage -Name "MyApp" -Version 2
```

This command downloads the version 2 of the package named MyApp.

### Example 2: Get all versions of a package
```
PS C:\> Mount-AppvClientPackage -Name "MyApp"
```

This command downloads the all versions of the package named MyApp.

### Example 3: Download all packages that match a string
```
PS C:\> Get-AppvClientPackage -Name "My*" | Mount-AppvClientPackage
```

This command gets all packages that have the string My in the name, and then downloads them.

### Example 4: Download and publish a new package
```
PS C:\> Add-AppvClientPackage -Path "http://MyServer/content/package.Appv" | Mount-AppvClientPackage | Publish-AppvClientPackage -Global
```

This command adds the package from the path specified, downloads it, and then publishes it to all users on the computer.

### Example 5: Cancel a download
```
PS C:\> Mount-AppvClientPackage -Name "MyApp" -Cancel
```

This command cancels the download of the package name MyApp.

## PARAMETERS

### -Cancel
Indicates that the cmdlet stops the loading of a package.

```yaml
Type: SwitchParameter
Parameter Sets: ByGuid, ByPackage
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of the package given during sequencing time.
This value is obtained from the package manifest.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Package
Specifies an App-V package.

```yaml
Type: AppvClientPackage
Parameter Sets: ByPackage
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PackageId
Specifies a GUID that uniquely identifies the package.
It can be found in the package manifest or by opening the package in the App-V Sequencer.
The package IDs are shared by all versions of a specific package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of an App-V package in one lineage.
If you do not specify this parameter, the cmdlet operates on all versions on the computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies a GUID that differentiates a package version from other versions, whether older, newer, or of a different lineage.
If you do not specify this parameter, the cmdlet operates on all versions of the package.

```yaml
Type: Guid
Parameter Sets: ByGuid
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AppvAgent.AppvClientPackage

## OUTPUTS

### Microsoft.AppvAgent.AppvClientPackage

## NOTES
* If a previous mount has been canceled, the cmdlet resumes that mount when it is run again. The package must be added to the system before mounting. Otherwise the cmdlet fails. If you do not specify any parameters, the cmdlet mounts all packages on the system.
* This cmdlet is synchronous. It returns when the mount option has completed. To make the cmdlet asynchronous, use the **Start-Job** cmdlet.

## RELATED LINKS

[Add-AppvClientPackage](./Add-AppvClientPackage.md)

[Get-AppvClientPackage](./Get-AppvClientPackage.md)

[Publish-AppvClientPackage](./Publish-AppvClientPackage.md)

[Remove-AppvClientPackage](./Remove-AppvClientPackage.md)

[Repair-AppvClientPackage](./Repair-AppvClientPackage.md)

[Set-AppvClientPackage](./Set-AppvClientPackage.md)

[Stop-AppvClientPackage](./Stop-AppvClientPackage.md)

[Unpublish-AppvClientPackage](./Unpublish-AppvClientPackage.md)

