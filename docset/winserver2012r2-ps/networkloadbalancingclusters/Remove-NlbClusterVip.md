---
external help file: Microsoft.NetworkLoadBalancingClusters.PowerShell.dll-Help.xml
Module Name: NetworkLoadBalancingClusters
online version: 
schema: 2.0.0
title: Remove-NlbClusterVip
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: B2176720-D908-4C14-AB07-6D28F3590D53
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-NlbClusterVip

## SYNOPSIS
Removes a virtual IP address from a Network Load Balancing (NLB) cluster.

## SYNTAX

### NonPipeline (Default)
```
Remove-NlbClusterVip [-PassThru] [-Force] [-HostName <String>] [-InterfaceName <String>] [-IP] <IPAddress>
 [<CommonParameters>]
```

### Pipeline
```
Remove-NlbClusterVip -InputObject <ClusterVip[]> [-PassThru] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-NlbClusterVIP** cmdlet removes a virtual IP address from a Network Load Balancing (NLB) cluster.
Once a virtual IP address is removed, the cluster will not be accessible through this IP address.

This cmdlet changes the configuration on all cluster nodes.
As a result, the NLB cluster will have to restart the convergence process on all nodes to guarantee that configuration changes have been applied on all nodes and that a consistent state is reached.
Any additional operations on the NLB cluster should not be initiated until all cluster nodes have completed the convergence process and are back to the converged state.

ps_nlbc_checkstate_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NlbClusterVip -IP fe80::94dc:5e59:3626:f1d4 | Remove-NlbClusterVip -Force
```

This example removes the virtual IP address from the NLB cluster without seeking user confirmation.

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
Specifies the IP address for the cluster from which the virtual IP address will be removed.

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
Specifies the cluster virtual IP address to remove.

```yaml
Type: ClusterVip[]
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

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## OUTPUTS

### Microsoft.NetworkLoadBalancingClusters.PowerShell.ClusterVip

## NOTES

## RELATED LINKS

[Add-NlbClusterVip](./Add-NlbClusterVip.md)

[Get-NlbClusterVip](./Get-NlbClusterVip.md)

[Set-NlbClusterVip](./Set-NlbClusterVip.md)

