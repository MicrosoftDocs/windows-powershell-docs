---
external help file: ScheduledTask_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 7426C09E-EA80-4C42-8F3A-0DEBB5C2B655
manager: dansimp
---

# Set-ScheduledTask

## SYNOPSIS
Modifies a scheduled task.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [[-Action] <CimInstance[]>]
 [[-Trigger] <CimInstance[]>] [[-Settings] <CimInstance>] [[-User] <String>] [[-Password] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [[-Action] <CimInstance[]>]
 [[-Trigger] <CimInstance[]>] [[-Settings] <CimInstance>] [[-Principal] <CimInstance>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Set-ScheduledTask [-InputObject] <CimInstance> [[-Password] <String>] [[-User] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Set-ScheduledTask** cmdlet modifies a task definition.

You can make changes to a task definition even if an instance of the task is running.
The changes do not affect the current instance.

## EXAMPLES

### Example 1: Modify a trigger in a scheduled task
```
PS C:\>$Time = New-ScheduledTaskTrigger -At 12:00 -Once PS C:\>Set-ScheduledTask -TaskName "SoftwareScan" -Trigger $Time
TaskPath                          TaskName 
--------                          -------- 
\                                 SoftwareScan
```

In this example, the first command uses the **New-ScheduledTaskTrigger** cmdlet to define a time trigger, to which the $Time variable is assigned. 

The second command adds (or replaces) the $Time trigger in the scheduled task SoftwareScan.

### Example 2: Modify settings in a scheduled task definition
```
PS C:\>$Act1 = New-ScheduledTaskAction -Execute Notepad.exe
PS C:\>$Act2 = New-ScheduledTaskAction -Execute Calc.exe
PS C:\>Set-ScheduledTask "DeployTools" -Action $A1,$A2
TaskPath                          TaskName 
--------                          -------- 
\                                 DeployTools
```

In this example, the set of commands uses cmdlets and variables to modify a scheduled task.

In this example, the first command uses the **New-ScheduledTaskAction** cmdlet to define an action, to which the $A1 variable is assigned.

The second command uses the **New-ScheduledTaskAction** cmdlet to define a second action, to which the $A2 variable is assigned.

The third command adds the two actions to the scheduled task DeployTools.

## PARAMETERS

### -Action
Specifies an array of work items to be performed by the task.
If you specify several actions, the computer runs them in order.
You can specify up to 32 actions.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Password
Specifies a password for the **\<run as\>** user.
The password is ignored for the well-known system accounts.

Well-known accounts are: NT AUTHORITY\SYSTEM, NT AUTHORITY\LOCALSERVICE, NT AUTHORITY\NETWORKSERVICE, and the well-known security identifiers (SIDs) for all three accounts.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Principal
Specifies the security context in which a task is run.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
Specifies a configuration object that the Task Scheduler service uses to determine how to run a task.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskName
Specifies the name of a scheduled task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskPath
Specifies the path for a scheduled task in Task Scheduler namespace.
You can use **\** for the root folder.
If you do not specify a path, the cmdlet uses the root folder.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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

A trigger is a set of criteria that, when met, starts a scheduled task.
You can use a time-based trigger or an event-based trigger to start a task and a task can be started by one or more triggers.
A task can have up to 48 triggers.
For more information about triggers, see Triggershttp://technet.microsoft.com/en-us/library/cc748841.aspx.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies the name of a **\<run as\>** user account to use when you run the task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: 6
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ScheduledTask

## NOTES

## RELATED LINKS

[Disable-ScheduledTask](./Disable-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Export-ScheduledTask](./Export-ScheduledTask.md)

[Get-ScheduledTask](./Get-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)

[New-ScheduledTaskTrigger](./New-ScheduledTaskTrigger.md)

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

