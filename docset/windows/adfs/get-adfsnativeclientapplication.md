---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 528740AC-B18F-4201-8178-1C1FFD51994A
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsNativeClientApplication
ms.reviewer:
---

# Get-AdfsNativeClientApplication

## SYNOPSIS
Gets native client application roles from an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Get-AdfsNativeClientApplication [[-Identifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsNativeClientApplication [-Name] <String[]> [<CommonParameters>]
```

### ApplicationObject
```
Get-AdfsNativeClientApplication [-Application] <NativeClientApplication> [<CommonParameters>]
```

### ApplicationGroupIdentifier
```
Get-AdfsNativeClientApplication [-ApplicationGroupIdentifier] <String> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsNativeClientApplication [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsNativeClientApplication** cmdlet gets native client application roles from an application in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -Application
Specifies the native client application to get.

```yaml
Type: NativeClientApplication
Parameter Sets: ApplicationObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroup
Specifies the application group from which to get native client applications.

```yaml
Type: ApplicationGroup
Parameter Sets: ApplicationGroupObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroupIdentifier
Specifies the ID of the application group from which to get native client applications.

```yaml
Type: String
Parameter Sets: ApplicationGroupIdentifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identifier
Specifies an array of IDs of native client applications get.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of native client applications get.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.IdentityServer.Management.Resources.ApplicationGroup
System.Uri[]

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.NativeClientApplication
ApplicationGroupIdentifier  string
Description                 string
Enabled                     bool
Identifier                  string
Name                        string
RedirectUri                 string[]

## NOTES

## RELATED LINKS

[Add-AdfsNativeClientApplication](./Add-AdfsNativeClientApplication.md)

[Remove-AdfsNativeClientApplication](./Remove-AdfsNativeClientApplication.md)

[Set-AdfsNativeClientApplication](./Set-AdfsNativeClientApplication.md)

