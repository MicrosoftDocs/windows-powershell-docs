---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Remove-NlbClusterNodeDip
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: B5CB8186-4D53-43D6-8B47-4ECA99F7E550
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-NlbClusterNodeDip

## SYNOPSIS
Removes a dedicate IP address from a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Remove-NlbClusterNodeDip [-PassThru] [-Force] [-HostName <String>] [-InterfaceName <String>] [-IP] <IPAddress>
 [<CommonParameters>]
```

### Pipeline
```
Remove-NlbClusterNodeDip -InputObject <ClusterNodeDip[]> [-PassThru] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NlbClusterNodeDIP** cmdlet removes a dedicate IP address from a Network Load Balancing (NLB) cluster.
Once a dedicated IP address is removed, the node will not be accessible through this IP address.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NlbClusterNodeDip -IP fe80::9bf9:2019:372a:ca5
```

This example removes the dedicated IP address from the local cluster after seeking confirmation from the user.

### EXAMPLE 2
```
PS C:\>Remove-NlbClusterNodeDip -IP fe80::9bf9:2019:372a:ca5 -Force
```

This example removes the dedicated IP address from the local cluster without seeking confirmation from the user.

### EXAMPLE 3
```
PS C:\>Remove-NlbClusterNodeDip -IP fe80::8cb4:defa:65b2:8983 -HostName node2
```

This example removes the dedicated IP address from the remote host.

## PARAMETERS

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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
Parameter Sets: NonPipeline
Aliases: Host, HN, H

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IP
Specifies the IP address for the cluster node from which the dedicated IP address will be removed.

```yaml
Type: IPAddress
Parameter Sets: NonPipeline
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the cluster node dedicated IP address to remove.

```yaml
Type: ClusterNodeDip[]
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output. 
                         
To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: Pass

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterNodeDip

## NOTES

## RELATED LINKS

[Add-NlbClusterNodeDip](./Add-NlbClusterNodeDip.md)

[Get-NlbClusterNodeDip](./Get-NlbClusterNodeDip.md)

[Set-NlbClusterNodeDip](./Set-NlbClusterNodeDip.md)

