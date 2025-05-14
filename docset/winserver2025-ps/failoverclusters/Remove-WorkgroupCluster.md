---
description: Removes a workgroup cluster. This cmdlet disconnects and removes all nodes from the specified workgroup cluster, using the provided credentials and authentication method.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 04/24/2025
online version: https://learn.microsoft.com/powershell/module/failoverclusters/remove-workgroupcluster?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WorkgroupCluster
---

# Remove-WorkgroupCluster

## SYNOPSIS
Removes a workgroup cluster.

## SYNTAX

```
Remove-WorkgroupCluster [[-Node] <String[]>] [[-Credentials] <PSCredential[]>] [-Force] [-Confirm] [-WhatIf]
 [-AuthenticationMethod] <WorkgroupClusterAuthenticationMethod> [<CommonParameters>]
```

## DESCRIPTION

The `Remove-WorkgroupCluster` cmdlet removes a workgroup cluster. This cmdlet disconnects and removes all nodes from the specified workgroup cluster, using the provided credentials and authentication method. If communication is lost with a node or the cluster membership is incomplete, manual cleanup may be required.

## EXAMPLES

### EXAMPLE 1

```powershell
Remove-WorkgroupCluster -Node "Node1", "Node2" -Credentials $cred1, $cred2
```

This example removes the cluster from both `Node1` and `Node2`.

If communication is lost with a node or the membership isn't complete, the cluster might not
be removed and manual cleanup may be needed.

## PARAMETERS

### -AuthenticationMethod
Specifies the authentication method to use when removing the workgroup cluster. Acceptable values are:
- `Certificates`: Uses certificate-based authentication for secure communication between nodes.
- `NoCertificates`: Uses local user accounts and passwords for authentication without certificates.

```yaml
Type: WorkgroupClusterAuthenticationMethod
Parameter Sets: (All)
Aliases:
Accepted values: Certificates, NoCertificates

Required: True
Position: 3
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

Required: False
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

### -Node

An array of nodes that form the current cluster.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: @()
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

## OUTPUTS

### None
This cmdlet does not generate any output. It performs the operation of removing a workgroup cluster.

## NOTES

## RELATED LINKS

[Add-WorkgroupClusterNode](add-workgroupclusternode.md)

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Set-WorkgroupClusterRemotingConfiguration](set-workgroupclusterremotingconfiguration.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
