---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 07/29/2021
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/get-scheduledtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledTask
---

# Get-ScheduledTask

## SYNOPSIS
Gets the task definition object of a scheduled task that is registered on the local computer.

## SYNTAX

```
Get-ScheduledTask [[-TaskName] <String[]>] [[-TaskPath] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ScheduledTask** cmdlet gets the task definition object of a scheduled task that is
registered on a computer.

## EXAMPLES

### Example 1: Get a scheduled task definition object

```powershell
Get-ScheduledTask -TaskName "SystemScan"
```

```Output
TaskPath                          TaskName                        State
--------                          --------                        --------
\                                 SystemScan                      Ready
```

This command gets the definition object of the SystemScan scheduled task in the root folder.

### Example 2: Get an array of scheduled task definition objects

```powershell
Get-ScheduledTask -TaskPath "\UpdateTasks\*"
```

```Output
TaskPath                          TaskName                        State
--------                          --------                        --------
\UpdateTasks                      UpdateApps                      Ready
\UpdateTasks                      UpdateDrivers                   Ready
\UpdateTasks                      UpdateOS                        Disabled
\UpdateTasks                      UpdateSignatures                Running
```

This command gets an array of task definitions objects from the UpdateTasks folder.

### Example 3: Get an array of scheduled task definition objects in multiple paths
```powershell
Get-ScheduledTask -TaskPath "\Microsoft\Windows\Work Folders\","\Microsoft\Windows\Workplace Join\"
```

```Output
TaskPath                                       TaskName                          State
--------                                       --------                          -----
\Microsoft\Windows\Work Folders\               Work Folders Logon Synchroniza... Ready
\Microsoft\Windows\Work Folders\               Work Folders Maintenance Work     Ready
\Microsoft\Windows\Workplace Join\             Automatic-Device-Join             Disabled
\Microsoft\Windows\Workplace Join\             Device-Sync                       Disabled
\Microsoft\Windows\Workplace Join\             Recovery-Check                    Disabled
```

This command gets task definition objects from multiple task paths

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

### -TaskName
Specifies an array of one or more names of a scheduled task. You can use **"*"** for a wildcard character query.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TaskPath
Specifies an array of one or more paths for scheduled tasks in Task Scheduler namespace. You can use **"*"** for a wildcard character query.
You can use **\\*** for the root folder. To specify a full TaskPath you need to include the leading and trailing **\\**.
If you do not specify a path, the cmdlet uses the root folder.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_ScheduledTask[]

## NOTES

## RELATED LINKS

[Disable-ScheduledTask](./Disable-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Export-ScheduledTask](./Export-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)
