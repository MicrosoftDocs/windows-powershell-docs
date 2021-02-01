---
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
online version:
schema: 2.0.0
title: Get-ScheduledTaskInfo
description:
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: E32DF15A-F488-43A1-A5E5-13307B63BB88
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-ScheduledTaskInfo

## SYNOPSIS
Gets run-time information for a scheduled task.

## SYNTAX

### Name
```
Get-ScheduledTaskInfo [-TaskName] <String> [[-TaskPath] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Object
```
Get-ScheduledTaskInfo [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ScheduledTaskInfo** cmdlet gets the last run-time information for a scheduled task.
You can use the **TaskName** parameter to specify a scheduled task, or you can use the **InputObject** parameter to specify the scheduled task.

## EXAMPLES

### Example 1: Get run-time information by using a task name
```
PS C:\> Get-ScheduledTaskInfo -TaskName "\Sample\SchedTask01"
```

This command gets run-time information for the scheduled task that is names \Sample\SchedTask01.

### Example 2: Get run-time information by using an input object
```
PS C:\>Get-ScheduledTask -TaskPath "\Sample\" | Get-ScheduledTaskInfo
```

In this example, the **Get-ScheduledTask** cmdlet gets all the scheduled tasks in the path \Sample\, and pipes the results to the **Get-ScheduledTaskInfo** cmdlet.

In the second part of the command, the **Get-ScheduledTaskInfo** cmdlet gets the run-time information for all the scheduled tasks in the path \Sample\.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskName
Specifies a name of a scheduled task.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskPath
Specifies an array of one or more paths for scheduled tasks in Task Scheduler namespace. You can use **"*"** for a wildcard character query.
You can use **\\*** for the root folder. To specify a full TaskPath you need to include the leading and trailing **\\**.
If you do not specify a path, the cmdlet uses the root folder.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_TaskDynamicInfo

## NOTES

## RELATED LINKS

[Get-ScheduledTask](./Get-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

