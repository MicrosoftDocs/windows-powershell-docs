---
description: The Get-CauDeviceInfoForFeatureUpdates cmdlet gets device information for feature updates to use with Cluster-Aware Updating (CAU).
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/17/2021
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/get-caudeviceinfoforfeatureupdates?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CauDeviceInfoForFeatureUpdates
---

# Get-CauDeviceInfoForFeatureUpdates

## SYNOPSIS
Gets device information for feature updates to use with CAU.

## SYNTAX

```
Get-CauDeviceInfoForFeatureUpdates [[-ClusterName] <String>] [-Credential <PSCredential>]
 -PathToDirectory <String> [<CommonParameters>]
```

## DESCRIPTION

The `Get-CauDeviceInfoForFeatureUpdates` cmdlet gets device information for feature updates to use
with Cluster-Aware Updating (CAU).

## EXAMPLES

### Example 1: Get device information

```powershell
$Parameters = @{
    ClusterName = 'CONTOSO-FC1'
    PathToDirectory = 'C:\temp\contoso-device-info'
}
Get-CauDeviceInfoForFeatureUpdates $Parameters
```

This example gets device information for CAU for the specified cluster. This example uses
splatting to pass parameter values from the `$Parameters` variable to the command. Learn more about
[Splatting](/powershell/module/microsoft.powershell.core/about/about_splatting).

## PARAMETERS

### -ClusterName

Specifies the name of the cluster fow which to get device information.

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

### -PathToDirectory

Specifies a directory.

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

[Get-CauClusterRole](get-cauclusterrole.md)

[Get-CauPlugin](get-cauplugin.md)

[Get-CauReport](get-caureport.md)

[Get-CauRun](get-caurun.md)
