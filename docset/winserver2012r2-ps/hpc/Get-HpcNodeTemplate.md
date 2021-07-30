---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcNodeTemplate
---

# Get-HpcNodeTemplate

## SYNOPSIS
Gets a node template for an HPC cluster.

## SYNTAX

```
Get-HpcNodeTemplate [[-Name] <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcNodeTemplate** cmdlet gets one or more specified node templates, or gets all of the node templates for an HPC cluster.
You can specify the node templates by name.
If you do not specify any node templates, the **Get-HpcNodeTemplate** cmdlet gets all of the node templates for the specified HPC cluster.

## EXAMPLES

### Example 1: Get all node templates for a head node
```
PS C:\>Get-HpcNodeTemplate -Scheduler MyHeadNode
```

This command gets all of the node templates for the HPC cluster with a head node named MyHeadNode.

### Example 2: Get a node template by name
```
PS C:\>Get-HpcNodeTemplate -Name MyNodeTemplate
```

This command gets the node template named MyNodeTemplate.

### Example 3: Get multiple node templates
```
PS C:\>Get-HpcNodeTemplate -Name "NodeTemplate01,NodeTemplate02"
```

This command gets the node templates named NodeTemplate01 and NodeTemplate02.

## PARAMETERS

### -Name
Specifies an array of the names of the node templates that you want to get.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the node templates.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcNodeTemplate[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)

[Export-HpcNodeTemplate](./Export-HpcNodeTemplate.md)

[Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)

[New-HpcNodeTemplate](./New-HpcNodeTemplate.md)

[Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate.md)
