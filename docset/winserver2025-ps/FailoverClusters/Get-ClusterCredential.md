---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 09/17/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clustercredential?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterCredential
---

# Get-ClusterCredential

## SYNOPSIS
Retrieves the credentials for a specified node in a failover cluster.

## SYNTAX

```
Get-ClusterCredential [[-NodeName] <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterCredential` cmdlet retrieves the credentials for a specified node in a failover
cluster.

## EXAMPLES

### Example 1

```powershell
Get-ClusterCredential -NodeName "Node01"
```

This example retrieves the credentials for a node named `Node01` in the failover cluster.

## PARAMETERS

### -NodeName

Specifies the name of the node for which to retrieve the credentials.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### System.Management.Automation.PSCredential

## NOTES

## RELATED LINKS
