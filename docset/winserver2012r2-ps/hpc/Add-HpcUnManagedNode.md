---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Add-HpcUnManagedNode
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-HpcUnManagedNode

## SYNOPSIS
Adds unmanaged compute resources to the cluster as a compute node.

## SYNTAX

### GroupName
``` Add-HpcUnManagedNode [-GroupName] <String> [-Memory <Int32>] [-Name <String>] [-Scheduler <String[]>] [-SubscribedCores <Int32>] [-SubscribedSockets <Int32>] [<CommonParameters>]
```

### Group
```
Add-HpcUnManagedNode Group <HpcGroup> [-Memory <Int32>] [-Name <String>] [-Scheduler <String[]>] [-SubscribedCores <Int32>] [-SubscribedSockets <Int32>]  [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcUnManagedNode** cmdlet adds unmanaged compute resources to the cluster as a compute node.
The HPC job scheduler service must be configured to use the unmanaged resources.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Group
Specifies the **HpcGroup** object for the node group to which the node is added.
You cannot specify both the *Group* and *GroupName* parameters.

```yaml
Type: HpcGroup
Parameter Sets: Group
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GroupName
Specifies the name of the node group to which the node is added.
You cannot specify both the *Group* and *GroupName* parameters.

```yaml
Type: String
Parameter Sets: GroupName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Memory
Specifies the amount of memory in megabytes (MB) that you want the HPC job scheduler service to use when it is allocating tasks to the node.

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
Specifies a name for the unmanaged node that you want to add to the cluster.

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
Specifies the host name or IP address of the head node for the cluster to which you add the node.
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

### -SubscribedCores
Specifies the number of cores that you want the HPC job scheduler service to use when it is allocating tasks to the node.
This value may be smaller than, or exceed the number of physical cores.
To clear this property, set the value to $Null.
If this value is $Null, the number of physical cores is used.

You should ensure that the number of subscribed cores is divisible by the number of subscribed sockets.
Therefore, each socket must have the same number of cores (for example 4 cores and 2 sockets are valid, but 10 cores and 4 sockets are not).

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

### -SubscribedSockets
Specifies the number of sockets that the HPC job scheduler service should use when it is allocating tasks to the node.
This value may be smaller than, or exceed the number of actual physical sockets.
To clear this property, set the value to $Null.

You should ensure that the number of subscribed cores is divisible by the number of subscribed sockets.
Therefore, each socket must have the same number of cores (for example 4 cores and 2 sockets are valid, but 10 cores and 4 sockets are not).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* This cmdlet was introduced in HPC Pack 2012 R2 Update 1. It is not supported in previous versions.

## RELATED LINKS
