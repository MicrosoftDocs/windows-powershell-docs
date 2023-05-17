---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
Module Name: WasPSExt
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/waspsext/get-wasjob?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WASJob
---

# Get-WASJob

## SYNOPSIS
Gets a list of the available jobs.

## SYNTAX

### JobId
```
Get-WASJob [-JobID] <Guid[]> [<CommonParameters>]
```

### JobName
```
Get-WASJob [[-JobName] <String[]>] [-ProjectName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The Get-WASJob cmdlet returns a list of the jobs that are available on the Windows Assessment Services server.
It also displays metadata, such as assessments, the project name, and assets associated with each job.
You can use the object returned to initiate a run of the job instance using the **Invoke-WASJob** command.

## EXAMPLES

### Example 1: Get all jobs that match a specific search string
```
PS C:\> Get-WASJob -JobName Driver*
```

This command returns all the jobs with a job name that starts with "driver".

### Example 2: Get all jobs and display first job in list
```
PS C:\> $jobs = Get-WASJob
PS C:\> $jobs[0]

This command lists all the assets associated with the first job in the list returned by the previous command.
PS C:\> $jobs[0].Assets
```

This command gets all jobs, saves it to a variable, and then displays the first job in the list.

## PARAMETERS

### -JobID
Specifies the ID of the job that you want to get.
If this parameter is not specified, all jobs are listed.

```yaml
Type: Guid[]
Parameter Sets: JobId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Specifies the name of the job that you want to get.
The full name of the job isn't required.
Wildcards are accepted.
If this parameter isn't specified, all jobs are listed.

```yaml
Type: String[]
Parameter Sets: JobName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectName
Specifies the project name associated with the job that you want to get.
The full name of the project isn't required.
Wildcards are accepted.
If this parameter isn't specified, all jobs are listed.

```yaml
Type: String[]
Parameter Sets: JobName
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASJobInstance](./Get-WASJobInstance.md)

[Get-WASJobInstanceStatus](./Get-WASJobInstanceStatus.md)

[Invoke-WASJob](./Invoke-WASJob.md)

[Skip-WASJobInstance](./Skip-WASJobInstance.md)

[Stop-WASJobInstance](./Stop-WASJobInstance.md)

[Update-WASJob](./Update-WASJob.md)

