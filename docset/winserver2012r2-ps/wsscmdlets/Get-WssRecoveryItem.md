---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssRecoveryItem
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: D6C1F900-9AB6-4864-9DDC-82A8670D5C5B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WssRecoveryItem

## SYNOPSIS
Gets child recovery items from a parent recovery item.

## SYNTAX

```
Get-WssRecoveryItem [-Parent] <RecoveryItem> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssRecoveryItem** cmdlet gets child recovery items from a parent recovery item. 
When you restore a file or folder, this cmdlet helps you locate the file or folder to restore by browsing from the root folder to the child folders, until you locate the missing folder.

## EXAMPLES

### Example 1: Get child recovery items
```
PS C:\> $ContosoRecOptions05Child = Get-WssRecoveryItem -Parent $ContosoRecOptions05Parent
```

This command gets child recovery options from the parent node that is stored in the variable named $ContosoRecOptions05Parent and stores those options in the variable named $ContosoRecOptions05Child.

## PARAMETERS

### -Parent
Specifies the parent recovery item.

```yaml
Type: RecoveryItem
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

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.RecoveryItem
This cmdlet generates a recovery item.

## NOTES

## RELATED LINKS

[New-WssRecoveryOption](./New-WssRecoveryOption.md)

