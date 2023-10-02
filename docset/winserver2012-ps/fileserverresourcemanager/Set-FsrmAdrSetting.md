---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmadrsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-FsrmAdrSetting

## SYNOPSIS
Changes configuration settings for access denied remediation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmAdrSetting [-Event] <FsrmAdrEventEnum[]> [-AllowRequests] [-AsJob] [-CimSession <CimSession[]>]
 [-DeviceTroubleshooting] [-DisplayMessage <String>] [-EmailMessage <String>] [-Enabled] [-EventLog]
 [-IncludeDeviceClaims] [-IncludeUserClaims] [-MailCCAdmin] [-MailTo <String>] [-MailToOwner] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmAdrSetting [-AllowRequests] [-AsJob] [-CimSession <CimSession[]>] [-DeviceTroubleshooting]
 [-DisplayMessage <String>] [-EmailMessage <String>] [-Enabled] [-EventLog] [-IncludeDeviceClaims]
 [-IncludeUserClaims] [-MailCCAdmin] [-MailTo <String>] [-MailToOwner] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmAdrSetting** cmdlet changes configuration settings for access denied remediation (ADR) for one or more events.
The File Server Resource Manager (FSRM) uses the ADR settings when a client cannot access a file.
Users get an access-denied message when they try to access shared files and folders on a file server for which they do not have permissions.

## EXAMPLES

### Example 1: Change ADR settings for an event
```
PS C:\>Set-FsrmAdrSetting -Event AccessDenied -Enabled -DisplayMessage "Access to file is denied" -EmailMessage "Access to file is denied. You can email a request for permission to access the file." -AllowRequests -MailToOwner:$false -MailCCAdmin -MailTo "john@contoso.com" -IncludeDeviceClaims -IncludeUserClaims -EventLog -DeviceTroubleShooting
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

## NOTES

## RELATED LINKS

[Get-FsrmAdrSetting](./Get-FsrmAdrSetting.md)

