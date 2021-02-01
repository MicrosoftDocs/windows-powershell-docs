---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
online version: 
schema: 2.0.0
title: Resume-WASComputer
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 0352DFC2-5F5D-49A1-9B78-E1C460945DC2
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Resume-WASComputer

## SYNOPSIS
Releases a hold on a test computer, and continues with the next action.

## SYNTAX

```
Resume-WASComputer [-Computer] <WASComputer[]> [-Retry] [<CommonParameters>]
```

## DESCRIPTION
The Resume-WASComputer cmdlet instructs dep_nextref_was to skip the current action on a specific computer and move to the next action.
This command releases the hold on a specified computer.
The **Computer** parameter is required.

## EXAMPLES

### Example 1
```
PS C:\> $Computer = Get-WASComputer -ComputerName 'TestComputer1'
PS C:\> Resume-WASComputer -Computer $Computer
```

Gets the test computer named "TestComputer1", saves it as a variable, and then resumes the computer.
This releases the hold on the computer so that it can continue with the next action.

### Example 2
```
PS C:\> $Computer = Get-WASComputer
PS C:\> Resume-WASComputer -Computer $Computer
```

Gets an array of all the test computers in inventory, saves it as a variable, and then resumes all the computer in the array.
This releases the hold on them so that the next action can continue.

## PARAMETERS

### -Computer
Specifies the computer or computers that you want to resume.
This is a required parameter.

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

### -Retry
Resumes the job and retries the action that failed, before going on to the next action.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASComputer](./Get-WASComputer.md)

