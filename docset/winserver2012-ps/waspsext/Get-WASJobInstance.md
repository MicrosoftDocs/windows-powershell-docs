---
external help file: WasPsExt_Cmdlets.xml
Module Name: WasPSExt
online version: https://docs.microsoft.com/powershell/module/waspsext/get-wasjobinstance?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WASJobInstance

## SYNOPSIS
Gets a list of job instances.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WASJobInstance [-Job] <WASJob[]> [[-Runtag] <String>] [[-Testpass] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WASJobInstance [-JobInstance] <WASJobInstance[]>
```

## DESCRIPTION
The **Get-WASJobInstance** cmdlet gets a list of job instances associated with a specific job, and displays metadata for each job instance.
The Job parameter is required.

## EXAMPLES

### Example 1: Get all job instances for a job
```
PS C:\>$job = Get-WASJob -JobName *automated*
Get-GetJobInstance -Job $job
```

This command gets all the jobs with "automated" in the job name, assigns it to a variable, and then gets all the job instances for the job.

### Example 2: Get all running job instances for a job
```
PS C:\> $job = Get-WASJob -JobName *automated*
PS C:\> Get-WASJobInstance -Job $job | where {$_.IsComplete -eq $false }
```

This command gets all the jobs with "automated" in the job name, assigns it to a variable, and then gets all the job instances that are currently running for the job.

### Example 3: Get all running job instances
```
PS C:\> $job = Get-WASJob | Get-WASJobInstance | where {$_.IsComplete -eq $false}
```

This command gets all the jobs that are currently running using dep_nextref_was server.

## PARAMETERS

### -Job
Specifies the job object for which to retrieve job instances.
This is a required parameter.

```yaml
Type: WASJob[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobInstance
Specifies the job instance for which to retrieve an updated object.
You can pass a job instance of itself to get an update or copy of the job instance object.

```yaml
Type: WASJobInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Runtag
Specifies the run tag for the job instance you want to get.
The full name of the run tag isn't required.
Wildcards are accepted.
If this parameter isn't specified, all job instances are listed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Testpass
Specifies the test pass for the job instance you want to get.
The full name of the test pass isn't required.
Wildcards are accepted.
If this parameter isn't specified, all job instances are listed.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

[Get-WASJobInstanceStatus](./Get-WASJobInstanceStatus.md)

[Skip-WASJobInstance](./Skip-WASJobInstance.md)

[Stop-WASJobInstance](./Stop-WASJobInstance.md)

