---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 686040F6-7835-48E1-925B-37E04384DD9F
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Remove-Cluster

## SYNOPSIS
Destroys an existing failover cluster.

## SYNTAX

```
Remove-Cluster [[-Cluster] <String>] [-CleanupAD] [-Force] [-InputObject <PSObject>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-Cluster** cmdlet destroys an existing failover cluster.
The affected servers will no longer function together as a cluster.

This cmdlet deletes all copies of the cluster configuration database on all cluster nodes.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\>Remove-Cluster
```

This example prompts the user for confirmation, then destroys the local failover cluster and removes cluster configuration information from the cluster nodes.

### Example 2
```
PS C:\>Remove-Cluster -Force
```

This example destroys the local failover cluster and removes cluster configuration information from the cluster nodes.
The cmdlet does not prompt for confirmation.

### Example 3
```
PS C:\>Get-Cluster -Name Cluster1 | Remove-Cluster -Force -CleanupAD
```

This example destroys the cluster named Cluster1, removes cluster configuration information from the cluster nodes, and deletes the cluster objects in Active Directory.
The cmdlet does not prompt for confirmation.

## PARAMETERS

### -CleanupAD
Specifies that when the cluster is destroyed, the objects in Active Directory that are associated with the cluster are removed.

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

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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
Specifies the cluster to destroy.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[New-Cluster](./New-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Stop-Cluster](./Stop-Cluster.md)

[Test-Cluster](./Test-Cluster.md)

