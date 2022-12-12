---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/remove-hpcazurenode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcAzureNode
---

# Remove-HpcAzureNode

## SYNOPSIS
Removes one or more Azure nodes from an HPC cluster.

## SYNTAX

### Name
```
Remove-HpcAzureNode [-Force <Boolean>] [-Async <Boolean>] [-Comment <String>] [-Name] <String[]> [-Scheduler <String[]>] [<CommonParameters>]
```

### Node
```
Remove-HpcAzureNode [-Force <Boolean>] [-Async <Boolean>] [-Comment <String>] -Node <HpcNode[]> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcAzureNode** cmdlet removes one or more Azure nodes from an HPC cluster.
When you remove the nodes from the cluster, you also remove the corresponding role instances in Azure.

## EXAMPLES

### Example 1: Remove nodes by group name
```
PS C:\>Get-HpcNode -GroupName "AzureNodes" | Remove-HpcAzureNode -Force $True
```

This command gets an **HpcNode** object for all the Azure nodes that are in the cluster, and then removes the nodes while forcing any online Azure nodes to be offline as part of the removal process.

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
Specifies the reason that the nodes were removed.

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
Indicates whether the online nodes in the specified nodes should be forced offline as part of the removal process, or should just be drained as part of the removal process.

A $True or nonzero value indicates that the online nodes should be forced offline as part of the removal process.
A $False or 0 value indicates that the online nodes should not be forced offline as part of the removal process, but should just be drained instead.

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

### -Name
Specifies an array of names, separated by commas, of the nodes that you want to remove.
You cannot specify both the *Name* and *Node* parameters.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
Specifies an array of **HpcNode** objects, separated by commas, for the nodes that you want to remove.
You cannot specify both the *Node* and *Name* parameters.

```yaml
Type: HpcNode[]
Parameter Sets: Node
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the Azure nodes that you want to stop.
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

### HpcNode[]

## OUTPUTS

### None

## NOTES
* Azure nodes that are started automatically by an availability policy that is configured in the node template cannot be removed by this cmdlet. You can use the Remove-HpcNodeSet cmdlet instead.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2012 R2. It is not supported in previous versions.

## RELATED LINKS

[Remove-HpcNodeSet](./Remove-HpcNodeSet.md)

[Start-HpcAzureNode](./Start-HpcAzureNode.md)

[Stop-HpcAzureNode](./Stop-HpcAzureNode.md)
