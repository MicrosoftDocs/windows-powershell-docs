---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Get-VMSwitchExtension
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 38546FDC-E327-4EAE-A851-E6C55615D982
---

# Get-VMSwitchExtension

## SYNOPSIS
Gets the extensions on one or more virtual switches.

## SYNTAX

### SwitchName (Default)
```
Get-VMSwitchExtension [-VMSwitchName] <String[]> [[-Name] <String[]>] [-ComputerName <String[]>]
 [<CommonParameters>]
```

### SwitchObject
```
Get-VMSwitchExtension [-VMSwitch] <VMSwitch[]> [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchExtension** cmdlet gets the extensions on one or more virtual switches.
These extensions may be of different types, and may be either enabled or disabled.
Output can be filtered by extension.
The retrieved extension object does not contain embedded objects for features, or an array of feature IDs.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMSwitch InternalSwitch | Get-VMSwitchExtension
```

Gets all virtual switch extensions available to the virtual switch InternalSwitch.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts on which the extensions are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SwitchName
Aliases: PSComputerName

Required: False
Position: Named
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the extension to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch from which the extensions are to be retrieved.

```yaml
Type: VMSwitch[]
Parameter Sets: SwitchObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchName
Specifies the name of the virtual switch from which the extensions are to be retrieved.

```yaml
Type: String[]
Parameter Sets: SwitchName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.SwitchExtension

## NOTES

## RELATED LINKS

