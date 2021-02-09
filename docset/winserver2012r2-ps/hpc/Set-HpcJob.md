---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Set-HpcJob
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-HpcJob

## SYNOPSIS
Sets the properties of the specified job.

## SYNTAX

### id (Default)
```
Set-HpcJob [-Id] <Int32> [-NumNodes <String>] [-NumSockets <String>] [-NumCores <String>] [-NumGpus <String>]
 [-ParentJobIds <Int32[]>] [-CustomProperties <String[]>] [-RequestedNodes <String[]>] [-Exclusive <Boolean>]
 [-RunUntilCanceled <Boolean>] [-ValidExitCodes <String>] [-FailDependentTasks <Boolean>] [-Priority <String>]
 [-RunTime <String>] [-Project <String>] [-Name <String>] [-License <String[]>] [-TemplateName <String>]
 [-NodeGroups <String[]>] [-OrderBy <String[]>] [-FailOnTaskFailure <Boolean>] [-MinMemoryPerNode <Int32>]
 [-MaxMemoryPerNode <Int32>] [-MinCoresPerNode <Int32>] [-MaxCoresPerNode <Int32>] [-Progress <Int32>]
 [-ProgressMessage <String>] [-NotifyOnStart <Boolean>] [-NotifyOnCompletion <Boolean>]
 [-Credential <PSCredential>] [-EmailAddress <String>] [-Holduntil <DateTime>] [-NodeGroupOp <JobNodeGroupOp>]
 [-SingleNode <Boolean>] [-EstimatedProcessMemory <Int32>] [-TaskExecutionFailureRetryLimit <Int32>]
 [-JobEnv <String[]>] [-AddExcludedNodes <String[]>] [-RemoveExcludedNodes <String[]>] [-ClearExcludedNodes]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### job
```
Set-HpcJob -Job <HpcJob> [-NumNodes <String>] [-NumSockets <String>] [-NumCores <String>] [-NumGpus <String>]
 [-ParentJobIds <Int32[]>] [-CustomProperties <String[]>] [-RequestedNodes <String[]>] [-Exclusive <Boolean>]
 [-RunUntilCanceled <Boolean>] [-ValidExitCodes <String>] [-FailDependentTasks <Boolean>] [-Priority <String>]
 [-RunTime <String>] [-Project <String>] [-Name <String>] [-License <String[]>] [-TemplateName <String>]
 [-NodeGroups <String[]>] [-OrderBy <String[]>] [-FailOnTaskFailure <Boolean>] [-MinMemoryPerNode <Int32>]
 [-MaxMemoryPerNode <Int32>] [-MinCoresPerNode <Int32>] [-MaxCoresPerNode <Int32>] [-Progress <Int32>]
 [-ProgressMessage <String>] [-NotifyOnStart <Boolean>] [-NotifyOnCompletion <Boolean>]
 [-Credential <PSCredential>] [-EmailAddress <String>] [-Holduntil <DateTime>] [-NodeGroupOp <JobNodeGroupOp>]
 [-SingleNode <Boolean>] [-EstimatedProcessMemory <Int32>] [-TaskExecutionFailureRetryLimit <Int32>]
 [-JobEnv <String[]>] [-AddExcludedNodes <String[]>] [-RemoveExcludedNodes <String[]>] [-ClearExcludedNodes]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcJob** cmdlet sets the properties of the specified job for the specified cluster.

## EXAMPLES

### Example 1: Get a job by ID and set its properties
```
PS C:\>Get-HpcJob -Id 47 | Set-HpcJob -Template "Default" -Project "Cluster Testing" -RunTime 0:0:30
```

This command modifies the job with an identifier of 47, sets its template to the default template, sets its project name to "Cluster Testing," and sets its run time to 30 minutes.

### Example 2: Set a status message for a job
```
PS C:\>Set-HpcJob -Id 86 -Progress 50 -ProgressMessage "The job is halfway done."
```

This command sets the progress percentage for the job with an ID of 86 to 50, and sets an appropriate status message for the job.

### Example 3: Specify an environment variable for a job
```
PS C:\>Set-HpcJob -Id 28 -Priority "Normal-15" -JobEnv "TestVariable=true" -NodeGroups "NodeGroup3"
```

This command sets the priority of the job with an ID of 28 to Normal-15 (that is, 1985), specifies that the environment variable named TestVariable should be set to true in the context of that job, and specifies that the job can run only on nodes in the node group named NodeGroup3.

### Example 4: Set email notification for a job
```
PS C:\>Set-HpcJob -Id 39 -NotifyOnComplete $True -EmailAddress "pfuller@contoso.com"
```

This command specifies that you want to receive email when job 39 is finished, and specifies that the HPC job scheduler service should send the email to pfuller@contoso.com.

## PARAMETERS

### -AddExcludedNodes
Specifies an array of the names of the nodes that you want to add to the list of nodes on which the job should not run.

If you add a node to the list of nodes that should not be used for the job while the job is running on that node, the tasks in the job that are running on the node are canceled and then re-queued if the value for the IsRerunnable property for the task is true.

If a node is specified in the RequiredNodes property for any of the tasks in the job, an exception occurs if you also specify that node in the *AddExcludedNodes* parameter.

If you specify a set of nodes in the *AddExcludedNodes* parameter that would cause the set of available resources to become smaller than the minimum number of resources that the job requires, an exception occurs when you submit the job.
For example, if you have an HPC cluster than consists of three nodes, and you include two of them in the *AddExcludedNodes* parameter, that action makes only one node available, and an exception occurs when you submit the job if the job requires a minimum of two nodes.

If you specify the name of a node that does not currently belong to the HPC cluster, the cmdlet generates an exception.

If you add the same node twice to the list of nodes that should not be used for the job, the second time that you add the node has no effect.

You cannot specify the *AddExcludedNodes* parameter if you also specify the *ClearExcludedNodes* or *RemoveExcludedNodes* parameter.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

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

### -ClearExcludedNodes
Removes all of the nodes in the list of nodes that should not be used for the job from that list.
To remove a specific node from the list of nodes that should not be used for the job, use the *RemoveExcludedNodes* parameter.

You cannot specify the *ClearExcludedNodes* parameter if you also specify the *AddExcludedNodes* or *RemoveExcludedNodes* parameter.

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

### -Credential
Specifies a **PSCredential** object for the credentials that you want to use to run the job.
Use the Get-Credential cmdlet to get a **PSCredential** object.
If you do not specify this parameter, the cmdlet runs the jobs with the credentials that were used to submit the job.

```yaml
Type: PSCredential
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
It is not supported in previous versions.

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
You still must use the NotifyOnStart and/or *NotifyOnCompletion* parameter of the New-HpcJob or Set-HpcJob cmdlet to specify when you want to receive notifications about the job.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1).
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

### -EstimatedProcessMemory
Specifies the maximum amount of memory in megabytes (MB) that each process in this job is expected to consume.
The HPC job scheduler service only runs the job on nodes that have at least the amount of memory specified.

A value of 0 indicates that the HPC job scheduler service will not allocate the job to nodes based on the memory requirements of the job.

This parameter was introduced in HPC Pack 2012.
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

### -Exclusive
Specifies whether the job scheduler should ensure that no other job runs on the same node as this job while this job runs.

A non-zero value or $True indicates that the job scheduler should ensure that no other job runs on the same node as this job while this job runs.

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

### -FailDependentTasks
Specifies that if a task fails or is canceled, all dependent tasks will fail.

This parameter was introduced in HPC Pack 2012.
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

### -FailOnTaskFailure
Specifies whether the scheduler should stop the job and fail the entire job immediately when a task in the job fails.

A non-zero value or $True indicates that the scheduler should stop the job and fail the entire job immediately when a task in the job fails.

A value of 0 or $False indicates that the scheduler should continue running the remaining tasks in the job after any task in the job fails.

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

You can specify the date and time in any format that the .NET Framework can parse for the current operating system culture.
For information about how the .NET Framework parses date and time strings, see Parsing Date and Time Strings in the .NET Frameworkhttp://go.microsoft.com/fwlink/p/?LinkId=200188 (http://go.microsoft.com/fwlink/p/?LinkId=200188) in MSDN.
The time specified using *Holduntil* is converted internally to UTC, and does not reflect local Daylight Saving Time.

You can only specify the Holduntil parameter for a job that is not running or has not completed.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

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

### -Id
Specifies the ID of the job for which you want to change the properties.
You can use the *Id* parameter or the *Job* parameter, but not both parameters at the same time.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies an **HpcJob** object that represents a job for which you want to change the properties.
Use the Get-HpcJob cmdlet to get an **HpcJob** object for the job.
You can use the *Job* parameter or the *Id* parameter, but not both parameters at the same time.

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

### -JobEnv
Specifies an array of environment variables that you want to set in the context of the job and the values to which you want to set those environment variables.
Specify the environment variables and values as a list of strings that have a format of environment_variable_name=value; for example, `"MyVariable1=yes","MyVariable2=no"`.
To unset an environment variable in the context of a job, leave out the value part of the string; for example, `"MyVariable3="`.

If you set or unset an environment variable for a job, that environment variable is also set or unset for each task in the job unless you override that environment variable setting for the task by specifying a new setting with the Env parameter when you call the Add-HpcTask cmdlet.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

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

### -License
Specifies a list of features for which the job requires licenses, and the number of licenses required for each.
Use a format of license_name1:number1,license_name2:number2,license_name3:number3,...
for this list.
For example, License1:10,License2:20,License3:12.
Each number can be any positive integer, or asterisk (*), which will request a number of licenses that is based on the number of cores, sockets, or nodes assigned to the job.
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
It is not supported in previous versions.

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
The HPC job scheduler service only allocates resources to the job from nodes that belong to all of the node groups in the list.

If you specify values for both the *NodeGroups* and the *RequestedNodes* parameters, the job runs only on the nodes in the list of nodes for the *RequestedNodes* parameter that also belong to all of the node groups in the list of node groups for the *NodeGroups* parameter (or to the nodes in *NodeGroups* that result from the operation of the *NodeGroupOp* parameter, if specified).

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

### -NotifyOnStart
Indicates whether the HPC job scheduler service should send an email notification when then job ends.
A nonzero value or $True indicates that the HPC job scheduler service should send an email notification when then job ends.
A value of 0 or $False indicates that the HPC job scheduler service should not send an email notification when then job ends.
A job ends and notification is sent when the state of the job changes to Finished, Failed, or Canceled.

A cluster administrator must configure notification for the HPC cluster before you can receive an email notification about a job.

This parameter was introduced in HPC Pack 2008 R2.
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

### -NumCores
Specifies the overall number of cores across the HPC cluster that the job requires, in the format \[minimum-\]maximum.
The job runs on at least the minimum number of cores and on no more than the maximum.
If you specify only one value, this cmdlet sets the minimum and maximum number of cores to that value.
If you specify a minimum value that exceeds the total number of cores available across the cluster, an error occurs when you submit the job.

The minimum and maximum values can only be positive integers or an asterisk (*).
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

The minimum and maximum values can only be positive integers or an asterisk (*).
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

The minimum and maximum values can only be positive integers or an asterisk (*).
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
For subsets of nodes that have the same amount of the resource that the primary order specifies, the job scheduler sorts the nodes within the subset by using the secondary sort order.
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
Specifies the list of Job IDs that the new job will depend on.
The HPC job scheduler service will schedule the job only when its parent jobs have completed and are all in a Finished state.
If any parent job has not completed or has completed but is in a Canceled or Failed state, the job remains queued.

This parameter was introduced in HPC Pack 2012.
It is not supported in previous versions.

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

### -ProgressMessage
Specifies a custom status message that you want to display for the job.
The maximum length for this string is 80 characters.

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

### -RemoveExcludedNodes
Specifies the names of the nodes that you want to remove from the list of nodes on which the job should not run.
To remove all of the nodes on the list of nodes that should not be used for the job from that list, use the *ClearExcludedNodes* parameter.

If you specify a node that does not currently belong to the HPC cluster, an exception occurs.
If you specify a node that is part of the HPC cluster but is not part of the current list of nodes that should not be used for the job, the *RemoveExcludedNodes* parameter has no effect and no error occurs.

You cannot specify the *RemoveExcludedNodes* parameter if you also specify the *AddExcludedNodes* or *ClearExcludedNodes* parameter.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

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
Specifies the maximum amount of time that the job should run.
After the job runs for this amount of time, the job scheduler cancels the job.

You specify the amount of time in a format of \[\[days:\]hours:\]minutes.
You can also specify "infinite" to indicate that the job can run for an unlimited amount of time.

If you specify only one part of the days:hours:minutes format, the cmdlet interprets the specified value as the number of minutes.
For example, `12` indicates 12 minutes.
If you specify two parts of the format, the command interprets the left part as hours and the right part as minutes.
For example, `10:30` indicates 10 hours and 30 minutes.

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
Specifies the host name or IP address of the head node for the cluster that contains the job.
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
Indicates whether to allocate all resources, such as cores or sockets, on one node.

A non-zero value or $True indicates that the job scheduler should allocate all job resources on a single node.

A value of 0 or $False indicates that the job can allocate job resources across multiple nodes.

This parameter was introduced in HPC Pack 2012.
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

### -TaskExecutionFailureRetryLimit
Specifies the maximum number of times a task in this job other than a node preparation or node release task will be automatically re-queued after an application execution failure occurs.

This parameter was introduced in HPC Pack 2012 R2 Update 1.
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
These codes only apply to tasks that do not specify their own success exit codes.
You can specify discrete integers and integer ranges separated by commas.

You can use **min** and **max** on a range, representing the start or end.
For example, `0..max` represents nonnegative integers.

This parameter was introduced in HPC Pack 2012.
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

### -NumGpus
If you add a node to the list of nodes that should not be used for the job while the job is running on that node, the tasks in the job that are running on the node are canceled and then re-queued if the value for the IsRerunnable property for the task is true.

If a node is specified in the RequiredNodes property for any of the tasks in the job, an exception occurs if you also specify that node in the *AddExcludedNodes* parameter.

If you specify a set of nodes in the *AddExcludedNodes* parameter that would cause the set of available resources to become smaller than the minimum number of resources that the job requires, an exception occurs when you submit the job.
For example, if you have an HPC cluster than consists of three nodes, and you include two of them in the *AddExcludedNodes* parameter, that action makes only one node available, and an exception occurs when you submit the job if the job requires a minimum of two nodes.

If you specify the name of a node that does not currently belong to the HPC cluster, the cmdlet generates an exception.

If you add the same node twice to the list of nodes that should not be used for the job, the second time that you add the node has no effect.

You cannot specify the *AddExcludedNodes* parameter if you also specify the *ClearExcludedNodes* or *RemoveExcludedNodes* parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### An HpcJob object

## OUTPUTS

### HpcJob

## NOTES
* You cannot change the properties of a job in the finished state. For jobs in the running state, you can only change the following properties:

- Name
- Project
- RunTime
- RunUntilCanceled
- Priority
- AddExcludedNodes
- ClearExcludedNodes
- RemoveExcludedNodes
- NotifyOnCompletion
- Progress
- ProgressMessage
- JobEnv



* Forhpcpack_gen, you can end a job that is set to run until it is canceled by using the **Set-HpcJob** cmdlet to set the RunUntilCanceled property to false. For more information about how to end a job that is set to run until it is canceled, see End a Run Until Canceled Job as Finishedhttps://technet.microsoft.com/en-us/library/dd796374(v=ws.10).aspx (https://technet.microsoft.com/en-us/library/dd796374(v=ws.10).aspx) in the TechNet library.

  Starting in Windows HPC Server 2008 R2, you can end a job that is set to run until it is canceled and set the state of that job to Finished by specifying the State parameter when you run the Stop-HpcJob cmdlet.

## RELATED LINKS

[Export-HpcJob](./Export-HpcJob.md)

[Get-HpcJob](./Get-HpcJob.md)

[New-HpcJob](./New-HpcJob.md)

[Stop-HpcJob](./Stop-HpcJob.md)

[Submit-HpcJob](./Submit-HpcJob.md)
