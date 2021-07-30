---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpcjobtemplateacl?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcJobTemplateAcl
---

# Get-HpcJobTemplateAcl

## SYNOPSIS
Gets the ACL for a job template.

## SYNTAX

### profile (Default)
```
Get-HpcJobTemplateAcl -Template <HpcJobTemplate> [-Scheduler <String[]>]
 [<CommonParameters>]
```

### name
```
Get-HpcJobTemplateAcl [-Name] <String> [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcJobTemplate** cmdlet gets the access control list (ACL) for the specified job template.
You can specify the job template by name or as an **HpcJobTemplate** object.
After you get the ACL for the job template, you can apply the ACL to a different job template to copy permissions between templates.
You can also change the ACL by using the .NET application programming interfaces (APIs) and then apply the modified ACL to a job template.

## EXAMPLES

### Example 1: Get the ACL for the default job template
```
PS C:\>Get-HpcJobTemplateAcl -Name "Default"
```

This command gets the ACL for the default job template.

### Example 2: Get the ACL for a specified job template
```
PS C:\>Get-HpcJobTemplate -Name "MyTemplate" | Get-HpcJobTemplateAcl
```

This command gets the **HpcJobTemplate** object for a job template called MyTemplate, and then gets the ACL for that job template by redirecting the object to the **Get-HpcJobTemplateAcl** cmdlet.

## PARAMETERS

### -Name
Specifies the name of the job template for which you want to get the ACL.
The maximum length of the name is 50 characters.
You cannot specify both the *Name* and *Template* parameters.

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
Specifies the **HpcJobTemplate** object for the job template for which you want to get the ACL.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcJobTemplate

## OUTPUTS

### HpcJobTemplateSecurityDescriptor

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcJobTemplate](./Get-HpcJobTemplate.md)

[Set-HpcJobTemplateAcl](./Set-HpcJobTemplateAcl.md)
