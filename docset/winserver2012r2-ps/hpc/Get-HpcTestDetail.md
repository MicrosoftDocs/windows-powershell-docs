---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcTestDetail
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

# Get-HpcTestDetail

## SYNOPSIS
Gets detailed information about a diagnostic test.

## SYNTAX

### TestName (Default)
```
Get-HpcTestDetail [-Alias] <String> [[-Company] <String>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### TestObject
```
Get-HpcTestDetail -Test <HpcTestCase> [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcTestDetail** cmdlet gets detailed information about a specified diagnostic test, including the metadata, parameters, environment variables, and commands for the test.
You can specify the diagnostic test by using the alias for the test or by using an **HpcTestCase** object for the test.
To get an **HpcTestCase** object for a test, use the Get-HpcTest cmdlet.

## EXAMPLES

### Example 1: Get information about a test
```
PS C:\>Get-HpcTestDetail -Alias "ping"
```

This command gets detailed information about the Ping Test.

### Example 2: Get information about a test by company
```
PS C:\>Get-HpcTestDetail -Alias "diskspace" -Company "Contoso, Ltd"
```

This command gets detailed information about the diagnostic test with an alias of diskspace from the company named Contoso, Ltd.

### Example 3: Get a test case and get test details for it
```
PS C:\>Get-HpcTest -Alias "dnstest" | Get-HpcTestDetail
```

This command gets the **HpcTestCase** object for the DNS Test, and then gets detailed information about that test by redirecting that object to the input of the Get-HpcTestDetail cmdlet.

## PARAMETERS

### -Alias
Specifies the alias of the diagnostic test for which you want to get detailed information.
You cannot specify both the Alias and Test parameters.
To view a list of the diagnostic tests that are available on the HPC cluster, use the Get-HpcTest cmdlet.

```yaml
Type: String
Parameter Sets: TestName
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Company
Specifies the company that created the diagnostic test for which you want to view detailed information.
If you specify the *Company* parameter, you must also specify the *Alias* parameter.
Specify the company if your HPC cluster includes two diagnostic tests with the same alias from different companies and you only want information for one of the tests.
You cannot specify both the *Company* and *Test* parameters.

```yaml
Type: String
Parameter Sets: TestName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the HPC cluster that includes the diagnostic test for which you want to view information.
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

### -Test
Specifies the **HPCTestCase** object for the diagnostic test for which you want to view detailed information.
Use the Get-HpcTest cmdlet to get an **HPCTestCase** object for a diagnostic test.
You cannot specify the *Test* parameter if you also specify the *Alias* or *Company* parameters.

```yaml
Type: HpcTestCase
Parameter Sets: TestObject
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

### HpcTestCase

## OUTPUTS

### HpcTestCaseDetail

### HpcTestCase
Zero or more **HpcTestCase** objects.

### HpcVariable
Zero or more **HpcVariable** objects.

### HpcTestCaseStep
One to three **HpcTestCaseStep** objects.

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Add-HpcTest](./Add-HpcTest.md)

[Get-HpcTest](./Get-HpcTest.md)
