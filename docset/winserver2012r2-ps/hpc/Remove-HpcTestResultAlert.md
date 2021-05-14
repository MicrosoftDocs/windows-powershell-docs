---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpctestresultalert?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcTestResultAlert
---

# Remove-HpcTestResultAlert

## SYNOPSIS
Clears the alert icon for diagnostic test runs.

## SYNTAX

### RunId (Default)
```
Remove-HpcTestResultAlert [[-RunId] <Int32[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

### RunObject
```
Remove-HpcTestResultAlert [-Run <HpcTestResult[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcTestResultAlert** cmdlet clears the alert icon for specified diagnostic test runs, or for all diagnostic test runs if none are specified.
You can specify a test run by providing the ID of the test run or by providing an **HpcTestResult** object for the test run.

The alert icon appears for failed test runs in the list of test runs under Diagnostics in HPC Cluster Manager.
Alert icons also appear for the nodes on which the diagnostic test failed under Node Management in HPC Cluster Manager.
An alert icon for a node clears only when you clear the alert icons for all of the test runs that failed on that node.

## EXAMPLES

### Example 1: Remove all alerts
```
PS C:\>Remove-HpcTestResultAlert
```

This command clears the alerts for all diagnostic test runs.

### Example 2: Remove an alert by ID
```
PS C:\>Remove-HpcTestResultAlert -RunId 62
```

This command clears the alert for the diagnostic test run with an ID of 62.

### Example 3: Get filtered test results and remove them
```
PS C:\>Get-HpcTestResult -Alias "ping" -Result Failure | Remove-HpcTestResultAlert
```

This command gets the **HpcTestResult** objects for all runs of the Ping Test that failed, and it removes the alerts for those test runs by redirecting the **HpcTestResult** objects to the **Remove-HpcTestResultAlert** cmdlet.

### Example 4: Select a test result and remove it
```
PS C:\>Get-HpcTestResult -Alias "ad" -Result Failure | Select-Object -Last 1 | Remove-HpcTestResultAlert
```

This command gets the **HpcTestResult** object for the most recent run of the Domain Connectivity Test that failed, and it removes the alert for that test run by redirecting the **HpcTestResult** object to the **Remove-HpcTestResultAlert** cmdlet.

## PARAMETERS

### -Run
Specifies an array of test runs for which you want to clear the alerts.
Use the Get-HpcTestResult cmdlet to get the **HpcTestResult** object for a test run.

```yaml
Type: HpcTestResult[]
Parameter Sets: RunObject
Aliases: TestResult

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the HPC cluster that includes the diagnostic test runs for which you want to clear the alerts.
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

### -RunId
Specifies an array of test IDs for test runs for which you want to clear the alerts.
Use the Get-HpcTestResult cmdlet to view a list of test runs and their IDs.

```yaml
Type: Int32[]
Parameter Sets: RunId
Aliases: Id

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcTestResult[]

## OUTPUTS

### None

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Get-HpcTest](./Get-HpcTest.md)

[Get-HpcTestResult](./Get-HpcTestResult.md)
