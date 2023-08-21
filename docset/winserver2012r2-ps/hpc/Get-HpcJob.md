---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpcjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcJob
---

# Get-HpcJob

## SYNOPSIS
Gets jobs.

## SYNTAX

### id (Default)
```
Get-HpcJob [[-Id] <Int32>] [-State <JobState>] [-Name <String>] [-Project <String>] [-TemplateName <String>]
 [-Pool <String>] [-Owner <String>] [-BeginSubmitDate <DateTime>] [-EndSubmitDate <DateTime>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### nodename
```
Get-HpcJob [-NodeName <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcJob** cmdlet gets jobs that match the specified values for the submission time, job ID, name, owner, project, state, or scheduler properties for the job.
By default, this form of the **Get-HpcJob** cmdlet only gets jobs that have a state of queued or running and that belong to the current user, unless you specify the job ID, the state, or the owner of the jobs that you want to get.

Alternatively, the **Get-HpcJob** cmdlet gets a list of jobs that are running on one or more specified nodes.

## EXAMPLES

### Example 1: Get a job by ID
```
PS C:\>Get-HpcJob -Id 4 -Scheduler "MyHeadNode"
```

This command gets the job with an ID of 4 on the cluster with the head node MyHeadNode.

### Example 2: Get jobs by date
```
PS C:\>$Start = Get-Date -Year 2008 -Month 1 -Day 1
PS C:\> $End = Get-Date -Year 2008 -Month 1 -Day 25
PS C:\> Get-HpcJob -BeginSubmitDate $Start -EndSubmitDate $End
```

This command gets jobs submitted on and after January 1, 2008 and before January 25, 2008.

### Example 3: Get jobs by user name
```
PS C:\>Get-HpcJob -Project "Experiments" -Owner "CONTOSO\pfuller"
```

This command gets all jobs that the user with the user name pfuller in the CONTOSO domain submitted for the project named Experiments.

## PARAMETERS

### -BeginSubmitDate
Specifies a **DateTime** object that begins the date and time range during which the jobs that you want to get were submitted.

Use the *BeginSubmitDate* and *EndSubmitDate* parameters to specify a time period.
The **Get-HpcJob** cmdlet gets all jobs submitted within this time period when you specify both parameters.

If you specify only the *BeginSubmitDate* parameter, the search time period is between the value of the *BeginSubmitDate* and the time that you run the **Get-HpcJob** cmdlet.

You can create a **DateTime** object by running the Get-Date cmdlet.

```yaml
Type: DateTime
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndSubmitDate
Specifies a **DateTime** object that ends the date and time range during which the jobs that you want to get were submitted.

Use the *BeginSubmitDate* and *EndSubmitDate* parameters to specify a time period.
The **Get-HpcJob** cmdlet gets all jobs submitted within this time period when you specify both parameters.

If you only specify the *EndSubmitDate* parameter, the search time period is before the value specified for the *EndSubmitDate* parameter.

You can create a **DateTime** object by running the Get-Date cmdlet.

```yaml
Type: DateTime
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the job that you want to get.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of that job that you want to get.

```yaml
Type: String
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName
Specifies an array of compute nodes for which you want to get the currently running jobs.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: nodename
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the owner of the jobs that you want to get, in the domain\user_name format.

```yaml
Type: String
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pool
Specifies the name of the resource pool used by the jobs you want to get.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2).
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Project
Specifies the project name for the jobs that you want to get.

```yaml
Type: String
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to get the jobs.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies a list of one or more states for the jobs that you want to get.
Valid values are:

- Configuring
- Submitted
- Validating
- ExternalValidation
- Queued
- Running
- Finishing
- Finished
- Failed
- Canceled
- Canceling
- All

If you do not specify the *State* parameter, the **Get-HpcJob** cmdlet only gets by default the jobs that are in the queued or running states, unless you specify the *Id* parameter.
If you specify an ID with the *Id* parameter, the **Get-HpcJob** cmdlet gets the job with that job ID, regardless of the state of that job.

```yaml
Type: JobState
Parameter Sets: id
Aliases:
Accepted values: Configuring, Submitted, Validating, ExternalValidation, Queued, Running, Finishing, Finished, Failed, Canceled, Canceling, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateName
Specifies name of the job template used by the jobs that you want to get.

```yaml
Type: String
Parameter Sets: id
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

### None

## OUTPUTS

### HpcJob[]

## NOTES

## RELATED LINKS

[Export-HpcJob](./Export-HpcJob.md)

[New-HpcJob](./New-HpcJob.md)

[Set-HpcJob](./Set-HpcJob.md)

[Stop-HpcJob](./Stop-HpcJob.md)

[Submit-HpcJob](./Submit-HpcJob.md)
