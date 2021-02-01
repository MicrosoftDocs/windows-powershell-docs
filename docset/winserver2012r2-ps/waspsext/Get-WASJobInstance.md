---
external help file: Microsoft.Assessments.WAS.PowerShell.dll-Help.xml
online version: 
schema: 2.0.0
title: Get-WASJobInstance
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 12/05/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E2EE9F05-FF43-41DD-9270-ABCB6D4DADD4
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-WASJobInstance

## SYNOPSIS
Gets a list of job instances.

## SYNTAX

### FindByJob
```
Get-WASJobInstance [-Job] <WASJob[]> [[-Runtag] <String>] [[-Testpass] <String>] [<CommonParameters>]
```

### FindByJobInstance
```
Get-WASJobInstance [-JobInstance] <WASJobInstance[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-WASJobInstance** cmdlet gets a list of job instances associated with a specific job, and displays metadata for each job instance.
The Job parameter is required.

## EXAMPLES

### Example 1: Get all job instances for a job
```
PS C:\>$job = Get-WASJob -JobName *automated*
Get-GetJobInstance -Job $job
```

This command gets all the jobs with "automated" in the job name, assigns it to a variable, and then gets all the job instances for the job.

### Example 2: Get all running job instances for a job
```
PS C:\> $job = Get-WASJob -JobName *automated*
PS C:\> Get-WASJobInstance -Job $job | where {$_.IsComplete -eq $false }
```

This command gets all the jobs with "automated" in the job name, assigns it to a variable, and then gets all the job instances that are currently running for the job.

### Example 3: Get all running job instances
```
PS C:\> $job = Get-WASJob | Get-WASJobInstance | where {$_.IsComplete -eq $false}
```

This command gets all the jobs that are currently running using dep_nextref_was server.

## PARAMETERS

### -Job
Specifies the job object for which to retrieve job instances.
This is a required parameter.

```yaml
Type: WASJob[]
Parameter Sets: FindByJob
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobInstance
Specifies the job instance for which to retrieve an updated object.
You can pass a job instance of itself to get an update or copy of the job instance object.

```yaml
Type: WASJobInstance[]
Parameter Sets: FindByJobInstance
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Runtag
Specifies the run tag for the job instance you want to get.
The full name of the run tag isn't required.
Wildcards are accepted.
If this parameter isn't specified, all job instances are listed.

```yaml
Type: String
Parameter Sets: FindByJob
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Testpass
Specifies the test pass for the job instance you want to get.
The full name of the test pass isn't required.
Wildcards are accepted.
If this parameter isn't specified, all job instances are listed.

```yaml
Type: String
Parameter Sets: FindByJob
Aliases: 

Required: False
Position: 2
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

[Get-WASJobInstanceStatus](./Get-WASJobInstanceStatus.md)

[Skip-WASJobInstance](./Skip-WASJobInstance.md)

[Stop-WASJobInstance](./Stop-WASJobInstance.md)

