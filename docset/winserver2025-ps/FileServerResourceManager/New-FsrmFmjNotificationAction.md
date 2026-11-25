---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmFmjNotificationAction.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfmjnotificationaction?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmFmjNotificationAction
---

# New-FsrmFmjNotificationAction

## SYNOPSIS
Returns a notification action object for file management jobs.

## SYNTAX

```
New-FsrmFmjNotificationAction [-Type] <FmjNotificationActionTypeEnum> [-MailTo <String>] [-MailCC <String>]
 [-MailBCC <String>] [-Subject <String>] [-Body <String>] [-AttachmentFileListSize <UInt32>]
 [-EventType <FmjNotificationActionEventTypeEnum>] [-Command <String>] [-WorkingDirectory <String>]
 [-CommandParameters <String>] [-SecurityLevel <FmjNotificationActionSecurityLevelEnum>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmFmjNotificationAction** cmdlet returns a notification action object that you can use to create file management job actions.
You can use the **FsrmFMJNotificationAction** object as input for the following File Server Resource Manager (FSRM) cmdlets:

- New-FsrmFileManagementJob
- Set-FsrmFileManagementJob
- New-FsrmFileScreen
- Set-FsrmFileScreen
- New-FsrmFileScreenTemplate
- Set-FsrmFileScreenTemplate

The **FsrmFmjAction** object defines an action that the server performs when the notification period is reached.
This cmdlet supports the following actions:

- Email
- Event
- Command

## EXAMPLES

### Example 1: Create an email notification action
```
PS C:\> New-FsrmFmjNotificationAction -Type Email -MailTo "[Admin Email];[File Owner]" -Subject "Warning: Files will expire soon" -Body "The attached list of files will expire in 30 days." -AttachmentFileListSize 1000
```

This command returns a notification action object that sends the specified email message to the administrator and file owner.
The command specifies that the action can attach a maximum of 1000 files to the message.

### Example 2: Create an event notification action
```
PS C:\> New-FsrmFmjNotificationAction -Type Event -EventType Information -Body "Files will expire in 30 days."
```

This command returns a notification action object that logs an information event that contains the message Files will expire in 30 days.
The server logs the event when an event that you associated with the action occurs.

### Example 3: Create a command notification action
```
PS C:\> New-FsrmFmjNotificationAction -Type Command -Command "c:\windows\system32\cmd.exe" -CommandParameters "echo [source file path] >> c:\log.txt"
```

This command returns a notification action object that runs Cmd.exe and logs the output in a file named Log.txt.
The server runs Cmd.exe when an event that you associated with the action occurs.

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

### -AttachmentFileListSize
Specifies the maximum number of files that the list can include.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Body
Specifies the content of an email.
If you specify this parameter, you specify Email or Event for the *Type* parameter.

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
Specifies the command that the action runs.
If you specify a command, you must specify Custom for the *Type* parameter.

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
Specifies the parameters that the action passes to the command when the action runs.
If you specify parameters for a command, you must specify Custom for the *Type* parameter.

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
If you specify an event type, you must specify Event for the *Type* parameter.
The acceptable values for this parameter are:

- None
- Information
- Warning
- Error

```yaml
Type: FmjNotificationActionEventTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: None, Information, Warning, Error

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MailBCC
Specifies a semicolon-separated list of email addresses for the Bcc recipients  of an email.
Valid email addresses are an administrator email account or the owner of the file.
If you specify this parameter, you must specify Email for the *Type* parameter.

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
If you specify this parameter, you must specify Email for the *Type* parameter.

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
If you specify this parameter, you must specify Email for the *Type* parameter.

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

### -SecurityLevel
Specifies the computer account type under which the executable program or script runs.
The acceptable values for this parameter are:

- LocalService
- NetworkService
- LocalSystem

The default value is LocalService.
If you specify this parameter, you must specify Command for the *Type* parameter.

```yaml
Type: FmjNotificationActionSecurityLevelEnum
Parameter Sets: (All)
Aliases:
Accepted values: None, NetworkService, LocalService, LocalSystem

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject
Specifies the subject of an email.
The maximum size of a subject is 1 KB.
If you specify this parameter, you must specify Email for the *Type* parameter.

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
Specifies the type of notification action.
The acceptable values for this parameter are:

- Email
- Event
- Command

```yaml
Type: FmjNotificationActionTypeEnum
Parameter Sets: (All)
Aliases:
Accepted values: Event, Email, Command

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
Specifies the working directory in which the executable program or script runs.
You must specify a valid path to a folder.
File Server Resource Manager (FSRM) does not support paths to remote computers.

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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjNotificationActionTypeEnum

### System.String

### System.UInt32

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjNotificationActionEventTypeEnum

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FmjNotificationActionSecurityLevelEnum

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[New-FsrmFMJNotification](./New-FsrmFMJNotification.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[New-FsrmFileScreen](./New-FsrmFileScreen.md)

[Set-FsrmFileScreen](./Set-FsrmFileScreen.md)

[New-FsrmFileScreenTemplate](./New-FsrmFileScreenTemplate.md)

[Set-FsrmFileScreenTemplate](./Set-FsrmFileScreenTemplate.md)

