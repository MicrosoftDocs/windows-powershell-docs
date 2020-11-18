---
external help file: WasPsExt_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 61BEFC93-70F6-487C-9505-B34DDFCCEE79
manager: dansimp
---

# Stop-WASJobInstance

## SYNOPSIS
Cancels the specified job instance.

## SYNTAX

```
Stop-WASJobInstance [-JobInstance] <WASJobInstance[]>
```

## DESCRIPTION
The **Stop-WASJobInstance** cmdlet cancels the specified job instance.
The **JobInstance** parameter is required.

## EXAMPLES

### Example 1 - Cancel all job instances for the specified job
```
PS C:\> $Job = Get-WasJob -JobID '88fa238c-e83c-44f6-afd8-c0b640059422'
PS C:\> $JobInstance = Get-WasJobInstance -Job $Job
PS C:\> Stop-WasJobInstance $JobInstance
```

This command gets a job based on the JobID, saves it to a variable, and then gets the job instances for that job.
The final command cancels all the job instances for the specified job.

## PARAMETERS

### -JobInstance
Specifies the job instances you want to cancel.
This is a required parameter.
To get a list of job instances associated with a job, use the **Get-WASJobInstance** cmdlet.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASJob](./Get-WASJob.md)

[Get-WASJobInstance](./Get-WASJobInstance.md)

