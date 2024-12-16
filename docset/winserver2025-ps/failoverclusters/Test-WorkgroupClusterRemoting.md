---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 09/11/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/test-workgroupclusterremoting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WorkgroupClusterRemoting
---

# Test-WorkgroupClusterRemoting

## SYNOPSIS
Tests if remoting is configured on all nodes.

## SYNTAX

```
Test-WorkgroupClusterRemoting [[-Node] <String[]>] [[-Credentials] <PSCredential[]>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Test-WorkgroupClusterRemoting` function tests if remoting is configured on all nodes. It also
verifies if CredSSP is configured.

## EXAMPLES

### EXAMPLE 1

```powershell
Test-WorkgroupClusterRemoting -Node "Node1", "Node2" -Credentials $cred1, $cred2
```

This example tests if remoting is configured on `Node1` and `Node2` using the credentials in
`$cred1` and `$cred2`.

## PARAMETERS

### -Node

An array of nodes to test remoting on.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: @()
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials

An array of credentials for the nodes.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-WorkgroupClusterNode](add-workgroupclusternode.md)

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)
