---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssbackuppolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssBackupPolicy

## SYNOPSIS
Creates or changes a scheduled backup policy.

## SYNTAX

```
Set-WssBackupPolicy [-BackupPolicy] <ScheduledBackupPolicy> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssBackupPolicy** command creates or changes a scheduled backup policy.

## EXAMPLES

### Example 1: Specify a scheduled backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy PS C:\>Add-WssBackupSchedule -BackupPolicy $ContosoBUPolicy25 -BackupTime 5:00 PS C:\>Set-WssBackupPolicy -BackupPolicy $ContosoBUPolicy25
```

This example sets a scheduled backup policy as the current scheduled backup policy.

The first command gets the current backup policy for the computer and stores it in the **$ContosoBUPolicy25** variable.

The second command adds 5:00 A.M.
daily as a backup schedule for the backup policy stored in **$ContosoBUPolicy25**.

The third command sets the scheduled backup policy stored in **$ContosoBUPolicy25** (including the new schedule) as the current scheduled backup policy.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to create or change.

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

[Suspend-WssBackupPolicy](./Suspend-WssBackupPolicy.md)

