---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/disable-scheduledtask?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledTask
---

# Disable-ScheduledTask

## SYNOPSIS
Disables a scheduled task.

## SYNTAX

### Name

```
Disable-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Object

```
Disable-ScheduledTask [-InputObject] <CimInstance> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Disable-ScheduledTask` cmdlet disables a scheduled task.

## EXAMPLES

### Example 1: Disable a scheduled task

```powershell
Disable-ScheduledTask -TaskName 'SystemScan'
```

```Output
TaskPath                    TaskName                    State
--------                    --------                    --------
\                           SystemScan                   Disabled
```

This command disables the SystemScan task in the root folder.

### Example 2: Disable all scheduled tasks in a folder

```powershell
Get-ScheduledTask -TaskPath '\UpdateTasks\' | Disable-ScheduledTask
```

```Output
TaskPath                          TaskName                        State
--------                          --------                        --------
\UpdateTasks\                     UpdateApps                      Disabled
\UpdateTasks\                     UpdateDrivers                   Disabled
```

This command uses the `Get-Scheduledtask` cmdlet to get all scheduled tasks in the `\UpdateTasks\`
folder. The command pipes this information to the `Disable-ScheduledTasks` cmdlet, which disables
these scheduled tasks.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer
name or a session object, such as the output of a
[New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or
[Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The
default is the current session on the local computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Specifies the input object that is used in a pipeline command.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskName

Specifies the name of a scheduled task.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskPath

Specifies an array of one or more paths for scheduled tasks in Task Scheduler namespace. You can use
`*` for a wildcard character query. You can use `\` for the root folder. To specify a full **TaskPath**
you need to include the leading and trailing `\`. If you do not specify a path, the cmdlet uses the
root folder.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ScheduledTask

## NOTES

## RELATED LINKS

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Export-ScheduledTask](./Export-ScheduledTask.md)

[Get-ScheduledTask](./Get-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)
