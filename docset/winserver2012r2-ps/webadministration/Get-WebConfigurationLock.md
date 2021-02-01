---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebConfigurationLock
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9B0D4DDB-F6AB-4986-90A7-600F5EBE5B86
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WebConfigurationLock

## SYNOPSIS
Gets the lock status of an IIS configuration location.

## SYNTAX

```
Get-WebConfigurationLock [-Location <String[]>] [-Filter] <String[]> [[-PSPath] <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebConfigurationLock** cmdlet gets the locking status of the specified Internet Information Services (IIS) configuration location.

## EXAMPLES

### Example 1: Get the locking status of an IIS configuration
```
IIS:\>Get-WebConfigurationLock -Filter "//asp" -PSPath "IIS:\"
```

This command returns the locking status of the asp IIS configuration section.

## PARAMETERS

### -Filter
Specifies an XPath filter expression.
This expression can be in XPath format.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the IIS configuration setting.

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

### -PSPath
Specifies an IIS configuration path in the format computer name/webroot/apphost.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WebConfigurationLock](./Add-WebConfigurationLock.md)

[Remove-WebConfigurationLock](./Remove-WebConfigurationLock.md)

