---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/stop-wssclientbackup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-WssClientBackup
---

# Stop-WssClientBackup

## SYNOPSIS
Cancels a client backup for a computer.

## SYNTAX

### ByName (Default)
```
Stop-WssClientBackup [-ComputerName] <String> [<CommonParameters>]
```

### BySid
```
Stop-WssClientBackup [-ComputerSid] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Stop-WssClientBackup** cmdlet cancels any currently running client backup for a computer.
Specify a computer by name or security identifier (SID).
Canceling a backup creates a partial backup, but does not cause the previous backup to be deleted.

## EXAMPLES

### Example 1: Cancel a client backup
```
PS C:\> Stop-WssClientBackup -ComputerName "Workstation073"
```

This command cancels any currently running client backup on the computer named Workstation073.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

