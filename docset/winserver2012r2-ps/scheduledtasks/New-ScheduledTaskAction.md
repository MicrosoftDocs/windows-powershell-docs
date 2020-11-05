---
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
online version: 
schema: 2.0.0
title: New-ScheduledTaskAction
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 919F1F91-CD15-4C0E-80F5-76E54531120E
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-ScheduledTaskAction

## SYNOPSIS
Creates a scheduled task action.

## SYNTAX

```
New-ScheduledTaskAction [-Id <String>] [-Execute] <String> [[-Argument] <String>]
 [[-WorkingDirectory] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-ScheduledTaskAction** cmdlet creates an object that contains the definition of a scheduled task action.
A scheduled task action represents a command that a task executes when Task Scheduler runs the task.
You can use a task action definition to register a new scheduled task or update an existing task registration.

A task can have a single action or a maximum of 32 actions.
When you specify multiple actions, Task Scheduler executes the actions sequentially.
The Task Scheduler service controls tasks activation, and it hosts the tasks that it starts.

## EXAMPLES

### Example 1: Create a scheduled task action
```
PS C:\> New-ScheduledTaskAction -Execute "PowerShell.exe"
```

This command creates a new scheduled task action that runs PowerShell.exe.

## PARAMETERS

### -Argument
Specifies arguments for the command-line operation.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Execute
Specifies the path to an executable file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an identifier of an action.
Task Scheduler uses this identifier for logging.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -WorkingDirectory
Specifies a directory where Task Scheduler will run the task.
If you do not specify a working directory, Task Scheduler runs the task in the %windir%\system32 directory.

```yaml
Type: String
Parameter Sets: (All)
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_TaskAction

## NOTES

## RELATED LINKS

[Register-ScheduledTask](./Register-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[New-ScheduledTaskPrincipal](./New-ScheduledTaskPrincipal.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

