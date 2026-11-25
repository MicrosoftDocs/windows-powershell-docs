---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 10/04/2022
online version: https://learn.microsoft.com/powershell/module/storagereplica/set-srgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SRGroup
---

# Set-SRGroup

## SYNOPSIS
Modifies settings of a replication group.

## SYNTAX

### AddVolumes (Default)

```
Set-SRGroup [[-ComputerName] <String>] [-Name] <String> [-AddVolumeName] <String[]> [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RemoveVolumes

```
Set-SRGroup [[-ComputerName] <String>] [-Name] <String> [-Force] [-RemoveVolumeName] <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ModifyConfig

```
Set-SRGroup [[-ComputerName] <String>] [-Name] <String> [-Force] [[-LogSizeInBytes] <UInt64>]
 [[-Description] <String>] [[-ReplicationMode] <ReplicationMode>] [[-Encryption] <Boolean>]
 [[-Compression] <Boolean>] [[-AllowVolumeResize] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-SRGroup` cmdlet modifies settings of an existing replication group. A replication group
contains one or more data volumes and an associated log volume. A replication group is the
container for replication.

## EXAMPLES

### Example 1: Add a volume to a replication group

```powershell
Set-SRGroup -Name "ReplicationGroup01" -AddVolumeName "F:"
```

This command adds the `F:` volume to the existing replication group named `ReplicationGroup01` on
the local computer.

### Example 2: Remove a volume from a replication group

```powershell
Set-SRGroup -Name "ReplicationGroup01" -RemoveVolumeName "F:"
```

This command removes the `F:` volume from the existing replication group `ReplicationGroup01` on the
local computer.

### Example 3: Resize volumes in a replication group

```powershell
Set-SRGroup -Name "ReplicationGroup01" -AllowVolumeResize $True
```

This command lets you resize volumes in the replication group named `ReplicationGroup01` on the
local computer. By default, the Storage Replica driver prevents volume resizes in order to protect
from block mismatches. To grow a volume, enable the allow volume resize mode on both resource
groups, increase the size of the volume on both servers to be the same size, then disable this
mode.

## PARAMETERS

### -AddVolumeName

Specifies an array of drive letters or mount point paths of partitions for the replica to add to the
group. The volumes must exist. The volumes cannot be mapped drives or UNC paths.

This is an ordered list. The order of volumes determines the order of replication. For more
information, see the **DestinationVolumeName** parameter of the `New-SRPartnership` cmdlet.

```yaml
Type: String[]
Parameter Sets: AddVolumes
Aliases: AV

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllowVolumeResize

Indicates that the replication group enables resizing of volumes.

```yaml
Type: Boolean
Parameter Sets: ModifyConfig
Aliases: VR

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Compression

Indicates that this Storage Replica group should use SMB compression for data transfer.

```yaml
Type: Boolean
Parameter Sets: ModifyConfig
Aliases: CMP

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of a
computer. The default value is the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description

Specifies a description for the replication group.

```yaml
Type: String
Parameter Sets: ModifyConfig
Aliases: D

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encryption

Indicates this partnership should encrypt connections by using SMB AES-128-GCM. Enabling encryption
can protect Storage Replica block transfers from man-in-the-middle interception or reading. Enabling
encryption decreases performance.

```yaml
Type: Boolean
Parameter Sets: ModifyConfig
Aliases: ENC

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
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
using the Windows PowerShell byte conversion capability, such as 4GB or 3200MB.

A value that is too small may cause decreased replication performance or increased recovery time
after an interruption between computers.

```yaml
Type: UInt64
Parameter Sets: ModifyConfig
Aliases: LS

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the name of the replication group to modify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemoveVolumeName

Specifies an array of drive letters or mount point paths of partitions for the replica to remove
from the group. The volumes must exist. The volumes cannot be mapped drives or UNC paths.

This is an ordered list. The order of volumes determines the order of replication. For more
information, see the **DestinationVolumeName** parameter of the `New-SRPartnership` cmdlet.

If there is a partnership already configured, before you change this replication group, you must
remove the partnership by using the `Set-SRPartnership` cmdlet. Then you must remove the same
volumes from the previously partnered replication group.

```yaml
Type: String[]
Parameter Sets: RemoveVolumes
Aliases: RVN

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplicationMode

Specifies the desired mode of replication for this source and destination pair. The acceptable
values for this parameter are:

- Synchronous or 1. The synchronous mode requires all writes to commit on the destination server and
  commit on the source server, which guarantees data integrity between computers.
- Asynchronous or 2. The asynchronous mode writes to the source server without waiting for the
  source server, which allows for replication over high latency, geographic networks.

The default value is synchronous. The default asynchronous recovery point alert time is 5 minutes.
You can modify it by using the `Set-SRPartnership` cmdlet. The alert time has no effect on
replication behavior, only on reporting.

```yaml
Type: ReplicationMode
Parameter Sets: ModifyConfig
Aliases: RM
Accepted values: Synchronous, Asynchronous

Required: False
Position: 8
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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String

### System.UInt64

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SREnum.ReplicationMode

### System.Boolean

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-SRGroup](Get-SRGroup.md)

[New-SRGroup](New-SRGroup.md)

[Remove-SRGroup](Remove-SRGroup.md)

[Set-SRPartnership](Set-SRPartnership.md)

[Suspend-SRGroup](Suspend-SRGroup.md)

[Sync-SRGroup](Sync-SRGroup.md)
