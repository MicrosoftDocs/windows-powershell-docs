---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/optimize-volume?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Optimize-Volume

## SYNOPSIS
Optimizes a volume, performing such tasks as defragmentation and trim.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Optimize-Volume [-DriveLetter] <Char[]> [-Analyze] [-AsJob] [-CimSession <CimSession[]>] [-Defrag] [-ReTrim]
 [-SlabConsolidate] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Optimize-Volume [-Analyze] [-AsJob] [-CimSession <CimSession[]>] [-Defrag] [-ReTrim] [-SlabConsolidate]
 [-ThrottleLimit <Int32>] -ObjectId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Optimize-Volume [-Analyze] [-AsJob] [-CimSession <CimSession[]>] [-Defrag] [-ReTrim] [-SlabConsolidate]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Optimize-Volume [-Analyze] [-AsJob] [-CimSession <CimSession[]>] [-Defrag] [-ReTrim] [-SlabConsolidate]
 [-ThrottleLimit <Int32>] -Path <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Optimize-Volume [-Analyze] [-AsJob] [-CimSession <CimSession[]>] [-Defrag] [-ReTrim] [-SlabConsolidate]
 [-ThrottleLimit <Int32>] -FileSystemLabel <String[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Optimize-Volume** cmdlet optimizes a volume, performing such tasks as defragmentation and trim.



 If no parameter is specified, then the default operation will be performed per the drive type as follows.



Defragment (drive type) : HDD


Slab : YES


Consolidation : NO


TRIM : NO



Defragment (drive type) : SSD


Slab : NO


Consolidation : NO


TRIM : YES



Defragment (drive type): VHD


Slab : YES


Consolidation : NO


TRIM : NO



Defragment (drive type): diff VHD


Slab : NO


Consolidation : NO


TRIM : YES



Defragment (drive type): Thinly Provisioned (Storage Spaces, thinly provisioned SAN Virtual Disk, Dynamic VHD)


Slab : NO


Consolidation : YES


TRIM : YES

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

## PARAMETERS

### -Analyze
Analyzes the volume specified for defrag or optimize statistics.
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
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -Defrag
Runs the defragment function on the specified volume, consolidating fragmented files to improve read and write performance.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel
Specifies the file system label of the volume to optimize.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of the volume to optimize.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReTrim
Generates TRIM and Unmap hints for all previously used sectors of the volume, notifying the underlying storage that the sectors are no longer needed and can be purged.
This can recover unused capacity on thinly provisioned drives and on solid state drives (SSDs).

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
Optimizes the volume per the supplied slab size and alignment to reduce the number of slabs on which the volumes is mounted.
Performs slab consolidation on the storage to optimize slab allocations.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Volume
You can pipe a Volume object to the **InputObject** parameter.

## OUTPUTS

## NOTES

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Volume](./Get-Volume.md)

[Repair-Volume](./Repair-Volume.md)

[Set-Volume](./Set-Volume.md)

