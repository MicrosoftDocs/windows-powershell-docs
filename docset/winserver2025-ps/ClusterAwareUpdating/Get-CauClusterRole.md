---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/get-cauclusterrole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauClusterRole
---

# Get-CauClusterRole

## SYNOPSIS
Gets configuration properties of the CAU clustered role on the specified cluster.

## SYNTAX

```
Get-CauClusterRole [[-ClusterName] <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-CauClusterRole` cmdlet gets configuration properties of the Cluster-Aware Updating (CAU)
clustered role on the specified cluster.

## EXAMPLES

### Example 1: Get information about a CAU clustered role on the specified cluster

```powershell
Get-CauClusterRole -ClusterName "CONTOSO-FC1"
```

This command gets information about the CAU clustered role on the cluster named CONTOSO-FC1.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster for which the CAU clustered role information that this cmdlet
gets. This parameter is only required when this cmdlet isn't run on a failover cluster node, or
this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the administrative credentials for the target cluster.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauParameter

## NOTES

## RELATED LINKS

[Add-CauClusterRole](./Add-CauClusterRole.md)

[Disable-CauClusterRole](./Disable-CauClusterRole.md)

[Enable-CauClusterRole](./Enable-CauClusterRole.md)

[Remove-CauClusterRole](./Remove-CauClusterRole.md)

[Set-CauClusterRole](./Set-CauClusterRole.md)

