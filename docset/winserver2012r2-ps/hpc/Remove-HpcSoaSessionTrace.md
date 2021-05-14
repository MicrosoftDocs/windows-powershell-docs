---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/remove-hpcsoasessiontrace?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-HpcSoaSessionTrace
---

# Remove-HpcSoaSessionTrace

## SYNOPSIS
This cmdlet is deprecated and was removed in HPC Pack 2012. Removes the Windows Communication Foundation (WCF) log files that contain the traces for the specified service-oriented architecture (SOA) session from the compute nodes.

## SYNTAX

### ID
```
Remove-HpcSoaSessionTrace [-Id] <Int32> [-Scheduler <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

### Job
```
Remove-HpcSoaSessionTrace -Job <HpcJob> [-Scheduler <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcSoaSessionTrace** cmdlet removes the WCF log files that contain the traces for the specified SOA session from the compute nodes. You can specify the SOA session by specifying the identifier for the SOA session or by specifying the HpcJob object for the service job for the session. This cmdlet performs the same action that occurs when you click Delete Trace in the Job Management view in HPC Cluster Manager.

## EXAMPLES

### Example 1: Remove log files by ID
```
PS C:\> Remove-HpcSoaSessionTrace –Id 6
```
This command removes the WCF log files for the SOA session with a session ID of 6.

### Example 2: Get a job and remove the log files for it

```
PS C:\> Remove-HpcSoaSessionTrace –Id 6
```

This command deletes the credentials for the user with a user name of pfuller and a domain of CONTOSO from the cached credentials that are used to create SOA sessions.

### Example 3: Get jobs by state and list the jobs for which the log files would be removed

```
PS C:\> Get-HpcJob –State Finished | Remove-HpcSoaSessionTrace –Job -WhatIf
```
This command gets HpcJob objects for the jobs with a state of Finished, and then lists the jobs for which the Remove-HpcSoaSessionTrace cmdlet would remove the WCF log files if you ran the example without including the WhatIf parameter in the Remove-HpcSoaSessionTrace cmdlet.

## PARAMETERS

### -ID
Specifies the identifier of the SOA session for which you want to remove the log files. In HPC Pack 2008 R2, this session identifier was changed to the job identifier of the service job for the session. You cannot specify both the Id and Job parameters.

```yaml
Type: <Int32>
Parameter Sets: 1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the service job for the SOA session for which you want to remove the log files. Use the Get-HpcJob cmdlet to get the HpcJob object for the service job. You cannot specify both the Id and Job parameters.

```yaml
Type: <HpcJob>
Parameter Sets:
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node of the HPC cluster that ran the SOA session for which you want to remove the log files. The value must be a valid computer name or IP address. If you do not specify the Scheduler parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies. To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER <head_node_name>`

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: %CCP_SCHEDULER%
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

### HpcJob

### None

## OUTPUTS

### None

## NOTES
* The WCF log files for a session get created only if the event logging level for the SOA service is set to a value other than Off when the session starts. To set the event logging level for a SOA service in the Configuration view in HPC Cluster Manager, click Services in the navigation pane, click the name of the service, and then click Set Event Logging Level.

* This cmdlet removes the WCF log files in the %CCP_DATA%\SoaTrace folder on each node. It does not remove copies of the WCF log files that were saved to other locations by running the Export-HpcSoaSessionTrace cmdlet or by clicking Collect Trace in the Job Management view of HPC Cluster Manager.

* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify –Confirm:$False. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify –Confirm or –Confirm:$True.
* You must be a cluster administrator to run this cmdlet successfully.

This cmdlet is supported only for HPC Pack 2008 R2. It is deprecated and was removed in HPC Pack 2012.

## RELATED LINKS

[Export-HpcSoaSessionTrace](./Export-HpcSoaSessionTrace.md)

[Get-HpcJob](./Get-HpcJob.md)
