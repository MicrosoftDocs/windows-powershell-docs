---
external help file: WasPsExt_Cmdlets.xml
Module Name: WasPSExt
online version: https://docs.microsoft.com/powershell/module/waspsext/get-wasjob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WASJob

## SYNOPSIS
Gets a list of the available jobs.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WASJob [-JobID] <Guid[]>
```

### UNNAMED_PARAMETER_SET_2
```
Get-WASJob [[-JobName] <String[]>] [-ProjectName <String[]>]
```

## DESCRIPTION
The **Get-WASJob** cmdlet returns a list of the jobs that are available on the Windows Assessment Services server.
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

