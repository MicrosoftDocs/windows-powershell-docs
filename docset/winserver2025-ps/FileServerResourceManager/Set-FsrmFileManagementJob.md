---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FSRMFileManagementJob.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmfilemanagementjob?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FsrmFileManagementJob
---

# Set-FsrmFileManagementJob

## SYNOPSIS
Changes configuration settings of a file management job.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmFileManagementJob [-Name] <String[]> [-Description <String>] [-Namespace <String[]>] [-Disabled]
 [-Condition <CimInstance[]>] [-Action <CimInstance>] [-ReportFormat <FmjReportFormatsEnum[]>]
 [-ReportLog <FmjReportLogsEnum[]>] [-MailTo <String>] [-Notification <CimInstance[]>]
 [-Schedule <CimInstance>] [-Continuous] [-ContinuousLog] [-ContinuousLogSize <UInt64>]
 [-Parameters <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmFileManagementJob -InputObject <CimInstance[]> [-Description <String>] [-Namespace <String[]>]
 [-Disabled] [-Condition <CimInstance[]>] [-Action <CimInstance>] [-ReportFormat <FmjReportFormatsEnum[]>]
 [-ReportLog <FmjReportLogsEnum[]>] [-MailTo <String>] [-Notification <CimInstance[]>]
 [-Schedule <CimInstance>] [-Continuous] [-ContinuousLog] [-ContinuousLogSize <UInt64>]
 [-Parameters <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmFileManagementJob** cmdlet changes configuration settings of a file management job.
You must specify at least one other parameter in addition to the *Name* parameter.

## EXAMPLES

### Example 1: Change the condition for a file management job
```
The first command returns a condition object for file management job that verifies that a file has a PII classification property set to true. The command stores the results in the $condition variable.
PS C:\> $condition = New-FsrmFmjCondition -Property "PII" -Condition Equal -Value "1"

The second command gets the file management job named "Expire stale data" and stores the results in the $current variable.
PS C:\> $current = Get-FsrmFileManagementJob -Name "Expire stale data"

The third command adds the new condition to the existing conditions of the file management job.
PS C:\> $newConditions = $current.Conditions + $condition

The fourth command sets the condition of the file management job named "Expire stale data" to the condition stored in the $newConditions variable.
PS C:\> Set-FsrmFileManagementJob "Expire stale data" -Condition $newConditions
```

This example changes the file management job named Expire stale data to include only files that have the PII property set to true in addition to the existing conditions.

## PARAMETERS

### -Action
Specifies a **FsrmFmjAction** object.
You can use the **New-FsrmFmjAction** cmdlet to create a **FsrmFmjAction** object.

```yaml
Type: CimInstance
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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

### -MailTo
Specifies a semicolon-separated list of email addresses to which the file server sends the email.

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

### -Name
Specifies a name for the file management job.

```yaml
Type: String[]
Parameter Sets: Query (cdxml)
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Specifies an array of strings using the format \<name\>=\<value\>.
The File Classification Infrastructure and other management tools use these parameters.

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
Accept pipeline input: False
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
Accept pipeline input: False
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

### System.String[]

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMFileManagementJob

## NOTES

## RELATED LINKS

[Get-FsrmFileManagementJob](./Get-FsrmFileManagementJob.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[New-FsrmFmjCondition](./New-FsrmFmjCondition.md)

[New-FsrmFmjNotificationAction](./New-FsrmFmjNotificationAction.md)

[New-FsrmScheduledTask](./New-FsrmScheduledTask.md)

[Remove-FsrmFileManagementJob](./Remove-FsrmFileManagementJob.md)

[Start-FsrmFileManagementJob](./Start-FsrmFileManagementJob.md)

[Stop-FsrmFileManagementJob](./Stop-FsrmFileManagementJob.md)

[Wait-FsrmFileManagementJob](./Wait-FsrmFileManagementJob.md)

