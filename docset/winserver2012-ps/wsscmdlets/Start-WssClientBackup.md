---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/start-wssclientbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-WssClientBackup

## SYNOPSIS
Starts a client backup for a computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-WssClientBackup [-ComputerName] <String> [-Description] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Start-WssClientBackup [-ComputerSid] <String> [-Description] <String>
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
Specifies a description for the backup job.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

