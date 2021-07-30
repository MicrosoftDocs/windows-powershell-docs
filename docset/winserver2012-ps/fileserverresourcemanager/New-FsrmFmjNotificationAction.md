---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://docs.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfmjnotificationaction?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-FsrmFmjNotificationAction

## SYNOPSIS
Returns a notification action object for file management jobs.

## SYNTAX

```
New-FsrmFmjNotificationAction [-Type] <FmjNotificationActionTypeEnum> [-AsJob]
 [-AttachmentFileListSize <UInt32>] [-Body <String>] [-CimSession <CimSession[]>] [-Command <String>]
 [-CommandParameters <String>] [-EventType <FmjNotificationActionEventTypeEnum>] [-MailBCC <String>]
 [-MailCC <String>] [-MailTo <String>] [-SecurityLevel <FmjNotificationActionSecurityLevelEnum>]
 [-Subject <String>] [-ThrottleLimit <Int32>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf]
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
PS C:\>New-FsrmFmjNotificationAction -Type Email -MailTo "[Admin Email];[File Owner]" -Subject "Warning: Files will expire soon" -Body "The attached list of files will expire in 30 days." -AttachmentFileListSize 1000
```

This command returns a notification action object that sends the specified email message to the administrator and file owner.
The command specifies that the action can attach a maximum of 1000 files to the message.

### Example 2: Create an event notification action
```
PS C:\>New-FsrmFmjNotificationAction -Type Event -EventType Information -Body "Files will expire in 30 days."
```

This command returns a notification action object that logs an information event that contains the message Files will expire in 30 days.
The server logs the event when an event that you associated with the action occurs.

### Example 3: Create a command notification action
```
PS C:\>New-FsrmFmjNotificationAction -Type Command -Command "c:\windows\system32\cmd.exe" -CommandParameters "echo [source file path] >> c:\log.txt"
```

This command returns a notification action object that runs Cmd.exe and logs the output in a file named Log.txt.
The server runs Cmd.exe when an event that you associated with the action occurs.

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

### -AttachmentFileListSize
Specifies the maximum number of files that the list can include.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Body
Specifies the content of an email.
If you specify this parameter, you specify Email or Event for the **Type** parameter.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
If you specify a command, you must specify Custom for the **Type** parameter.

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
If you specify parameters for a command, you must specify Custom for the **Type** parameter.

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

### -EventType
Specifies the event type of the action.
If you specify an event type, you must specify Event for the Type parameter.
The acceptable values for this parameter are:
- None
- Information
- Warning
- Error

```yaml
Type: FmjNotificationActionEventTypeEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MailBCC
Specifies a semicolon-separated list of email addresses for the Bcc recipients  of an email.
Valid email addresses are an administrator email account or the owner of the file.
If you specify this parameter, you must specify Email for the **Type** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MailCC
Specifies a semicolon-separated list of email addresses for the Cc recipients of an email.
Valid email addresses are an administrator email account or the owner of the file.
If you specify this parameter, you must specify Email for the **Type** parameter.

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
If you specify this parameter, you must specify Email for the **Type** parameter.

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
If you specify this parameter, you must specify Command for the **Type** parameter.

```yaml
Type: FmjNotificationActionSecurityLevelEnum
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: LocalService
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject
Specifies the subject of an email.
The maximum size of a subject is 1 KB.
If you specify this parameter, you must specify Email for the **Type** parameter.

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

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFMJNotificationAction

## NOTES

## RELATED LINKS

[New-FsrmFMJNotification](./New-FsrmFMJNotification.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[New-FsrmFileScreen](./New-FsrmFileScreen.md)

[Set-FsrmFileScreen](./Set-FsrmFileScreen.md)

[New-FsrmFileScreenTemplate](./New-FsrmFileScreenTemplate.md)

[Set-FsrmFileScreenTemplate](./Set-FsrmFileScreenTemplate.md)

