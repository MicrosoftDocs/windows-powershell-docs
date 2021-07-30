---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
Module Name: WasPSExt
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/waspsext/reset-wascomputer?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-WASComputer
---

# Reset-WASComputer

## SYNOPSIS
Drops a computer from all running job instances.

## SYNTAX

```
Reset-WASComputer [-Computer] <WASComputer[]> [<CommonParameters>]
```

## DESCRIPTION
The Reset-WASComputer cmdlet drops a computer from all running job instances.
When you drop a computer from a job, the job continues to run on other computers.
The **Computer** parameter is required.
Use **Get-WASComputer** to get the computer object.

## EXAMPLES

### Example 1
```
PS C:\> $Computer = Get-WasComputer -ComputerName 'TestComputer1'
PS C:\> Reset-WasComputer -Computer $Computer
```

Gets the test computer named "TestComputer1", saves it as a variable, and then resets the computer.
This drops it from all running job instances.

## PARAMETERS

### -Computer
Specifies the computer that you want to drop.
Use **Get-WASComputer** to get the computer object.

```yaml
Type: WASComputer[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

