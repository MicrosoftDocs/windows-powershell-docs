---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://docs.microsoft.com/powershell/module/failoverclusters/remove-clustervmmonitoreditem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-ClusterVMMonitoredItem

## SYNOPSIS
Removes monitoring of a service or event that is currently being monitored on a virtual machine.

## SYNTAX

```
Remove-ClusterVMMonitoredItem [[-VirtualMachine] <String>] [-Cluster <String>] [-EventId <Int32>]
 [-EventLog <String>] [-EventSource <String>] [-InputObject <PSObject>] [-Service <StringCollection>]
```

## DESCRIPTION
The **Remove-ClusterVMMonitoredItem** cmdlet removes monitoring of a service or event that is currently being monitored.
After removal, if the service fails or the event occurs, the system will no longer take an action, such as restarting the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Get-ClusterVMMonitoredItem -VirtualMachine VM1 | Remove-ClusterVMMonitoredItem -VirtualMachine VM1
```

This example removes all of the items being monitored on the virtual machine named VM1.

### Example 2
```
PS C:\>Remove-ClusterVMMonitoredItem -VirtualMachine VM1 -Service spooler
https://go.microsoft.com/fwlink/?LinkId=216240
```

This example removes monitoring on the print spooler service on the virtual machine named VM1.

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
Specifies the event identifier (ID) of the Event Tracing for Windows (ETW) event to be removed from monitoring.

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
Specifies the cluster on which to run the cmdlet, the clustered virtual machine from which to remove monitoring, or the clustered virtual machine monitored item object to stop monitoring.

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

### -VirtualMachine
Specifies the name of the clustered virtual machine from which to remove monitoring.
When this parameter is specified, this cmdlet must be run on one of the host cluster nodes, or else the **Cluster** parameter must also be specified.

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

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)

