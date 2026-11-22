---
description: Use this topic to help manage Storage Spaces Direct with Windows PowerShell.
external help file: ClusterStorageSpacesDirect.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/enable-clusterstoragespacesdirect?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ClusterStorageSpacesDirect
---

# Enable-ClusterStorageSpacesDirect

## SYNOPSIS
Enables Storage Spaces Direct on a Fail-Over Cluster.

## SYNTAX

### Auto

```
Enable-ClusterStorageSpacesDirect [-PoolFriendlyName <String>] [-Autoconfig <Boolean>]
 [-CacheState <CacheStateType>] [-CacheMetadataReserveBytes <UInt64>]
 [-CachePageSizeKBytes <UInt32>] [-SkipEligibilityChecks] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WithXML

```
Enable-ClusterStorageSpacesDirect [-PoolFriendlyName <String>] [-Autoconfig <Boolean>]
 [-CacheState <CacheStateType>] [-CacheMetadataReserveBytes <UInt64>]
 [-CachePageSizeKBytes <UInt32>] [-SkipEligibilityChecks] -XML <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WithCacheDeviceModel

```
Enable-ClusterStorageSpacesDirect [-PoolFriendlyName <String>] [-Autoconfig <Boolean>]
 [-CacheState <CacheStateType>] [-CacheMetadataReserveBytes <UInt64>]
 [-CachePageSizeKBytes <UInt32>] [-SkipEligibilityChecks] -CacheDeviceModel <String[]>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Enable-ClusterStorageSpacesDirect` cmdlet enables highly available Storage Spaces that use
directly attached storage Storage Spaces Direct (S2D) on a cluster.

## EXAMPLES

### Example 1: Enable Storage Spaces Direct

```powershell
Enable-ClusterStorageSpacesDirect
```

This command enables S2D on the cluster.

### Example 2: Enable Storage Spaces Direct specifying a Friendly Name

```powershell
Enable-ClusterStorageSpacesDirect -PoolFriendlyName 'Sales'
```

This command enables S2D on the cluster and sets a friendly name for the Storage Spaces Direct pool.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

The cmdlet immediately returns an object that represents the job and then displays the command
prompt. You can continue to work in the session while the job completes. To manage the job, use the
`*-Job` cmdlets. To get the job results, use the
[Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see
[about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Autoconfig

Indicates that this cmdlet that the pool should be automatically created and configured. When a pool
already exists before Storage Spaces Direct is enabled the **AutoConfig** parameter becomes a no-op.
**AutoConfig** is set to true by default. If you don't want the pool to be automatically created,
but created manually, you should set **AutoConfig** to false.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheDeviceModel

Specifies a list of disk models that should be used by Storage Spaces Direct cache. When this
parameter is omitted the system automatically determines which disks to use for the operation.

```yaml
Type: String[]
Parameter Sets: WithCacheDeviceModel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheMetadataReserveBytes

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CachePageSizeKBytes

Specifies the page size used by Storage Spaces Direct cache. This parameter is useful to control the
memory footprint used to manage the pages. To reduce the memory overhead on systems with
considerably large amounts of storage the page size can be increased to 32 kilobytes (KB) or even 64
KB. The default value is 16 KB, which represents a good tradeoff on most systems.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:
Accepted values: 8, 16, 32, 64

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheState

Specifies the Storage Spaces Direct cache state. The acceptable values for this parameter are:
`Enabled` or `Disabled`. The default value is `Enabled`.

```yaml
Type: CacheStateType
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967)
or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
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

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolFriendlyName

Specifies the friendly name of the Storage Spaces Direct pool when it is created.

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

### -SkipEligibilityChecks

Indicates that this cmdlet skips cache eligibility checks.

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

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -XML

Specifies the XML file that contains the storage supported configuration information.

```yaml
Type: String
Parameter Sets: WithXML
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
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-ClusterStorageSpacesDirect](./Disable-ClusterStorageSpacesDirect.md)

[Get-ClusterStorageSpacesDirect](./Get-ClusterStorageSpacesDirect.md)

[Set-ClusterStorageSpacesDirect](./Set-ClusterStorageSpacesDirect.md)

[Get-Cluster](./Get-Cluster.md)
