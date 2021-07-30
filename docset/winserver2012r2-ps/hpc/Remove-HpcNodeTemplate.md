---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcNodeTemplate
---

# Remove-HpcNodeTemplate

## SYNOPSIS
Deletes node templates from the HPC cluster.

## SYNTAX

### Name (Default)
```
Remove-HpcNodeTemplate [-Name] <String[]> [-Scheduler <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Template
```
Remove-HpcNodeTemplate -Template <HpcNodeTemplate[]> [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcNodeTemplate** cmdlet deletes one or more specified node templates from the HPC cluster.

## EXAMPLES

### Example 1: Remove a template by name
```
PS C:\>Remove-HpcNodeTemplate -Name "MyNodeTemplate"
```

This command deletes the node template named MyNodeTemplate.

### Example 2: Get node templates by name and remove them
```
PS C:\>Get-HpcNodeTemplate -Name "MyTemplate*" | Remove-HpcNodeTemplate -WhatIf
```

Gets the **HpcNodeTemplate** objects for the node templates that have names that begin with MyTemplate, and then describes what would happen if you redirected those objects to serve as input for the **Remove-HpcNodeTemplate** cmdlet.

## PARAMETERS

### -Name
Specifies an array of names of the node templates that you want to delete.
You cannot specify both the *Name* and *Template* parameters.

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

### -Template
Specifies an array of **HpcNodeTemplate** objects for the node templates that you want to delete.
Use the Get-HpcNodeTemplate cmdlet to get the **HpcNodeTemplate** objects for the node templates.
You cannot specify both the *Template* and *Name* parameters.

```yaml
Type: HpcNodeTemplate[]
Parameter Sets: Template
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcNodeTemplate[]

## OUTPUTS

### None

## NOTES
* You must remove any associations between a node template and all of the nodes in the HPC cluster before you can delete the node template. Use the Assign-HpcNodeTemplate cmdlet to assign a new node template to a node, thus removing the association between the node and the node template that was previously associated with the node.
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)

[Get-HpcNodeTemplate](./Get-HpcNodeTemplate.md)

[Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)

[New-HpcNodeTemplate](./New-HpcNodeTemplate.md)
