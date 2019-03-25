---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: New-WebAppPool
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: CBFB45D2-3658-41FA-BDEB-13920DF3908F
ms.author: kenwith
ms.reviewer: brianlic
---

# New-WebAppPool

## SYNOPSIS
Creates an IIS application pool.

## SYNTAX

```
New-WebAppPool [-Name] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **New-WebAppPool** cmdlet creates an Internet Information Services (IIS) application pool.

## EXAMPLES

### Example 1: Create new an IIS application pool
```
IIS:\>New-WebAppPool -Name "NewAppPool"
```

This command creates an IIS application pool named NewAppPool.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the IIS application pool to create.

```yaml
Type: String
Parameter Sets: (All)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-WebAppPool](./Remove-WebAppPool.md)

[Restart-WebAppPool](./Restart-WebAppPool.md)

[Start-WebAppPool](./Start-WebAppPool.md)

[Stop-WebAppPool](./Stop-WebAppPool.md)

