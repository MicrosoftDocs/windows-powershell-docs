---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/copy-hpcjobtemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-HpcJobTemplate
---

# Copy-HpcJobTemplate

## SYNOPSIS
Copies a job template.

## SYNTAX

### profile (Default)
```
Copy-HpcJobTemplate -NewName <String> -Template <HpcJobTemplate> [-Scheduler <String[]>] [<CommonParameters>]
```

### name
```
Copy-HpcJobTemplate [-Name] <String> -NewName <String> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-HpcJobTemplate** cmdlet creates a job template by copying an existing job template.
You can use the name of the existing job template or use an **HpcJobTemplate** object to specify the job template that you want to copy.

## EXAMPLES

### Example 1: Copy a template
```
PS C:\>Copy-HpcJobTemplate -Name "OriginalTemplate" -NewName "NewTemplate"
```

This command creates a job template named NewTemplate by copying the existing OriginalTemplate job template.

### Example 2: Get the default job template and copy it
```
PS C:\>Get-HpcJobTemplate -Name Default | Copy-HpcJobTemplate -NewName "NewTemplate2"
```

This command gets an **HpcJobTemplate** object for the Default job template, and then redirects that object to the **Copy-HpcJobTemplate** cmdlet to create a new job template called NewTemplate2 by copying the Default job template.

## PARAMETERS

### -Name
Specifies the name of the job the template that you want to copy.
The maximum length for the name is 50 characters.
You cannot specify both the *Name* and the *Template* parameters.

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

### -NewName
Specifies the name to use for the new job template.
The maximum length for the name is 50 characters.
The name can be any alphanumeric string that is less than the maximum length, except **Default**, which is reserved for the default template.
The name can include spaces.
To specify a name that includes spaces, enclose the name in double quotation marks (").

You cannot use the **Copy-HpcJobTemplate** cmdlet to overwrite an existing job template, so an error occurs if you specify the name of an existing job template for the *NewName* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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
Specifies an **HpcJobTemplate** object for the job template that you want to copy.
Use the Get-HpcJobTemplate cmdlet to get an **HpcJobTemplate** object for a job template.
You cannot specify both the *Template* and the *Name* parameters.

This parameter was introduced in Windows HPC Server 2008 R2 and is not supported in previous versions.

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
* To view the names of existing job templates that you might want to copy, run the Get-HpcJobTemplate cmdlet without specifying a value for the *Name* parameter.
* Only administrators on the head node can create new job templates.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcJobTemplate](./Get-HpcJobTemplate.md)

[Import-HpcJobTemplate](./Import-HpcJobTemplate.md)

[Remove-HpcJobTemplate](./Remove-HpcJobTemplate.md)
