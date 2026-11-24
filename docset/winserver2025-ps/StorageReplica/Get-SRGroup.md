---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storagereplica/get-srgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SRGroup
---

# Get-SRGroup

## SYNOPSIS
Gets replication groups.

## SYNTAX

### FromPartnership
```
Get-SRGroup [-SourceComputerName] <String> [-SourceRGName] <String> [-DestinationComputerName] <String>
 [-DestinationRGName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### FromGroup
```
Get-SRGroup [[-ComputerName] <String>] [[-Name] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SRGroup** cmdlet gets replication groups.
A replication group contains replicated volumes, replication properties, and replication state.
Partnerships join replication groups to form a source and destination topology.

## EXAMPLES

### Example 1: Get all replication groups
```
PS C:\>Get-SRGroup
AllowVolumeResize  : False
AsyncRPO           :
ComputerName       : SR-SRV05
Description        :
Id                 : a19cc039-4cb0-47ad-b848-a1723858ff73
IsAutoFailover     :
IsCluster          : False
IsEncrypted        : False
IsInPartnership    : True
IsPrimary          : True
IsSuspended        : False
IsWriteConsistency : False
LastInSyncTime     :
LogSizeInBytes     : 8589934592
LogVolume          : e:\
Name               : ReplicationGroup01
NumOfReplicas      : 1
Partitions         : {6b3ee5ef-5a95-4685-a395-726ed3b644d3}
Replicas           : {MSFT_WvrReplica (PartitionId = "6b3ee5ef-5a95-4685-a395-726ed3b644d3")}
ReplicationMode    : Synchronous
ReplicationStatus  : ContinuouslyReplicating
PSComputerName     :
```

This command gets properties of all replication groups on the local computer.

### Example 2: Get a specific replication group
```
PS C:\>Get-SRGroup -SourceComputerName "SR-SRV05" -SourceRGName "ReplicationGroup01" -DestinationComputerName "SR-SRV06" -DestinationRGName "ReplicationGroup02"
AllowVolumeResize  : False
AsyncRPO           :
ComputerName       : SR-SRV05
Description        :
Id                 : a19cc039-4cb0-47ad-b848-a1723858ff73
IsAutoFailover     :
IsCluster          : False
IsEncrypted        : False
IsInPartnership    : True
IsPrimary          : True
IsSuspended        : False
IsWriteConsistency : False
LastInSyncTime     :
LogSizeInBytes     : 8589934592
LogVolume          : e:\
Name               : ReplicationGroup01
NumOfReplicas      : 1
Partitions         : {6b3ee5ef-5a95-4685-a395-726ed3b644d3}
Replicas           : {MSFT_WvrReplica (PartitionId = "6b3ee5ef-5a95-4685-a395-726ed3b644d3")}
ReplicationMode    : Synchronous
ReplicationStatus  : ContinuouslyReplicating
PSComputerName     :

AllowVolumeResize  : False
AsyncRPO           :
ComputerName       : SR-SRV06
Description        :
Id                 : d1b7923b-af5b-4b5c-9d26-eb5a071f244f
IsAutoFailover     :
IsCluster          : False
IsEncrypted        : False
IsInPartnership    : True
IsPrimary          : False
IsSuspended        : False
IsWriteConsistency : False
LastInSyncTime     : 9/6/2016 5:56:06 PM
LogSizeInBytes     : 8589934592
LogVolume          : e:\
Name               : ReplicationGroup02
NumOfReplicas      : 1
Partitions         : {eb517127-a5c8-48c6-8962-39036c0f3347}
Replicas           : {MSFT_WvrReplica (PartitionId = "eb517127-a5c8-48c6-8962-39036c0f3347")}
ReplicationMode    : Synchronous
ReplicationStatus  : ContinuouslyReplicating
PSComputerName     :
```

This command gets properties of a specific replication group on this computer.

### Example 3: Display replicas for all replication groups
```
PS C:\>(Get-SRGroup).replicas
CurrentLsn          : 54
DataVolume          : D:\
LastInSyncTime      :
LastKnownPrimaryLsn : 54
LastOutOfSyncTime   :
NumOfBytesRecovered : 165440
NumOfBytesRemaining : 0
PartitionId         : 6b3ee5ef-5a95-4685-a395-726ed3b644d3
PartitionSize       : 69145198592
ReplicationMode     : Synchronous
ReplicationStatus   : ContinuouslyReplicating
PSComputerName      :
```

This command displays properties of the Replicas object for all replication groups on this computer.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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

### -ComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of a computer for which this cmdlet gets groups.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: FromGroup
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the destination computer for which this cmdlet gets groups.

```yaml
Type: String
Parameter Sets: FromPartnership
Aliases: DCN

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGName
Specifies the name of the destination replication group that this cmdlet gets.

```yaml
Type: String
Parameter Sets: FromPartnership
Aliases: DN

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the replication group that this cmdlet gets.

```yaml
Type: String
Parameter Sets: FromGroup
Aliases: N

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the source computer for which this cmdlet gets groups.

```yaml
Type: String
Parameter Sets: FromPartnership
Aliases: SCN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceRGName
Specifies the name of the source replication group that this cmdlet gets.

```yaml
Type: String
Parameter Sets: FromPartnership
Aliases: SN

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### replicationgroup

## NOTES

## RELATED LINKS

[New-SRGroup](./New-SRGroup.md)

[Remove-SRGroup](./Remove-SRGroup.md)

[Set-SRGroup](./Set-SRGroup.md)

[Suspend-SRGroup](./Suspend-SRGroup.md)

[Sync-SRGroup](./Sync-SRGroup.md)

