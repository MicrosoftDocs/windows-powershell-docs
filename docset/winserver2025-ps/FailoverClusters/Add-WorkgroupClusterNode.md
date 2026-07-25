---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 04/25/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-workgroupclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-WorkgroupClusterNode
ai-usage: ai-generated
---

# Add-WorkgroupClusterNode

## SYNOPSIS

Adds a node to a workgroup cluster.

## SYNTAX

```
Add-WorkgroupClusterNode [-Node] <String[]> [-Credentials] <PSCredential[]> [-Name] <String>
 [-Credential] <PSCredential> [-NoStorage] [-Confirm] [-WhatIf]
 [-AuthenticationMethod] <WorkgroupClusterAuthenticationMethod> [<CommonParameters>]
```

## DESCRIPTION

The `Add-WorkgroupClusterNode` cmdlet adds a node to a workgroup cluster. This cmdlet lets you
expand an existing workgroup cluster by adding a new node, specifying the required credentials and
authentication method. The node can be added with or without shared storage, depending on your
configuration.

## EXAMPLES

### Example 1: Add a node to a workgroup cluster

This example adds `Node3` to the cluster whose membership is comprised of `Node1` and `Node2`.

```powershell
$parameters = @{
    Node = @("Node1", "Node2")
    Credentials = @($cred1, $cred2)
    Name = "Node3"
    Credential = $cred3
}
Add-WorkgroupClusterNode @parameters
```

## PARAMETERS

### -AuthenticationMethod

Specifies the authentication method to use when adding the node to the workgroup cluster. Acceptable values are:

- `Certificates`: Uses certificate-based authentication for secure communication between nodes.
- `NoCertificates`: Uses local user accounts and passwords for authentication without certificates.

```yaml
Type: WorkgroupClusterAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: Certificates, NoCertificates

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

The credential for the node to be added.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credentials

An array of credentials for the nodes.

```yaml
Type: System.Management.Automation.PSCredential[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

The name of the node to be added.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node

An array of nodes to be added to the cluster.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoStorage

Specifies that shared storage is ignored for the workgroup cluster node.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

You can pipe an array of node names to this cmdlet.

### System.Management.Automation.PSCredential[]

You can pipe an array of credentials to this cmdlet.

### System.String

You can pipe the name of the node to be added.

### System.Management.Automation.PSCredential

You can pipe the credential for the node to be added.

## OUTPUTS

### None

This cmdlet doesn't generate any output. It performs the operation of adding a node to a workgroup cluster.

## NOTES

## RELATED LINKS

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
