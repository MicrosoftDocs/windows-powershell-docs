---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 07/01/2024
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/get-caudeviceinfoforfeatureupdates?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauDeviceInfoForFeatureUpdates
---

# Get-CauDeviceInfoForFeatureUpdates

## SYNOPSIS
Retrieves device information for feature updates from a specified directory.

## SYNTAX

```
Get-CauDeviceInfoForFeatureUpdates [[-ClusterName] <String>] [-Credential <PSCredential>]
 -PathToDirectory <String> [-PathToDeploymentCab <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-CauDeviceInfoForFeatureUpdates` cmdlet retrieves device information for feature updates
from a specified directory.

## EXAMPLES

### Example 1

```powershell
$parameters = @{
ClusterName = "CONTOSO-FC1"
PathToDirectory = "C:\Updates" 
PathToDeploymentCab = "C:\Deployment\FeatureUpdate.cab"
}
Get-CauDeviceInfoForFeatureUpdates $parameters
```

This command retrieves device information for feature updates from the `C:\Updates` directory for
the cluster named **CONTOSO-FC1**. It also specifies the path to the deployment cab file that will
be created for the update in `C:\Deployment\FeatureUpdate.cab`.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster on which to create the CAU clustered role. This parameter is only
required when this cmdlet isn't run on a failover cluster node, or this cmdlet is used to reference
a failover cluster different from where the cmdlet is run.

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

### -PathToDeploymentCab

Specifies the path to the deployment cab file that will be created for the update.

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

### -PathToDirectory

Specifies the path to the directory that contains the device information files. This parameter is
required.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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

### System.String

### Microsoft.ClusterAwareUpdating.ActivityIdMap

## NOTES

## RELATED LINKS
