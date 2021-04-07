---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
manager: jasgro
Module Name: StorageReplica
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/storagereplica/set-srpartnership?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SRPartnership
---

# Set-SRPartnership

## SYNOPSIS
Modifies a replication partnership between two replication groups.

## SYNTAX

### AddVolumes (Default)
```
Set-SRPartnership [[-SourceComputerName] <String>] [-SourceRGName] <String>
 [-SourceAddVolumePartnership] <String[]> [-DestinationComputerName] <String> [-DestinationRGName] <String>
 [-DestinationAddVolumePartnership] <String[]> [-Seeded] [-Force] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ModifySettings
```
Set-SRPartnership [[-SourceComputerName] <String>] [-SourceRGName] <String> [-DestinationComputerName] <String>
 [-DestinationRGName] <String> [[-ReplicationMode] <ReplicationMode>] [[-LogSizeInBytes] <UInt64>]
 [[-AsyncRPO] <UInt32>] [[-Encryption] <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ModifyPartnership
```
Set-SRPartnership [-SourceRGName] <String> [-DestinationComputerName] <String> [-DestinationRGName] <String>
 [-Force] [[-NewSourceComputerName] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SRPartnership** cmdlet modifies a replication partnership between two existing replication groups.
You can use this cmdlet to add replicated volumes.
You can also change the direction of replication which makes a source volume into a destination volume.

## EXAMPLES

### Example 1: Reverse replication direction
```
PS C:\>Set-SRPartnership -NewSourceComputerName "SR-SRV06" -SourceRGName "ReplicationGroup02" -DestinationComputerName "SR-SRV05" -DestinationRGName "ReplicationGroup01"
Confirm
Are you sure you want to perform this action? 
Performing operation "Set Source Replication Group" to replication group ReplicationGroup02. This may
result in data loss. Are you sure you want to continue? 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command changes the replication direction by an administrator after a disaster has occurred.
The previous source replication group named ReplicationGroup01 on previous source server SR-SRV05 becomes the new destination for ReplicationGroup02 on SR-SRV06.
Replication is now reversed.
You must direct any applications or users attempting to read or write against SR-SRV05 to SR-SRV06.

### Example 2: Change size of log
```
PS C:\>Set-SRPartnership -SourceComputerName "SR-SRV05" -SourceRGName "ReplicationGroup01" -DestinationComputerName "SR-SRV06" -DestinationRGName "ReplicationGroup02" -LogSizeInBytes 32GB
PS C:\> Get-SRPartnership | Get-SRGroup
AllowVolumeResize  : False
AsyncRPO           : 30
ComputerName       : SR-SRV05
Description        : 
Id                 : 74f2254c-a910-4780-98b4-ea4ea049e69b
IsAutoFailover     : 
IsCluster          : False
IsEncrypted        : False
IsInPartnership    : True
IsPrimary          : True
IsSuspended        : False
IsWriteConsistency : False
LastInSyncTime     : 
LogSizeInBytes     : 34359738368
LogVolume          : e:\ 
Name               : ReplicationGroup01
NumOfReplicas      : 1
Partitions         : {bc49f059-4f78-464d-b88a-3a092108816e}
Replicas           : {MSFT_WvrReplica (PartitionId =
                     "bc49f059-4f78-464d-b88a-3a092108816e")}
ReplicationMode    : Asynchronous
ReplicationStatus  : ContinuouslyReplicating_InRPO
PSComputerName     : 

AllowVolumeResize  : False
AsyncRPO           : 30
ComputerName       : SR-SRV06
Description        : 
Id                 : 291cb733-b753-469d-8092-5b54d4a6752d
IsAutoFailover     : 
IsCluster          : False
IsEncrypted        : False
IsInPartnership    : True
IsPrimary          : False
IsSuspended        : False
IsWriteConsistency : False
LastInSyncTime     : 10/11/2016 1:48:04 PM
LogSizeInBytes     : 34359738368
LogVolume          : e:\ 
Name               : ReplicationGroup02
NumOfReplicas      : 1
Partitions         : {92306c9f-655c-48e2-a28f-f08010514161}
Replicas           : {MSFT_WvrReplica (PartitionId =
                     "92306c9f-655c-48e2-a28f-f08010514161")}
ReplicationMode    : Asynchronous
ReplicationStatus  : ContinuouslyReplicating
PSComputerName     :
```

This command changes the log from its default size of 8GB to 32GB, on the partnership between SR-SRV05 and SR-SRV06.

### Example 3: Change to asynchronous mode
```
PS C:\>Set-SRPartnership -SourceComputerName "SR-SRV05" -SourceRGName "ReplicationGroup01" -ReplicationMode Asynchronous -DestinationComputerName "SR-SRV06" -DestinationRGName "ReplicationGroup02"
WARNING: The replication group ReplicationGroup01 is the source. Modifying replication mode on source
replication group will not affect the current replication partnership.
```

This command changes the replication mode from synchronous to asynchronous.
The warning is generated by the setting being applied to both replication groups.

### Example 4: Display replicas after a change
```
PS C:\>Set-SRPartnership -SourceComputerName "SR-SRV05" -SourceRGName "ReplicationGroup01" -SourceAddVolumePartnership "F:","G:" -DestinationComputerName "SR-SRV06" -DestinationRGName "ReplicationGroup02" -DestinationAddVolumePartnership "F:","G:"
PS C:\> (Get-SRGroup).replicas 
CurrentLsn          : 1
DataVolume          : D:\ 
LastInSyncTime      : 
LastKnownPrimaryLsn : 1
LastOutOfSyncTime   : 
NumOfBytesRecovered : 0
NumOfBytesRemaining : 0
PartitionId         : bc49f059-4f78-464d-b88a-3a092108816e
PartitionSize       : 34730934272
ReplicationMode     : Synchronous
ReplicationStatus   : ContinuouslyReplicating
PSComputerName      : 

CurrentLsn          : 1
DataVolume          : F:\ 
LastInSyncTime      : 
LastKnownPrimaryLsn : 1
LastOutOfSyncTime   : 
NumOfBytesRecovered : 0
NumOfBytesRemaining : 0
PartitionId         : 51c97fb1-b280-452c-96b7-442f400889da
PartitionSize       : 13759414272
ReplicationMode     : Synchronous
ReplicationStatus   : InitialBlockCopy
PSComputerName      : 

CurrentLsn          : 1
DataVolume          : G:\ 
LastInSyncTime      : 
LastKnownPrimaryLsn : 1
LastOutOfSyncTime   : 
NumOfBytesRecovered : 0
NumOfBytesRemaining : 0
PartitionId         : 97a3d483-8766-49a9-be54-5f1e52aaba51
PartitionSize       : 20091764736
ReplicationMode     : Synchronous
ReplicationStatus   : InitialBlockCopy
PSComputerName      :
```

The first command changes the partnership for the servers named SR-SRV05 and SR-SRV06.

The second command gets all replication groups for the current computer by using the Get-SRGroup cmdlet.
The command displays all the replicas by using standard Windows PowerShell syntax.

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

### -AsyncRPO
Specifies the maximum difference in time that data for an asynchronous partnership can be different between source and destination.
This is a Recovery Point Objective.
The default value is 30 seconds.

After this time is exceeded, the source server alerts the Health Service on clusters.
It logs event 1239 in the Storage Replica Admin event log channel.
If the RPO time is lower than the configured time, event 1240 is logged.
Changing this value modifies monitoring and logging.
It does not affect replication or Input/Output.

```yaml
Type: UInt32
Parameter Sets: ModifySettings
Aliases: RPO

Required: False
Position: 51
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

### -DestinationAddVolumePartnership
Specifies an array of drive letters or mount point paths of partitions to add to the existing replication group.
You cannot specify paths already added to the replication group.

This list is ordered.
The order of volumes determines the order of replication.
For more information, see the *DestinationVolumeName* parameter of the New-SRPartnership cmdlet.

We do not recommend replicating different drive letters or mount point paths.
The practice can cause application failures because of stored settings after a failover occurs.

```yaml
Type: String[]
Parameter Sets: AddVolumes
Aliases: DAV

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationComputerName
Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of the destination computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DCN

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationRGName
Specifies the name of the destination replication group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DGN

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Encryption
Indicates that the connections on this partnership should be encrypted by using SMB AES-128-GCM.
Enabling encryption can protect Storage Replica block transfers from man-in-the-middle interception or reading.
Enabling encryption can decrease replication and write Input/Output performance.

```yaml
Type: Boolean
Parameter Sets: ModifySettings
Aliases: ENC

Required: False
Position: 52
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: AddVolumes, ModifyPartnership
Aliases: F

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogSizeInBytes
Specifies the aggregate size of log files on each server in the replication group for the volumes that are associated with this replication group.
The minimum size 512MB.
You can specify a value by using the Windows PowerShell byte conversion capability, such as 4GB or 3200MB.
A value that is too small may cause decreased replication performance or increased recovery time after an interruption between computers.

```yaml
Type: UInt64
Parameter Sets: ModifySettings
Aliases: LS

Required: False
Position: 50
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewSourceComputerName
Specifies the new source of replication.
This parameter changes the direction of replication for the source computer and the source replication group.
When changed, replication stops originating on the current source and moves to the new source.

This operation is very likely to disrupt access to data.
There is a time when neither volumes are writable and when clients and applications might still access the previously writable source volume.
You may also have to reconfigure applications and repoint users to this new location, using technologies such as DFS Namespaces.
When switching asynchronously-replicated volumes, to avoid data loss, you must first make sure that user and application data is quiescent.

```yaml
Type: String
Parameter Sets: ModifyPartnership
Aliases: NSCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicationMode
Specifies the desired mode of replication for this source and destination pair.
The acceptable values for this parameter are:

- Synchronous or 1.
The synchronous mode requires all writes to commit on the destination server and commit on the source server, which guarantees data integrity between computers. 
- Asynchronous or 2. 
The asynchronous mode writes to the source server without waiting for the server, which allows for replication over high latency, geographic networks. 

The default value is synchronous. 
The default asynchronous recovery point alert time is 30 seconds.
You can modify it by using this cmdlet.
The alert time has no effect on replication behavior, only on reporting.

```yaml
Type: ReplicationMode
Parameter Sets: ModifySettings
Aliases: RM
Accepted values: Synchronous, Asynchronous

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Seeded
Indicates that the destination server contains a seeded copy of the data from the source server.
Seeded data is defined as a copy of data from the source server that has a high similarity, such as mostly empty blocks, restoring a recent backup, or shipping cloned copies of disks to the destination server.

Seeding is most effective when using a previous copy of the storage, such as a split mirror or previously replicated drives, or when the storage is mostly empty and was always empty, such as a recently initialized drive with a newly formatted volume.
Seeding is somewhat effective with data that came from a backup restore or a complete tree copy of data or from copies of very large files.

Seeding is least effective when copying many small files from some random locations to some other random locations.
Storage Replica automatically uses seeding when it restarts replication after a long outage that wrapped the logs.

```yaml
Type: SwitchParameter
Parameter Sets: AddVolumes
Aliases: S

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceAddVolumePartnership
Specifies an array of drive letters or mount point paths of partitions to add to the existing replication group.
You cannot specify paths already added to the replication group.

This is an ordered list.
The order of volumes determines the order of replication.
For more information, see the *DestinationVolumeName* parameter of the New-SRPartnership cmdlet.

```yaml
Type: String[]
Parameter Sets: AddVolumes
Aliases: SAV

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceComputerName
Specifies a single replica host computer NetBIOS name or FQDN of the source computer.
The default value is the local computer.

```yaml
Type: String
Parameter Sets: AddVolumes
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ModifySettings
Aliases: SCN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SRGroup](./Get-SRGroup.md)

[Get-SRPartnership](./Get-SRPartnership.md)

[New-SRPartnership](./New-SRPartnership.md)

[Remove-SRPartnership](./Remove-SRPartnership.md)

