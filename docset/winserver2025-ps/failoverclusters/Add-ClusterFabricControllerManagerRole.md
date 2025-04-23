---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version:
schema: 2.0.0
ms.date: 04/22/2025
ai-usage: ai-generated
---

# Add-ClusterFabricControllerManagerRole

## SYNOPSIS

Adds a Fabric Controller Manager role to a failover cluster.

## SYNTAX

```
Add-ClusterFabricControllerManagerRole [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The Add-ClusterFabricControllerManagerRole cmdlet adds a Fabric Controller Manager role to an
existing failover cluster. This role is used to integrate and manage fabric resources within the
cluster, enabling advanced orchestration and management scenarios. You can specify the target
cluster by name or use the current cluster context. Optionally, you can provide an input object
representing the cluster to which the role will be added.

## EXAMPLES

### Add a Fabric Controller Manager role to a specific cluster

This example adds a Fabric Controller Manager role to the cluster named Cluster01.

```powershell
Add-ClusterFabricControllerManagerRole -Cluster "Cluster01"
```

## PARAMETERS

### -Cluster

Specifies the name of the cluster to which the Fabric Controller Manager role will be added. If this parameter is not specified, the cmdlet uses the local cluster context.

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

Specifies a cluster object to which the Fabric Controller Manager role will be added. You can pass a cluster object through the pipeline to this parameter.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.PSObject

You can pipe a cluster object to this cmdlet to specify the target cluster for the Fabric Controller Manager role.

## OUTPUTS

### System.Object

This cmdlet returns an object representing the newly added Fabric Controller Manager role or the result of the operation.

## NOTES

## RELATED LINKS
