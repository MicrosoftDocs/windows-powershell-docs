---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/networkloadbalancingclusters/remove-nlbcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NlbCluster
---

# Remove-NlbCluster

## SYNOPSIS
Removes a NLB cluster.

## SYNTAX

### NonPipeline (Default)
```
Remove-NlbCluster [-PassThru] [[-HostName] <String>] [[-InterfaceName] <String>] [-Force] [<CommonParameters>]
```

### Pipeline
```
Remove-NlbCluster -InputObject <Cluster[]> [-PassThru] [[-HostName] <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NlbCluster** cmdlet removes a Network Load Balancing (NLB) cluster.
When the cluster is removed, all existing connections to the hosts in the cluster are lost and the cluster will no longer exist.

## EXAMPLES

### Example 1: Remove an NLB cluster with confirmation
```
PS C:\>Remove-NlbCluster
```

This command removes the NLB cluster after asking for user confirmation.

### Example 2: Remove an NLB cluster without confirmation
```
PS C:\>Remove-NlbCluster -Force
```

This command removes the NLB cluster.
Because the *Force* parameter is used, the cmdlet does not ask for user confirmation.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the name of the cluster host against which this cmdlet is run.
If this parameter is omitted or a value of `.` is entered, then the local cluster is assumed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Host, HN, H

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies an array of clusters that this cmdlet removes.

```yaml
Type: Cluster[]
Parameter Sets: Pipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InterfaceName
Specifies the interface to which NLB is bound.
This is the interface of the cluster against which this cmdlet is run.

```yaml
Type: String
Parameter Sets: NonPipeline
Aliases: Interface, IN, I

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Passthru By default, this cmdlet does not generate any output.

To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are also supported.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Pass

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## OUTPUTS

### None or Microsoft.NetworkLoadBalancingClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-NlbCluster](./Get-NlbCluster.md)

[New-NlbCluster](./New-NlbCluster.md)

[Resume-NlbCluster](./Resume-NlbCluster.md)

[Set-NlbCluster](./Set-NlbCluster.md)

[Start-NlbCluster](./Start-NlbCluster.md)

[Stop-NlbCluster](./Stop-NlbCluster.md)

[Suspend-NlbCluster](./Suspend-NlbCluster.md)

