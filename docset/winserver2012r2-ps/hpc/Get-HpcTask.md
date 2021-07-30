---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpctask?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcTask
---

# Get-HpcTask

## SYNOPSIS
Gets a task or subtask for a job.

## SYNTAX

### id (Default)
```
Get-HpcTask -JobId <Int32> [-TaskId <Int32>] [-SubTaskId <Int32>] [-State <TaskState[]>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### job
```
Get-HpcTask -Job <HpcJob> [-TaskId <Int32>] [-SubTaskId <Int32>] [-State <TaskState[]>]
[-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcTask** cmdlet gets a specified task or subtask for the specified job, or gets a list of all tasks for the specified job.
You can cancel, requeue, or submit the task that you get with this cmdlet by using the **Cancel**, **Requeue**, or **Submit** method of the **HpcTask** object that the cmdlet returns.

## EXAMPLES

### Example 1: Get a task by ID
```
PS C:\>Get-HpcTask -JobId 35 -TaskId 4
```

This command gets the fourth task from the job with a job ID of 35.

### Example 2: Get all tasks from a job
```
PS C:\>Get-HpcJob -Id 35 | Get-HpcTask
```

This command gets all of the tasks from the job with a job ID of 35.

### Example 3: Use HpcTask object methods
```
PS C:\>$T = Get-HpcTask -JobId 3 -TaskId 1
PS C:\> $T.Requeue() $T.Cancel() $T.Submit()
```

The first command gets the specified **HpcTask** object, and then stores it in the $T variable.

The second command uses the methods of the **HpcTask** object in $T to requeue, cancel, and submit a task.

### Example 4: Get a parametric subtask
```
PS C:\>Get-HpcTask -JobId 3 -TaskId 1 -SubTaskId 95
```

This command gets the ninety-fifth step of the parametric sweep task that is the first task in the job with a job ID of 3.

## PARAMETERS

### -Job
Specifies an **HpcJob** object that corresponds to the job that contains the tasks or subtasks that you want to get.
Use the Get-HpcJob cmdlet to get an **HpcJob** object for a job.
You can specify either the *Job* parameter or the *JobId* parameter, but not both parameters at the same time.

```yaml
Type: HpcJob
Parameter Sets: job
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Specifies the job ID for the job that contains the tasks or subtasks that you want to get.
Use the Get-HpcJob cmdlet to view a list of jobs and their job IDs.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the tasks or subtasks.
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
Specifies an array of states that the tasks or subtasks that you want to get should have.
Valid values are:

- Configuring
- Submitted
- Validating
- Queued
- Dispatching
- Running
- Finishing
- Finished
- Failed
- Canceled
- Canceling
- All

```yaml
Type: TaskState[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubTaskId
Specifies the subtask ID for the subtask that you want to get.
Only parametric tasks have subtasks.
A parametric task has one task ID and multiple subtask IDs.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskId
Specifies the ID of the task that you want to get.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcJob

## OUTPUTS

### HpcTask

## NOTES
* If you specify the *Job* or *JobId* parameter, but not the *TaskId* or *SubTaskID* parameter, this cmdlet gets all of the tasks in the specified job. If any of the tasks are parametric tasks, the cmdlet also gets all of the subtasks of the parametric task.

  If you specify the *Job* or *JobId* parameter and specify a parametric task for the *TaskId* parameter, but do not specify the *SubTaskID* parameter, this cmdlet gets the parametric task, but not the subtasks of the parametric task.

## RELATED LINKS

[Add-HpcTask](./Add-HpcTask.md)

[Export-HpcTask](./Export-HpcTask.md)

[Get-HpcJob](./Get-HpcJob.md)

[Set-HpcTask](./Set-HpcTask.md)

[Stop-HpcTask](./Stop-HpcTask.md)
