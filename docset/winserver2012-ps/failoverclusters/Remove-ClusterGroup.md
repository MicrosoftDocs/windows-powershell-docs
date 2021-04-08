---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/remove-clustergroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-ClusterGroup

## SYNOPSIS
Removes a clustered role, also called a resource group, from a failover cluster.

## SYNTAX

```
Remove-ClusterGroup [[-Name] <StringCollection>] [-Cluster <String>] [-Force] [-InputObject <PSObject>]
 [-RemoveResources]
```

## DESCRIPTION
The **Remove-ClusterGroup** cmdlet removes a clustered role.
also called a resource group, from a failover cluster.

Use this cmdlet to delete a group.
If the group still has resources in it, then either remove the resources first, or specify the **RemoveResources** parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-ClusterGroup -Name MyFileServer
```

This example prompts the user for confirmation and then removes the clustered role named MyFileServer, if the resources have first been removed from it.

### EXAMPLE 2
```
PS C:\>Remove-ClusterGroup -Name MyFileServer -Force
```

This example removes the clustered role named MyFileServer, if the resources have first been removed from it.
The cmdlet does not prompt for confirmation.

### EXAMPLE 3
```
PS C:\>Remove-ClusterGroup -Name MyFileServer -Force -RemoveResources
```

This example removes the clustered  role named MyFileServer, without prompting for confirmation.
All cluster resources in MyFileServer will be deleted.

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
Specifies the clustered role to remove.

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
Specifies the name of the clustered role to remove.

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

### -RemoveResources
Causes the cmdlet to delete all resources in the clustered role before removing the clustered role.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterGroup](./Add-ClusterGroup.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

