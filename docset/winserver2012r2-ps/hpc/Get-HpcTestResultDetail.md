---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcTestResultDetail
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

# Get-HpcTestResultDetail

## SYNOPSIS
Gets detailed information about the results of a run for a diagnostic test.

## SYNTAX

### RunId (Default)
```
Get-HpcTestResultDetail [-RunId] <Int32> [-Scheduler <String[]>]
 [<CommonParameters>]
```

### RunObject
```
Get-HpcTestResultDetail -Run <HpcTestResult> [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcTestResultDetail** cmdlet gets detailed information about the results of a specific run for a diagnostic test, including the start and end times for the test, the values specified for the parameters of the test, and the results of the test on each node in the test.

You can specify the test run for which you want to view detailed results by specifying the identifier of the test run or by specifying an **HpcTestResult** object for the run.
Use the Get-HpcTestResult cmdlet to get the identifier of the runs for a diagnostic test or to get the **HpcTestResult** object for a specific run.

## EXAMPLES

### Example 1: Get test result details by run ID
```
PS C:\>Get-HpcTestResultDetail -RunId 9
```

This command gets detailed information about the results of a test run with a test run identifier of 9.

### Example 2: Get test result details by result type
```
PS C:\>Get-HpcTestResult -Alias "ping" -Result Failure | Get-HpcTestResultDetail
```

This command gets **HpcTestResult** objects for the test runs of the Ping Test that has a result of Failure, and gets detailed information about those test runs by redirecting the **HpcTestResult** object to the input of the Get-HpcTestResultDetail cmdlet.

## PARAMETERS

### -Run
Specifies the test run for which you want to view information.
Use the Get-HpcTestResult cmdlet to get the **HpcTestResult** object for the test run.
You cannot specify both the *Run* and *RunId* parameters.

```yaml
Type: HpcTestResult
Parameter Sets: RunObject
Aliases: TestResult

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RunId
Specifies the run identifier to the test run for which you want to view information.
Use the Get-HpcTestResult cmdlet to view a list of test runs for the HPC cluster.
You cannot specify both the *RunId* and *Run* parameters.

```yaml
Type: Int32
Parameter Sets: RunId
Aliases: Id

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the HPC cluster on which the diagnostic test was run.
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

### HpcTestResult

## OUTPUTS

### HpcTestResultDetail

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Get-HpcTest](./Get-HpcTest.md)

[Get-HpcTestResult](./Get-HpcTestResult.md)
