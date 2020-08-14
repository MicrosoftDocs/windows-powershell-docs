---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Import-HpcNodeXml
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

# Import-HpcNodeXml

## SYNOPSIS
Imports nodes from the lists of nodes in one or more specified node XML files, and adds the nodes to the HPC cluster.

## SYNTAX

```
Import-HpcNodeXml [-Path] <String[]> [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-HpcNodeXml** cmdlet imports nodes from the lists of nodes in one or more specified node XML files, and adds the nodes to the HPC cluster.

## EXAMPLES

### Example 1: Import compute nodes
```
PS C:\>Import-HpcNodeXML -Path "C:\MyNodeXMLFiles\NewNodes.xml"
```

This command imports the compute nodes listed in the XML file located at C:\MyNodeXMLFiles\NewNodes.xml, and adds those nodes to the cluster.

## PARAMETERS

### -Path
Specifies an array of names for node XML files from which you want to import nodes, including the relative or full path if the files are not in the current directory.
The file name and path must be valid.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the compute nodes.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* The **Import-HpcNodeXML** cmdlet skips any nodes that are already part of the HPC cluster and have a known state. You can use this cmdlet to update properties of nodes that are in the unknown state. The **Import-HpcNodeXML** cmdlet corresponds to the process of adding compute nodes under Configuration in HPC Cluster Manager. The cmdlet provisions the nodes and leaves the nodes in the offline state after provisioning is complete. You can bring the nodes online by running the Set-HpcNodeState cmdlet or by using HPC Cluster Manager.
* For information about creating a node XML file that you can import, see Appendix 2: Creating a Node XML Filehttp://go.microsoft.com/fwlink/?LinkId=124145 (http://go.microsoft.com/fwlink/?LinkId=124145).
* The built-in ConfirmImpact setting for this cmdlet is High. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Export-HpcNodeXml](./Export-HpcNodeXml.md)

[Set-HpcNodeState](./Set-HpcNodeState.md)
