---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
Module Name: WasPSExt
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/waspsext/skip-wasjobinstance?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Skip-WASJobInstance
---

# Skip-WASJobInstance

## SYNOPSIS
Drops a computer from the running job instance.

## SYNTAX

```
Skip-WASJobInstance [-Computer] <WASComputer[]> [-JobInstance] <WASJobInstance[]> [<CommonParameters>]
```

## DESCRIPTION
The Skip-WASJobInstance cmdlet drops a computer from the running job instance.
The computer is removed from the job instance but is still available.
The job instance continues to run on other computers included in the job.

## EXAMPLES

### Example 1
```
PS C:\> $computer = get-wascomputer testcomputer-toast2
PS C:\> $instance = get-wasjob *automated* | get-wasjobinstance | where { $_.IsComplete -eq $false }
PS C:\> Skip-WASJobInstance -computer $computer -jobinstance $instance
```

This command gets the computer, and saves it as a variable.
It then gets all running job instances of jobs with "automated" in the name, and drops the computer from all running job instances.

## PARAMETERS

### -Computer
Specifies the computer to drop from the specified job instance.
The computer can be in any state.

```yaml
Type: WASComputer[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobInstance
Specifies the job instance object that includes the computer you want to drop.

```yaml
Type: WASJobInstance[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASComputer](./Get-WASComputer.md)

[Get-WASJob](./Get-WASJob.md)

[Get-WASJobInstance](./Get-WASJobInstance.md)

