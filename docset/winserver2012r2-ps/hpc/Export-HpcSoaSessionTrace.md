---
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/export-hpcsoasessiontrace?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HpcSoaSessionTrace
---

# Export-HpcSoaSessionTrace

## SYNOPSIS
This cmdlet is deprecated and was removed in Microsoft® HPC Pack 2012. Copies the WCF log files that contain the traces for an SOA session from each of the compute nodes to a single location so that you can view the log files with Service Trace Viewer.

## SYNTAX

### ID
```
Export-HpcSoaSessionTrace [-Id] <Int32> -Path <String> [-Scheduler <String> ] [ <CommonParameters>]
```

### Job
```
Export-HpcSoaSessionTrace -Job <HpcJob> -Path <String> [-Scheduler <String> ] [ <CommonParameters>]
```

## DESCRIPTION
The **Export-HpcSoaSessionTrace** cmdlet copies the Windows Communication Foundation (WCF) log files that contain the traces for the specified service-oriented architecture (SOA) session from each of the compute nodes to a single location so that you can view the log file with Service Trace Viewer. You can specify the SOA session by specifying the identifier for the SOA session or by specifying the **HpcJob** object for the service job for the session. This cmdlet performs the same action that occurs when you click Collect Trace in the Job Management view in HPC Cluster Manager.

## EXAMPLES

### Example 1: Export WCF log files
```
PS C:\> Export-HpcSoaSessionTrace –Id 3 –Path "\\HeadNode\CcpSpoolDir"
```

This command copies the WCF log files from the SOA session with a session identifier of 3 from the compute nodes to the shared folder at \\HeadNode\CcpSpoolDir.

### Example 2: Get a job by ID an export the WCF log files
```
PS C:\> Get-HpcJob –Id 6 | Export-HpcSoaSessionTrace –Path "\\HeadNode\CcpSpoolDir"
```

This command gets the **HpcJob** object for the job with a job ID of 6, and copies the WCF log files from the SOA session for which that job is the service job from the compute nodes to the shared folder at \\HeadNode\CcpSpoolDir.

### Example 3: Export WCF log files
```
PS C:\> $Job = Get-HpcJob –Id 8
PS C:\> Export-HpcSoaSessionTrace –Job $Job –Path "\\HeadNode\CcpSpoolDir"
```

This command gets the **HpcJob** object for the job with a job ID of 8 and saves that object in a variable. The example then uses that variable with the Job parameter of the **Export-HpcSoaSessionTrace** cmdlet to copy the WCF log files from the SOA session for which that job is the service job from the compute nodes to the shared folder at \\HeadNode\CcpSpoolDir.

## PARAMETERS

### -ID
Specifies the ID of the SOA session for which you want to collect the log files. In HPC Pack 2008 R2, this session ID is the job ID of the service job for the session. You cannot specify both the Id and Job parameters.

```yaml
Type: Int32
Parameter Sets: 1
Aliases: None

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the ID of the SOA session for which you want to collect the log files. In HPC Pack 2008 R2, this session ID is the job ID of the service job for the session. You cannot specify both the *Id* and *Job* parameters.

```yaml
Type: HpcJob
Parameter Sets: Name
Aliases: None

Required: True
Position: 1
Default value: None
Accept pipeline input: (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the location where you want the log files to be collected. This location should be a shared folder that is accessible from all of the compute nodes; for example, *\\%CCP_SCHEDULER%\CcpSpoolDir*.

```yaml
Type: String
Parameter Sets: All
Aliases: None

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a name for the XML file to which you want to export the nodes, including the full or relative path to the file if the **Export-HpcNodeXML** cmdlet should not save the file in the current directory.

This cmdlet creates any directories that do not already exist in that path.
If the file already exists and you do not specify the *Force* parameter, the cmdlet prompts you to confirm whether or not you want to replace the file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node of the HPC cluster that ran the SOA session for which you want to collect the log files. The value must be a valid computer name or IP address. If you do not specify the Scheduler parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies. To set this environment variable, run the following cmdlet:


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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### HpcJob

## OUTPUTS

### None

## NOTES
* The WCF log files for a session get created only if the event logging level for the SOA service is set to a value other than Off when the session starts. To set the event logging level for an SOA service in the Configuration view in HPC Cluster Manager, click Services in the navigation pane, click the name of the service, and then click Set Event Logging Level.
* The WCF log files are originally saved in the %CCP_DATA%\SoaTrace folder on each node. The log files have names of *[job_id]_[task_id].[subtask_id]_trace.svclog*, where there is a different subtask for each node. This cmdlet copies all of these files to a shared folder on a single node.
* The WCF log files can take up a lot of disk space, so you should remove them periodically by running the Remove-HpcSoaSessionTrace cmdlet.
* You must be a cluster administrator to run this cmdlet successfully.
* This cmdlet is supported only for HPC Pack 2008 R2. It is deprecated and was removed in HPC Pack 2012.

## RELATED LINKS

[Get-HpcJob](./Get-HpcJob.md)

[Remove-HpcSoaSessionTrace](./Remove-HpcSoaSessionTrace.md)
