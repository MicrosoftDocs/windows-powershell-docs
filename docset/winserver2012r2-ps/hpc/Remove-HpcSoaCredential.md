---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/remove-hpcsoacredential?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcSoaCredential
---

# Remove-HpcSoaCredential

## SYNOPSIS
Deletes the cached credentials for users that SOA clients use to create SOA sessions.

## SYNTAX

```
Remove-HpcSoaCredential [[-UserName] <String[]>] [-Azure] [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcSoaCredential** cmdlet deletes the cached credentials for one or more specified users that service-oriented architecture (SOA) clients use to create SOA sessions.
If you do not specify a user name, the cmdlet deletes the credential of the user who ran the cmdlet.

## EXAMPLES

### Example 1: Remove cached credentials for a user
```
PS C:\>Remove-HpcSOACredential -UserName "CONTOSO\pfuller"
```

This command deletes the credentials for the user with a user name of pfuller and a domain of CONTOSO from the cached credentials that are used to create SOA sessions.

## PARAMETERS

### -Azure
Indicates that the *Scheduler* parameter is the URL of an  Azure cloud service that is running the Azure HPC Scheduler.

This parameter was introduced in HPC Pack 2008 R2 with Service Pack 3.
It is not available in previous versions.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster for which the specified user can create SOA sessions.
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

### -UserName
Specifies an array of the names of users for whom you want to delete the cached credential.

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
* You cannot delete installation credentials, and you can only delete credentials for creating SOA sessions, submitting jobs, or running diagnostic tests.
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* This cmdlet was introduced in HPC Pack 2008 R2. It is not supported in previous versions.

## RELATED LINKS

[Remove-HpcJobCredential](./Remove-HpcJobCredential.md)

[Remove-HpcTestCredential](./Remove-HpcTestCredential.md)

[Set-HpcSoaCredential](./Set-HpcSoaCredential.md)
