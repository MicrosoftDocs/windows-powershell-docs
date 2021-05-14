---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/copy-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-HpcNodeTemplate
---

# Copy-HpcNodeTemplate

## SYNOPSIS
Creates a node template by making a copy of an existing node template.

## SYNTAX

### Name (Default)
```
Copy-HpcNodeTemplate [-Name] <String> [-NewName <String>] [-Scheduler <String[]>] [<CommonParameters>]
```

### Template
```
Copy-HpcNodeTemplate -Template <HpcNodeTemplate> [-NewName <String>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-HpcNodeTemplate** cmdlet creates a node template by making a copy of an existing node template.

## EXAMPLES

### Example 1: Copy a node template
```
PS C:\>Copy-HpcNodeTemplate -Name "MyTemplate"
```

This command creates a node template as a copy of the existing node template named MyTemplate.
The new node template has a name of Copy of MyTemplate by default.

### Example 2: Copy a node template to a specified file
```
PS C:\>Copy-HpcNodeTemplate -Name "MyExistingTemplate" -NewName "MyNewTemplate"
```

This command creates a node template named MyNewTemplate as a copy of the existing node template named MyExistingTemplate.

### Example 3: Get a node template and make a copy of it
```
PS C:\>Get-HpcNodeTemplate -Name "MyExistingTemplate" | Copy-HpcNodeTemplate -NewName "MyNewTemplate"
```

This command gets an **HpcNodeTemplate** object for the node template named MyExistingTemplate, and then creates a new node template named MyNewTemplate as a copy of that existing node template.

## PARAMETERS

### -Name
Specifies the name of the existing node template that you want to copy.
You cannot specify both the *Name* and *Template* parameters.
Use the Get-HpcNodeTemplate cmdlet to view the names of existing node templates.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies a name for the new node template that the **Copy-HpcNodeTemplate** cmdlet creates.
If you do not specify a name for the new node template, the cmdlet uses "Copy of " followed by the name of the node template you want to copy as the name of new node template.
If a node template with that name already exists, the **Copy-HpcNodeTemplate** cmdlet tries the names Copy of \<original_template_name\> (2), Copy of \<original_template_name\> (3),...
until the cmdlet finds a name that no other node template uses.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the node template you want to copy.
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
Specifies an **HpcNodeTemplate** object for the node template that you want to copy.
Use the Get-HpcNodeTemplate cmdlet to get an **HpcNodeTemplate** object for a node template.
You cannot specify both the *Template* and *Name* parameters.

```yaml
Type: HpcNodeTemplate
Parameter Sets: Template
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

### HpcNodeTemplate

## OUTPUTS

### HpcNodeTemplate

## NOTES
* You can specify the node template that you want to copy by name or by using an **HpcNodeTemplate** object.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Export-HpcNodeTemplate](./Export-HpcNodeTemplate.md)

[Get-HpcNodeTemplate](./Get-HpcNodeTemplate.md)

[Import-HpcNodeTemplate](./Import-HpcNodeTemplate.md)

[New-HpcNodeTemplate](./New-HpcNodeTemplate.md)

[Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate.md)
