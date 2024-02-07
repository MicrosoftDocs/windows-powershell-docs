---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_ScheduledTask_v1.0.cdxml-help.xml
Module Name: ScheduledTasks
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/scheduledtasks/export-scheduledtask?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ScheduledTask
---

# Export-ScheduledTask

## SYNOPSIS
Exports a scheduled task as an XML string.

## SYNTAX

### Name
```
Export-ScheduledTask [[-TaskName] <String>] [[-TaskPath] <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### Object
```
Export-ScheduledTask [-InputObject] <CimInstance> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Export-ScheduledTask** cmdlet exports the definition of a scheduled task into an XML string.

## EXAMPLES

### Example 1: Export a scheduled task into an XML string.
```
PS C:\> Export-ScheduledTask -TaskName "UpdateDrivers" -TaskPath "\UpdateTasks\"
```

This command exports the UpdateDrivers scheduled task in the \UpdateTasks\ folder into an XML string.
The command lists the XML string as its output.

### Example 2: Export all scheduled task definitions that are in the UpdateTasks folder.
```
PS C:\> Get-ScheduledTask -TaskPath "\UpdateTasks\" | Export-ScheduledTask
```

This command uses the Get-ScheduledTask cmdlet to get all scheduled tasks in the **\UpdateTasks\** folder.
The command pipes this information to the **Export-ScheduledTasks** cmdlet, which exports the definitions of these scheduled tasks.
The command lists the XML string of each task as its output.

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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskName
Specifies the name of a scheduled task to export.

```yaml
Type: String
Parameter Sets: Name
Aliases:

Required: False
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
Parameter Sets: Name
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

### String

## NOTES

## RELATED LINKS

[Disable-ScheduledTask](./Disable-ScheduledTask.md)

[Enable-ScheduledTask](./Enable-ScheduledTask.md)

[Get-ScheduledTask](./Get-ScheduledTask.md)

[New-ScheduledTask](./New-ScheduledTask.md)

[Register-ScheduledTask](./Register-ScheduledTask.md)

[Set-ScheduledTask](./Set-ScheduledTask.md)

[Start-ScheduledTask](./Start-ScheduledTask.md)

[Stop-ScheduledTask](./Stop-ScheduledTask.md)

[Unregister-ScheduledTask](./Unregister-ScheduledTask.md)

