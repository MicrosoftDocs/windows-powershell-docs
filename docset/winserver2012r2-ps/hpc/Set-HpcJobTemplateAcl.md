---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Set-HpcJobTemplateAcl
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-HpcJobTemplateAcl

## SYNOPSIS
Sets the ACL on a job template.

## SYNTAX

### profile (Default)
```
Set-HpcJobTemplateAcl -Template <HpcJobTemplate> -Acl <HpcJobTemplateSecurityDescriptor> [-Scheduler <String[]>] [<CommonParameters>]
```

### name
```
Set-HpcJobTemplateAcl [-Name] <String> -Acl <HpcJobTemplateSecurityDescriptor> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HpcJobTemplateAcl** cmdlet sets the access control list (ACL) on the specified job template.
You can get an ACL for another job template by using the Get-HpcJobTemplateAcl cmdlet and then set that ACL on another job template to copy permissions between job templates.
You can also modify the ACL before you apply it to another job template by using .NET application programming interfaces (APIs).

## EXAMPLES

### Example 1: Copy an ACL and set its name
```
PS C:\>Get-HpcJobTemplateAcl -Name "Default" | Set-HpcJobTemplateAcl -Name "Template 2"
```

This command copies the ACL from the default job template named Template 2.

## PARAMETERS

### -Acl
Specifies an **HpcJobTemplateSecurityDescriptor** object for the ACL that you want to set on the template.
Use the Get-HpcJobTemplateAcl cmdlet to get the **HpcJobTemplateSecurityDescriptor** object, and modify that object with .NET APIs if needed.

```yaml
Type: HpcJobTemplateSecurityDescriptor
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the job template on which you want to set the ACL.
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
Specifies the **HpcJobTemplate** object for the job template on which you want to set the ACL.
You cannot specify both the *Name* and *Template* parameters.
Use the Get-HpcJobTemplate cmdlet to get an **HpcJobTemplate** object for the job template.

```yaml
Type: HpcJobTemplate
Parameter Sets: profile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcJobTemplateSecurityDescriptor

## OUTPUTS

### None

## NOTES
* Only users who have permission to modify the job template can set permissions on the template.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcJobTemplate](./Get-HpcJobTemplate.md)

[Get-HpcJobTemplateAcl](./Get-HpcJobTemplateAcl.md)
