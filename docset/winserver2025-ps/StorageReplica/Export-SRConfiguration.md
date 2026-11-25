---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageReplica-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/export-srconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-SRConfiguration
---

# Export-SRConfiguration

## SYNOPSIS
Exports replication configuration to a Windows PowerShell script.

## SYNTAX

```
Export-SRConfiguration [[-ComputerName] <String>] [-Path] <String> [-Seeded] [-AllowClobber]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-SRConfiguration** cmdlet exports the replication configuration for a computer to a Windows PowerShell .ps1 configuration script.
You can use this .ps1 file as a configuration backup to reapply in event that Storage Replica settings are damaged or removed.
You can also use this file to migrate settings to another computer.

## EXAMPLES

### Example 1: Export configuration
```
This command exports all replication partnership and group information to a Windows PowerShell script named sr-srv01.ps1 in the C:\temp folder.
PS C:\>Export-SRConfiguration -Path "C:\temp\sr-srv01.ps1"
Exported 1 Storage Replica partnerships.
Exported 2 Storage Replica groups.

This command displays the contents of the script by using the Get-Content cmdlet.
PS C:\>Get-Content -Path "C:\temp\sr-srv01.ps1"
New-SRGroup -Computer SR-SRV01 -Name ReplicationGroup01 -VolumeName D:\ -LogVolumeName e:\ -LogSizeInBytes 8589934592
New-SRGroup -Computer SR-SRV03 -Name ReplicationGroup02 -VolumeName D:\ -LogVolumeName e:\ -LogSizeInBytes 8589934592
New-SRPartnership -SourceComputerName SR-SRV01 -SourceRGName ReplicationGroup01 -DestinationComputerName SR-SRV03 -DestinationRGName Rep
licationGroup02 -ReplicationMode Synchronous -PreventReplication
Write-Host Please execute Sync-SRGroup to resume replication.
```

## PARAMETERS

### -AllowClobber
Indicates that the cmdlet overwrites an existing file.
By default, this cmdlet does not overwrite an existing file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: AC

Required: False
Position: 99
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) for which this cmdlet exports configuration.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path of the exported configuration file, including the file name.
By default, this cmdlet does not overwrite an existing file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: P

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Seeded
Specifies that the destination computer contains a seeded copy of the data from the source server.
Seeded data is a copy of data from the source server, such as a restored backup or copies of drives.
Unused blocks also count toward seeding.
This option may reduce bandwidth usage during initial replication and is likely to use more CPU and memory.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: S

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

