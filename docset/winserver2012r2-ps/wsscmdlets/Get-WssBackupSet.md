---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WssBackupSet
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: DB52B2F9-16B3-401F-9814-8A9C026C8EE6
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-WssBackupSet

## SYNOPSIS
Gets a collection of backup sets from a server backup.

## SYNTAX

```
Get-WssBackupSet [[-BackupTarget] <BackupTarget>] [[-MachineName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupSet** cmdlet gets a collection of backup sets from a server backup.
A backup set is the output of a successful backup operation.

## EXAMPLES

### Example 1: Get backup sets from a server backup
```
PS C:\> Get-WssBackupSet -BackupTarget $ContosoWest01
```

This command gets a list of backup sets from the server backup that is stored in the variable named **$ContosoWest01**.

## PARAMETERS

### -BackupTarget
Specifies the target volume from which to get the backup sets.

```yaml
Type: BackupTarget
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MachineName
Specifies the name of the server whose data is in the backup set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.BackupSet
This cmdlet returns a backup set.

## NOTES

## RELATED LINKS

[Get-WssBackupJob](./Get-WssBackupJob.md)

[Start-WssBackupJob](./Start-WssBackupJob.md)

[Stop-WssBackupJob](./Stop-WssBackupJob.md)

