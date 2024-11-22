---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/start-hpcazurenode?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-HpcAzureNode
---

# Start-HpcAzureNode

## SYNOPSIS
Starts Azure nodes.

## SYNTAX

### Name
```
Start-HpcAzureNode [-Async <Boolean>] [-Name] <String[]>
 [-Scheduler <String[]>] [<CommonParameters>]
```

### Node
```
Start-HpcAzureNode [-Async <Boolean>] -Node <HpcNode[]>
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-HpcAzureNode** cmdlet starts one or more Azure nodes.
Starting the nodes provisions the corresponding role instances in Azure.

## EXAMPLES

### Example 1: Start an Azure node by name
```
PS C:\>Start-HpcAzureNode -Name "AzureCN-0114" -Async $True
```

This command starts the Azure node named AzureCN-0114 and returns without waiting for the node to start.

### Example 2: Get Azure nodes by state and start them
```
PS C:\>Get-HpcNode -GroupName "AzureNodes" -State Not-Deployed | Start-HpcAzureNode
```

This command gets an **HpcNode** object for the Azure nodes that are in the Not-Deployed state, and then starts those Azure nodes.

## PARAMETERS

### -Async
Indicates whether the cmdlet should return immediately without waiting for the nodes to start.

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

### -Name
Specifies an array of names, separated by commas, of the nodes that you want to start.
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
Specifies an array of **HpcNode** objects, separated by commas, for the nodes that you want to start.
You cannot specify both the Node and Name parameters.

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
Specifies the host name or IP address of the head node for the cluster that includes the Azure nodes that you want to start.
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
* Azure nodes that are stopped automatically by an availability policy that is configured in the node template cannot be started by this cmdlet.
* If a problem exists with your Internet connection, the process of starting the nodes can fail.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2012 R2 Update 1. It is not supported in previous versions.

## RELATED LINKS

[Remove-HpcAzureNode](/powershell/module/hpcpack2016/remove-hpcazurenode?view=hpc16-ps)

[Start-HpcNodeSet](./Start-HpcNodeSet.md)

[Stop-HpcAzureNode](./Stop-HpcAzureNode.md)

[Stop-HpcNodeSet](./Stop-HpcNodeSet.md)
