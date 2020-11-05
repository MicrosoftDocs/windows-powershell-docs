---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Set-HpcGroup
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

# Set-HpcGroup

## SYNOPSIS
Modifies the name or description of a node group.

## SYNTAX

### Group (Default)
```
Set-HpcGroup -Group <HpcGroup> [-Name <String>] [-Description <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### Id
```
Set-HpcGroup [-Id] <Int32> [-Name <String>] [-Description <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcGroup** cmdlet changes the name or description of the specified node group.

## EXAMPLES

### Example 1: Set the name of a node group
```
PS C:\>Set-HpcGroup -Id 37 -Name "RenamedGroup"
```

This command changes the name of the node group with an identifier of 37 to RenamedGroup.

### Example 2: Get a node group and set its name
```
PS C:\>Get-HpcGroup -Name "MyNdoeGruop" | Set-HpcGroup -Name "MyNodeGroup"
```

This command gets the **HpcGroup** object for a group named MyNdoeGruop and changes the name of the group to MyNodeGroup to fix the spelling error.

### Example 3: Get a node group and set its description
```
PS C:\>Get-HpcGroup -Name "RetiringNodeGroup" | Set-HpcGroup -Description "This node group has been retired."
```

This command gets the **HpcGroup** object for a group named RetiringNodeGroup and changes the description for the group to "This node group has been retired."

## PARAMETERS

### -Description
Specifies the new description to use for the group.

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

### -Group
Specifies the **HpcGroup** object for the node group for which you want to change the name or description.
Use the Get-HpcGroup cmdlet to get an **HpcGroup** object for a node group.

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

### -Id
Specifies the node group identifier for the node group for which you want to change the name or description.
Use the Get-HpcGroup cmdlet to get the node group identifiers for the nodes in the HPC cluster.

```yaml
Type: Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the new name to use for the node group.
The maximum length for the name of a node group is 64 characters.

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
Specifies the host name or IP address of the head node for the cluster that includes the node group.
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

### HpcGroup

## OUTPUTS

### HpcGroup

## NOTES
* If you do not specify either the *Description* or *Name* parameter, **Set-HpcGroup** behaves like the Get-HpcGroup cmdlet and just gets information about the specified node group, or gets an **HpcGroup** object for that node group.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcGroup](./Add-HpcGroup.md)

[Get-HpcGroup](./Get-HpcGroup.md)

[New-HpcGroup](./New-HpcGroup.md)

[Remove-HpcGroup](./Remove-HpcGroup.md)
