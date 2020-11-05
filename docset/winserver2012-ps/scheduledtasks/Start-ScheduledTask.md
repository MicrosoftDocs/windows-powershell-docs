---
external help file: ScheduledTask_Cmdlets.xml
online version:
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: A95C9523-FFAF-4E16-9020-BEF0A605E47D
manager: dansimp
---

# Start-ScheduledTask

## SYNOPSIS
Starts one or more instances of a scheduled task.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-ScheduledTask [-TaskName] <String> [[-TaskPath] <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Start-ScheduledTask [-InputObject] <CimInstance> [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
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

This command uses the **Get-ScheduledTask** cmdlet to get the full task path for the UpdateVirus folder and pipes that value to **Start-ScheduledTask**, which starts all tasks in the UpdateVirus folder.

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskName
Specifies the name of a scheduled task.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

