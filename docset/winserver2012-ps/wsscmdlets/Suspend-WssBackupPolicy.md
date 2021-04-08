---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/suspend-wssbackuppolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Suspend-WssBackupPolicy

## SYNOPSIS
Stops a scheduled task from running the next scheduled backup.

## SYNTAX

```
Suspend-WssBackupPolicy [-BackupPolicy] <ScheduledBackupPolicy> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Suspend-WssBackupPolicy** cmdlet stops a scheduled task from running the next scheduled backup.

## EXAMPLES

### Example 1: Suspend a backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WBPolicy PS C:\>Suspend-WssBackupPolicy -BackupPolicy $ContosoBUPolicy25
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssBackupPolicy](./Disable-WssBackupPolicy.md)

[Get-WssBackupPolicy](./Get-WssBackupPolicy.md)

[Resume-WssBackupPolicy](./Resume-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

