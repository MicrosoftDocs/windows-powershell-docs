---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/submit-hpcjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Submit-HpcJob
---

# Submit-HpcJob

## SYNOPSIS
Submits or re-queues jobs to the HPC cluster.

## SYNTAX

### job (Default)
```
Submit-HpcJob -Job <HpcJob[]> [-Credential <PSCredential>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

### id
```
Submit-HpcJob [-Id] <Int32[]> [-Credential <PSCredential>]
 [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Submit-HpcJob** cmdlet submits or re-queues one or more specified jobs to the HPC cluster that you want to run the jobs.
You can use either the job IDs or **HpcJob** objects to specify the jobs.
You can resubmit jobs that have a state of canceled or failed.

## EXAMPLES

### Example 1: Submit a job
```
PS C:\>Submit-HpcJob -Id 35 -Scheduler "MyHeadNode"
```

This command submits the job with job ID 35 on the cluster that has a head node named MyHeadNode.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object for the credentials you want to use to submit the jobs.
You can use the Get-Credential cmdlet to get a **PSCredential** object.
If you do not specify this parameter, then the cmdlet submits the jobs with the Windows credentials of the user currently logged in.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an array of job IDs for the jobs you want to submit.

```yaml
Type: Int32[]
Parameter Sets: id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies an array of **HpcJob** objects for the jobs that you want to submit for running on the cluster.

```yaml
Type: HpcJob[]
Parameter Sets: job
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to submit the jobs.
The value must be a valid computer name.
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

### HpcJob[]

## OUTPUTS

### HpcJob[]

## NOTES
* After you submit the job, the job scheduler validates the job and enters the job in the job queue. The job scheduler waits to start the job until sufficient resources become available.
* In HPC Pack 2012 with Service Pack 1 (SP1), a cluster member added as a job operator can use this cmdlet to requeue (but not submit) a job. However, a job operator cannot modify any job properties at the time that the job is requeued.

## RELATED LINKS

[Export-HpcJob](/powershell/module/hpcpack2016/export-hpcjob?view=hpc16-ps)

[Get-HpcJob](/powershell/module/hpcpack2016/get-hpcjob?view=hpc16-ps)

[New-HpcJob](/powershell/module/hpcpack2016/new-hpcjob?view=hpc16-ps)

[Set-HpcJob](/powershell/module/hpcpack2016/set-hpcjob?view=hpc16-ps)

[Stop-HpcJob](./Stop-HpcJob.md)
