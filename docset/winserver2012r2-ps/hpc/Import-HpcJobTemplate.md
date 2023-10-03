---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/import-hpcjobtemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-HpcJobTemplate
---

# Import-HpcJobTemplate

## SYNOPSIS
Imports a job template from an XML file.

## SYNTAX

```
Import-HpcJobTemplate -Name <String> -Path <String> [-Force]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-HpcJobTemplate** cmdlet imports a job template from an XML file, and as a result creates a new job template or overwrites an existing job template.

## EXAMPLES

### Example 1: Import a job template by name
```
PS C:\>Import-HpcJobTemplate -Name "MyNewTemplate" -Path "C:\MyTemplates\MyNewTemplate.xml"
```

This command imports a new job template named MyNewTemplate from the file at C:\MyTemplates\MyNewTemplate.xml.

### Example 2: Replace an existing job template
```
PS C:\>Import-HpcJobTemplate -Name "MyExistingTemplate" -Path "C:\MyTemplates\MyExistingTemplate_revised.xml" -Force
```

Replaces an existing job template named MyExistingTemplate by importing the new job template settings from the file at C:\MyTemplates\MyExistingTemplate_revised.xml.

## PARAMETERS

### -Force
Replaces an existing template without prompting when the value of the Name parameter matches the name of an existing job template.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name for the imported job template.
The maximum length of the name is 50 characters.
The value can be any alphanumeric string that is less than the maximum length except "default", which is reserved for the default template.
The name can include spaces.
To specify a name that includes spaces, enclose the name in double quotation marks (").

This name overrides the value that the Name attribute of the JobTemplate element in the XML file specifies, if the names differ.

If this name matches the name of an existing job template and you do not specify the *Force* parameter, the **Import-HpcJobTemplate** cmdlet prompts you to confirm whether you want to replace the existing job template.

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

### -Path
Specifies the name of the XML file from which to import the job template, including the relative or full path if the file is not in the current directory.
The file name and path must be valid.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcJobTemplate

## NOTES
* If you do not save the **HpcJobTemplate** object that this cmdlet returns in a variable or redirect the object to another cmdlet, **Import-HpcJobTemplate** displays information about the job templates. This information includes the name and description for the job template and the dates and times in local time that the job template was created and last changed.

  Job templates are stored centrally on the head node.
When you import a new job template, administrators on the head node have full control, modify, and submit jobs permissions on the job template by default.
Local users on the head node have submit permissions on the job template.
For information about changing permissions on job templates, see the Get-HpcJobTemplateAcl and Set-HpcJobTemplateAcl cmdlets.

  Only administrators on the head node can add new job templates.

* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Remove-HpcJobTemplate](./Remove-HpcJobTemplate.md)
