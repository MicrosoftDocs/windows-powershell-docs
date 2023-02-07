---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/stop-wssclientbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-WssClientBackup

## SYNOPSIS
Cancels a client backup for a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-WssClientBackup [-ComputerName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Stop-WssClientBackup [-ComputerSid] <String>
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

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

