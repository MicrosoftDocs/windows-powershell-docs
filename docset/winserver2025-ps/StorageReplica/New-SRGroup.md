---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WvrAdminTasks.cdxml-help.xml
Module Name: StorageReplica
ms.date: 10/04/2022
online version: https://learn.microsoft.com/powershell/module/storagereplica/new-srgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SRGroup
---

# New-SRGroup

## SYNOPSIS
Creates a replication group.

## SYNTAX

```
New-SRGroup [[-ComputerName] <String>] [-Name] <String> [-VolumeName] <String[]>
 [-LogVolumeName] <String> [[-LogSizeInBytes] <UInt64>] [[-Description] <String>]
 [-EnableConsistencyGroups] [-EnableEncryption] [-EnableCompression] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `New-SRGroup` cmdlet creates a replication group. A replication group contains one or more
data volumes and an associated log volume. A replication group is the container for replication.

## EXAMPLES

### Example 1: Create a replication group

```powershell
New-SRGroup -ComputerName "SR-SRV05" -Name "ReplicationGroup01" -VolumeName "D:" -LogVolumeName "E:"
```

This command creates a replication group for server named `SR-SRV05`. The command specifies the
replicated volume and the log volume. Because this command does not specify other parameters, the
replication group uses default values. Replication will not start until you run the
`New-SRPartnership` cmdlet.

### Example 2: Create a replication group that uses custom properties

```powershell
$Parameters = @{
    ComputerName = 'SR-SRV05'
    Name = 'ReplicationGroup02'
    VolumeName = 'D:'
    LogVolumeName = 'E:'
    LogSizeInBytes = '32GB'
    EnableEncryption = $True
}
New-SRGroup @Parameters
```

This command creates a replication group for server named `SR-SRV05`. The command specifies the
replicated volume and the log volume. The command also specifies a custom log size in GB and enables
replication traffic encryption. Replication will not start until you run `New-SRPartnership`.

This example uses splatting to pass parameter values from the `$Parameters` variable to the command.
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

### -ComputerName

Specifies a single replica host computer NetBIOS name or fully qualified domain name (FQDN) of a
computer to belong to the replication group. The default value is the local computer.

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
Parameter Sets: (All)
Aliases: D

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableCompression

Indicates that this Storage Replica group should use SMB compression for data transfer. SMB
compression is only used with TCP, and isn't supported on both SMB Direct and RDMA networks.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ECMP

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableConsistencyGroups

Indicates that consistency groups are enabled for the replication group that contains multiple
volumes. Consistency groups provide write ordering. This can be important, for example, for
replication of application data on multiple volumes.

If you enable consistency groups, it may decrease replication and write Input/Output performance.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: EC

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEncryption

Indicates that this partnership should encrypt connection by using SMB AES-128-GCM. Enabling
encryption can protect Storage Replica block transfers from man-in-the-middle interception or
reading. Enabling encryption decreases performance.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: EE

Required: False
Position: 7
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
using the Windows PowerShell byte conversion capability, such as 4GB or 3200MB.

A value that is too small may cause decreased replication performance or increased recovery time
after an interruption between computers.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: LS

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogVolumeName

Specifies a drive letter, mount point path, or volume GUID where Storage Replication creates
destination replication logs. The value must contain an NTFS-formatted volume or ReFS-formatted
volume. The path must exist. The path cannot be a mapped drive or UNC path.

Storage Replication creates logs in the System Volume Information folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LV

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies a name for the replication group.

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

### -VolumeName

Specifies an array of drive letters or mount point paths for the replica. The volumes must exist.
The volumes cannot be mapped drives or UNC paths.

This is an ordered list. The order of volumes determines the order of replication. For more
information, see the **DestinationVolumeName** parameter of the `New-SRPartnership` cmdlet.

We do not recommend replicating different drive letters or mount point paths. The practice can cause
application failures because of stored settings after a failover occurs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: VN

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[Get-SRGroup](Get-SRGroup.md)

[New-SRPartnership](New-SRPartnership.md)

[Remove-SRGroup](Remove-SRGroup.md)

[Set-SRGroup](Set-SRGroup.md)

[Suspend-SRGroup](Suspend-SRGroup.md)

[Sync-SRGroup](Sync-SRGroup.md)
