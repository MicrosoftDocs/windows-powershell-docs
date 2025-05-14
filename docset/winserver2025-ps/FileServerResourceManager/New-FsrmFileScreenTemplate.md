---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmFileScreenTemplate.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmfilescreentemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmFileScreenTemplate
---

# New-FsrmFileScreenTemplate

## SYNOPSIS
Creates a file screen template.

## SYNTAX

```
New-FsrmFileScreenTemplate [-Name] <String> [-Description <String>] [-IncludeGroup <String[]>] [-Active]
 [-Notification <CimInstance[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmFileScreenTemplate** cmdlet creates a file screen template.
A file screen template defines the group of file groups to block, the type of screening to perform (active or passive), and the set of notifications that the file screen generates.

You can use file screen templates to centrally manage your file screens by updating the templates instead of the individual file screens.
When you make changes to a template, you can choose to apply those changes to all file screens that are based on that template or only to the file screens whose properties match those in the template.

## EXAMPLES

### Example 1: Create a passive file screen template
```
PS C:\> New-FsrmFileScreenTemplate "Filter Non-HTML text files" -IncludeGroup "Non-HTML text files"
```

This command creates a passive file screen template named "Filter Non-HTML text files" that logs any files that match the "Non-HTML text files" file group.
The file screen template is passive because the command does not specify the *Active* parameter.
This means that users can create non-HTML text files.

### Example 2: Create an active file screen template
```
PS C:\> $Notification = New-FsrmAction -Type Email -MailTo "[Admin Email];[File Owner]" -Subject "Warning: attempted to create a non-HTML text file" -Body "You attempted to create a non-HTML text file. This is not allowed." -RunLimitInterval 120
PS C:\> New-FsrmFileScreenTemplate -Name "Filter Non-HTML text files" -IncludeGroup "Non-HTML text files" -Notification $Notification -Active
```

The first command creates a File Server Resource Manager (FSRM) action object and stores the results in the $Notification variable.
The action sends an email notification to the file owner and administrator.
The *RunLimitInterval* parameter specifies an interval of 2 minutes before the server can send the email notification again.

This second command creates an active file screen template named "Filter Non-HTML text files" that restricts any files that match the Non-HTML text files file group.
When a user attempts to create a non-HTML text file, the file screen performs the notification action stored in the $Notification variable.

## PARAMETERS

### -Active
Indicates that the server will fail any I/O operation that violates the file screen.
If you do not specify this parameter, the server does not fail violating I/O operations and still runs any action that is associated with the file screen.

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

### -Description
Specifies a description for the file screen template.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeGroup
Specifies an array of names of file groups that you want to exclude from file screening.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name for the file screen template.

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

### -Notification
Specifies an array of notification action objects.
You can use the New-New-FsrmFmjNotificationAction cmdlet to create a **FsrmFmjNotificationAction** object.

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

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-FsrmFileScreenTemplate](./Get-FsrmFileScreenTemplate.md)

[New-FsrmAction](./New-FsrmAction.md)

[Remove-FsrmFileScreenTemplate](./Remove-FsrmFileScreenTemplate.md)

[Set-FsrmFileScreenTemplate](./Set-FsrmFileScreenTemplate.md)

