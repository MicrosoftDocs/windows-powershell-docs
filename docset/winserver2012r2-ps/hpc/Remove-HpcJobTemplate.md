---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/remove-hpcjobtemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcJobTemplate
---

# Remove-HpcJobTemplate

## SYNOPSIS
Deletes a job template.

## SYNTAX

### profile (Default)
```
Remove-HpcJobTemplate -Template <HpcJobTemplate> [-Scheduler <String[]>]
 [<CommonParameters>]
```

### name
```
Remove-HpcJobTemplate [-Name] <String>  [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcJobTemplate** cmdlet deletes a job template from the specified cluster.
You can specify the job template that you want to delete either by name or by passing an **HpcJobTemplate** object to the **Remove-JobTemplate** cmdlet.

## EXAMPLES

### Example 1: Remove a template
```
PS C:\>Remove-HpcJobTemplate -Name "Template 2"
```

This command deletes the job template named Template 2.

### Example 2: Get a template and then remove it
```
PS C:\>Get-HpcJobTemplate -Name "MyExtraTemplate" | Remove-HpcJobTemplate
```

This command gets the **HpcJobTemplate** object for a job template called MyExtraTemplate, and then deletes that job template by redirecting the object to the **Remove-HpcJobTemplate** cmdlet.

## PARAMETERS

### -Name
Specifies the name of the job template that you want to delete.
You cannot specify both the *Name* and *Template* parameters.
The maximum length of the name of the job template is 50 characters.

```yaml
Type: String
Parameter Sets: name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the job templates.
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
Specifies the **HpcJobTemplate** object for the job template you want to delete.
You cannot specify both the *Name* and *Template* parameters.
Use the Get-HpcJobTemplate cmdlet to get an **HpcJobTemplate** object for the job template.

```yaml
Type: HpcJobTemplate
Parameter Sets: profile
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

### HpcJobTemplate

## OUTPUTS

### None

## NOTES
* You cannot delete the default job template. Only cluster administrators can delete job templates. If a job in the queued or running state uses the template, an error occurs and the cmdlet does not delete the template.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcJobTemplate](./Get-HpcJobTemplate.md)

[Import-HpcJobTemplate](./Import-HpcJobTemplate.md)
