---
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
online version: https://go.microsoft.com/fwlink/?LinkId=691106
schema: 2.0.0
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

The `Test-WorkgroupClusterRemoting` function tests if remoting is configured on all nodes.
Additionally it verifies that CredSSP is configured.

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


