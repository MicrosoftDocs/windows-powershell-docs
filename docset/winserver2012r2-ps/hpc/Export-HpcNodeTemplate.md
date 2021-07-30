---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/export-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HpcNodeTemplate
---

# Export-HpcNodeTemplate

## SYNOPSIS
Creates an XML-based representation of a node template and stores it in a file.

## SYNTAX

### Name
```
Export-HpcNodeTemplate [-Name] <String> -Path <String> [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

### Template
```
Export-HpcNodeTemplate  -Path <String> -Template <HpcNodeTemplate [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The Export-HpcNodeTemplate cmdlet creates an XML-based representation of a node template and stores it in a file.

## EXAMPLES

### Example 1: Export a node template to a specified file
```
PS C:\> Export-HpcNodeTemplate -Name "Default ComputeNode Template" -Path C:\MyNodeTemplates\DefaultNodeTemplate.xml
```

This command exports the default node template for compute nodes to the XML file located at C:\MyNodeTemplates\DefaultNodeTemplate.xml.

### Example 2: Get a node template and export it
```
PS C:\> Get-HpcNodeTemplate -Name MyNodeTemplate | Export-HpcNodeTemplate -Path C:\MyNodeTemplates\MyNodeTemplate.xml -Force
```

This command gets the HpcNodeTemplate object for the node template named MyNodeTemplate, and then exports that node template to the XML file located at C:\MyNodeTemplates\MyNodeTemplate.xml. If the file already exists, this example overwrites the file.

## PARAMETERS

### -Force
Indicates that this operation replaces the node template file if it already exists, without prompting the user.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: None

Required: False
Position: Named
Default value: Not Applicable
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the node template that you want to export.
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

### -Path
Specifies a name for the XML file to which you want to export the job template, including the full or relative path to the file if the **Export-HpcNodeTemplate** cmdlet should not save the file in the current directory.

This cmdlet creates any directories that do not already exist in the path.
If the file already exists and you do not specify the *Force* parameter, the cmdlet prompts you to confirm whether you want to replace the file.

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
Specifies the **HpcNodeTemplate** object for the node template that you want to export. Use the **Get-HpcNodeTemplate** cmdlet to get the HpcNodeTemplate object for a node template.
You cannot specify both the *Name* and *Template* parameters.

```yaml
Type: HpcNodeTemplate
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

### HpcNodeTemplate

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)

[Get-HpcNodeTemplate](./Get-HpcNodeTemplate.md)

[Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)

[New-HpcNodeTemplate](./New-HpcNodeTemplate.md)

[Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate .md)
