---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-clusterresource?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-ClusterResource

## SYNOPSIS
Removes a clustered resource from the failover cluster.

## SYNTAX

```
Remove-ClusterResource [[-Name] <StringCollection>] [-Cluster <String>] [-Force] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Remove-ClusterResource** cmdlet removes a clustered resource from the failover cluster.
Before removing a resource, be sure to review whether any other resource is dependent on that resource.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-ClusterResource -Name "Cluster Disk 4"
```

This example prompts the user for confirmation and then deletes the cluster named Cluster Disk 4 from the local cluster.

### EXAMPLE 2
```
PS C:\>Remove-ClusterResource -Name "Cluster Disk 5" -Force
```

This example deletes the cluster named Cluster Disk 5 from the local cluster without prompting for confirmation.

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
Specifies the cluster resource to remove.

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
Specifies the name of the cluster resource to remove.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterResource](./Add-ClusterResource.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)

