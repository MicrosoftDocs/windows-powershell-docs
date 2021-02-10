---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-Help.xml
Module Name: Appx
online version: 
schema: 2.0.0
title: Get-AppxPackageManifest
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9F4A31F1-9110-4A66-BF20-961CC447DFC8
---

# Get-AppxPackageManifest

## SYNOPSIS
Gets the manifest of an app package (.appx).

## SYNTAX

```
Get-AppxPackageManifest [-Package] <String> [[-User] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxPackageManifest** cmdlet gets the manifest of an app package (.appx).
The manifest is a .xml document that contains information about the package, like the package ID.

## EXAMPLES

### Example 1
```
PS C:\>Get-AppxPackageManifest -Package package1_1.0.0.0_neutral__8wekyb3d8bbwe
```

This command gets the manifest for an app package that's named package1_1.0.0.0_neutral__8wekyb3d8bbwe.

### Example 2
```
PS C:\>(Get-AppxPackage -Name "*WinJS*" | Get-AppxPackageManifest).package.applications.application.id
```

This command gets the application ID for an app package (.appx) that has "WinJS" in the name.

### Example 3
```
PS C:\>(Get-AppxPackage -Name "*ZuneMusic*" | Get-AppxPackageManifest).Package.Capabilities
```

This command gets the capabilities for an app package (.appx) that has "ZuneMusic" in the name.

## PARAMETERS

### -Package
Specifies an AppxPackage object or the full name of a package.
To get the manifest of a package on the computer that isn't installed for the current user, you must run this command by using administrator permissions.
Wildcards are permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -User
that are installed for the specified user.
To get the list of packages for a user profile other than the profile for the current user, you must run this command by using administrator permissions.
The user name can be in one of these formats:

-- domain\user_name
-- user_name@fqn.domain.tld
-- user_name
-- SID-string

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.Appx.PackageManager.Commands.AppxPackage[]
An array of AppxPackage objects that contain information, including the full name of the app package (.appx).

## OUTPUTS

### System.XML.XMLDocument
A read-only .xml document that contains information about the app package (.appx), like the package ID.

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Add-AppxPackage](./Add-AppxPackage.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)

[Get-AppxLog](./Get-AppxLog.md)

[Get-AppxLastError](./Get-AppxLastError.md)

