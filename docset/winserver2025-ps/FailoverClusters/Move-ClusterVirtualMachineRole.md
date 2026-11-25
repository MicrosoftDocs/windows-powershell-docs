---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 01/10/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/move-clustervirtualmachinerole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ClusterVirtualMachineRole
---

# Move-ClusterVirtualMachineRole

## SYNOPSIS
Moves the ownership of a clustered virtual machine to a different node.

## SYNTAX

```
Move-ClusterVirtualMachineRole [[-Name] <String>] [[-Node] <String>] [-Cancel]
 [-MigrationType <VmMigrationType>] [-IgnoreLocked] [-VMId <Guid>] [-Wait <Int32>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Move-ClusterVirtualMachineRole` cmdlet moves the ownership of a clustered virtual machine to
a different node.

This cmdlet is used to live migrate a clustered virtual machine. For quick migration, use
`Move-ClusterGroup` after using `Get-ClusterResource` and `Set-ClusterParameter` to set the
**OfflineAction** parameter of the virtual machine resource to save state, or a value of 1.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP)
authentication on the server computer.

## EXAMPLES

### Example 1

```powershell
Move-ClusterVirtualMachineRole -Name "Virtual Machine1" -Node node2
```

This example performs a live migration of the clustered virtual machine named Virtual Machine1 to
the node named `node2`. The Windows PowerShell prompt doesn't return until the action is complete.

### Example 2

```powershell
Get-ClusterGroup -Name "Virtual Machine1" | Move-ClusterVirtualMachineRole -Node node2 -Wait 0
```

This example performs a live migration of clustered virtual machine named `Virtual Machine1` to the
node named `node2`. The Windows PowerShell prompt returns as soon as the action has been initiated.

### Example 3

```powershell
Move-ClusterVirtualMachineRole -Name "Virtual Machine1" -Cancel
```

This example cancels the live migration in progress for the clustered virtual machine named `Virtual
Machine1`.

### Example 4

```powershell
$vmGroups = Get-ClusterNode -Name node1 |
    Get-ClusterGroup |
    Where-Object -FilterScript {
        Get-ClusterResource -InputObject $_ |
            Where-Object ResourceType -Like "Virtual Machine"
    }
ForEach-Object -InputObject $vmGroups -Process { $_ | Move-ClusterVirtualMachineRole -Node node2 }
```

This example queries a specific cluster node, `node1`, to find the currently owned groups. The
example further filters the owned groups where there resource type is a virtual machine cluster
resource. The filtered groups are stored in the `$vmGroups` variable. For each cluster group in the
variable, the command will perform a live migration of all clustered virtual machines to the node
named `node2`. The migration of each virtual machine will complete before the next migration is
started.

## PARAMETERS

### -Cancel

Specifies that an in-progress live migration of the virtual machine be canceled.

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

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreLocked

Specifies that locked groups are ignored when running the cmdlet.

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

### -InputObject

Specifies the clustered virtual machine to move.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MigrationType

Specifies the type of migration to perform for the virtual machine. The options are as follows:

- `Live`: Transparently migrates the virtual machine without a dropped network connection or
  perceived downtime.

- `Quick`: Rapidly migrates a running virtual machine with minimal downtime.

- `Shutdown`: Performs an orderly shutdown of the operating system (waiting for all processes to
  close) on the virtual machine, and then migrates the virtual machine.

- `ShutdownForce`: Shuts down the operating system on the virtual machine without waiting for slower
  processes to finish, and then migrates the virtual machine.

- `TurnOff`: Turns off the virtual machine without shutting down the operating system first, then
  migrates the virtual machine. This is the same as turning off the power, which means that data
  loss may occur.

```yaml
Type: VmMigrationType
Parameter Sets: (All)
Aliases:
Accepted values: TurnOff, Quick, Shutdown, ShutdownForce, Live

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the clustered virtual machine to move.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node

Specifies the name of the cluster node to which to move the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMId

Specifies the virtual machine identifier (ID).

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If `-Wait 0` is specified, then the call is initiated and the
cmdlet returns without waiting.

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
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterVirtualMachineRole](./Add-ClusterVirtualMachineRole.md)

[Update-ClusterVirtualMachineConfiguration](./Update-ClusterVirtualMachineConfiguration.md)
