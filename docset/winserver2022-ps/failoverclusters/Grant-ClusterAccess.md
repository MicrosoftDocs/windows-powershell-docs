---
description: Use this article to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 05/17/2023
online version: https://learn.microsoft.com/powershell/module/failoverclusters/grant-clusteraccess?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-ClusterAccess
---

# Grant-ClusterAccess

## SYNOPSIS
Grants access to a failover cluster, either full access or read-only access.

## SYNTAX

```
Grant-ClusterAccess [-User] <StringCollection> [-Full] [-ReadOnly] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Grant-ClusterAccess` cmdlet grants access to a failover cluster, either full access or
read-only access. To provide someone with read-only access to the cluster, use the **ReadOnly**
parameter. Granting full access to the cluster is equivalent to granting full access to each of the
cluster nodes.

## EXAMPLES

### Example 1

```powershell
Grant-ClusterAccess -User contoso\johnj99 -Full
```

This example grants full access to the local cluster to `johnj99` in the `contoso` domain.

### Example 2

```powershell
Grant-ClusterAccess -User contoso\johnj99 -ReadOnly
```

This example grants read-only access to the local cluster to `johnj99` in the `contoso` domain.

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

### -Full

Specifies that the user gets full cluster access. If no access level is specified, then the user
gets read-only cluster access.

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

Specifies the cluster on which to grant access for the given user.

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

### -ReadOnly

Specifies that the user gets read-only cluster access. If no access level is specified, then the
user gets read-only cluster access.

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

### -User

Specifies the user for whom to grant cluster access.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: True
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

### None

## NOTES

## RELATED LINKS

[Block-ClusterAccess](./Block-ClusterAccess.md)

[Get-ClusterAccess](./Get-ClusterAccess.md)

[Remove-ClusterAccess](./Remove-ClusterAccess.md)
