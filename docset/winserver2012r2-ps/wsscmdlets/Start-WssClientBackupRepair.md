---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Start-WssClientBackupRepair
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E5FD7B3D-C0BE-4681-867D-47AE093F1C38
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Start-WssClientBackupRepair

## SYNOPSIS
Starts an attempt to repair the database of client computer backups.

## SYNTAX

```
Start-WssClientBackupRepair [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssClientBackupRepair** cmdlet starts an attempt to repair the database of client computer backups.
You can use this cmdlet in the event that the database becomes corrupt or unusable.

## EXAMPLES

### Example 1: Start client backup database repair
```
PS C:\> Start-WssClientBackupRepair
```

This command starts an attempt to repair the client backup database.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Stop-WssClientBackupRepair](./Stop-WssClientBackupRepair.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

