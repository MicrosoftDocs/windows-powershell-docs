---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FsrmStorageReport.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmstoragereport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-FsrmStorageReport
---

# New-FsrmStorageReport

## SYNOPSIS
Creates a storage report on the server.

## SYNTAX

```
New-FsrmStorageReport [-Name] <String> -Namespace <String[]> [-Interactive]
 -ReportType <StorageReportReportTypeEnum[]> [-FileScreenAuditDaysSince <UInt32>]
 [-FileScreenAuditUser <String[]>] [-FileGroupIncluded <String[]>] [-FileOwnerUser <String[]>]
 [-FileOwnerFilePattern <String>] [-PropertyName <String>] [-FolderPropertyName <String>]
 [-PropertyFilePattern <String>] [-LargeFileMinimum <UInt64>] [-LargeFilePattern <String>]
 [-LeastAccessedMinimum <UInt32>] [-LeastAccessedFilePattern <String>] [-MostAccessedMaximum <UInt32>]
 [-MostAccessedFilePattern <String>] [-QuotaMinimumUsage <UInt32>]
 [-ReportFormat <StorageReportReportFormatsEnum[]>] [-MailTo <String>] [-Schedule <CimInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-FsrmStorageReport** cmdlet creates a storage report on the server.
A storage report job specifies a set of directories that the server analyzes to generate one or more report types that help you to better understand how storage is utilized in the specified directories.
You can configure report jobs to run according to a schedule or on demand.

## EXAMPLES

### Example 1: Create a large files storage report
```powershell
# The first command gets a **DateTime** object and stores it in the $d variable.
PS C:\> $d = Get-Date "12:00am"

# This second command returns a **FsrmScheduledTask** object that describes a schedule that runs the task at midnight on the first day
# of the month. The command stores results in the $task variable.
PS C:\> $task = New-FsrmScheduledTask -Time $d -Monthly 1

# The third command creates a LargeFiles storage report named "Find large files" on C:\Shares.
# The command sets the schedule for the report stored in the $task variable, and limits the
# report to files larger than 10MB.
PS C:\> New-FsrmStorageReport -Name "Find large files" -Namespace @("C:\Shares") -Schedule $task -ReportType @("LargeFiles") -LargeFileMinimum 10MB
```

This example creates a LargeFiles storage report that the server runs monthly and restricts the report to files larger than 10MB.

### Example 2: Create a large files storage report by using a namespace condition
```powershell
# The first command gets a **DateTime** object and stores it in the $d variable.
PS C:\> $d = get-date "12:00am"

# This second command returns an **FsrmScheduledTask** object that describes a schedule
# that runs the task at midnight on the first day of the month. The command stores results in
# the $task variable.
PS C:\> $task = new-FsrmScheduledTask -Time $d -Monthly 1

# The third command creates a LargeFiles storage report named "Find large files" that generates a
# Large Files report on any folders whose Folder Usage property includes the User Data value.
# The command sets the schedule for the report stored in the $task variable.
PS C:\> New-FsrmStorageReport -Name "Find large files" -Namespace @("[FolderUsage=User Data]") -Schedule $task -ReportType @("LargeFiles")
```

This example creates a LargeFiles storage report that the server runs monthly and reports on any folders whose Folder Usage property includes the User Data value.
This example creates a LargeFiles storage report that the server runs monthly and restricts the report to files larger than 10MB.

### Example 3: Create a storage report for files from a file group
```powershell
# The first command gets a **DateTime** object and stores it in the $d variable.
PS C:\> $d = get-date "12:00am"

# This second command returns a **FsrmScheduledTask** object that describes a schedule that
# runs the task at midnight on the first day of the month. The command stores results in
# the $task variable.
PS C:\> $task = new-FsrmScheduledTask -Time $d -Monthly 1

# The third command creates a storage report named "Find large files" and file groups on th
# folder C:\Shares. The command sets the schedule for the report stored in the $task variable,
# set the report type to LargeFiles and a FilesByFileGroup, limits the report to files larger
# than 10MB, and restricts the FilesByFileGroup report to include only files from the
# "Text files file" group.
PS C:\> New-FsrmStorageReport -Name "Find large files and file groups" -Namespace @("C:\Shares") -Schedule $task -ReportType @("LargeFiles", "FilesByFileGroup") -LargeFileMinimum 10MB -FileGroupIncluded "Text files"
```

This example creates a storage report that the server runs monthly and generates a LargeFiles and a FilesByFileGroup report.

### Example 4: Create an interactive storage report
```powershell
PS C:\> New-FsrmStorageReport -Name "Find large files" -Namespace @("C:\Shares") -Interactive -ReportType @("LargeFiles")
```

This command creates a storage report named "Find large files" that the server runs immediately.
The command creates a LargeFile storage report for the folder C:\Shares.
The LargeFile storage report is saved to the **C:\StorageReports\Interactive** folder

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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Interactive
Indicates that the report is interactive.
When you specify this parameter, the report does not require a schedule, the report cannot be modified, the report is generated immediately when you run this cmdlet, and the server removes the report automatically from the system when it finishes running the report.

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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the storage report.
If you do not specify a name, the server generates a standard name.
You must specify this parameter if you specify the *Interactive* parameter.

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

### -Namespace
Specifies an array of namespaces that are part of the scope of the report.
Each string must be either a value of the FolderType property on the server, the string "All Shares", or a static path.
The FolderType properties must be in the format \[Folder type property name=\<value\>\].

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PropertyName
Specifies the name of the classification property to report on for a file by property report.
Specify the value of the Name property in an **FsrmClassificationPropertyDefinition** object.
If you specify this parameter, you must set FilesByProperty for the *ReportType* parameter.

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
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportType
Specifies the types of reports that the action generates.
Specify this parameter only if you set the *Type* parameter to Report.The acceptable values for this parameter are:

- DuplicateFiles
- FilesByFileGroup
- FilesByOwner
- FilesByProperty
-	FileScreenAuditFiles
- FoldersByProperty
- LargeFiles
- LeastRecentlyAccessed
- MostRecentlyAccessed
- QuotaUsage

```yaml
Type: StorageReportReportTypeEnum[]
Parameter Sets: (All)
Aliases:
Accepted values: LargeFiles, FilesByFileGroup, LeastRecentlyAccessed, MostRecentlyAccessed, QuotaUsage, FilesByOwner, DuplicateFiles, FileScreenAuditFiles, FilesByProperty, FoldersByProperty

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String[]

### System.Management.Automation.SwitchParameter

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.StorageReportReportTypeEnum[]

### System.UInt32

### System.UInt64

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.StorageReportReportFormatsEnum[]

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS

[Get-FsrmStorageReport](./Get-FsrmStorageReport.md)

[New-FsrmScheduledTask](./New-FsrmScheduledTask.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[Remove-FsrmStorageReport](./Remove-FsrmStorageReport.md)

[Set-FsrmStorageReport](./Set-FsrmStorageReport.md)

[Start-FsrmStorageReport](./Start-FsrmStorageReport.md)

[Stop-FsrmStorageReport](./Stop-FsrmStorageReport.md)

[Wait-FsrmStorageReport](./Wait-FsrmStorageReport.md)

