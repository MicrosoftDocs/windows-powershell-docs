---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 65A0C90E-C243-4EF7-913A-687FDCC61080
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-ClusterAccess

## SYNOPSIS
Gets information about permissions that control access to a failover cluster.

## SYNTAX

```
Get-ClusterAccess [[-User] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterAccess** cmdlet gets information about permissions that control access to a failover cluster.

A cluster can allow full access or read-only access.
Read-only access limits the user to Windows PowerShell® cmdlets that provide information about the cluster.

## EXAMPLES

### Example 1
```
PS C:\>Get-ClusterAccess
IdentityReference              AccessControlType        ClusterRights 
-----------------              -----------------        ------------- 
CONTOSO\user1                               Deny                 Full 
NT AUTHORITY\SYSTEM                        Allow                 Full 
NT AUTHORITY\NETWORK SE...                 Allow                 Full 
BUILTIN\Administrators                     Allow                 Full 
CONTOSO\user2                              Allow                 Read 
NT SERVICE\MSDTC                           Allow                 Full
```

This example lists the level of permissions that have been assigned to users of this cluster, including users who are blocked from access.

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
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterAccessRule

## NOTES

## RELATED LINKS

[Block-ClusterAccess](./Block-ClusterAccess.md)

[Grant-ClusterAccess](./Grant-ClusterAccess.md)

[Remove-ClusterAccess](./Remove-ClusterAccess.md)

