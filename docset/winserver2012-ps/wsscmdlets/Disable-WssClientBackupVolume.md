---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/disable-wssclientbackupvolume?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-WssClientBackupVolume

## SYNOPSIS
Disables backup for a volume on a client.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-WssClientBackupVolume [-ComputerName] <String> [-VolumeGuid] <Guid> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-WssClientBackupVolume [-ComputerSid] <String> [-VolumeGuid] <Guid> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-WssClientBackupVolume** cmdlet disables client backup for a volume on a computer.
Specify a computer by name or security identifier (SID).
Specify a volume by using its GUID.

## EXAMPLES

### Example 1: Disable backup for a volume
```
PS C:\> Disable-WssClientBackupVolume -ComputerName "Workstation073" -VolumeGuid b6b093a2-1860-4172-a4a5-07ce2aebfa13
```

This command disables backup for the specified volume on the computer named Workstation073.

## PARAMETERS

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

### -VolumeGuid
Specifies the GUID of a volume.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

[Get-WssClientBackupVolumeJob](./Get-WssClientBackupVolumeJob.md)

