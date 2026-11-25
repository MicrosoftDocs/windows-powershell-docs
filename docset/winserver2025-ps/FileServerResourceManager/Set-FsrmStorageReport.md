---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmStorageReport.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/set-fsrmstoragereport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-FsrmStorageReport
---

# Set-FsrmStorageReport

## SYNOPSIS
Changes settings of a storage report.

## SYNTAX

### Query (cdxml) (Default)
```
Set-FsrmStorageReport [-Name] <String[]> [-Namespace <String[]>] [-ReportType <StorageReportReportTypeEnum[]>]
 [-FileScreenAuditDaysSince <UInt32>] [-FileScreenAuditUser <String[]>] [-FileGroupIncluded <String[]>]
 [-FileOwnerUser <String[]>] [-FileOwnerFilePattern <String>] [-PropertyName <String>]
 [-FolderPropertyName <String>] [-PropertyFilePattern <String>] [-LargeFileMinimum <UInt64>]
 [-LargeFilePattern <String>] [-LeastAccessedMinimum <UInt32>] [-LeastAccessedFilePattern <String>]
 [-MostAccessedMaximum <UInt32>] [-MostAccessedFilePattern <String>] [-QuotaMinimumUsage <UInt32>]
 [-ReportFormat <StorageReportReportFormatsEnum[]>] [-MailTo <String>] [-Schedule <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-FsrmStorageReport -InputObject <CimInstance[]> [-Namespace <String[]>]
 [-ReportType <StorageReportReportTypeEnum[]>] [-FileScreenAuditDaysSince <UInt32>]
 [-FileScreenAuditUser <String[]>] [-FileGroupIncluded <String[]>] [-FileOwnerUser <String[]>]
 [-FileOwnerFilePattern <String>] [-PropertyName <String>] [-FolderPropertyName <String>]
 [-PropertyFilePattern <String>] [-LargeFileMinimum <UInt64>] [-LargeFilePattern <String>]
 [-LeastAccessedMinimum <UInt32>] [-LeastAccessedFilePattern <String>] [-MostAccessedMaximum <UInt32>]
 [-MostAccessedFilePattern <String>] [-QuotaMinimumUsage <UInt32>]
 [-ReportFormat <StorageReportReportFormatsEnum[]>] [-MailTo <String>] [-Schedule <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-FsrmStorageReport** cmdlet changes settings of a storage report on the server.
You cannot change the settings of an interactive storage report or a storage report that does not have a schedule.
You must specify the *Name* parameter and at least one additional parameter.

## EXAMPLES

### Example 1: Change report types of a storage report
```
PS C:\> Set-FsrmStorageReport -Name "Get storage usage info" -ReportTypes @(LargeFiles, DuplicateFiles)
```

This command changes the storage report named "Get storage usage info" to generate a LargeFiles and a DuplicateFiles report.

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

### -FileGroupIncluded
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

### -FileOwnerFilePattern
Specifies a string of files to include in the file by owner report.
You can use the wildcard characters \* and ?
in the string.
If you specify this parameter, you must set FilesByOwner for the *ReportType* parameter.

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

### -FileOwnerUser
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

### -FileScreenAuditDaysSince
Specifies the minimum number of days since the audit event to include in the report.
If you specify this parameter, you must set FileScreenAuditFiles for the *ReportType* parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileScreenAuditUser
Specifies an array of user email addresses to include audit events for.
The default value is an empty list, which indicates all users.
If you specify this parameter, you must set FileScreenAuditFiles for the *ReportType* parameter.

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

### -FolderPropertyName
Specifies a name of the classification property name to report on for a folder by property report.
Specify the value of the Name property in an **FsrmClassificationPropertyDefinition** object.
If you specify this parameter, you must set FoldersByProperty for the *ReportType* parameter.

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
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LargeFileMinimum
Specifies the minimum file size to include in the large file report.
If you specify this parameter, you must set LargeFiles for the *ReportType* parameter.

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

### -LargeFilePattern
Specifies a string of files to include in the large file report.
You can use the wildcard characters \* and ?
in the string.
If you specify this parameter, you must set LargeFiles for the *ReportType* parameter.

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

### -LeastAccessedFilePattern
Specifies a string of files to include in the least frequently accessed report.
You can use the wildcard characters \* and ?
in the string.
If you specify this parameter, you must set LeastRecentlyAccessed for the *ReportType* parameter.

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

### -LeastAccessedMinimum
Specifies the minimum number of days since the report was last accessed, to include in the least frequently accessed report.
If you specify this parameter, you must set LeastRecentlyAccessed for the *ReportType* parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailTo
Specifies a semicolon-separated list of email addresses for the recipients of an email.
\[Admin Email\] is a valid email address.

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

### -MostAccessedFilePattern
Specifies a string of files to include in the most frequently accessed report.
You can use the wildcard characters \* and ?
in the string.
If you specify this parameter, you must set MostRecentlyAccessed for the *ReportType* parameter.

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

### -MostAccessedMaximum
Specifies the maximum number of days since the report was last accessed, to include in the most frequently accessed report.
If you specify this parameter, you must set MostRecentlyAccessed for the *ReportType* parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the storage reports.
If you do not specify a name for a storage report, the server generates a standard name.
You must specify this parameter if you specify the *Interactive* parameter.

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
Specifies an array of namespaces that are part of the scope of the report.
Each string must be either a value of the FolderType property on the server, the string "All Shares", or a static path.
The FolderType properties must be in the format \[Folder type property name=\<value\>\].

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

### -PropertyFilePattern
Specifies a string of files to include in the file by property report.
You can use the wildcard characters \* and ?
in the string.
If you specify this parameter, you must set FilesByProperty for the *ReportType* parameter.

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

### -PropertyName
Specifies the name of the classification property to report on for a file by property report.
Specify the value of the Name property in a **FsrmClassificationPropertyDefinition** object.
If you specify this parameter, you must set FilesByProperty for the *ReportType* parameter.

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

### -QuotaMinimumUsage
Specifies the minimum quota usage level to include in the quota usage report.
If you specify this parameter, you must set QuotaUsage for the *ReportType* parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportFormat
Specifies an array of report formats that the classification report produces.
The acceptable values for this parameter are:

- DHTML
- HTML
- XML
- CSV
- Text

```yaml
Type: StorageReportReportFormatsEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: DHtml, Html, Text, Csv, XML

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportType
Specifies the types of reports that the action generates.
Specify this parameter only if you set the *Type* parameter to Report.The acceptable values for this parameter are:

- DuplicateFiles
- FilesByFileGroup
- FilesByOwner
- FilesByProperty
- LargeFiles
- LeastRecentlyAccessed
- MostRecentlyAccessed
- QuotaUsage

```yaml
Type: StorageReportReportTypeEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: LargeFiles, FilesByFileGroup, LeastRecentlyAccessed, MostRecentlyAccessed, QuotaUsage, FilesByOwner, DuplicateFiles, FileScreenAuditFiles, FilesByProperty, FoldersByProperty

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Schedule
Specifies a File Server Resource Manager (FSRM) scheduled task object that describes the schedule for running the storage report.
Use the **New-FsrmScheduledTask** cmdlet to create a scheduled task object.

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

### Microsoft.Management.Infrastructure.CimInstance#Root/Microsoft/Windows/FSRM/MSFT_FSRMStorageReport

## NOTES

## RELATED LINKS

[Get-FsrmStorageReport](./Get-FsrmStorageReport.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[Remove-FsrmStorageReport](./Remove-FsrmStorageReport.md)

[Start-FsrmStorageReport](./Start-FsrmStorageReport.md)

[Stop-FsrmStorageReport](./Stop-FsrmStorageReport.md)

[Wait-FsrmStorageReport](./Wait-FsrmStorageReport.md)

