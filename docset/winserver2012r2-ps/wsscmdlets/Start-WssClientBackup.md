---
author: Kateyanne
description: 
external help file: WssCmdlets.dll-Help.xml
manager: jasgro
Module Name: WSSCmdlets
ms.author: v-kaunu
ms.date: 12/05/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/start-wssclientbackup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WssClientBackup
---

# Start-WssClientBackup

## SYNOPSIS
Starts a client backup for a computer.

## SYNTAX

### ByName (Default)
```
Start-WssClientBackup [-Description] <String> [-ComputerName] <String> [<CommonParameters>]
```

### BySid
```
Start-WssClientBackup [-Description] <String> [-ComputerSid] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssClientBackup** cmdlet starts a client backup for a computer.
Specify a computer by name or security identifier (SID).
Include a description for the backup job.

## EXAMPLES

### Example 1: Start a client backup
```
PS C:\> Start-WssClientBackup -ComputerName "Workstation073" -Description "End of month backup"
```

This command starts a client backup for a computer named Workstation073.
The command specifies a description.

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

### -Description
Specifies a description for the backup job.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

