---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Add-HpcNodeSet
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

# Add-HpcNodeSet

## SYNOPSIS
Adds a set of Azure nodes to the HPC cluster.

## SYNTAX

```
Add-HpcNodeSet -Template <HpcNodeTemplate> -Quantity <Int32> -Size <String>
[-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcNodeSet** cmdlet adds the specified number of Azure nodes with the specified virtual machine size to the HPC cluster by using the specified node template.

## EXAMPLES

### Example 1: Add nodes with a template: Add nodes with a template
```
PS C:\>Get-HpcNodeTemplate -Name "MyWorkerNodeTemplate" | Add-HpcNodeSet -Quantity 500 -Size "Large"
```

This command gets an **HpcNodeTemplate** object for the node template named MyWorkerNodeTemplate, and then adds 500 large worker nodes to the HPC cluster by using that node template.

## PARAMETERS

### -Quantity
Specifies the number of Azure nodes that you want to add to the HPC cluster.
You can specify a value from 1 through 1000.
Ensure that the number is within the quota of role instances in the Azure subscription.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add Azure nodes.
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

### -Size
Specifies a predefined virtual machine size of the Azure nodes that is supported in HPC Pack.
The size of the virtual machine determines characteristics such as the number of CPU cores, the memory capacity, and the local file system size of each node.

For more information, see Virtual Machine Sizes for Azurehttp://go.microsoft.com/fwlink/?LinkId=294911.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Template
Specifies an **HpcNodeTemplate** object that corresponds to the node template that you want to associate with the Azure nodes that you want to add to the HPC cluster.

The node template that you specify must be an Azure node template.
An error occurs if you specify a different type of node template.

```yaml
Type: HpcNodeTemplate
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNodeTemplate

## OUTPUTS

### HpcNode[]

## NOTES
* To add Azure nodes of different sizes, run this command separately for each size.
* All of the nodes that you add to an HPC cluster by using a specific Azure node template define a set of nodes that can be deployed and managed together in Azure when you start the nodes. This set includes nodes that you add later by using the same node template.
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1). It is not supported in previous versions.

## RELATED LINKS

[Remove-HpcNodeSet](./Remove-HpcNodeSet.md)

[Start-HpcNodeSet](./Start-HpcNodeSet.md)

[Stop-HpcNodeSet](./Stop-HpcNodeSet.md)

[Start-HpcAzureNode](./Start-HpcAzureNode.md)

[Stop-HpcAzureNode](./Stop-HpcAzureNode.md)
