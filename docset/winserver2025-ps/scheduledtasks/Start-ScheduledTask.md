---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/start-scheduledtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ScheduledTask
---

# Start-ScheduledTask

## SYNOPSIS
Starts one or more instances of a scheduled task.

## SYNTAX

### Path (Default)
```
Start-ScheduledTask [[-TaskPath] <String>] [-TaskName] <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Object
```
Start-ScheduledTask [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-ScheduledTask** cmdlet starts a registered background task asynchronously.

## EXAMPLES

### Example 1: Start a registered scheduled task
```
PS C:\> Start-ScheduledTask -TaskName "ScanSoftware"
```

This command starts a task named ScanSoftware in the root folder.

### Example 2: Start all tasks in a folder
```
PS C:\>Get-ScheduledTask -TaskPath "\UpdateTasks\UpdateVirus\" | Start-ScheduledTask
```

This command uses the Get-ScheduledTask cmdlet to get the full task path for the UpdateVirus folder and pipes that value to **Start-ScheduledTask**, which starts all tasks in the UpdateVirus folder.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: Object
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
Parameter Sets: Path
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
Parameter Sets: Path
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-ScheduledTask](./Disable-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Export-ScheduledTask](./Export-ScheduledTask.md)

[Get-ScheduledTask](./Get-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)

