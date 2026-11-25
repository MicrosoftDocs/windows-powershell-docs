---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/28/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/repair-clusternameaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-ClusterNameAccount
---

# Repair-ClusterNameAccount

## SYNOPSIS
Repairs the Cluster Name Account and ensures that the cluster continues to function properly.

## SYNTAX

### InputObject (Default)

```
Repair-ClusterNameAccount [-Credentials <PSCredential>] [-Domain <String>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

### Credentials

```
Repair-ClusterNameAccount [-Credentials <PSCredential>] [-Domain <String>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Repair-ClusterNameAccount` cmdlet repairs or updates the Cluster Name Account used for
authentication and authorization on a Failover Cluster. The Cluster Name Account is used to create
Highly Available applications or Virtual Computer Objects (VCOs) in the cluster.

To learn more about cluster accounts in domain environments, see
[Configuring cluster accounts in Active Directory](/windows-server/failover-clustering/configure-ad-accounts).

## EXAMPLES

### Example 1

```powershell
Repair-ClusterNameAccount -Cluster "Cluster01"
```

This example repairs or updates the Cluster Name Account for the cluster named `Cluster01`.

### Example 2

```powershell
$cred = Get-Credential
Repair-ClusterNameAccount -Cluster "Cluster01" -Credentials $cred -Domain "contoso.com"
```

This example repairs or updates the Cluster Name Account for the cluster named `Cluster01` using
the specified credentials and domain. The `Get-Credential` cmdlet is used to create a PSCredential
object for the `-Credentials` parameter.

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

### -Credentials

Specifies the credentials that this cmdlet uses when it connects to Active Directory Domain
Services.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the name of the domain in which to repair the cluster name account. This should be the
fully qualified domain name (FQDN) of the domain that the cluster is in.

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

Specifies the cluster name account to repair.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.Management.Automation.PSObject

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-ClusterExcludedAdapter](add-clusterexcludedadapter.md)

[Get-ClusterExcludedAdapter](get-clusterexcludedadapter.md)

[Remove-ClusterExcludedAdapter](remove-clusterexcludedadapter.md)

[Set-ClusterExcludedAdapter](set-clusterexcludedadapter.md)
