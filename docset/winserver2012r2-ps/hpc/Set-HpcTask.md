---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/set-hpctask?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HpcTask
---

# Set-HpcTask

## SYNOPSIS
Sets the properties for a task.

## SYNTAX

### task (Default)
```
Set-HpcTask -Task <HpcTask> [-CommandLine <String>] [-Name <String>] [-Exclusive <Boolean>]
 [-FailJobOnFailure <Boolean>] [-FailJobOnFailureCount <Int32>] [-Rerunnable <Boolean>]
 [-ValidExitCodes <String>] [-RunTime <String>] [-NumNodes <String>] [-NumSockets <String>]
 [-NumCores <String>] [-RequiredNodes <String[]>] [-WorkDir <String>] [-Stdin <String>] [-Stdout <String>]
 [-Stderr <String>] [-Depend <String[]>] [-CustomProperties <String[]>] [-Env <String[]>]
 [-Parametric <Boolean>] [-Type <TaskType>] [-Start <Int32>] [-End <Int32>] [-Increment <Int32>]
  [-Scheduler <String[]>] [<CommonParameters>]
```

### id
```
Set-HpcTask -JobId <Int32> -TaskId <Int32> [-CommandLine <String>] [-Name <String>] [-Exclusive <Boolean>]
 [-FailJobOnFailure <Boolean>] [-FailJobOnFailureCount <Int32>] [-Rerunnable <Boolean>]
 [-ValidExitCodes <String>] [-RunTime <String>] [-NumNodes <String>] [-NumSockets <String>]
 [-NumCores <String>] [-RequiredNodes <String[]>] [-WorkDir <String>] [-Stdin <String>] [-Stdout <String>]
 [-Stderr <String>] [-Depend <String[]>] [-CustomProperties <String[]>] [-Env <String[]>]
 [-Parametric <Boolean>] [-Type <TaskType>] [-Start <Int32>] [-End <Int32>] [-Increment <Int32>]
  [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcTask** cmdlet sets the properties for a specified task.
You can specify a task by using the job identifier and task identifier for the task or by using an **HpcTask** object for the task.
You can only change the properties for a task that is in the configuring state.

## EXAMPLES

### Example 1: Change the name of a task
```
PS C:\>Set-HpcTask -JobId 10 -TaskId 2 -Name "NewTaskName"
```

This command changes the name of the second task of the job with an identifier of 10 to NewTaskName.

### Example 2: Get a task and set its properties
```
PS C:\>Get-HpcTask -JobId 12 -TaskId 3 | Set-HpcTask -Rerunnable $False -WorkDir "C:\logs" -Stdout Task12_3.log
```

This command gets an **HpcTask** object for the third task of the job with an identifier of 12, and then sets the Rerunnable property of the task to $False and the Stdout property to C:\logs\Task12_3.log.

### Example 3: Set a task as critical
```
PS C:\>Set-HpcTask -JobId 96 -TaskId 2 -FailJobOnFailure $True -Command "MyApplication.exe"
```

This command specifies that the second task of job 96 is a critical task, so that the job and its tasks stop running and the job is marked as failed if the second task fails.

### Example 4: Set a parametric sweep task
```
PS C:\>Set-HpcTask -JobId 156 -TaskId 3 -Type ParametricSweep -Start 1 -End 100 -FailJobOnFailure $True -FailJobOnFailureCount 5 -Command "MyApplication.exe *"
```

This command sets the third task of job 156 to be a critical parametric sweep task, and specifies that when 5 of the subtasks of the parametric sweep task fail, the job and its task and subtasks stop running and the job and parametric sweep task are marked as failed.

## PARAMETERS

### -CommandLine
Specifies the command line for the task, including the command or application name and any necessary arguments.

In tasks that include subtasks, you can use the asterisk character as a placeholder for the parametric sweep index in Parametric Sweep tasks or for the subtask identifier in Service, Node Preparation, and Node Release tasks.
You can include more than one asterisk to indicate the minimum number of positions to use when expressing the number of the index or subtask.
This does not limit numbers that require more positions.
This placeholder can be useful when defining the command or the input and output files for the task.

The HPC job scheduler service interprets commands before it sends them to the compute nodes.
To run a command that uses an asterisk, you can include the caret (^) as an escape character.

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

### -CustomProperties
Specifies an array of custom properties of the job.
The list should have a format of variable_name1=value1\[;variable_name2=value2\[;...\]\].
Custom properties are case insensitive, and will reflect the case used when they were first defined.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

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

### -Depend
Specifies an array of names for the tasks in the specified job on which the new task depends.
The new task does not start until all the tasks in the list finish running.

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

### -End
Specifies the ending index for a parametric task.
The ending index must be larger than the starting index.
A parametric task runs the command multiple times, substituting the current index value for any asterisks in the command line.
The current index starts at the index that the *Start* parameter specifies, and increases by the value that the *Increment* parameter specifies each subsequent time the command runs.
When the current index exceeds the ending index, the task stops running the command.

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

### -Env
Specifies an array of environment variables to set in the run-time environment of the task and the values to assign to those environment variables.
The list should have a format of variable_name1=value1\[,variable_name2=value2\[,...\]\].
To unset an environment variable, do not specify a value.
For example, "variable_to_unset_name=".

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

### -Exclusive
Indicates whether the job scheduler should ensure that no other task runs on the same node as this task while this task runs.

A non-zero value or $True indicates that the job scheduler should ensure that no other task runs on the same node as this task while this task runs.
If you specify a non-zero value or $True value for the *Exclusive* parameter for the task, you must also specify a non-zero value or $True value for the *Exclusive* parameter for the job to which you are adding the task, or the task fails on submission.

A value of 0 or $False indicates that this task can share compute nodes with other tasks.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailJobOnFailure
Indicates whether the task is critical for the job, so that the job and its tasks stop running and the job is marked as failed if the task fails.

A nonzero value or $True indicates that the task is critical for the job, and that the job and its tasks stop running and the job is marked as failed if the task fails.
A value of 0 or $False indicates that the task is not critical for the job, so that job continues to run the remaining tasks when the task that is not critical fails, and the job is marked as failed only when those remaining tasks finish.

If you specify a value for the *FailJobOnFailureCount* parameter, and do not specify a value for the *FailJobOnFailure* parameter, *FailJobOnFailure* is automatically set to $True.

To specify that a job and its tasks should stop running and that job should be marked as failed when any of the tasks in the job fail, use the *FailOnTaskFailure* parameter of the New-HpcJob or Set-HpcJob cmdlet.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1).
It is not supported in previous versions.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailJobOnFailureCount
Specifies the number of subtasks of a critical parametric sweep or service task that must fail before the job and its tasks and subtask should stop running and the task and job should be marked as failed.
You can specify a value from 1 through 1,000,000.
If you specify more subtasks than the critical task contains, the job and its tasks and subtasks run to completion no matter how many subtasks fail.

If you specify a value for the *FailJobOnFailureCount* parameter, but also specify $False for the *FailJobOnFailure* parameter, *FailJobOnFailureCount* is set to 0.
If you specify a value for *FailJobOnFailureCount*, and do not specify a value for *FailJobOnFailure*, *FailJobOnFailure* is automatically set to $True.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1).
It is not supported in previous versions.

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

### -Increment
Specifies the value to use when incrementing the index for a parametric task.
This value must be a positive integer.
A parametric task runs the command multiple times, substituting the current index value for any asterisks (*) in the command line.
The current index starts at the index that the *Start* parameter specifies, and it increases by the value that the *Increment* parameter specifies each subsequent time the command runs.
When the current index exceeds the index that the *End* parameter specifies, the task stops running the command.

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

### -JobId
Specifies the ID of the job that contains the task that you want to modify.
Use the Get-HpcJob cmdlet to get a list of jobs and their identifiers.
You can use the *JobId* and *TaskId* parameters to specify a task, or you can use the *Task* parameter, but you cannot combine the *Task* parameter with the *JobId* or the *TaskId* parameter.

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

### -Name
Specifies a name to use for this task in command output and in the user interface.
The maximum length for the name is 80 characters.

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

### -NumCores
Specifies the overall number of cores that the task requires across the HPC cluster, in the format \[minimum-\]maximum.
The task runs on at least the minimum number of cores and on no more than the maximum.
If you specify only one value, this cmdlet sets the minimum and maximum number of cores to that value.
If you specify a minimum value that exceeds the total number of cores available across the cluster, an error occurs when you submit the task or the job that contains the task.

The minimum and maximum values can be only positive integers.

You cannot specify the *NumCores* parameter if you also specify the *NumNodes* or *NumSockets* parameter.

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

### -NumNodes
Specifies the overall number of nodes that the task requires across the HPC cluster, in the format \[minimum-\]maximum.
The task runs on at least the minimum number of nodes and on no more than the maximum.
If you specify only one value, this cmdlet sets the minimum and maximum number of nodes to that value.
If you specify a minimum value that exceeds the total number of nodes available across the cluster, an error occurs when you submit the task or the job that contains the task.

The minimum and maximum values can be only positive integers.

You cannot specify the *NumNodes* parameter if you also specify the *NumCores* or *NumSockets* parameter.

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

### -NumSockets
Specifies the overall number of sockets that the task requires across the HPC cluster, in the format \[minimum-\]maximum.
The task runs on at least the minimum number of sockets and on no more than the maximum.
If you specify only one value, this cmdlet sets the minimum and maximum number of sockets to that value.
If you specify a minimum value that exceeds the total number of sockets available across the cluster, an error occurs when you submit the task or the job that contains the task.

The minimum and maximum values can be only positive integers.

You cannot specify the *NumSockets* parameter if you also specify the *NumCores* or *NumNodes* parameter.

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

### -Parametric
Indicates whether the new task is a parametric task.
A parametric task runs the command multiple times, substituting the current index value for any asterisks in the command line.
If you specify this parameter, you should also specify values for the Start, End, and Increment values if you do not want to use the default values that define the index values for the parametric task.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredNodes
Specifies an array of nodes on which the task must run.
The job scheduler exclusively allocates all of the nodes in this list to run the task.

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

### -Rerunnable
Indicates whether the job scheduler attempts to rerun the task if the task runs and fails.

A non-zero value or $True indicates that the job scheduler should attempt to rerun the task if the task runs and fails.

A value of 0 or $False indicates that the job scheduler should not attempt to rerun the task if the task runs and fails, and it should move the task to the failed state immediately.

The cluster administrator can configure the number of times that the job scheduler tries to rerun a task before moving the task to the failed state.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunTime
Specifies the maximum amount of time that the task should run.
After the task runs for this amount of time, the job scheduler cancels the task.

You specify the amount of time in a format of \[\[days:\]hours:\]minutes.
You can also specify "infinite" to indicate that the task can run for an unlimited amount of time.

If you specify only one part of the days:hours:minutes format, the cmdlet interprets the specified value as the number of minutes.
For example, 12 indicates 12 minutes.
If you specify two parts of the format, the command interprets the left part as hours and the right part as minutes.
For example, 10:30 indicates 10 hours and 30 minutes.

You can use one or more digits for each part of the format.
The maximum value for each part is 2,147,483,647.

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
Specifies the host name or IP address of the head node for the cluster that includes the task that you want to modify.
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

### -Start
Specifies the starting index for a parametric task.
The starting index must be less than the ending index.
A parametric task runs the command multiple times, substituting the current index value for any asterisks in the command line.
The current index starts at the starting index, and it increases by the value that the Increment parameter specifies each subsequent time the command runs.
When the current index exceeds the ending index that the *End* parameter specifies, the task stops running the command.

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

### -Stderr
Specifies the name for the file to which the task should redirect the standard error stream, including the full path or path relative to the working directory for the file if the task should not redirect the standard error stream to a file in the working directory.
If you specify a path that does not exist, the task fails.

If you do not specify the *Stderr* parameter, the task stores up to 4 kilobytes (KB) of data in the job scheduler database that the Output property for the task specifies.
Any output that exceeds 4 KB is lost.

The maximum length of value for this parameter is 160 characters.

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

### -Stdin
Specifies the name for the file from which the task should receive standard input.
This includes the full path or a path that is relative to the working directory for the file if the task should not receive standard input from a file in the working directory.
If you specify a file or path that does not exist, the task fails.

The maximum length of value for this parameter is 160 characters.

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

### -Stdout
Specifies the name for the file to which the task should redirect standard output.
This includes the full path or a path that is relative to the working directory for the file if the task should not redirect standard output to a file in the working directory.
If you specify a path that does not exist, the task fails.

If you do not specify the *Stdout* parameter, the task stores up to 4 kilobytes (KB) of data in the job scheduler database that the Output property for the task specifies.
Any output that exceeds 4 KB is lost.

The maximum length of value for this parameter is 160 characters.

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

### -Task
Specifies an **HpcTask** object that corresponds to the task that you want to modify.
Use the Get-HpcTask cmdlet to get an **HpcTask** object for a task.
You can use the *Task* parameter to specify a task, or you can use the *TaskId* and *JobId* parameters together, but you cannot combine the *Task* parameter with either the *JobId* or the *TaskId* parameter.

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
Specifies the task identifier of the task that you want to modify.
Use the Get-HpcTask cmdlet to get a list of tasks in a job and their task identifiers.
You can use the *TaskId* and *JobId* parameters to specify a task, or you can use the *Task* parameter, but you cannot combine the *Task* parameter with either the *JobId* or the *TaskId* parameter.

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

### -Type
Specifies a type for the task, which defines how to run the command for the task.
Valid values are:

- Basic
- ParametricSweep
- NodePrep
- NodeRelease
- Service

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: TaskType
Parameter Sets: (All)
Aliases:
Accepted values: Basic, ParametricSweep, NodePrep, NodeRelease, Service

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidExitCodes
Specifies the exit codes to be used for checking whether the task successfully exits.
You can specify discrete integers and integer ranges separated by commas.

You can use min and max on a range, representing the start or end.
For example, `0..max` represents nonnegative integers.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

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

### -WorkDir
Specifies the working directory under which the task should run.

The maximum length of value for this parameter is 160 characters.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcTask

## OUTPUTS

### HpcTask

## NOTES

## RELATED LINKS

[Add-HpcTask](/powershell/module/hpcpack2016/add-hpctask?view=hpc16-ps)

[Export-HpcTask](/powershell/module/hpcpack2016/export-hpctask?view=hpc16-ps)

[Get-HpcTask](/powershell/module/hpcpack2016/get-hpctask?view=hpc16-ps)

[Stop-HpcTask](./Stop-HpcTask.md)
