---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/stop-hpcnodeset?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-HpcNodeSet
---

# Stop-HpcNodeSet

## SYNOPSIS
Stops a set of Azure nodes.

## SYNTAX

```
Stop-HpcNodeSet -Template <HpcNodeTemplate> [-Force <Boolean>] [-Async <Boolean>] [-Comment <String>]
  [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HpcNodeSet** cmdlet stops the set of Azure nodes that use the specified node template.
When you stop a set of nodes, you remove the set of role instances in Azure and reset the state of the nodes to Not Deployed.

## EXAMPLES

### Example 1: Stop Azure nodesAzure
```
PS C:\>Get-HpcNodeTemplate -Name "MyWorkerNodeTemplate" | Stop-HpcNodeSet -Async $True
```

This command gets an **HpcNodeTemplate** object for the node template named MyWorkerNodeTemplate, and then stops all of the worker nodes that are associated with that node template from the HPC cluster and returns without waiting for the nodes to stop.

## PARAMETERS

### -Async
Specifies whether the cmdlet should return immediately without waiting for the nodes to stop.

A nonzero or $True value specifies that the cmdlet should return immediately without waiting for the nodes to stop.
A 0 or $False value specifies that the cmdlet should wait for the nodes to stop before returning.

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

### -Comment
Specifies the reason that the set of nodes was stopped.

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

### -Force
Specifies whether the online nodes in the node set should be forced offline as part of the process to stop the nodes, or should just be drained as part of that process.

A $True or nonzero value indicates that the online nodes in the node set should be forced offline as part of the process to stop the nodes.
A $False or 0 value indicates that the online nodes in the node set should not be forced offline as part of that process, but should just be drained instead.

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
Specifies the host name or IP address of the head node for the cluster that includes the set of Azure nodes that you want to stop.
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

### -Template
Specifies an **HpcNodeTemplate** object that corresponds to the node template that is associated with the set of Azure nodes that you want to stop.

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

### None

## NOTES
* All of the Azure nodes that you add to an HPC cluster by using a specific node template define a set of nodes that are deployed and can be managed together in Azure when you start the nodes. This set includes nodes that you add later by using the same node template.
* Starting in hpcpack_r2_2012_2, you can also stop one or more specified Azure nodes by using the **Stop-HpcAzureNode** cmdlet.
* If a problem exists with your Internet connection or with the connection information for Azure in the specified node template, the process of stopping the nodes can fail.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1). It is not supported in previous versions.

## RELATED LINKS

[Add-HpcNodeSet](/powershell/module/hpcpack2016/add-hpciscsistoragearray?view=hpc16-ps)

[Remove-HpcNodeSet](/powershell/module/hpcpack2016/remove-hpcnodeset?view=hpc16-ps)

[Start-HpcNodeSet](./Start-HpcNodeSet.md)

[Stop-HpcAzureNode](./Stop-HpcAzureNode.md)
