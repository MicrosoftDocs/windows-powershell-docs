---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustergroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterGroup
---

# Get-ClusterGroup

## SYNOPSIS
Gets information about one or more clustered roles (resource groups) in a failover cluster.

## SYNTAX

```
Get-ClusterGroup [[-Name] <StringCollection>] [-VMId <Guid>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterGroup` cmdlet gets information about one or more clustered roles (resource groups)
in a failover cluster.

A resource group is the unit of failover. During failover, all resources in the resource group move
together.

## EXAMPLES

### Example 1

```powershell
Get-ClusterGroup
```

This example lists the state and owner node of each clustered role, or resource group, in the local
cluster.

### Example 2

```powershell
Get-ClusterGroup -Name "Cluster Group" | Get-ClusterResource
```

This example lists the resources in `Cluster Group` on the local cluster.

### Example 3

```powershell
Get-ClusterNode -Name node1 | Get-ClusterGroup
```

This example lists the clustered services and applications, or resource groups, that are currently
owned by `node1` in the local cluster.

### Example 4

```powershell
Get-ClusterGroup -Name FileServer1 | Format-List -Property *
```

This example displays the properties of a clustered file server, or resource group, called
`FileServer1`, in the form of a list.

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

Specifies the cluster or cluster node on which to enumerate the clustered roles.

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

Specifies the name of the clustered role to get.

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

### -VMId

Specifies the virtual machine identifier (ID).

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Add-ClusterGroup](./Add-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)
