---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsServerApplication
ms.assetid: 368AA5D3-5523-47EE-8A0A-049CB8D7AB37
---

# Get-AdfsServerApplication

## SYNOPSIS
Gets configuration settings for a server application role for an application in AD FS.

## SYNTAX

### Identifier (Default)
```
Get-AdfsServerApplication [[-Identifier] <String[]>] [<CommonParameters>]
```

### Name
```
Get-AdfsServerApplication [-Name] <String[]> [<CommonParameters>]
```

### ApplicationObject
```
Get-AdfsServerApplication [-Application] <ServerApplication> [<CommonParameters>]
```

### ApplicationGroupIdentifier
```
Get-AdfsServerApplication [-ApplicationGroupIdentifier] <String> [<CommonParameters>]
```

### ApplicationGroupObject
```
Get-AdfsServerApplication [-ApplicationGroup] <ApplicationGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsServerApplication** cmdlet gets configuration settings for a server application role for an application in Active Directory Federation Services (AD FS).

## EXAMPLES


## PARAMETERS

### -Application
Specifies the server application to get.

```yaml
Type: ServerApplication
Parameter Sets: ApplicationObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationGroup
Specifies the application group from which to get server applications.

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
Specifies the ID of the application group from which to get server applications.

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
Specifies an array of IDs of the application groups from which to get server applications.

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
Specifies an array of names of the application groups from which to get server applications.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsServerApplication](./Add-AdfsServerApplication.md)

[Remove-AdfsServerApplication](./Remove-AdfsServerApplication.md)

[Set-AdfsServerApplication](./Set-AdfsServerApplication.md)

