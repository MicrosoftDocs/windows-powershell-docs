---
author: brianlic
description: 
external help file: DedupFileMetadata.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Measure-DedupFileMetadata
ms.assetid: E39F7A3B-2E8E-4038-B8E5-45CC4279898D
---

# Measure-DedupFileMetadata

## SYNOPSIS
Measures potential disk space on a volume.

## SYNTAX

```
Measure-DedupFileMetadata [-Path] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Measure-DedupFileMetadata** cmdlet measures potential disk space on a volume.
The **DedupDistinctSize** value that this cmdlet returns indicates how much disk space you can reclaim on a volume if you delete a group of folders and then run a garbage collection job.

Files often have chunks that are shared across other folders.
The deduplication engine calculates which chunks are unique and would be deleted after the garbage collection job.

## EXAMPLES

### Example 1: Measure potential disk space on a volume
```
PS C:\>Measure-DedupFileMetadata -Path "X:\A_Data","X:\Archive1"
```

This command measures potential disk space that you can reclaim on all folders in the paths X:\A_Data and X:\Archive1.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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
Specifies an array of paths of folders.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Update-DedupStatus](./Update-DedupStatus.md)

