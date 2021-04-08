---
author: Kateyanne
external help file: WasPsExt_Cmdlets.xml
manager: dansimp
Module Name: WasPSExt
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/waspsext/invoke-wasjob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Invoke-WASJob

## SYNOPSIS
Creates and runs a job instance.

## SYNTAX

```
Invoke-WASJob [-Job] <WASJob[]> [[-Runtag] <String>] [[-Testpass] <String>]
```

## DESCRIPTION
The **Invoke-WASJob** cmdlet creates a new job instance in Windows Assessment Services.
It also initiates a run of the job instance.
The **Job** parameter is required.

## EXAMPLES

### Example 1: Run a job
```
PS C:\> $job = Get-WASJob -JobName *automated*
PS C:\> Invoke-WASJob -Job $job
```

This command gets all the jobs with "automated" in the job name, saves it as a variable, and runs the jobs.

### Example 2: Run a job specifying runtag and testpass
```
PS C:\> $job = Get-WASJob -JobName *automated*
PS C:> Invoke-WASJob -Job $job -RunTag "Test iteration 5" -TestPass "Spring 2012"
```

This command gets all the jobs with "automated" in the job name, saves it as a variable, and runs the jobs adding run tag and test pass metadata to the job.

## PARAMETERS

### -Job
Specifies the job to invoke.
This is a required parameter.

```yaml
Type: WASJob[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Runtag
Specifies the run tag you want to add to the job.
If not specified, the default run tag is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Testpass
Specifies the test pass you want to label the job with.
If not specified, the default test pass is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASJob](./Get-WASJob.md)

[Update-WASJob](./Update-WASJob.md)

