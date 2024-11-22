---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/start-hpcnodeset?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-HpcNodeSet
---

# Start-HpcNodeSet

## SYNOPSIS
Starts a set of Azure nodes.

## SYNTAX

```
Start-HpcNodeSet -Template <HpcNodeTemplate> [-Async <Boolean>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-HpcNode** cmdlet starts the set of Azure nodes that use the specified node template.
When you start a set of nodes, you deploy a set of role instances for the nodes in Azure.

## EXAMPLES

### Example 1: Start Azure nodes
```
PS C:\>Get-HpcNodeTemplate -Name "MyWorkerNodeTemplate" | Start-HpcNodeSet -Async $True
```

This command gets an **HpcNodeTemplate** object for the node template named MyWorkerNodeTemplate, and then starts all of the nodes that are associated with that node template from the HPC cluster and returns without waiting for the nodes to start.

## PARAMETERS

### -Async
Specifies whether the cmdlet should return immediately without waiting for the nodes to start.

A nonzero or $True value specifies that the cmdlet should return immediately without waiting for the nodes to start.
A 0 or $False value specifies that the cmdlet should wait for the nodes to start before returning.

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
Specifies the host name or IP address of the head node for the cluster that includes the set of Azure nodes that you want to start.
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
Specifies an **HpcNodeTemplate** object that corresponds to the node template that is associated with the set of Azure nodes that you want to start.

The node template that you specify must be a Azure node template.
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
* All of the nodes that you add to an HPC cluster by using a specific node template define a set of nodes that are deployed and can be managed together in Azure when you start the nodes. This set includes nodes that you add later by using the same node template. You can start the entire set of nodes, but not individual nodes.
* The deployment of role instances in Azure can take several minutes if you start a large number of nodes.
* If a problem exists with your Internet connection or with the connection information for Azure in the specified node template, the deployment of the nodes can fail.
* When you start a set of nodes, additional proxy role instances are configured in Azure to facilitate communication between HPC Cluster Manager and the nodes. Starting in HPC Pack 2012, the number of proxy nodes can be configured in the Azure node template. These proxy instances appear in the Azure Management Portal, incur charges in Azure, and count toward the quota for role instances in the Azure subscription.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1). It is not supported in previous versions.

## RELATED LINKS

[Add-HpcNodeSet](/powershell/module/hpcpack2016/add-hpcnodeset?view=hpc16-ps)

[Remove-HpcNodeSet](/powershell/module/hpcpack2016/remove-hpcnodeset?view=hpc16-ps)

[Start-HpcAzureNode](./Start-HpcAzureNode.md)

[Stop-HpcNodeSet](./Stop-HpcNodeSet.md)
