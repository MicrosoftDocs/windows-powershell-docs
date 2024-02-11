---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmSetting.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmsetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FsrmSetting
---

# Set-FsrmSetting

## SYNOPSIS
Changes global FSRM settings for the computer.

## SYNTAX

```
Set-FsrmSetting [-InputObject <CimInstance[]>] [-SmtpServer <String>] [-FromEmailAddress <String>]
 [-AdminEmailAddress <String>] [-EmailNotificationLimit <Int32>] [-EventNotificationLimit <Int32>]
 [-CommandNotificationLimit <Int32>] [-ReportNotificationLimit <Int32>] [-ReportLimitMaxFile <Int32>]
 [-ReportLimitMaxFileGroup <Int32>] [-ReportLimitMaxOwner <Int32>] [-ReportLimitMaxFilesPerFileGroup <Int32>]
 [-ReportLimitMaxFilesPerOwner <Int32>] [-ReportLimitMaxFilesPerDuplicateGroup <Int32>]
 [-ReportLimitMaxDuplicateGroup <Int32>] [-ReportLimitMaxQuota <Int32>]
 [-ReportLimitMaxFileScreenEvent <Int32>] [-ReportLimitMaxPropertyValue <Int32>]
 [-ReportLimitMaxFilesPerPropertyValue <Int32>] [-ReportLocationIncident <String>]
 [-ReportLocationScheduled <String>] [-ReportLocationOnDemand <String>]
 [-ReportFileScreenAuditDaysSince <Int32>] [-ReportFileScreenAuditUser <String[]>]
 [-ReportFileGroupIncluded <String[]>] [-ReportFileOwnerUser <String[]>] [-ReportFileOwnerFilePattern <String>]
 [-ReportPropertyName <String>] [-ReportPropertyFilePattern <String>] [-ReportLargeFileMinimum <UInt64>]
 [-ReportLargeFilePattern <String>] [-ReportLeastAccessedMinimum <Int32>]
 [-ReportLeastAccessedFilePattern <String>] [-ReportMostAccessedMaximum <Int32>]
 [-ReportMostAccessedFilePattern <String>] [-ReportQuotaMinimumUsage <Int32>] [-ReportFileScreenAuditEnable]
 [-ReportClassificationFormat <FsrmReportClassificationFormatEnum[]>] [-ReportClassificationMailTo <String>]
 [-ReportClassificationLog <FsrmReportClassificationLogEnum[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmSetting** cmdlet changes global File Server Resource Manager (FSRM) settings for the computer.

## EXAMPLES

### Example 1: Change the FSRM setting for administrator email address
```
PS C:\> Set-FsrmSetting -AdminEmailAddress "john@contoso.com"
```

This command specifies the address "john@contoso.com" for the recipient of email that the server sends to the administrator.

### Example 2: Change the FSRM setting for command notification limit
```
PS C:\> Set-FsrmSetting -CommandNotificationLimit 80
```

This command specifies 80 as the minimum number of minutes between individual running events of a command-type notification.

### Example 3: Change the FSRM setting for report classification format
```
PS C:\> Set-FsrmSetting -ReportClassificationFormat @('Xml')
```

This command specifies XML as the format of classification reports that the server generates.

### Example 4: Change the FSRM setting for report classification log type
```
PS C:\> Set-FsrmSetting -ReportClassificationLog @('ErrorsInSystemLog')
```

This command specifies ErrorsInSystemLog as the type of log that the File Classification Infrastructure generates during classification.

### Example 5: Change the FSRM settings for large file reports and quota usage reports
```
PS C:\> Set-FsrmSetting -ReportLargeFilePattern '*' -ReportLimitMaxQuota 100
```

This command specifies the wildcard character (*) to indicate that the large file report includes any files that match the value set for the **ReportLargeFileMinimum** parameter.
The command also specifies that 100 is the maximum number of quotas to include in a quota usage report.

### Example 6: Change the FSRM setting for the SMTP server and file by owner reports
```
PS C:\> Set-FsrmSetting -SmtpServer "10.121.24.132" -ReportFileOwnerFilePattern "*.xml"
```

This command specifies 10.121.24.132 as the IP address of the SMTP server that FSRM uses to send email.
The command also specifies *.XML as the file pattern to match for the file by owner report.

## PARAMETERS

### -AdminEmailAddress
Specifies a semicolon-separated list of email addresses for the recipients of any email that the server sends to the administrator.

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

### -CommandNotificationLimit
Specifies the minimum number of minutes between individual running events of a command-type notification.
If multiple command notifications occur, the server runs the command notification only if at least this amount of time has passed since the server last performed this action.

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EmailNotificationLimit
Specifies the minimum number of minutes between individual running events of an email-type notification.
If multiple command notifications occur, the server runs the command notification only if at least this amount of time has passed since the server last performed this action.

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

### -EventNotificationLimit
Specifies the minimum number of minutes between individual running events of an event-type notification.
If multiple command notifications occur, the server runs the command notification only if at least this amount of time has passed since the server last performed this action.

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

### -FromEmailAddress
Specifies the default email address from which FSRM sends email messages.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -ReportClassificationFormat
Specifies an array of formats of classification reports that the server generates.
The acceptable values for this parameter are:

- DHTML
- HTML
- XML
- CSV
- Text

```yaml
Type: FsrmReportClassificationFormatEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: DHtml, Html, Text, Csv, Xml

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportClassificationLog
Specifies an array of types of logs that the File Classification Infrastructure can generate during classification.
The acceptable values for this parameter are:

- None
- ClassificationsInLogFile
- ErrorsInLogFile
- ClassificationsInSystemLog
- ErrorsInSystemLog

```yaml
Type: FsrmReportClassificationLogEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: ClassificationsInLogFile, ErrorsInLogFile, ClassificationsInSystemLog, ErrorsInSystemLog

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportClassificationMailTo
Specifies a semicolon-separated list of email addresses.
The server sends the classification reports to the email addresses after a scheduled classification is complete.

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

### -ReportFileGroupIncluded
Specifies an array of names of file groups to include in the report.
Each string must be the name of a valid file group.

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

### -ReportFileOwnerFilePattern
Specifies a file pattern string that indicates which files to include in the file by owner report.
You can use the wildcard characters \* and ?
in the string.

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

### -ReportFileOwnerUser
Specifies an array of users, in Domain\User format, to include files for in the file by owner report.
The default value is an empty list, which indicates all users.

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

### -ReportFileScreenAuditDaysSince
Specifies the minimum number of days since the audit event to include in the report.

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

### -ReportFileScreenAuditEnable
Indicates that file screen auditing is enabled.

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

### -ReportFileScreenAuditUser
Specifies an array of user email addresses to include audit events for.
The default value is an empty list, which indicates all users.

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

### -ReportLargeFileMinimum
Specifies the minimum file size to include in the large file report.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportLargeFilePattern
Specifies a string of files to include in the large file report.
You can use the wildcard characters \* and ?
in the string.

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

### -ReportLeastAccessedFilePattern
Specifies a string of files to include in the least frequently accessed report.
You can use the wildcard characters \* and ?
in the string.

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

### -ReportLeastAccessedMinimum
Specifies the minimum number of days since the report was last accessed, to include in the least frequently accessed report.

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

### -ReportLimitMaxDuplicateGroup
Specifies the maximum number of groups of duplicate files to include in the duplicate files report.

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

### -ReportLimitMaxFile
Specifies the maximum number of files to include in a storage report.

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

### -ReportLimitMaxFileGroup
Specifies the maximum number of file groups to include in a file group report.

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

### -ReportLimitMaxFileScreenEvent
Specifies the maximum number of file screens events to include in a file screen audit report.

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

### -ReportLimitMaxFilesPerDuplicateGroup
Specifies the maximum number of files in an individual duplicate group to include in a duplicate files report.

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

### -ReportLimitMaxFilesPerFileGroup
Specifies the maximum number of files in any file group to include in a file group report.

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

### -ReportLimitMaxFilesPerOwner
Specifies the maximum number of files for any owner to include in a files by owner report.

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

### -ReportLimitMaxFilesPerPropertyValue
Specifies the maximum number of files for each property value to include in a files by property report.

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

### -ReportLimitMaxOwner
Specifies the maximum number of owners to include in a files by owner report.

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

### -ReportLimitMaxPropertyValue
Specifies the maximum number of property values to include in a files by property report.

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

### -ReportLimitMaxQuota
Specifies the maximum number of quotas to include in a quota usage report.

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

### -ReportLocationIncident
Specifies a path to a folder where the server stores incident reports.

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

### -ReportLocationOnDemand
Specifies a path to a folder where the server stores on demand reports.

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

### -ReportLocationScheduled
Specifies a path to a folder where the server stores scheduled reports.

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

### -ReportMostAccessedFilePattern
Specifies a string of files to include in the most frequently accessed report.
You can use the wildcard characters \* and ?
in the string.

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

### -ReportMostAccessedMaximum
Specifies the maximum number of days since the report was last accessed, to include in the most frequently accessed report.

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

### -ReportNotificationLimit
Specifies the minimum number of minutes between individual running events of a report notification.
If multiple report notifications occur, the server runs the report notification only if at least this amount of time have passed since the server last performed this action.

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

### -ReportPropertyFilePattern
Specifies a string of files to include in the file by property report.
You can use the wildcard characters \* and ?
in the string.

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

### -ReportPropertyName
Specifies the property name to report on for a file by property report.

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

### -ReportQuotaMinimumUsage
Specifies the minimum quota usage level to include in the quota usage report.

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

### -SmtpServer
Specifies the fully qualified domain name (FQDN) or IP address of the SMTP server that FSRM uses to send email.

You can use the **Send-FsrmTestEmail** cmdlet to send an email messages to test the SMTP server that you specify.

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

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMSettings

## NOTES

## RELATED LINKS

[Get-FsrmSetting](./Get-FsrmSetting.md)

