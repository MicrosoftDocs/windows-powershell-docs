---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssclientbackupvolumejob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssClientBackupVolumeJob

## SYNOPSIS
Gets backup information for a backup volume job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WssClientBackupVolumeJob [-ComputerName] <String> [-BackupIndex] <Int32>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WssClientBackupVolumeJob [-ComputerSid] <String> [-BackupIndex] <Int32>
```

## DESCRIPTION
The **Get-WssClientBackupVolumeJob** cmdlet gets backup information for a backup volume job.
Specify a computer by name or security identifier (SID).
Specify a job by using its index.

## EXAMPLES

### Example 1: Get backup volume job information
```
PS C:\> Get-WssClientBackupVolumeJob -ComputerName "Workstation073" -BackupIndex 1
```

This command gets information for a backup volume job for the computer named Workstation073.
The command specifies the backup index of the job.

## PARAMETERS

### -BackupIndex
Specifies the index for a backup volume job.

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

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.VolumeJobInfo

## NOTES

## RELATED LINKS

[Disable-WssClientBackupVolume](./Disable-WssClientBackupVolume.md)

[Enable-WssClientBackupVolume](./Enable-WssClientBackupVolume.md)

[Get-WssClientBackupVolume](./Get-WssClientBackupVolume.md)

