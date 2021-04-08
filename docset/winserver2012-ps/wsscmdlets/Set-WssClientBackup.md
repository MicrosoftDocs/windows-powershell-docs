---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssclientbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-WssClientBackup

## SYNOPSIS
Changes job retention policy and description for a client backup.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-WssClientBackup [-ComputerName] <String> [-BackupIndex] <Int32> [-Description <String>] [-Retention]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-WssClientBackup [-ComputerSid] <String> [-BackupIndex] <Int32> [-Description <String>] [-Retention]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-WssClientBackup** cmdlet changes job retention policy and description for a client backup for a computer.
Specify a computer by name or security identifier (SID).
Specify which backup to change by using its backup index.

## EXAMPLES

### Example 1: Change a description for a client backup
```
PS C:\> Set-WssClientBackup -ComputerName "Workstation073" -BackupIndex 1 -Description "January backup"
```

This command changes the description for a backup of the computer named Workstation073.
The command specifies the backup by using its index.
The description is January backup.

## PARAMETERS

### -BackupIndex
Specifies the index for a backup job.
To obtain a backup index, use the Get-WssClientBackup cmdlet.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerSid
Specifies the SID of a computer.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the backup.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Retention
Specifies a retention policy for the backup.
The acceptable values for this parameter are:

- Automatic
- Delete
- Keep

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Automatic, Delete, Invalid, Keep

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

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

