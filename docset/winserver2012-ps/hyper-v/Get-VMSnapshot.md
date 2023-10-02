---
external help file: Hyper-V_Cmdlets.xml
Module Name: Hyper-V
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmsnapshot?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-VMSnapshot

## SYNOPSIS
Gets the snapshots associated with a virtual machine or snapshot.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-VMSnapshot [[-Name] <String>] [-SnapshotType <SnapshotType>] -ChildOf <VMSnapshot>
```

### UNNAMED_PARAMETER_SET_2
```
Get-VMSnapshot [-Id] <Guid> [-ComputerName <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-VMSnapshot [-VMName] <String[]> [[-Name] <String>] [-ComputerName <String[]>]
 [-SnapshotType <SnapshotType>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-VMSnapshot [[-Name] <String>] [-SnapshotType <SnapshotType>] -ParentOf <VirtualMachineBase>
```

### UNNAMED_PARAMETER_SET_5
```
Get-VMSnapshot [-VM] <VirtualMachine[]> [[-Name] <String>] [-SnapshotType <SnapshotType>]
```

## DESCRIPTION
The **Get-VMSnapshot** cmdlet gets the snapshots associated with a virtual machine or snapshot.

## EXAMPLES

### Example 1
```
PS C:\>Get-VMSnapshot -VMName TestVM
```

Gets all snapshots of virtual machine TestVM.

### Example 2
```
PS C:\>Get-VM -Name TestVM | Get-VMSnapshot -SnapshotType Standard
```

Gets all standard snapshots of virtual machine TestVM.

### Example 3
```
PS C:\>$snapshot = Get-VMSnapshot -Name 'Before applying updates' -VMName TestVM


PS C:\>Get-VMSnapshot -ParentOf $snapshot
```

Gets the immediate parent of snapshot Before applying updates of virtual machine TestVM.

### Example 4
```
PS C:\>$snapshot = Get-VMSnapshot -Name 'Before applying updates' -VMName TestVM


PS C:\>Get-VMSnapshot -ChildOf $snapshot
```

Gets the immediate child snapshots of snapshot Before applying updates of virtual machine TestVM.

## PARAMETERS

### -ChildOf
Specifies the snapshot whose child snapshots are to be retrieved.
This retrieves immediate children only.

```yaml
Type: VMSnapshot
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which snapshots are to be retrieved.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique identifier of the virtual machine whose snapshots are to be retrieved.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the snapshot to be retrieved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentOf
Specifies the snapshot whose immediate parent snapshot is to be retrieved.

```yaml
Type: VirtualMachineBase
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotType
Specifies the type of the snapshots to be retrieved.
Allowed values are **Standard**, **Recovery**, **Planned**, **Missing**, **Replica**, **AppConsistentReplica**, and **SyncedReplica**.

```yaml
Type: SnapshotType
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine whose snapshots are to be retrieved.

```yaml
Type: VirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies the name of the virtual machine whose snapshots are to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Virtualization.Powershell.Snapshot

## NOTES

## RELATED LINKS



