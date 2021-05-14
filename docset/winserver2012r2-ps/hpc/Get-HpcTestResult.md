---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/get-hpctestresult?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcTestResult
---

# Get-HpcTestResult

## SYNOPSIS
Gets test runs.

## SYNTAX

### TestName (Default)
```
Get-HpcTestResult [[-Alias] <String>] [-Result <DiagnosticResult>] [-NeedReview <Boolean>]
 [-LastRunTime <DateTime>] [[-Company] <String>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### TestObject
```
Get-HpcTestResult -Test <HpcTestCase> [-Result <DiagnosticResult>] [-NeedReview <Boolean>]
 [-LastRunTime <DateTime>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcTestResult** cmdlet gets the test runs for the specified diagnostic test that meets the specified criteria.
You can use either the alias or an **HpcTestCase** object for a diagnostic test to specify it.

If you do not specify a diagnostic test but do specify other criteria, the cmdlet gets the test runs for all of the diagnostic tests that meet the specified criteria.
If you specify a diagnostic test without specifying other criteria, the cmdlet gets all of the test runs for the specified diagnostic test.
If you specify neither a diagnostic test nor any other criteria, the cmdlet gets all test runs for all diagnostic tests for the HPC cluster.

## EXAMPLES

### Example 1: Get all test runs
```
PS C:\>Get-HpcTestResult
```

This command gets all of the test runs for all diagnostic tests for the cluster.

### Example 2: Get all test runs by last run time
```
PS C:\>Get-HpcTestResult -Alias "ping" -Result Failure -LastRunTime "5/18/2010 12:00:00 AM"
```

This command gets all of the test runs for the Ping Test that ran after midnight on 5/18/2010 and failed.

### Example 3: Get a test case and get results for alerts
```
PS C:\>Get-HpcTest -Alias "dnstest" | Get-HpcTestResult -NeedReview $True
```

This command gets the **HpcTestCase** object for the DNS Test and redirects that object to the input of the **Get-HpcTestResult** cmdlet to get all test runs for the DNS Test that have alerts that have not been cleared.

## PARAMETERS

### -Alias
Specifies the alias of the diagnostic test for which you want to get test runs.
Use the Get-HpcTest cmdlet to see the diagnostic tests available for the cluster.
You cannot specify both the *Alias* and *Test* parameters.

In HPC Pack 2008 R2 this parameter replaced the *Name* parameter.

```yaml
Type: String
Parameter Sets: TestName
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Company
Specifies the company that created the diagnostic test for which you want to get test runs.
If you specify the *Company* parameter, you must also specify the *Alias* parameter.
Specify the company if your HPC cluster includes two diagnostic tests with the same alias from different companies and you only want test runs for one of the tests.
You cannot specify both the *Company* and *Test* parameters.

This parameter was introduced in HPC Pack 2008 R2.
It is not available in previous versions.

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

### -LastRunTime
Specifies a **DateTime** object or equivalent string for the date and time at or after which a user ran the diagnostic test that generated the test runs that you want to get.
You can use the Get-Date cmdlet to get a **DateTime** object.
If you specify the *LastRunTime* parameter, the **Get-HpcTestResult** cmdlet gets only the test results for diagnostic tests that ran at or after the specified date and time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeedReview
Indicates whether to get test runs that have an alert that has not been cleared.
A value of $True indicates that the cmdlet should get test runs that have an alert that has not been cleared.
A value of $False indicates that the cmdlet should get test runs that do not have an alert or for which the alert has been cleared.
To clear an alert for a test run, use the Remove-HpcTestResultAlert cmdlet.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Result
Specifies the type of result for which you want to get test runs.
The acceptable values for this parameter are:

- NoResult
- Success
- Warning
- Failure
- FailedToRun
- Complete
- Canceled

In HPC Pack 2008 R2 this parameter replaced the *TestState* parameter.

```yaml
Type: DiagnosticResult
Parameter Sets: (All)
Aliases: TestState
Accepted values: NoResult, Success, Warning, Failure, FailedToRun, Complete, Canceled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the diagnostic tests and test runs.
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
Specifies the **HpcTestCase** object for the diagnostic test for which you want to get test runs.
Use the Get-HpcTest cmdlet to get the **HpcTestCase** object for a diagnostic test.
You can either save that **HpcTestCase** object in a variable that you specify for the *Test* parameter, or redirect the output of a command or an expression that gets an **HpcTestCase** object to the **Get-HpcTestResult** cmdlet by using the object pipeline.

You cannot specify both the *Test* parameter and either the *Alias* or *Company* parameter.

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

### HpcTestResult[]

## NOTES
* The databases in the HPC cluster store information about test runs for only the number of days that the TtlCompletedJobs configuration parameter specifies, which is 5 by default. The **Get-HpcTestResult** cmdlet cannot get information about older test runs. To view the value of the TtlCompletedJobs configuration parameters, use the Get-HpcClusterProperty cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.
* The *FailedNode* and *Suite* parameters that this cmdlet had before HPC Pack 2008 R2 are no longer supported.

## RELATED LINKS

[Export-HpcTestResult](./Export-HpcTestResult.md)

[Get-HpcClusterProperty](./Get-HpcClusterProperty.md)

[Get-HpcTest](./Get-HpcTest.md)

[Get-HpcTestResultDetail](./Get-HpcTestResultDetail.md)

[Remove-HpcTestResultAlert](./Remove-HpcTestResultAlert.md)

[Stop-HpcTestResult](./Stop-HpcTestResult.md)
