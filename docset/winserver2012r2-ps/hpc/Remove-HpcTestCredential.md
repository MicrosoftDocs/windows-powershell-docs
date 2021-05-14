---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpctestcredential?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcTestCredential
---

# Remove-HpcTestCredential

## SYNOPSIS
Clears the cached credentials that the HPC Diagnostics Service uses to run diagnostic tests.

## SYNTAX

```
Remove-HpcTestCredential [-Scheduler <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcTestCredential** cmdlet clears the cached credentials that the HPC Diagnostics Service uses to run diagnostic tests.
These credentials are used to run the clusrun commands that run each phase of the diagnostic test if the user does not specify credentials when running the test.

## EXAMPLES

### Example 1: Remove cached credentials
```
PS C:\>Remove-HpcTestCredential
```

This command clears the cached credentials that the HPC Diagnostics Service uses to run diagnostics tests.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which you want to clear the cached credentials that the HPC Diagnostics Service uses to run diagnostic tests.
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

### None

## OUTPUTS

### None

## NOTES
* You cannot delete installation credentials. You can only delete credentials for running diagnostic tests, submitting jobs, or creating SOA sessions.
* After you clear the cached credentials that the HPC Diagnostics Service uses to run diagnostic tests, the cluster administrator is prompted for credentials the next time the cluster administrator runs a diagnostic test and also is asked whether those credentials should be saved.
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Invoke-HpcTest](./Invoke-HpcTest.md)

[Remove-HpcJobCredential](./Remove-HpcJobCredential.md)

[Remove-HpcSoaCredential](./Remove-HpcSoaCredential.md)

[Set-HpcTestCredential](./Set-HpcTestCredential.md)
