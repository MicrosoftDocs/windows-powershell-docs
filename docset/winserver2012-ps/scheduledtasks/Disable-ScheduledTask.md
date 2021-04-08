---
author: Kateyanne
external help file: ScheduledTask_Cmdlets.xml
manager: dansimp
Module Name: ScheduledTasks
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/scheduledtasks/disable-scheduledtask?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Disable-ScheduledTask

## SYNOPSIS
Disables a scheduled task.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Disable-ScheduledTask [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Disable-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Disable-ScheduledTask** cmdlet disables a scheduled task.

## EXAMPLES

### Example 1: Disable a scheduled task
```
PS C:\> Disable-ScheduledTask -TaskName "SystemScan"
TaskPath                    TaskName                    State
--------                    --------                    --------
\                           SystemScan                   Disabled
```

This command disables the SystemScan task in the root folder.

### Example 2: Disable all scheduled tasks in a folder
```
PS C:\> Get-ScheduledTask -TaskPath "\UpdateTasks\" | Disable-ScheduledTask
TaskPath                          TaskName                        State
--------                          --------                        --------
\UpdateTasks\                     UpdateApps                      Disabled
\UpdateTasks\                     UpdateDrivers                   Disabled
```

This command uses the **Get-Scheduledtask** cmdlet to get all scheduled tasks in the \UpdateTasks\ folder.
The command pipes this information to the **Disable-ScheduledTasks** cmdlet, which disables these scheduled tasks.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskName
Specifies the name of a scheduled task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

