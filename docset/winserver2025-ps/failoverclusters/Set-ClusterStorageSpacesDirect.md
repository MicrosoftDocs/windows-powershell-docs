---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterStorageSpacesDirect.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterstoragespacesdirect?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterStorageSpacesDirect
---

# Set-ClusterStorageSpacesDirect

## SYNOPSIS
Sets S2D cache parameters.

## SYNTAX

```
Set-ClusterStorageSpacesDirect [-CacheState <CacheStateType>] [-CacheModeHDD <CacheModeType>]
 [-CacheModeSSD <CacheModeType>] [-Nodes <String[]>] [-SkipEligibilityChecks]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterStorageSpacesDirect` cmdlet sets Storage Spaces Direct (S2D) cache parameters.

## EXAMPLES

### Example 1: Set S2D cache parameters

```powershell
Set-ClusterStorageSpacesDirect -CimSession "cluster01.contoso.com" -CacheModeHDD ReadWrite
```

The following command sets the S2D cache parameter as ReadWrite on the cluster named
`cluster01.contoso.com`.

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

### -CacheModeHDD

Specifies the cache mode of the hard disk drive. The acceptable values for this parameter are:

- `ReadOnly`
- `WriteOnly`
- `ReadWrite`

```yaml
Type: CacheModeType
Parameter Sets: (All)
Aliases:
Accepted values: ReadOnly, WriteOnly, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheModeSSD

Specifies the cache mode of the solid state drive. The acceptable values for this parameter are:

- `ReadOnly`
- `WriteOnly`
- `ReadWrite`

```yaml
Type: CacheModeType
Parameter Sets: (All)
Aliases:
Accepted values: ReadOnly, WriteOnly, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheState

Specifies the S2D cache state. The acceptable values for this parameter are: `Enabled` or
`Disabled`. The default value is `Enabled`.

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

### -Nodes

Specifies, as a string array, the nodes on which this operation takes place.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipEligibilityChecks

Indicates that the cmdlet skips cache eligibility checks. If cache stores are found with data
partitions on them, then you can use `Enable-ClusterStorageSpacesDirect` with the cache state as
Disabled but not as ReadOnly or ReadWrite.

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

[Enable-ClusterStorageSpacesDirect](./Enable-ClusterStorageSpacesDirect.md)

[Get-ClusterStorageSpacesDirect](./Get-ClusterStorageSpacesDirect.md)
