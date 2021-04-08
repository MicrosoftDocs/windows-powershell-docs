---
author: Kateyanne
external help file: WasPsExt_Cmdlets.xml
manager: dansimp
Module Name: WasPSExt
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/waspsext/get-wasjobinstancestatus?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WASJobInstanceStatus

## SYNOPSIS
Gets the current status of a job instance.

## SYNTAX

```
Get-WASJobInstanceStatus [-JobInstance] <WASJobInstance[]>
```

## DESCRIPTION
The **Get-WASJobInstanceStatus** cmdlet gets the current status of the specified job instance, including the computers and the tasks running on the computers.
The **JobInstance** parameter is required.

## EXAMPLES

### Example 1: Get detailed status of a running job
```
The first command gets the job and saves it as a variable.
PS C:\> $job = Get-WASJob -JobName *Automated*

The second command gets the job instances that are running, and saves it as a variable.
PS C:\> $instance = Get-WASJobInstance -Job $job | where {$_.IsComplete -eq $false}

The third command displays the status of the job instances.
PS C:\> Get-WASJobInstanceStatus -JobInstance $instance
```

### Example 2: Get a list of computers still running within a specified job instance
```
The first command gets the job and saves it as a variable.
PS C:\> $job = Get-WASJob -JobName *Automated*

The second command gets the job instances that are running, and saves it as a variable.
PS C:\> $instance = Get-WASJobInstance -Job $job | where {$_.IsComplete -eq $false}

The third command gets the computers that are running for that job instance.
PS C:\> $runningComps = foreach ($status in Get-WASJobInstanceStatus -JobInstance $instance) { foreach ($comp in $status.computers) { if ($comp.Status -eq "Running") { $comp.Computer} }}

The fourth command formats the output data as a table.
PS C:\> format-table -property ComputerName,Location,RebootRequired -inputobject $runningComps
```

## PARAMETERS

### -JobInstance
Specifies the job instance that you want to get status for.
Use the **Get-WASJobInstance** cmdlet to get the job instance object to use with this parameter.
This is a required parameter.

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

