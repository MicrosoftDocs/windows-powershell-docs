---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/stop-hpcjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-HpcJob
---

# Stop-HpcJob

## SYNOPSIS
Cancels a job.

## SYNTAX

### id (Default)
```
Stop-HpcJob [-Id] <Int32[]> [-Message <String>] [-State <String>] [-Force] [-Graceful]
  [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### job
```
Stop-HpcJob -Job <HpcJob[]> [-Message <String>] [-State <String>] [-Force] [-Graceful]
  [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HpcJob** cmdlet cancels one or more specified jobs.
You can specify the job by using its ID or by using the **HpcJob** object for the job.
You can specify that you want to cancel the job immediately, without using the grace period for task cancellation and without running the node release task.
You can also specify that the state of the job after it is canceled should be Finished instead of Canceled, and you can specify an error message to explain why you canceled the jobs.

When you cancel a job, the job scheduler removes the job from the job queue if the job is waiting to run.
If the job is running, the scheduler by default stops the tasks that are running, and it frees the resources that those tasks were using so that they can be allocated to another job.

Only an administrator or the owner of the job can cancel a job.

## EXAMPLES

### Example 1: Stop a job by ID
```
PS C:\>Stop-HpcJob -Id 45 -Message "Clearing space for Job 51, which needs to run immediately."
```

This command cancels the job with an ID of 45 and provides the user with a cancellation message that explains that you canceled the job to make room for a different job to run.

### Example 2: Stop a job immediately
```
PS C:\>Stop-HpcJob -Id 39 -Force
```

This command cancels the job with an ID of 39 immediately, without using the grace period for task cancellation and without running the node release task.

### Example 3: Create a job, add a task to it, submit it, and then stop it
```
PS C:\>$Job = New-HpcJob -RunUntilCanceled $True -NumCores "1-3"
PS C:\> $Job | Add-HpcTask -Command "echo Hello World!"
PS C:\> $Job | Submit-HpcJob$Job | Stop-HpcJob -State "Finished"
```

This command creates a job with the RunUntilCanceled property set to $True, adds a task to the job, submits the job to the HPC cluster, and then cancels the job so that it has a state of Finished.

### Example 4: Stop a job gracefully
```
PS C:\>Stop-HpcJob -Id 27 -Graceful -State "Finished"
```

This command cancels the job with an ID of 27 gracefully, by allowing running tasks to complete, and sets the job state to finished.

## PARAMETERS

### -Force
Stops the job immediately, without using the grace period for task cancellation and without running the node release task, if the job contains one.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

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

### -Graceful
Stops the job gracefully, by letting running tasks complete.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not supported in previous versions.

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

### -Id
Specifies an array of IDs for the jobs that you want to cancel.
Specify the *Id* parameter or the *Job* parameter, but not both.

```yaml
Type: Int32[]
Parameter Sets: id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies an array of **HpcJob** objects that represent the jobs that you want to cancel.

```yaml
Type: HpcJob[]
Parameter Sets: job
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Message
Specifies an error message to provide to the user that explains why you canceled the job.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you submitted the job.
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
Specifies the state of the job after it is canceled.
The only valid value is Finished.
If you do not specify the *State* parameter, the job has a state of Canceled after it is canceled.
Use this parameter when you want to end a job that has the RunUntilCanceled property set to true, and want to set the state of the job to Finished because you have an alternate way to check that the job finished.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcJob[]

## OUTPUTS

### None

## NOTES
* To cancel a job, the state of the job must be Configuring, Submitted, Validating, Queued, or Running. If the job is running tasks when you cancel the job, the tasks are stopped and marked as failed.

  If you queue the job again, the status of the tasks in the job depends on the state of the tasks when you can canceled the job.
Tasks that were finished when you canceled the job stay finished.
Tasks that were explicitly canceled before they ran and that are currently in the canceled state stay canceled.
All other tasks are queued, including those that failed.

* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.

## RELATED LINKS

[Export-HpcJob](/powershell/module/hpcpack2016/export-hpcjob?view=hpc16-ps)

[Get-HpcJob](/powershell/module/hpcpack2016/get-hpcjob?view=hpc16-ps)

[New-HpcJob](/powershell/module/hpcpack2016/new-hpcjob?view=hpc16-ps)

[Set-HpcJob](/powershell/module/hpcpack2016/set-hpcjob?view=hpc16-ps)

[Submit-HpcJob](./Submit-HpcJob.md)
