---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssglobalclientbackuppolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssGlobalClientBackupPolicy

## SYNOPSIS
Changes the global client backup policy.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-WssGlobalClientBackupPolicy [-BackupEndTime <TimeSpan>] [-BackupStartTime <TimeSpan>]
 [-DailyRetainCount <UInt32>] [-MonthlyRetainCount <UInt32>] [-WeeklyRetainCount <UInt32>]
 [-YearlyRetainCount <UInt32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-WssGlobalClientBackupPolicy [-Default] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssGlobalClientBackupPolicy** cmdlet changes the global client backup policy.
This policy includes the following values: 

- BackupStartTime.
The beginning of the backup window.
The default value is 18:00.
- BackupEndTime.
The end of the backup window.
The default value is 9:00.
- DailyRetainCount.
The number of daily backups to keep.
The default value is five. 
- WeeklyRetainCount.
The number of weekly backups to keep.
The default value is four.
- MonthlyRetainCount.
The number of monthly backups to keep.
The default value is six. 
- YearlyRetainCount.
The number of yearly backups to keep.
The default value is ten.

This cmdlet can change any of these values, or you can use the **Default** parameter to reset all the settings to the default values.

## EXAMPLES

### Example 1: Change the backup window for the global policy
```
PS C:\> Set-WssGlobalClientBackupPolicy -BackupEndTime 8:00 -BackupStartTime 19:00
```

This command changes the backup window for the global backup policy.
The command specifies new start and end times for the policy.

### Example 2: Restore default settings for the backup policy
```
PS C:\> Set-WssGlobalClientBackupPolicy -Default
```

This command restores default settings for the global backup policy.
The command includes the **Default** parameter.

## PARAMETERS

### -BackupEndTime
Specifies the end of the backup window as a **TimeSpan** object.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupStartTime
Specifies the beginning of the backup window as a **TimeSpan** object.

```yaml
Type: TimeSpan
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DailyRetainCount
Specifies the number of daily backups to keep.
The default value is five.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Default
Indicates that the cmdlet resets all the settings to their default values.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthlyRetainCount
Specifies the number of monthly backups to keep.
The default value is six.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeklyRetainCount
Specifies the number of weekly backups to keep.
The default value is four.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -YearlyRetainCount
Specifies the number of yearly backups to keep.
The default value is ten.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

[Get-WssGlobalClientBackupPolicy](./Get-WssGlobalClientBackupPolicy.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

