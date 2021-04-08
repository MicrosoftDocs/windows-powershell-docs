---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/stop-cluster?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Stop-Cluster

## SYNOPSIS
Stops the Cluster service on all nodes in a failover cluster, which will stop all services and applications configured in the cluster.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-Cluster [-Cluster <String>] [-Force] [-InputObject <PSObject>]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-Cluster [[-Name] <String>] [-Cluster <String>] [-Force]
```

## DESCRIPTION
The **Stop-Cluster** cmdlet stops the Cluster service on all nodes in a failover cluster, which will stop all services and applications configured in the cluster.
A node can only function as part of the cluster when the Cluster service is running on that node.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Stop-Cluster
```

This example stops the Cluster service on all nodes in the local cluster, which will stop all services and applications configured in the cluster.

### EXAMPLE 2
```
PS C:\>Stop-Cluster cluster1
```

This example stops the Cluster service on all nodes in the cluster named cluster1, which will stop all services and applications configured in the cluster.

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

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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
Specifies the cluster to stop.

```yaml
Type: PSObject
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the cluster to stop.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Test-Cluster](./Test-Cluster.md)

