---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: A86B6D12-3F22-4124-A654-AA0EF4F28ED0
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-ClusterAccess

## SYNOPSIS
Removes a user from the access list on the cluster.

## SYNTAX

```
Remove-ClusterAccess [[-User] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Remove-ClusterAccess** cmdlet removes a user from the access list on the cluster.
After this cmdlet is run, the user might still have access to the cluster if the user account is part of another user group which is on the cluster access list.

## EXAMPLES

### Example 1
```
PS C:\>Remove-ClusterAccess -User contoso\johnj99
```

This example removes the user johnj99 in the contoso domain from the access list of the local cluster.
After this cmdlet runs, the user might still have access to the cluster if the user is part of another user group granted access to the cluster.

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

### -InputObject
Specifies the cluster from which to remove access for the given user.

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
Specifies the user for which to remove cluster access.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Block-ClusterAccess](./Block-ClusterAccess.md)

[Get-ClusterAccess](./Get-ClusterAccess.md)

[Grant-ClusterAccess](./Grant-ClusterAccess.md)

