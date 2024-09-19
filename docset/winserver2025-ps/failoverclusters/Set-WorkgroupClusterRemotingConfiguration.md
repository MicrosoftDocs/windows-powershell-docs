---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.Adless.PowerShell.psm1-help.xml
Module Name: FailoverClusters
ms.date: 09/11/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-workgroupclusterremotingconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WorkgroupClusterRemotingConfiguration
---

# Set-WorkgroupClusterRemotingConfiguration

## SYNOPSIS
Configures the remote management settings for a failover cluster that is part of a workgroup.

## SYNTAX

```
Set-WorkgroupClusterRemotingConfiguration [<CommonParameters>]
```

## DESCRIPTION

The `Set-WorkgroupClusterRemotingConfiguration` cmdlet configures the remote management settings for
a failover cluster that is part of a workgroup.

## EXAMPLES

### Example 1

```powershell
Set-WorkgroupClusterRemotingConfiguration -Verbose
```

This example displays detailed information about the current workgroup cluster remoting
configuration.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WorkgroupClusterNode](add-workgroupclusternode.md)

[New-WorkgroupCluster](new-workgroupcluster.md)

[Remove-WorkgroupCluster](remove-workgroupcluster.md)

[Remove-WorkgroupClusterNode](remove-workgroupclusternode.md)

[Test-WorkgroupCluster](test-workgroupcluster.md)

[Test-WorkgroupClusterRemoting](test-workgroupclusterremoting.md)
