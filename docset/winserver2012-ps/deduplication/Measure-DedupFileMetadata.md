---
external help file: Dedup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: E39F7A3B-2E8E-4038-B8E5-45CC4279898D
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Measure-DedupFileMetadata

## SYNOPSIS
Measures deduplication metadata for files in a set of folders on the same volume.

## SYNTAX

```
Measure-DedupFileMetadata [-Path] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Measure-DedupFileMetadata** cmdlet measures deduplication metadata for files in a set of folders on the same volume.
The DedupDistinctSize value that this cmdlet returns indicates how much disk space you can reclaim on a volume if you delete a group of folders and then run a Garbage Collection job.

Files often have chunks that are shared across other folders.
The deduplication engine  calculates which chunks are unique and would be deleted after the Garbage Collection job.

## EXAMPLES

### Example 1: Measure potential disk space on a volume
```
PS C:\>Measure-DedupFileMetadata -Path "X:\A_Data","X:\Archive1"
```

This command measures potential disk space that you can reclaim on all folders in the paths X:\A_Data and X:\Archive1.

## PARAMETERS

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

### -Path
Specifies an array of paths to folders.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Update-DedupStatus](./Update-DedupStatus.md)

