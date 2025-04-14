---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 10/04/2022
online version: https://learn.microsoft.com/powershell/module/storagereplica/new-srpartnership?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SRPartnership
---

# New-SRPartnership

## SYNOPSIS
Creates a replication partnership between two replication groups.

## SYNTAX

### CreatePartnership (Default)

```
New-SRPartnership [[-SourceComputerName] <String>] [-SourceRGName] <String>
 [-DestinationComputerName] <String> [-DestinationRGName] <String>
 [[-ReplicationMode] <ReplicationMode>] [-PreventReplication] [-Seeded] [[-AsyncRPO] <UInt32>]
 [-EnableEncryption] [-EnableCompression] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### CreateTopology

```
New-SRPartnership [[-SourceComputerName] <String>] [-SourceRGName] <String>
 [-SourceVolumeName] <String[]> [-SourceLogVolumeName] <String> [[-SourceRGDescription] <String>]
 [-DestinationComputerName] <String> [-DestinationRGName] <String>
 [-DestinationVolumeName] <String[]> [-DestinationLogVolumeName] <String>
 [[-DestinationRGDescription] <String>] [[-ReplicationMode] <ReplicationMode>]
 [[-LogSizeInBytes] <UInt64>] [-PreventReplication] [-Seeded] [-EnableConsistencyGroups]
 [[-AsyncRPO] <UInt32>] [-EnableEncryption] [-EnableCompression] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `New-SRPartnership` cmdlet creates a replication partnership between two new or existing
replication groups. This cmdlet can create the complete replication topology. It can also tie
together separately created replication groups.

## EXAMPLES

### Example 1: Create a topology between two servers

```powershell
$Parameters = @{
    SourceComputerName = 'SR-SRV05'
    SourceRGName = 'ReplicationGroup01'
    SourceVolumeName = 'D:'
    SourceLogVolumeName = 'E:'
    DestinationComputerName = 'SR-SRV06'
    DestinationRGName = 'ReplicationGroup02'
    DestinationVolumeName = 'D:'
    DestinationLogVolumeName = 'E:'
}
New-SRPartnership @Parameters
```

This command creates a replication topology between servers `SR-SRV05` and `SR-SRV06`. The
`SR-SRV05` server is the source and `SR-SRV06` is the destination, with volume `D:` used as both the
source and destination. The `E:` volume contains the logs for this partnership. The log has the
default value of 8GB. As the replication mode has not been specified, it will use the default value
of synchronous. The command does not specify seeding, encryption, and consistency groups.
Replication will start immediately.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 2: Pair existing groups

```powershell
$Parameters = @{
    SourceComputerName = 'SR-SRV05'
    SourceRGName = 'ReplicationGroup01'
    DestinationComputerName = 'SR-SRV06'
    DestinationRGName = 'ReplicationGroup02'
}
New-SRGroup -ComputerName "SR-SRV05" -Name "ReplicationGroup01" -VolumeName "D:" -LogVolumeName "E:"
New-SRGroup -ComputerName "SR-SRV06" -Name "ReplicationGroup02" -VolumeName "D:" -LogVolumeName "E:"
New-SRPartnership @Parameters"
```

This example creates two replication groups separately and then creates a partnership between those
groups.

The example uses splatting to pass parameter values from the `$Parameters` variable to the command.
Learn more about [Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsyncRPO

Specifies the maximum difference in time, in seconds, that data for an asynchronous partnership can
be different between source and destination. This is a Recovery Point Objective. The minimum value
is 30 seconds. The default value is 5 minutes.

After exceeding this time, the source server alerts the Health Service on clusters. It logs event
1239 in the Storage Replica Admin event log channel. If the RPO time is lower than the configured
time, event 1240 is logged.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: RPO

Required: False
Position: 51
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or
[Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the current
session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName

Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of the
destination computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DCN

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationLogVolumeName

Specifies a drive letter, mount point path, or volume GUID where Storage Replication creates
destination replication logs. The volume must contain an NTFS-formatted volume or ReFS-formatted
volume. The path must exist. The path cannot be a mapped drive or UNC path.

Storage Replication creates logs in the System Volume Information folder.

```yaml
Type: String
Parameter Sets: CreateTopology
Aliases: DLV

Required: True
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGDescription

Specifies a description for the destination replication group.

```yaml
Type: String
Parameter Sets: CreateTopology
Aliases: DGD

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationRGName

Specifies a name for the destination replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DGN

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationVolumeName

Specifies an array of drive letters or mount point paths of partitions for the replica. The volumes
must exist. The volumes cannot be mapped drives or UNC paths. You can omit the colon symbol when you
specify drive letters.

This is an ordered list. The order of volumes determines the order of replication.

For instance, to replicate the F: and H: drives on one server to the F: and H: drives of another
server, specify the following values:

`-SourceVolumeName "F:","H:" -DestinationVolumeName "F:","H:"`

 To replicate F: to H: instead, specify the following values:

`-SourceVolumeName "F:","H:" -DestinationVolumeName "H:","F:"`

We do not recommend replicating different drive letters or mount point paths. This practice can
cause application failures because of stored settings after a failover occurs.

```yaml
Type: String[]
Parameter Sets: CreateTopology
Aliases: DVN

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableCompression

Indicates that the connections in this partnership should use SMB compression for data transfer.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ECMP

Required: False
Position: 99
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableConsistencyGroups

Indicates that consistency groups are enabled for the replication group that contains multiple
volumes. Consistency groups provide write ordering. This can be important, for example, for
replication of application data on multiple volumes. If you enable consistency groups, it may
decrease replication and write Input/Output performance.

```yaml
Type: SwitchParameter
Parameter Sets: CreateTopology
Aliases: EC

Required: False
Position: 14
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEncryption

Indicates that this partnership should encrypt connections by using SMB AES-128-GCM. Enabling
encryption can protect Storage Replica block transfers from man-in-the-middle interception or
reading. Enabling encryption decreases replication and write Input/Output performance.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: EE

Required: False
Position: 99
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogSizeInBytes

Specifies the aggregate size of log files on each server in the replication group for the volumes
that are associated with this replication group. The minimum size 512MB. You can specify a value by
using the Windows PowerShell byte conversion capability, such as 4GB or 3200MB. A value that is too
small may cause decreased replication performance or increased recovery time after an interruption
between computers.

```yaml
Type: UInt64
Parameter Sets: CreateTopology
Aliases: LS

Required: False
Position: 11
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreventReplication

Indicates that this cmdlet prevent replication from starting immediately. By default, replication
starts automatically at the time that you create the partnership. To start replication later, use
the `Sync-SRGroup` cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: P

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicationMode

Specifies the desired mode of replication for this source and destination pair. The acceptable
values for this parameter are:

- Synchronous or 1. The synchronous mode requires all writes to commit on the destination server and
  on the source server, which guarantees data integrity between computers.
- Asynchronous or 2. The asynchronous mode writes to the source server without waiting for the
  destination server, which allows for replication over high latency, geographic networks.

The default value is synchronous.

The default asynchronous recovery point alert time is 5 minutes. You can modify it by using the
`Set-SRPartnership` cmdlet. The alert time has no effect on replication behavior, only on reporting.

```yaml
Type: ReplicationMode
Parameter Sets: (All)
Aliases: RM
Accepted values: Synchronous, Asynchronous

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Seeded

Indicates that the destination server contains a seeded copy of the data from the source server.
Seeded data is defined as a copy of data from the source server that has a high similarity, such as
mostly empty blocks, restoring a recent backup, or shipping cloned copies of disks to the
destination server.

Seeding is most effective when using a previous copy of the storage, such as a split mirror or
previously replicated drives, or when the storage is mostly empty and was always empty, such as a
recently initialized drive with a newly formatted volume. Seeding is somewhat effective with data
that came from a backup restore or a complete tree copy of data or from copies of very large files.

Seeding is least effective when copying large numbers of small files from some random locations to
some other random locations. Storage Replica automatically uses seeding when it restarts replication
after a long outage that wrapped the logs.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: S

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputerName

Specifies a single replica host computer NetBIOS name or FQDN of the source computer. The default
value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceLogVolumeName

Specifies a drive letter, mount point path, or volume GUID where Storage Replication creates source
replication logs. The volume must contain an NTFS-formatted volume or ReFS-formatted volume. The
path must exist. The path cannot be a mapped drive or UNC path.

Storage Replication creates logs in the System Volume Information folder.

```yaml
Type: String
Parameter Sets: CreateTopology
Aliases: SLN

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceRGDescription

Specifies a description for the source replication group.

```yaml
Type: String
Parameter Sets: CreateTopology
Aliases: SGD

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRGName

Specifies the name of the source replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SGN

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceVolumeName

Specifies an array of drive letters or mount point paths of partitions for the replica. The volumes
must exist. The volumes cannot be mapped drives or UNC paths.

This is an ordered list. The order of volumes determines the order of replication. For more
information, see the **DestinationVolumeName** parameter.

```yaml
Type: String[]
Parameter Sets: CreateTopology
Aliases: SVN

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

### replicationgroups

## NOTES

## RELATED LINKS

[Get-SRPartnership](Get-SRPartnership.md)

[New-SRGroup](New-SRGroup.md)

[Remove-SRPartnership](Remove-SRPartnership.md)

[Set-SRPartnership](Set-SRPartnership.md)

[Sync-SRGroup](Sync-SRGroup.md)
