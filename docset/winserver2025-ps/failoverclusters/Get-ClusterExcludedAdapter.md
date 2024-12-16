---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 08/28/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterexcludedadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterExcludedAdapter
---

# Get-ClusterExcludedAdapter

## SYNOPSIS
Retrieves a network adapter from the list of excluded adapters.

## SYNTAX

```
Get-ClusterExcludedAdapter -ExclusionType <AdapterExclusionType> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterExcludedAdapter` cmdlet retrieves a network adapter from a list of network adapters
that should be excluded from use by the Failover Cluster. By default, the cluster will use all
available network adapters, but in some cases you may want to reserve certain adapters as backup or
management, such as Dell iDRAC or HPE iLO.

## EXAMPLES

### Example 1

```powershell
Get-ClusterExcludedAdapter -ExclusionType "FriendlyName" 
```

This example retrieves a list of network adapters that have been excluded from use by the cluster
based on the friendly name.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes.

For more information about Windows PowerShell background jobs, see
[about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionType

Specifies the type of exclusion to retrieve from the cluster. Acceptable values are:

- `IPPrefix`: Excludes a network adapter based on its IP address.
- `Description`: Excludes a network adapter based on its description.
- `FriendlyName`: Excludes a network adapter based on its friendly name.

```yaml
Type: AdapterExclusionType
Parameter Sets: (All)
Aliases:
Accepted values: IPPrefix, Description, FriendlyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then PowerShell calculates an optimum
throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### System.String[]

## NOTES

## RELATED LINKS

[Add-ClusterExcludedAdapter](add-clusterexcludedadapter.md)

[Remove-ClusterExcludedAdapter](remove-clusterexcludedadapter.md)

[Repair-ClusterNameAccount](repair-clusternameaccount.md)

[Set-ClusterExcludedAdapter](set-clusterexcludedadapter.md)
