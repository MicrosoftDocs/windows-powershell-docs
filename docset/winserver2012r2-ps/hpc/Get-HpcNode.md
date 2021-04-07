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
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcnode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcNode
---

# Get-HpcNode

## SYNOPSIS
Gets nodes in the HPC cluster.

## SYNTAX

```
Get-HpcNode [[-Name] <String[]>] [-GroupName <String[]>] [-Group <HpcGroup>] [-State <ClusterNodeState[]>]
 [-Health <NodeHealth[]>] [-HealthState <NodeHealthState[]>] [-TemplateName <String[]>] [-Location <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcNode** cmdlet gets one or more nodes in the HPC cluster that meet the specified criteria for name, group, location, node template, node health, or node state.

## EXAMPLES

### Example 1: Get nodes by template
```
PS C:\>Get-HpcNode -TemplateName "ApplicationA"
```

This command gets all compute nodes that use the node template named ApplicationA.
You can set up nodes to have a particular node template when you provision the nodes for a particular application.

### Example 2: Get nodes by health state
```
PS C:\>Get-HpcNode -HealthState OK
```

This command gets all healthy nodes.

### Example 3: Get nodes by state
```
PS C:\>Get-HpcNode -State Offline,Rejected
```

This command gets all of the nodes that have a state of Offline or Rejected.

### Example 4: Get nodes by location
```
PS C:\>Get-HpcNode -Location "\datacenter01"
```

This command gets all of the nodes that are located in data center 01, regardless of their rack or chassis locations.

## PARAMETERS

### -Group
Specifies the **HpcGroup** object for the node group that contains the nodes that you want to get.

```yaml
Type: HpcGroup
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GroupName
Specifies an array of names for the node groups that contain the nodes that you want to get.
The cmdlet gets nodes only once if they belong to multiple groups.

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

### -Health
Specifies an array of the health values for the nodes that you want to get.
The cmdlet gets the nodes that have a health value that matches any value on the list.
Valid values are:

- OK
- Unreachable
- OngoingOperation
- DiagnosticFailed
- ProvisioningFailed

```yaml
Type: NodeHealth[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies an array of locations for the nodes that you want to get.
A location is a string with a format of \\\<DataCenter\>\[\\\<Rack\>\[\\\<Chassis\>\]\].
The cmdlet gets the nodes that have a location that matches any location on the list.

The location must begin with a backslash (\\).
If you include the \<Rack\> or secondary location part of the string, you must also include the \<DataCenter\> or primary location.
If you include the \<Chassis\> or tertiary location part of the string, you must also specify the \<Rack\> or secondary location plus the \<DataCenter\> or primary location.
Each part of the string has a maximum length of 256 characters.

If you specify only the \<DataCenter\> or primary location part of the location, the cmdlet gets all of the nodes that have the specified \<DataCenter\> or primary location, regardless of their \<Rack\> or secondary location and \<Chassis\> or tertiary location values.
If you specify only the \<DataCenter\> or primary location and the \<Rack\> or secondary location, the cmdlet gets all of the nodes that have the specified \<DataCenter\> or primary location and the specified \<Rack\> or secondary location, regardless of their \<Chassis\> or tertiary location values.

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

### -HealthState
Specifies an array of node health values for the nodes that you want to get.
The cmdlet gets the nodes that have a node health values that matches any value in the list.
Valid values are:

- Error
- OK
- Transitional
- Unapproved
- Warning

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

```yaml
Type: NodeHealthState[]
Parameter Sets: (All)
Aliases:
Accepted values: Error, OK, Transitional, Unapproved, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the nodes that you want to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the nodes.
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
Specifies the states of the nodes that you want to get.
The state of a node reflects the deployment state of the node and whether or not an administrator wants the node to be available as a resource for cluster jobs.
The cmdlet gets the nodes that have a state that matches any value in the list.
The acceptable values for this parameter are:

- Unknown
- Provisioning
- Offline
- Starting
- Online
- Draining
- Rejected
- Removing
- NotDeployed
- Stopping

```yaml
Type: ClusterNodeState[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateName
Specifies an array of names for the node templates that are associated with the nodes that you want to get.

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

### HpcGroup

## OUTPUTS

### HpcNode[]

## NOTES
* The behavior of this parameter was changed in Windows HPC Pack 2008 R2 so that when you provision nodes from bare metal the nodes are not assigned to any node groups until provisioning is complete.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Remove-HpcNode](./Remove-HpcNode.md)

[Restart-HpcNode](./Restart-HpcNode.md)

[Set-HpcNode](./Set-HpcNode.md)

[Shutdown-HpcNode](./Shutdown-HpcNode.md)

[Start-HpcNode](./Start-HpcNode.md)
