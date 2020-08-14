---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: New-HpcGroup
description:
keywords: powershell, cmdlet
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
title: Add-HpcDriver
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# New-HpcGroup

## SYNOPSIS
Creates a node group.

## SYNTAX

```
New-HpcGroup [-Name] <String> [-Description <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-HpcGroup** cmdlet creates a node group with the specified name and description.

## EXAMPLES

### Example 1: Create a node group
```
PS C:\>New-HpcGroup -Name "NewNodeGroup"
```

This command creates a node group named NewNodeGroup.

### Example 2: Create a node group for a specified head node
```
PS C:\>New-HpcGroup -Name "AnotherNewNodeGroup" -Description "A new node group for my HPC cluster." -Scheduler "MyHeadNode"
```

Creates a new node group named AnotherNewNodeGroup on the HPC cluster that has a head node with the name MyHeadNode, and provides a description for the node group.

## PARAMETERS

### -Description
Specifies a description for the new node group.

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

### -Name
Specifies the name to use for the new node group.
The maximum length of the name is 64 characters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the new node group.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcGroup

## NOTES
* After you create a new node group, you can add nodes to the node group by using the Add-HpcGroup cmdlet. To change the name or description of the group after you create it, use the Set-HpcGroup cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcGroup](./Add-HpcGroup.md)

[Get-HpcGroup](./Get-HpcGroup.md)

[Remove-HpcGroup](./Remove-HpcGroup.md)

[Set-HpcGroup](./Set-HpcGroup.md)
