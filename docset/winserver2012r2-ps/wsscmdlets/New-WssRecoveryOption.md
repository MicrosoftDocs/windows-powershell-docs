---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: New-WssRecoveryOption
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9D2B573F-9668-4437-B8BC-2284E24E372E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-WssRecoveryOption

## SYNOPSIS
Creates a recovery configuration for a file restore operation.

## SYNTAX

```
New-WssRecoveryOption [-OverwriteExisting] [-RestoreAcl] [<CommonParameters>]
```

## DESCRIPTION
The **New-WssRecoveryOption** cmdlet creates a recovery configuration that a later file restore operation can use to determine which files to restore.

## EXAMPLES

### Example 1: Create a recovery configuration
```
PS C:\> $RecoverOpt15 = New-WssRecoveryOption -RestoreAcl
```

This command creates a configuration for a file restore operation that includes the ACL along with files and stores the configuration in the variable named $RecoverOpt15.

## PARAMETERS

### -OverwriteExisting
Indicates that the restore operation overwrites existing files.

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

### -RestoreAcl
Indicates that the cmdlet restores an access control list (ACL) along with files.
An ACL is a list of the users and groups that have permission to view or change a file.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.RecoveryOptions
This cmdlet generates recovery options.

## NOTES

## RELATED LINKS

[Get-WssRecoveryItem](./Get-WssRecoveryItem.md)

