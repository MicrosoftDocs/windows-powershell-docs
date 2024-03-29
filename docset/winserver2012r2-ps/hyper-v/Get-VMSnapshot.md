---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmsnapshot?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMSnapshot
---

# Get-VMSnapshot

## SYNOPSIS
Gets the checkpoints associated with a virtual machine or checkpoint.

## SYNTAX

### VMName (Default)
```
Get-VMSnapshot [-ComputerName <String[]>] [-VMName] <String[]> [[-Name] <String>]
 [-SnapshotType <SnapshotType>] [<CommonParameters>]
```

### Id
```
Get-VMSnapshot [-ComputerName <String[]>] [-Id] <Guid> [<CommonParameters>]
```

### VMObject
```
Get-VMSnapshot [-VM] <VirtualMachine[]> [[-Name] <String>] [-SnapshotType <SnapshotType>] [<CommonParameters>]
```

### Child
```
Get-VMSnapshot [[-Name] <String>] -ChildOf <VMSnapshot> [-SnapshotType <SnapshotType>] [<CommonParameters>]
```

### Parent
```
Get-VMSnapshot [[-Name] <String>] -ParentOf <VirtualMachineBase> [-SnapshotType <SnapshotType>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSnapshot** cmdlet gets the checkpoints associated with a virtual machine or checkpoint.

Note: In Windows Server 2012 R2, virtual machine snapshots were renamed to virtual machine checkpoints.
For clarity, this document will refer to virtual machine snapshots as checkpoints.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSnapshot -VMName TestVM
```

Gets all checkpoints of virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM | Get-VMSnapshot -SnapshotType Standard
```

Gets all standard checkpoints of virtual machine TestVM.

### Example 3
```
PS C:\>$snapshot = Get-VMSnapshot -Name 'Before applying updates' -VMName TestVM


PS C:\>Get-VMSnapshot -ParentOf $snapshot
```

Gets the immediate parent of checkpoint Before applying updates of virtual machine TestVM.

### Example 4
```
PS C:\>$snapshot = Get-VMSnapshot -Name 'Before applying updates' -VMName TestVM


PS C:\>Get-VMSnapshot -ChildOf $snapshot
```

Gets the immediate child checkpoints of checkpoint Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ChildOf
Specifies the checkpoint whose child checkpoints are to be retrieved.
This retrieves immediate children only.

```yaml
Type: VMSnapshot
Parameter Sets: Child
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which checkpoints are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: VMName, Id
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique identifier of the virtual machine whose checkpoints are to be retrieved.

```yaml
Type: Guid
Parameter Sets: Id
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the checkpoint to be retrieved.

```yaml
Type: String
Parameter Sets: VMName, VMObject, Child, Parent
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentOf
Specifies the checkpoint whose immediate parent checkpoint is to be retrieved.

```yaml
Type: VirtualMachineBase
Parameter Sets: Parent
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotType
Specifies the type of the checkpoints to be retrieved.
Allowed values are **Standard**, **Recovery**, **Planned**, **Missing**, **Replica**, **AppConsistentReplica**, and **SyncedReplica**.

```yaml
Type: SnapshotType
Parameter Sets: VMName, VMObject, Child, Parent
Aliases: 
Accepted values: Standard, Recovery, Planned, Missing, Replica, AppConsistentReplica, SyncedReplica

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose checkpoints are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose checkpoints are to be retrieved.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.Snapshot

## NOTES

## RELATED LINKS

