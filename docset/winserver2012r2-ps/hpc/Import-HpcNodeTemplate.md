---
author: Kateyanne
description: 
external help file: 
manager: dansimp
Module Name: HPC
ms.author: v-kaunu
ms.date: 12/20/2016
ms.prod: powershell
ms.reviewer: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/hpc/import-hpcnodetemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-HpcNodeTemplate
---

# Import-HpcNodeTemplate

## SYNOPSIS
Imports node template XML files.

## SYNTAX

```
Import-HpcNodeTemplate [-Path] <String[]> [-Force] [-Upgrade]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-HpcNodeTemplate** cmdlet imports one or more node template XML files, and then creates new node templates or overwrites existing node templates based on the information in the node template XML files.
The names of the node template XML files without the file extensions serve as the names of the node templates.

## EXAMPLES

### Example 1: Import a node template
```
PS C:\>Import-HpcNodeTemplate -Path "C:\MyNodeTemplate\Template1.xml"
```

This command imports the node template XML file located at C:\MyNodeTemplate\Template1.xml, and creates a node template named Template1 if a node template with that name does not exist already.

### Example 2: Import multiple node templates
```
PS C:\>Import-HpcNodeTemplate -Force -Path "C:\MyNodeTemplate\Template2.xml,C:\MyNodeTemplate\Template3.xml"
```

This command imports the node template XML files located at C:\MyNodeTemplate\Template2.xml and C:\MyNodeTemplate\Template3.xml, and creates node templates named Template2 and Template3.
If node templates with either of these names already exists, the **Import-HpcNodeTemplate** cmdlet overwrites the existing templates that have these names.

### Example 3: Import and upgrade a node template for use in HPC Pack 2008 R2
```
PS C:\>Import-HpcNodeTemplate -Path "C:\TemplatesForUpgrade\Template4.xml" -Upgrade
```

This command imports the node template XML file located at C:\TemplatesForUpgrade\Template4.xml and creates a node template named Template4.
If the file at C:\TemplatesForUpgrade\Template4.xml was created by using the Create Node Template Wizard in HPC Pack 2008 and then exported, this example also upgrades the node template for use in HPC Pack 2008 R2 before importing it to an HPC cluster.

## PARAMETERS

### -Force
Indicates that this operation replaces the existing node template that has a name that is the same as the name of the node template XML file without the file name extension, without prompting the user.

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

### -Path
Specifies an array of the names of XML files from which to import the node templates, including the relative or full paths if the files are not in the current directory.
The file names and paths must be valid.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to import the node templates.
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

### -Upgrade
Indicates that this operation upgrades node templates that were created by using the Create Node Template Wizard with a previous version of HPC Pack and then exported.
The cmdlet imports the upgraded template to an HPC cluster.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

When you specify the *Upgrade* parameter, the cmdlet fixes the task that installs HPC Pack so that the correct version of the .NET Framework is also installed.

This cmdlet cannot upgrade a customized node template that was not created with the Create Node Template Wizard.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Assign-HpcNodeTemplate](./Assign-HpcNodeTemplate.md)

[Copy-HpcNodeTemplate](./Copy-HpcNodeTemplate.md)

[Export-HpcNodeTemplate](./Export-HpcNodeTemplate.md)

[Get-HpcNodeTemplate](./Get-HpcNodeTemplate.md)

[New-HpcNodeTemplate](./New-HpcNodeTemplate.md)

[Remove-HpcNodeTemplate](./Remove-HpcNodeTemplate.md)
