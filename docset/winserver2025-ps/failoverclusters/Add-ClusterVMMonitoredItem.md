---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clustervmmonitoreditem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterVMMonitoredItem
---

# Add-ClusterVMMonitoredItem

## SYNOPSIS
Configures monitoring for a service or an Event Tracing for Windows (ETW) event so that it is
monitored on a virtual machine.

## SYNTAX

### VirtualMachine (Default)

```
Add-ClusterVMMonitoredItem [-Service <StringCollection>] [-EventLog <String>]
 [-EventSource <String>] [-EventId <Int32>] [-OverrideServiceRecoveryActions]
 [[-VirtualMachine] <String>] [-Wait <Int32>] [-Cluster <String>] [<CommonParameters>]
```

### VMId

```
Add-ClusterVMMonitoredItem [-Service <StringCollection>] [-EventLog <String>]
 [-EventSource <String>] [-EventId <Int32>] [-OverrideServiceRecoveryActions] [-VMId <Guid>]
 [-Wait <Int32>] [-Cluster <String>] [<CommonParameters>]
```

### InputObject

```
Add-ClusterVMMonitoredItem [-Service <StringCollection>] [-EventLog <String>]
 [-EventSource <String>] [-EventId <Int32>] [-OverrideServiceRecoveryActions] [-Wait <Int32>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ClusterVMMonitoredItem` cmdlet configures monitoring for a service or an Event Tracing
for Windows (ETW) event so that it is monitored on a virtual machine. If the service fails or the
event occurs, then the system responds by taking an action based on the failover configuration for
the virtual machine resource. For example, the configuration might specify that the virtual machine
be restarted.

## EXAMPLES

### Example 1

```powershell
$parameters = @{
    VirtualMachine = 'test-VM11'
    EventLog = 'Microsoft-Windows-FailoverClustering-Manager/Admin'
    EventSource = 'Microsoft-Windows-FailoverClustering-Manager'
    EventId = '4708'
}
Add-ClusterVMMonitoredItem @parameters
```

This example adds monitoring for the ETW event ID `4708`. This example uses splatting to pass
parameter values from the `$Parameters` variable to the command. Learn more about
[Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

### Example 2

```powershell
Add-ClusterVMMonitoredItem -VirtualMachine test-VM11 -Service spooler
```

This example configures monitoring for the print spooler service.

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

Specifies the event identifier (ID) of the event to be monitored.

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

Specifies the event log of the event to be monitored.

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

Specifies the event source of the event to be monitored.

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

Specifies the cluster on which to run the cmdlet, the clustered virtual machine on which to
configure monitoring, and the cluster virtual machine monitored item object to monitor.

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

### -OverrideServiceRecoveryActions

Specifies that the cluster service will fix, by overriding, the service recovery actions in the
event that it isn't properly configured for monitoring. To be configured for monitoring the
following conditions need to be met:

- None of the service recovery actions are set to Restart the computer.

AND

- At least one of the service recovery actions are set to Take no action.

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

### -Service

Specifies the name of a service to be monitored. This must be the short name, not the long name, of
the service. For example, specify clussvc instead of Failover Cluster service.

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
then the cmdlet waits for completion. If the value `0` is specified, then the call is initiated and
the cmdlet returns without waiting.

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

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)

[Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)
