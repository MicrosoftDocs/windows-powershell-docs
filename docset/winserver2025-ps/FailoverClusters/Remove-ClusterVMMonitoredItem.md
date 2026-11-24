---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clustervmmonitoreditem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterVMMonitoredItem
---

# Remove-ClusterVMMonitoredItem

## SYNOPSIS
## SYNTAX

### VirtualMachine (Default)

```
Remove-ClusterVMMonitoredItem [-InputObject <PSObject>] [-Service <StringCollection>]
 [-EventLog <String>] [-EventSource <String>] [-EventId <Int32>] [[-VirtualMachine] <String>]
 [-Wait <Int32>] [-Cluster <String>] [<CommonParameters>]
```

### VMId

```
Remove-ClusterVMMonitoredItem [-InputObject <PSObject>] [-Service <StringCollection>]
 [-EventLog <String>] [-EventSource <String>] [-EventId <Int32>] [-VMId <Guid>] [-Wait <Int32>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-ClusterVMMonitoredItem` cmdlet removes monitoring of a service or event that is
currently being monitored. After removal, if the service fails or the event occurs, the system will
no longer take an action, such as restarting the virtual machine.

## EXAMPLES

### Example 1

```powershell
Get-ClusterVMMonitoredItem -VirtualMachine VM1 | Remove-ClusterVMMonitoredItem -VirtualMachine VM1
```

This example removes all of the items being monitored on the virtual machine named `VM1`.

### Example 2

```powershell
Remove-ClusterVMMonitoredItem -VirtualMachine VM1 -Service spooler
```

This example removes monitoring on the print spooler service on the virtual machine named `VM1`.

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

### -EventId

Specifies the event identifier (ID) of the Event Tracing for Windows (ETW) event to be removed from
monitoring.

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

### -EventLog

Specifies the event log of the event to be removed from monitoring.

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

### -EventSource

Specifies the event source of the event to be removed from monitoring.

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

Specifies the cluster on which to run the cmdlet, the clustered virtual machine from which to remove
monitoring, or the clustered virtual machine monitored item to stop monitoring.

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

### -Service

Specifies the name of the service to be removed from monitoring.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

Specifies the name of the clustered virtual machine from which to remove monitoring. When this
parameter is specified, this cmdlet must be run on one of the host cluster nodes, or else the
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

### Microsoft.FailoverClusters.PowerShell.ClusterVMMonitoredItem

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)
