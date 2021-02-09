---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Enable-SecurityPolicy
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C07A0E06-13F1-4CF5-95CB-6894459E75FA
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Enable-SecurityPolicy

## SYNOPSIS
Enables predefined security group policies.

## SYNTAX

### All
```
Enable-SecurityPolicy [-AllPolicy] [<CommonParameters>]
```

### Specific
```
Enable-SecurityPolicy -Policy <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SecurityPolicy** cmdlet enables pre-defined group policies for security features.
The cmdlet enables group policies for Windows Defender, Windows Update, and Windows Firewall.

## EXAMPLES

### Example 1: Enable predefined security group policies
```
PS C:\> Enable-SecurityPolicy -Policy "WindowsUpdate"
```

This command enables the security group policy for Windows Update.

## PARAMETERS

### -AllPolicy
Indicates that the cmdlet enables all pre-defined group policies for Windows Update, Windows Firewall, and Windows Defender.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies an array of group policies to enable.
The acceptable values for this parameter are:

- WindowsUpdate
- Firewall
- WindowsDefender

```yaml
Type: String[]
Parameter Sets: Specific
Aliases: 
Accepted values: WindowsUpdate, Firewall, WindowsDefender

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-SecurityPolicy](./Disable-SecurityPolicy.md)

