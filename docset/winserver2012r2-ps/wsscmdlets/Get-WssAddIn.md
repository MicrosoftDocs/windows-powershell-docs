---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssAddIn
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 9CC442EE-64AC-4E7D-8D17-79CDCA9980FC
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssAddIn

## SYNOPSIS
Gets installed add-ins.

## SYNTAX

```
Get-WssAddIn [[-Id] <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssAddIn** cmdlet gets the add-ins for an installed package.
If you do not specify the **Id** parameter, the cmdlet gets all installed add-ins on the local computer.

## EXAMPLES

### Example 1: Get all installed add-ins
```
PS C:\> Get-WssAddIn
```

This command gets all add-ins installed on the local computer.

## PARAMETERS

### -Id
Specifies the GUID for an installed package.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.AddinInfrastructure.PackageInfo
This cmdlet returns package information of specific add-ins.

## NOTES

## RELATED LINKS

[Install-WssAddIn](./Install-WssAddIn.md)

[Uninstall-WssAddIn](./Uninstall-WssAddIn.md)

