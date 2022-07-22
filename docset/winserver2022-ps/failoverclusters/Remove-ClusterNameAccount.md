---
description: Remove-ClusterNameAccount
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/31/2021
online version: https://docs.microsoft.com/powershell/module/failoverclusters/remove-clusternameaccount?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ClusterNameAccount
---

# Remove-ClusterNameAccount

## SYNOPSIS
Removes a cluster name account from the cluster configuration.

## SYNTAX

```
Remove-ClusterNameAccount [-DeleteComputerObjects] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ClusterNameAccount** cmdlet removes a cluster name account from cluster configuration. A cluster name account is also referred to as a cluster name object (CNO).

The cluster name resource must be offline for the command to succeed.

## EXAMPLES

### Example 1
```powershell
Remove-ClusterNameAccount
```

This command removes the cluster name account from the cluster configuration and disables the cluster name object in Active Directory Domain Services.

### Example 2
```powershell
$cluster = Get-Cluster -Name "CONTOSOCL01.contoso.com"
Remove-ClusterNameAccount -DeleteComputerObjects -InputObject $cluster
```

This command gets the cluster object for the cluster CONTOSOCL01.contoso.com" and removes the
cluster name account from the cluster configuration, deleting the cluster name object in Active
Directory Domain Services.


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

### -DeleteComputerObjects
Specifies that the cluster name object in Active Directory Domain Services should be deleted.

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
Specifies the cluster object for which this cmdlet adds a cluster name account.

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

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-Cluster](Get-Cluster.md)
[New-ClusterNameAccount](New-ClusterNameAccount.md)