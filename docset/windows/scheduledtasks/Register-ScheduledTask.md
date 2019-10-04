---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Register-ScheduledTask
ms.reviewer:
ms.assetid: 40985269-AF17-444C-921F-42AC576C1AC3
---

# Register-ScheduledTask

## SYNOPSIS
Registers a scheduled task definition on a local computer.

## SYNTAX

### User (Default)
```
Register-ScheduledTask [-Force] [[-Password] <String>] [[-User] <String>] [-TaskName] <String>
 [[-TaskPath] <String>] [-Action] <CimInstance[]> [[-Description] <String>] [[-Settings] <CimInstance>]
 [[-Trigger] <CimInstance[]>] [[-RunLevel] <RunLevelEnum>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Xml
```
Register-ScheduledTask [-Force] [[-Password] <String>] [[-User] <String>] [-TaskName] <String>
 [[-TaskPath] <String>] [-Xml] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### Principal
```
Register-ScheduledTask [-Force] [-TaskName] <String> [[-TaskPath] <String>] [[-Principal] <CimInstance>]
 [-Action] <CimInstance[]> [[-Description] <String>] [[-Settings] <CimInstance>] [[-Trigger] <CimInstance[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Object
```
Register-ScheduledTask [-Force] [-InputObject] <CimInstance> [[-Password] <String>] [[-User] <String>]
 [[-TaskName] <String>] [[-TaskPath] <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Register-ScheduledTask** cmdlet registers a scheduled task definition on a local computer.

You can register a task to run any of the following application or file types: Win32 applications, Win16 applications, OS/2 applications, MS-DOS applications, batch files (*.bat), command files (*.cmd), or any properly registered file type.

## EXAMPLES

### Example 1: Register a scheduled task
```
PS C:\> $Time = New-ScheduledTaskTrigger -At 12:00 -Once 
PS C:\> $User = "Contoso\Administrator"
PS C:\> $PS = New-ScheduledTaskAction -Execute "PowerShell.exe"
PS C:\> Register-ScheduledTask -TaskName "SoftwareScan" -Trigger $Time -User $User -Action $PS
```

In this example, the set of commands uses cmdlets and variables to define and register a scheduled task.

The first command uses the New-ScheduledTaskTrigger cmdlet to assign a time trigger to the $Time variable.

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
Parameter Sets: User, Principal
Aliases: 

Required: True
Position: 2
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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://docs.microsoft.com/en-us/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://docs.microsoft.com/en-us/powershell/module/cimcmdlets/get-cimsession) cmdlet.
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
Parameter Sets: User, Principal
Aliases: 

Required: False
Position: 8
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
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: Object
Aliases: 

Required: True
Position: 2
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
Parameter Sets: User, Xml, Object
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Principal
Specifies the security context in which a task is run.

```yaml
Type: CimInstance
Parameter Sets: Principal
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunLevel
Specifies the required privilege level to run tasks that are associated with the principal.

```yaml
Type: RunLevelEnum
Parameter Sets: User
Aliases: 
Accepted values: Limited, Highest

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Settings
Specifies a configuration that the Task Scheduler service uses to determine how to run a task.

```yaml
Type: CimInstance
Parameter Sets: User, Principal
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskName
Specifies the name of a scheduled task.

```yaml
Type: String
Parameter Sets: User, Xml, Principal
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Object
Aliases: 

Required: False
Position: 0
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

### -Trigger
Specifies an array of one or more trigger objects that start a scheduled task.
A task can have a maximum of 48 triggers.

```yaml
Type: CimInstance[]
Parameter Sets: User, Principal
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Specifies the name of the **\<run as\>** user account to use when you run the task.

```yaml
Type: String
Parameter Sets: User, Xml, Object
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Xml
Specifies the XML string that contains a task definition.

```yaml
Type: String
Parameter Sets: Xml
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)

