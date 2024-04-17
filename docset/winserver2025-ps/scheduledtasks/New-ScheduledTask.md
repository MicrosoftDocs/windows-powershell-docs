---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/new-scheduledtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledTask
---

# New-ScheduledTask

## SYNOPSIS
Creates a scheduled task instance.

## SYNTAX

```
New-ScheduledTask [[-Action] <CimInstance[]>] [[-Description] <String>] [[-Principal] <CimInstance>]
 [[-Settings] <CimInstance>] [[-Trigger] <CimInstance[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-ScheduledTask** cmdlet creates an object that contains the definition of a scheduled task.
**New-ScheduledTask** does not automatically register the object with the Task Scheduler service.

You can register a task to run any of the following application or file types: Win32 applications, Win16 applications, OS/2 applications, MS-DOS applications, batch files (*.bat), command files (*.cmd), or any properly registered file type.

## EXAMPLES

### Example 1: Define a scheduled task and register it at a later time
```powershell
PS C:\> $action = New-ScheduledTaskAction -Execute "Taskmgr.exe"
PS C:\> $trigger = New-ScheduledTaskTrigger -AtLogon
PS C:\> $principal = "Contoso\Administrator"
PS C:\> $settings = New-ScheduledTaskSettingsSet
PS C:\> $task = New-ScheduledTask -Action $action -Principal $principal -Trigger $trigger -Settings $settings
PS C:\> Register-ScheduledTask T1 -InputObject $task
```

In this example, the set of commands uses several cmdlets and variables to define and then register a scheduled task.

The first command uses the **New-ScheduledTaskAction** cmdlet to assign the executable file `tskmgr.exe` to the variable `$action`.

The second command uses the **New-ScheduledTaskTrigger** cmdlet to assign the value `AtLogon` to the variable `$trigger`.

The third command assigns the principal of the scheduled task `Contoso\Administrator` to the variable `$principal`.

The fourth command uses the **New-ScheduledTaskSettingsSet** cmdlet to assign a task settings object to the variable `$settings`.

The fifth command creates a new task and assigns the task definition to the variable `$task`.

The sixth command (hypothetically) runs at a later time.
It registers the new scheduled task and defines it by using the `$task` variable.

### Example 2: Define a scheduled task with multiple actions
```powershell
PS C:\> $actions = (New-ScheduledTaskAction –Execute 'foo.ps1'), (New-ScheduledTaskAction –Execute 'bar.ps1')
PS C:\> $trigger = New-ScheduledTaskTrigger -Daily -At '9:15 AM'
PS C:\> $principal = New-ScheduledTaskPrincipal -UserId 'DOMAIN\user' -RunLevel Highest
PS C:\> $settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -WakeToRun
PS C:\> $task = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings

PS C:\> Register-ScheduledTask 'baz' -InputObject $task

```

This example creates and registers a scheduled task that runs two PowerShell scripts daily at 09:15 AM.

## PARAMETERS

### -Action
Specifies an array of work items for a task to run.
When you specify multiple actions, they run sequentially.
A task can have up to 32 actions.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Description
Briefly describes the task.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Principal
Specifies the security context in which a task runs.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
Specifies a configuration object that the Task Scheduler service uses to determine how to run a task.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### -Trigger
Specifies an array of one or more trigger objects that cause a scheduled task to start.

A trigger is a set of criteria that starts a scheduled task when the criteria are met.
You can use a time-based trigger or an event-based trigger to start a task, and one or more triggers can start a task.
A task can have up to 48 triggers.
For more information about triggers, see [Triggers](https://technet.microsoft.com/library/cc748841.aspx).

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ScheduledTask

## NOTES

## RELATED LINKS

[Disable-ScheduledTask](./Disable-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Export-ScheduledTask](./Export-ScheduledTask.md)

[Get-ScheduledTask](./Get-ScheduledTask.md)

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

[New-ScheduledTaskSettingsSet](./New-ScheduledTaskSettingsSet.md)

[New-ScheduledTaskPrincipal](./New-ScheduledTaskPrincipal.md)

[New-ScheduledTaskTrigger](./New-ScheduledTaskTrigger.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)
