---
Module Name: HPC
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/hpc/export-hpcjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-HpcJob
---

# Export-HpcJob

## SYNOPSIS
Saves information about a job in an XML file.

## SYNTAX

### job (Default)
```
Export-HpcJob -Job <HpcJob> -Path <String> [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

### id
```
Export-HpcJob [-Id] <Int32> -Path <String> [-Force] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-HpcJob** cmdlet exports the specified job to an XML file.
You can then import the file by specifying the file in the *JobFile* parameter of the New-HpcJob cmdlet to create a new job based on the exported job.

## EXAMPLES

### Example 1: Get a job and export it
```
PS C:\>Get-HpcJob -Id 8 | Export-HpcJob -Path "Job8.xml"
```

This command exports the job with an ID of 8 to a file named Job8.xml.

## PARAMETERS

### -Force
Replaces the job XML file if it already exists, without prompting the user.

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

### -Id
Specifies the identifier of the job that you want to export.
You cannot use the *Id* parameter together with the *Job* parameter.

```yaml
Type: Int32
Parameter Sets: id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies an **HpcJob** object that corresponds to the job that you want to export.
To get an **HpcJob** object, use the Get-HpcJob command.
You cannot use the *Job* parameter together with the *Id* parameter.

```yaml
Type: HpcJob
Parameter Sets: job
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a name for the XML file to which you want to export the job, including the full or relative path to the file if the **Export-HpcJob** cmdlet should not save the file in the current directory.

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
Specifies the host name or IP address of the head node for the cluster that contains the job you want to export.
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

### HpcJob

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-HpcJob](./Get-HpcJob.md)

[New-HpcJob](./New-HpcJob.md)

[Set-HpcJob](./Set-HpcJob.md)

[Stop-HpcJob](./Stop-HpcJob.md)

[Submit-HpcJob](./Submit-HpcJob.md)
