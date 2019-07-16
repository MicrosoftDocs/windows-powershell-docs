---
external help file: WssCmdlets.dll-Help.xml
online version: 
schema: 2.0.0
title: Disable-WssClientBackupVolume
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-12-05
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 2825A6B0-A54E-4A38-881C-A998F84DA4AA
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Disable-WssClientBackupVolume

## SYNOPSIS
Disables backup for a volume on a client.

## SYNTAX

### ByName (Default)
```
Disable-WssClientBackupVolume [-VolumeGuid] <Guid> [-ComputerName] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BySid
```
Disable-WssClientBackupVolume [-VolumeGuid] <Guid> [-ComputerSid] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
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

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

[Get-WssClientBackupVolumeJob](./Get-WssClientBackupVolumeJob.md)

