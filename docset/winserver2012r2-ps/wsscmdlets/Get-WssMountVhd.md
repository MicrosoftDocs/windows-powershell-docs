---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssMountVhd
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 07D67763-DB64-47D6-ADA2-BADD3714A4F8
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssMountVhd

## SYNOPSIS
Gets a collection of VHDs from a backup set.

## SYNTAX

```
Get-WssMountVhd [-BackupSet] <BackupSet> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssMountVhd** cmdlet gets a collection of virtual hard drives (VHDs) from a backup set.
Each VHD represents a backup volume in the set.

## EXAMPLES

### Example 1: Get VHDs from a backup set
```
PS C:\> $ContosoBUSet25VHD = Get-WssMountVhd -BackupSet $ContosoBUSet25
```

This example gets the VHD collection from the backup set that is stored in the variable named $ContosoBUSet25 and stores the collection in the variable named $ContosoBUSet25VHD.

## PARAMETERS

### -BackupSet
Specifies the backup set from which to get the collection of VHDs.

```yaml
Type: BackupSet
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

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.MountVhdData
This cmdlet generates the Mount Vhd data.

## NOTES

## RELATED LINKS

[Select-WssMountVhd](./Select-WssMountVhd.md)

