---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmAction.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmAction
---

# New-FsrmAction

## SYNOPSIS
Returns an FSRM action object.

## SYNTAX

```
New-FsrmAction [-Type] <ActionTypeEnum> [-MailTo <String>] [-MailCC <String>] [-MailBCC <String>]
 [-Subject <String>] [-Body <String>] [-EventType <ActionEventTypeEnum>] [-Command <String>]
 [-WorkingDirectory <String>] [-CommandParameters <String>] [-SecurityLevel <ActionSecurityLevelEnum>]
 [-KillTimeOut <Int32>] [-ShouldLogError] [-ReportTypes <ActionReportTypeEnum[]>] [-RunLimitInterval <Int32>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmAction** cmdlet returns a File Server Resource Manager (FSRM) action object.
An **FsrmAction** object does not contain the trigger for the action.
You can pass the action object to other cmdlets that use notifications and quota thresholds.

An **FsrmAction** object encapsulates a single action, such as sending an email.
FSRM does not save an action object unless it is used as part of another object.
For example, you can use an **FsrmAction** object to create notifications and quota thresholds.
The saved object provides the trigger for the action.

The **New-FsrmAction** cmdlet supports the following actions:

- Email: Send email to the user or administrator that the event triggered
- Event: Create an event log entry
- Command: Run a command that the administrator specifies
- Report: Run one or more storage reports

## EXAMPLES

### Example 1: Create an action that sends an email
```
PS C:\> New-FsrmAction Email -MailCC "john.smith@contosco.com" -MailTo "sarah.jones@contosco.com" -Subject "Warning: Approaching storage limit" -Body "You are about to reach the end of your available storage."
```

This command returns an object that indicates that the server sends an email when an associated event occurs.
The recipient of the email is the user sarah.jones@contosco.com and the CC recipient of the email is the administrator, john.smith@contosco.com.

### Example 2: Create an action that has a run limit
```
PS C:\> New-FsrmAction Email -MailTo "john.smith@contosco.com;sarah.jones@contosco.com" -Subject "Warning: Approaching storage limit" -Body "You are about to reach the end of your available storage." -RunLimitInterval 120
```

This command returns an object that indicates that the server sends an email to the administrator and the file owner when an associated event occurs.
The command specifies that the event can trigger no more than once every 120 minutes.
If the event does trigger, the action will have no effect before the time interval passes.

### Example 3: Create an action that logs an event
```
PS C:\> New-FsrmAction Event -EventType Information -Body "The user [File Owner] is about to reach the end of his available storage." -RunLimitInterval 180
```

This command returns an object that indicates the server logs an event that contains the specified message when an associated event occurs.
The event should trigger no more than once every 180 minutes.
If the event does trigger, no additional event log entries are created before the time interval passes.

### Example 4: Create an action that runs a command and logs errors
```
PS C:\> New-FsrmAction Command -Command "c:\windows\system32\cmd.exe"-CommandParameters "echo [source file path] >> c:\log.txt" -ShouldLogError
```

This command returns an object that indicates that when an associated event occurs, the server runs Cmd.exe with the specified parameters.
The command specifies that the server records errors codes from the command in the error log.

### Example 5: Create an action that runs a storage report
```
PS C:\> New-FsrmAction Report -ReportType @(LargeFiles, DuplicateFiles)
```

This command returns an object that indicates that the server runs LargeFiles and DuplicateFiles reports when an associated event occurs.

## PARAMETERS

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

### -Body
Specifies the content of an email.
If you specify this parameter, you must set Email or Event Specify for the *Type* parameter.

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

### -Command
Specifies the full path to the program or script.
If you specify this parameter, you must set Command for the *Type* parameter.

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

### -CommandParameters
Specifies the parameters for the program or script.
If you specify this parameter, you must set Command for the *Type* parameter.

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

### -EventType
Specifies the event type of the action.
If you specify this parameter, you must set Event for the *Type* parameter.
The acceptable values for this parameter are:

- None
- Information
- Warning
- Error

```yaml
Type: ActionEventTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: None, Information, Warning, Error

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KillTimeOut
Specifies the timeout period, in minutes, after which the process that the action created is ended.
Specify the default, -1, to indicate that the server does not end the process.
If you specify this parameter, you must set Command for the *Type* parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MailBCC
Specifies a semicolon-separated list of email addresses for the Bcc recipients of an email.
Valid email addresses are an administrator email account or the owner of the file.
If you specify this parameter, you must set Email for the *Type* parameter.

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

### -MailCC
Specifies a semicolon-separated list of email addresses for the Cc recipients of an email.
Valid email addresses are an administrator email account or the owner of the file.
If you specify this parameter, you must set Email for the *Type* parameter.

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

### -MailTo
Specifies a semicolon-separated list of email addresses for the recipients of an email.
Valid email addresses are an administrator email account or the owner of the file.
If you specify this parameter, you must set Email for the *Type* parameter.

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

### -ReportTypes
Specifies an array of report types that the action generates.
If you specify this parameter, you must set Report for the *Type* parameter.
The acceptable values for this parameter are:

- DuplicateFiles
- FilesByFileGroup
- FilesByOwner
- FilesByProperty
- LargeFiles
- LeastRecentlyAccessed
- MostRecentlyAccessed
- QuotaUsage

```yaml
Type: ActionReportTypeEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: LargeFiles, FilesByFileGroup, LeastRecentlyAccessed, MostRecentlyAccessed, QuotaUsage, FilesByOwner, DuplicateFiles, FileScreenAuditFiles, FilesByProperty

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunLimitInterval
Specifies the minimum interval, in minutes, before the server can run the action again.
For example, if the interval expired since the action last ran, the server runs the action again in response to an event; otherwise, the server cannot run the action again.
The default value, 60, specifies that there is no limit.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityLevel
Specifies the computer account type under which the program or script runs.
The acceptable values for this parameter are:

- LocalService
- NetworkService
- LocalSystem

```yaml
Type: ActionSecurityLevelEnum
Parameter Sets: (All)
Aliases:
Accepted values: None, NetworkService, LocalService, LocalSystem

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShouldLogError
Indicates that the server records errors codes from running commands in the event log.

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

### -Subject
Specifies the subject of an email.
The maximum size of a subject is 1 KB.
If you specify this parameter, you must set Email for the *Type* parameter.

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

### -Type
Specifies the type of the action.
This setting determines the action that the server takes in response to a quota or file screen event.
The acceptable values for this parameter are:

- Email
- Event
- Command
- Report

```yaml
Type: ActionTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: Event, Email, Command, Report

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -WorkingDirectory
Specifies the working directory in which the program or script runs.
You must specify a valid path to a folder.
FSRM does not support paths to remote computers.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.ActionTypeEnum

### System.String

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.ActionEventTypeEnum

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.ActionSecurityLevelEnum

### System.Int32

### System.Management.Automation.SwitchParameter

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.ActionReportTypeEnum[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[New-FsrmQuotaThreshold](./New-FsrmQuotaThreshold.md)

[New-FsrmFileScreen](./New-FsrmFileScreen.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[New-FsrmScheduledTask](./New-FsrmScheduledTask.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[New-FsrmFMJNotification](./New-FsrmFMJNotification.md)

