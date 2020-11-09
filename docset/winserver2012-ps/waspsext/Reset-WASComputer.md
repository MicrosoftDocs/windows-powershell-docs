---
external help file: WasPsExt_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: CBBA788E-2BC9-448F-8CC6-B5DD4F2B727E
manager: dansimp
---

# Reset-WASComputer

## SYNOPSIS
Drops a computer from all running job instances.

## SYNTAX

```
Reset-WASComputer [-Computer] <WASComputer[]>
```

## DESCRIPTION
The **Reset-WASComputer** cmdlet drops a computer from all running job instances.
When you drop a computer from a job, the job continues to run on other computers.
The **Computer** parameter is required.
Use **Get-WASComputer** to get the computer object.

## EXAMPLES

### Example 1: Drop a computer from running job instances
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
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASComputer](./Get-WASComputer.md)

