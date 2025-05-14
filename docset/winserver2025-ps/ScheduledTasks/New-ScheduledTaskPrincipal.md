---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/new-scheduledtaskprincipal?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledTaskPrincipal
---

# New-ScheduledTaskPrincipal

## SYNOPSIS
Creates an object that contains a scheduled task principal.

## SYNTAX

### User (Default)
```
New-ScheduledTaskPrincipal [[-Id] <String>] [[-RunLevel] <RunLevelEnum>]
 [[-ProcessTokenSidType] <ProcessTokenSidTypeEnum>] [[-RequiredPrivilege] <String[]>] [-UserId] <String>
 [[-LogonType] <LogonTypeEnum>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### Group
```
New-ScheduledTaskPrincipal [-GroupId] <String> [[-Id] <String>] [[-RunLevel] <RunLevelEnum>]
 [[-ProcessTokenSidType] <ProcessTokenSidTypeEnum>] [[-RequiredPrivilege] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **New-ScheduledTaskPrincipal** cmdlet creates an object that contains a scheduled task principal.
Use a scheduled task principal to run a task under the security context of a specified account.
When you use a scheduled task principal, Task Scheduler can run the task regardless of whether that account is logged on.

You can use the definition of a scheduled task principal to register a new scheduled task or update an existing task registration.

## EXAMPLES

### Example 1: Register a scheduled task by using a user ID for a task principal
```
PS C:\>$Sta = New-ScheduledTaskAction -Execute "Cmd"

The second command creates a scheduled task principal. The **New-ScheduledTaskPrincipal** cmdlet specifies that Task Scheduler uses the Local Service account to run tasks, and that the Local Service account uses the Service Account logon. The command assigns the **ScheduledTaskPrincipal** object to the $STPrin variable.
PS C:\>$STPrin = New-ScheduledTaskPrincipal -UserId "LOCALSERVICE" -LogonType ServiceAccount

The third command registers the scheduled task Task01 to run the task action named Cmd. The **Principal** parameter specifies that the Task Scheduler uses the Local Service account to run the task.
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Principal $STPrin
```

This example registers a scheduled task that will run as the Local Service account.

The first command creates a scheduled task action named Cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.

### Example 2: Register a scheduled task by using a user group for a task principal
```
PS C:\>$Sta = New-ScheduledTaskAction cmd

The second command creates a scheduled task principal. The **New-ScheduledTaskPrincipal** cmdlet specifies that Task Scheduler uses the Administrators user group that has the highest privileges to run tasks. The command assigns the **ScheduledTaskPrincipal** object to the $STPrin variable.
PS C:\>$STPrin = New-ScheduledTaskPrincipal -GroupId "BUILTIN\Administrators" -RunLevel Highest

The third command registers the scheduled task Task01 to run the task action named Cmd. The *Principal* parameter specifies that Task Scheduler uses the Administrators user group to run the task.
PS C:\>Register-ScheduledTask Task01 -Action $Sta -Principal $STPrin
```

This example registers a scheduled task that runs under logged-in members of the Administrators user group that has the highest privileges.

The first command creates a scheduled task action named cmd and assigns the **ScheduledTaskAction** object to the $Sta variable.

## PARAMETERS

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -GroupId
Specifies the ID of a user group that Task Scheduler uses to run the tasks that are associated with the principal.

```yaml
Type: String
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of a scheduled task principal.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogonType
Specifies the security logon method that Task Scheduler uses to run the tasks that are associated with the principal.
The acceptable values for this parameter are:

- None
- Password
- S4U
- Interactive
- Group
- ServiceAccount
- InteractiveOrPassword

For more information about LogonType values, see [Principal.LogonType](/windows/win32/taskschd/principal-logontype#property-value)

```yaml
Type: LogonTypeEnum
Parameter Sets: User
Aliases:
Accepted values: None, Password, S4U, Interactive, Group, ServiceAccount, InteractiveOrPassword

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessTokenSidType
Specifies the security ID (SID) type of the process token.
The acceptable values for this parameter are:

- None
- Unrestricted
- Default

```yaml
Type: ProcessTokenSidTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: None, Unrestricted, Default

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredPrivilege
Specifies an array of user rights that Task Scheduler uses to run the tasks that are associated with the principal.
Specify the constant name that is associated with a user right.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunLevel
Specifies the level of user rights that Task Scheduler uses to run the tasks that are associated with the principal.
The acceptable values for this parameter are:

- Highest.
Tasks run by using the highest privileges.
- Limited.
Tasks run by using the least-privileged user account (LUA).

```yaml
Type: RunLevelEnum
Parameter Sets: (All)
Aliases:
Accepted values: Limited, Highest

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

### -UserId
Specifies the user ID that Task Scheduler uses to run the tasks that are associated with the principal.

```yaml
Type: String
Parameter Sets: User
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_TaskPrincipal

## NOTES

## RELATED LINKS

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

[New-ScheduledTaskAction](./New-ScheduledTaskAction.md)

[New-ScheduledTaskSettingsSet](./New-ScheduledTaskSettingsSet.md)

[New-ScheduledTaskTrigger](./New-ScheduledTaskTrigger.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)


