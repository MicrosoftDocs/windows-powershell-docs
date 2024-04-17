---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/enable-wssclientbackupvolume?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WssClientBackupVolume
---

# Enable-WssClientBackupVolume

## SYNOPSIS
Enables backup for a volume on a computer.

## SYNTAX

### ByName (Default)
```
Enable-WssClientBackupVolume [-VolumeGuid] <Guid> [-ComputerName] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BySid
```
Enable-WssClientBackupVolume [-VolumeGuid] <Guid> [-ComputerSid] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WssClientBackupVolume** cmdlet enables client backup for a volume on a computer.
Specify a computer by name or security identifier (SID).
Specify a volume by using its GUID.

## EXAMPLES

### Example 1: Enable backup for a volume
```
PS C:\> Enable-WssClientBackupVolume -ComputerName "Workstation073" -VolumeGuid b6b093a2-1860-4172-a4a5-07ce2aebfa13
```

This command enables backup for the specified volume on the computer named Workstation073.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerSid
Specifies the SID of a computer.

```yaml
Type: String
Parameter Sets: BySid
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### -VolumeGuid
Specifies the GUID of a volume.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

[Get-WssClientBackupVolumeJob](./Get-WssClientBackupVolumeJob.md)

