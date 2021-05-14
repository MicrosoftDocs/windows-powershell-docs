---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/new-hpcjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HpcJob
---

# New-HpcJob

## SYNOPSIS
Creates a job, or creates a copy of an existing job.

## SYNTAX

```
New-HpcJob [-JobFile <String>] [-Job <HpcJob>] [-ValidExitCodes <String>] [-NumNodes <String>]
 [-NumSockets <String>] [-NumCores <String>] [-NumGpus <String>] [-RequestedNodes <String[]>]
 [-Exclusive <Boolean>] [-RunUntilCanceled <Boolean>] [-Priority <String>] [-RunTime <String>]
 [-Project <String>] [-Name <String>] [-License <String[]>] [-TemplateName <String>] [-NodeGroups <String[]>]
 [-OrderBy <String[]>] [-FailOnTaskFailure <Boolean>] [-MinMemoryPerNode <Int32>] [-MaxMemoryPerNode <Int32>]
 [-MinCoresPerNode <Int32>] [-MaxCoresPerNode <Int32>] [-Progress <Int32>] [-ProgressMessage <String>]
 [-NotifyOnStart <Boolean>] [-NotifyOnCompletion <Boolean>] [-EmailAddress <String>] [-Holduntil <DateTime>]
 [-NodeGroupOp <JobNodeGroupOp>] [-SingleNode <Boolean>] [-EstimatedProcessMemory <Int32>] [-JobEnv <String[]>]
 [-ParentJobIds <Int32[]>] [-FailDependentTasks <Boolean>] [-TaskExecutionFailureRetryLimit <Int32>]
 [-CustomProperties <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-HpcJob** cmdlet creates a job on the specified cluster by using the settings that the parameters or job XML files specify, or creates a new copy of an existing job.

## EXAMPLES

### Example 1: Create a job from a job file
```
PS C:\>New-HpcJob -JobFile "C:\JobFiles\SampleJob1.xml"
```

This command creates a job by using the settings in the job file at C:\JobFiles\SampleJob1.xml.

### Example 2: Create a job with a specified run time
```
PS C:\>New-HpcJob -Name "Sample Job" -Template "Default" -Project "Cluster Testing" -RunTime 0:0:30
```

This command creates a job named Sample Job by using the default job template.
This job has a run-time limit of 30 minutes.

### Example 3: Create a copy of a job and set its properties
```
PS C:\>Get-HpcJob -Id 47 | New-HpcJob -Priority "AboveNormal+15" -NotifyOnStart $True -NotifyOnCompletion $True
```

This command creates a job that is a copy of the job with an ID of 47, but sets the priority of the new job to 3015 and specifies that the HPC job scheduler service should send an email notification when the job starts and when the job ends.

### Example 4: Create a job and set environment variables for it
```
PS C:\>New-HpcJob -JobEnv "MyVariable1=yes","MyVariable2=" -Progress 15 -ProgressMessage "Making management believe that we have done more than we really have."
```

This command creates a job for which an environment variable named MyVariable1 is set to yes and the environment variable named MyVariable2 is unset within the context of the job.
It also sets the progress percentage for the job to 15 and sets a status message for the job.

### Example 5: Create a job that sends email when it starts
```
PS C:\>New-HpcJob -NotifyOnStart $True -EmailAddress "pfuller@contoso.com"
```

This command creates a job for which you want to receive email when the job starts, and specifies that the HPC job scheduler service should send the email to pfuller@contoso.com.

## PARAMETERS

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

### -EmailAddress
Specifies the email address to which the HPC job scheduler service should send notifications when the job starts or finishes.

The maximum length for the email address that you specify is 256 characters.

When you specify an email address for receiving notifications about a job, the notifications are not turned on automatically.
You still need to use the *NotifyOnStart* and/or *NotifyOnCompletion* parameter to specify when you want to receive notifications about the job.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1).
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

### -Exclusive
Indicates whether the job scheduler should ensure that no other job runs on the same nodes as this job while this job runs.

A non-zero value or $True indicates that the job scheduler should ensure that no other job runs on the same nodes as this job while this job runs.

A value of 0 or $False indicates that this job can share compute nodes with other jobs.

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

### -EstimatedProcessMemory
Specifies the maximum amount of memory in megabytes (MB) that each process in this job is expected to consume.
The HPC job scheduler service only runs the job on nodes that have at least the amount of memory specified.

A value of 0 indicates that the HPC job scheduler service will not allocate the job to nodes based on the memory requirements of the job.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

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

### -FailDependentTasks
Indicates that if a task fails or is canceled, all dependent tasks will fail.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

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

### -FailOnTaskFailure
Specifies whether the job scheduler should stop the job and fail the entire job immediately when a task in the job fails.

A non-zero value or $True indicates that the job scheduler should stop the job and fail the entire job immediately when a task in the job fails.

A value of 0 or $False indicates that the job scheduler should continue running the rest of the tasks in the job after any task in the job fails.

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

### -Holduntil
Specifies the date and time in local time until which the HPC job scheduler service should wait before trying to start the job.
The HPC job scheduler service only runs the job at the date and time that this parameter specifies if the resources needed for the job are available.
If the resources needed for the job are not available at that date and time, the job remains queued until the necessary resources become available.
You can only specify the *Holduntil* parameter for a job in the queued state.

The HPC job scheduler service only runs the job at the date and time that this parameter specifies if the resources needed for the job are available.
If the resources needed for the job are not available at that date and time, the job remains queued until the necessary resources become available.

You can specify the date and time in any format that the .NET Framework can parse for the current operating system culture.
For information about how the .NET Framework parses date and time strings, see Parsing Date and Time Strings in the .NET Frameworkhttp://go.microsoft.com/fwlink/p/?LinkId=200188 (http://go.microsoft.com/fwlink/p/?LinkId=200188) in MSDN.
The time specified using *Holduntil* is converted internally to UTC, and does not reflect local Daylight Saving Time.

You can only specify the *Holduntil* parameter for a job that is not running or has not completed.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies an **HpcJob** object that represents an existing job that you want to copy when you create the new job.
Use the Get-HpcJob cmdlet to get an **HpcJob** object for an existing job.
You cannot specify both the *Job* and the *JobFile* parameters.

```yaml
Type: HpcJob
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobEnv
Specifies an array of environment variables that you want to set in the context of the job and the values that you want to set for the environment variables.
Specify the environment variables and values as a list of strings that have a format of environment_variable_name=value; for example, `"MyVariable1=yes","MyVariable2=no"`.
To unset an environment variable in the context of a job, leave out the value part of the string; for example, `"MyVariable3="`.

If you set or unset an environment variable for a job, that environment variable is also set or unset for each task in the job unless you override that environment variable setting for the task by specifying a new setting with the *Env* parameter when you call the Add-HpcTask cmdlet.

This parameter was introduced in HPC Pack 2008 R2.
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

### -JobFile
Specifies the file name and path for a job XML file that contains settings to use for the job that you want to create.
You cannot specify both the *JobFile* and *Job* parameters.

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

### -License
Specifies an array of features for which the job requires licenses, and the number of licenses required for each.
Use a format of license_name1:number1,license_name2:number2,license_name3:number3,...
for this list, for example, `License1:10,License2:20,License3:12`.
Each number can be any positive integer, or asterisk, which requests a number of licenses that is based on the number of cores, sockets, or nodes assigned to the job.
The list has a maximum length of 160 characters.

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

### -MaxCoresPerNode
Specifies the maximum number of cores that a node can have for the job scheduler to consider the node as a candidate node on which to run the job.
The job will not run on a node that has more cores than the value that this parameter specifies.
If all of the nodes in the cluster have more cores than the value you specify for this parameter, an error occurs when you submit the job.

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

### -MaxMemoryPerNode
Specifies the maximum amount of memory in megabytes (MB) that a node can have for the job scheduler to consider the node as a candidate node on which to run the job.
The job will not run on a node that has more memory than the value that this parameter specifies.
If all of the nodes in the cluster have more memory than the amount you specify for this parameter, an error occurs when you submit the job.

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

### -MinCoresPerNode
Specifies the minimum number of cores that a node can have for the job scheduler to consider the node as a candidate node on which to run the job.
The job will not run on a node that has fewer cores than the value that this parameter specifies.
If all of the nodes in the cluster have fewer cores than the value you specify for this parameter, an error occurs when you submit the job.

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

### -MinMemoryPerNode
Specifies the minimum amount of memory in megabytes (MB) that a node can have for the job scheduler to consider the node as a candidate node on which to run the job.
The job will not run on a node that has less memory than the value that this parameter specifies.
If all of the nodes in the cluster have less memory than the amount you specify for this parameter, an error occurs when you submit the job.

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

### -Name
Specifies a name to use for this job in command output and in the user interface.
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

### -NodeGroupOp
Specifies the operator for the NodeGroups list.
Valid operators are:

- Intersect (the default).
  Creates a list of nodes that belong to all of the specified node groups
- Uniform.
  Creates a list of nodes that belong to only one of the specified node groups.
  The groups are tested in the order listed to identify a group that has sufficient resources to run the job.
  If enough resources are not found in a single group, the job remains queued.
- Union.
  Creates a list of nodes that belong to any of the specified node groups

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

```yaml
Type: JobNodeGroupOp
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeGroups
Specifies an array of node groups on which this job can run.
The job scheduler allocates resources to the job from nodes that belong to all of the node groups in the list by default, or to the nodes resulting from the operation of NodeGroupOp, if specified, on the list of groups.

If you specify values for both the *NodeGroups* and *RequestedNodes* parameters, the job runs only on the nodes in the list of nodes for the *RequestedNodes* parameter that also belong to all of the node groups in the list of node groups for the *NodeGroups* parameter (or to the nodes in *NodeGroups* that result from the operation of the *NodeGroupOp* parameter, if specified).

This parameter was named *Nodegroup* prior to HPC Pack 2008 R2.

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

### -NotifyOnCompletion
Indicates whether the HPC job scheduler service should send an email notification when the job ends.
A nonzero value or $True indicates that the HPC job scheduler service should send an email notification when then job ends.
A value of 0 or $False indicates that the HPC job scheduler service should not send an email notification when the job ends.
A job ends and the notification is sent when the state of the job changes to Finished, Failed, or Canceled.

A cluster administrator must configure notification for the HPC cluster before you can receive an email notification about a job.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

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

### -NotifyOnStart
Specifies whether the HPC job scheduler service should send an email notification when then job starts.
A nonzero value or $True indicates that the HPC job scheduler service should send an email notification when then job starts.
A value of 0 or $False indicates that the HPC job scheduler service should not send an email notification when then job starts.

A cluster administrator must configure notification for the HPC cluster before you can receive an email notification about a job.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

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

### -NumCores
Specifies the overall number of cores across the HPC cluster that the job requires, in the format \[minimum-\]maximum.
The job runs on at least the minimum number of cores and on no more than the maximum.
If you specify only one value, this cmdlet sets both the minimum and maximum number of cores to that value.
If you specify a minimum value that exceeds the total number of cores available across the cluster, an error occurs when you submit the job.

The minimum and maximum values can only be positive integers or an asterisk.
If you specify the minimum or maximum value as an asterisk, the scheduler automatically calculates the minimum or maximum number of cores at run time, based on the minimum and maximum number of cores for the tasks in the job.

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
Specifies the overall number of nodes across the HPC cluster that the job requires, in the format \[minimum-\]maximum.
The job runs on at least the minimum number of nodes and on no more than the maximum.
If you specify only one value, this cmdlet sets the minimum and maximum number of nodes to that value.
If you specify a minimum value that exceeds the total number of nodes available across the cluster, an error occurs when you submit the job.

The minimum and maximum values can only be positive integers or an asterisk.
If you specify the minimum or maximum value as an asterisk, the scheduler automatically calculates the minimum or maximum number of nodes at run time, based on the minimum and maximum number of nodes for the tasks in the job.

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
Specifies the overall number of sockets across the HPC cluster that the job requires, in the format \[minimum-\]maximum.
The job runs on at least the minimum number of sockets and on no more than the maximum.
If you specify only one value, this cmdlet sets the minimum and maximum number of sockets to that value.
If you specify a minimum value that exceeds the total number of sockets available across the cluster, an error occurs when you submit the job.

The minimum and maximum values can only be positive integers or an asterisk.
If you specify the minimum or maximum value as an asterisk, the scheduler automatically calculates the minimum or maximum number of socket at run time, based on the minimum and maximum number of sockets for the tasks in the job.

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

### -OrderBy
Specifies the order that the job scheduler should use to allocate nodes to the job, in the format primary_order\[,secondary_order\].
The primary_order and secondary_order portions of the value can be one of the following values:

- Memory.
The job scheduler sorts the nodes by the amount of memory that they have available, and then first allocates the job to nodes with more memory.
- -Memory.
The job scheduler sorts the nodes by the amount of memory that they have available, and then first allocates the job to nodes with less memory.
- Cores.
The job scheduler sorts the nodes by the number of cores that they have available, and then first allocates the job to nodes with more cores.
- -Cores.
The job scheduler sorts the nodes by the number of cores that they have available, and then first allocates the job to nodes with fewer cores.

When you specify a secondary order, the job scheduler sorts the nodes according to the primary order first.
For subsets of nodes that have the same amount of the resource that the primary order specifies, the job scheduler then sorts the nodes within the subset by using the secondary sort order.
For example, if you specify `memory,-cores`, the job scheduler sorts the nodes from the highest amount of memory to the lowest.
For subsets of nodes that have the same amount of memory, the job scheduler uses the number of cores to specify the order, and it sorts the nodes that have the same amount of memory from the fewest number of cores to the most.

The primary order and secondary order must refer to different types of resources.
For example, `memory,-cores` is a valid combination of primary and secondary sort orders.
Combinations such as `memory,-memory` and `-cores,-cores` are not valid.

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

### -ParentJobIds
Specifies an array of job IDs the job depends on.
The HPC job scheduler service will schedule the job only when its parent jobs have completed and are all in a Finished state.
If any parent job has not completed or has completed but is in a Canceled or Failed state, the job remains queued.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies the priority for scheduling the job on a scale from 0 to 4000, with 0 as the lowest priority and 4000 as the highest.
In addition to specifying the priority as a number between 0 and 4000, you can specify one of the following named priority values:

- Highest
- AboveNormal
- Normal
- BelowNormal
- Lowest

These named priority values correspond to numeric priorities of 4000, 3000, 2000, 1000, and 0, respectively.

You can also specify the priority as \<named_value\>+\<offset\> or \<named_value\>-\<offset\>.
However, the priority value that results when the numeric equivalent of the \<named_value\> is substituted for the \<named_value\> still must be a value between 0 and 4000.

The job template that the job uses specifies permissions that affect who can specify elevated priorities.

The job scheduler places jobs with the same priority into the job queue in the order that users submit the jobs, unless a user re-queues a job.
If a user re-queues a job, the job scheduler places that job first among the jobs with the same priority.

The values that are valid for this parameter have changed since nextref_hpcpack.

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

### -Progress
Specifies the percentage of the job that is complete.
This value must be between 0 and 100.

If you do not set the value of this property, the HPC job scheduler service calculates the progress based on the percentage of tasks that are complete for the job.
When you set this property for a job, the HPC job scheduler service does not continue to update this property, so you must continue to update the property.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

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

### -ProgressMessage
Specifies a custom status message that you want to display for the job.
The maximum length for this string is 80 characters.

This parameter was introduced in HPC Pack 2008 R2.
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

### -Project
Specifies a project name for the job that you can use for tracking jobs.
The maximum length for the project name is 80 characters.

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

### -RequestedNodes
Specifies an array of names for the nodes on which the job can run.
These nodes are candidates for the job, but not all of the nodes will necessarily run the job if the available resources on these nodes exceed the resources that the job requires.
The job scheduler allocates the top nodes according to the value of the *Orderby* parameter until the allocated nodes meet the value that you specified with the *NumCores*, *NumSockets*, or *NumNodes* parameter.

If you do not specify the *RequestedNodes* parameter, the job scheduler considers all nodes as candidates that the job scheduler can allocate to the job.

If you specify values for both the *RequestedNodes* and *NodeGroups* parameters, the job runs only on the nodes in the list of nodes for the *RequestedNodes* parameter that also belong to all of the node groups in the list of node groups for the *NodeGroups* parameter.

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

### -RunTime
Specifies the maximum amount of time the job should run.
After the job runs for this amount of time, the job scheduler cancels the job.

You specify the amount of time in a format of \[\[days:\]hours:\]minutes.
You can also specify "infinite" to indicate that the job can run for an unlimited amount of time.

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

### -RunUntilCanceled
Indicates whether the job continues to run and hold resources until the run-time limit expires or someone cancels the job.

A non-zero or $True value indicates that the job continues to run and hold resources until the run-time limit expires or someone cancels the job.
If you specify a non-zero or $True value, you must specify minimum and maximum values for the *NumCores*, *NumNodes*, or *NumSockets* parameter, or an error occurs when you submit the job.

A value of 0 or $False indicates that the job should stop and release its resources when all of the tasks in the job are complete.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster on which you want to create the job.
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

### -SingleNode
Indicates whether all resources such as cores or sockets are allocated on one node.

A non-zero value or $True indicates that the job scheduler should allocate all job resources on a single node.

A value of 0 or $False indicates that the job can allocate job resources across multiple nodes.

This parameter was introduced in HPC Pack 2012.
It is not available in previous versions.

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

### -TaskExecutionFailureRetryLimit
Specifies the maximum number of times a task in this job other than a node preparation or node release task will be automatically re-queued after an application execution failure occurs.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
It is not available in previous versions.

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

### -TemplateName
Specifies the name of the default template to use for the job.
The maximum length for the name of a job template is 80 characters.

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

### -ValidExitCodes
Specifies the exit codes to be used for checking whether tasks in the job successfully exit.
These codes apply to tasks that do not specify their own success exit codes.
You can specify discrete integers and integer ranges separated by commas.

You can use **min** and **max** on a range, representing the start or end.
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

### -NumGpus
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcJob

## OUTPUTS

### HpcJob

## NOTES
* Before the job scheduler can run the new job, you need to add tasks to the job by using the Add-HpcTask cmdlet, and then submit the job by using the Submit-HpcJob cmdlet.

## RELATED LINKS

[Add-HpcTask](./Add-HpcTask.md)

[Export-HpcJob](./Export-HpcJob.md)

[Get-HpcJob](./Get-HpcJob.md)

[Set-HpcJob](./Set-HpcJob.md)

[Stop-HpcJob](./Stop-HpcJob.md)

[Submit-HpcJob](./Submit-HpcJob.md)
