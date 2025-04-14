---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterStorageSpacesDirect.cdxml-help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/repair-clusterstoragespacesdirect?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Repair-ClusterStorageSpacesDirect
---

# Repair-ClusterStorageSpacesDirect

## SYNOPSIS
Repairs disks in a Storage Spaces Direct (S2D) system.

## SYNTAX

### DefaultParameterSet (Default)

```
Repair-ClusterStorageSpacesDirect [-DisableStorageMaintenanceMode] [-RecoverUnboundDrives]
 [-Node <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SkipDiskRecoverySet

```
Repair-ClusterStorageSpacesDirect [-DisableStorageMaintenanceMode] [-Node <String>]
 [-SkipDiskRecovery] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Repair-ClusterStorageSpacesDirect` cmdlet repairs Storage Spaces Direct (S2D) disks.

## EXAMPLES

### Example 1: Repair S2D on all nodes

```powershell
Repair-ClusterStorageSpacesDirect -Verbose -Confirm:$False
```

This command repairs S2D on all nodes without user confirmation.

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

### -DisableStorageMaintenanceMode

Indicates that this cmdlet disables storage maintenance mode. You can use this parameter to clean
the storage maintenance mode setting on physical disks.

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

### -Node

Specifies a node on which the cmdlet performs the operation. If you don't specify a value, all
nodes are used.

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

### -RecoverUnboundDrives

Indicates that this cmdlet recovers physical disks that are unbound. This parameter can be used when
disks are reported to be in a lost communication state. When this parameter is specified, S2D
attempts to reestablish the binding between disks in slow and fast tiers, making disks accessible
again.

```yaml
Type: SwitchParameter
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipDiskRecovery

Indicates that this cmdlet recovers disks so they can be reevaluated to be claimed when repairing
Storage Spaces Direct.

```yaml
Type: SwitchParameter
Parameter Sets: SkipDiskRecoverySet
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

[Set-ClusterStorageSpacesDirect](./Set-ClusterStorageSpacesDirect.md)
