---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpctest?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcTest
---

# Get-HpcTest

## SYNOPSIS
Gets diagnostic tests for the HPC cluster.

## SYNTAX

```
Get-HpcTest [[-Alias] <String[]>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcTest** cmdlet gets one or more specified diagnostic tests, or gets all of the diagnostic tests for the HPC cluster if you do not specify any tests.
You can specify diagnostic tests by their aliases.

## EXAMPLES

### Example 1: Get all diagnostic tests
```
PS C:\>Get-HpcTest
```

This command gets all of the diagnostic tests for the HPC cluster.

### Example 2: Get diagnostic tests by alias
```
PS C:\>Get-HpcTest -Alias "ping,dnstest"
```

This command gets the ping and DNS tests.

### Example 3: Get filtered diagnostic tests
```
PS C:\>Get-HpcTest -Alias "svc*"
```

This command gets all of the diagnostic tests that have aliases that begin with the letters "svc."

## PARAMETERS

### -Alias
Specifies an array of aliases for the diagnostic tests that you want to get.

This parameter replaces the *Name* parameter that this cmdlet had in HPC Pack 2008.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the diagnostic tests.
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

### HpcTestCase[]

## NOTES
* This cmdlet gets information about or **HpcTestCase** objects for the diagnostic tests that you can run. To get the result of a diagnostic test run, use the Get-HpcTestResult cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.

## RELATED LINKS

[Add-HpcTest](./Add-HpcTest.md)

[Get-HpcTestResult](./Get-HpcTestResult.md)

[Invoke-HpcTest](./Invoke-HpcTest.md)

[Remove-HpcTest](./Remove-HpcTest.md)
