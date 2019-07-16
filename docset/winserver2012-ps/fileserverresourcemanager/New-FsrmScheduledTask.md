---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 67E030DA-8AB7-4E42-BEE7-BDAA9A6B5681
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# New-FsrmScheduledTask

## SYNOPSIS
Creates a scheduled task object.

## SYNTAX

```
New-FsrmScheduledTask [-Time] <DateTime> [-AsJob] [-CimSession <CimSession[]>] [-Monthly <Int32[]>]
 [-RunDuration <Int32>] [-ThrottleLimit <Int32>] [-Weekly <FsrmScheduledTaskDaysEnum[]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-FsrmScheduledTask** cmdlet creates a scheduled task object that defines scheduling for reports, classification, and file management jobs.

## EXAMPLES

### Example 1: Create a weekly scheduled task
```
PS C:\>$d = get-date "12:00am" PS C:\>New-FsrmScheduledTask -Time $d -Weekly @(Monday, Tuesday, Wednesday, Thursday, Friday)
```

The first command gets a **DateTime** object and stores it in the variable $d.

The second command returns a **FsrmScheduledTask** object that defines a schedule that runs the task at midnight every day, Monday through Friday.

### Example 2: Create a monthly scheduled task
```
PS C:\>$d = get-date "12:00am" PS C:\>New-FsrmScheduledTask -Time $d -Monthly @(-1,15) -RunDuration 4
```

The first command gets a **DateTime** object and stores it in the variable **$d**.

This second command returns a **FsrmScheduledTask** object that describes a schedule that runs the task at midnight on the 15th and the last day of every month.
The **RunDuration** parameter specifies that the server terminates the process after 4 hours if the process has not ended.

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

### -Monthly
Specifies an array of days on which to run the task.
Specify a value of -1 to run the task on the last day of the month.
If you specify this parameter, do not specify the **Weekly** parameter.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunDuration
Specifies the number of hours that the server runs the task before canceling it.
The value 0 indicates that the server runs the task to completion.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
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

### -Time
Specifies a date and time value, in standard Coordinated Universal Time (UTC) format, to run the task.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Weekly
Specifies an array of weekdays on which to run the task. 
If you specify this parameter, do not specify the **Monthly** parameter.

```yaml
Type: FsrmScheduledTaskDaysEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMScheduledTask

## NOTES

## RELATED LINKS

[Set-FsrmClassification](./Set-FsrmClassification.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Set-FsrmStorageReport](./Set-FsrmStorageReport.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

