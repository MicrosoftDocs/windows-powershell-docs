---
external help file: ScheduledTask_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 2B7F5F72-48E5-480B-913F-E8AEF0B2B13C
manager: dansimp
---

# Get-ScheduledTask

## SYNOPSIS
Gets the task definition object of a scheduled task that is registered on the local computer.

## SYNTAX

```
Get-ScheduledTask [[-TaskName] <String[]>] [[-TaskPath] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-ScheduledTask** cmdlet gets the task definition object of a scheduled task that is registered on the local computer.

## EXAMPLES

### Example 1: Get a scheduled task definition object
```
PS C:\> Get-ScheduledTask -TaskName "SystemScan"
TaskPath                          TaskName                        State
--------                          --------                        --------
\                                 SystemScan                      Ready
```

This command gets the definition object of the SystemScan scheduled task in the root folder.

### Example 2: Get an array of scheduled task definition objects
```
PS C:\> Get-ScheduledTask -TaskPath "\UpdateTasks\"
TaskPath                          TaskName                        State
--------                          --------                        --------
\UpdateTasks                      UpdateApps                      Ready 
\UpdateTasks                      UpdateDrivers                   Ready 
\UpdateTasks                      UpdateOS                        Disabled 

\UpdateTasks                      UpdateSignatures                Running
```

This command gets an array of task definitions objects from the UpdateTasks folder.

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

### -TaskName
Specifies an array of one or more names of a scheduled task.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -TaskPath
Specifies an array of one or more paths for scheduled tasks in Task Scheduler namespace.
You can use **\** for the root folder.
If you do not specify a path, the cmdlet uses the root folder.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-ScheduledTaskInfo](./Get-ScheduledTaskInfo.md)

