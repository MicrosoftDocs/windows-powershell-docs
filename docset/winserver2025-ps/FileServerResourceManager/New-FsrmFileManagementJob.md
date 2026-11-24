---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMFileManagementJob.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfilemanagementjob?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmFileManagementJob
---

# New-FsrmFileManagementJob

## SYNOPSIS
Creates a file management job.

## SYNTAX

```
New-FsrmFileManagementJob [-Name] <String> [-Description <String>] -Namespace <String[]> [-Disabled]
 [-Condition <CimInstance[]>] -Action <CimInstance> [-ReportFormat <FmjReportFormatsEnum[]>]
 [-ReportLog <FmjReportLogsEnum[]>] [-MailTo <String>] [-Notification <CimInstance[]>] -Schedule <CimInstance>
 [-Continuous] [-ContinuousLog] [-ContinuousLogSize <UInt64>] [-Parameters <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmFileManagementJob** cmdlet creates a file management job on the server.
The job specifies a schedule, conditions, a command or actions to run if a file meets all the conditions, user notifications, and reporting.

To use this cmdlet to create a file management job, you must pass in a **FsrmScheduledTask** object, a **FsrmFmjAction** object, and a **FsrmFmjNotification** object.

## EXAMPLES

### Example 1: Create a file management job that expires data
```
The first command gets a **DateTime** object and stores it in the variable $date.
PS C:\> $date = Get-Date "12:00am"

This second command returns a **FsrmScheduledTask** object that runs the task at midnight on the first day of the month. The command stores results in the $task variable.
PS C:\> $task = New-FsrmScheduledTask -Time $date -Monthly 1

The third command returns an action object for a management job and stores the results in the $action variable. The command specifies an expiration action and specifies a path that the action uses to expire files.
PS C:\> $action = New-FsrmFmjAction -Type Expiration -ExpirationFolder "C:\Expire"

The fourth command creates a file management job named "Expire all data" for the folder C:\Share01. The command specifies the schedule stored in the $task variable and specifies the action stored in the $action variable.
PS C:\> New-FsrmFileManagementJob -Name "Expire all data" -Namespace @("C:\Share01") -Schedule $task -Action $action
```

This example creates a file management job that expires all data in a namespace.

### Example 2: Create a file management job that expires data continuously
```
The first command gets a **DateTime** object and stores it in the variable $date.
PS C:\> $date = Get-Date "12:00am"

This second command returns a **FsrmScheduledTask** object that runs the task at midnight on the first day of the month. The command stores results in the $task variable.
PS C:\> $task = New-FsrmScheduledTask -Time $date -Monthly 1

The third command returns an action object for a management job and stores the results in the $action variable. The command specifies an expiration action and specifies a path that the action uses to expire files.
PS C:\> $action = New-FsrmFmjAction -Type Expiration -ExpirationFolder "C:\Expire"

The fourth command creates a file management job named "Expire all data" for the folder C:\Share01. The command specifies the schedule stored in the $task variable, specifies the action stored in the $action variable, and specifies that the server continuously apply classification to files in the background.
PS C:\> New-FsrmFileManagementJob -Name "Expire all data" -Namespace @("C:\Share01") -Schedule $task -Action $action -Continuous
```

This example creates a file management job that expires data in a namespace when the server runs the file management job and when a file is modified or classified.

### Example 3: Create a file management job that sends notifications
```
The first command gets a **DateTime** object and stores it in the variable $date.
PS C:\> $date = Get-Date "12:00am"

This second command returns a **FsrmScheduledTask** object that runs the task at midnight on the first day of the month. The command stores results in the $task variable.
PS C:\> $task = New-FsrmScheduledTask -Time $date -Monthly 1

The third command returns an action object for a management job and stores the results in the $action variable. The command specifies an expiration action and specifies a path that the action uses to expire files.
PS C:\> $action = New-FsrmFmjAction -Type Expiration -ExpirationFolder "C:\Expire"

The fourth command returns a notification action object that sends the specified email message to the administrator and file owner. The command specifies that the action can attach a maximum of 1000 files to the message. The command stores the results in the $notificationaction variable.
PS C:\> $notificationaction = New-FsrmFmjNotificationAction -Type Email -MailTo "[Admin Email];[File Owner]" -Subject "Warning: Files will expire soon" -Body "The attached list of files will expire in 30 days." -AttachmentFileListSize 1000

The fifth command returns a notification object for a file management job that runs the notification action stored in the $notificationaction variable 30 days before the file management job acts. The command stores the results in the $notification variable.
PS C:\> $notification = New-FsrmFmjNotification -Days 30 -Action $notificationaction

The sixth command creates a file management job named "Expire all data" for the folder C:\Share01. The command specifies the schedule stored in the $task variable, specifies the action stored in the $action variable, and specifies the notification stored in the $notification variable.
PS C:\> New-FsrmFileManagementJob -Name "Expire all data" -Namespace @("C:\Share01") -Schedule $task -Action $action -Notification $notification
```

This example creates a file management job that expires data in a namespace and sends an email notice to the file owner and administrator 30 days before the server runs the file management job.

### Example 4: Create a conditional file management job
```
The first command gets a **DateTime** object and stores it in the variable $date.
PS C:\> $date = Get-Date "12:00am"

This second command returns an **FsrmScheduledTask** object that runs the task at midnight on the first day of the month. The command stores results in the $task variable.
PS C:\> $task = New-FsrmScheduledTask -Time $date -Monthly 1

The third command returns an action object for a management job and stores the results in the $action variable. The command specifies an expiration action and specifies a path that the action uses to expire files.
PS C:\> $action = New-FsrmFmjAction -Type Expiration -ExpirationFolder "C:\Expire"

The fourth command returns a condition object for file management job that verifies that a file has a PII classification property set to true. The command stores the results in the $condition variable.
PS C:\> $condition = New-FsrmFmjCondition -Property "PII" -Condition Equal -Value "1"

The fifth command creates a file management job named "Expire all data" for the folder C:\Share01. The command specifies the schedule stored in the $task variable, specifies the action stored in the $action variable, and specifies the condition stored in the $condition variable.
PS C:\> New-FsrmFileManagementJob -Name "Expire all data" -Namespace @("C:\Share01") -Schedule $task -Action $action -Condition $condition
```

This example creates a file management job that expires all files that have the PII property set to true.

## PARAMETERS

### -Action
Specifies a **FsrmFmjAction** object.
You can use the **New-FsrmFmjAction** cmdlet to create a **FsrmFmjAction** object.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Condition
Specifies a **FsrmFmjCondition** object.
You can use the **New-FsrmFmjCondition** cmdlet to create a **FsrmFmjCondition** object.

```yaml
Type: CimInstance[]
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Continuous
Indicates that the server continuously applies classification to files in the background.

If you specify this parameter, you cannot specify any notifications and the conditions that you specify cannot include any objects where the classification property is set to the following values:
- File.DateCreated
- File.DateLastModified
- File.DateLastAccessed

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContinuousLog
Indicates that the server maintains a log of continuous classification activities.
You must specify the *Continuous* parameter to log classification activities.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContinuousLogSize
Specifies the maximum size of the log that contains continuous classification activity.
You must specify the *Continuous* parameter to log classification activities.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description for the file management job.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disabled
Indicates that the file management job is disabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MailTo
Specifies a semicolon-separated list of email addresses to which the file server sends the email.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the file management job.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Specifies an array of namespaces that are part of the scope.
Each value must be either a value of the FolderType property defined on the server (in the format "\[Folder type property name=\<value\>\]") or a static path.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Notification
Specifies a **FsrmFmjNotificationAction** object.
You can use the **New-FsrmFmjNotificationAction** cmdlet to create a **FsrmFmjNotificationAction** object.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Parameters
Specifies an array of strings of the form \<name\>=\<value\>.
The File Classification Infrastructure and other management tools use these parameters.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportFormat
Specifies an array of report formats that the file management job produces.
The acceptable values for this parameter are:

- DHTML
- HTML
- XML
- CSV
- Text

```yaml
Type: FmjReportFormatsEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: DHtml, Html, Text, Csv, XML

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportLog
Specifies an array of report types that the file management job generates.
The acceptable values for this parameter are:

- Information
- Error
- Audit

```yaml
Type: FmjReportLogsEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: Error, Information, Audit

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Schedule
Specifies a File Server Resource Manager (FSRM) scheduled task object that describes the schedule for performing the continuous classification.
Use the **New-FsrmScheduledTask** cmdlet to create a scheduled task object.
Any duration information in the FSRM scheduled task object is ignored.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Management.Automation.SwitchParameter

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjReportFormatsEnum[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjReportLogsEnum[]

### System.UInt64

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-FsrmFileManagementJob](./Get-FsrmFileManagementJob.md)

[New-FsrmFmjAction](./New-FsrmFmjAction.md)

[New-FsrmFmjCondition](./New-FsrmFmjCondition.md)

[New-FsrmFMJNotification](./New-FsrmFMJNotification.md)

[New-FsrmFmjNotificationAction](./New-FsrmFmjNotificationAction.md)

[New-FsrmScheduledTask](./New-FsrmScheduledTask.md)

[Remove-FsrmFileManagementJob](./Remove-FsrmFileManagementJob.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[Start-FsrmFileManagementJob](./Start-FsrmFileManagementJob.md)

[Stop-FsrmFileManagementJob](./Stop-FsrmFileManagementJob.md)

[Wait-FsrmFileManagementJob](./Wait-FsrmFileManagementJob.md)

