---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Volume.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/optimize-volume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Optimize-Volume
---

# Optimize-Volume

## SYNOPSIS
Optimizes a volume.

## SYNTAX

### ByDriveLetter (Default)
```
Optimize-Volume [-DriveLetter] <Char[]> [-ReTrim] [-Analyze] [-Defrag] [-SlabConsolidate] [-TierOptimize]
 [-NormalPriority] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ById
```
Optimize-Volume -ObjectId <String[]> [-ReTrim] [-Analyze] [-Defrag] [-SlabConsolidate] [-TierOptimize]
 [-NormalPriority] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByPaths
```
Optimize-Volume -Path <String[]> [-ReTrim] [-Analyze] [-Defrag] [-SlabConsolidate] [-TierOptimize]
 [-NormalPriority] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByLabel
```
Optimize-Volume -FileSystemLabel <String[]> [-ReTrim] [-Analyze] [-Defrag] [-SlabConsolidate] [-TierOptimize]
 [-NormalPriority] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Optimize-Volume -InputObject <CimInstance[]> [-ReTrim] [-Analyze] [-Defrag] [-SlabConsolidate] [-TierOptimize]
 [-NormalPriority] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Optimize-Volume** cmdlet optimizes a volume, performing defragmentation, trim, slab consolidation, and storage tier processing.
If no parameter is specified, then the default operation will be performed per the drive type as follows.

- HDD, Fixed VHD, Storage Space. -Analyze -Defrag.
- Tiered Storage Space. -TierOptimize.
- SSD with TRIM support. -Retrim.
- Storage Space (Thinly provisioned), SAN Virtual Disk (Thinly provisioned), Dynamic VHD, Differencing VHD. -Analyze -SlabConsolidate -Retrim.
- SSD without TRIM support, Removable FAT, Unknown. No operation.

## EXAMPLES

### Example 1: Perform TRIM optimization
```
PS C:\>Optimize-Volume -DriveLetter H -ReTrim -Verbose
```

This example optimizes drive H by re-sending Trim requests.
This is useful on SSD media, and thinly provisioned storage.

### Example 2: Analyze a volume
```
PS C:\>Optimize-Volume -DriveLetter H -Analyze -Verbose
```

This example reports only the current optimization state of drive H.

### Example 3: Defragment a volume
```
PS C:\>Optimize-Volume -DriveLetter H -Defrag -Verbose
```

This example defragments drive H.

### Example 4: Perform slab consolidation
```
PS C:\>Optimize-Volume -DriveLetter H -SlabConsolidate -Verbose
```

This example performs slab consolidation on the storage space backing volume H.

### Example 5: Tier optimize a volume
```
PS C:\>Optimize-Volume -DriveLetter H -TierOptimize
```

This example performs tier optimization on the tiered storage space backing volume H.

## PARAMETERS

### -Analyze
Analyzes the volume specified for fragmentation statistics.
Performs analysis only and reports the current optimization state of the volume.

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

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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

### -Defrag
Indicates that the cmdlet initiates defragmentation on the specified volume.
Defragmentation consolidates fragmented regions of files to improve performance of sequential reads or writes.

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

### -DriveLetter
Specifies the drive letter of the volume to optimize.

```yaml
Type: Char[]
Parameter Sets: ByDriveLetter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the file system label of the volume to optimize.

```yaml
Type: String[]
Parameter Sets: ByLabel
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NormalPriority
Indicates that this cmdlet the operation at normal priority.
By default, the priority is low.

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

### -ObjectId
Specifies the ID of the volume to optimize.

```yaml
Type: String[]
Parameter Sets: ById
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of the volume to optimize.

```yaml
Type: String[]
Parameter Sets: ByPaths
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReTrim
Generates TRIM and Unmap hints for all currently unused sectors of the volume, notifying the underlying storage that the sectors are no longer needed and can be purged.
This can recover unused capacity on thinly provisioned drives.

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

### -SlabConsolidate
Indicates that the cmdlet performs slab consolidation on the storage to optimize slab allocations and to reduce the number of used slabs.

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
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -TierOptimize
Indicates that the cmdlet performs tier optimization of the volume, which places file data on the optimal storage tier according to heat or desired placement.
This parameter only applies to tiered spaces volumes with more than one storage tier.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume

You can use the pipeline operator to pass a Volume object to the *InputObject* parameter.

## OUTPUTS

### None

By default, this cmdlet doesn't return any output.

## NOTES

- When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[Repair-Volume](./Repair-Volume.md)

[Set-Volume](./Set-Volume.md)
