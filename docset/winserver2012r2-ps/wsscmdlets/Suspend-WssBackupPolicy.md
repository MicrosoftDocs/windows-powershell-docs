---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Suspend-WssBackupPolicy
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: C1A93E15-CFC5-4E18-995E-A9715C52DC60
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Suspend-WssBackupPolicy

## SYNOPSIS
Stops a scheduled task from running the next scheduled backup.

## SYNTAX

```
Suspend-WssBackupPolicy [-BackupPolicy] <ScheduledBackupPolicy> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-WssBackupPolicy** cmdlet stops a scheduled task from running the next scheduled backup.

## EXAMPLES

### Example 1: Suspend a backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WBPolicy
PS C:\> Suspend-WssBackupPolicy -BackupPolicy $ContosoBUPolicy25
```

This example suspends a backup policy.

The first command gets the backup policy for the computer and stores it in the variable named $ContosoBUPolicy25.

The second command suspends the backup policy that is stored in $ContosoBUPolicy25.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to suspend.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.ScheduledBackupPolicy
This cmdlet generates the **BackupPolicy** parameter value.

## NOTES

## RELATED LINKS

[Disable-WssBackupPolicy](./Disable-WssBackupPolicy.md)

[Get-WssBackupPolicy](./Get-WssBackupPolicy.md)

[Resume-WssBackupPolicy](./Resume-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

