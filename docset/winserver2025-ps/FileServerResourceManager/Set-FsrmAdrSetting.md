---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmAdrSetting.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmadrsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FsrmAdrSetting
---

# Set-FsrmAdrSetting

## SYNOPSIS
Changes configuration settings for access denied remediation.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmAdrSetting [-Event] <FsrmAdrEventEnum[]> [-Enabled] [-DisplayMessage <String>] [-EmailMessage <String>]
 [-AllowRequests] [-MailToOwner] [-MailCCAdmin] [-MailTo <String>] [-IncludeDeviceClaims] [-IncludeUserClaims]
 [-EventLog] [-DeviceTroubleshooting] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmAdrSetting -InputObject <CimInstance[]> [-Enabled] [-DisplayMessage <String>] [-EmailMessage <String>]
 [-AllowRequests] [-MailToOwner] [-MailCCAdmin] [-MailTo <String>] [-IncludeDeviceClaims] [-IncludeUserClaims]
 [-EventLog] [-DeviceTroubleshooting] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmAdrSetting** cmdlet changes configuration settings for access denied remediation (ADR) for one or more events.
The File Server Resource Manager (FSRM) uses the ADR settings when a client cannot access a file.
Users get an access-denied message when they try to access shared files and folders on a file server for which they do not have permissions.

## EXAMPLES

### Example 1: Change ADR settings for an event
```
PS C:\> Set-FsrmAdrSetting -Event AccessDenied -Enabled -DisplayMessage "Access to file is denied" -EmailMessage "Access to file is denied. You can email a request for permission to access the file." -AllowRequests -MailToOwner:$false -MailCCAdmin -MailTo "john@contoso.com" -IncludeDeviceClaims -IncludeUserClaims -EventLog -DeviceTroubleShooting
```

This command changes ADR settings for the AccessDenied event.
The command enables remediation for the AccessDenied event, specifies the display message and email message for the event, and indicates that users can request access by sending email.

## PARAMETERS

### -AllowRequests
Indicates that users can request access by sending email.

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

### -DeviceTroubleshooting
Indicates that Windows shows the user the device claims in the access-denied message.

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

### -DisplayMessage
Specifies the message that the file server displays to the user when the server receives the event.
The length of the string must not exceed 10KB.

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

### -EmailMessage
Specifies the email message that the file server sends to the user when the server receives the event.
The length of the string must not exceed 10KB.

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

### -Enabled
Indicates that remediation is enabled for events on this server.

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

### -Event
Specifies an array of types of events that ADR handles.
The acceptable values for this parameter are: AccessDenied and FileNotFound.

```yaml
Type: FsrmAdrEventEnum[]
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: AccessDenied, FileNotFound

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EventLog
Indicates that the server creates an Event Log entry for each access request email that the file server sends.

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

### -IncludeDeviceClaims
Indicates that the file server includes device claims when a user requests access.

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

### -IncludeUserClaims
Indicates that the file server includes user claims when a user requests access.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MailCCAdmin
Indicates that the file server includes the system administrator on the CC line of the email message when a user requests access.

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

### -MailTo
Specifies a semicolon-separated list of email addresses to which the file server sends the request.

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

### -MailToOwner
Indicates that the file server emails the data owner when a user requests access.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.FsrmAdrEventEnum[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMADRSettings

## NOTES

## RELATED LINKS

[Get-FsrmAdrSetting](./Get-FsrmAdrSetting.md)

