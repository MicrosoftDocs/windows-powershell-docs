---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clustervmmonitoreditem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusterVMMonitoredItem

## SYNOPSIS
Configures monitoring for a service or an Event Tracing for Windows (ETW) event so that it is monitored on a virtual machine.

## SYNTAX

```
Add-ClusterVMMonitoredItem [[-VirtualMachine] <String>] [-Cluster <String>] [-EventId <Int32>]
 [-EventLog <String>] [-EventSource <String>] [-InputObject <PSObject>] [-OverrideServiceRecoveryActions]
 [-Service <StringCollection>]
```

## DESCRIPTION
The **Add-ClusterVMMonitoredItem** cmdlet configures monitoring for a service or an Event Tracing for Windows (ETW) event so that it is monitored on a virtual machine.
If the service fails or the event occurs, then the system responds by taking an action based on the failover configuration for the virtual machine resource.
For example, the configuration might specify that the virtual machine be restarted.

## EXAMPLES

### Example 1
```
PS C:\>Add-ClusterVMMonitoredItem -VirtualMachine test-VM11 -EventLog "Microsoft-Windows-FailoverClustering-Manager/Admin" -EventSource "Microsoft-Windows-FailoverClustering-Manager" -EventId 4708
Name 
---- 
Microsoft-Windows-FailoverClustering-Manager+Admin,Microsoft-Windows-FailoverClustering-Manager,4708
```

This example adds monitoring for the ETW event ID 4708.

### Example 2
```
PS C:\>Add-ClusterVMMonitoredItem -VirtualMachine test-VM11 -Service spooler
Name 
---- 
Spooler
```

This example configures monitoring for the print spooler service.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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
Specifies the cluster on which to run the cmdlet, the clustered virtual machine on which to configure monitoring, and the cluster virtual machine monitored item object to monitor.

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

### -OverrideServiceRecoveryActions
Specifies that the cluster service will fix, by overriding, the service recovery actions in the event that it is not properly configured for monitoring.
To be configured for monitoring the following conditions need to be met: 

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
Specifies the name of a service to be monitored.
This must be the short name, not the long name, of the service.
For example, specify clussvc instead of Failover Cluster service.

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

### -VirtualMachine
Specifies the name of the clustered virtual machine on which to perform monitoring.
When this parameter is specified, the cmdlet must be run on one of the host cluster nodes, or else the **Cluster** parameter must also be specified.

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

