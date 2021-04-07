---
author: Kateyanne
description: 
external help file: 
manager: dansimp
Module Name: HPC
ms.author: v-kaunu
ms.date: 12/20/2016
ms.prod: powershell
ms.reviewer: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcoperation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcOperation
---

# Get-HpcOperation

## SYNOPSIS
Gets an operation.

## SYNTAX

### ByNode (Default)
```
Get-HpcOperation [-Node <HpcNode[]>] [-NodeName <String[]>] [-State <ChangeState[]>] [-StartTime <DateTime>]
 [-EndTime <DateTime>] [-Name <String[]>] [-Definition <String[]>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### ById
```
Get-HpcOperation [[-Id] <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### ByWorkItem
```
Get-HpcOperation [-WorkItem <HpcWorkItem>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcOperation** cmdlet gets one or more specified operations, or gets the operations that meet the specified criteria.
If you do not redirect the **HpcOperation** objects that are the output of the **Get-HpcOperation** cmdlet to another cmdlet or save the objects to variables, the **Get-HpcOperation** cmdlet displays information about the operation such as the name, status, and last update time for the operation.

## EXAMPLES

### Example 1: Get all operations
```
PS C:\>Get-HpcOperation
```

This command gets all of the operations for the HPC cluster.

### Example 2: Get operations by node name
```
PS C:\>Get-HpcOperation -NodeName "ComputeNode01,ComputeNode02" -StartDate (Get-Date).AddDays(-1) -EndDate (Get-Date)
```

This command gets all of the operations that were performed on the nodes named ComputeNode01 and ComputeNode02 in the last day.

### Example 3: Get operations by state
```
PS C:\>Get-HpcOperation -Definition "Reimage Nodes" -State Failed,Reverted
```

This command gets all of the operations with the operation type named Reimage Nodes that have a state of Failed or Reverted.

### Example 4: Get operations by name
```
PS C:\>Get-HpcOperation -Name "Deleting metric MyMetric."
```

This command gets all of the operations named Deleting metric MyMetric.

## PARAMETERS

### -Definition
Specifies an array of operation types or definitions for the operations that you want to get.

Valid operation types are:

- Add Node To Group
- Add or Update Counter
- Archive Management Data
- Archive Scheduler Data
- Assign Template
- Bring Nodes Online
- Check Head Node Configuration
- Collect Usage Data
- Configuration Update
- Delete Operations
- Delete Template
- Discovery
- Edit Nodes
- Export Metrics
- Export Template
- Import Metrics
- Import Template
- Initialize Cluster
- Load Node Configuration
- Maintain Nodes
- Modify Groups
- Reboot Nodes
- Reimage Nodes
- Reject Nodes
- Remove Counters
- Remove Node From Group
- Remove Nodes
- Run Diagnostics
- Save Node Configuration
- Security Update
- Shutdown Nodes
- Start Nodes
- Take Nodes Offline
- Update Global Configuration
- Update Network
- Update Template

```yaml
Type: String[]
Parameter Sets: ByNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies a **DateTime** object or equivalent string that indicates the ending date and time of the period for which you want to get operations.
The period covers dates and times that are earlier than the value that the *EndTime* parameter specifies and later than the value that the *StartTime* parameter specifies.

```yaml
Type: DateTime
Parameter Sets: ByNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an array of globally unique identifiers (GUIDs) for the operations that you want to get.
If you specify the *Id* parameter, the only other parameters you can specify are the *Scheduler* parameter and the common parameters.

```yaml
Type: String[]
Parameter Sets: ById
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the operations that you want to get.

```yaml
Type: String[]
Parameter Sets: ByNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects for the nodes on which the operations that you want to get were performed.
Use the Get-HpcNode cmdlet to get **HpcNode** objects for the nodes.
You cannot specify both the *Node* and *NodeName* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: ByNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeName
Specifies an array of the names of nodes on which the operations that you want to get were performed.
You cannot specify both the *NodeName* and *Node* parameters.
This parameter is a filter parameter, so you do not receive an error for specifying a node the does not exist in the HPC cluster as long as you specify at least one node that does exist.

```yaml
Type: String[]
Parameter Sets: ByNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster on which the operations ran.
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

### -StartTime
Specifies a **DateTime** object or equivalent string that indicates the starting date and time of the period for which you want to get operations.
The period covers dates and times that are later than the value that the *StartTime* parameter specifies and earlier than the value that the *EndTime* parameter specifies.

```yaml
Type: DateTime
Parameter Sets: ByNode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies an array of states that currently apply to the operations that you want to get.
Valid values are:

- Archived
- Committed
- Executing
- Failed
- Reverted
- Editable
- Reverting
- FailedToExecute
- FailedToRevert
- Deleted

```yaml
Type: ChangeState[]
Parameter Sets: ByNode
Aliases:
Accepted values: Editable, Executing, Committed, Reverting, Reverted, FailedToExecute, FailedToRevert, Deleted, Archived

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkItem
Specifies the **HpcWorkItem** object that contains the operations that you want to get.
An **HpcWorkItem** object is a collection of operations.
The Assign-HpcNodeTemplate cmdlet returns an **HpcWorkItem** object when you specify the *Async* parameter for that cmdlet.

```yaml
Type: HpcWorkItem
Parameter Sets: ByWorkItem
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

### HpcNode[]

## OUTPUTS

### HpcOperation[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Get-HpcOperationLog](./Get-HpcOperationLog.md)

[Stop-HpcOperation](./Stop-HpcOperation.md)
