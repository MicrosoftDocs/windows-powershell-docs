---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 73476D36-C62C-484B-B674-9D549686C92C
manager: dansimp
---

# Get-WssClientBackupVolume

## SYNOPSIS
Gets the volume configuration of a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WssClientBackupVolume [-ComputerName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WssClientBackupVolume [-ComputerSid] <String>
```

## DESCRIPTION
The **Get-WssClientBackupVolume** cmdlet gets the volume configuration of a previously backed up computer.
Specify a computer by name or security identifier (SID).

## EXAMPLES

### Example 1: Get volume configuration for a client computer
```
PS C:\> Get-WssClientBackupVolume -ComputerName "Workstation073"
```

This command gets the volume configuration for a computer named Workstation073.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolumeJob](./Get-WssClientBackupVolumeJob.md)

