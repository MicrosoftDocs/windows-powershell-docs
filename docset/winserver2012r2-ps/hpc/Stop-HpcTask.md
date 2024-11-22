---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/stop-hpctask?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-HpcTask
---

# Stop-HpcTask

## SYNOPSIS
Cancels a task or subtask.

## SYNTAX

### id (Default)
```
Stop-HpcTask -JobId <Int32> -TaskId <Int32> [-SubTaskId <Int32>] [-Message <String>] [-State <String>] [-Force]
  [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### task
```
Stop-HpcTask -Task <HpcTask> [-Message <String>] [-State <String>] [-Force]
  [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HpcTask** cmdlet cancels the specified task or subtask.
You can specify a task or subtask by specifying an **HpcTask** object for the task or subtask, or by specifying the job, task, and subtask IDs.
You can also specify that the state of the task after it is canceled should be Finished instead of Canceled.

When you cancel a task or subtask, the job scheduler removes the task or subtask from the queue if the task or subtask is waiting to run.
If the task or subtask is running, the scheduler stops the task or subtask and frees the resources that it was using so that they can be allocated to other jobs.

Only an administrator or the owner of the job that contains a task or subtask can cancel the task or subtask.

## EXAMPLES

### Example 1: Stop a task by ID
```
PS C:\>Stop-HpcTask -JobId 12 -TaskId 2
```

This command cancels the task with a task ID of 2 in the job with a job ID of 12.

### Example 2: Stop a subtask by ID
```
PS C:\>Stop-HpcTask -JobId 46 -TaskId 3 -SubTaskId 12 -Message "Clearing space for other tasks that need to run immediately." -Force
```

This command cancels the subtask with a subtask ID of 12 for the task with a task ID of 3 in the job with a job ID of 46 without using the grace period for task cancellation, and then sets the message that explains the reason for the cancellation to "Clearing space for other tasks that need to run immediately."

### Example 3: Get a task by ID and stop it
```
PS C:\>GetHpcTask -JobId 25 -TaskId 1 | Stop-HpcTask
```

This command gets an **HpcTask** object for the task with a task ID of 1 in the job with a job ID of 25, and then cancels that task by redirecting that **HpcTask** object to the input of the **Stop-HpcTask** cmdlet.

### Example 4: Stop a task and set its state
```
PS C:\>Stop-HpcTask -JobId 5 -TaskId 1 -SubTaskId 5 -State Finished
```

This command cancels the subtask with a subtask ID of 5 for the task with a task ID of 1 in the job with a job ID of 5, and sets the state of the task after it is canceled to Finished.

## PARAMETERS

### -Force
Stops the task immediately without using the grace period for task cancellation.
Only tasks that respond when the user types CTRL+BREAK can use the grace period for task cancellation.

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

### -JobId
Specifies the job ID of the job that includes the task or subtask that you want to cancel.
You cannot specify both the *JobId* and *Task* parameters.
If you specify the *JobId* parameter, you must also specify the *TaskId* parameter.

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

### -Message
Specifies a message that indicates the reason that you are canceling the task.

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
Specifies the host name or IP address of the head node for the HPC cluster to which the job that contains the task or subtask that you want to cancel was submitted.
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
Specifies the state of the task after it is canceled.
The only valid value is Finished.
If you do not specify the *State* parameter, the task has a state of Canceled after it is canceled.

Use this parameter when you want to end a task process immediately.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
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

### -SubTaskId
Specifies the subtask ID of the subtask that you want to cancel.
If you specify the *SubTaskId* parameter, you must also specify the *JobId* and *TaskId* parameters.
You cannot specify both the *SubTaskId* and *Task* parameters.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Task
Specifies the task or subtask that you want to cancel.
Use the Get-HpcTask cmdlet to get the **HpcTask** object for the task or subtask.
You cannot specify the Task parameter if you also specify the *JobId*, the *TaskId*, or the *SubtaskId* parameter.

```yaml
Type: HpcTask
Parameter Sets: task
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskId
Specifies the task ID of the task that you want to cancel.
If you specify the *TaskId* parameter, you must also specify the *JobId* parameter.
You cannot specify both the *TaskId* and *Task* parameters.

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

### HpcTask

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcTask](/powershell/module/hpcpack2016/add-hpctask?view=hpc16-ps)

[Export-HpcTask](/powershell/module/hpcpack2016/export-hpctask?view=hpc16-ps)

[Get-HpcTask](/powershell/module/hpcpack2016/get-hpctask?view=hpc16-ps)

[Set-HpcTask](./Set-HpcTask.md)

[Stop-HpcJob](./Stop-HpcJob.md)

[Submit-HpcJob](./Submit-HpcJob.md)
