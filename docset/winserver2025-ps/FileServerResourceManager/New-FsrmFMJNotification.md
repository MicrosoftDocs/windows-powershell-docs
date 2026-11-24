---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMFmjNotification.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfmjnotification?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmFMJNotification
---

# New-FsrmFMJNotification

## SYNOPSIS
Returns a notification object for file management jobs.

## SYNTAX

```
New-FsrmFMJNotification [-Days] <UInt32> [-Action <CimInstance[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmFMJNotification** cmdlet returns a notification object that you can use to create file management job actions.
You can use the **FsrmFMJNotification** object as input for the **New-FsrmFileManagementJob** cmdlet and the **Set-FsrmFileManagementJob** cmdlet.

The **FsrmFmjAction** object defines a notification period before a file management job acts on a file.
This cmdlet supports the following actions:

- Email
- Event
- Command

## EXAMPLES

### Example 1: Create a notification for file management jobs
```
PS C:\> $action = New-FsrmFmjNotificationAction -Type Email -MailTo "[Admin Email];[File Owner]" -Subject "Warning: Files will expire soon" -Body "The attached list of files will expire in 30 days." -AttachmentFileListSize 1000
PS C:\> New-FsrmFmjNotification -Days 30 -Action $action
```

The first command returns an object that represents a notification action.
The notification action sends the specified email message to the administrator and file owner, and specifies that the action can attach a maximum of 1000 files to the message.
The command stores the notification action object in the $action variable.

The second command returns a notification object for a file management job that runs the notification action stored in the $action variable 30 days before the file management job acts.

## PARAMETERS

### -Action
Specifies an array of file management job actions.
You can create a job action by using the **New-FsrmFmjAction** cmdlet.

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

### -Days
Specifies the number of days before a file management job acts on a file to run the notification action.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### System.UInt32

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

## NOTES

## RELATED LINKS

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[New-FsrmFmjAction](./New-FsrmFmjAction.md)

[New-FsrmFmjNotificationAction](./New-FsrmFmjNotificationAction.md)

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

