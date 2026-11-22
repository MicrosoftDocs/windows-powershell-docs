---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusteraccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterAccess
---

# Get-ClusterAccess

## SYNOPSIS
Gets information about permissions that control access to a failover cluster.

## SYNTAX

```
Get-ClusterAccess [[-User] <StringCollection>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterAccess` cmdlet gets information about permissions that control access to a
failover cluster.

A cluster can allow full access or read-only access. Read-only access limits the user to Windows
PowerShell cmdlets that provide information about the cluster.

## EXAMPLES

### Example 1

```powershell
Get-ClusterAccess
```

This example lists the level of permissions that have been assigned to users of this cluster,
including users who are blocked from access.

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

Specifies the cluster on which to enumerate cluster access details.

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

### -User

Specifies the user for which to get cluster access.

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

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterAccessRule

## NOTES

## RELATED LINKS

[Block-ClusterAccess](./Block-ClusterAccess.md)

[Grant-ClusterAccess](./Grant-ClusterAccess.md)

[Remove-ClusterAccess](./Remove-ClusterAccess.md)
