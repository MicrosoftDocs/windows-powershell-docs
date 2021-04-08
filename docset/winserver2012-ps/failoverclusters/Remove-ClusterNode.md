---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/remove-clusternode?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-ClusterNode

## SYNOPSIS
Removes a node from a failover cluster.

## SYNTAX

```
Remove-ClusterNode [[-Name] <StringCollection>] [-Cluster <String>] [-Force] [-InputObject <PSObject>]
 [-Wait <Int32>]
```

## DESCRIPTION
The **Remove-ClusterNode** cmdlet removes a node from a failover cluster.
After the node is removed, the node no longer functions as part of the cluster unless the node is added back to the cluster.
Removing a node is also called evicting a node from the cluster.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-ClusterNode -Name node4
```

This example removes the node named node4 from the local cluster.

### EXAMPLE 2
```
PS C:\>Remove-ClusterNode -Name node4 -Force
```

This example removes the node named node4 from the local cluster without prompting for confirmation.

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

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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
Specifies the cluster node to remove.

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
Specifies the name of the cluster node to remove.

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

### -Wait
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-ClusterNode](./Add-ClusterNode.md)

[Get-ClusterNode](./Get-ClusterNode.md)

[Resume-ClusterNode](./Resume-ClusterNode.md)

[Start-ClusterNode](./Start-ClusterNode.md)

[Stop-ClusterNode](./Stop-ClusterNode.md)

[Suspend-ClusterNode](./Suspend-ClusterNode.md)

