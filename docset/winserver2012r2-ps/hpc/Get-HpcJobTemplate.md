---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcJobTemplate
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

# Get-HpcJobTemplate

## SYNOPSIS
Gets information for one or more specified job templates, or for all job templates if none are specified.

## SYNTAX

```
Get-HpcJobTemplate [[-Name] <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcJobTemplate** cmdlet gets information for one or more specified job templates, or for all job templates if none are specified.

If you do not save the **HpcJobTemplate** object that this cmdlet returns in a variable or redirect the object to another cmdlet, **Get-HpcJobTemplate** displays information about the job templates.
This information includes the name and description for the job template and the dates and times in local time that the job template was created and last changed.

## EXAMPLES

### Example 1: Get the default job template
```
PS C:\>Get-HpcJobTemplate -Name Default
```

This command gets the default job template for the cluster.

## PARAMETERS

### -Name
Specifies an array of the names of job templates for which you want to get an **HpcJobTemplate** object or information.
To specify multiple job templates, separate the names with commas (,).
If you do not specify the *Name* parameter, the **Get-HpcJobTemplate** cmdlet gets **HpcJobTemplate** objects or information for all available job templates.

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

## RELATED LINKS

[Copy-HpcJobTemplate](./Copy-HpcJobTemplate.md)

[Import-HpcJobTemplate](./Import-HpcJobTemplate.md)

[Remove-HpcJobTemplate](./Remove-HpcJobTemplate.md)
