---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clustervmmonitoreditem?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterVMMonitoredItem

## SYNOPSIS
Gets the list of services and events currently being monitored in the virtual machine.

## SYNTAX

```
Get-ClusterVMMonitoredItem [[-VirtualMachine] <String>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterVMMonitoredItem** cmdlet gets the list of services and events currently being monitored in the virtual machine.
If one of those services fails or one of the events occurs, then the system responds by taking an action based on the failover configuration for the virtual machine resource.
For example, the configuration might specify that the virtual machine be restarted.

## EXAMPLES

### Example 1
```
PS C:\>Get-Cluster -Name Cluster1 | Get-ClusterVMMonitoredItem -VirtualMachine vm1
Name 
---- 
Microsoft-Windows-FailoverClustering-Manager+Admin,Microsoft-Windows-FailoverClustering-Manager,4708 
Spooler
```

This example returns the services and events being monitored in the virtual machine named vm1 on the cluster named Cluster1.

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
Default value: Local Cluster
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster on which to run the cmdlet or the clustered virtual machine for which to retrieve the clustered virtual machine monitored item object.

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

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterVMMonitoredItem

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)

[Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)

