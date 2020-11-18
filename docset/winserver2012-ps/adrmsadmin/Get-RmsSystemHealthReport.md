---
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
ms.assetid: B017BBE0-7879-44F2-996D-82CC934E2AA3
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-RmsSystemHealthReport

## SYNOPSIS
Generates a system health report of the Active Directory Rights Management Services (AD RMS) cluster.

## SYNTAX

```
Get-RmsSystemHealthReport [-StartTime <DateTime>] [-EndTime <DateTime>] [-ServerName <String>]
 [-RequestType <String>] [-DomainName <String>] [-UserName <String>] -ReportType <ReportType>
 [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet generates a report that contains information about the overall health of the Active Directory Rights Management Services (AD RMS) cluster.

To obtain the report, set the parameters for the type of report you want and then set the Path parameter to the AD RMS provider drive subpath "\<PSDrive\>:\Report" where \<PSDrive\> is the provider drive ID.
You can also specify a relative path.
For example, "." specifies the current location.

The cmdlet generates a summary report for the specified ReportType unless you specify RequestType, ServerName, DomainName, or UserName.

## EXAMPLES

### --------------  EXAMPLE 1 --------------
```
C:\PS>Get-RmsSystemHealthReport -Path . -ReportType Request
```

This command displays a summary report of requests processed by the AD RMS cluster.

### --------------  EXAMPLE 2 --------------
```
C:\PS>Get-RmsSystemHealthReport -Path . -StartTime 12/1/2008 -EndTime 12/31/2008 -ReportType User
```

This command displays a summary report of user activity during calendar year 2008.

### --------------  EXAMPLE 3 --------------
```
C:\PS>Get-RmsSystemHealthReport -Path . -ReportType User -Domain Research
```

This command displays a summary report of requests by all users in the Research domain.

## PARAMETERS

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

### -DomainName
Specifies the domain name of the e-mail of the user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -EndTime
Specifies the end of a time period for a system health report.
This parameter specifies a time value.
See the description of the StartTime parameter for information on specifying a time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Path
Specifies a provider drive and path or relative path on the current drive.
This parameter is required.
Use a dot (.) to specify the current location.
This parameter does not accept wildcards and has no default value.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportType
Specifies the type of report.
Possible values are "Server", "Request", "Domain", and "User".

```yaml
Type: ReportType
Parameter Sets: (All)
Aliases: 
Accepted values: Server, Request, Domain, User

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RequestType
Specifies the type of user request, such as "Acquire License", "Pre-Certify", and "Get Client Licensor Certificate".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server for which you are requesting the health report.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StartTime
Specifies the beginning of a time period.
This parameter specifies a time value.

The following examples show commonly-used syntax to specify a time.
Time is assumed to be local time unless otherwise specified.
When a time value is not specified, the time is assumed to 12:00:00 AM local time.
When a date is not specified, the date is assumed to be the current date.

- "4/17/2006"

- "Monday, April 17, 2006"

- "2:22:45 PM"

- "Monday, April 17, 2006 2:22:45 PM"

These examples specify the same date and the time without the seconds.

- "4/17/2006 2:22 PM"

- "Monday, April 17, 2006 2:22 PM"

- "2:22 PM"

The following example shows how to specify a date and time by using the RFC1123 standard.
This example defines time by using Greenwich Mean Time (GMT).

-"Mon, 17 Apr 2006 21:22:48 GMT"

The following example shows how to specify a round-trip value as Coordinated Universal Time (UTC).
This example represents Monday, April 17, 2006 at 2:22:48 PM UTC.

-"2000-04-17T14:22:48.0000000"

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UserName
Specifies the user name for which you are requesting a system health report.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

[ADRMSAdmin Module](./ADRMSAdmin.md)

