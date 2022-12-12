---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssclientbackup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssClientBackup

## SYNOPSIS
Gets information about client backup jobs.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WssClientBackup [-ComputerName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WssClientBackup [-ComputerSid] <String>
```

## DESCRIPTION
The **Get-WssClientBackup** cmdlet gets information about client backup jobs for a computer.
Specify a computer by name or security identifier (SID).

## EXAMPLES

### Example 1: Get client backup job information
```
PS C:\> Get-WssClientBackup -ComputerName "Workstation073"
```

This command gets information for client backup jobs for a computer named Workstation073.

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

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.ClientJobInfo

## NOTES

## RELATED LINKS

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

