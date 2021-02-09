---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Add-HpcTest
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-HpcTest

## SYNOPSIS
Adds custom diagnostic tests to the set of diagnostic tests that administrators can run on the HPC cluster.

## SYNTAX

```
Add-HpcTest [-File] <String> [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcTest** cmdlet adds the custom diagnostic tests that the specified XML file defines to the set of diagnostic tests that administrators can run on the HPC cluster.

For information about creating custom diagnostic tests, see Diagnostics Extensibility in Windows HPC Server 2008 R2 Step-by-Step Guidehttp://go.microsoft.com/fwlink/?LinkId=177604 (http://go.microsoft.com/fwlink/?LinkId=177604).

## EXAMPLES

### Example 1: Add a diagnostic test
```
PS C:\>Add-HpcTest -File "C:\DiagnosticTest\CustomSuite1.xml"
```

This command adds the diagnostic tests defined in the XML file at C:\DiagnosticTest\CustomSuite1.xml to the set of diagnostic tests for the HPC cluster.

## PARAMETERS

### -File
Specifies the name of the XML file that defines the diagnostic tests that you want to add to the cluster, including the relative or full path if the file is not in the current directory.
The file name and path must be valid.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the diagnostic tests.
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

### HpcTest[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Get-HpcTest](./Get-HpcTest.md)

[Get-HpcTestDetail](./Get-HpcTestDetail.md)

[Invoke-HpcTest](./Invoke-HpcTest.md)

[Remove-HpcTest](./Remove-HpcTest.md)
