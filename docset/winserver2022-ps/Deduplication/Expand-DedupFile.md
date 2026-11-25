---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: DedupVolume.cdxml-help.xml
Module Name: Deduplication
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/deduplication/expand-dedupfile?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-DedupFile
---

# Expand-DedupFile

## SYNOPSIS
Expands an optimized file into its original location.

## SYNTAX

```
Expand-DedupFile [-Path] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Expand-DedupFile` cmdlet expands an optimized file into its original location. You may need to
expand optimized files because of compatibility with applications or other requirements.

Ensure that there is enough space on the volume to store the expanded file. If you do not have
enough disk space, the cmdlet attempts to expand the file, and then informs you when it is unable to
finish the operation. If you attempt to restore a file that is not optimized, the cmdlet notifies
you of the error.

## EXAMPLES

### Example 1: Expand a file

```powershell
Expand-DedupFile -Path "D:\Share\File07.doc"
```

This command expands a file to its original location, `D:\Share\File07.doc`. If the file is not
optimized, the cmdlet informs you of the problem.

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
Type: System.Management.Automation.SwitchParameter
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
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or
[Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the
current session on the local computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Specifies an array of file paths. The cmdlet expands files to the file paths specified by this
parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: System.Int32
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

### Uint32

This cmdlet generates an integer that indicates success or failure of the operation. A value of zero
indicates success.

## NOTES

## RELATED LINKS

[Get-DedupVolume](./Get-DedupVolume.md)
