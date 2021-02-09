---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcGroup
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

# Get-HpcGroup

## SYNOPSIS
Gets node groups.

## SYNTAX

### Name (Default)
```
Get-HpcGroup [[-Name] <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

### Id
```
Get-HpcGroup [-Id] <Int32[]> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcGroup** cmdlet gets one or more node groups, specified by the names or identifiers of the node groups.
If you do not specify a node group, **Get-HpcGroup** gets all of the node groups for the HPC cluster.

## EXAMPLES

### Example 1: Get all node groups in the cluster
```
PS C:\>Get-HpcGroup
```

This command gets information about all of the node groups in the HPC cluster.

### Example 2: Get a node group by name
```
PS C:\>Get-HpcGroup -Name "MyNodeGroup"
```

This command gets information about the node group named MyNodeGroup.

### Example 3: Get node groups by ID
```
PS C:\>Get-HpcGroup -Id 5,6
```

This command gets information about the node groups with node group identifiers of 5 and 6.

## PARAMETERS

### -Id
Specifies an array of node group IDs for the node groups that you want to get.
You cannot specify both the *Id* and *Name* parameters.

```yaml
Type: Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the node groups that you want to get.
You cannot specify both the *Name* and *Id* parameters.
The maximum length for the name of a node group is 64 characters.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the node groups.
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
This cmdlet returns one or more **HpcGroup** objects.

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcGroup](./Add-HpcGroup.md)

[New-HpcGroup](./New-HpcGroup.md)

[Remove-HpcGroup](./Remove-HpcGroup.md)

[Set-HpcGroup](./Set-HpcGroup.md)
