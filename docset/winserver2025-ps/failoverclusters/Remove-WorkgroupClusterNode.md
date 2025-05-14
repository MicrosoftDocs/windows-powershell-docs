---
description: Learn how to remove a node from a workgroup cluster using the Remove-WorkgroupClusterNode cmdlet in PowerShell. Includes syntax, examples, and parameter details.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 04/24/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-workgroupclusternode?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WorkgroupClusterNode
ai-usage: ai-generated
---

# Remove-WorkgroupClusterNode

## SYNOPSIS

Removes a node from a workgroup cluster.

## SYNTAX

```
Remove-WorkgroupClusterNode [-Node] <String[]> [-Credentials] <PSCredential[]> [-Name] <String>
 [[-Wait] <Int32>] [-IgnoreStorageConnectivityLoss] [-CleanupDisks] [-Force] [-Confirm] [-WhatIf]
 [-AuthenticationMethod] <WorkgroupClusterAuthenticationMethod> [<CommonParameters>]
```

## DESCRIPTION

The `Remove-WorkgroupClusterNode` function removes a node from the membership in a workgroup
cluster. The rest of the parameters will be forwarded to the `Remove-ClusterNode` function. Please
refer to the documentation for the
[Remove-ClusterNode](/powershell/module/failoverclusters/remove-clusternode) cmdlet.

## EXAMPLES

### Example 1: Remove a node from the cluster

This example removes the node named `Node2` from the cluster that consists of `Node1` and `Node2`.

```powershell
Remove-WorkgroupClusterNode -Node "Node1", "Node2" -Credentials $cred1, $cred2 -Name $Node2
```

### Example 2: Remove a node not currently in the cluster

This example removes `Node3` from the cluster membership. Manual cleanup may be required to clear the node state by logging into `Node3` and running `Clear-ClusterNode`.

```powershell
Remove-WorkgroupClusterNode -Node "Node1", "Node2" -Credentials $cred1, $cred2 -Name $Node3
```

## PARAMETERS

### -AuthenticationMethod

Specifies the authentication method to use when removing the node from the workgroup cluster. Acceptable values are:
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

### -CleanupDisks

Removes any residual cluster metadata from the specified disks. This metadata includes information
that the cluster service uses to manage the disks. By cleaning the metadata, the disks are freed
from any old cluster configurations, making them available for new clusters or other purposes. This
cmdlet may prevent potential conflicts that could arise from leftover metadata when reusing disks.

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

### -Force

Forces the command to run without asking for user confirmation.

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

### -IgnoreStorageConnectivityLoss

Indicates that this cmdlet doesn't check whether the cluster node contains non-shared storage, if
Storage Spaces Direct is enabled. If you don't specify this parameter, the cmdlet checks whether
this node has any Storage Spaces Direct storage. If this cmdlet finds Storage Spaces Direct storage,
it prompts you for confirmation before it removes the node.

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

### -Name

The name of the node to be removed. If the name isn't included in **Node** parameter, the first
node in the **Node** parameter will be used to remove the node. Additional cleanup will be required
to clear the node state.

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

An array of nodes in the workgroup cluster.

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

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If the value `0` is specified, then the call is initiated and
the cmdlet returns without waiting.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: 0
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
You can pipe the name of the node to be removed.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-WorkgroupClusterNode](add-workgroupclusternode.md)

[Clear-ClusterNode](clear-clusternode.md)

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
