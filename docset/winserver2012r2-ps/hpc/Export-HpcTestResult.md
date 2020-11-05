---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Export-HpcTestResult
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

# Export-HpcTestResult

## SYNOPSIS
Exports the test results for the specified diagnostic test run to the specified directory.

## SYNTAX

### RunId (Default)
```
Export-HpcTestResult [-RunId] <Int32> [-Path <String>] [-Force][-Scheduler <String[]>] [<CommonParameters>]
```

### RunObject
```
Export-HpcTestResult -Run <HpcTestResult> [-Path <String>] [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-HpcTestResult** cmdlet exports the test results for the specified diagnostic test run to the specified directory.
You can specify the diagnostic test run for which you want to export the test results by specifying the identifier for the test run or the **HpcTestResult** object for the test run.

The test results can consist of several files, including a Poststep.result file that concatenates the standard output and standard error streams from all of the nodes in the diagnostic test; a PostStepResult.xml file that contains the results of the diagnostic test, which is structured according to the Diagnostic Test Step Result XML Schema; and a Report.html file that contains the results of the diagnostic test that is formatted as an HTML page that HPC Cluster Manager displays on the Result tab for the test results.

## EXAMPLES

### Example 1: Export test results by ID
```
PS C:\>Export-HpcTestResult -RunId 9 -Path "C:\TestResults\Run9"
```

This command exports the test results of the test run with an ID of 9 to the C:\TestResults\Run9 directory.

### Example 2: Export failed test results
```
PS C:\>Export-HpcTestResult -Run (Get-HpcTestResult -Alias "ping" -Result Failure | Select-Object -Last 1) -Path "C:\TestResults\LastPingTestFailure"
```

This command exports the test results for the last failed run of the ping test to the C:\TestResults\LastPingTestFailure directory.

## PARAMETERS

### -Force
This parameter is deprecated.
Use `-Confirm:$False` instead.

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
Specifies the directory to which you want to export the test results, including the full or relative path to the directory if the **Export-HpcTestResult** cmdlet should not save the test results in a subdirectory in the current directory.

This cmdlet creates directories that do not already exist in the path.
If the directory already exists and you do not specify the *Force* parameter, the cmdlet prompts you to confirm whether you want to replace the contents of the directory.

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

### -Run
Specifies the test run for which you want to export the results.
To get the HpcTestResult object for a test run, use the Get-HpcTestResult cmdlet.
You cannot specify both the *Run* and *RunId* parameters.

This parameter was named *TestResult* prior to HPC Pack 2008 R2.

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
Specifies the identifier of the test run for which you want to export the results.
To view the test runs for the HPC cluster, use the Get-HpcTestResult cmdlet.
You cannot specify both the *RunId* and *Run* parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not supported in previous versions.

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
Specifies the host name or IP address of the head node for the cluster that includes the test results that you want to export.
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

### None

## NOTES
* The **Export-HpcTestResult** cmdlet can only export one set of test results at a time. If you get more than one test run when you run the Get-HpcTestResult cmdlet and then redirect the multiple **HpcTestResult** objects to the **Export-HpcTestResult** cmdlet, the **Export-HpcTestResult** cmdlet overwrites the test results files each time that the **Export-HpcTestResult** cmdlet processes a new **HpcTestResult** object.
* The **Export-HpcTestResult** cmdlet exports a Poststep.result file only when the PostStep phase of the diagnostic test sends text to standard output or standard error.
* Before HPC Pack 2008 R2, this cmdlet exported a single HTML file.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Get-HpcTestResult](./Get-HpcTestResult.md)

[Get-HpcTestResultDetail](./Get-HpcTestResultDetail.md)
