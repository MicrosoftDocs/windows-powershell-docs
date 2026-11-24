---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/23/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/update-clusternetworknameresource?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ClusterNetworkNameResource
---

# Update-ClusterNetworkNameResource

## SYNOPSIS
Registers existing Network Name resources with a DNS server in a way that doesn't interrupt cluster
availability.

## SYNTAX

```
Update-ClusterNetworkNameResource [[-Name] <StringCollection>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Update-ClusterNetworkNameResource` cmdlet registers existing Network Name resources with a
DNS server in a way that doesn't interrupt cluster availability.

## EXAMPLES

### Example 1: Register name resources with a DNS server

```powershell
Get-ClusterResource -Name "Cluster Name" | Update-ClusterNetworkNameResource
```

This example registers the Network Name resources of the local cluster with a DNS server.

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

Specifies the network name resource to register with the DNS server.

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

### -Name

Specifies the network name to be registered with the DNS server.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Get-ClusterResource](./Get-ClusterResource.md)

[Update-ClusterIPResource](./Update-ClusterIPResource.md)
