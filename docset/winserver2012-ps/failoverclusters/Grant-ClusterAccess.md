---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 3D6FE616-2674-444A-BA26-832FC93B3CBD
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Grant-ClusterAccess

## SYNOPSIS
Grants access to a failover cluster, either full access or read-only access.

## SYNTAX

```
Grant-ClusterAccess [-User] <StringCollection> [-Cluster <String>] [-Full] [-InputObject <PSObject>]
 [-ReadOnly]
```

## DESCRIPTION
The **Grant-ClusterAccess** cmdlet grants access to a failover cluster, either full access or read-only access.
To provide someone with read-only access to the cluster, use the **ReadOnly** parameter.

## EXAMPLES

### Example 1
```
PS C:\>Grant-ClusterAccess -User contoso\johnj99 -Full
```

This example grants full access to the local cluster to johnj99 in the contoso domain.

### Example 2
```
PS C:\>Grant-ClusterAccess -User contoso\johnj99 -ReadOnly
```

This example grants read-only access to the local cluster to johnj99 in the contoso domain.

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

### -Full
Specifies that the user gets full cluster access.
If no access level is specified, then the user gets read-only cluster access.

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
Specifies that the user gets read-only cluster access.
If no access level is specified, then the user gets read-only cluster access.

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

[Block-ClusterAccess](./Block-ClusterAccess.md)

[Get-ClusterAccess](./Get-ClusterAccess.md)

[Remove-ClusterAccess](./Remove-ClusterAccess.md)

