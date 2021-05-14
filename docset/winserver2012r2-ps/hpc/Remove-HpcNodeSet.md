---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcnodeset?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcNodeSet
---

# Remove-HpcNodeSet

## SYNOPSIS
Removes a set of Azure nodes from an HPC cluster.

## SYNTAX

```
Remove-HpcNodeSet -Template <HpcNodeTemplate> [-Force <Boolean>] [-Async <Boolean>] [-Comment <String>][-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcNodeSet** cmdlet removes the set of Azure nodes that are associated with the specified node template from an HPC cluster.

## EXAMPLES

### Example 1: Remove nodes from a node template
```
PS C:\>Get-HpcNodeTemplate -Name "MyWorkerNodeTemplate" | Remove-HpcNodeSet -Async $True
```

This command gets an **HpcNodeTemplate** object for the node template named MyWorkerNodeTemplate, and then removes all of the worker nodes that are associated with that node template from the HPC cluster and returns without waiting for the removal to take effect.

## PARAMETERS

### -Async
Indicates whether the cmdlet should return immediately without waiting for the node removal to take effect.

A nonzero or $True value specifies that the cmdlet should return immediately without waiting for the node removal to take effect.
A 0 or $False value specifies that the cmdlet should wait for the node removal to take effect before returning.

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
Specifies the reason that the set of nodes was removed.

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
Indicates whether the online nodes in the node set should be forced offline as part of the removal process, or should just be drained as part of the removal process.

A $True or nonzero value indicates that the online nodes in the node set should be forced offline as part of the removal process.
A $False or 0 value indicates that the online nodes in the node set should not be forced offline as part of the removal process, but should just be drained instead.

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
Specifies the host name or IP address of the head node for the cluster that includes the set of Azure nodes that you want to remove.
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
Specifies an **HpcNodeTemplate** object that corresponds to the node template that is associated with the set of Azure nodes that you want to remove from the HPC cluster.

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

### An HpcNodeTemplate object

## OUTPUTS

### None

## NOTES
* All of the Azure nodes that you add to an HPC cluster by using a specific node template define a set of nodes that are deployed and can be managed together in Azure when you start the nodes. This set includes nodes that you add later by using the same node template.
* Starting in HPC Pack 2012 R2, you can also remove one or more specified Azure nodes by using the Remove-HpcAzureNode cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 1 (SP1). It is not supported in previous versions.

## RELATED LINKS

[Add-HpcNodeSet](./Add-HpcNodeSet.md)

[Remove-HpcAzureNode](./Remove-HpcAzureNode.md)

[Start-HpcNodeSet](./Start-HpcNodeSet.md)

[Stop-HpcNodeSet](./Stop-HpcNodeSet.md)
