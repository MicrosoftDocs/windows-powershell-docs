---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/stop-hpctestresult?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-HpcTestResult
---

# Stop-HpcTestResult

## SYNOPSIS
Cancels a diagnostic test if it is still running.

## SYNTAX

### RunId (Default)
```
Stop-HpcTestResult [-RunId] <Int32>  [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RunObject
```
Stop-HpcTestResult -Run <HpcTestResult>  [-Scheduler <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-HpcTestResult** cmdlet cancels the specified diagnostic test run if it is still running.
You can specify the test run ID or an **HpcTestResult** object for the diagnostic test to cancel it.
If the diagnostic test run is not running, an error occurs.

## EXAMPLES

### Example 1: Cancel a test by ID
```
PS C:\>Stop-HpcTestResult -RunId 6
```

This command cancels the diagnostic test run with an ID of 6.

### Example 2: Get a test result and cancel the test if the user confirms
```
PS C:\>Get-HpcTestResult -Alias "ping" | Select-Object -Last 1 | Stop-HpcTestResult -Confirm
```

This command gets the **HpcTestResult** object for the most recent run of the Ping Test and cancels that test run if the user confirms the cancellation when prompted.

## PARAMETERS

### -Run
Specifies the **HpcTestResult** object for the running diagnostic test that you want to cancel.
Use the Get-HpcTestResult cmdlet to get the **HpcTestResult** object for a running diagnostic test.
You cannot specify both the *Run* and *RunId* parameters.

This parameter was named *TestResult* in HPC Pack 2008.

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
Specifies the ID for the diagnostic test run that you want to cancel.
Use the Get-HpcTestResult cmdlet to see the diagnostic test runs for an HPC cluster.
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
Specifies the host name or IP address of the head node for the cluster on which the diagnostic test is running.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Export-HpcTestResult](/powershell/module/hpcpack2016/export-hpctestresult?view=hpc16-ps)

[Get-HpcTestResult](/powershell/module/hpcpack2016/get-hpctestresult?view=hpc16-ps)

[Invoke-HpcTest](/powershell/module/hpcpack2016/invoke-hpctest?view=hpc16-ps)
