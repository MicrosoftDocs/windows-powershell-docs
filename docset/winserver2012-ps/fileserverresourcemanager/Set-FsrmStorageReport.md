---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 151AEC03-AAB5-4C2D-B2E9-ACD6C203A125
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-FsrmStorageReport

## SYNOPSIS
Changes settings of a storage report.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-FsrmStorageReport [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-FileGroupIncluded <String[]>]
 [-FileOwnerFilePattern <String>] [-FileOwnerUser <String[]>] [-FileScreenAuditDaysSince <UInt32>]
 [-FileScreenAuditUser <String[]>] [-FolderPropertyName <String>] [-LargeFileMinimum <UInt64>]
 [-LargeFilePattern <String>] [-LeastAccessedFilePattern <String>] [-LeastAccessedMinimum <UInt32>]
 [-MailTo <String>] [-MostAccessedFilePattern <String>] [-MostAccessedMaximum <UInt32>] [-Namespace <String[]>]
 [-PassThru] [-PropertyFilePattern <String>] [-PropertyName <String>] [-QuotaMinimumUsage <UInt32>]
 [-ReportFormat <StorageReportReportFormatsEnum[]>] [-ReportType <StorageReportReportTypeEnum[]>]
 [-Schedule <CimInstance>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-FsrmStorageReport [-AsJob] [-CimSession <CimSession[]>] [-FileGroupIncluded <String[]>]
 [-FileOwnerFilePattern <String>] [-FileOwnerUser <String[]>] [-FileScreenAuditDaysSince <UInt32>]
 [-FileScreenAuditUser <String[]>] [-FolderPropertyName <String>] [-LargeFileMinimum <UInt64>]
 [-LargeFilePattern <String>] [-LeastAccessedFilePattern <String>] [-LeastAccessedMinimum <UInt32>]
 [-MailTo <String>] [-MostAccessedFilePattern <String>] [-MostAccessedMaximum <UInt32>] [-Namespace <String[]>]
 [-PassThru] [-PropertyFilePattern <String>] [-PropertyName <String>] [-QuotaMinimumUsage <UInt32>]
 [-ReportFormat <StorageReportReportFormatsEnum[]>] [-ReportType <StorageReportReportTypeEnum[]>]
 [-Schedule <CimInstance>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-FsrmStorageReport** cmdlet changes settings of a storage report on the server.
You cannot change the settings of an interactive storage report or a storage report that does not have a schedule.
You must specify the **Name** parameter and at least one additional parameter.

## EXAMPLES

### Example 1: Change report types of a storage report
```
PS C:\>Set-FsrmStorageReport -Name "Get storage usage info" -ReportTypes @(LargeFiles, DuplicateFiles)
```

This command changes the storage report named "Get storage usage info" to generate a LargeFiles and a DuplicateFiles report.

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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the storage reports.
If you do not specify a name for a storage report, the server generates a standard name.
You must specify this parameter if you specify the **Interactive** parameter.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertyName
Specifies the name of the classification property to report on for a file by property report.
Specify the value of the Name property in a **FsrmClassificationPropertyDefinition** object.
If you specify this parameter, you must set FilesByProperty for the **ReportType** parameter.

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
If you specify this parameter, you must set QuotaUsage for the **ReportType** parameter.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMStorageReport

## NOTES

## RELATED LINKS

[Get-FsrmStorageReport](./Get-FsrmStorageReport.md)

[New-FsrmStorageReport](./New-FsrmStorageReport.md)

[Start-FsrmStorageReport](./Start-FsrmStorageReport.md)

[Wait-FsrmStorageReport](./Wait-FsrmStorageReport.md)

[Stop-FsrmStorageReport](./Stop-FsrmStorageReport.md)

[Remove-FsrmStorageReport](./Remove-FsrmStorageReport.md)

