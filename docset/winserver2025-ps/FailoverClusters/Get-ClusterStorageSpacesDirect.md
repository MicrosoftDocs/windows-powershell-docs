---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterStorageSpacesDirect.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 11/22/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/get-clusterstoragespacesdirect?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterStorageSpacesDirect
---

# Get-ClusterStorageSpacesDirect

## SYNOPSIS
Gets the S2D settings from a cluster.

## SYNTAX

```
Get-ClusterStorageSpacesDirect [-Node <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ClusterStorageSpacesDirect` cmdlet gets the Storage Spaces Direct (S2D) settings from a
cluster.

## EXAMPLES

### Example 1: Get the Storage Spaces Direct settings from a cluster

```powershell
Get-ClusterStorageSpacesDirect -Node "K0617-C1.contoso.com"
```

This command sets the S2D settings from the `K0617-C1.contoso.com` cluster.

### Example 2: Get the Storage Spaces Direct settings from a cluster

```powershell
Get-Cluster "K0617-C1.contoso.com" | Get-ClusterStorageSpacesDirect
```

This command gets the S2D settings from cluster `K0617-C1.contoso.com` and pipes the cluster object
to `Get-ClusterStorageSpacesDirect`.

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

### -Node

Specifies the name of the cluster node from which to get storage spaces direct information.

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

[Set-ClusterStorageSpacesDirect](./Set-ClusterStorageSpacesDirect.md)

[Get-Cluster](./Get-Cluster.md)
