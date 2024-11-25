---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/stop-hpcazurenode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-HpcAzureNode
---

# Stop-HpcAzureNode

## SYNOPSIS
Stops Azure nodes.

## SYNTAX

### Name
```
Stop-HpcAzureNode [-Force <Boolean>] [-Async <Boolean>] [-Comment <String>] [-Name] <String[]>
  [-Scheduler <String[]>] [<CommonParameters>]
```

### Node
```
Stop-HpcAzureNode [-Force <Boolean>] [-Async <Boolean>] [-Comment <String>] -Node <HpcNode[]>
  [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HpcAzureNode** cmdlet stops one or more Azure nodes.
When you stop the nodes, you remove the corresponding role instances in Azure and reset the state of the nodes to Not Deployed.

## EXAMPLES

### Example 1: Stop an Azure node by name
```
PS C:\>Stop-HpcAzureNode -Name "AzureCN-0117" -Async $True
```

This command stops the Azure node named AzureCN-0117 and returns without waiting for the node to stop.

### Example 2: Get Azure nodes by state and stop them
```
PS C:\>Get-HpcNode -GroupName "AzureNodes" -State Offline | Stop-HpcAzureNode
```

This command gets an **HpcNode** object for the Azure nodes that are in the Offline state, and then stops those Azure nodes.

## PARAMETERS

### -Async
Indicates whether the cmdlet should return immediately without waiting for the nodes to stop.

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
Specifies the reason that the nodes were stopped.

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
Indicates whether the online nodes in the specified nodes should be forced offline as part of the process to stop the nodes, or should just be drained as part of that process.

A $True or nonzero value indicates that the online nodes should be forced offline as part of the process to stop the nodes.
A $False or 0 value indicates that the online nodes should not be forced offline as part of that process, but should just be drained instead.

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
Specifies an array of names, separated by commas, of the nodes that you want to stop.
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
Specifies an array of **HpcNode** objects, separated by commas, for the nodes that you want to stop.
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
* Azure nodes that are started automatically by an availability policy that is configured in the node template cannot be stopped by this cmdlet.
* If all of the nodes in an Azure deployment from a node template are stopped, the deployment is deleted.
* If a problem exists with your Internet connection, the process of stopping the nodes can fail.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2012 R2. It is not supported in previous versions.

## RELATED LINKS

[Remove-HpcAzureNode](/powershell/module/hpcpack2016/remove-hpcazurenode?view=hpc16-ps)

[Start-HpcAzureNode](./Start-HpcAzureNode.md)

[Start-HpcNodeSet](./Start-HpcNodeSet.md)

[Stop-HpcNodeSet](./Stop-HpcNodeSet.md)
