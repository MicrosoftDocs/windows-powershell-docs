---
external help file: FSRM_Cmdlets.xml
Module Name: FileServerResourceManager
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/new-fsrmstoragereport?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-FsrmStorageReport

## SYNOPSIS
Creates a storage report on the server.

## SYNTAX

```
New-FsrmStorageReport [-Name] <String> [-AsJob] [-CimSession <CimSession[]>] [-FileGroupIncluded <String[]>]
 [-FileOwnerFilePattern <String>] [-FileOwnerUser <String[]>] [-FileScreenAuditDaysSince <UInt32>]
 [-FileScreenAuditUser <String[]>] [-FolderPropertyName <String>] [-Interactive] [-LargeFileMinimum <UInt64>]
 [-LargeFilePattern <String>] [-LeastAccessedFilePattern <String>] [-LeastAccessedMinimum <UInt32>]
 [-MailTo <String>] [-MostAccessedFilePattern <String>] [-MostAccessedMaximum <UInt32>]
 [-PropertyFilePattern <String>] [-PropertyName <String>] [-QuotaMinimumUsage <UInt32>]
 [-ReportFormat <StorageReportReportFormatsEnum[]>] [-Schedule <CimInstance>] [-ThrottleLimit <Int32>]
 -Namespace <String[]> -ReportType <StorageReportReportTypeEnum[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-FsrmStorageReport** cmdlet creates a storage report on the server.
A storage report job specifies a set of directories that the server analyzes to generate one or more report types that help you to better understand how storage is utilized in the specified directories.
You can configure report jobs to run according to a schedule or on demand.

## EXAMPLES

### Example 1: Create a large files storage report
```
The first command gets a **DateTime** object and stores it in the **$d** variable.
PS C:\>$d = Get-Date "12:00am"

This second command returns a **FsrmScheduledTask** object that describes a schedule that runs the task at midnight on the first day of the month. The command stores results in the **$task** variable.
PS C:\>$task = New-FsrmScheduledTask -Time $d.ToFileTimeUtc() -Monthly 1

The third command creates a LargeFiles storage report named "Find large files" on C:\Shares. The command sets the schedule for the report stored in the **$task** variable, and limits the report to files larger than 10MB.
PS C:\>New-FsrmStorageReport -Name "Find large files" -Namespace @("C:\Shares") -Schedule $task -ReportType @("LargeFiles") -LargeFileMinimum 10MB
```

This example creates a LargeFiles storage report that the server runs monthly and restricts the report to files larger than 10MB.

### Example 2: Create a large files storage report by using a namespace condition
```
The first command gets a **DateTime** object and stores it in the **$d** variable.
PS C:\>$d = get-date "12:00am"

This second command returns an **FsrmScheduledTask** object that describes a schedule that runs the task at midnight on the first day of the month. The command stores results in the **$task** variable.
PS C:\>$task = new-FsrmScheduledTask -Time $d.ToFileTimeUtc() -Monthly 1

The third command creates a LargeFiles storage report named "Find large files" that generates a Large Files report on any folders whose Folder Usage property includes the User Data value. The command sets the schedule for the report stored in the **$task** variable.
PS C:\>New-FsrmStorageReport -Name "Find large files" -Namespace @("[FolderUsage=User Data]") -Schedule $task -ReportType @("LargeFiles")
```

This example creates a LargeFiles storage report that the server runs monthly and reports on any folders whose Folder Usage property includes the User Data value.
This example creates a LargeFiles storage report that the server runs monthly and restricts the report to files larger than 10MB.

### Example 3: Create a storage report for files from a file group
```
The first command gets a **DateTime** object and stores it in the **$d** variable.
PS C:\>$d = get-date "12:00am"

This second command returns a **FsrmScheduledTask** object that describes a schedule that runs the task at midnight on the first day of the month. The command stores results in the **$task** variable.
PS C:\>$task = new-FsrmScheduledTask -Time $d.ToFileTimeUtc() -Monthly 1

The third command creates a storage report named "Find large files" and file groups on the folder C:\Shares. The command sets the schedule for the report stored in the **$task** variable, set the report type to LargeFiles and a FilesByFileGroup, limits the report to files larger than 10MB, and restricts the FilesByFileGroup report to include only files from the "Text files file" group.
PS C:\>New-FsrmStorageReport -Name "Find large files and file groups" -Namespace @("C:\Shares") -Schedule $task -ReportType @("LargeFiles", "FilesByFileGroup") -LargeFileMinimum 10MB -FileGroupIncluded "Text files"
```

This example creates a storage report that the server runs monthly and generates a LargeFiles and a FilesByFileGroup report.

### Example 4: Create an interactive storage report
```
PS C:\>New-FsrmStorageReport -Name "Find large files" -Namespace @("C:\Shares") -Interactive -ReportType @("LargeFiles")
```

This command creates a storage report named "Find large files" that the server runs immediately.
The command creates a LargeFile storage report for the folder C:\Shares.

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
You can use the wildcard characters * and ?
in the string.
If you specify this parameter, you must set FilesByOwner for the **ReportType** parameter.

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
Specifies an array of users, in **Domain\User** format, to include files for in the file by owner report.
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
If you specify this parameter, you must set FileScreenAuditFiles for the **ReportType** parameter.

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
If you specify this parameter, you must set FileScreenAuditFiles for the **ReportType** parameter.

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
If you specify this parameter, you must set FoldersByProperty for the **ReportType** parameter.

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
If you specify this parameter, you must set LargeFiles for the **ReportType** parameter.

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
You can use the wildcard characters * and ?
in the string. 
If you specify this parameter, you must set LargeFiles for the **ReportType** parameter.

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
You can use the wildcard characters * and ?
in the string. 
If you specify this parameter, you must set LeastRecentlyAccessed for the **ReportType** parameter.

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
If you specify this parameter, you must set LeastRecentlyAccessed for the **ReportType** parameter.

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
You can use the wildcard characters * and ?
in the string.
If you specify this parameter, you must set MostRecentlyAccessed for the **ReportType** parameter.

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
If you specify this parameter, you must set MostRecentlyAccessed for the **ReportType** parameter.

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
You must specify this parameter if you specify the **Interactive** parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
You can use the wildcard characters * and ?
in the string.
If you specify this parameter, you must set FilesByProperty for the **ReportType** parameter.

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
If you specify this parameter, you must set FilesByProperty for the **ReportType** parameter.

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
If you specify this parameter, you must set QuotaUsage for the **ReportType** parameter.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportType
Specifies the types of reports that the action generates.
Specify this parameter only if you set the **Type** parameter to Report.The acceptable values for this parameter are:
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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Schedule
Specifies a File Server Resource Manager (FSRM) scheduled task object that describes the schedule for running the storage report.
Use the New-FsrmScheduledTask cmdlet to create a scheduled task object.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMStorageReport

## NOTES

## RELATED LINKS

[New-FsrmScheduledTask](./New-FsrmScheduledTask.md)

