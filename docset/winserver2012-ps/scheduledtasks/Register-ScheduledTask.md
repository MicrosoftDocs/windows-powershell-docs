---
external help file: ScheduledTask_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 40985269-AF17-444C-921F-42AC576C1AC3
manager: dansimp
---

# Register-ScheduledTask

## SYNOPSIS
Registers a scheduled task definition on a local computer.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Register-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [-Action] <CimInstance[]>
 [[-Trigger] <CimInstance[]>] [[-Settings] <CimInstance>] [[-User] <String>] [[-Password] <String>]
 [[-RunLevel] <RunLevelEnum>] [[-Description] <String>] [-AsJob] [-CimSession <CimSession[]>] [-Force]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Register-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [-Action] <CimInstance[]>
 [[-Trigger] <CimInstance[]>] [[-Settings] <CimInstance>] [[-Principal] <CimInstance>]
 [[-Description] <String>] [-AsJob] [-CimSession <CimSession[]>] [-Force] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Register-ScheduledTask [[-TaskName] <String>] [[-TaskPath] <String>] [-InputObject] <CimInstance>
 [[-User] <String>] [[-Password] <String>] [-AsJob] [-CimSession <CimSession[]>] [-Force]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Register-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [-Xml] <String> [[-User] <String>]
 [[-Password] <String>] [-AsJob] [-CimSession <CimSession[]>] [-Force] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Register-ScheduledTask** cmdlet registers a scheduled task definition on a local computer.

You can register a task to run any of the following application or file types: Win32 applications, Win16 applications, OS/2 applications, MS-DOS applications, batch files (*.bat), command files (*.cmd), or any properly registered file type.

## EXAMPLES

### Example 1: Register a scheduled task
```
PS C:\>$Time = New-ScheduledTaskTrigger -At 12:00 -Once 

PS C:\>$User = "Contoso\Administrator"

PS C:\>$PS = New-ScheduledTaskAction -Execute "PowerShell.exe"

PS C:\>Register-ScheduledTask -TaskName "SoftwareScan" -Trigger $Time -User $User -Action $PS
```

In this example, the set of commands uses cmdlets and variables to define and register a scheduled task. 
The first command uses the **New-ScheduledTaskTrigger** cmdlet to assign a time trigger to the $Time variable.
The second command assigns the $User variable to the **\<run as\>** user account name (Contoso\Administrator). 
The third command assigns the $PS variable to PowerShell.exe.
This variable is used to define a task action.
The fourth command registers a scheduled task that is named SoftwareScan in the root folder.
The registered task uses the pre-created action and trigger values that are specified by the $Action and $User variables.

## PARAMETERS

### -Action
Specifies an array of one or more work items for the task to run.
If you specify multiple actions, the computer runs them in order.
You can specify up to 32 actions.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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

### -Description
Briefly describes the task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Instructs the cmdlet to perform the operation without prompting for confirmation.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 3
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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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

### -RunLevel
Specifies the required privilege level to run tasks that are associated with the principal.

```yaml
Type: RunLevelEnum
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
Specifies a configuration that the Task Scheduler service uses to determine how to run a task.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
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
Specifies an array of one or more trigger objects that start a scheduled task.
A task can have a maximum of 48 triggers.

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
Specifies the name of the **\<run as\>** user account to use when you run the task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: 6
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Xml
Specifies the XML string that contains a task definition.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ScheduledTask

## NOTES

## RELATED LINKS

[Get-ScheduledTask](./Get-ScheduledTask.md)

[Disable-ScheduledTask](./Disable-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Export-ScheduledTask](./Export-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)

