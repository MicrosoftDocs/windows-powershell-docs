---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustervmmonitoreditem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterVMMonitoredItem
---

# Get-ClusterVMMonitoredItem

## SYNOPSIS
Gets the list of services and events currently being monitored in the virtual machine.

## SYNTAX

### VirtualMachine (Default)

```
Get-ClusterVMMonitoredItem [[-VirtualMachine] <String>] [-Wait <Int32>] [-Cluster <String>]
 [<CommonParameters>]
```

### VMId

```
Get-ClusterVMMonitoredItem [-VMId <Guid>] [-Wait <Int32>] [-Cluster <String>] [<CommonParameters>]
```

### InputObject

```
Get-ClusterVMMonitoredItem [-Wait <Int32>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterVMMonitoredItem` cmdlet gets the list of services and events currently being
monitored in the virtual machine. If one of those services fails or one of the events occurs, then
the system responds by taking an action based on the failover configuration for the virtual machine
resource. For example, the configuration might specify that the virtual machine be restarted.

## EXAMPLES

### Example 1

```powershell
Get-Cluster -Name Cluster1 | Get-ClusterVMMonitoredItem -VirtualMachine vm1
```

This example returns the services and events being monitored in the virtual machine named `vm1` on
the cluster named `Cluster1`.

## PARAMETERS

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

### -InputObject

Specifies the cluster on which to run the cmdlet or the clustered virtual machine for which to
retrieve the clustered virtual machine monitored item object.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMId

Specifies the virtual machine identifier (ID).

```yaml
Type: Guid
Parameter Sets: VMId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachine

Specifies the name of the clustered virtual machine on which to perform monitoring. When this
parameter is specified, the cmdlet must be run on one of the host cluster nodes, or else the
**Cluster** parameter must also be specified.

```yaml
Type: String
Parameter Sets: VirtualMachine
Aliases: VM

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterVMMonitoredItem

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)

[Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)
